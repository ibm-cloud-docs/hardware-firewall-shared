---

copyright:
  years: 2017
lastupdated: "2021-02-24"

keywords: about, overview, features, firewall

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# About Hardware Firewall
{: #about-hardware-firewall-shared-}

A Hardware Firewall is a network device that is connected upstream from a server. The firewall blocks unwanted traffic from a server before the traffic ever reaches the server. The main advantage to having a Hardware Firewall is that a server handles only 'good' traffic and no resources are wasted dealing with the 'bad' traffic.
{: shortdesc}

The Hardware Firewall uses a multi-tenant enterprise platform to protect an individual server. It can be purchased with the server or added on later. It delivers virtualized network security through its Virtual Domain (VDOM) technology, providing virtualized security domains that are separately provisioned and managed.  

Because multiple customers are associated with the hardware, if the firewall fails or is overwhelmed by an attack, every customer that shares a Hardware Firewall instance might be impacted.

Up to 79 firewall rules can be configured for the primary and statically routed IP addresses assigned to the server. Reports for Firewalls are available based on the activity of a single IP for a selected date range.
Customers can manage the firewall through two ways: the IBM Cloud console (the firewall tab under the protected server details page) and SLDN APIs.

Since monthly server bandwidth is recorded at the server switch port, traffic that is blocked by the Hardware Firewall is not counted against your monthly allotments, eliminating the need to pay for unwanted traffic.

## Overview and features
{: #overview-and-features}

Intended Use: Single-Server Primary Public IP Protection

User Interface: Integrated into IBM Cloud console and APIs

Features: Stateful Packet Inspection, Ingress Firewall Rules, IPv4, IPv6, Basic Logging

Server Network Interface Speeds:* 100 Mbps, 200 Mbps, 1000 Mbps, and 2000 Mbps

It is required that the throughput of a Hardware Firewall instance match the uplink speed of the server the firewall is being added to.
