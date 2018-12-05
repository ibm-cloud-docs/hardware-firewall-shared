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

# 檢視您的防火牆 

您可以識別帳戶上使用中的防火牆及其關聯的 VLAN，以及識別未受保護的 VLAN 並規劃防火牆解決方案的部署。

## 透過 VLAN 的防火牆概觀

若要取得系統上的防火牆概觀，以及起始基本管理，請導覽至[客戶入口網站![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){: new_window}中的**網路 > IP 管理 > VLAN**。

**附註：** 若只要檢視公用 VLAN，請按一下**過濾器**下拉清單，然後針對**主要路由器**輸入 ``fcr``。 

每一列代表基礎架構中的一個 VLAN。IBM Cloud 會自動移入 **VLAN 號碼**及**主要路由器**資訊，以指示真實的 VLAN 號碼及其配置的路由器。請使用**名稱**欄位來定義可識別的名稱。 

**閘道/防火牆**直欄包含有關哪些硬體防火牆保護準備就緒的詳細資料，例如：

**新增防火牆**表示此 VLAN 上的伺服器沒有防火牆準備就緒。

**個別受保護的伺服器**表示一台以上的伺服器正在使用 Hardware Firewall (Shared)，而且沒有 Hardware Firewall (Dedicated)、FortiGate Security Appliance 或「網路閘道」準備就緒。VLAN 防火牆和網路閘道無法置於有個別受保護的伺服器的 VLAN 上。

**Firewall-vlanXXXX.networklayer.com** 表示有 Hardware Firewall (Dedicated) 或 FortiGate Security Appliance 準備就緒。只有一個 VLAN 防火牆或「網路閘道」可以與 VLAN 相關聯，但可以透過 VLAN 防火牆在公用 VLAN 上保護伺服器，並在專用網路上與「網路閘道」相關聯。

**閘道名稱**表示 VLAN 與「網路閘道」相關聯。

## 個別受保護的伺服器視圖

在 VLAN 畫面上，在**閘道/防火牆**直欄中識別具有**個別受保護的伺服器**的列，然後按一下相關聯的 VLAN 號碼鏈結。這會顯示包括關聯裝置的 VLAN 詳細資料。

從這裡，您可以按一下每個裝置，並檢閱該特定伺服器的防火牆是否準備就緒。

按一下裝置之後，請捲動到「配置」標籤的底端。您會在附加元件區段中看到**防火牆**，狀態為**已安裝**或**未安裝**。**未安裝**表示此裝置沒有防火牆準備就緒。**已安裝**表示防火牆已準備就緒，而且在可以管理防火牆配置的裝置上您會有一個**防火牆**標籤可用。

## 專用的防火牆視圖

在 VLAN 畫面上，在**閘道/防火牆**直欄中識別具有 **Firewall-vlanXXXX.networklayer.com** 的列，然後按一下該防火牆。您會看到 Hardware Firewall (Dedicated) 或 FortiGate Security Appliance。裝置詳細資料包括「路由器」、VLAN 及「IPv4/IPv6 子網路」、與該 VLAN 相關聯的裝置，以及穿過或圍繞防火牆路由資料流量的控制項。

**FortiGate Security Appliance** 裝置會具有管理 IP、使用者名稱及密碼。管理是透過管理 GUI 或 SSH 型的主控台來完成的。

## 網路閘道視圖

在 VLAN 畫面上，識別具有「網路閘道」裝置名稱移入的**閘道/防火牆**直欄的列，然後按一下該網路閘道。然後您會進到一個介面，當中顯示相關聯的前端 (FCR) 和後端 (BCR) VLAN 及「網路閘道」管理選項。
