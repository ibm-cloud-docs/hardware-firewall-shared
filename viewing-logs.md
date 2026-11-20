---

copyright:
  years: 2017, 2026
lastupdated: "2026-11-20"

keywords: viewing, logs, reports, firewall, troubleshooting

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Viewing log reports for hardware firewalls
{: #viewing-log-reports-for-hardware-firewall}
{: help}
{: support}

Logs for your hardware firewall are available on a per-IP basis by navigating to the protected device **Firewall Details** page and clicking **Actions > Firewall Logs**.
{: shortdesc}

Logs are presented in CSV format and contain the following fields:

Event type
:   The action taken by the firewall (such as `Deny`).

Protocol
:   The protocol used for communication (such as `TCP`, `PING`, or `UDP`).

Source IP address
:   The IP address where the packet originated.

Source port
:   The port where the packet originated.

Destination IP
:   The intended target IP address for the packet.

Destination port
:   The intended port for the packet.

Creation date
:   The date and time of the action in 24-hour format.
