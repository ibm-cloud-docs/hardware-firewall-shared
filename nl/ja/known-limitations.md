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

# 既知の制限

ハードウェア・ファイアウォール (共有) は、以下のいずれかの条件を満たす VLAN 上のサーバーにはデプロイできません。 

* ネットワーク・ゲートウェイ、ハードウェア・ファイアウォール、または FortiGate Security Appliance に現在関連付けられている VLAN。
* 30 以上のサーバーを含む VLAN。
* /28 よりも大きいプライマリー・サブネットがある VLAN。

以上の場合、ファイアウォールのために新しい VLAN を確立する必要、または別の製品を選択する必要があります。

ハードウェア・ファイアウォール (共有) のその他の制限を以下に示します。 

* ポータブル・サブネットは保護されません。
* 10Gb サーバーに対しては使用できません。
* 1 つのハードウェア・ファイアウォール (共有) で使用できるファイアウォール・ルールは最大で 79 です。
* ARP の処理方法が原因で Windows ネットワーク負荷分散 (NLB) とは非互換です。
