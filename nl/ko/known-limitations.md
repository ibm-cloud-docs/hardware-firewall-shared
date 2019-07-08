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

# Hardware Firewall의 알려진 제한사항
{: #known-limitations-with-hardware-firewall-shared-}

Hardware Firewall은 다음 기준을 충족하는 VLAN의 서버에 배치할 수 없습니다. 

* 현재 네트워크 게이트웨이, Hardware Firewall 또는 FortiGate Security Appliance와 연관되어 있습니다.
* 30개 이상의 서버를 포함합니다.
* /28 보다 큰 기본 서브넷이 있습니다.

이러한 인스턴스의 경우 방화벽에 대한 새 VLAN을 설정하거나 다른 제품을 선택해야 합니다.

Hardware Firewall에 대한 추가적인 제한사항은 다음과 같습니다. 

* 포터블 서브넷이 보호되지 않음
* 10Gb 서버에 사용할 수 없음
* Hardware Firewall당 최대 79개의 방화벽 규칙
* ARP가 처리되는 방식으로 인해 Windows NLB(Network Load Balancing)와 호환되지 않음
* 규칙 대상 서브넷은 보호된 서버의 공인 IP로 제한됩니다. Hardware Firewall (Dedicated)에는 이 제한사항이 없습니다. 
* 시간별로 비용이 청구되는 서버는 허용되지 않습니다. Hardware Firewall은 월별로 비용이 청구되는 서버에 적용될 수 있습니다. 
