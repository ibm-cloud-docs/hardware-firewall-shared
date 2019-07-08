---

copyright:
  years: 2017,2018
lastupdated: "2018-11-12"

keywords: faqs, firewall, ips, traffic, public, private, bandwidth, vpn, nat

subcollection: hardware-firewall-shared

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}
{:note: .note}
{:important: .important}

# Domande frequenti per Hardware Firewall
{: #faqs-for-hardware-firewall-shared-}

Le seguenti sono le domande frequenti quando si lavora con l'Hardware Firewall.

## Cosa è un firewall?
{: faq}

Un firewall è un dispositivo di rete collegato in upstream da un server. Il firewall blocca il traffico non desiderato da un server prima che venga raggiunto.

## Perché dovrei utilizzare un firewall?
{: faq}

Il vantaggio principale di avere un firewall è che il tuo server deve gestire solo il traffico “buono” – questo significa che la tua risorsa viene utilizzata solamente per lo scopo previsto invece di gestire anche il traffico non desiderato.

## Quali prodotti firewall offre IBM©?
{: faq}

Puoi trovare un confronto dettagliato di tutti i prodotti firewall offerti in IBM© Cloud esaminando questo [argomento](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls).

## L'Hardware Firewall è compatibile con i prodotti del programma di bilanciamento del carico di IBM?
{: faq}

Sì. L'Hardware Firewall è compatibile con il servizio di bilanciamento del carico cloud, il programma di bilanciamento del carico locale, nonché Citrix Netscaler VPX e MPX.

## Gli IP portatili possono essere protetti dall'Hardware Firewall?
{: faq}

No. Gli IP portatili non sono disponibili per la protezione perché possono essere spostati tra i server. Le eccezioni vengono fatte caso per caso in base a diverse precisazioni e richiedono ulteriori dettagli sulla progettazione del sistema del cliente.

## Posso avere un Hardware Firewall e un gateway di rete associati alla stessa VLAN?
{: faq}

No, non è possibile avere un Hardware Firewall (Standard o Dedicated) e un dispositivo gateway di rete assegnati alla stessa VLAN.  La funzionalità espansa del dispositivo gateway di rete fornisce le funzioni firewall per la tua rete in uso di un firewall Standard o Dedicated.

## Il traffico pubblico passa prima nel mio programma di bilanciamento del carico o nell'Hardware Firewall?
{: faq}

Per il traffico proveniente da internet pubblico, i prodotti di bilanciamento del carico vengono prima, i prodotti Hardware Firewall vengono dopo e i prodotti NetScaler vengono per ultimi (insieme ai server dei clienti).

## Una velocità della porta di uplink di un server deve corrispondere all'Hardware Firewall?
{: faq}

L'Hardware Firewall non deve corrispondere alla velocità della porta di uplink del server. Tuttavia, poiché protegge solo il lato pubblico della rete, la velocità di uplink pubblica deve corrispondere alla selezione del firewall.  I clienti possono creare un ticket per richiedere un downgrade delle sole interfacce pubbliche se desiderato.

## IBM effettua un addebito per la larghezza di banda?
{: faq}

L'Hardware Firewall, l'Hardware Firewall (Dedicated) e FSA (FortiGate Security Appliance) 1G non vengono misurati per la larghezza di banda.  FSA 10G viene addebitato per la larghezza di banda del firewall dopo che sono stati utilizzati 20 TB. In aggiunta, questi prodotti possono ridurre l'utilizzo della larghezza di banda totale limitando il traffico a cui devono rispondere i server.

## Come eseguo l'upgrade dell'uplink del mio Hardware Firewall?
{: faq}

L'Hardware Firewall è bloccato alla velocità della porta di uplink pubblica di un server. Puoi eseguire l'upgrade in uso annullando il firewall, aggiornando la velocità della porta del server e ordinando un nuovo firewall. In alternativa, puoi distribuire un nuovo server con gli uplink desiderati e il firewall associato.

## È possibile l'elevata disponibilità con l'Hardware Firewall?
{: faq}

No. La piattaforma dell'Hardware Firewall è a livello aziendale e a lunga durata, ma l'elevata disponibilità reale (dispositivi ridondanti) non è un'opzione per l'Hardware Firewall. Per HA, è necessario un Hardware Firewall (Dedicated con l'elevata disponibilità) o un FortiGate Security Appliance (elevata disponibilità).  Anche il prodotto gateway di rete ha un'opzione HA con le funzionalità del firewall.

## Sto eseguendo un hypervisor su un server IBM Cloud. L'Hardware Firewall proteggerà le macchine virtuali in esecuzione sul mio hypervisor?
{: faq}

No. Gli IP portatili sono utilizzati per le VM in un ambiente hypervisor e non sono protetti dal firewall hardware.  È consigliato un Hardware Firewall (Dedicated) o un FortiGate Security Appliance.

## Cosa sono le porte in grigio nel mio firewall Windows?
{: faq}

IBM Cloud offre molti servizi differenti che puoi utilizzare con il tuo server, inclusi il monitoraggio Nagios, SNMP e Evault. Questi servizi richiedono che i tuoi sistemi interni comunichino con il tuo server in qualche modo. Le porte in grigio che vedi nell'elenco delle eccezioni sono porte aperte solo nella porta di rete interna. Rimangono ancora bloccate nella connessione di rete (internet) pubblica. Poiché la rete interna è una rete protetta, avere queste porte aperte viene considerato sicuro.

Queste porte generalmente non possono essere modificate; tuttavia, se reimposti le regole del firewall, le eliminerà dall'elenco delle eccezioni. Tieni presente che reimpostando le regole del firewall potresti avere un impatto negativo su soltanto questi servizi aggiuntivi e puoi anche causare altri problemi a seconda della tua configurazione del server corrente.

## Quali opzioni dell'Hardware Firewall sono disponibili per i server 10Gbps?
{: faq}

FSA 10G è la sola opzione per supportare i server 10Gbps sia per il traffico pubblico che per quello privato. Se 10Gbps è necessario solo per la rete privata (per il database, il backup, l'archiviazione, ecc), i clienti possono richiedere un downgrade di soltanto i propri uplink pubblici e ordinare un qualsiasi prodotto Hardware Firewall.

## Quali intervalli di IP consento tramite il firewall?
{: faq}

Per l'elenco degli indirizzi IP e di intervalli di IP da consentire tramite il firewall, vai [qui](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}.

## Quali opzioni VPN sono incluse con ogni prodotto firewall?
{: faq}

Non tutti i firewall offrono la VPN e non tutte le opzioni VPN sono uguali.  Le opzioni generali della VPN sono:

* Ogni cliente riceve connessioni VPN SSL illimitate alla nostra rete privata. Queste connessioni possono essere stabilite facendo clic sul link della VPN all'inizio della pagina quando si ha eseguito l'accesso al portale del cliente.
* I clienti ricevono inoltre una VPN PPTP per account. Possono aggiungere ulteriori utenti VPN PPTP ai propri account in pacchetti di 5 per ulteriori 5$/mese.
* SoftLayer offre inoltre un servizio VPN IPSec a più tenant di base a partire da 99$/mese.
* Il FortiGate Security Appliance 1G fornisce le opzioni VPN SSL e IPSec con l'accesso solo alla rete pubblica (nessun accesso alla rete privata SoftLayer).FSA 10G fornisce le opzioni VPN IPsec e SSL con l'accesso alla rete pubblica o privata.
* Il gateway di rete fornisce le funzionalità SSL, IPSec e OpenVPN nella rete privata o pubblica.
* I prodotti NetScaler possono fornire la VPN SSL e IPSec nella rete privata o pubblica.
* I clienti possono inoltre distribuire una soluzione VPN nel server all'interno del loro ambiente IBM Cloud.

## Quali prodotti firewall supportano il NAT da pubblico a privato e/o la segmentazione della VLAN privata?
{: faq}

Fortigate Security Appliance 10G supporta la segmentazione VLAN privata e NAT Le altre offerte firewall supportano solo il traffico pubblico.
