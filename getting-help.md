---

copyright:
  years: 2017, 2024
lastupdated: "2024-08-02"

keywords: help, support, troubleshooting

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Getting help and support for Hardware Firewall
{: #getting-help-and-support-for-hardware-firewall-shared}

If you experience an issue or have questions when you use Hardware Firewall, you can use the following resources before you open a support case.
{: shortdesc}

* Review the [FAQs](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-faqs-for-hardware-firewall-shared).
* Review [known limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared).
* Check the status of the {{site.data.keyword.Bluemix_notm}} platform and resources by going to the [Status page](/status){: external}.

If you still can't resolve the problem, you can open a support case. For more information, see [Creating support cases](/docs/get-support?topic=get-support-open-case).

## Providing support case details for Virtual Router Appliance
{: #support-case-details-vra}

To ensure a timely resolution to your issue, include the following information in your support case for issues with your Hardware Firewall:

1. The public IP address of the server this issue affects.

1. To track down where an issue is happening across a network connection, we generally request the source IP address, destination IP address, the destination port and protocol, and the relevant output from network tools such as `ping`, `traceroute`, `mtr`, or `nmap` and `netcat`.

1. Hardware Firewalls can affect traffic on the same VLAN as other servers that do not have a Hardware Firewall applied. As a result, indicate whether the affected server has a Hardware Firewall that is applied, or if it is only on the same VLAN as another server with a Hardware Firewall applied.
