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

# A propos de

Un pare-feu matériel (partagé) est un périphérique réseau connecté en amont d'un serveur. Le pare-feu bloque le trafic indésirable avant même qu'il n'atteigne le serveur. Le principal avantage d'un pare-feu matériel est qu'un serveur n'a à traiter que le "bon" trafic et qu'aucune ressource n'est gaspillée dans le traitement du "mauvais" trafic. 

Le pare-feu matériel (partagé) tire parti d'une plateforme d'entreprise à service partagé pour protéger un serveur individuel.  Il peut être acheté avec le serveur ou ajouté ultérieurement.  Il offre une sécurité des réseaux virtualisée via sa technologie de domaine virtuel (VDOM), en fournissant des domaines de sécurité virtuels mis à disposition et gérés séparément.  

Comme il y a plusieurs clients associés au matériel, si le pare-feu échoue ou est dépassé par une attaque, tous les clients qui partagent une instance de pare-feu matériel (partagé) sont susceptibles d'être impactés. 

Jusqu'à 79 règles de pare-feu peuvent être configurées pour les adresses IP principales et à routage statique affectées au serveur. Les rapports pour les pare-feux partagés sont disponibles en fonction de l'activité d'une adresse IP unique dans une plage de dates sélectionnée.
Les clients peuvent gérer le pare-feu via l'interface graphique Web FortiOS ou l'interface de ligne de commande (CLI) en utilisant SSH. Vous pouvez également commander l'option Haute disponibilité, qui fournit deux dispositifs en déploiement actif-passif avec des configurations synchronisées.

Comme la bande passante mensuelle du serveur est enregistrée au niveau du port de commutation du serveur, le trafic bloqué par le pare-feu matériel (partagé) n'est pas comptabilisé dans vos allocations mensuelles, donc vous n'avez pas à payer le trafic non souhaité.

## Présentation et fonctions

**Usage prévu :** protection d'adresse IP principale de serveur unique

**Interface utilisateur :** intégrée dans le portail de contrôle de SoftLayer et l'API SoftLayer

**Fonctions :** filtrage dynamique de paquets (SPI), règles de pare-feu (trafic entrant), IPv4, IPv6, journalisation de base

**Débit :** 10 Mbit/s, 100 Mbit/s, 1000 Mbit/s ou 2000 Mbit/s 

Le débit de l'instance de pare-feu matériel (partagé) doit correspondre à la vitesse de la liaison montante du serveur auquel est ajouté le pare-feu.
