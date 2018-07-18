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

# Häufig gestellte Fragen
Die folgenden Fragen sind häufig gestellte Fragen zur Hardware-Firewall (freigegeben).

## Was ist eine Firewall?

Eine Firewall ist eine Netzeinheit, die einem Server vorgeschaltet ist. Die Firewall blockiert unerwünschten Datenverkehr von einem Server, bevor der Server erreicht wird.

## Warum wird eine Firewall empfohlen?

Der Hauptvorteil einer Firewall besteht darin, dass Ihr Server nur den "guten" Datenverkehr verarbeiten muss. Das bedeutet, dass Ihre Ressource ausschließlich für den beabsichtigten Zweck verwendet wird und für unerwünschten Datenverkehr.

## Welche Firewall bietet IBM an?
In diesem [Abschnitt ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.bluemix.net/docs/infrastructure/fortigate-10g/explore-firewalls.html#explore-firewalls){: new_window} finden Sie einen detaillierten Vergleich aller in der IBM Cloud angebotenen Firewall-Produkte. 

## Ist die Hardware-Firewall (freigegeben) mit den Load-Balancer-Produkten von IBM kompatibel?

Ja. Die Hardware-Firewall (freigegeben) ist mit dem Lastausgleichsservice, der lokalen Lastausgleichsfunktion sowie dem Citrix Netscaler VPX und MPX kompatibel.

## Können portierbare IP-Adressen durch die Hardware-Firewall (freigegeben) geschützt werden?

Nein. Portierbare IP-Adressen können nicht geschützt werden, da sie zwischen Servern verschoben werden können. Ausnahmen werden auf Fallbasis getroffen, da es zahlreiche Vorbehalte gibt und zusätzliche Details zum Systemdesign des Kunden erforderlich sind.

## Kann ich eine Hardware-Firewall und ein Netzgateway mit demselben VLAN verbinden?

Nein, es ist nicht möglich, eine Hardware-Firewall (freigegeben oder dediziert) und ein Netzgateway-Gerät demselben VLAN zuzuweisen.  Die erweiterte Funktionalität des Netzgateway-Geräts bietet Firewall-Features für Ihr Netz anstelle einer freigegebenen oder dedizierten Firewall.

## Fließt der öffentliche Datenverkehr zuerst durch die Einrichtung für den Lastausgleich oder die Hardware-Firewall?

Aus dem öffentlichen Internet kommen zuerst die Lastausgleich-Produkte, dann die Hardware-Firewall-Produkte und als letztes die NetScaler-Produkte (zusammen mit den Kundenservern).

## Muss die Uplink-Port-Geschwindigkeit eines Servers mit der Hardware-Firewall (freigegeben) übereinstimmen?

Die Hardware-Firewall (freigegeben) muss der öffentlichen Uplink-Geschwindigkeit des Servers entsprechen. Da jedoch nur die öffentliche Seite des Netzwerks geschützt wird, muss die öffentliche Uplink-Geschwindigkeit mit der Auswahl der Firewall übereinstimmen.  Kunden können ein Ticket erstellen, um ein Downgrade der allgemein zugänglichen Schnittstellen anzufordern.

## Berechnet IBM Cloud für die Firewall-Bandbreite eine Gebühr?

Die Bandbreite für die Hardware-Firewall (freigegeben), die Hardware-Firewall (dediziert) und die FortiGate Security Appliance wird nicht abgerechnet.  Darüber hinaus können diese Produkte die gesamte Bandbreitenauslastung reduzieren, indem sie den Datenverkehr begrenzt, auf den Server reagieren müssen.

## Wie aktualisiere ich den Uplink meiner Hardware Firewall (freigegeben)?

Die Hardware-Firewall (freigegeben) ist mit der öffentlichen Uplink-Port-Geschwindigkeit eines Servers verbunden. Sie können ein Upgrade durchführen, indem Sie die Firewall inaktivieren, die Portgeschwindigkeit für den Server erhöhen und eine neue Firewall bestellen. Alternativ können Sie einen neuen Server mit den gewünschten Uplinks und der zugehörigen Firewall bereitstellen.

## Gibt es für die Hardware-Firewall (freigegeben) eine Hochverfügbarkeit?

Nein. Die Hardware-Firewall-Plattform ist auf Unternehmen abgestimmt und sehr langlebig, aber echte Hochverfügbarkeit (redundante Geräte) ist keine Option für die Hardware-Firewall (freigegeben). Denn für eine Hochverfügbarkeit (HA) ist eine Hardware-Firewall (dediziert mit Hochverfügbarkeit) oder eine FortiGate Security Appliance (Hochverfügbarkeit) erforderlich.  Das Netzgateway-Produkt hat auch eine HA-Option mit Firewallfunktionalitäten.

## Auf einem IBM Cloud-Server wird ein Hypervisor ausgeführt. Schützt die Hardware-Firewall (freigegeben) auch die virtuellen Maschinen, die auf meinem Hypervisor ausgeführt werden?

Nein. Portierbare IP-Adressen werden für die VMs in einer Hypervisor-Umgebung verwendet und sind nicht durch die gemeinsame Hardware-Firewall geschützt.  Es wird eine Hardware-Firewall (dediziert) oder FortiGate Security Appliance empfohlen.

## Was bedeuten die ausgegrauten Ports in meiner Windows-Firewall?

IBM Cloud bietet viele verschiedene Services, die Sie mit Ihrem Server nutzen können, einschließlich Evault, SNMP und Nagios-Überwachung. Diese Services erfordern, dass unsere internen Systeme zu einem gewissen Grad mit Ihrem Server kommunizieren. Die ausgegrauten Ports, die in der Ausnahmeliste angezeigt werden, sind Ports, die nur am internen Netzport geöffnet sind. Sie sind weiterhin über die öffentliche (Internet-)Netzverbindung blockiert. Da das interne Netz ein gesichertes Netz ist, wird das Öffnen dieser Ports als sicher angenommen.

Diese Ports können in der Regel nicht geändert werden. Wenn Sie jedoch die Firewallregeln zurücksetzen, werden die Ports aus der Ausnahmeliste gelöscht. Beachten Sie, dass das Zurücksetzen der Firewallregeln sich nachteilig auf diese zusätzlichen Services auswirken und abhängig von Ihrer Serverkonfiguration auch andere Probleme verursachen kann.

## Welche Hardware-Firewall-Optionen sind für 10-Gbit/s-Server verfügbar?

Um öffentliche 10-Gbit/s-Uplinks zu unterstützen, ist ein Netzgateway erforderlich.  Wenn 10 Gbit/s nur für das private Netz (für Datenbank, Sicherung, Speicher usw.) erforderlich sind, können Kunden ein Downgrade ihrer allgemein zugänglichen Uplinks anfordern und Hardware-Firewall-Produkte bestellen.

## Welche IP-Bereiche sind für die Firewall zulässig?

Die Liste der IP-Adressen und IP-Bereiche, die die Firewall zulässt, finden Sie [hier](https://console.bluemix.net/docs/infrastructure/hardware-firewall-dedicated/ips.html){: new_window}. 

## Welche VPN-Optionen sind mit jedem Firewallprodukt enthalten?

Nicht alle Firewalls bieten VPN an und nicht alle VPN-Optionen sind identisch.  Die allgemeinen Optionen für VPN lauten:

* Jeder Kunde erhält uneingeschränkte SSL-VPN-Verbindungen zu unserem privaten Netz. Diese Verbindungen können hergestellt werden, indem Sie oben auf der Seite auf den VPN-Link klicken, während Sie beim Kundenportal angemeldet sind.
* Kunden erhalten außerdem pro Konto jeweils ein PPTP-VPN. Es können weitere PPTP-VPN-Benutzer in Paketen aus 5 Benutzern für 5 $ pro Monat zum Konto hinzugefügt werden.
* SoftLayer bietet auch einen einfachen Multi-Tenant-IPSec-VPN-Service ab 99 $ pro Monat.
* Die FortiGate Security Appliance bietet SSL- und IPSec-VPN-Optionen ausschließlich mit Zugriff auf das öffentliche Netz (kein Zugriff auf das private SoftLayer-Netz).
* Das Network Gateway bietet SSL-, IPSec- und OpenVPN-Funktionalitäten im öffentlichen oder privaten Netz.
* Die NetScaler-Produkte können SSL- und IPSec-VPN im öffentlichen oder privaten Netz bereitstellen.
* Kunden können in ihrer IBM Cloud-Umgebung auch eine VPN-Lösung auf einem Server bereitstellen.

## Welche Firewallprodukte unterstützen die Public-to-Private-NAT- bzw. private VLAN-Segmentierung?

Keines der Hardware-Firewallprodukte hat Zugriff auf das private Netz. Ein Netzgateway muss diese Funktionen inline bereitstellen. Die NetScaler-Produkte haben Zugriff auf das öffentliche und private Netz.
