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

# 關於 Hardware Firewall
{: #about-hardware-firewall-shared-}

Hardware Firewall 是從伺服器上游連接的網路裝置。在資料流量快要到達伺服器之前，防火牆會阻止不想要的資料流量進到伺服器。具有 Hardware Firewall 的主要優點是伺服器只需處理「良好的」資料流量，而且不會浪費任何資源來處理「不正確的」資料流量。

Hardware Firewall 會善用多方承租戶企業平台，以保護個別伺服器。它可以與伺服器一起購買或稍後添加。它可透過其「虛擬網域 (VDOM)」技術來提供虛擬化的網路安全，以提供個別佈建及管理的虛擬化安全網域。  

因為有多個客戶與硬體相關聯，所以如果防火牆故障或被攻擊所摧垮，共用 Hardware Firewall 實例的每個客戶都可能會受到影響。

可以為指派給伺服器的主要和靜態路由 IP 位址配置多達 79 個防火牆規則。根據單一 IP 在選定日期範圍內的活動提供「防火牆」的報告。客戶可以透過兩種方式管理防火牆：SoftLayer Control Portal（受保護伺服器詳細資料頁面下的防火牆標籤）和 SoftLayer SLDN API。

由於每月的伺服器頻寬會在伺服器交換器埠中記錄，因此 Hardware Firewall 封鎖的資料流量不會計入您的每月分配量中，進而可消除支付不必要資料流量的需求。

## 概觀及特性
{: #overview-and-features}

**預期的使用：** 單一伺服器主要 IP 保護

**使用者介面：** 整合到 SoftLayer Control Portal 及 SoftLayer API

**特性：** 有狀態封包檢驗、進入防火牆規則、IPv4、IPv6、基本記載

**傳輸量：** 10Mbps、100Mbps、1000Mbps 或 2000Mbps

Hardware Firewall 實例的傳輸量必須與新增防火牆之伺服器的上行鏈路速度相符合。
