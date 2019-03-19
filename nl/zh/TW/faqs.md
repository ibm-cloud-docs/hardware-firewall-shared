---

copyright:
  years: 2017,2018
lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# Hardware Firewall (Shared) 的常見問題
{: #faqs-for-hardware-firewall-shared-}

下列是使用 Hardware Firewall (Shared) 時的常見問題。

## 何謂防火牆？
{:faq}

防火牆是從伺服器上游連接的網路裝置。在到達伺服器之前，防火牆會阻止不想要的資料流量進到伺服器。

## 為何應該使用防火牆？
{:faq}

擁有防火牆的主要優點在於您的伺服器只需處理「良好的」資料流量 - 這表示您的資源僅用於其預期目的，而不是處理不想要的資料流量。

## IBM© 提供哪些防火牆產品？
{:faq}

您可以找到 IBM© Cloud 中提供的所有防火牆產品的詳細比較，方法是檢閱本[主題](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls)。 

## Hardware Firewall (Shared) 是否與 IBM 的負載平衡器產品相容？
{:faq}

是的。Hardware Firewall (Shared) 與雲端負載平衡服務、本端負載平衡器，以及 Citrix Netscaler VPX 和 MPX 相容。

## 是否可以透過 Hardware Firewall (Shared) 保護可攜式 IP？
{:faq}

不可以。可攜式 IP 不適用於保護，因為它們可能會在伺服器之間移動。有一些例外情況是根據具體的情況而發生的，因為會有許多的注意事項，而且需要有關客戶系統設計的其他詳細資料。

## 我可以擁有與同一個 VLAN 相關聯的 Hardware Firewall 和「網路閘道」嗎？
{:faq}

不可以，不可能將 Hardware Firewall (Shared) 或 Hardware Firewall (Dedicated) 和「網路閘道」裝置指派給相同的 VLAN。「網路閘道」裝置的擴充功能是為您的網路提供防火牆特性，代替共用或專用的防火牆。

## 公用資料流量是否先通過負載平衡器或 Hardware Firewall？
{:faq}

負載平衡產品會先從公用網際網路進來、接著是 Hardware Firewall 產品，最後是 NetScaler 產品（連同客戶伺服器）。

## 伺服器的上行鏈路埠速度是否需要與 Hardware Firewall (Shared) 相符？
{:faq}

Hardware Firewall (Shared) 確實需要與伺服器的公用上行鏈路速度相符。但是，因為它只保護網路的公用端，所以公用上行鏈路的速度必須與防火牆選項相符。若想要，客戶可以建立問題單要求只降級公用介面。

## IBM Cloud 是否會收取防火牆頻寬費用？
{:faq}

Hardware Firewall (Shared)、Hardware Firewall (Dedicated) 及 FortiGate Security Appliance 不會針對頻寬進行計量。此外，這些產品還可以透過限制伺服器必須回應的資料流量來減少總頻寬使用率。

## 如何升級 Hardware Firewall (Shared) 的上行鏈路？
{:faq}

Hardware Firewall (Shared) 已鎖定到伺服器的公用上行鏈路埠速度。您可以透過取消防火牆、升級伺服器的埠速度以及訂購新的防火牆來就地升級。或者，您也可以部署具有所需上行鏈路和相關聯防火牆的新伺服器。

## Hardware Firewall (Shared) 是否可具有高可用性？
{:faq}

不可以。Hardware Firewall 平台是企業級且高度耐用的，但真正的「高可用性」（冗餘裝置）不是 Hardware Firewall (Shared) 的選項。對於 HA，需要具有高可用性的 Hardware Firewall (Dedicated) 或 FortiGate Security Appliance（高可用性）。「網路閘道」產品也有含防火牆功能的 HA 選項。

## 我正在 IBM Cloud 伺服器上執行 Hypervisor。Hardware Firewall (Shared) 是否會保護 Hypervisor 上執行的「虛擬機器」？
{:faq}

不會。可攜式 IP 用於 Hypervisor 環境中的 VM，而可攜式 IP 不受共用硬體防火牆的保護。建議使用 Hardware Firewall (Dedicated) 或 FortiGate Security Appliance。

## 什麼是 Windows 防火牆中的灰色埠？
{:faq}

IBM Cloud 提供許多可用於伺服器的不同服務，包括 Evault、SNMP 和 Nagios 監視。這些服務需要我們的內部系統在部分程度上與您的伺服器通訊。您在「例外情況」清單中看到的灰色埠是只在內部網路埠上開啟的埠。其仍會在公用（網際網路）網路連線上遭到封鎖。因為內部網路是一個安全的網路，所以讓這些埠開啟會被認為是安全的。

這些埠一般無法修改；但是，如果您重設防火牆規則，則會從「例外情況」清單中將其清除。請注意，重設防火牆規則可能會對這些其他服務產生不利的影響，而且對您的伺服器（根據其現行配置）也可能會導致其他問題。

## 哪些 Hardware Firewall 選項適用於 10Gbps 伺服器？
{:faq}

為了支援 10Gbps 公用上行鏈路，「網路閘道」是必要的。如果只有專用網路需要 10Gbps（用於資料庫、備份、儲存空間等），則客戶可以要求只降級其公用上行鏈路並訂購任何的 Hardware Firewall 產品。

## 哪些 IP 範圍容許通過防火牆？
{:faq}

如需容許通過防火牆的 IP 位址及 IP 範圍清單，請進到[這裡](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}。 

## 每一個防火牆產品隨附哪些 VPN 選項？
{:faq}

並非所有防火牆都提供 VPN，而且並非所有 VPN 選項都相同。VPN 的一般選項如下：

* 每個客戶都可以收到連接到我們的專用網路的無限制 SSL VPN 連線。這些連線可以進行建立，方法是在登入客戶入口網站時按一下頁面頂端的 VPN 鏈結。
* 客戶也可以為每一個帳戶收到一個 PPTP VPN。他們可以將其他 PPTP VPN 使用者以 5 個一組、每個月額外 5 美元的價格新增到其帳戶中。
* SoftLayer 還提供基本的多方承租戶 IPSec VPN 服務，每月起價為 99 美元。
* FortiGate Security Appliance 提供 SSL 和 IPSec VPN 選項，並只能存取公用網路（無法存取 SoftLayer 專用網路）。
* 「網路閘道」在公用或專用網路上提供 SSL、IPSec 及 OpenVPN 功能
* NetScaler 產品可以在公用或專用網路上提供 SSL 及 IPSec VPN。
* 客戶也可以將 VPN 解決方案部署到其 IBM Cloud 環境內的伺服器上。

## 哪些防火牆產品支援公用到專用 NAT 及（或）專用 VLAN 區段？
{:faq}

沒有任何 Hardware Firewall 產品可以存取專用網路。需要「網路閘道」在線上提供這些功能，而 NetScaler 產品可以同時存取公用和專用網路。
