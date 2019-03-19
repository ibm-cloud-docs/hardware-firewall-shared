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

# Verschiedene Firewalls anzeigen
{: #viewing-your-various-firewalls} 

Sie können die verwendeten Firewalls für ein Konto und ihre zugehörigen VLANs sowie nicht geschützte VLANs ermitteln sowie die Bereitstellung einer Firewall-Lösung planen.

## Firewall-Übersicht nach VLAN

Um eine Übersicht über die Firewalls auf Ihrem System zu erhalten und eine grundlegende Verwaltung aufzurufen, navigieren Sie zu **Netz > IP-Verwaltung > VLANs** im [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){: new_window}.

**HINWEIS:** Um ausschließlich öffentliche VLANs anzuzeigen, klicken Sie auf das Dropdown-Menü **Filtern** und geben Sie ``fcr`` für den **Primären Router** ein. 

Jede Zeile stellt ein VLAN in Ihrer Infrastruktur dar. IBM© Cloud gibt die Informationen für **VLAN-NUMMER** und **PRIMÄRER ROUTER** automatisch ein. Dabei wird die echte VLAN-Nummer und der Router angegeben, auf die sie konfiguriert ist. Definieren Sie mit dem Feld **NAME** einen erkennbaren Namen. 

Die Spalte **GATEWAY/FIREWALL** enthält Details dazu, welcher Hardware-Firewall-Schutz vorhanden ist. Beispiel:

**Firewall hinzufügen** gibt an, dass in diesem VLAN keine Firewalls für Server vorhanden sind.

**Einzeln geschützte Server** gibt an, dass mindestens ein Server eine Hardware-Firewall (gemeinsam genutzt) verwendet und keine Hardware-Firewall (dediziert), keine FortiGate Security Appliance und kein Netzgateway vorhanden ist. VLAN-Firewalls und Netzgateways können nicht auf einem VLAN mit einzeln geschützten Servern platziert werden.

**Firewall-vlanXXXX.networklayer.com** gibt an, dass eine Hardware-Firewall (dediziert) oder eine FortiGate Security Appliance vorhanden ist. Einem VLAN kann nur eine VLAN-Firewall oder ein Netzgateway zugeordnet werden. Ein Server kann jedoch im öffentlichen VLAN durch eine VLAN-Firewall geschützt und im privaten Netz mit einem Netzgateway verknüpft werden.

**Gateway-Name** gibt an, dass das VLAN mit diesem Netzgateway verknüpft ist.

## Ansicht zu einzeln geschützten Servern

Suchen Sie im VLAN-Bildschirm eine Zeile mit **einzeln geschützten Servern** in der Spalte **Gateway/Firewall** und klicken Sie auf den zugehörigen VLN-Nummer-Link. Daraufhin werden die Details für das VLAN angezeigt, einschließlich der zugehörigen Geräte.

Von hier aus können Sie auf jedes Gerät klicken und prüfen, ob eine Firewall für diesen bestimmten Server vorhanden ist.

Sobald Sie auf ein Gerät geklickt haben, blättern Sie auf der Registerkarte "Konfiguration" nach unten. Angezeigt wird **Firewall** im Abschnitt "Add-ons" mit dem Status **Installiert** oder **Nicht installiert**. **Nicht installiert** gibt an, dass für diese Einheit keine Firewall vorhanden ist. **Installiert** gibt an, dass eine Firewall vorhanden ist und auf der Einheit eine Registerkarte **Firewall** verfügbar ist, auf der Sie die Firewallkonfiguration verwalten können.

## Ansicht zur dedizierten Firewall

Suchen Sie im VLAN-Bildschirm eine Zeile mit **Firewall-vlanXXXX.networklayer.com** in der Spalte **Gateway/Firewall** und klicken Sie auf diese Firewall. Es wird entweder eine Hardware-Firewall (dediziert) oder eine FortiGate Security Appliance angezeigt. Zu den Einheitendetails gehören die zugehörigen Router, VLANs und IPv4/IPv6-Teilnetze, die mit diesem VLAN verbundenen Einheiten sowie die Steuerelemente für die Weiterleitung des Datenverkehrs durch oder um die Firewall herum.

Die **FortiGate Security Appliance**-Einheiten enthalten Verwaltungs-IP-Adresse, Benutzername und Kennwort.  Die Verwaltung erfolgt über die Benutzerschnittstelle für die Verwaltung oder über die SSH-basierte Konsole.

## Ansicht zum Netzgateway

Suchen Sie im VLAN-Bildschirm eine Zeile mit dem Netzgateway-Gerätenamen in der Spalte **Gateway/Firewall** und klicken Sie auf dieses Netzgateway. Sie werden dann zur Benutzeroberfläche weiter geleitet, auf der die zugehörigen Front-End (FCR)- und Back-End- (BCR)-VLANs und Netzgateway-Verwaltungsoptionen angezeigt werden.
