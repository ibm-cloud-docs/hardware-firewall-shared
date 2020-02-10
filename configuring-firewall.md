---

copyright:
  years: 2017
lastupdated: "2019-11-12"

keywords: configure, configuring, firewall, add, adding, edit, editing, rules, ports, common

subcollection: hardware-firewall-shared

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:note: .note}
{:important: .important}

# Configuring the Hardware Firewall
{: #configuring-the-hardware-firewall-shared-}

Configuring your Hardware Firewall is as simple as creating a set of rules to allow access to certain IP addresses/ports from specific internet addresses while denying traffic from other sources.
{: shortdesc}

## Adding a Firewall to a Server
{: #adding-a-firewall-to-a-server}

To add a firewall to a server, follow the steps in [Getting Started](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared). If you receive an error, see the [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) and [Getting help and support](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-help-and-support-for-hardware-firewall-shared-).

## Editing Rules
{: #editing-rules}

When a firewall is first added to a server, a set of rules is initially put in place that allows all traffic to reach the server. The rules can then be edited to control the traffic reaching the server.

Ensure the "status" indicates that the firewall is "Processing All Rules." Users can choose to bypass the rules in the event that implemented rules have an unintended impact on their environment by clicking **Bypass Rules** in the **Actions** drop-down.

1. From your browser, open the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com){:new_window} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Select **Devices > Device List** and click on the firewall protected device you want to configure.
4. In the **Firewall** tab, ensure the "Status" indicates that the firewall is "Processing All Rules."  
  The page displays the current rules in effect for IPv4 and IPv6 addresses. If no rules are implemented, a faded placeholder is displayed. At this point, links are available to edit the current rules.  This list of rules is known as the 'working config'. A 'working config' is a set of rules that is in the process of being created but has not yet been applied to the firewall. A user may edit, add, and delete rules until the rule set is completed.

     Rules are displayed in the order in which they are processed, with lower numbered rules having precedence over higher
     number rules (if rule one allows a packet through, rules two and beyond are ignored by the packet).

     The fields are:

      **Order** - This field contains the rule number.  Rules can be moved up or down the list with the provided arrows.

      **Action** - This select list is used to 'permit' or 'deny' traffic matching this rule.

      **Source** - This field can be either 'any' or a specific IP address or the network address for a specific subnet.

      **Destination** - This field selects the destination IP (see [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) if there are issues).

      **CIDR** - This field indicates the standard CIDR notation for the selected source/destination.

      **Port Range** - These two fields indicate the range of ports (between 1 and 65535) that the rule will apply to.

      **Protocol** - This field selects the protocol the rule will apply to (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).

      **Notes:** Freeform field to enter any note about this rule.

4. Click on a rule to edit it or click on the plus sign at the bottom of the table to add an additional rule. Clicking on the minus icon will delete the rule. The rules are automatically validated as you enter them.

5. Once the 'working config' is complete, press the **Update Rules** button to have the 'working config' applied to the firewall. The rules should take effect within two minutes.

## Common Ports
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
| VNC Web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 or 10000 ||
