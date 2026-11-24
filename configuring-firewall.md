---

copyright:
  years: 2017, 2026
lastupdated: "2026-11-20"

keywords: configure, configuring, firewall, add, adding, edit, editing, rules, ports, common

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Configuring the hardware firewall
{: #configuring-the-hardware-firewall-shared}

Configuring your hardware firewall involves creating rules that allow or deny traffic from specific IP addresses and ports.
{: shortdesc}

## Adding a firewall to a server
{: #adding-a-firewall-to-a-server}

To add a firewall to a server, follow the steps in [Getting started with hardware firewalls](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started). If you receive an error, see [Known limitations with hardware firewalls](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared) and [Getting help and support for hardware firewalls](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-help-and-support-for-hardware-firewall-shared).

## Editing rules
{: #editing-rules}

When a firewall is first added to a server, a set of rules is put in place that allows all traffic to reach the server. You can edit the rules to control the traffic that reaches the server.

Verify that the status indicates **Processing All Rules**. You can choose to bypass the rules if active rules cause unintended network disruption by selecting **Bypass Rules** from the **Actions** menu.

1. In your browser, open the [{{site.data.keyword.cloud_notm}} catalog](/catalog){: external} and log in to your account.
1. Select the **Navigation Menu** icon ![Menu icon](../../icons/icon_hamburger.svg), then click **Infrastructure > Classic Infrastructure**.
1. From the devices list, click the firewall-protected device that you want to configure.
1. In the **Add-ons** section, click **Firewall details**.
1. The **Firewall Details** page shows the active rules for IPv4 and IPv6 addresses. If no rules are implemented, a yellow status icon displays with a **Bypassing all rules** message.

   Rules are evaluated in numerical order, with lower-numbered rules having precedence over higher-numbered rules. For example, if rule 1 allows a packet through, subsequent rules are ignored.

   Priority
   :   The rule number. Lower-numbered rules have precedence over higher-numbered rules.

   Action
   :   Permits or denies traffic that matches the rule.

   Source
   :   `Any`, a specific IP address, or the network address for a specific subnet.

   Destination
   :   The destination IP address. For more information, see [Known limitations with hardware firewalls](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared).

   CIDR
   :   The standard CIDR notation for the selected source or destination.

   Port range
   :   The range of ports (between 1 and 65535) that the rule applies to.

   Protocol
   :   The protocol that the rule applies to (`TCP`, `GRE`, `ICMP`, `UDP`, `PPTP`, `AH`, or `ESP`).

   Notes
   :   An optional description for the rule.

1. Click the **Actions** menu icon at the end of the rule row to edit or delete the rule. Click **Add rule** above the table to add a rule. Rules are automatically validated as you enter them.
1. Click **Save** or **Add** to apply the rule to the firewall. Changes take effect within two minutes.

The **Delete** action is disabled if the firewall includes only one rule.
{: note}

## Common ports
{: #common-ports}

| Protocol | Port |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| Remote Desktop | 3389 |
| PostgreSQL | 5432 |
| VNC web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 or 10000 |
{: caption="Common ports" caption-side="bottom"}
