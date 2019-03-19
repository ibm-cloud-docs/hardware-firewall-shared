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

# Hardware Firewall (Shared) 已知限制
{: #known-limitations-with-hardware-firewall-shared-}

无法将 Hardware Firewall (Shared) 部署到满足以下任何条件的 VLAN 的服务器上。 

* 当前与网关、Hardware Firewall 或 FortiGate Security Appliance 关联。
* 包含超过 30 台服务器。
* 具有大于 /28 的主要子网。

在这些实例中，必须针对防火墙建立新的 VLAN，或者必须选择其他产品。

Hardware Firewall (Shared) 具有以下更多限制： 

* 可移植子网不受保护
* 不可用于 10Gb 服务器
* 每个 Hardware Firewall (Shared) 最多 79 个防火墙规则
* 处理 ARP 的方式导致与 Windows 网络负载均衡 (NLB) 不兼容。
