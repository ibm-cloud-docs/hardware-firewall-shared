---

copyright:
  years: 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 製品情報

ハードウェア・ファイアウォール (共有) は、サーバーの上流に接続されるネットワーク・デバイスです。ファイアウォールは、不要なトラフィックがサーバーに到達する前に、そのトラフィックをブロックします。ハードウェア・ファイアウォールを使用する主な利点は、サーバーで処理する必要があるのが「良好な」トラフィックのみになるという点、および「不正な」トラフィックの処理にリソースを無駄に使用する必要がなくなる点です。 

ハードウェア・ファイアウォール (共有) では、個々のサーバーを保護するためにマルチテナント・エンタープライズ・プラットフォームが活用されます。ハードウェア・ファイアウォール (共有) は、サーバーとともに購入すること、または後で追加することができます。ハードウェア・ファイアウォール (共有) は、その仮想ドメイン (VDOM) テクノロジーを通じて仮想化されたネットワーク・セキュリティーを実現します。これにより、個別にプロビジョンおよび管理される仮想化されたセキュリティー・ドメインが提供されます。  

ハードウェアには複数のお客様が関連付けられるため、ファイアウォールで障害が発生した場合、またはファイアウォールが攻撃によって機能不全になった場合には、ハードウェア・ファイアウォール (共有) インスタンスを共有するすべてのお客様が影響を受ける場合があります。 

サーバーに割り当てられるプライマリー IP アドレスおよび静的に経路指定される IP アドレスに対して、最大 79 のファイアウォール・ルールを構成できます。選択した日付範囲について、単一 IP のアクティビティーに基づき、共有ファイアウォールのレポートを利用できます。お客様は、Web ベースの FortiOS GUI または SSH を使用する CLI (コマンド・ライン・インターフェース) を通じてファイアウォールを管理できます。高可用性も注文でき、その場合は、2 台のアプライアンスがアクティブ/パッシブ・デプロイメントとして同期化構成で提供されます。

サーバー・スイッチ・ポートで毎月のサーバー帯域幅が記録されるため、ハードウェア・ファイアウォール (共有) によってブロックされたトラフィックは毎月の割り当てに対してカウントされません。このため、不要なトラフィックに対して支払いを行う必要はありません。

## 概要と機能

**使用目的:** 単一サーバーのプライマリー IP の保護

**ユーザー・インターフェース:** SoftLayer Control Portal および SoftLayer API に統合済み

**機能:** ステートフル・パケット検査、入口ファイアウォール・ルール、IPv4、IPv6、基本ロギング

**スループット:** 10Mbps、100Mbps、1000Mbps、または 2000Mbps 

ハードウェア・ファイアウォール (共有) インスタンスのスループットは、ファイアウォールを追加する先のサーバーのアップリンク速度に一致させる必要があります。