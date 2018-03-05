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

# Sobre

Um Firewall de hardware (compartilhado) é um dispositivo de rede que está conectado
para envio de dados de um servidor. O firewall bloqueia tráfego indesejado de um servidor
antes mesmo que o tráfego atinja o servidor. A principal vantagem de ter um Firewall de
hardware é que um servidor tem que manipular apenas tráfego 'bom' e nenhum recurso é
desperdiçado lidando com tráfego 'mau'. 

O Firewall de hardware (compartilhado) alavanca uma plataforma corporativa de
diversos locatários para proteger um servidor individual. Ele pode ser comprado com o
servidor ou incluído posteriormente. Ele fornece segurança de rede virtualizada por meio de sua tecnologia de Domínio Virtual (VDOM), fornecendo domínios de segurança virtualizados que são provisionados e gerenciados separadamente.  

Como existem vários clientes associados ao hardware, se o firewall falhar ou for sobrecarregado por um ataque, cada cliente que compartilha uma instância do Firewall de hardware (compartilhado) pode ser impactado. 

Até 79 regras de firewall podem ser configuradas para os endereços IP primário e estaticamente roteado designados ao servidor. Relatórios para Firewalls compartilhados estão disponíveis com base na atividade de um único IP para um intervalo de data selecionado. Os clientes podem gerenciar o firewall por meio da GUI FortiOS baseada na web ou pela CLI (interface da linha de comandos) usando SSH. Também pode ser solicitada uma alta disponibilidade, que fornece configurações sincronizadas a dois dispositivos em implementação
ativa/passiva.

Como a largura de banda mensal do servidor é registrada na porta do comutador do
servidor, o tráfego bloqueado pelo Firewall de hardware (compartilhado) não é contado com
relação a dotações mensais, eliminando a necessidade de pagar por tráfego indesejado.

## Visão geral e recursos

**Uso desejado:** proteção a IP primário de servidor único

**Interface com o usuário:** integrada no Portal de controle do SoftLayer e na API do SoftLayer

**Recursos:** inspeção de pacote stateful, regras de firewall de
ingresso, IPv4, IPv6, criação de log básica

**Rendimento:** 10Mbps, 100Mbps, 1000Mbps ou 2000Mbps 

É necessário que o rendimento da instância do Firewall de hardware (compartilhado)
corresponda à velocidade de Uplink do servidor no qual o firewall está sendo incluído.
