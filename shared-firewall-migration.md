---

copyright:
  years: 2026
lastupdated: "2026-11-23"

keywords: migration, shared hardware firewall, classic security groups, host firewall, bare metal, virtual server, end of support, deprecation

subcollection: hardware-firewall-shared

content-type: tutorial
account-plan: paid
---

{{site.data.keyword.attribute-definition-list}}

# Migrate off the shared hardware firewall
{: #shared-fw-migration}
{: toc-content-type="tutorial"}

In this tutorial, you learn how to replace the shared hardware firewall on an {{site.data.keyword.cloud}} Classic server before it reaches End of Support. You review the options and put the replacement in place while the shared firewall is still filtering: Classic security groups for a virtual server, or an OS-level firewall for a bare metal server. You then bypass the shared firewall, verify that the replacement filters traffic the way you expect on its own, and cancel the shared firewall.
{: shortdesc}

**End of Support: 31 December 2026.** The shared hardware firewall reached End of Marketing on 17 December 2025 and reaches End of Support on 31 December 2026. Firewalls that remain active after this date will continue to operate without vendor support, maintenance updates, or availability guarantees. Because the product reached End of Marketing, a cancelled firewall cannot be reprovisioned. Ensure that your replacement filtering solution is in place and verified before you cancel the firewall.
{: important}

**Why this tutorial does not cover a move to VPC.** Moving a workload to {{site.data.keyword.cloud_notm}} VPC is a platform migration: new servers, new addressing and new networking. It does not replace a layer of inbound firewall rules on a Classic server that is staying where it is. This tutorial assumes you are keeping the server and replacing the filtering, so a move to VPC is out of scope.
{: note}

## Purpose
{: #shared-fw-purpose}

This tutorial is for the person who plans and carries out the replacement of a shared hardware firewall on a Classic server. It assumes you want to keep the filtering the firewall provides and need something else to provide it. It covers three things:

1. What the firewall did, so the replacement covers the same traffic.
1. The replacement options for a virtual server instance (VSI) and for a bare metal server, with the cost of each.
1. A procedure for the two low-cost paths, Classic security groups for a VSI and a host firewall for bare metal. You put the replacement in place while the shared firewall is still filtering, bypass the shared firewall, verify, and only then cancel it.

For a move to a gateway appliance, use this tutorial for the inventory and the cancel steps, and the FSA 10G to vFSA migration tutorial for the pattern of routing VLANs through the new gateway.

## What the firewall did
{: #shared-fw-behavior}

Build the replacement against this list. Each row comes from {{site.data.keyword.cloud_notm}}'s documentation for the product.

| Behavior | Detail |
|---|---|
| Scope | One server. It filters the primary public IP and statically routed IPs. |
| Portable subnets | Not protected. Traffic to a portable IP on the server passed unfiltered. |
| Network | Public side only. Private network traffic never crossed it. |
| Direction | Inbound rules only. It has no egress rules. |
| State | Stateful packet inspection. |
| Rule model | Numbered rules, permit or deny, lowest number first, first match applies. |
| Rule limit | 79 rules per firewall. |
| Protocols | TCP, UDP, ICMP, GRE, PPTP, AH, ESP. IPv4 and IPv6. |
| Logging | Denied-traffic log per IP, exported as CSV from the portal. |
| Bypass | The **Bypass Rules** action passes all traffic. **Process Rules** turns filtering back on. Each takes about two minutes. |
| High availability | None. |
{: caption="Shared hardware firewall behavior" caption-side="bottom"}

Two consequences for the migration:

* The equivalent rule set is the public inbound rules and nothing else. Private filtering and egress filtering are new scope. Add them only if you want them.
* A replacement that filters the whole public interface also filters portable IPs. Traffic to those IPs passed unfiltered before the move. List what runs on them before you start.

## Options
{: #shared-fw-options}

Two questions decide the path: is the server a VSI or bare metal, and how much of your network needs the filtering.

The shared firewall is a low-cost, per-server, easily editable public inbound firewall policy. The closest replacements are per-server too: Classic security groups for a VSI, and OS-level software firewalls like firewalld or Windows Defender Firewall for bare metal servers.

Many users already have security groups configured for their virtual servers, or OS-level software firewall rules configured for their bare metal servers. If you already have these in place, compare your existing rules against the shared firewall's rule list, address any rule gaps, and then proceed with the bypass, verification, and cancellation steps.

**Kubernetes and OpenShift worker nodes.** If the server is a worker node in an {{site.data.keyword.cloud_notm}} Kubernetes Service or Red Hat OpenShift on {{site.data.keyword.cloud_notm}} classic cluster, manage its public exposure the way the cluster documentation describes. See [What else can I do to reduce the surface for external attacks for Classic clusters?](/docs/containers?topic=containers-security#external-what-else) It lists three options: limit the number of apps you expose publicly, keep worker nodes private by connecting them to a private VLAN only, and limit public connectivity to a small pool of edge nodes. Classic clusters with a public VLAN also come with default Calico network policies on each worker node's public interface. They allow public inbound traffic only to cluster components such as NodePort, LoadBalancer and Ingress services, and you can add your own policies to restrict it further. See [Controlling traffic with network policies](/docs/containers?topic=containers-network_policies).
{: note}

A gateway appliance is a router and firewall deployed on dedicated bare metal hardware in a network pod. You associate public and private VLANs from that pod with the appliance and route traffic through it. You must configure and manage VLAN interfaces, subnet gateways, firewall policies, hardening configurations, and telemetry across every routed VLAN. Costs include the bare metal servers and software licensing. Managing a gateway appliance typically requires network engineering expertise to configure, harden, troubleshoot, monitor, and maintain the appliance, underlying host, and hypervisor.

Choose this option only if you have enough servers and VLANs to warrant managing a dedicated network appliance and have experience managing Classic gateway appliances.

### Virtual server instance
{: #shared-fw-vsi}

| Option | Scope | Cost | Fit |
|---|---|---|---|
| Classic security groups | Per interface, public and private | No charge | The default path. A per-server inbound policy on one VSI, the closest match to the shared firewall. |
| Gateway appliance: vFSA, vSRX, VRA, or bring your own | Every VLAN you route through it, public and private, in one pod | The bare metal server or servers plus licensing, billed monthly, and a network engineer to run it | Enough servers and VLANs to warrant managing your own network appliance, and experience running one. |
| Host firewall in the guest OS | The server itself | No charge | A second layer under any option above. |
{: caption="Replacement options for a virtual server instance" caption-side="bottom"}

Classic security groups are the only {{site.data.keyword.cloud_notm}} feature that matches the firewall on price and on per-server scope. The following table compares how each service behaves in terms of firewall rules and packet filtering:

| Shared hardware firewall | Classic security groups |
|---|---|
| Stateful. When a rule allows a packet in one direction, the response packet is allowed in the opposite direction. | Stateful, with the same behavior. |
| Permit and deny rules | Allow rules only |
| Rule order decides the result | Order does not matter. The least restrictive rule wins. |
| Inbound only. Outbound always passed. | Inbound and outbound. Everything not allowed is denied, outbound included. |
| Primary and static IPs only | The whole interface, portable IPs included |
| 79 rules | 50 rules per group, 5 groups per interface |
| Denied-traffic log | Audit log of configuration changes. No traffic log. |
| Takes effect in two minutes, no restart | The first attach to an interface needs a restart |
{: caption="Shared hardware firewall compared with Classic security groups" caption-side="bottom"}

### Bare metal server
{: #shared-fw-bare-metal}

{{site.data.keyword.cloud_notm}}'s documentation says: "You cannot assign security groups to bare metal servers." Security groups were developed specifically for the hypervisors that host the virtual server offering, at a level in the stack that isn't applicable to the bare metal offering.

| Option | Scope | Cost | Fit |
|---|---|---|---|
| Host firewall: nftables, firewalld, Windows Firewall | The server itself | No charge | The default path for one or two servers, where a gateway costs more than the servers it protects. |
| Gateway appliance: vFSA, vSRX, VRA, or bring your own | Every VLAN you route through it, public and private, in one pod | The bare metal server or servers plus licensing, billed monthly, and a network engineer to run it. Two servers for HA. | The only upstream filter left for Classic bare metal. Worth it only with enough servers and VLANs to warrant managing your own network appliance, and experience running one. |
{: caption="Replacement options for a bare metal server" caption-side="bottom"}

No {{site.data.keyword.cloud_notm}} product replaces the firewall for a single bare metal server at a comparable price. A gateway appliance filters upstream for every VLAN you route through it and costs a server, licensing, and engineering time. A host firewall costs nothing, but eliminates the upstream filtering that the hardware firewall provided.

Trade-offs of using a host firewall:

* The server receives and drops unwanted traffic itself. High-volume traffic or attacks that were previously filtered upstream now reach the server's CPU and network uplink.
* Anyone with root or administrator access on the server controls the firewall rules.
* An incorrect rule can lock administrators out, requiring recovery through the IPMI console over the private network.
* Virtual machines running on a bare metal hypervisor require their own firewall rules. (The shared firewall did not protect those either, because they use portable IPs.)

### FSA 10G is not a replacement option
{: #shared-fw-not-a-replacement}

Do not migrate to the FortiGate Security Appliance (FSA) 10G. It reached end of marketing on 17 December 2025 and reaches end of support on 31 December 2026, on the same schedule as the shared hardware firewall. If you require a Fortinet gateway appliance, migrate to the Virtual FortiGate Security Appliance (vFSA) instead.

## Prerequisites
{: #shared-fw-prerequisites}

* Access to the {{site.data.keyword.cloud_notm}} portal, or the `ibmcloud` CLI with the `sl` plugin, logged in to the account. Either one can do every step.
* Classic infrastructure permissions: **Manage Firewalls**, **Manage Firewall Rules**, **Cancel Services**, and **Manage Security Groups**.
* A maintenance window. The VSI path restarts the server once.
* A test host outside {{site.data.keyword.cloud_notm}} for the verification steps.
* For bare metal: working IPMI console access over the private network or the SSL VPN, tested before the window.

The examples use VSI ID `12345678`, firewall ID `vs:445566`, public IP `203.0.113.10` and an office network of `198.51.100.0/24`.

## Virtual servers: replace the shared firewall with security groups
{: #shared-fw-vsi-procedure}

You can do all of this in the {{site.data.keyword.cloud_notm}} portal instead of the CLI. The steps below show CLI commands because they are easy to copy and to keep as a record. The portal equivalents:

| Task | Where in the portal |
|---|---|
| View, bypass or cancel the firewall and its rules | **Classic Infrastructure > Devices > the server > Firewall** |
| Create a security group | **Classic Infrastructure > Security > Network Security > Security Groups > Create group** |
| Add rules to a group | The group's details page, **Create rule** |
| Attach a group to the server | Assign the group to the VSI's public interface. The portal warns that a restart is required. |
{: caption="Portal locations for security group tasks" caption-side="bottom"}

The portal's create form adds a rule that allows all outbound traffic unless you clear that option. That covers step 4.

## Export the firewall rules
{: #shared-fw-step-export}
{: step}

```sh
ibmcloud sl firewall list
ibmcloud sl firewall detail vs:445566 | tee shared-fw-445566-rules.txt
```
{: pre}

`list` prints a table with the columns `Firewall ID`, `Type`, `Features` and `Server/Vlan Id`. A shared firewall on a VSI has the type `Virtual Server - standard` and a firewall ID of the form `vs:445566`. Find the row whose `Server/Vlan Id` is your VSI ID and use its firewall ID. The number in the firewall ID is not the VSI ID.

`detail` prints one row per rule with the columns `#`, `action`, `protocol`, `src_ip`, `src_mask`, `dest` and `dest_mask`. The `dest` column holds the destination IP and port range as `IP:start-end`. Compare the saved output against the rules the portal shows. Keep the file. It is the only record of the rules after the firewall is cancelled, and the backout depends on it.

In the portal: **Classic Infrastructure > Devices > the server > Firewall**.

## Translate the rules
{: #shared-fw-step-translate}
{: step}

Work down the rule list in priority order and write each rule as a security group rule.

| Shared firewall rule | Security group rule |
|---|---|
| Permit TCP 443 from any | Ingress, TCP, ports 443 to 443, remote IP `0.0.0.0/0` |
| Permit TCP 22 from `198.51.100.0/24` | Ingress, TCP, ports 22 to 22, remote IP `198.51.100.0/24` |
| Permit ICMP from any | Ingress, ICMP, remote IP `0.0.0.0/0` |
| An IPv6 permit | The same rule with ether type `IPv6` |
| The final deny all | Nothing. A security group denies what it does not allow. |
| Permit GRE, ESP, or AH | Classic security groups do not support these protocol names directly (the API supports only `icmp`, `tcp`, `udp`, and `vrrp`). A rule without a protocol specified, restricted to the peer IP with `-r`, can cover this traffic. Test this rule in your environment before you rely on it. |
| A deny above a broader permit | No direct translation. See the following section on deny rules. |
{: caption="Translation of shared firewall rules to security group rules" caption-side="bottom"}

**Deny rules do not translate.** A pair such as "deny `192.0.2.50`, then permit any on TCP 443" depends on rule order. Security groups have no deny action and no order. Rewrite the pair as an allow list of the networks that need access, or keep the block in the host firewall or the application. Find the rules that fall in this case before the window.
{: attention}

**The initial rule set permits everything.** A new shared firewall starts with rules that allow all traffic. If the export shows only that, the firewall filtered nothing. Decide what to allow instead of copying it.
{: attention}

Count the result. More than 50 rules need a second group. An interface takes five groups.

## Create the group and its rules
{: #shared-fw-step-create-group}
{: step}

```sh
ibmcloud sl securitygroup create -n web01-public -d "Replaces shared hardware firewall on web01"
```
{: pre}

Expected: the command prints the new group with its ID. The examples use `7654321`.

```sh
ibmcloud sl securitygroup rule-add 7654321 -d ingress -p tcp -m 443 -M 443 -r 0.0.0.0/0
ibmcloud sl securitygroup rule-add 7654321 -d ingress -p tcp -m 22 -M 22 -r 198.51.100.0/24
ibmcloud sl securitygroup rule-add 7654321 -d ingress -p icmp -r 0.0.0.0/0
ibmcloud sl securitygroup rule-list 7654321
```
{: pre}

How `rule-add` treats its flags:

* `-d` is required and takes `ingress` or `egress`. Both directions take the same flags.
* `-r` is the remote address: the source for an ingress rule, the destination for an egress rule. Use `-s` for a remote security group instead. A rule takes one or the other.
* `-p` is required when you give `-m` or `-M`. With ports, it must be `icmp`, `tcp` or `udp`.
* For `icmp`, `-m` is the ICMP type and `-M` is the ICMP code.
* `-e` defaults to `IPv4`. Pass `-e IPv6` for an IPv6 rule.

Expected: `rule-list` shows one row per rule with direction `ingress`. Compare it line by line against the translation table from step 2.

## Allow outbound traffic
{: #shared-fw-step-outbound}
{: step}

The shared firewall never filtered outbound traffic. A security group denies it unless a rule allows it. Find the {{site.data.keyword.cloud_notm}} provided `allow_outbound` group:

```sh
ibmcloud sl securitygroup list
```
{: pre}

Expected: the list includes `allow_ssh`, `allow_http`, `allow_https`, `allow_outbound` and `allow_all`, each with an ID. Note the ID of `allow_outbound`. The examples use `1111111`.

**No outbound rule, no outbound traffic.** A VSI with inbound rules and no egress rule accepts connections and cannot open any. Updates, DNS lookups, and license checks fail. Replies to inbound connections still pass, because the rules are stateful, so the issue looks intermittent.
{: attention}

## Attach both groups to the public interface
{: #shared-fw-step-attach}
{: step}

Attach to the public interface only. The shared firewall did not filter the private network, and a group on the private interface must allow {{site.data.keyword.cloud_notm}} service traffic such as the update servers, NAS and monitoring.

```sh
ibmcloud sl securitygroup interface-add 7654321 -s 12345678 -i public
ibmcloud sl securitygroup interface-add 1111111 -s 12345678 -i public
ibmcloud sl securitygroup interface-list 7654321
```
{: pre}

Expected: `interface-list` shows the VSI's public network component.

## Restart the VSI
{: #shared-fw-step-restart}
{: step}

The first time a group attaches to an interface, the rules apply after a restart.

```sh
ibmcloud sl vs reboot 12345678
ibmcloud sl vs detail 12345678
```
{: pre}

Expected: the VSI returns to a running state. Both the shared firewall and the security groups now filter the public interface.

Inbound traffic to the VSI reaches the shared firewall first, then the security groups, then the VSI's interface. Outbound traffic from the VSI reaches the security groups first, then the shared firewall. A connection has to pass both.

## Put the shared firewall in bypass
{: #shared-fw-step-bypass}
{: step}

In the portal: **Classic Infrastructure > Devices > the server > Firewall > Actions > Bypass Rules**. Wait until the status reads `Bypassing All Rules`. {{site.data.keyword.cloud_notm}} documents about two minutes.

The security groups are now the only filter. This step is the reason the change is reversible: **Process Rules** restores the old filtering in two minutes.

## Verify
{: #shared-fw-step-verify}
{: step}

Run these from the test host outside {{site.data.keyword.cloud_notm}}.

```sh
nc -zv -w 5 203.0.113.10 443
nc -zv -w 5 203.0.113.10 3306
```
{: pre}

Expected: port 443 connects. Port 3306, or any port the rules do not allow, times out.

From the VSI:

```sh
curl -sS -o /dev/null -w "%{http_code}\n" https://www.ibm.com
```
{: pre}

Expected: an HTTP status code, which proves outbound traffic and DNS work.

Then test each service the server provides, each source network with restricted access, and each portable IP on the server.

## Monitor, then cancel
{: #shared-fw-step-cancel}
{: step}

Leave the firewall in bypass for a monitoring period. Use it to monitor and test until you have validated that all necessary traffic flows properly. Cancel the firewall after the monitoring period:

```sh
ibmcloud sl firewall cancel vs:445566
```
{: pre}

In the portal: **Firewall > Actions > Cancel firewall**, then choose immediate or the next billing cycle.

**Cancellation is permanent.** The product reached End of Marketing in December 2025. After the cancellation completes, the firewall cannot be restored. Do not cancel to see if anything breaks; bypass answers that question.
{: attention}

## Bare metal servers: replace the shared firewall with an OS-level firewall
{: #shared-fw-bare-metal-procedure}

The sequence matches the VSI path with the middle replaced: export, build, bypass, verify, monitor, cancel.

1. Export the rules as in step 1 above. A shared firewall on a bare metal server has the type `Hardware Server - standard` and a firewall ID of the form `server:445566`.
1. Confirm IPMI console access works. This is the way back in after a bad rule.
1. Identify the public interface. On a Classic Linux server with bonded uplinks it is often `bond1`. Check with `ip -br addr` and match the public IP.
1. Build the rule set on the server with its own firewall tooling. Scope the rules to the public interface so the private network stays as it was. If the server is a Kubernetes or OpenShift worker node, see the note under Options.
1. Load the rules with an automatic rollback in place, confirm a new session connects, then make them persistent.
1. Put the shared firewall in bypass, verify from the outside test host, monitor, and cancel, as in steps 7 to 9 above.

Unlike a security group, an OS-level firewall has deny rules and rule order. The shared firewall's rule list ports across one for one, deny rules included.

For Windows Server, build the same inbound rules in Windows Firewall and confirm they apply to the profile the public adapter uses.

## Moving to a gateway appliance
{: #shared-fw-gateway}

Order a vFSA, vSRX or VRA only when you have enough servers and VLANs to warrant managing your own network appliance, and the experience to run one. One gateway takes multiple VLANs from its pod, public and private.

* Routing a VLAN through the gateway moves every server on that VLAN behind it at the same time, firewalled or not. Plan one window per VLAN.
* Build the gateway or firewall appliance configuration from the ground up before the route-through, including VLAN interfaces with subnet gateways, firewall rules and security policies, and full configuration hardening. A vFSA denies traffic by default. A Vyatta with no firewall configured passes everything.
* The gateway must allow {{site.data.keyword.cloud_notm}} service traffic to the servers behind it, or provisioning and monitoring transactions stall.
* Cancel every per-server shared firewall on a VLAN before you associate that VLAN with the gateway. After all of them are cancelled, the VLAN is released from the shared firewall automatically. If that has not happened within 10 minutes, open a case to have {{site.data.keyword.cloud_notm}} Support manually reclaim the backend firewall. After the release, you can associate the VLAN with the gateway appliance and then set it to route through. Cover the gap between the cancel and the route-through with an OS-level firewall.
* No conversion tool applies. The shared firewall never exposed its FortiOS configuration, so the policy move is a manual rebuild from the exported rule list.

The cutover pattern is in the FSA 10G to vFSA migration tutorial. Product pages: Fortinet FortiGates, Juniper vSRX, Vyatta, BYOGWA.

## Backout
{: #shared-fw-backout}

Before the cancel step, every path backs out in minutes:

1. In the portal, choose **Firewall > Actions > Process Rules**. The status returns to `Processing All Rules` within two minutes.
1. For a VSI, detach the groups. A VSI with no group attached is not limited by security groups.

   ```sh
   ibmcloud sl securitygroup interface-remove 7654321 -s 12345678 -i public
   ibmcloud sl securitygroup interface-remove 1111111 -s 12345678 -i public
   ```
   {: pre}

1. For bare metal, flush the host rule set from the IPMI console.

After the cancel step there is no backout to the shared firewall. Fix the replacement rules instead, using the export from step 1 as the reference.

## Related
{: #shared-fw-related}

* Security groups overview: how the hypervisor enforces them.

## Sources
{: #shared-fw-sources}

{{site.data.keyword.cloud_notm}} documentation, read on 18 November 2026:

* [About hardware firewalls](/docs/hardware-firewall-shared): the end of marketing and end of support dates, features, the 79-rule limit, known limitations, FAQs, bypass and cancel procedures.
* [Exploring firewalls](/docs/fortigate-10g?topic=fortigate-10g-exploring-firewalls): {{site.data.keyword.cloud_notm}}'s feature comparison across the Classic firewall offerings.
* [Security groups guidelines](/docs/security-groups?topic=security-groups-security-groups-guidelines): stateful rules, rule order, the restart on first attach, no bare metal.
* [Security groups limits](/docs/security-groups?topic=security-groups-performance-limitations-for-security-groups): groups per interface and rules per group.
* [Getting started with vFSA](/docs/vfsa?topic=vfsa-getting-started-vfsa): license types.
* [Security for {{site.data.keyword.cloud_notm}} Kubernetes Service](/docs/containers?topic=containers-security#external-what-else) and [Controlling traffic with network policies](/docs/containers?topic=containers-network_policies): reducing the public attack surface of classic clusters, and the default Calico policies on worker nodes.
* {{site.data.keyword.cloud_notm}} CLI reference for `ibmcloud sl firewall` and `ibmcloud sl securitygroup`.
* [softlayer-cli](https://github.com/softlayer/softlayer-cli){: external} source for the `ibmcloud sl` plugin, `plugin/commands/firewall/`: the identifier format and the output columns of `firewall list`, `detail` and `cancel`.
