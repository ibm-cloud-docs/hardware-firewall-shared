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

# Ver los cortafuegos distintos
{: #viewing-your-various-firewalls} 

Puede identificar los cortafuegos en uso en una cuenta y sus VLAN asociadas, así como identificar las VLAN desprotegidas y planificar el despliegue de una solución de cortafuegos.

## Visión general de cortafuegos por VLAN

Para obtener una visión general de los cortafuegos del sistema, además de iniciar la gestión básica, navegue a **Red > Gestión de IP > VLAN** en el [Portal de clientes ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window}.

**NOTA:** Para ver sólo las VLAN públicas, pulse el desplegable **Filtrar** y escriba ``fcr`` en **Direccionador primario**. 

Cada fila representa una VLAN en la infraestructura. IBM© Cloud rellena la información de **NÚMERO DE VLAN** y **DIRECCIONADOR PRINCIPAL** automáticamente con el número exacto de VLAN y el direccionador en el que está configurada. Utilice el campo **NOMBRE** para definir un nombre reconocible. 

La columna **PASARELA/CORTAFUEGOS** contiene detalles sobre la protección de cortafuegos de hardware que está activa, por ejemplo:

**Añadir cortafuegos** indica que no hay ningún cortafuegos establecido para los servidores de esta VLAN.

**Servidores protegidos individualmente** indica que uno o varios servidores utilizan un cortafuegos de hardware (compartido) y que no hay establecido ningún cortafuegos de hardware (dedicado), dispositivo de seguridad FortiGate o pasarela de red. Las pasarelas de red y los cortafuegos de VLAN no se pueden establecer en una VLAN que tenga servidores protegidos individualmente.

**Cortafuegos-vlanXXXX.networklayer.com** indica que hay establecido un cortafuegos de hardware (dedicado) o un dispositivo de seguridad FortiGate. Solo se puede asociar una pasarela de red o un cortafuegos de VLAN con una VLAN, pero un servidor puede estar protegido en la VLAN pública por un cortafuegos de VLAN y asociado en la red privada con una pasarela de red.

**Nombre de pasarela** indica la pasarela de red con la que está asociada la VLAN.

## Vista de servidores protegidos individualmente

En la pantalla de VLAN, identifique una fila con el valor **Servidores protegidos individualmente** en la columna **Pasarela/cortafuegos** y pulse el enlace del número de VLAN asociada. Se mostrarán los detalles de la VLAN, incluidos los dispositivos asociados.

Desde aquí, puede pulsar en cada dispositivo y revisar si hay un cortafuegos establecido para ese servidor en particular.

Una vez que haya pulsado en un dispositivo, desplácese hasta la parte inferior del separador Configuración. Verá **Cortafuegos** en la sección de complementos con el estado **Instalado** o **No instalado**. **No instalado** indica que no hay ningún cortafuegos establecido para ese dispositivo. **Instalado** indica que hay un cortafuegos establecido, y habrá un separador **Cortafuegos** disponible en el dispositivo, donde podrá gestionar la configuración del cortafuegos.

## Vista de cortafuegos dedicado

En la pantalla de VLAN, identifique una fila con el valor **Cortafuegos-vlanXXXX.networklayer.com** en la columna **Pasarela/cortafuegos** y pulse ese cortafuegos. Aparecerá un cortafuegos de hardware (dedicado) o un dispositivo de seguridad FortiGate. Los detalles del dispositivo incluyen el direccionador asociado, la VLAN y las subredes IPv4/IPv6, los dispositivos asociados con la VLAN y los controles para direccionar el tráfico a través del cortafuegos o sortear el cortafuegos.

Los **dispositivos de seguridad FortiGate** incluirán la IP de gestión, el nombre de usuario y la contraseña.  La gestión se completa mediante la GUI de gestión o la consola basada en SSH.

## Vista de pasarela de red

En la pantalla de VLAN, identifique una fila que tenga un nombre de dispositivo de pasarela de red en la columna **Pasarela/cortafuegos** y pulse dicha pasarela de red. Se le dirigirá a la interfaz que muestra las opciones de gestión de la pasarela de red y las VLAN frontal (FCR) y de fondo (BCR) asociadas.
