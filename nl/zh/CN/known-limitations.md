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

# Hardware Firewall 已知限制
{: #known-limitations-with-hardware-firewall-shared-}

无法将 Hardware Firewall 部署到满足以下任何条件的 VLAN 上的服务器。

* 当前与网关、Hardware Firewall 或 FortiGate Security Appliance 关联。
* 包含超过 30 台服务器。
* 具有大于 /28 的主要子网。

在这些实例中，必须针对防火墙建立新的 VLAN，或者必须选择其他产品。

Hardware Firewall 存在以下更多限制：

* 可移植子网不受保护
* 不可用于 10Gb 服务器
* 每个 Hardware Firewall 最多 79 个防火墙规则
* 处理 ARP 的方式导致与 Windows 网络负载均衡 (NLB) 不兼容。
* 规则目标子网仅限于受保护服务器的公共 IP。Hardware Firewall (Dedicated) 没有此限制。
* 不允许按小时计费的服务器。Hardware Firewall 可以应用于按月计费的服务器。
