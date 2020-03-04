---

copyright:
  years: 2017
lastupdated: "2019-11-12"

keywords: bypass, bypassing, firewall, rules, enable, enabling

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

# Bypassing the Hardware Firewall rules
{: #bypassing-the-hardware-firewall-shared-rules}

You can bypass the rules of your Hardware Firewall by following the instructions here.
{: shortdesc}

1. From your browser, open the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com){:new_window} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Select **Devices > Device List** and click on the firewall protected device you want to bypass.
4.  In the **Firewall** tab, click on the **Actions** dropdown menu and choose **Bypass Rules**. Click **Yes** to confirm the action. Bypassing the rules takes approximately two minutes to take effect. While in bypass mode, the "Status" will be "Bypassing All Rules".

## Enabling the rules again
{: #enable-the-rules-again}

To enable the rules again, follow the instructions above to reach the Firewall tab of the device and click on the **Actions** dropdown menu and choose **Process Rules**. The "Status" should change back to "Processing All Rules" within two minutes.
