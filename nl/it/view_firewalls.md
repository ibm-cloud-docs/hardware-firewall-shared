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

# Visualizzazione dei tuoi firewall
{: #viewing-your-various-firewalls} 

Puoi identificare i firewall in uso su un account e le loro VLAN associate, nonché identificare le VLAN non protette e pianificare la distribuzione di una soluzione firewall.

## Panoramica sul firewall per VLAN

Per ottenere una panoramica sui firewall nel tuo sistema, nonché iniziare la gestione di base, passa a **Network > IP Management > VLANs** in [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window}.

**NOTA:** per visualizzare solo le VLAN pubbliche, fai clic sul menu a discesa **Filter** e immetti ``fcr`` per **Primary Router**. 

Ogni riga rappresenta una VLAN nella tua infrastruttura. IBM© Cloud popola le informazioni **VLAN NUMBER** e **PRIMARY ROUTER** automaticamente indicando il numero VLAN reale e il router su cui è configurata. Utilizza il campo **NAME** per definire un nome riconoscibile. 

La colonna **GATEWAY/FIREWALL** contiene i dettagli su quale protezione firewall hardware è in uso, ad esempio:

**Add Firewall** indica che non ci sono firewall in uso per i server su questa VLAN.

**Individually Protected Servers** indica che uno o più server sta utilizzando un Hardware Firewall (Shared) e non è in uso un Hardware Firewall (Dedicated), FortiGate Security Appliance o un gateway di rete. I gateway di rete e i firewall della VLAN non possono essere utilizzati su una VLAN che ha server protetti individualmente.

**Firewall-vlanXXXX.networklayer.com** indica che è in uso un Hardware Firewall (Dedicated) o un FortiGate Security Appliance. Può essere associato solo un firewall VLAN o un gateway di rete a una VLAN, ma un server può essere protetto su una VLAN pubblica da un firewall VLAN e associato a una rete privata con un gateway di rete.

**GatewayName** indica che la VLAN viene associata con tale gateway di rete.

## Vista server protetti individualmente

Nella schermata delle VLAN, identifica una riga con **Individually Protected Servers** nella colonna **Gateway/Firewall** e fai clic sul link del numero della VLAN associata. Questo visualizzerà i dettagli della VLAN inclusi i dispositivi associati.

Da qui, puoi fare clic su ogni dispositivo e controllare se un firewall è in uso per tale server in particolare.

Dopo aver fatto clic, scorri fino alla fine della scheda Configuration. Visualizzerai **Firewall** nella sezione dei componenti aggiuntivi con **Installed** o **Not Installed** per lo stato. **Not Installed** indica che nessun firewall è in uso per questo dispositivo. **Installed** indica che un firewall è in uso e che avrai una scheda **Firewall** disponibile sul dispositivo dove puoi gestire la configurazione del firewall.

## Vista firewall dedicato

Nella schermata delle VLAN, identifica una riga con **Firewall-vlanXXXX.networklayer.com** nella colonna **Gateway/Firewall** e fai clic su tale firewall. Ti viene offerto un Hardware Firewall (Dedicated) o un FortiGate Security Appliance. I dettagli del dispositivo includono il router associato, la VLAN, le sottoreti IPv4/IPv6, i dispositivi associati alla VLAN e i controlli per l'instradamento del traffico tramite o intorno al firewall.

I dispositivi **FortiGate Security Appliance** avranno un IP di gestione, un nome utente e una password.  La gestione viene completata tramite la GUI di gestione o la console basata su SSH.

## Vista gateway di rete

Nella schermata delle VLAN, identifica una riga con la colonna **Gateway/Firewall** popolata da un dispositivo gateway di rete e fai clic su di esso. Vieni quindi portato all'interfaccia che visualizza le VLAN di frontend (FCR) e di backend (BCR) associate e le opzioni di gestione del gateway di rete.
