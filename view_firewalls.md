---

copyright:
  years: 2017
lastupdated: "2019-11-12"

keywords: views, firewalls, overview, vlan,

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Viewing your various firewalls
{: #viewing-your-various-firewalls}

You can identify the Hardware Firewalls in use on an account and their associated VLANs, as well as identify unprotected VLANs and plan the deployment of a firewall solution.
{: shortdesc}

## Firewall overview by VLAN
{: #firewall-overview-by-vlan}

To get an overview of firewalls on your system, as well as initiate basic management:

1. From your browser, open the [IBM Cloud catalog](https://cloud.ibm.com){: external} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.
3. Select **Network > IP Management > VLANs**.

To view only public VLANS, click on the **Filter** drop down and enter `fcr` for **Primary Router**.
{: tip}

Each row represents a VLAN in your infrastructure. IBM© Cloud populates the **VLAN NUMBER** and **PRIMARY ROUTER** information automatically indicating the true VLAN number and the router that it is configured on. Use the **NAME** field to define a recognizable name.

The **GATEWAY/FIREWALL** column contains details about which hardware firewall protection is in place, for example:

**Individually Protected Servers** indicates that one or more servers is utilizing a Hardware Firewall and that there is not a Hardware Firewall (Dedicated), FortiGate Security Appliance, or Network Gateway in place. VLAN firewalls and network gateways are not able to be placed on a VLAN that has individually protected servers.

**Firewall-vlanXXXX.networklayer** indicates that there is a Hardware Firewall (Dedicated) or FortiGate Security Appliance in place. Only one VLAN firewall or Network Gateway can be associated with a VLAN, but a server can be protected on the public VLAN by a VLAN firewall and associated on the private network with a Network Gateway.

**GatewayName** indicates the VLAN is associated with that Network Gateway.

## Individually protected servers view
{: #individually-protected-servers-view}

On the VLANs screen, identify a row with **Individually Protected Servers** in the **Gateway/Firewall** column and click on the associated VLAN number link. This will display the details for the VLAN including the associated devices.

From here, you can click on each device and review whether a firewall is in place for that particular Server.

Once you have clicked on a device, scroll to the bottom of the Configuration tab. You will see **Firewall** in the Addons section with **Installed** or **Not installed** for the status. **Not Installed** indicates that no firewall is in place for this device. **Installed** indicates that a firewall is in place and you will have a **Firewall details** button. It will redirect you to the "Firewall Details" page where you can manage the firewall configuration.

## Dedicated firewall view
{: #dedicated-firewall-view}

On the VLANs screen, identify a row with **Firewall-vlanXXXX.networklayer.com** in the **Gateway/Firewall** column and click on that firewall. You are presented with either a Hardware Firewall (Dedicated) or a FortiGate Security Appliance. The device details include the associated Router, VLAN, and IPv4/IPv6 Subnets, the devices associated with that VLAN, and the controls for routing traffic through or around the firewall.

**FortiGate Security Appliance** devices will have the management IP, username, and password.  Management is completed through the management GUI or SSH-based console.

## Network gateway view
{: #network-gateway-view}

On the VLANs screen, identify a row with the **Gateway/Firewall** column populated by a Network Gateway device name and click on that network gateway. You are then taken to the interface displaying associated frontend (FCR) and backend (BCR) VLANs and Network Gateway management options.
