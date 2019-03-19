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

# Limitazioni note con Hardware Firewall (Shared)
{: #known-limitations-with-hardware-firewall-shared-}

Un Hardware Firewall (Shared) non può essere distribuito a un server su una VLAN che soddisfa uno dei seguenti criteri. 

* È al momento associato a un gateway di rete, un Hardware Firewall o un FortiGate Security Appliance.
* Contiene 30 o più server.
* Ha una sottorete primaria maggiore di /28.

In queste istanze, deve essere stabilita una nuova VLAN per il firewall o deve essere selezionato un altro prodotto.

Ulteriori limitazioni per il Hardware Firewall (Shared) includono: 

* Le sottoreti portatili non sono protette
* Non disponibile per i server 10Gb
* Un massimo di 79 regole del firewall per Hardware Firewall (Shared)
* Incompatibile con Windows Network Load Balancing (NLB) a causa del modo in cui viene elaborato ARP
