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

# Die Firewall konfigurieren

Das Konfigurieren der Firewall ist so einfach wie das Erstellen eines Regelsatzes, der den Zugriff auf bestimmte IP-Adressen/Ports von spezifischen Internetadressen erlaubt, während der Datenverkehr aus anderen Quellen abgewiesen wird.

## Eine Firewall zu einem Server hinzufügen

Um einem Server eine Firewall hinzuzufügen, klicken Sie auf der Seite unten auf den Link **Geräte > Geräteliste > Klick auf den gewünschten Server > Konfiguration >: Hardware-Firewall bestellen** im Kundenportal. Dadurch startet der Bestellvorgang für eine geeignete Firewall anhand der Uplink-Geschwindigkeit des ausgewählten Servers. Wenn eine Fehlermeldung angezeigt wird, erhalten Sie weitere Informationen unter [bekannte Einschränkungen](known-limitations.html) oder wenden Sie sich an den SoftLayer-Support.

## Regeln bearbeiten

Wenn eine Firewall erstmalig zu einem Server hinzugefügt wird, wird zunächst ein Regelsatz eingerichtet, mit dem der gesamte Datenverkehr den Server erreicht. Die Regeln können dann bearbeitet werden, um den Datenverkehr zu steuern, der den Server erreicht.

Stellen Sie sicher, dass der Status angibt, dass die Firewall alle Regeln verarbeitet. Benutzer können die Regeln umgehen, wenn implementierte Regeln unbeabsichtigte Auswirkungen auf die Umgebung haben. Klicken Sie dazu auf **Regeln umgehen** im Dropdown-Menü **Aktionen**.

1. Öffnen Sie im Browser das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){: new_window} und melden Sie sich bei Ihrem Konto an.
2. Wählen Sie in der Navigation des Kundenportals **Geräte > Geräteliste** aus und klicken Sie auf das durch die Firewall geschützte Gerät, das Sie konfigurieren möchten.
3. Stellen Sie in der Registerkarte **Firewall** sicher, dass der Status angibt, dass die Firewall alle Regeln verarbeitet.  Die Seite zeigt die aktuellen Regeln für IPv4- und IPv6-Adressen an. Wenn keine Regeln implementiert sind, wird ein ausgeblendeter Platzhalter angezeigt. Hier sind Links verfügbar, um die aktuellen Regeln zu bearbeiten.  Diese Liste aus Regeln ist auch als 'working config' (Arbeitskonfiguration) bekannt. Die 'working config' ist ein Satz von Regeln, der erstellt, aber noch nicht auf die Firewall angewendet wurde. Ein Benutzer kann so lange Regeln bearbeiten, hinzufügen und löschen, bis der Regelsatz abgeschlossen ist. 

     Regeln werden in der Reihenfolge angezeigt, in der sie verarbeitet werden. Regeln mit geringeren Nummern erhalten Vorrang vor Regeln mit höheren Nummern. (Wenn Regel 1 ein Paket durchlässt, werden die Regeln 2 und höher vom Paket ignoriert.)
     
     Felder:

      **Reihenfolge:** Dieses Feld enthält die Regelnummer.  Regeln können mit den angezeigten Pfeilen in der Liste nach oben oder nach unten verschoben werden.
      
      **Aktion:** Diese Auswahlliste wird verwendet, um den Datenverkehr, der dieser Regel entspricht, zuzulassen oder abzulehnen.
      
      **Quelle:** Dieses Feld kann entweder 'alle' oder eine bestimmte IP-Adresse oder die Netzadresse für ein Teilnetz sein.
      
      **CIDR:** Dieses Feld zeigt die Standard-CIDR-Notation für die ausgewählte Quelle an. Mit "32" wird die Regel für eine einzelne IP-Adresse implementiert, und beispielsweise mit "24" wird die Regel für 256 IP-Adressen implementiert.
      
      **Ziel:** Dieses Feld wählt die Ziel-IP-Adresse aus (bei Problemen siehe [Bekannte Einschränkungen](known-limitations.html)).
      
      **CIDR:** Dieses Feld zeigt die Standard-CIDR-Notation für das ausgewählte Ziel an.
      
      **Portbereich:** Die zwei Felder geben den Bereich der Ports (zwischen 1 und 65535) an, auf die die Regel angewendet wird.
      
      **Protokoll:** Mit diesem Feld wird das Protokoll (TCP/GRE/ICMP/UDP/PPTP/AH/ESP) ausgewählt, auf das die Regel angewendet wird.
      
      **Anmerkungen:** Freiform-Feld, um für diese Regel eine Anmerkung einzugeben.

4. Klicken Sie auf eine Regel, um sie zu bearbeiten, oder klicken Sie auf das Pluszeichen am Ende der Tabelle, um eine zusätzliche Regel hinzuzufügen. Beim Klicken auf das Minus-Symbol wird die Regel gelöscht. Die Regeln werden während der Eingabe automatisch validiert.
5. Wenn die Arbeitskonfiguration 'working config' abgeschlossen ist, klicken Sie auf die Schaltfläche **Regeln aktualisieren**, damit die 'working config' auf die Firewall angewendet wird. Die Regeln werden innerhalb von zwei Minuten wirksam.

## Allgemeine Ports

| Protokoll | Port |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| Remote Desktop | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC-Client | 5900 |
| Urchin | 9999 oder 10000 ||

    
