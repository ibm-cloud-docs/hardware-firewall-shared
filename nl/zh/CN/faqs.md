---

copyright:
  years: 2017,2018
lastupdated: "2018-11-12"

keywords: faqs, firewall, ips, traffic, public, private, bandwidth, vpn, nat

subcollection: hardware-firewall-shared

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}
{:note: .note}
{:important: .important}

# Hardware Firewall 常见问题
{: #faqs-for-hardware-firewall-shared-}

以下是使用 Hardware Firewall 时的常见问题。

## 什么是防火墙？
{: faq}

防火墙是服务器所连接的上游网络设备。防火墙用于阻止不需要的流量到达服务器。

## 为何应该使用防火墙？
{: faq}

部署防火墙的主要优势在于，服务器仅需要处理“好”流量，这表示您的资源仅用于预期目的，而不是处理不需要的流量。

## IBM© 提供哪些防火墙产品？
{: faq}

您可以通过查看此[主题](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls)，找到 IBM© Cloud 中提供的所有防火墙产品的详细对比信息。

## Hardware Firewall 是否与 IBM 的负载均衡器产品兼容？
{: faq}

是的。Hardware Firewall 与云负载均衡服务、本地负载均衡器以及 Citrix Netscaler VPX 和 MPX 兼容。

## Hardware Firewall 是否可以保护可移植的 IP？
{: faq}

不可以。无法保护可移植 IP，因为可以在服务器之间移动这些 IP。根据不同情况，存在例外，因为具有多个注意事项且需要更多有关客户系统设计的详细信息。

## 我可以将 Hardware Firewall 和网关与相同 VLAN 关联吗？
{: faq}

不可以，无法将 Hardware Firewall (standard) 或 Hardware Firewall (Dedicated) 和网关设备分配给相同 VLAN。网关设备的扩展功能提供网络的防火墙功能来代替标准或专用防火墙。

## 公用流量是首先通过负载均衡器还是 Hardware Firewall？
{: faq}

来自公共因特网的流量首先会通过负载均衡产品，然后通过 Hardware Firewall 产品，最后通过 NetScaler 产品（以及客户服务器）。

## 服务器的上行端口速度是否需要与 Hardware Firewall 匹配？
{: faq}

Hardware Firewall 不需要与服务器的公共上行链路速度匹配。但是，由于它仅保护网络的公共侧，因此公共上行链路速度必须与所选防火墙匹配。客户可以根据需要创建凭单以请求仅对公共接口进行降级。

## IBM Cloud 是否对防火墙带宽进行收费？
{: faq}

Hardware Firewall、Hardware Firewall (Dedicated) 和 FortiGate Security Appliance (FSA) 1G 不占用带宽。使用 20 TB 后，对防火墙带宽收取 FSA 10G 费用。而且，这些产品可通过限制服务器必须响应的流量降低总带宽利用率。

## 如何升级 Hardware Firewall 的上行链路？
{: faq}

Hardware Firewall 锁定为服务器的公共上行端口速度。可以通过取消防火墙、升级服务器的端口速度以及订购新的防火墙来就地升级。或者，可以使用所需上行链路和关联防火墙部署新服务器。

## Hardware Firewall 是否可以实现高可用性？
{: faq}

不可以。Hardware Firewall 平台是企业级的高耐久性平台，但是 Hardware Firewall 无法实现真正的高可用性（冗余设备）。要实现 HA，需要 Hardware Firewall（专用且具有高可用性）或 FortiGate Security Appliance（高可用性）。网关产品还具有 HA 选项以及防火墙功能。

## 我正在 IBM Cloud 服务器上运行系统管理程序。Hardware Firewall 是否将保护系统管理程序上运行的虚拟机？
{: faq}

否。可移植 IP 在系统管理程序环境中用于 VM，且不受硬件防火墙的保护。建议使用 Hardware Firewall (Dedicated) 或 FortiGate Security Appliance。

## 我的 Windows 防火墙中有哪些端口灰掉？
{: faq}

IBM Cloud 提供很多不同服务，可用于诸如 Evault、SNMP 和 Nagios 监控的服务器。这些服务需要内部系统与服务器在一定程度上进行通信。“异常”列表中的灰显端口为仅在内部网络端口上打开的端口。这些端口在公用（因特网）网络连接上也被阻止。由于内部网络是安全网络，打开这些端口可确保网络安全。

通常，无法修改这些端口；但是，如果重置防火墙规则，会从“异常”列表清除这些端口。请注意，重置防火墙规则可能不仅对这些额外的服务产生负面影响，还可能会根据服务器当前配置导致其他服务器问题。

## 哪些 Hardware Firewall 选择适用于 10Gbps 服务器？
{: faq}

FSA 10G 是支持公共和专用流量的 10Gbps 服务器的唯一选项。如果仅在专用网络（针对数据库、备份和存储等）上需要 10Gbps，那么客户可请求仅降级其公共上行链路，并订购任何 Hardware Firewall 产品。

## 我允许哪些 IP 范围通过防火墙？
{: faq}

有关允许通过防火墙的 IP 地址和 IP 范围的列表，请转至[此处](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}。

## 每个防火墙产品提供了哪些 VPN 选项？
{: faq}

不是所有的防火墙都提供 VPN，也不是所有的 VPN 选项都相同。VPN 的常规选项为：

* 每个客户收到专用网络的不受限制的 SSL VPN 连接。可以在登录到客户门户网站时单击页面顶部的 VPN 链路来建立这些连接。
* 针对每个帐户，客户还会收到一个 PPTP VPN。客户可以向其帐户成批添加更多 PPTP VPN 用户，每个月添加 5 个用户额外收取 5 美元。
* SoftLayer 还提供基本多租户 IPSec VPN 服务，最低每月 99 美元。
* FortiGate Security Appliance 1G 提供仅带有公用网络访问权（无法访问 SoftLayer 专用网络）的 SSL 和 IPSec VPN 选项。FSA 10G 提供带有公用或专用网络访问权的 SSL 和 IPSec VPN 选项。
* 网关提供公用或专用网络上的 SSL、IPSec 和 OpenVPN 功能。
* NetScaler 产品可提供公用或专用网络上的 SSL 和 IPSec VPN。
* 客户还可在其 IBM Cloud 环境中将 VPN 解决方案部署到服务器上。

## 哪些防火墙产品支持公共到专用 NAT 和/或专用 VLAN 分段？
{: faq}

Fortigate Security Appliance 10G 支持 NAT 和专用 VLAN 分段。其他防火墙产品仅支持公共流量。
