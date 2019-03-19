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

# Visualizando vários firewalls
{: #viewing-your-various-firewalls} 

Você pode identificar os firewalls em uso em uma conta e suas VLANs associadas, bem como identificar as VLANs desprotegidas e planejar a implementação de uma solução de firewall.

## Visão geral de firewall por VLAN

Para obter uma visão geral de firewalls em seu sistema, bem como iniciar o gerenciamento básico, navegue para **Rede > Gerenciamento de IP > VLANs** no [Portal do cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){: new_window}.

**NOTA:** Para visualizar apenas VLANs públicas, clique no menu suspenso **Filtrar** e insira ``fcr`` para **Roteador primário**. 

Cada linha representa uma VLAN em sua infraestrutura. O IBM© Cloud preenche as informações de **NÚMERO DA
VLAN** e **ROTEADOR PRIMÁRIO** automaticamente, indicando o número verdadeiro
da VLAN e o roteador no qual ela está configurada. Use o campo **NAME** para definir um nome reconhecível. 

A coluna **GATEWAY/FIREWALL** contém detalhes sobre qual proteção de firewall de hardware está em vigor, por exemplo:

**Incluir firewall** indica que não há firewalls em vigor para servidores nessa VLAN.

**Servidores individualmente protegidos** indica que um ou mais servidores estão usando um Hardware Firewall (Shared) e que não há um Hardware Firewall (Dedicated), FortiGate Security Appliance ou gateway de rede em vigor. Os firewalls de VLAN e os gateways de rede não podem ser colocados em uma VLAN que tem servidores protegidos individualmente.

**Firewall-vlanXXXX.networklayer.com** indica que há um Hardware Firewall (Dedicated) ou FortiGate Security Appliance em vigor. Somente um firewall de VLAN ou um gateway de rede pode ser associado a uma VLAN, mas um servidor pode ser protegido na VLAN pública por um firewall de VLAN e associado na rede privada a um gateway de rede.

**Nome do gateway** indica a VLAN associada a esse gateway de rede.

## Visualização Servidores protegidos individualmente

Na tela VLANs, identifique uma linha com **Servidores protegidos individualmente** na coluna **Gateway/Firewall** e clique no link do número da VLAN associada. Isso exibirá os detalhes da VLAN, incluindo os dispositivos associados.

A partir daqui, você pode clicar em cada dispositivo e revisar se um firewall está em vigor para esse servidor específico.

Depois de ter clicado em um dispositivo, role para a parte inferior da guia Configuração. Você verá **Firewall** na seção Complementos com um status de **Instalado** ou **Não instalado**. **Não instalado** indica que nenhum firewall está em vigor para esse dispositivo. **Instalado** indica que um firewall está em vigor e você terá uma guia **Firewall** disponível no dispositivo no qual poderá gerenciar a configuração do firewall.

## Visualização Firewall dedicado

Na tela VLANs, identifique uma linha com **Firewall-vlanXXXX.networklayer.com** na coluna **Gateway/Firewall** e clique nesse firewall. Você é apresentado a um Hardware Firewall (Dedicated) ou um FortiGate Security Appliance. Os detalhes do dispositivo incluem o roteador associado, VLAN e Subnets IPv4/IPv6, os dispositivos associados a essa VLAN e os controles para rotear o tráfego através ou em torno do firewall.

Os dispositivos **FortiGate Security Appliance** terão um IP de gerenciamento, um nome de usuário e uma senha.  O gerenciamento é concluído por meio da GUI de gerenciamento ou do console baseado em SSH.

## Visualização Gateway de rede

Na tela VLANs, identifique uma linha com a coluna **Gateway/Firewall** preenchida por um nome de dispositivo de Gateway de rede e clique nesse gateway de rede. Você então será levado para a interface que exibe as opções associadas frontend (FCR) e backend (BCR) de gerenciamento de VLANs e gateway de rede.
