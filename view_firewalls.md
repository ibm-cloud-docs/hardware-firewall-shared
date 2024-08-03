---

copyright:
  years: 2017, 2024
lastupdated: "2024-08-02"

keywords: views, firewalls, overview, vlan,

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Viewing your various firewalls
{: #viewing-your-various-firewalls}

You can identify the Hardware Firewalls in use on an account and their associated VLANs, and identify unprotected VLANs and plan the deployment of a firewall solution.
{: shortdesc}

## Firewall overview by VLAN
{: #firewall-overview-by-vlan}

To get an overview of firewalls on your system and initiate basic management:

1. From your browser, open the [IBM Cloud catalog](/catalog){: external} and log in to your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the upper left, then click **Classic Infrastructure**.
3. Select **Network > IP Management > VLANs**.

To view only public VLANS, click the **Filter** menu and enter `fcr` for **Primary Router**.
{: tip}

Each row represents a VLAN in your infrastructure. IBM© Cloud populates the **VLAN NUMBER** and **PRIMARY ROUTER** information automatically indicating the true VLAN number and the router that it is configured on. Use the **NAME** field to define a recognizable name.

The **GATEWAY/FIREWALL** column contains details about which hardware firewall protection is in place, for example:

**Individually Protected Servers** indicates that one or more servers is using a Hardware Firewall and that there is not a FortiGate Security Appliance, or Network Gateway in place. You cannot place VLAN firewalls and network gateways on a VLAN with individually protected servers.

**Firewall-vlanXXXX.networklayer** indicates that there is a FortiGate Security Appliance in place. Only one VLAN firewall or Network Gateway can be associated with a VLAN, but a server can be protected on the public VLAN by a VLAN firewall and associated on the private network with a Network Gateway.

**GatewayName** indicates that the VLAN is associated with that Network Gateway.

## Individually protected servers view
{: #individually-protected-servers-view}

On the VLANs screen, identify a row with **Individually Protected Servers** in the **Gateway/Firewall** column and click the associated VLAN number link. The details for the VLAN including the associated devices are displayed.

From here, you can click each device and review whether a firewall is in place for that particular Server.

After you click a device, scroll to the end of the Configuration tab. You see **Firewall** in the Addons section with **Installed** or **Not installed** for the status. **Not Installed** indicates that a firewall isn't in place for this device. **Installed** indicates that a firewall is in place and you have a **Firewall details** button. It will redirect you to the "Firewall Details" page where you can manage the firewall configuration.

## Dedicated firewall view
{: #dedicated-firewall-view}

On the VLANs screen, identify a row with **Firewall-vlanXXXX.networklayer.com** in the **Gateway/Firewall** column and click that firewall. You are presented with a FortiGate Security Appliance. The device details include the associated Router, VLAN, and IPv4/IPv6 Subnets, the devices associated with that VLAN, and the controls for routing traffic through or around the firewall.

**FortiGate Security Appliance** devices have the management IP, username, and password. Management is completed through the management GUI or SSH-based console.

## Network gateway view
{: #network-gateway-view}

On the VLANs screen, identify a row with the **Gateway/Firewall** column with a Network Gateway device name and click that network gateway. You are then taken to the interface that displays associated front end (FCR) and backend (BCR) VLANs and Network Gateway management options.
