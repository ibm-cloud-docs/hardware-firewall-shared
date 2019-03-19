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

# Perguntas frequentes para o Hardware Firewall (Shared)
{: #faqs-for-hardware-firewall-shared-}

A seguir estão as perguntas mais frequentes ao trabalhar com o Hardware Firewall (Shared).

## O que é um firewall?
{:faq}

Um firewall é um dispositivo de rede que está conectado para envio de dados de um servidor. O firewall bloqueia o
tráfego indesejado de um servidor antes que servidor seja atingido.

## Por que devo usar um firewall?
{:faq}

A principal vantagem de ter um firewall é que seu servidor terá de manipular apenas o tráfego "bom", significando que seu recurso está sendo usado exclusivamente para seu propósito desejado e não para manipular o tráfego indesejado também.

## Quais produtos de firewall a IBM© oferece?
{:faq}

É possível localizar uma comparação detalhada de todos os produtos de firewall oferecidos no IBM© Cloud revisando este [tópico](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls). 

## O Hardware Firewall (Shared) é compatível com produtos de balanceador de carga da IBM?
{:faq}

Sim. O Hardware Firewall (Shared) é compatível com o serviço de balanceamento de carga em nuvem, balanceador de carga local, bem como o Citrix Netscaler VPX e MPX.

## IPs móveis podem ser protegidos pelo Hardware Firewall (Shared)?
{:faq}

Não. IDs móveis não estão disponíveis para proteção porque podem ser movidos entre servidores. Exceções são feitas caso a caso, visto que há várias advertências e requerem detalhes adicionais sobre o design do sistema do cliente.

## Posso ter um Hardware Firewall e um Gateway de rede associados à mesma VLAN.
{:faq}

Não, não é possível ter um Hardware Firewall (compartilhado ou dedicado) e um dispositivo de Gateway de rede designado à mesma VLAN.  A funcionalidade expandida do dispositivo de Gateway de rede fornece recursos de firewall para sua rede em vez de um firewall compartilhado ou dedicado.

## O tráfego público passa pelo meu balanceador de carga ou Hardware Firewall primeiro?
{:faq}

Vindos da Internet pública, os produtos de balanceamento de carga são os primeiros, os produtos de Hardware Firewall vêm em seguida e os produtos NetScaler são os últimos (junto com os servidores dos clientes).

## A velocidade da porta de uplink de um servidor precisa corresponder ao Hardware Firewall (Shared)?
{:faq}

O Hardware Firewall (Shared) precisa corresponder à velocidade de uplink público do servidor. No entanto, como ele só protege o lado público da rede, a velocidade de uplink público é o que deve corresponder à seleção de firewall.  Os clientes podem criar um chamado para solicitar um downgrade somente das interfaces públicas, se desejado.

## O IBM Cloud cobra pela largura de banda do firewall?
{:faq}

O Hardware Firewall (Shared), Hardware Firewall (Dedicated) e o FortiGate Security Appliance não são medidos em largura de banda.  Além disso, esses produtos podem reduzir a utilização da largura de banda total limitando o tráfego ao qual os servidores devem responder.

## Como fazer upgrade do uplink do meu Hardware Firewall (Shared)?
{:faq}

O Hardware Firewall (Shared) é bloqueado para a velocidade da porta de uplink pública de um servidor. É possível fazer upgrade no local cancelando o firewall, fazendo upgrade da velocidade da porta para o servidor e pedindo um novo firewall. Como alternativa, é possível implementar um novo servidor com os uplinks desejados e o firewall associado.

## É possível alta disponibilidade com o Hardware Firewall (Shared)?
{:faq}

Não. A plataforma de Hardware Firewall é de nível corporativo e altamente durável, mas alta disponibilidade verdadeira (dispositivos redundantes) não é uma opção para o Hardware Firewall (Shared). Para HA, um Hardware Firewall (dedicado com alta disponibilidade) ou FortiGate Security Appliance (alta disponibilidade) é necessário.  O produto Network Gateway também tem uma opção de HA com recursos de firewall.

## Estou executando um hypervisor em um servidor IBM Cloud. O Hardware Firewall (Shared) protegerá as máquinas virtuais que estão sendo executadas em meu hypervisor.
{:faq}

Não. IPs móveis são usados para as VMs em um ambiente de hypervisor e IPs móveis não são protegidos pelo firewall de hardware compartilhado.  Um Hardware Firewall (Dedicated) ou o FortiGate Security Appliance é recomendado.

## Quais são as portas esmaecidas no meu firewall do Windows?
{:faq}

O IBM Cloud oferece muitos serviços diferentes que você pode utilizar com seu servidor, incluindo de monitoramento Evault, SNMP e Nagios. Esses serviços requerem que os nossos sistemas internos se comuniquem com seu servidor em algum grau. As portas esmaecidas que você vê na lista Exceções são portas abertas na porta de rede interna apenas. Elas ainda estão bloqueadas na conexão de rede pública (Internet). Como a rede interna é uma rede segura, ter essas portas abertas é considerado seguro.

Essas portas geralmente não podem ser modificadas; no entanto, se você reconfigurar as regras de firewall, ele as limpará da lista Exceções. Esteja ciente de que a reconfiguração das regras de firewall pode ter um efeito negativo não somente nesses serviços adicionais, mas pode causar outros problemas também com seu servidor dependendo da configuração atual dele.

## Quais opções de Hardware Firewall estão disponíveis para servidores de 10Gbps?
{:faq}

Para suportar uplinks públicos de 10Gbps, um Gateway de rede é necessário.  Se 10Gbps for necessário apenas na rede privada (para banco de dados, backup, armazenamento etc.), os clientes poderão solicitar um downgrade apenas de seus uplinks públicos e pedir quaisquer produtos de Hardware Firewall.

## Quais intervalos de IP permitir por meio do firewall?
{:faq}

Para obter a lista de endereços IP e intervalos de IP a serem permitidos por meio do firewall, acesse [aqui](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}. 

## Quais opções de VPN são incluídas com cada produto de Firewall?
{:faq}

Nem todos os firewalls oferecem VPN e nem todas as opções VPN são as mesmas.  As opções gerais para VPN são:

* Cada cliente recebe conexões SSL VPN ilimitadas com nossa rede privada. Essas conexões podem ser estabelecidas clicando no link VPN na parte superior da página enquanto com login efetuado no portal do cliente.
* Os clientes também recebem um PPTP VPN por conta. Eles podem incluir usuários adicionais PPTP VPN em suas contas em pacotes de 5 por US$5/mês extra.
* O SoftLayer também oferece um serviço de VPN IPSec básico de vários locatários, começando com $99/mês.
* O FortiGate Security Appliance fornece opções de VPN SSL e IPSec com acesso de rede pública apenas (sem acesso à rede privada do SoftLayer).
* O Gateway de rede fornece recursos SSL, IPSec e OpenVPN na rede pública ou privada
* Os produtos NetScaler podem fornecer VPN SSL e IPSec na rede pública ou privada.
* Os clientes também podem implementar uma solução de VPN em um servidor em seu ambiente do IBM Cloud.

## Quais produtos de firewall suportam NAT público para privado e/ou segmentação de VLAN privada?
{:faq}

Nenhum dos produtos Hardware Firewall tem acesso à rede privada. Um Gateway de rede é necessário para fornecer esses recursos sequenciais e os produtos NetScaler têm acesso às redes pública e privada.
