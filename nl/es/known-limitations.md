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

# Limitaciones conocidas del cortafuegos de hardware
{: #known-limitations-with-hardware-firewall-shared-}

Un cortafuegos de hardware no se puede desplegar en un servidor en una VLAN que cumpla alguno de los siguientes criterios.

* Que esté actualmente asociado con una pasarela de red, un cortafuegos de hardware o un dispositivo de seguridad FortiGate.
* Que contenga 30 o más servidores.
* Que tenga una subred primaria que sea mayor que una /28.

En estos casos, se debe establecer una nueva VLAN para el cortafuegos o se debe seleccionar otro producto.

Entre otras limitaciones para el cortafuegos de hardware, se incluyen:

* Las subredes portátiles no están protegidas.
* No está disponible para servidores 10Gb.
* 79 reglas de cortafuegos como máximo por cortafuegos de hardware.
* No es compatible con Windows Network Load Balancing (NLB) debido a la forma en la que se procesa el ARP.
* La subred de destino de regla está limitada a la IP pública del servidor protegido. El cortafuegos de hardware (dedicado) no tiene esta limitación.
* No se permiten servidores de facturación por horas. El cortafuegos de hardware se puede aplicar a servidor de facturación mensual.
