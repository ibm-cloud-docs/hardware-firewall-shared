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

# Sobre o Hardware Firewall
{: #about-hardware-firewall-shared-}

Um Hardware Firewall é um dispositivo de rede que está conectado para envio de dados de um servidor. O firewall bloqueia tráfego indesejado de um servidor antes mesmo que o tráfego atinja o servidor. A principal vantagem de ter um Hardware Firewall é que um servidor tem que manipular apenas tráfego 'bom' e nenhum recurso é
desperdiçado lidando com tráfego 'mau'.

O Hardware Firewall alavanca uma plataforma corporativa de diversos locatários para proteger um servidor individual. Ele pode ser comprado com o
servidor ou incluído posteriormente.  Ele fornece segurança de rede virtualizada por meio de sua tecnologia de Domínio Virtual (VDOM), fornecendo domínios de segurança virtualizados que são provisionados e gerenciados separadamente.  

Como existem vários clientes associados ao hardware, se o firewall falhar ou for sobrecarregado por um ataque, cada cliente que compartilhar uma instância do Hardware Firewall poderá ser impactado.

Até 79 regras de firewall podem ser configuradas para os endereços IP primário e estaticamente roteado designados ao servidor. Os relatórios para Firewalls estão disponíveis com base na atividade de um único IP para um intervalo de data selecionado. Os clientes podem gerenciar o firewall por meio de duas maneiras: Portal de controle do SoftLayer (a guia de firewall
na página de detalhes do servidor protegido) e as APIs SLDN do SoftLayer.

Como a largura da banda mensal do servidor é registrada na porta do comutador do servidor, o tráfego bloqueado pelo Hardware Firewall não é contado com relação às suas alocações mensais, eliminando a necessidade de pagar pelo tráfego indesejado.

## Visão geral e recursos
{: #overview-and-features}

**Uso desejado:** proteção a IP primário de servidor único

**Interface com o usuário:** integrada no Portal de controle do SoftLayer e na API do SoftLayer

**Recursos:** inspeção de pacote stateful, regras de firewall de
ingresso, IPv4, IPv6, criação de log básica

**Rendimento:** 10Mbps, 100Mbps, 1000Mbps ou 2000Mbps

É necessário que o rendimento da instância do Hardware Firewall corresponda à velocidade de uplink do servidor no qual o firewall está sendo incluído.
