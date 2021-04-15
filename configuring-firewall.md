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

## Adding a firewall to a server
{: #adding-a-firewall-to-a-server}

To add a firewall to a server, follow the steps in [Getting Started](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started#getting-started). If you receive an error, see the [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-#known-limitations-with-hardware-firewall-shared-) and [Getting help and support](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-getting-help-and-support-for-hardware-firewall-shared-#getting-help-and-support-for-hardware-firewall-shared-).

## Editing rules
{: #editing-rules}

When a firewall is first added to a server, a set of rules is initially put in place that allows all traffic to reach the server. The rules can then be edited to control the traffic reaching the server.

Ensure the "status" indicates that the firewall is "Processing All Rules." Users can choose to bypass the rules in the event that implemented rules have an unintended impact on their environment by clicking **Bypass Rules** in the **Actions** drop-down.

1. From your browser, open the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com){:new_window} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Select **Devices > Device List** and click on the firewall protected device you want to configure.
4. In the **Add-ons** section, click **Firewall details**. It will redirect you to the firewall page. 
5. The Firewall Details page shows the current rules in effect for IPv4 and IPv6 addresses. If no rules are implemented, a yellow status icon will show with a "Bypassing all rules" message next to the device name on the top of the page. 

     Rules are displayed in the order in which they are processed, with lower numbered rules having precedence over higher
     number rules (if rule one allows a packet through, rules two and beyond are ignored by the packet).

     The fields are:

      **Priority** - This field contains the rule number. Lower numbered rules have precedence over higher numbered rules. 

      **Action** - This select list is used to 'permit' or 'deny' traffic matching this rule.

      **Source** - This field can be either 'any' or a specific IP address or the network address for a specific subnet.

      **Destination** - This field selects the destination IP (see [Known Limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) if there are issues).

      **CIDR** - This field indicates the standard CIDR notation for the selected source/destination.

      **Port Range** - These two fields indicate the range of ports (between 1 and 65535) that the rule will apply to.

      **Protocol** - This field selects the protocol the rule will apply to (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).

      **Notes:** Freeform field to enter any note about this rule.

6. Click on the Overflow menu icon at the end of the row of the firewall rule to edit or delete the rule. Click the **Add rule** button at the right top corner of the table to add an additional rule. The rules are automatically validated as you enter them.

7. Click the **Save** or **Add** buttons to save the rule and apply to the firewall. The rule addition or update should take effect within two minutes.

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
| VNC Web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 or 10000 ||
