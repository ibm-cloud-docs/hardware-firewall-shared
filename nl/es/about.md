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

# Acerca de

Un cortafuegos de hardware (compartido) es un dispositivo de red que está conectado en sentido ascendente desde un servidor. El cortafuegos bloquea el tráfico no deseado de un servidor antes de que el tráfico llegue al servidor. La ventaja principal de tener un cortafuegos de hardware es que el servidor sólo tiene que manejar el tráfico 'bueno' y no se desperdician recursos en el tráfico 'malo'. 

El cortafuegos de hardware (compartido) aprovecha una plataforma empresarial multiarrendatario para proteger a un servidor individual.  Se puede adquirir con el servidor o añadirlo después.  Ofrece seguridad virtualizada de red a través de su tecnología de dominio virtual (VDOM), proporcionando dominios de seguridad virtualizados que se suministran y gestionan por separado.  

Dado que hay varios clientes asociados con el hardware, si el cortafuegos falla o se sobrecarga por un ataque, todos los clientes que comparten una instancia del cortafuegos de hardware (compartido) pueden verse afectados. 

Se pueden configurar hasta 79 reglas de cortafuegos para las direcciones IP primarias y direccionadas estáticamente asignadas al servidor. Hay disponibles informes para cortafuegos compartidos en función de la actividad de una sola dirección IP para un rango de fechas seleccionado.
Los clientes pueden gestionar el cortafuegos a través de la GUI de FortiOS basada en web o la CLI (interfaz de línea de mandatos) utilizando SSH. También se puede pedir alta disponibilidad, que proporciona dos dispositivos en despliegue activo-pasivo con configuraciones sincronizadas.

Puesto que el ancho de banda mensual del servidor se registra en el puerto de conmutador del servidor, el tráfico bloqueado por el cortafuegos de hardware (compartido) no cuenta para la asignación mensual, y así no es necesario pagar por el tráfico no deseado.

## Visión general y características

**Uso previsto:** protección de IP primaria de un único servidor

**Interfaz de usuario:** integrada en SoftLayer Control Portal y API de SoftLayer

**Características:** inspección de paquete con estado, reglas de cortafuegos de ingreso, IPv4, IPv6, registro básico

**Rendimiento:** 10 Mbps, 100 Mbps, 1000 Mbps o 2000Mbps 

Es necesario que el rendimiento de la instancia del cortafuegos de hardware (compartido) coincida con la velocidad de enlace ascendente del servidor al que se va a añadir el cortafuegos.
