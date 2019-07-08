---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: configure, configuring, firewall, add, adding, edit, editing, rules, ports, common

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

# Configurando o Hardware Firewall
{: #configuring-the-hardware-firewall-shared-}

A configuração do firewall é tão simples quanto criar um conjunto de regras para
permitir o acesso a determinados endereços IP/portas de endereços de Internet
específicos enquanto nega o tráfego de outras fontes.

## Incluindo um firewall em um servidor
{: #adding-a-firewall-to-a-server}

Para incluir um firewall em um servidor, siga as etapas em
[Introdução](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-getting-started-with-hardware-firewall-shared). Se você receber um erro, consulte as
[Limitações conhecidas](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) e/ou entre em contato
com o suporte do SoftLayer.

## Editando regras
{: #editing-rules}

Quando um firewall é incluído pela primeira vez em um servidor, um conjunto de
regras é colocado inicialmente no local que permite que todo o tráfego atinja o servidor. As
regras podem então ser editadas para controlar o tráfego que atinge o servidor.

Assegure-se de que o "status" indique que o firewall está "Processando todas as
regras". Os usuários podem optar por efetuar bypass das regras caso as regras
implementadas tenham um impacto indesejado no ambiente, clicando em
**Efetuar bypass de regras** no menu suspenso
**Ações**.

1. Em seu navegador, abra [Portal do Cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){: new_window} e efetue login em sua conta.
2. Na navegação do Portal do cliente, acesse **Dispositivos > Lista de
dispositivos** e clique no dispositivo protegido por firewall que você deseja
configurar.
3. Na guia **Firewall**, assegure-se de que o "Status" indique
que o firewall está "Processando todas as regras".  A página exibe as regras atuais em
vigor para endereços IPv4 e IPv6. Se nenhuma regra estiver implementada, um sinalizador
esmaecido será exibido. Nesse ponto, os links estão disponíveis para editar as regras
atuais.  Essa lista de regras é conhecida como 'configuração de trabalho'. Uma
'configuração de trabalho' é um conjunto de regras que está no processo de ser criado,
mas ainda não foi aplicado ao firewall. Um usuário pode editar, incluir e excluir regras
até que o conjunto de regras seja concluído.

     As regras são exibidas na ordem em que são processadas, com as regras de
numeração mais baixa tendo precedência sobre as de número mais alto (se a regra um
permitir um pacote, as regras dois e acima serão ignoradas pelo pacote).

     Os campos são:

      **Ordem** - esse campo contém o número da regra.  As
regras podem ser movidas para cima ou para baixo na lista com as setas fornecidas.

      **Ação** - essa lista de seleção é usada para 'permitir' ou 'negar' o tráfego que correspondem a essa regra.

      **Origem** - esse campo pode ser 'any' ou um endereço IP específico ou o endereço de rede para uma sub-rede específica.

      **Destino** - esse campo seleciona o IP de destino
(consulte [Limitações conhecidas](/docs/infrastructure/hardware-firewall-shared?topic=hardware-firewall-shared-known-limitations-with-hardware-firewall-shared-) se houver
problemas).

      **CIDR**: esse campo indica a notação CIDR padrão para a origem/destino selecionado.

      **Intervalo de portas** - esses dois campos indicam o intervalo de portas (entre 1 e 65535) ao qual a regra será aplicada.

      **Protocolo** - esse campo seleciona o protocolo ao qual
a regra será aplicada (TCP/GRE/ICMP/UDP/PPTP/AH/ESP).

      **Notas:** campo Formulário livre para inserir qualquer nota sobre essa regra.

4. Clique em uma regra para editá-la ou clique no sinal de mais na parte inferior
da tabela para incluir uma regra adicional. Clicar no ícone menos excluirá a regra. As
regras são automaticamente validadas conforme você as insere.

5. Depois que a 'configuração de trabalho' estiver concluída, pressione o botão
**Atualizar regras** para que a 'configuração de trabalho' seja
aplicada ao firewall. Em dois minutos, as regras deverão entrar em vigor.

## Portas comuns
{: #common-ports}

| Protocolo | Porta |
| :-----: | :-----: |
| FTP | 21 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 |
| DNS | 53 |
| HTTP (Protocolo de Transporte de Hipertexto) | 80 |
| POP3 | 110 |
| IMAP | 143 |
| HTTPS | 443 |
| MSSQL | 1433 |
| MySQL | 3306 |
| Área de trabalho remota | 3389 |
| PostgreSQL | 5432 |
| VNC Web | 5800 |
| VNC Client | 5900 |
| Urchin | 9999 ou 10000 ||
