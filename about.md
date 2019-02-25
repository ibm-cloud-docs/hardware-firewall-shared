---

copyright:
  years: 2017
lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# About Hardware Firewall (Shared)
{: #about-hardware-firewall-shared-}

A Hardware Firewall (Shared) is a network device that is connected upstream from a server. The firewall blocks unwanted traffic from a server before the traffic ever reaches the server. The main advantage to having a Hardware Firewall is that a server only has to handle 'good' traffic and no resources are wasted dealing with the 'bad' traffic. 

The Hardware Firewall (Shared) leverages a multi-tenant enterprise platform to protect an individual server.  It can be purchased with the server or added on later.  It delivers virtualized network security through its Virtual Domain (VDOM) technology, providing virtualized security domains that are separately provisioned and managed.  

Because there are multiple customers associated with the hardware, if the firewall fails or is overwhelmed by an attack, every customer that shares a Hardware Firewall (Shared) instance may be impacted. 

Up to 79 firewall rules can be configured for the primary and statically routed IP addresses assigned to the server. Reports for Shared Firewalls are available based on the activity of a single IP for a selected date range.
Customers can manage the firewall through two ways: SoftLayer Control Portal (the firewall tab under the protected server details page) and SoftLayer SLDN APIs.

Since monthly server bandwidth is recorded at the server switch port, traffic blocked by the Hardware Firewall (Shared) is not counted against your monthly allotments, eliminating the need to pay for unwanted traffic.

## Overview and Features

**Intended Use:** Single Server Primary IP Protection

**User Interface:** Integrated into SoftLayer Control Portal and SoftLayer API

**Features:** Stateful Packet Inspection, Ingress Firewall Rules, IPv4, IPv6, Basic Logging

**Throughput:** 10Mbps, 100Mbps, 1000Mbps, or 2000Mbps 

It is required that the throughput of Hardware Firewall (Shared) instance match the uplink speed of the server the firewall is being added to.