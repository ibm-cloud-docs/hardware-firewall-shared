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

# Configuración del cortafuegos de hardware (compartido)
{: #configuring-the-hardware-firewall-shared-}

La configuración del cortafuegos es tan sencilla como crear un conjunto de reglas para permitir el acceso a determinados puertos/direcciones IP de direcciones de Internet específicas y denegar el tráfico de otras fuentes.

## Adición de un cortafuegos a un servidor

Para añadir un cortafuegos a un servidor, siga los pasos de [Iniciación](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared). Si recibe un error, consulte las [Limitaciones conocidas](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) o póngase en contacto con el equipo de soporte de SoftLayer.

## Edición de reglas

Cuando se añade un cortafuegos a un servidor por primera vez, se ponen en práctica una serie de reglas que permiten que todo el tráfico llegue al servidor. Las reglas se pueden editar para controlar el tráfico que llega al servidor.

Asegúrese de que en el "estado" se indica que el cortafuegos está "Procesando todas las reglas". Los usuarios pueden optar por ignorar las reglas, en caso de que las reglas aplicadas tengan un impacto no deseado en su entorno, pulsando **Ignorar reglas** en el desplegable **Acciones**.

1. En el navegador, abra el [Portal de clientes ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window} e inicie sesión en su cuenta.
2. En la navegación del Portal de clientes, vaya a **Dispositivos > Lista de dispositivos** y pulse el dispositivo protegido por cortafuegos que desee configurar.
3. En el separador **Cortafuegos**, asegúrese de que en el "estado" se indica que el cortafuegos está "Procesando todas las reglas".  La página muestra las reglas actuales en vigor para las direcciones IPv4 e IPv6. Si no hay reglas implementadas, aparece un marcador sin color. En este punto, los enlaces están disponibles para editar las reglas actuales.  Esta lista de reglas se conoce como "configuración operativa". Una "configuración operativa" es un conjunto de reglas que está en proceso de creación pero que todavía no se han aplicado al cortafuegos. Un usuario puede editar, añadir y suprimir reglas hasta que el conjunto de reglas se haya completado. 

     Las reglas se visualizan en el orden en que se procesan, y las reglas con números más bajos tienen prioridad sobre las reglas con números más altos (si la regla número uno permite que un paquete pase, el paquete ignora las reglas número dos en adelante).
     
     Los campos son:

      **Orden**: este campo contiene el número de regla.  Las reglas se pueden mover hacia arriba o hacia abajo con las flechas.
      
      **Acción**: esta lista se utiliza para 'permitir' o 'denegar' el tráfico que coincida con esta regla.
      
      **Origen**: este campo puede ser 'todos' o una dirección IP específica o la dirección de red para una subred específica.
      
      **Destino**: este campo selecciona la IP de destino (consulte [Limitaciones conocidas](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) si hay problemas).
      
      **CIDR**: este campo indica la notación CIDR estándar para el origen/destino seleccionado.
      
      **Rango de puertos**: estos dos campos indican el rango de puertos (entre 1 y 65535) a los que se aplicará la regla.
      
      **Protocolo**: este campo selecciona el protocolo al que se aplicará la regla (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).
      
      **Notas:** campo libre para entrar cualquier nota sobre esta regla.

4. Pulse una regla para editarla o pulse el signo más en la parte inferior de la tabla para añadir otra regla. Al pulsar el icono menos, se suprimirá la regla. Las reglas se validan automáticamente a medida que se especifican.
5. Una vez que la 'configuración operativa' se haya completado, pulse el botón **Actualizar reglas** para aplicar la 'configuración operativa' al cortafuegos. Las reglas se aplicarán pasados dos minutos.

## Puertos comunes

| Protocolo | Puerto |
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
| Remote Desktop | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 o 10000 ||
