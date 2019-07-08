---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: about, overview, features, firewall

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

# 关于 Hardware Firewall
{: #about-hardware-firewall-shared-}

Hardware Firewall 是服务器所连接的上游网络设备。防火墙用于阻止不需要的流量到达服务器。部署 Hardware Firewall 的主要好处在于，服务器仅需要处理“好”流量，不会浪费资源处理“坏”流量。

Hardware Firewall 利用多租户企业平台保护单个服务器。可以与服务器一起购买，也可以之后再添加。它通过其虚拟域 (VDOM) 技术实现虚拟化网络安全性，同时提供单独供应和管理的虚拟安全域。  

由于有多个客户与硬件关联，因此，如果防火墙发生故障或被攻击攻破，那么共享 Hardware Firewall 实例的每个客户都可能会受到影响。

可以为分配给服务器的主要和静态路由 IP 地址最多配置 79 个防火墙规则。将基于单个 IP 在所选日期范围的活动提供防火墙的报告。
客户可以通过两种方式管理防火墙：SoftLayer Control Portal（受保护服务器详细信息页面下的防火墙选项卡）和 SoftLayer SLDN API。

由于每月服务器带宽在服务器交换机端口记录，因此 Hardware Firewall 阻止的流量不会计入每月分配，无需为不需要的流量付费。

## 概述和功能
{: #overview-and-features}

**用途：**单一服务器主要 IP 保护

**用户界面：**集成到 SoftLayer Control Portal 和 SoftLayer API

**功能：**有状态包检查、入防火墙规则、IPv4、IPv6 和基本日志记录

**吞吐量：**10Mbps、100Mbps、1000Mbps 或 2000Mbps

Hardware Firewall 实例的吞吐量需要与要向其添加防火墙的服务器的上行链路速度匹配。
