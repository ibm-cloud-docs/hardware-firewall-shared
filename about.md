---

copyright:
  years: 2017, 2026
lastupdated: "2026-11-20"

keywords: about, overview, features, firewall

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# About hardware firewalls
{: #about-hardware-firewall-shared}

Effective 17 December 2025, the {{site.data.keyword.cloud}} shared hardware firewall reached End of Marketing (EOM) and no longer accepts new orders. Additionally, this service will reach End of Support (EOS) on 31 December 2026. After this date, it will no longer be supported or available for use on {{site.data.keyword.cloud_notm}}. For migration information, see [Migrate off a shared hardware firewall](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-shared-fw-migration).
{: deprecated}

A hardware firewall is a network device that is connected upstream from a server. The firewall blocks unwanted traffic from a server before the traffic ever reaches the server. The main advantage to having a hardware firewall is that a server handles only "good" traffic and no resources are wasted dealing with "bad" traffic.
{: shortdesc}

The hardware firewall uses a multi-tenant enterprise platform to protect an individual server. It can be purchased with the server or added on later. It delivers virtualized network security through its Virtual Domain (VDOM) technology, providing virtualized security domains that are separately provisioned and managed.

Because multiple customers are associated with the hardware, if the firewall fails or is overwhelmed by an attack, every customer that shares a hardware firewall instance might be impacted.

Up to 79 firewall rules can be configured for the primary and statically routed IP addresses assigned to the server. Reports for firewalls are available based on the activity of a single IP for a selected date range.
You can manage the firewall through the {{site.data.keyword.cloud_notm}} console (the firewall tab under the protected server details page) or SoftLayer APIs.

Because monthly server bandwidth is recorded at the server switch port, traffic that is blocked by the hardware firewall is not counted against your monthly allotments, eliminating the need to pay for unwanted traffic.

## Overview and features
{: #overview-and-features}

Intended use
:   Single-server primary public IP protection.

User interface
:   Integrated into the {{site.data.keyword.cloud_notm}} console and APIs.

Features
:   Stateful packet inspection, ingress firewall rules, IPv4, IPv6, and basic logging.

Server network interface speeds
:   100 Mbps, 200 Mbps, 1000 Mbps, and 2000 Mbps. The throughput of a hardware firewall instance must match the uplink speed of the server that the firewall is added to.
