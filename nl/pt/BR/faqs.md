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

# Perguntas mais frequentes
A seguir estão as perguntas mais frequentes ao trabalhar com o Firewall de hardware (compartilhado).

## O que é um firewall?

Um firewall é um dispositivo de rede que está conectado para envio de dados de um servidor. O firewall bloqueia tráfego indesejado de um servidor antes que o servidor seja atingido.

## Por que devo usar um firewall?

A principal vantagem de ter um firewall é que seu servidor terá de manipular apenas o tráfego "bom", significando que seu recurso está sendo usado exclusivamente para seu propósito desejado e não para manipular o tráfego indesejado também.

## Quais produtos de firewall a IBM oferece?
Você pode encontrar uma comparação detalhada de todos os produtos de firewall oferecidos no IBM Cloud revisando este [tópico ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/docs/infrastructure/fortigate-10g/explore-firewalls.html#explore-firewalls){: new_window}. 

## O Firewall de hardware (compartilhado) é compatível com produtos de balanceador de carga da IBM?

Sim.O Firewall de hardware (compartilhado) é compatível com o serviço de balanceamento de carga em nuvem, balanceador de carga local, bem como o Citrix Netscaler VPX e MPX.

## IPs móveis podem ser protegidos pelo Firewall de hardware (compartilhado)?

Não. IDs móveis não estão disponíveis para proteção porque podem ser movidos entre servidores. Exceções são feitas caso a caso, visto que há várias advertências e requerem detalhes adicionais sobre o design do sistema do cliente.

## Posso ter um Firewall de hardware e um Gateway de rede associados à mesma VLAN.

Não, não é possível ter um Firewall de hardware (compartilhado ou dedicado) e um dispositivo de Gateway de rede designado à mesma VLAN. A funcionalidade expandida do dispositivo de Gateway de rede fornece recursos de firewall para sua rede em vez de um firewall compartilhado ou dedicado.

## O tráfego público passa pelo meu balanceador de carga ou Firewall de hardware primeiro?

Vindos da Internet pública, os produtos de balanceamento de carga são os primeiros, os produtos de Firewall de hardware vêm em seguida e os produtos NetScaler são os últimos (junto com os servidores dos clientes).

## A velocidade da porta de uplink de um servidor precisa corresponder ao Firewall de hardware (compartilhado)?

O Firewall de hardware (compartilhado) precisa corresponder à velocidade de uplink público do servidor. No entanto, como ele só protege o lado público da rede, a velocidade de uplink público é o que deve corresponder à seleção de firewall. Os clientes podem criar um chamado para solicitar um downgrade somente das interfaces públicas, se desejado.

## O IBM Cloud cobra pela largura de banda do firewall?

O Firewall de hardware (compartilhado), Firewall de hardware (dedicado) e o FortiGate Security Appliance não são medidos em largura de banda. Além disso, esses produtos podem reduzir a utilização da largura de banda total limitando o tráfego ao qual os servidores devem responder.

## Como fazer upgrade do uplink do meu Firewall de hardware (compartilhado)?

O Firewall de hardware (compartilhado) é bloqueado para a velocidade da porta de uplink pública de um servidor. É possível fazer upgrade no local cancelando o firewall, fazendo upgrade da velocidade da porta para o servidor e pedindo um novo firewall. Como alternativa, é possível implementar um novo servidor com os uplinks desejados e o firewall associado.

## É possível alta disponibilidade com o Firewall de hardware (compartilhado)?

Não. A plataforma de Firewall de hardware é de nível corporativo e altamente durável, mas alta disponibilidade verdadeira (dispositivos redundantes) não é uma opção para o Firewall de hardware (compartilhado). Para HA, um Firewall de hardware (dedicado com alta disponibilidade) ou FortiGate Security Appliance (alta disponibilidade) é necessário. O produto Network Gateway também tem uma opção de HA com recursos de firewall.

## Estou executando um hypervisor em um servidor IBM Cloud. O Firewall de hardware (compartilhado) protegerá as máquinas virtuais que estão sendo executadas em meu hypervisor.

Não. IPs móveis são usados para as VMs em um ambiente de hypervisor e IPs móveis não são protegidos pelo firewall de hardware compartilhado. Um Firewall de hardware (dedicado) ou o FortiGate Security Appliance é recomendado.

## Quais são as portas esmaecidas no meu firewall do Windows?

O IBM Cloud oferece muitos serviços diferentes que você pode utilizar com seu servidor, incluindo de monitoramento Evault, SNMP e Nagios. Esses serviços requerem que os nossos sistemas internos se comuniquem com seu servidor em algum grau. As portas esmaecidas que você vê na lista Exceções são portas abertas na porta de rede interna apenas. Elas ainda estão bloqueadas na conexão de rede pública (Internet). Como a rede interna é uma rede segura, ter essas portas abertas é considerado seguro.

Essas portas geralmente não podem ser modificadas; no entanto, se você reconfigurar as regras de firewall, ele as limpará da lista Exceções. Esteja ciente de que a reconfiguração das regras de firewall pode ter um efeito negativo não somente nesses serviços adicionais, mas pode causar outros problemas também com seu servidor dependendo da configuração atual dele.

## Quais opções de Firewall de hardware estão disponíveis para servidores de 10Gbps?

Para suportar uplinks públicos de 10Gbps, um Gateway de rede é necessário. Se 10Gbps for necessário apenas na rede privada (para banco de dados, backup, armazenamento etc.), os clientes poderão solicitar um downgrade apenas de seus uplinks públicos e pedir quaisquer produtos de Firewall de hardware.

## Quais intervalos de IP permitir por meio do firewall?

Para obter a lista de endereços IP e intervalos de IP a serem permitidos por meio do firewall, acesse [aqui](https://console.bluemix.net/docs/infrastructure/hardware-firewall-dedicated/ips.html){: new_window}. 

## Quais opções de VPN são incluídas com cada produto de Firewall?

Nem todos os firewalls oferecem VPN e nem todas as opções VPN são as mesmas. As opções gerais para VPN são:

* Cada cliente recebe conexões SSL VPN ilimitadas com nossa rede privada. Essas conexões podem ser estabelecidas clicando no link VPN na parte superior da página enquanto com login efetuado no portal do cliente.
* Os clientes também recebem um PPTP VPN por conta. Eles podem incluir usuários adicionais PPTP VPN em suas contas em pacotes de 5 por US$5/mês extra.
* O SoftLayer também oferece um serviço de VPN IPSec básico de vários locatários, começando com $99/mês.
* O FortiGate Security Appliance fornece opções de VPN SSL e IPSec com acesso de rede pública apenas (sem acesso à rede privada do SoftLayer).
* O Gateway de rede fornece recursos SSL, IPSec e OpenVPN na rede pública ou privada
* Os produtos NetScaler podem fornecer VPN SSL e IPSec na rede pública ou privada.
* Os clientes também podem implementar uma solução de VPN em um servidor em seu ambiente do IBM Cloud.

## Quais produtos de firewall suportam NAT público para privado e/ou segmentação de VLAN privada?

Nenhum dos produtos Firewall de hardware tem acesso à rede privada. Um Gateway de rede é necessário para fornecer esses recursos sequenciais e os produtos NetScaler têm acesso às redes pública e privada.
