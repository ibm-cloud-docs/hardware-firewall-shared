---

copyright:
  years: 2017
lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Limitações conhecidas com o Hardware Firewall (Shared)
{: #known-limitations-with-hardware-firewall-shared-}

Um Firewall de hardware (compartilhado) não pode ser implementado em um servidor em
uma VLAN que atenda a qualquer um dos critérios a seguir. 

* Está atualmente associado a um Gateway de rede, Firewall de hardware ou FortiGate Security Appliance.
* Contém 30 ou mais servidores.
* Tem uma sub-rede primária maior que /28.

Nesses casos, uma nova VLAN deve ser estabelecida para o Firewall ou outro produto deve ser selecionado.

Limitações adicionais para o Firewall de hardware (compartilhado) incluem: 

* Sub-redes móveis não são protegidas
* Não disponível para servidores de 10Gb
* No máximo 79 regras de firewall por Hardware Firewall (Shared)
* Incompatível com Windows Network Load Balancing (NLB) devido à maneira como o
ARP é processado
