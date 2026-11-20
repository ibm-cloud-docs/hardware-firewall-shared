---

copyright:
  years: 2017, 2026
lastupdated: "2026-11-20"

keywords: help, support, troubleshooting

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Getting help and support for hardware firewalls
{: #getting-help-and-support-for-hardware-firewall-shared}

If you experience an issue or have questions when you use a hardware firewall, you can use the following resources before you open a support case.
{: shortdesc}

* Troubleshoot with [{{site.data.keyword.paver_full}}](http://paver.cloud.ibm.com){: external}. {{site.data.keyword.paver}} is an embedded AI operator that understands your account context, creates a resolution plan, and executes changes on your behalf, while always requiring your approval before touching your live environment.
* Review the [FAQs](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-faqs-for-hardware-firewall-shared).
* Review [known limitations](/docs/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared).
* Check the status of the {{site.data.keyword.cloud_notm}} platform and resources on the [Status page](/status){: external}.
* Review [Stack Overflow](https://stackoverflow.com/questions/tagged/ibm-cloud){: external} to see whether other users experienced the same problem. When you ask a question, tag the question with `ibm-cloud` and `hardware-firewall` so that it is seen by the {{site.data.keyword.cloud_notm}} development teams.

If you still cannot resolve the problem, you can open a support case. For more information, see [Creating support cases](/docs/support?topic=support-open-case&interface=ui). To provide feedback, see [Submitting feedback](/docs/overview?topic=overview-feedback).

## Providing support case details for hardware firewalls
{: #support-case-details-hardware-firewall}

To ensure a timely resolution to your issue, include the following information in your support case for issues with your hardware firewall:

1. The public IP address of the server that the issue affects.
1. Network diagnostic details, including the source IP address, destination IP address, destination port and protocol, and output from network tools such as `ping`, `traceroute`, `mtr`, `nmap`, or `netcat`.
1. Hardware firewalls can affect traffic on the same VLAN as other servers that do not have a hardware firewall applied. Indicate whether the affected server has a hardware firewall applied, or if it is on the same VLAN as another server with a hardware firewall applied.
