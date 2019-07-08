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

# Preguntas más frecuentes del cortafuegos de hardware
{: #faqs-for-hardware-firewall-shared-}

Las preguntas siguientes son las más frecuentes cuando se trabaja con el cortafuegos de hardware.

## ¿Qué es un cortafuegos?
{: faq}

Un cortafuegos es un dispositivo de red que está conectado en sentido ascendente desde un servidor. El cortafuegos bloquea el tráfico no deseado de un servidor antes de que llegue al servidor.

## ¿Por qué debo utilizar un cortafuegos?
{: faq}

La principal ventaja de tener un cortafuegos es que el servidor sólo tiene que manejar el tráfico "bueno", lo que significa que el recurso se va a utilizar únicamente para su propósito previsto, en lugar de manejar también el tráfico no deseado.

## ¿Qué productos de cortafuegos ofrece IBM©?
{: faq}

Para ver una comparación detallada de todos los productos de cortafuegos que se ofrecen en IBM© Cloud, consulte este [tema](/docs/infrastructure/fortigate-10g?topic=fortigate-10g-exploring-firewalls).

## ¿Es compatible el cortafuegos de hardware con los productos de equilibrador de carga de IBM?
{: faq}

Sí. El cortafuegos de hardware es compatible con el servicio de equilibrio de carga en la nube, el equilibrador de carga local y Citrix Netscaler VPX y MPX.

## ¿Se pueden proteger las IP portátiles con el cortafuegos de hardware?
{: faq}

No. La protección de las IP portátiles no está disponible porque se pueden mover entre servidores. Se hacen excepciones caso por caso, ya que hay numerosas advertencias y se requieren detalles adicionales sobre el diseño del sistema del cliente.

## ¿Puedo tener un cortafuegos de hardware y una pasarela de red asociados con la misma VLAN?
{: faq}

No, no es posible tener un cortafuegos de hardware (estándar o compartido) y un dispositivo de pasarela de red asignados a la misma VLAN.  La funcionalidad ampliada del dispositivo de pasarela de red proporciona características de cortafuegos a la red en lugar de un cortafuegos estándar o compartido.

## El tráfico público, ¿pasa primero por el equilibrador de carga o por el cortafuegos de hardware?
{: faq}

Cuando procede de Internet público, los productos de equilibrio de carga van primero, después los productos de cortafuegos de hardware, y por último los productos de NetScaler (junto con los servidores de los clientes).

## ¿Debe coincidir la velocidad de puerto de enlace ascendente de un servidor con la del cortafuegos de hardware?
{: faq}

La velocidad del cortafuegos de hardware debe coincidir con la velocidad de enlace ascendente del servidor. Sin embargo, puesto que sólo protege la parte pública de la red, es la velocidad de enlace ascendente público la que debe coincidir con la selección del cortafuegos.  Si lo desean, los clientes pueden crear una incidencia para solicitar que se degraden solo las interfaces públicas.

## ¿Cobra IBM Cloud el ancho de banda del cortafuegos?
{: faq}

El cortafuegos de hardware, el cortafuegos de hardware (dedicado) y el dispositivo de seguridad FortiGate (FSA) de 1 Gbps no se miden por ancho de banda.  Al FSA de 10G se le factura el ancho de banda de cortafuegos tras haber utilizado 20 TB. Además, estos productos pueden reducir el uso total de ancho de banda limitando el tráfico al que deben responder los servidores.

## ¿Cómo puedo actualizar el enlace ascendente del cortafuegos de hardware?
{: faq}

El cortafuegos de hardware está bloqueado a la velocidad de puerto de enlace ascendente público de un servidor. Para actualizar, cancele el cortafuegos, actualice la velocidad de puerto del servidor y pida un nuevo cortafuegos. Como alternativa, puede desplegar un nuevo servidor con los enlaces ascendentes deseados y el cortafuegos asociado.

## ¿Es posible la alta disponibilidad con el cortafuegos de hardware?
{: faq}

No. La plataforma de cortafuegos de hardware es de nivel empresarial y altamente duradera, pero la alta disponibilidad (dispositivos redundantes) no es una opción para el cortafuegos de hardware. Para la alta disponibilidad, se necesita un cortafuegos de hardware (dedicado con alta disponibilidad) o un dispositivo de seguridad FortiGate (alta disponibilidad).  El producto de pasarela de red también tiene una opción de alta disponibilidad con funciones de cortafuegos.

## Estoy ejecutando un hipervisor en un servidor de IBM Cloud. El cortafuegos de hardware, ¿protege las máquinas virtuales que se ejecutan en el hipervisor?
{: faq}

No. Las IP portátiles se utilizan para las VM en un entorno de hipervisor y las direcciones IP portátiles no están protegidas por el cortafuegos de hardware.  Se recomienda un cortafuegos de hardware (dedicado) o un dispositivo de seguridad FortiGate.

## ¿Qué son los puertos inactivos en el cortafuegos de Windows?
{: faq}

IBM Cloud ofrece muchos servicios diferentes que puede utilizar con el servidor, como supervisión de Evault, SNMP y Nagios. Estos servicios requieren que nuestros sistemas internos se comuniquen con el servidor en cierta medida. Los puertos inactivos que se ven en la lista de excepciones son puertos abiertos solo en el puerto de red interno. Siguen bloqueados en la conexión de red pública (a Internet). Puesto que la red interna es una red protegida, tener estos puertos abiertos se considera seguro.

Por lo general, estos puertos generalmente no se pueden modificar; sin embargo, si restablece las reglas de cortafuegos, se eliminarán de la lista de excepciones. Tenga en cuenta que restablecer las reglas de cortafuegos no solo puede afectar negativamente a estos servicios adicionales, sino que también puede producir otros problemas con el servidor, en función de su configuración actual.

## ¿Qué opciones de cortafuegos de hardware están disponibles para servidores a 10 Gbps?
{: faq}

FSA de 10G es la única opción para dar soporte a servidores a 10 Gbps para el tráfico público y privado. Si 10 Gbps solo se necesita en la red privada (para la base de datos, la copia de seguridad, el almacenamiento, etc.), los clientes pueden solicitar que se degraden solo los enlaces ascendentes públicos y pedir alguno de los otros productos de cortafuegos de hardware.

## ¿Qué rangos de IP puedo permitir a través del cortafuegos?
{: faq}

Para consultar la lista de direcciones IP y los rangos IP que se pueden permitir a través del cortafuegos, vaya [aquí](/docs/infrastructure/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges){: new_window}.

## ¿Qué opciones de VPN se incluyen con cada producto de cortafuegos?
{: faq}

No todos los cortafuegos ofrecen VPN y no todas las opciones de VPN son las mismas.  Las opciones generales para VPN son:

* Cada cliente recibe conexiones ilimitadas VPN con SSL a nuestra red privada. Estas conexiones pueden establecerse pulsando el enlace de VPN en la parte superior de la página, con la sesión iniciada en el portal de clientes.
* Los clientes también reciben una VPN PPTP por cuenta. Pueden añadir más usuarios de VPN PPTP a su cuenta en paquetes de 5 por 5 USD/mes adicionales.
* SoftLayer también ofrece un servicio de VPN IPSec multiarrendatario básico a partir de 99 USD/mes.
* El dispositivo de seguridad FortiGate de 1G proporciona opciones de VPN IPSec y SSL con acceso sólo a la red pública (sin acceso a la red privada de SoftLayer). El FSA de 10G proporciona opciones de VPN IPSec y SSL con acceso a la red pública o privada.
* La pasarela de red proporciona funciones SSL, IPSec y OpenVPN en la red pública o privada.
* Los productos NetScaler pueden proporcionar VPN IPSec y SSL en la red pública o privada.
* Los clientes también pueden desplegar una solución VPN en un servidor dentro de su entorno de IBM Cloud.

## ¿Qué productos de cortafuegos son compatibles con la segmentación de VLAN privada o NAT pública a privada?
{: faq}

El dispositivo de seguridad Fortigate de 10G da soporte a la segmentación de VLAN privada y NAT. El resto de las ofertas de cortafuegos solo dan soporte al tráfico público.
