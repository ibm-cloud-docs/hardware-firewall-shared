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

# Limitations connues

Un pare-feu matériel (partagé) ne peut pas être déployé sur un serveur dans un VLAN correspondant à l'un des critères suivants. 

* Il est actuellement associé à une passerelle réseau, un pare-feu matériel ou un dispositif de sécurité FortiGate (FSA).
* Il contient un nombre de serveurs supérieur ou égal à 30.
* Il comporte un sous-réseau principal supérieur à /28.

Dans ces instances, un nouveau VLAN doit être établi pour le pare-feu ou vous devez sélectionner un autre produit.

Voici d'autres limitations liées au pare-feu matériel (partagé) : 

* Les sous-réseaux portables ne sont pas protégés
* Il n'est pas disponible pour les serveurs 10 Gigabits
* Le nombre maximal de règles de pare-feu est limité à 79 règles par pare-feu matériel (partagé)
* Il est incompatible avec l'équilibrage de la charge réseau (NLB) de Windows en raison du mode de traitement du protocole ARP
