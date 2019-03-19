---

copyright:
  years: 2017,2018
lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# Foire aux questions concernant le pare-feu matériel (partagé)
{: #faqs-for-hardware-firewall-shared-}

Voici les questions les plus fréquentes concernant l'utilisation du pare-feu matériel (partagé).

## Qu'est-ce qu'un pare-feu ?
{:faq}

Un pare-feu est un périphérique réseau connecté en amont d'un serveur. Le pare-feu bloque le trafic indésirable avant qu'il n'atteigne le serveur.

## Pourquoi utiliser un pare-feu ?
{:faq}

Avec l'utilisation d'un pare-feu, l'avantage principal est de laisser passer uniquement le "bon" trafic, c'est-à-dire que vos ressources sont uniquement utilisées à cette fin, évitant ainsi le traitement de trafic non souhaité.

## Quels sont les produits de pare-feu proposés par IBM© ?
{:faq}

Vous trouverez un comparatif détaillé de tous les produits de pare-feu proposés dans IBM© Cloud en consultant cette [rubrique](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls). 

## Le pare-feu matériel (partagé) est-il compatible avec les produits d'équilibrage de charge d'IBM ?
{:faq}

Oui. Le pare-feu matériel (partagé) est compatible avec le service d'équilibrage de charge de cloud, l'équilibreur de charge local, ainsi que Citrix Netscaler VPX et MPX.

## Les adresses IP portables peuvent-elles être protégées par le pare-feu matériel (partagé) ?
{:faq}

Non. Les adresses IP portables ne peuvent pas faire l'objet d'une protection car elles sont transférables entre les serveurs. Il peut y avoir des exceptions au cas par cas car il y a de nombreuses réserves et cela nécessite des détails supplémentaires sur la conception système du client.

## Puis-je disposer d'un pare-feu matériel et d'une passerelle réseau associés au même réseau local virtuel (VLAN) ?
{:faq}

Non, il est impossible d'avoir un pare-feu (dédié ou partagé) et une passerelle réseau affectés au même réseau local virtuel.  La fonctionnalité étendue du dispositif de passerelle réseau fournit des fonctions de pare-feu pour votre réseau à la place d'un pare-feu dédié ou partagé.

## Le trafic public passe-t-il d'abord via mon équilibreur de charge ou par le pare-feu matériel ?
{:faq}

Lorsqu'il provient du réseau Internet public, il passe d'abord par les produits d'équilibrage de charge, puis par les produits de pare-feu matériel, et enfin par les produits NetScaler (auxquels s'ajoutent les serveurs du client).

## La vitesse des ports de liaison montante d'un serveur doit-elle correspondre au pare-feu matériel (partagé) ?
{:faq}

Le pare-feu matériel (partagé) n'a pas besoin de correspondre à la vitesse des ports de liaison montante du serveur. Cependant, comme il ne protège que le côté public du réseau, la vitesse de liaison montante publique doit correspondre à la sélection du pare-feu.  Les clients peuvent créer un ticket de demande de service pour demander une rétromigration pour les interfaces publiques uniquement, s'ils le souhaitent.

## IBM Cloud facture-t-il des frais pour la bande passante de pare-feu ?
{:faq}

La bande passante du pare-feu matériel (partagé), du pare-feu matériel (dédié) et du dispositif de sécurité FortiGate (FSA) n'est pas comptabilisée.  Par ailleurs, ces produits contribuent à réduire l'utilisation de la bande passante totale en limitant le trafic auquel les serveurs doivent répondre.

## Comment mettre à niveau la liaison montante de mon pare-feu matériel (partagé) ?
{:faq}

Le pare-feu matériel (partagé) est verrouillé par rapport à la vitesse de port de liaison montante publique d'un serveur. Vous pouvez effectuer une mise à niveau sur site en annulant le pare-feu, en mettant à niveau la vitesse du port du serveur et en commandant un nouveau pare-feu. Autrement, vous pouvez déployer un nouveau serveur avec les liaisons montantes souhaitées et le pare-feu correspondant.

## La haute disponibilité est-elle possible avec le pare-feu matériel (partagé) ?
{:faq}

