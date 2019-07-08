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

# Limitations connues du pare-feu matériel
{: #known-limitations-with-hardware-firewall-shared-}

Un pare-feu matériel ne peut pas être déployé sur un serveur dans un VLAN correspondant à l'un des critères suivants.

* Il est actuellement associé à une passerelle réseau, un pare-feu matériel ou un dispositif de sécurité FortiGate (FSA).
* Il contient un nombre de serveurs supérieur ou égal à 30.
* Il comporte un sous-réseau principal supérieur à /28.

Dans ces instances, un nouveau VLAN doit être établi pour le pare-feu ou vous devez sélectionner un autre produit.

Voici d'autres limitations liées au pare-feu matériel :

* Les sous-réseaux portables ne sont pas protégés
* Il n'est pas disponible pour les serveurs 10 Gigabits
* Le nombre maximal de règles de pare-feu est limité à 79 règles par pare-feu matériel 
* Il est incompatible avec l'équilibrage de la charge réseau (NLB) de Windows en raison du mode de traitement du protocole ARP
* Le sous-réseau de destination de règle est limité à l'IP publique du serveur protégé. Le pare-feu matériel (dédié) n'a pas cette limitation.
* Les serveurs facturés à l'heure ne sont pas autorisés. Le pare-feu matériel peut être appliqué à un serveur facturé au mois.
