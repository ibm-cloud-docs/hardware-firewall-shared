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

# Limitações conhecidas com o Hardware Firewall
{: #known-limitations-with-hardware-firewall-shared-}

Um Hardware Firewall não pode ser implementado em um servidor em uma VLAN que atenda a qualquer um dos critérios a seguir.

* Está atualmente associado a um Gateway de rede, Firewall de hardware ou FortiGate Security Appliance.
* Contém 30 ou mais servidores.
* Tem uma sub-rede primária maior que /28.

Nesses casos, uma nova VLAN deve ser estabelecida para o Firewall ou outro produto deve ser selecionado.

As limitações adicionais para o Hardware Firewall incluem:

* Sub-redes móveis não são protegidas
* Não disponível para servidores de 10Gb
* Máximo de 79 regras de firewall por Hardware Firewall
* Incompatível com Windows Network Load Balancing (NLB) devido à maneira como o
ARP é processado
* A sub-rede de destino da regra é limitada ao IP público do servidor protegido. O Hardware Firewall (Dedicated) não tem essa limitação.
* Os servidores faturados por hora não são permitidos. O Hardware Firewall pode ser aplicado a um servidor faturado por mês.
