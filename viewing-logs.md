---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: viewing, logs, reports, firewall, troubleshooting

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

# Viewing Log Reports for Hardware Firewall
{: #viewing-log-reports-for-hardware-firewall}

Logs are available on a per-IP basis by navigating to the protected device, selecting the **Firewall** tab, and clicking **Actions > Firewall Logs**. Logs are presented in .CSV format and contain the following:

**Event Type:** The action taken by the firewall (Deny)

**Protocol:** The protocol used for communication (TCP/PING/UDP/IRD/etc)

**Source IP Address:** IP where the packet originated

**Source Port:** Port where the packet originated

**Destination IP:** Intended target for the packet

**Destination Port:** Intended port for the packet

**Creation Date:** Date and time of action (24-hour format)
