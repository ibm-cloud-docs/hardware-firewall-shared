---

copyright:
  years: 2017,2018
lastupdated: "2018-01-16"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# FAQ
다음은 Hardware Firewall (Shared)에 대한 작업을 할 때 자주 묻는 질문(FAQ)입니다.

## 방화벽이 무엇인가요?

방화벽은 서버의 업스트림에 연결된 네트워크 디바이스입니다. 방화벽은 원치 않는 트래픽이 서버에 도달하기 전에 서버에서 트래픽을 차단합니다.

## 왜 방화벽을 사용해야 하나요?

방화벽을 사용할 때의 기본적인 장점은 서버에서 "양호한" 트래픽만 처리하면 된다는 것입니다. 이것은 원치 않는 트래픽도 처리해야 하는 것이 아니라 의도한 목적에 대해서만 리소스가 사용된다는 것을 의미합니다.

## IBM에서 제공하는 방화벽 제품은 무엇이 있나요?
IBM Cloud에서 제공하는 모든 방화벽 제품에 대한 자세한 비교 정보는 이 [주제 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.bluemix.net/docs/infrastructure/fortigate-10g/explore-firewalls.html#explore-firewalls){: new_window}를 검토하십시오. 

## Hardware Firewall (Shared)은 IBM의 로드 밸런서 제품과 호환 가능한가요?

예. Hardware Firewall (Shared)은 클라우드 로드 밸런싱 서비스, 로컬 로드 밸런서, Citrix Netscaler VPX 및 MPX와 호환 가능합니다.

## 포터블 IP를 Hardware Firewall (Shared)으로 보호할 수 있나요?

아니오. 포터블 IP는 서버 간에 이동할 수 있으므로 보호할 수 없습니다. 제한사항이 많거나 고객 시스템의 디자인에 대한 추가적인 세부사항이 필요한 경우에는 상황에 따라 예외가 발생합니다.

## Hardware Firewall 및 네트워크 게이트웨이를 동일한 VLAN과 연관시킬 수 있나요?

아니오. Hardware Firewall (Shared 또는 Dedicated) 및 네트워크 게이트웨이 디바이스를 동일한 VLAN에 연관시킬 수 없습니다.  네트워크 게이트웨이 디바이스의 확장된 기능에서 공유 또는 전용 방화벽을 대신하여 네트워크에 대한 방화벽 기능을 제공합니다.

## 공용 트래픽이 내 로드 밸런서 또는 Hardware Firewall을 먼저 통과하나요?

공용 인터넷에서 오는 경우 로드 밸런싱 제품이 첫 번째, Hardware Firewall 제품이 그 다음, 그리고 NetScaler 제품이 (고객 서버와 함께) 마지막입니다.

## 서버의 업링크 포트 속도가 Hardware Firewall (Shared)과 일치해야 하나요?

Hardware Firewall (Shared)은 서버의 공용 업링크 속도와 일치해야 합니다. 그러나 공용 네트워크 측면만 보호하므로 공용 업링크 속도는 방화벽 선택사항과 일치해야 합니다.  원하는 경우에 고객은 공용 인터페이스만 다운그레이드하도록 요청하는 티켓을 작성할 수 있습니다.

## IBM Cloud는 방화벽 대역폭의 비용을 청구하나요?

Hardware Firewall (Shared), Hardware Firewall (Dedicated) 및 FortiGate 보안 어플라이언스는 대역폭에 대해 측정되지 않습니다.  또한 이러한 제품들은 해당 서버가 응답해야 하는 트래픽을 제한함으로써 전체 대역폭 이용도를 줄일 수 있습니다.

## 내 Hardware Firewall (Shared)의 업링크를 어떻게 업그레이드하나요?

Hardware Firewall (Shared)은 서버의 공용 업링크 포트 속도에 대해 잠겨 있습니다. 방화벽을 취소하고, 서버의 포트 속도를 업그레이드하고, 새 방화벽을 주문하여 업그레이드할 수 있습니다. 또는 원하는 업링크와 연관된 방화벽을 사용하여 새 서버를 배치할 수 있습니다.

## 고가용성이 Hardware Firewall (Shared)에서도 가능한가요?

아니오. Hardware Firewall 플랫폼은 엔터프라이즈급으로 내구성이 강하지만, 실제 고가용성(중복 디바이스)은 Hardware Firewall (Shared)에 대한 옵션이 아닙니다. HA의 경우, Hardware Firewall (Dedicated with High Availability) 또는 FortiGate 보안 어플라이언스(고가용성)가 필수입니다.  네트워크 게이트웨이 제품도 방화벽 기능에 HA 옵션이 있습니다.

## IBM Cloud 서버에서 하이퍼바이저를 실행 중입니다. Hardware Firewall (Shared)이 내 하이퍼바이저에서 실행 중인 가상 머신을 보호하나요?

아니오. 하이퍼바이저 환경의 VM에 대해 포터블 IP가 사용되며 포터블 IP는 공유된 Hardware Firewall에 의해 보호되지 않습니다.  Hardware Firewall (Dedicated) 또는 FortiGate 보안 어플라이언스가 권장됩니다.

## 내 Windows 방화벽에서 회색으로 표시되는 포트는 무엇인가요?

IBM Cloud는 Evault, SNMP 및 Nagios 모니터링을 포함하여 서버와 함께 이용할 수 있는 다양한 여러 서비스를 제공합니다. 이러한 서비스를 이용하려면 IBM의 내부 시스템이 사용자 서버와 어느 정도 통신할 수 있어야 합니다. 예외 목록에서 회색으로 표시되는 포트는 내부 네트워크 포트 전용으로 열린 포트입니다. 이러한 포트는 공용 (인터넷) 네트워크 연결에서 계속 차단됩니다. 내부 네트워크는 보안이 설정된 네트워크이므로 이러한 포트가 열려 있는 것을 안전하다고 간주합니다.

일반적으로 이러한 포트는 수정할 수 없습니다. 그러나 방화벽 규칙을 재설정하는 경우 예외 목록에서 포트가 지워집니다. 방화벽 규칙을 재설정하면 이러한 추가적인 서비스에 부정적인 영향을 줄 수 있을 뿐만 아니라 현재 구성에 따라 서버에 다른 문제가 발생할 수도 있다는 점에 주의하십시오.

## 10Gbps 서버에 사용 가능한 Hardware Firewall 옵션은 무엇인가요?

10Gbps 공용 업링크를 지원하려면 네트워크 게이트웨이가 필요합니다.  (데이터베이스, 백업, 스토리지 등에 대해) 사설 네트워크에 10Gbps만 필요한 경우 고객이 공용 업링크만 다운그레이드를 요청할 수 있으며 Hardware Firewall 제품 중에 주문할 수 있습니다.

## 방화벽에서 허용되는 IP 범위는 어떻게 되나요?

방화벽에서 허용되는 IP 주소 및 IP 범위 목록은 [여기](https://console.bluemix.net/docs/infrastructure/hardware-firewall-dedicated/ips.html){: new_window}로 이동하십시오. 

## 각 방화벽 제품에 포함되는 VPN 옵션은 무엇인가요?

모든 방화벽에서 VPN을 제공하는 것은 아니며 모든 VPN 옵션이 동일하지는 않습니다.  VPN에 대한 일반 옵션은 다음과 같습니다.

* 각 고객은 사설 네트워크에 대한 무제한 SSL VPN 연결을 수신합니다. 고객 포털에 로그인되어 있는 동안 페이지의 맨 위에 있는 VPN 링크를 클릭하여 이러한 연결을 설정할 수 있습니다.
* 또한 고객은 계정 당 하나의 PPTP VPN을 수신합니다. $5/월에 5씩 추가하여 계정에 PPTP VPN 사용자를 추가할 수 있습니다.
* 또한 SoftLayer는 월 $99부터 기본 다중 테넌트 IPSec VPN 서비스를 제공합니다.
* FortiGate 보안 어플라이언스는 공용 네트워크 전용으로 SSL 및 IPSec VPN 옵션을 제공합니다(SoftLayer 사설 네트워크에 액세스할 수 없음).
* 네트워크 게이트웨이는 공용 또는 사설 네트워크에서 SSL, IPSec 및 OpenVPN 기능을 제공합니다.
* NetScaler 제품에서는 공용 또는 사설 네트워크에서 SSL 및 IPSec VPN을 제공할 수 있습니다.
* 또한 고객은 VPN 솔루션을 IBM Cloud 환경 내의 서버로 배치할 수 있습니다.

## 어떤 방화벽 제품이 공용 대 사설 NAT 및/또는 사설 VLAN 세그먼트화를 지원하나요?

사설 네트워크에 액세스할 수 있는 Hardware Firewall 제품은 없습니다. 이러한 기능 인라인을 제공하려면 네트워크 게이트웨이가 필요하며 NetScaler 제품이 공용 및 사설 네트워크 둘 다에 대한 액세스를 포함하고 있습니다.
