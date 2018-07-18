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

# Configurar o firewall

A configuração do firewall é tão simples quanto criar um conjunto de regras para
permitir o acesso a determinados endereços IP/portas de endereços de Internet
específicos enquanto nega o tráfego de outras fontes.

## Incluindo um firewall em um servidor

Para incluir um firewall em um servidor, clique no link **Dispositivos >
Lista de dispositivos > Clique no servidor desejado > Configuração > Parte inferior da
página: Pedir Hardware Firewall** no Portal do cliente. Isso inicia o
processo de ordem para um firewall apropriado com base na velocidade de uplink do
servidor selecionado. Se você receber um erro, consulte as
[Limitações conhecidas](known-limitations.html) e/ou entre em contato
com o suporte do SoftLayer.

## Editando regras

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
      
      **CIDR** - esse campo indica a notação CIDR padrão para a origem selecionada. "32" implementará a regra para um IP único, enquanto, por exemplo, "24" implementará a regra para 256 IPs.
      
      **Destino** - esse campo seleciona o IP de destino
(consulte [Limitações conhecidas](known-limitations.html) se houver
problemas).
      
      **CIDR** - esse campo indica a notação CIDR padrão para o destino selecionado.
      
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

    
