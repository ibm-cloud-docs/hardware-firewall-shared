---

copyright:
  years: 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Limitaciones conocidas

Un cortafuegos de hardware compartido no se puede desplegar en un servidor en una VLAN que cumpla alguno de los siguientes criterios. 

Un cortafuegos de hardware (compartido) no se puede desplegar en un servidor en una VLAN que cumpla alguno de los siguientes criterios. 

* Que esté actualmente asociado con una pasarela de red, un cortafuegos de hardware o un dispositivo de seguridad FortiGate.
* Que contenga 30 o más servidores.
* Que tenga una subred primaria que sea mayor que una /28.

En estos casos, se debe establecer una nueva VLAN para el cortafuegos o se debe seleccionar otro producto.

Entre otras limitaciones para el cortafuegos de hardware (compartido), se incluyen: 

* No está disponible para servidores 10Gb
* 79 reglas de cortafuegos como máximo por cortafuegos de hardware compartido
* Las subredes portátiles no están protegidas
* No está disponible para servidores 10Gb
* 79 reglas de cortafuegos como máximo por cortafuegos de hardware (compartido)
* No es compatible con Windows Network Load Balancing (NLB) debido a la forma en la que se procesa el ARP
