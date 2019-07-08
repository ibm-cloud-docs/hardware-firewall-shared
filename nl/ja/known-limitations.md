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

# ハードウェア・ファイアウォールの既知の制限
{: #known-limitations-with-hardware-firewall-shared-}

ハードウェア・ファイアウォールは、次のいずれかの条件を満たす VLAN 上のサーバーにはデプロイできません。

* ネットワーク・ゲートウェイ、ハードウェア・ファイアウォール、または FortiGate Security Appliance に現在関連付けられている VLAN。
* 30 以上のサーバーを含む VLAN。
* /28 よりも大きいプライマリー・サブネットがある VLAN。

以上の場合、ファイアウォールのために新しい VLAN を確立する必要、または別の製品を選択する必要があります。

ハードウェア・ファイアウォールのその他の制限には次のものがあります。

* ポータブル・サブネットは保護されません。
* 10Gb サーバーに対しては使用できません。
* 1 つのハードウェア・ファイアウォールで使用できるファイアウォール・ルールは最大で 79 です。
* ARP の処理方法が原因で Windows ネットワーク負荷分散 (NLB) とは非互換です。
* ルールの宛先サブネットは、保護サーバーのパブリック IP に制限されます。この制限はハードウェア・ファイアウォール (専用) にはありません。
* 時間課金のサーバーは許可されません。月額課金のサーバーにはハードウェア・ファイアウォールを適用できます。
