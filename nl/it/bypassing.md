---

copyright:
  years: 2017
lastupdated: "2018-11-12"

keywords: bypass, bypassing, firewall, rules, enable, enabling

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

# Esclusione delle regole dell'Hardware Firewall
{: #bypassing-the-hardware-firewall-shared-rules}

Per escludere le regole del firewall,

1. Dal tuo browser, apri il [Portale del cliente ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} e accedi al tuo account.
2. Nella navigazione del Portale del cliente, vai a **Devices > Device List** e fai clic sul dispositivo protetto dal firewall che desideri escludere.
3.  Nella scheda **Firewall**, fai clic sul menu a discesa **Actions** e scegli **Bypass Rules**. Fai clic su **Yes** per confermare l'azione. L'esclusione delle regole ha effetto dopo circa due minuti. Durante la modalità di esclusione, "Status" sarà "Bypassing All Rules".

## Riabilita le regole
{: #enable-the-rules-again}

Per riabilitare le regole, completa le precedenti istruzioni per raggiungere la scheda Firewall del dispositivo e fai clic sul menu a discesa **Actions** e scegli **Process Rules**. "Status" dovrebbe ritornare "Processing All Rules" in due minuti.
