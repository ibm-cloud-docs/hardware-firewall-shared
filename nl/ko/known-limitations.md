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

# 알려진 제한사항

공유 하드웨어 방화벽을 다음 기준에 해당하는 VLAN의 서버에 배치할 수 없습니다. 

하드웨어 방화벽(공유)을 다음 기준에 해당하는 VLAN의 서버에 배치할 수 없습니다. 

* 현재 네트워크 게이트웨이, 하드웨어 방화벽 또는 FortiGate 보안 어플라이언스와 연관되어 있습니다.
* 30개 이상의 서버를 포함합니다.
* /28 보다 큰 기본 서브넷이 있습니다.

이러한 인스턴스의 경우 방화벽에 대한 새 VLAN을 설정하거나 다른 제품을 선택해야 합니다.

추가적인 하드웨어 방화벽(공유)의 제한사항은 다음을 포함합니다. 

* 10Gb 서버에 사용할 수 없음
* 공유 하드웨어 방화벽 당 최대 79개의 방화벽 규칙
* 포터블 서브넷이 보호되지 않음
* 10Gb 서버에 사용할 수 없음
* 하드웨어 방화벽(공유) 당 최대 79개의 방화벽 규칙
* ARP가 처리되는 방식으로 인해 Windows NLB(Network Load Balancing)와 호환되지 않음
