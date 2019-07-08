---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: configure, configuring, firewall, add, adding, edit, editing, rules, ports, common

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

# 配置 Hardware Firewall
{: #configuring-the-hardware-firewall-shared-}

配置防火墙与创建一组可实现以下目的的规则一样简单：允许从特定因特网地址访问特定 IP 地址/端口，同时拒绝来自其他源的流量。

## 将防火墙添加到服务器
{: #adding-a-firewall-to-a-server}

要将防火墙添加到服务器，请按照[开始使用](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared)中的步骤进行操作。如果收到错误，那么会看到[已知限制](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-)和/或“联系 SoftLayer 支持”。

## 编辑规则
{: #editing-rules}

首次将防火墙添加到服务器时，最初会设置一组规则，允许所有流量到达服务器。然后，可以编辑这些规则以控制到达服务器的流量。

确保“状态”指示防火墙“正在处理所有规则”。如果实施的规则对用户的环境具有非预期影响，那么用户可选择通过单击**操作**下拉列表中的**绕过规则**来绕过规则。

1. 从浏览器，打开[客户门户网站![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){: new_window}，并登录到帐户。
2. 在“客户门户网站”导航中，转至**设备 > 设备列表**，并单击要配置的受防火墙保护的设备。
3. 在**防火墙**选项卡中，确保“状态”指示防火墙“正在处理所有规则”。此页面显示 IPv4 和 IPv6 地址的当前有效规则。如果未实施任何规则，那么会显示变暗的占位符。此时，可以通过链接编辑当前规则。此规则列表称为“工作配置”。“工作配置”是一组正在创建但尚未应用于防火墙的规则。用户可以编辑、添加和删除规则，直到完成规则集。

     规则按处理顺序显示，编号较小的规则优先级高于编号较大的规则（如果规则 1 允许通过包，那么规则 2 及以上会被包忽略）。

     字段为：

      **顺序** - 此字段包含规则号。可以使用提供的箭头在列表中向上或向下移动规则。

      **操作** - 此选择列表用于“允许”或“拒绝”与此规则匹配的流量。

      **源** - 此字段可以为“任何”、特定 IP 地址或特定子网的网络地址。

      **目标** - 此字段用于选择目标 IP（如果遇到问题，请参阅[已知限制](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-)）。

      **CIDR** - 此字段指示所选源/目标的标准 CIDR 表示法。

      **端口范围** - 这两个字段指示将向其应用规则的端口范围（1 到 65535 之间）。

      **协议** - 此字段用于选择将向其应用规则的协议 (TCP/GRE/ICMP/UDP/PPTP/AH/ESP)。

      **注：**用于输入有关此规则的任何注释的自由格式字段。

4. 单击规则以对其进行编辑，或单击表底部的加号以添加更多规则。单击减号图标将删除此规则。输入规则时会自动验证这些规则。

5. 完成“工作配置”后，按**更新规则**按钮以向防火墙应用“工作配置”。这些规则应该会在两分钟内生效。

## 公共端口
{: #common-ports}

|协议 |端口|
| :-----: | :-----: |
|FTP|21 |
|SSH |22 |
|Telnet |23 |
|SMTP |25|
|DNS |53 |
|HTTP |80 |
|POP3 |110 |
|IMAP |143 |
|HTTPS |443 |
|MSSQL |1433 |
|MySQL |3306 |
|远程桌面|3389 |
|PostgreSQL|5432 |
|VNC Web |5800 |
|VNC 客户端|5900 |
|Urchin |9999 或 10000 ||
