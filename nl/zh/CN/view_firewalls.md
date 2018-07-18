---

copyright:
  years: 2017
lastupdated: "2017-11-29"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 查看防火墙 

您可以识别帐户上所使用的防火墙及其关联 VLAN，还可以识别未受保护的 VLAN 和计划防火墙解决方案的部署。

## 防火墙概述（按 VLAN）

要获取系统上防火墙的概述以及启动基本管理，请浏览至[客户门户网站![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){: new_window}中的**网络 > IP 管理 > VLAN**。

**注：**要仅查看公共 VLAN，请单击**过滤器**下拉菜单并针对**主要路由器**输入 ``fcr``。 

每行表示基础结构中一个 VLAN。IBM Cloud 自动填充 **VLAN 号**和**主要路由器**信息，以指示真实 VLAN 数及在其上配置 VLAN 的路由器。
使用**名称**字段定义可识别的名称。 

**网关/防火墙**列包含有关所部署的硬件防火墙保护的详细信息，例如：

**添加防火墙**指示没有针对此 VLAN 上服务器设置防火墙。

**单独保护的服务器**指示一个或多个服务器正在利用硬件防火墙（共享），且没有设置硬件防火墙（专用）、FortiGate Security Appliance 或网关。无法在具有单独保护的服务器的 VLAN 上设置 VLAN 防火墙和网关。

**Firewall-vlanXXXX.networklayer.com** 指示设置了硬件防火墙（专用）或 FortiGate Security Appliance。仅可以将一个 VLAN 防火墙或网关与 VLAN 关联，但可以在公共 VLAN 上通过 VLAN 防火墙保护服务器，并可以在专用网络上通过网关关联服务器。

**网关名称**指示 VLAN 与此网关关联。

## 单独保护的服务器视图

在 VLAN 屏幕上，使用**网关/防火墙**列中**单独保护的服务器**标识行，并单击关联 VLAN 号链接。这会显示包含关联设备的 VLAN 的详细信息。

从此处，可单击每个设备，并查看是否为此特定服务器设置了防火墙。

单击设备后，滚动到“配置”选项卡的底部。将在“附加组件”部分中看到状态为**已安装**或**未安装**的**防火墙**。**未安装**指示没有针对此设备设置防火墙。**已安装**指示设置了防火墙，设备上将显示**防火墙**选项卡，可在其中管理防火墙配置。

## 专用防火墙视图

在 VLAN 屏幕上，使用**网关/防火墙**列中 **Firewall-vlanXXXX.networklayer.com** 标识行，并单击此防火墙。将显示硬件防火墙（专用）或 FortiGate Security Appliance。设备详细信息包括关联路由器、VLAN 和 IPv4/IPv6 子网、与此 VLAN 关联的设备以及用于通过防火墙路由流量或绕过防火墙路由流量的控制。

**FortiGate Security Appliance** 设备将具有管理 IP、用户名和密码。管理通过管理 GUI 或基于 SSH 的控制台完成。

## 网关视图

在 VLAN 屏幕上，使用填充了网关设备名称的**网关/防火墙**列标识行，并单击此网关。然后，会将您带至显示关联前端 (FCR) 和后端 (BCR) VLAN 以及网关管理选项的界面。
