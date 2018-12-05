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

# Informationen

Eine Hardware-Firewall (freigegeben)ist ein Netzgerät, das einem Server vorgeschaltet ist. Die Firewall blockiert unerwünschten Datenverkehr, bevor dieser den Server erreicht. Der Hauptvorteil einer Hardware-Firewall besteht darin, dass ein Server nur "guten" Datenverkehr bewältigen muss und keine Ressourcen verschwendet werden, die mit "schlechtem" Datenverkehr umgehen. 

Die Hardware-Firewall (freigegeben) nutzt eine Multi-Tenant-Unternehmensplattform, um einen einzelnen Server zu schützen.  Sie kann mit einem Server gekauft werden. Der Server kann aber auch später hinzugefügt werden.  Sie bietet über die VDOM-Technologie (Virtual Domain) virtualisierte Netzsicherheit und stellt virtualisierte Sicherheitsdomänen bereit, die separat bereitgestellt und verwaltet werden.  

Da mehrere Kunden mit der Hardware verbunden sind, kann sich ein Ausfall der Firewall oder ein Angriff auf die Firewall auf alle Kunden auswirken, die die Hardware-Firewall (freigegeben) gemeinsam nutzen. 

Für die primären und statisch gerouteten IP-Adressen, die dem Server zugewiesen sind, können bis zu 79 Firewallregeln konfiguriert werden. Berichte für gemeinsam genutzte Firewalls basieren auf der Aktivität einer einzelnen IP-Adresse für einen ausgewählten Datumsbereich.
Kunden können die Firewall entweder über die webbasierte FortiOS-Benutzerschnittstelle oder die CLI (Command Line Interface) mit SSH verwalten. Es kann auch eine Hochverfügbarkeit bestellt werden, die zwei Geräte in der Aktiv-Passiv-Bereitstellung mit synchronisierten Konfigurationen bereitstellt.

Da die monatliche Serverbandbreite am Server-Switch-Port aufgezeichnet wird, wird der von der Hardware-Firewall (freigegeben) blockierte Datenverkehr nicht auf Ihre monatlichen Kontingente angerechnet, sodass kein unnötiger Datenverkehr bezahlt werden muss.

## Überblick und Features

**Bestimmungsgemäßer Gebrauch:** Primärer IP-Schutz für einzelne Server

**Benutzerschnittstelle:** Integriert in das SoftLayer Control Portal und die SoftLayer-API

**Features:** Zustandsorientierte Paketüberprüfung (SPI, Stateful Packet Inspection), Firewall-Eingangsregeln, IPv4, IPv6, Basisprotokollierung

**Durchsatz:** 10 Mbit/s, 100 Mbit/s, 1000 Mbit/s oder 2000 Mbit/s 

Es ist sehr wichtig, dass der Durchsatz der Hardware-Firewall (freigegeben) mit der Uplink-Geschwindigkeit des Servers übereinstimmt, dem die Firewall hinzugefügt wird.
