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

# Affichage de vos divers pare-feux
{: #viewing-your-various-firewalls} 

Vous pouvez identifier les pare-feux utilisés sur un compte et les réseaux locaux virtuels (VLAN) associés, ainsi qu'identifier les VLAN non protégés et envisager le déploiement d'une solution de pare-feu.

## Vue d'ensemble des pare-feux par VLAN

Pour obtenir une vue d'ensemble des pare-feux présents sur votre système et initier une gestion de base, accédez à **Réseau > Gestion IP > VLAN** dans le [portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){: new_window}.

**REMARQUE :** pour afficher uniquement les VLAN publics, cliquez sur le menu déroulant **Filtre** et entrez ``fcr`` pour **Routeur principal**. 

Chaque ligne représente un réseau local virtuel dans votre infrastructure. IBM© Cloud renseigne automatiquement les informations **NUMERO DE VLAN** et **ROUTEUR PRINCIPAL** en indiquant le vrai numéro de réseau local virtuel et le routeur sur lequel il est configuré. Utilisez la zone **NOM** pour définir un nom reconnaissable. 

La colonne intitulée **PASSERELLE/PARE-FEU** contient les détails de la protection par pare-feu matériel en vigueur, par exemple :

**Ajouter pare-feu** indique qu'il n'y a aucun pare-feu en vigueur pour les serveurs de ce réseau local virtuel.

**Serveurs protégés individuellement** indique qu'un ou plusieurs serveurs utilisent un pare-feu matériel (partagé) et qu'il n'y a aucun pare-feu matériel (dédié), aucun dispositif de sécurité FortiGate, ni passerelle réseau en vigueur. Les pare-feux VLAN et les passerelles réseau ne peuvent pas être appliqués sur un VLAN comprenant des serveurs protégés individuellement.

**Firewall-vlanXXXX.networklayer.com** indique qu'un pare-feu matériel (dédié) ou un dispositif de sécurité FortiGate est en place. Il ne peut y avoir qu'un seul pare-feu VLAN ou une passerelle réseau associé à un VLAN, mais un serveur peut être protégé sur le VLAN public par un pare-feu VLAN et associé au réseau privé avec une passerelle réseau.

**Nom de la passerelle** indique le VLAN associé à cette passerelle réseau.

## Vue des serveurs protégés individuellement

Sur l'écran VLAN, identifiez une ligne avec **Serveurs protégés individuellement** dans la colonne **Passerelle/pare-feu** et cliquez sur le lien du numéro de VLAN associé. Vous obtenez alors l'affichage des détails du VLAN, y compris les unités associées.

A partir de là, vous pouvez cliquer sur chaque unité et vérifier si un pare-feu est en place pour ce serveur particulier.

Lorsque vous avez cliqué sur une unité, faites défiler l'écran vers le bas de l'onglet Configuration. Vous verrez **Pare-feu** indiqué dans la zone Modules complémentaires avec le statut **Installé** ou **Non Installé**. **Non installé** indique qu'aucun pare-feu n'est appliqué pour cette unité. **Installé** indique qu'un pare-feu est appliqué et qu'il y aura un onglet **Pare-feu** sur l'unité dans lequel vous pouvez gérer la configuration de pare-feu.

## Vue du pare-feu dédié

Sur l'écran VLAN, identifiez une ligne avec **Firewall-vlanXXXX.networklayer.com** indiqué das la colonne **Passerelle/pare-feu** et cliquez sur ce pare-feu. Vous obtenez alors un pare-feu matériel (dédié) ou un dispositif de sécurité FortiGate (FSA). Les détails de l'unité comprennent le routeur associé, le réseau local virtuel (VLAN), les sous-réseaux IPv4/IPv6, les unités associées à ce VLAN et les commandes permettant de router le trafic via ou hors du pare-feu.

Les **dispositifs de sécurité FortiGate** (FSA) ont une adresse IP de gestion, un nom d'utilisateur et un mot de passe.  La gestion s'effectue via l'interface graphique de gestion ou la console SSH.

## Vue de la passerelle réseau

Sur l'écran VLAN, identifiez une ligne dont la colonne **Passerelle/pare-feu** est remplie avec un nom de dispositif de passerelle réseau et cliquez sur cette passerelle. Vous êtes alors dirigé vers l'interface affichant les options de gestion des VLAN front-end (FCR) et back-end (BCR), ainsi que celles de la passerelle réseau.
