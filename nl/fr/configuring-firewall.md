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

# Configuration du pare-feu matériel (partagé)
{: #configuring-the-hardware-firewall-shared-}

La configuration du pare-feu est aussi simple que la création d'un ensemble de règles pour autoriser l'accès à une sélection d'adresses IP ou de ports à partir d'adresses IP Internet spécifiques tout en refusant le trafic provenant d'autres sources.

## Ajout d'un pare-feu à un serveur

Pour ajouter un pare-feu à un serveur, suivez la procédure décrite dans [Initiation](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared). Si vous recevez un message d'erreur, consultez la rubrique [Limitations connues](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) et/ou contactez le support SoftLayer.

## Edition de règles

La première fois qu'un pare-feu est ajouté à un serveur, un ensemble de règles est instauré pour autoriser tout le trafic à atteindre le serveur. Les règles peuvent alors être modifiées pour contrôler le trafic atteignant le serveur.

Vérifiez que le "statut" indique "Traiter toutes les règles" pour le pare-feu. Les utilisateurs peuvent choisir d'ignorer les règles si les règles implémentées ont un impact non souhaité sur leur environnement en cliquant sur **Contourner les règles** dans la liste déroulante **Actions**.

1. Depuis votre navigateur, ouvrez le [portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){: new_window} et connectez-vous à votre compte.
2. Dans la navigation du portail client, accédez à **Unités > Liste des unités** et cliquez sur l'unité protégée par le pare-feu que vous voulez configurer.
3. Dans l'onglet **Pare-feu**, vérifiez que "Statut" indique "Traiter Toutes les Règles" pour le pare-feu.  Cette page affiche les règles actuellement en vigueur pour les adresses IPv4 et IPv6. Si aucune règle n'est implémentée, une marque de réservation estompée est affichée. A ce stade, les liens sont disponibles pour éditer les règles en cours.  Cette liste de règles constitue la configuration opérationnelle ('working config'). Une configuration opérationnelle est un ensemble de règles en cours de création mais qui n'a pas encore été appliqué au pare-feu. L'utilisateur peut modifier, ajouter et supprimer des règles jusqu'à ce que l'ensemble de règles soit finalisé. 

     Les règles sont affichées dans l'ordre dans lequel elles sont traitées, les règles ayant les numéros les moins élevés étant prioritaires par rapport à celles ayant les numéros les plus élevés (si la règle un autorise le transfert d'un paquet, les règles deux et supérieures sont ignorées par le paquet).
     
     Les zones sont les suivantes :

      **Ordre** - Cette zone contient le numéro de la règle.  Les règles peuvent être déplacées vers le haut ou vers le bas de la liste avec les flèches fournies.
      
      **Action** - Cette liste de sélection est utilisée pour 'autoriser' ou 'refuser' le trafic correspondant à cette règle.
      
      **Source** - Cette zone peut avoir la valeur 'tout' ou une adresse IP spécifique, ou l'adresse réseau d'un sous-réseau particulier.
      
      **Destination** - Cette zone sélectionne l'adresse IP de destination (voir la rubrique [Limitations connues](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) en cas d'erreur).
      
      **CIDR** - Cette zone indique la notation CIDR standard correspondant à la source/destination sélectionnée.
      
      **Plage de Ports** - Ces deux zones indiquent la plage de ports (comprise entre 1 et 65535) à laquelle la règle va s'appliquer.
      
      **Protocole** - Cette zone sélectionne le protocole auquel la règle va s'appliquer (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).
      
      **Remarques** - Zone à format libre utilisée pour saisir une remarque concernant cette règle.

4. Cliquez sur une règle pour l'éditer ou cliquez sur le signe plus au bas du tableau pour ajouter une règle supplémentaire. Cliquer sur l'icône avec le signe moins permet de supprimer la règle. Les règles sont automatiquement validées dès que vous les saisissez.
5. Lorsque la configuration opérationnelle est terminée, cliquez sur le bouton **Mettre à jour les règles** pour qu'elle s'applique au pare-feu. En principe, les règles prennent effet en l'espace de deux minutes.

## Ports communs

| Protocole | Port |
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
| RDP | 3389 |
| PostgreSQL | 5432 |
| Web VNC | 5800 |
| Client VNC | 5900 |
| Urchin | 9999 ou 10000 ||
