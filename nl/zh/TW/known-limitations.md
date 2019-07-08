---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: limitations, firewall, gateway, fortigate, fsa, subnet, vlan, problems, issues

subcollection: hardware-firewall-shared

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:download: .download}

# Hardware Firewall 的已知限制
{: #known-limitations-with-hardware-firewall-shared-}

Hardware Firewall 無法部署到符合下列任一準則之 VLAN 上的伺服器中。

* 目前與「網路閘道」、Hardware Firewall 或 FortiGate Security Appliance 相關聯。
* 包含 30 台以上的伺服器。
* 具有大於 /28 的主要子網路。

在這些實例中，必須為「防火牆」建立新的 VLAN，或者必須選取另一個產品。

Hardware Firewall 的進一步限制包括：

* 可攜式子網路不受保護
* 不適用於 10Gb 伺服器
* 每個 Hardware Firewall 最多有 79 個防火牆規則
* 由於處理 ARP 的方式而與「Windows 網路負載平衡 (NLB)」不相容
* 規則目的地子網路僅限於受保護伺服器的公用 IP。Hardware Firewall (Dedicated) 沒有這項限制。
* 不接受每小時計費的伺服器。Hardware Firewall 可套用到每月計費的伺服器。
