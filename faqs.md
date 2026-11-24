---

copyright:
  years: 2017, 2026
lastupdated: "2026-11-20"

keywords: faqs, firewall, ips, traffic, public, private, bandwidth, vpn, nat

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for hardware firewalls
{: #faqs-for-hardware-firewall-shared}

The following frequently asked questions can help you when you work with your hardware firewall.
{: shortdesc}

## What is a firewall?
{: #faqs-what}
{: faq}

A firewall is a network device that is connected upstream from a server. The firewall blocks unwanted traffic from a server before the server is reached.

## Why use a firewall?
{: #faqs-why}
{: faq}

The primary advantage of having a firewall is that your server handles only "good" traffic. This means that your resource is used for its intended purpose rather than handling unwanted traffic.

## What firewall products does IBM Cloud offer?
{: #products}
{: faq}
{: support}

You can find a detailed comparison of all firewall products that are offered in [Exploring firewalls](/docs/fortigate-10g?topic=fortigate-10g-exploring-firewalls).

## Is the hardware firewall compatible with load-balancing products?
{: #compatibility}
{: faq}
{: support}

Yes. The hardware firewall is compatible with the cloud load-balancing service, local load balancer, and Citrix NetScaler VPX and MPX.

## Can portable IPs be protected by the hardware firewall?
{: #portable}
{: faq}
{: support}

No. Portable IPs cannot be protected because they can be moved between servers.

## Can I have a hardware firewall and a network gateway associated with the same VLAN?
{: #vlan}
{: faq}
{: support}

No, it is not possible to have a hardware firewall and a network gateway device assigned to the same VLAN. The expanded functions of the network gateway device provide firewall features for your network in place of a standard firewall.

## Does public traffic pass through my load balancer or hardware firewall first?
{: #faqs-public-traffic}
{: faq}

Coming from the public internet in, the load-balancing products are first, the hardware firewall products are next, and the NetScaler products are last (along with customer servers).

## Does a server's uplink port speed need to match the hardware firewall?
{: #uplink}
{: faq}
{: support}

The hardware firewall must match the public uplink speed of the server. Because it protects only the public side of the network, the public uplink speed is what must match the firewall selection.

## Does IBM Cloud charge for firewall bandwidth?
{: #bandwidth}
{: faq}
{: support}

The hardware firewall and FortiGate Security Appliance (FSA) 1G are not metered for bandwidth. FSA 10G is charged for firewall bandwidth after 20 TB is used. These products can also reduce total bandwidth use by limiting the traffic that servers must respond to.

## How do I upgrade the uplink of my hardware firewall?
{: #faqs-upgrade-uplink}
{: faq}

The hardware firewall is locked to the public uplink port speed of a server. You can upgrade in place by canceling the firewall, upgrading the port speed for the server, and ordering a new firewall. Alternatively, you can deploy a new server with the required uplinks and associated firewall.

## Is high availability possible with the hardware firewall?
{: #faqs-ha}
{: faq}

No. True high availability (redundant devices) is not an option for the shared hardware firewall. For high availability, a dedicated hardware firewall (High Availability) or FortiGate Security Appliance (High Availability) is required. The network gateway product also has a high availability option with firewall capabilities.

## Will the hardware firewall protect virtual machines that run on a hypervisor?
{: #faqs-hypervisor}
{: faq}

No. Portable IPs are used for virtual machines in a hypervisor environment, and portable IPs are not protected by the hardware firewall. A FortiGate Security Appliance is recommended.

## What are the unavailable ports in my Windows Firewall?
{: #greyed-out}
{: faq}
{: support}

{{site.data.keyword.cloud_notm}} offers many different services that you can use with your server, including EVault, SNMP, and Nagios monitoring. These services require internal systems to communicate with your server. The unavailable ports shown in the Exceptions list are open on the internal network port only. They are blocked on the public internet network connection.

## What hardware firewall options are available for 10 Gbps servers?
{: #faqs-10g-options}
{: faq}

FSA 10G is the only option to support 10 Gbps servers for both public and private traffic. If 10 Gbps is required only on the private network (for database, backup, or storage), you can request a downgrade of your public uplinks and order any of the hardware firewall products.

## What IP ranges do I allow through the firewall?
{: #ip}
{: faq}
{: support}

For the list of IP addresses and IP ranges to allow through the firewall, see [{{site.data.keyword.cloud_notm}} IP ranges (Classic infrastructure)](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-ibm-cloud-ip-ranges){: external}.

## What VPN options are included with each firewall product?
{: #faqs-VPN}
{: faq}

Not all firewalls offer VPN, and VPN options vary across products:

* Unlimited SSL VPN connections to the private network through the {{site.data.keyword.cloud_notm}} console.
* Multi-tenant IPsec VPN service.
* FortiGate Security Appliance 1G provides SSL and IPsec VPN options with public network access only. FSA 10G provides SSL and IPsec VPN options with public or private network access.
* Network Gateway provides SSL, IPsec, and OpenVPN capabilities on the public or private network.
* NetScaler products can provide SSL and IPsec VPN on the public or private network.

## Which firewall products support public-to-private NAT or private VLAN segmentation?
{: #faqs-NAT}
{: faq}

FortiGate Security Appliance 10G supports NAT and private VLAN segmentation. Other firewall offerings support public traffic only.
