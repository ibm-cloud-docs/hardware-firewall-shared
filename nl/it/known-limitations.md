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

# Limitazioni note con l'Hardware Firewall
{: #known-limitations-with-hardware-firewall-shared-}

Un Hardware Firewall non può essere distribuito a un server su una VLAN che soddisfa uno dei seguenti criteri.

* È al momento associato a un gateway di rete, un Hardware Firewall o un FortiGate Security Appliance.
* Contiene 30 o più server.
* Ha una sottorete primaria maggiore di /28.

In queste istanze, deve essere stabilita una nuova VLAN per il firewall o deve essere selezionato un altro prodotto.

Ulteriori limitazioni per l'Hardware Firewall includono:

* Le sottoreti portatili non sono protette
* Non disponibile per i server 10Gb
* Un massimo di 79 regole del firewall per ogni Hardware Firewall
* Incompatibile con Windows Network Load Balancing (NLB) a causa del modo in cui viene elaborato ARP
* La sottorete di destinazione della regola è limitata all'IP pubblico del server protetto. Hardware Firewall (Dedicated) non ha questa limitazione.
* I server fatturati su base oraria non sono consentiti. L'Hardware Firewall può essere applicato a un server fatturato su base mensile.
