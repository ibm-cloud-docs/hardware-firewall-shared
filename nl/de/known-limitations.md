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

# Bekannte Einschränkungen

Eine Hardware-Firewall (freigegeben) kann nicht auf einem Server in einem VLAN bereitgestellt werden, das eines der folgenden Kriterien erfüllt. 

* Ist einem Netzgateway, einer Hardware-Firewall oder einer FortiGate Security Appliance zugeordnet.
* Enthält 30 oder mehr Server.
* Hat ein primäres Teilnetz, das größer als /28 ist.

In diesen Fällen muss ein neues VLAN für die Firewall eingerichtet oder ein anderes Produkt ausgewählt werden.

Weitere Einschränkungen für die Hardware-Firewall (freigegeben): 

* Portierbare Teilnetze sind nicht geschützt
* Nicht für 10-GB-Server verfügbar
* Maximal 79 Firewallregeln pro Hardware-Firewall (freigegeben)
* Inkompatibel mit dem Windows-Netzlastenausgleich (NLB) aufgrund der Verarbeitung von ARP
