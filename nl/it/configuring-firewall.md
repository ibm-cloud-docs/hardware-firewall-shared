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

# Configurazione di Hardware Firewall (Shared)
{: #configuring-the-hardware-firewall-shared-}

La configurazione del firewall è semplice così come la creazione di una serie di regole per consentire l'accesso ad alcuni indirizzi IP/porte da indirizzi internet specifici mentre si nega il traffico da altre origini.

## Aggiunta di un firewall a un server

Per aggiungere un firewall a un server, segui i passi presenti in [Introduzione](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared). Se ricevi un errore, consulta le [Limitazioni note](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) e/o contatta il supporto SoftLayer.

## Modifica delle regole

Quando un firewall viene aggiunto per la prima volta a un server, viene inizialmente messa in uso una serie di regole che consente a tutto il traffico di raggiungere il server. Le regole possono essere modificate per controllare il traffico che raggiunge il server.

Assicurati che "status" indichi che il firewall sia "Processing All Rules." Gli utenti possono scegliere di escludere le regole nel caso in cui le regole implementate abbiano un impatto non desiderato sul proprio ambiente facendo clic su **Bypass Rules** nel menu a discesa **Actions**.

1. Dal tuo browser, apri [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} e accedi al tuo account.
2. Nella navigazione di Customer Portal, vai a **Devices > Device List** e fai clic sul dispositivo protetto dal firewall che desideri configurare.
3. Nella scheda **Firewall**, assicurati che "Status" indichi che il firewall sia "Processing All Rules."  La pagina visualizza le regole correnti in vigore per gli indirizzi IPv4 e IPv6. Se non viene implementata alcuna regola, viene visualizzato un segnaposto sbiadito. A questo punto, i link sono disponibili per la modifica delle regole correnti.  Questo elenco di regole è noto come 'working config'. Un 'working config' è una serie di regole che sono in fase di creazione ma che non sono ancora state applicate al firewall. Un utente può modificare, aggiungere ed eliminare le regole finché non viene completata la serie di regole. 

     Le regole sono visualizzate nell'ordine in cui vengono elaborate, con le regole con numeri più piccoli che hanno la precedenza su quelle
     con numeri più grandi (se la regola uno consente l'attraversamento di un pacchetto, le regole da due in poi vengono ignorate dal pacchetto).
     
     I campi sono:

      **Order** - Questo campo contiene il numero della regola.  Le regole possono essere spostate in alto e in basso nell'elenco con le frecce fornite.
      
      **Action** - Seleziona l'elenco che viene utilizzato per 'consentire' o 'negare' il traffico che corrisponde a questa regola.
      
      **Source** - Questo campo può essere 'uno qualsiasi' o un indirizzo IP specifico o l'indirizzo di rete di una sottorete specifica.
      
      **Destination** - Questo campo seleziona l'IP di destinazione (consulta [Limitazioni note](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) se si
      riscontrano dei problemi).
      
      **CIDR** - Questo campo indica la notazione CIDR standard per l'origine/la destinazione selezionata.
      
      **Port Range** - Questi due campi indicano l'intervallo di porte (tra 1 e 65535) a cui sarà applicata la regola.
      
      **Protocol** - Questo campo seleziona il protocollo a cui sarà applicata la regola (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).
      
      **Notes:** Campo a formato libero per inserire le note su questa regola.

4. Fai clic su una regola per modificarla o sul segno più alla fine della tabella per aggiungere una ulteriore regola. Facendo clic sull'icona meno si eliminerà la regola. Le regole sono automaticamente convalidate come le inserisci.
5. Dopo aver completato il 'working config', premi il pulsante **Update Rules** in modo che 'working config' venga applicato al firewall. Le regole dovrebbero avere effetto in due minuti.

## Porte comuni

| Protocollo | Porta |
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
| Desktop remoto | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 o 10000 ||
