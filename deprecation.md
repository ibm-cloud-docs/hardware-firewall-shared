---

copyright:
  years: 2026
lastupdated: "2026-03-03"

keywords: hardware-firewall, firewall, deprecation

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Deprecation of IBM shared hardware firewall
{: #deprecation-hardware-shared-firewall}

IBM shared hardware firewall has reached End of Marketing (EOM) and no longer accepts new orders. It is deprecated on IBM Cloud as of 17 December 2025. The service will no longer be supported by {{site.data.keyword.cloud}} as of 31 December 2026 and any instances of the shared hardware firewall that are still running will no longer receive updates for security issues.
{: shortdesc}

## Important dates
{: #deprecation-timeline}

| Stage | Date | Description |
| ---------------- | ----------------- | ------------------------------------------------------------ |
| Deprecation announcement | 17 December 2025 | Announcement of the shared hardware firewall deprecation. Existing instances will continue to run. |
| End of marketing | 17 December 2025 | No new instances of shared hardware firewall can be created or purchased. Existing instances will continue to run. |
| End of support | 31 December 2026 | Running instances of shared hardware firewall are no longer supported or updated. |
{: caption="Deprecation timeline for IBM shared hardware firewall" caption-side="bottom"}

## Deprecation details
{: #deprecation-details}

Review the following details about the IBM shared hardware firewall deprecation:

* Effective 17 December 2025, IBM Cloud no longer accepts new orders for IBM shared hardware firewall.
* Any existing instances created before 17 December 2025 will continue to run and receive support until 31 December 2026.
* After 31 December 2026, support for IBM shared hardware firewall devices including updates, bug fixes, and technical support for the service will no longer be available.
* No support cases can be opened after 31 December 2026.

## Migration options for FSA 10 Gbps
{: #migration-options-hardware-shared-firewall}

IBM shared hardware firewall is expected to reach end of support on 31 December 2026. To keep your network secure and avoid any business disruptions, we recommend planning your migration well before the end of support date.

The following alternatives help you migrate to a suitable firewall offering:

1. Recommended option:
   * Migrate to the Fortinet Virtual Firewall (vFSA). See [Getting started with vFSA](/docs/vfsa?topic=vfsa-getting-started-vfsa) and [license types](https://cloud.ibm.com/docs/vfsa?topic=vfsa-getting-started-vfsa#choosing-vfsa-license).
   * Use Forti-Converter Service that is included in the enterprise license to migrate security policies and configurations from Fortinet hardware to the Fortinet virtual appliance.
      * Register an account in the [FortiConverter Service](https://service.forticonverter.com/){: external} for customer self-managed service.
      * For help with creating a migration ticket, see the [Forti-Converter Service Ticket Guide](https://docs.fortinet.com/document/forticonverter-service/25.1.0/online-help/783478/create-forticonverter-service-ticket){: external}.
1. Other virtual firewall options:
   * Juniper vSRX with Content Security Bundle: Enhanced security features, VLAN protection, HA configurations, IPS/IDS/UTM capabilities. See [Getting started with Juniper vSRX](/docs/vsrx?topic=vsrx-getting-started-vsrx).
   * Virtual Router Appliance (VRA 5600): Enterprise router with firewall, VPN, traffic shaping, and policy-based    routing. See [Getting started with Virtual Router Appliance](/docs/virtual-router-appliance?topic=virtual-router-appliance-getting-started-vra).

Contact [IBM Cloud Support](https://www.ibm.com/cloud/support){: external} for any guidance or to know more about the migration process.
