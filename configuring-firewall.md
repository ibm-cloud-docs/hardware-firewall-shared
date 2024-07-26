---

copyright:
  years: 2017
lastupdated: "2019-11-12"

keywords: configure, configuring, firewall, add, adding, edit, editing, rules, ports, common

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Configuring the Hardware Firewall
{: #configuring-the-hardware-firewall-shared-}

Configuring your Hardware Firewall is as simple as creating a set of rules to allow access to certain IP addresses or ports from specific internet addresses while denying traffic from other sources.
{: shortdesc}

## Adding a firewall to a server
{: #adding-a-firewall-to-a-server}

To add a firewall to a server, follow the steps in [Getting Started](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started#getting-started). If you receive an error, see the [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-#known-limitations-with-hardware-firewall-shared-) and [Getting help and support](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-help-and-support-for-hardware-firewall-shared-#getting-help-and-support-for-hardware-firewall-shared-).

## Editing rules
{: #editing-rules}

When a firewall is first added to a server, a set of rules is initially put in place that allows all traffic to reach the server. The rules can then be edited to control the traffic that reaches the server.

Make sure the "status" indicates that the firewall is "Processing All Rules." Users can choose to bypass the rules if implemented rules have an unintended impact on their environment by clicking **Bypass Rules** in the **Actions** menu.

1. From your browser, open the [IBM Cloud catalog](https://cloud.ibm.com){: external} and log in to your account.
1. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the upper left, then click **Classic Infrastructure**.
1. Select **Devices > Device List** and click the firewall-protected device that you want to configure.
1. In the **Add-ons** section, click **Firewall details**. It will redirect you to the firewall page.
1. The Firewall Details page shows the current rules in effect for IPv4 and IPv6 addresses. If no rules are implemented, a yellow status icon shows with a "Bypassing all rules" message next to the device name.

     Rules are displayed in the order in which they are processed, with lower numbered rules having precedence over higher
     number rules. For example, if rule one allows a packet through, the packet ignores rules two and beyond.

     The fields are:

      **Priority** - This field contains the rule number. Lower numbered rules have precedence over higher numbered rules.

      **Action** - This select list is used to 'permit' or 'deny' traffic that matches this rule.

      **Source** - This field can be either 'any' or a specific IP address or the network address for a specific subnet.

      **Destination** - This field selects the destination IP (see [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) if any issues arise).

      **CIDR** - This field indicates the standard CIDR notation for the selected source/destination.

      **Port Range** - These two fields indicate the range of ports (between 1 and 65535) that the rule applies to.

      **Protocol** - This field selects the protocol that the rule applies to (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).

      **Notes:** Freeform field to enter any note about this rule.

1. Click the **Actions** menu icon at the end of the row of the firewall rule to edit or delete the rule. Click **Add rule** at the upper right of the table to add a rule. The rules are automatically validated as you enter them.

1. Click the **Save** or **Add** buttons to save the rule and apply to the firewall. The rule addition or update takes effect within two minutes.

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
