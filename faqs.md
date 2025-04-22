---

copyright:
  years: 2017, 2025
lastupdated: "2025-04-22"

keywords: faqs, firewall, ips, traffic, public, private, bandwidth, vpn, nat

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for Hardware Firewall
{: #faqs-for-hardware-firewall-shared}

The following frequently asked questions can help you when you work with your Hardware Firewall.
{: shortdesc}

## What is a firewall?
{: #faqs-what}
{: faq}

A firewall is a network device that is connected upstream from a server. The firewall blocks unwanted traffic from a server before the server is reached.

## Why use a firewall?
{: #faqs-why}
{: faq}

The primary advantage of having a firewall is that your server handles only “good” traffic. This means that your resource is solely being used for its intended purpose as opposed to handling unwanted traffic, too.

## What firewall products does IBM offer?
{: #products}
{: faq}
{: support}

You can find a detailed comparison of all firewall products that are offered in [Exploring firewalls](/docs/fortigate-10g?topic=fortigate-10g-exploring-firewalls).

## Is the Hardware Firewall compatible with IBM's load balancer products?
{: #compatibility}
{: faq}
{: support}

Yes. The Hardware Firewall is compatible with the cloud load-balancing service, local load balancer, and the Citrix Netscaler VPX and MPX.

## Can portable IP’s be protected by the Hardware Firewall?
{: #portable}
{: faq}
{: support}

No. Portable IPs are not available for protection because they can be moved between servers. Exceptions are made on a case-by-case basis as there are numerous caveats and require more details about the customer's system design.

## Can I have a Hardware Firewall and a Network Gateway associated with the same VLAN?
{: #vlan}
{: faq}
{: support}

No, it is not possible to have a Hardware Firewall and a Network Gateway device that is assigned to the same VLAN. The expanded functions of the Network Gateway device provide firewall features for your network in place of a standard firewall.

## Does public traffic pass through my load balancer or Hardware Firewall first?
{: #faqs-public-traffic}
{: faq}

Coming from the public internet in, the load-balancing products are first. The Hardware Firewall products are next, and the NetScaler products are last (along with the customers' servers).

## Does a server's uplink port speed need to match the Hardware Firewall?
{: #uplink}
{: faq}
{: support}

The Hardware Firewall does need to match the public uplink speed of the server. However, because it protects only the public side of the network, the public uplink speed is what must match the firewall selection. Customers can create a case to request a downgrade of only the public interfaces if wanted.

## Does IBM Cloud charge for firewall bandwidth?
{: #bandwidth}
{: faq}
{: support}

The Hardware Firewall and FortiGate Security Appliance (FSA) 1G are not metered for bandwidth. FSA 10G is charged for firewall bandwidth after 20 TB is used. Also, these products can reduce total bandwidth use by limiting the traffic that servers must respond to.

## How do I upgrade the uplink of my Hardware Firewall?
{: #faqs-upgrade-uplink}
{: faq}

The Hardware Firewall is locked to the public uplink port speed of a server. You can upgrade in place by cancelling the firewall, upgrading the port speed for the server, and ordering a new firewall. Alternatively, you can deploy a new server with the wanted uplinks and associated firewall.

## Is High Availability possible with the Hardware Firewall?
{: #faqs-ha}
{: faq}

No. The Hardware Firewall platform is enterprise-grade and highly durable, but true High Availability (redundant devices) is not an option for the Hardware Firewall. For HA, a Hardware Firewall (High Availability) or FortiGate Security Appliance (High Availability) is required. The Network Gateway product also has an HA option with firewall capabilities.

## I am running a hypervisor on an IBM Cloud server. Will the Hardware Firewall protect the virtual machines that run on my hypervisor?
{: #faqs-hypervisor}
{: faq}

No. Portable IPs are used for the VMs in a hypervisor environment and portable IPs are not protected by the hardware firewall. A FortiGate Security Appliance is recommended.

## What are the unavailable ports in my Windows Firewall?
{: #greyed-out}
{: faq}
{: support}

IBM Cloud offers many different services that you can use with your server, including EVault, SNMP, and Nagios monitoring. These services require that our internal systems communicate with your server to some degree. The unavailable ports that you see in the Exceptions list are ports that are open on the internal network port only. They are still blocked on the public (internet) network connection. Because the internal network is a secured network, having these ports open is considered secure.

These ports generally cannot be modified; however, if you reset the firewall rules, it clears them from the Exceptions list. Beware that resetting the firewall rules might have an adverse effect, not only on these additional services, but also might cause other issues with your server (depending on its current configuration).

## What Hardware Firewall options are available for 10 Gbps servers?
{: #faqs-10g-options}
{: faq}

FSA 10G is the only option to support 10 Gbps servers for both public and private traffic. If 10 Gbps is only required on the private network (for database, backup, storage, and so on), then customers can request a downgrade of only their public uplinks and order any of the Hardware Firewall products.

## What IP ranges do I allow through the firewall?
{: #ip}
{: faq}
{: support}

For the list of IP addresses and IP ranges to allow through the firewall, go [here](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-ibm-cloud-ip-ranges){: external}.

## What VPN options are included with each firewall product?
{: #faqs-VPN}
{: faq}

Not all firewalls offer VPN and not all VPN options are the same. The general options for VPN are:

* Each customer receives unlimited SSL VPN connections to our private network. These connections can be established by clicking the VPN link while logged in to the IBM Cloud console.
* IBM Cloud also offers a basic multi-tenant IPsec VPN service.
* The FortiGate Security Appliance 1G provides SSL and IPsecVPN options with Public network access only (no access to the IBM Cloud Private network). FSA 10G provides SSL and IPsecVPN options with Public or Private network access.
* The Network Gateway provides SSL, IPsec, and OpenVPN capabilities on the public or private network
* The NetScaler products can provide SSL and IPsecVPN on the public or private network.
* Customers can also deploy a VPN solution on to a server within their IBM Cloud environment.

## Which firewall products support public-to-private NAT, private VLAN segmentation, or both?
{: #faqs-NAT}
{: faq}

Fortigate Security Appliance 10G supports NAT and private VLAN segmentation. The other firewall offerings support only public traffic.