Non. La plateforme du pare-feu matériel est de qualité professionnelle et extrêmement durable, mais la haute disponibilité véritable (unités redondantes) n'est pas une option du pare-feu matériel (partagé). Pour obtenir la fonction de haute disponibilité, un pare-feu matériel (dédié avec haute disponibilité) ou le dispositif de sécurité FortiGate (haute disponibilité) est requis.  Le produit Passerelle réseau dispose également d'une option haute disponibilité avec des fonctions de pare-feu.

## J'exécute un hyperviseur sur un serveur IBM Cloud. Le pare-feu matériel (partagé) protège-t-il les machines virtuelles qui s'exécutent sur mon hyperviseur ?
{:faq}

Non. Des adresses IP portables sont utilisées pour les machines virtuelles dans un environnement à hyperviseur et ces adresses ne sont pas protégées par le pare-feu matériel partagé.  Un pare-feu matériel (dédié) ou un dispositif de sécurité FortiGate est recommandé.

## A quoi correspondent les ports grisés dans mon pare-feu Windows ?
{:faq}

IBM Cloud offre de nombreux services divers et variés que vous pouvez utiliser avec votre serveur, parmi lesquels Evault, SNMP et le service de surveillance Nagios. Ces services nécessitent que nos systèmes internes communiquent avec votre serveur dans une certaine mesure. Les ports grisés que vous voyez dans la liste Exceptions sont des ports ouverts sur le port réseau interne uniquement. Ils restent bloqués pour la connexion au réseau (Internet) public. Le réseau interne étant un réseau sécurisé, ces ports peuvent donc rester ouverts en toute sécurité.

En général, ces ports ne sont pas modifiables. Cependant si vous réinitialisez les règles de pare-feu, ils seront supprimés de la liste Exceptions. Soyez vigilant, car la réinitialisation des règles de pare-feu peut avoir des effets indésirables sur ces services supplémentaires mais peut également générer d'autres problèmes avec votre serveur en fonction de la configuration actuelle du serveur.

## Quelles sont les options de pare-feu matériel disponibles pour les serveurs 10 Gbit/s ?
{:faq}

Pour prendre en charge les liaisons montantes 10 Gbit/s, une passerelle réseau est requise.  Si 10 Gbit/s sont requis sur le réseau privé uniquement (pour la base de données, la sauvegarde, le stockage, etc.), les clients peuvent demander une rétromigration seulement pour leurs liaisons montantes publiques et commander n'importe quel produit de pare-feu matériel.

## Quelles plages d'adresses IP autoriser via le pare-feu ?
{:faq}

Pour obtenir la liste des adresses IP et des plages d'adresses IP à autoriser via le pare-feu, cliquez [ici](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}. 

## Quelles sont les options VPN incluses dans chaque produit de pare-feu ?
{:faq}

Tous les pare-feux n'offrent pas forcément de réseau VPN et toutes les options VPN ne sont pas identiques.  Les options générales de réseau VPN sont :

* Chaque client reçoit des connexions VPN SSL illimitées à notre réseau privé. Ces connexions peuvent être établies en cliquant sur le lien Réseau privé virtuel (VPN) en haut de la page lorsque vous êtes connecté au portail client.
* Les clients reçoivent également un réseau VPN PPTP par compte. Ils peuvent ajouter d'autres réseaux VPN PPTP à leur compte par pack de 5 pour un supplément de 5 $/mois.
* SoftLayer propose également un service VPN IPSec à service partagé à partir de 99 $/mois.
* Le dispositif de sécurité FortiGate (FSA) fournit des options VPN SSL et IPSec avec accès au réseau public uniquement (aucun accès au réseau privé SoftLayer).
* La passerelle réseau fournit les fonctions SSL, IPSec et OpenVPN sur réseau public ou privé.
* Les produits NetScaler peuvent fournir les fonctions VPN SSL et IPSec sur réseau public ou privé.
* Les clients peuvent également déployer une solution VPN sur un serveur au sein de leur environnement IBM Cloud.

## Quels sont les produits de pare-feu qui prennent en charge la conversion d'adresses réseau NAT public vers privé et/ou la segmentation de VLAN privé ?
{:faq}

Aucun produit de pare-feu matériel n'a accès au réseau privé. Une passerelle réseau est nécessaire pour fournir ces fonctions en ligne et les produits NetScaler ont accès à la fois aux réseaux publics et privés.
