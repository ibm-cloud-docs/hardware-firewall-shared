---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: viewing, logs, reports, firewall, troubleshooting

subcollection: hardware-firewall-shared

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:note: .note}
{:important: .important}

# Visualización de informes de registro del cortafuegos de hardware
{: #viewing-log-reports-for-hardware-firewall}

Los registros están disponibles por cada IP navegando al dispositivo protegido, seleccionando el separador **Cortafuegos** y pulsando **Acciones > Registros de cortafuegos**. Los registros se presentan en formato .CSV y contienen lo siguiente:

**Tipo de suceso:** la acción que realiza el cortafuegos (Denegar)

**Protocolo:** el protocolo utilizado para la comunicación (TCP/PING/UDP/IRD/etc.)

**Dirección IP de origen:** IP donde se origina el paquete

**Puerto de origen:** puerto donde se origina el paquete

**IP de destino:** destino previsto para el paquete

**Puerto de destino:** puerto previsto para el paquete

**Fecha de creación:** fecha y hora de la acción (formato 24 horas)
