---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-19"

keywords: cli, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# Esercitazione introduttiva
{: #getting-started}

In questa esercitazione, vengono forniti i passi per installare una serie di strumenti per sviluppatori {{site.data.keyword.cloud}}, verificare l'installazione e configurare l'ambiente. {{site.data.keyword.dev_cli_notm}} offre un approccio da riga di comando per la creazione, lo sviluppo e la distribuzione di applicazioni cloud.
{: shortdesc}

Il comando di installazione in questa esercitazione installa l'ultima versione disponibile della CLI {{site.data.keyword.cloud_notm}} autonoma, oltre ai seguenti strumenti:

* `Homebrew` (solo Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.cos_full_notm}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}

## Prima di iniziare
{: #idt-prereq}

Hai bisogno di un [account {{site.data.keyword.cloud_notm}} ](https://cloud.ibm.com/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") e dei seguenti requisiti di sistema:

* Se stai utilizzando Windows&trade;, alcune funzioni non sono supportate a meno che tu non stia utilizzando Windows&trade; 10 Pro.
* Devi utilizzare il canale stabile per Docker con una versione minima di 1.13.1.

## Passo 1. Esegui il comando di installazione
{: #step1-install-idt}

Viene installa la versione più recente della CLI {{site.data.keyword.cloud_notm}} quando esegui il comando.

* Per Mac e Linux&trade;, immetti il seguente comando:
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Per Windows&trade; 10 Pro, esegui il seguente comando come amministratore:
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Fai clic con il tasto destro del mouse sull'icona Windows&trade; PowerShell e seleziona **Run as administrator**.
  {: tip}

Puoi anche scaricare lo script del programma di installazione da questo [repository GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

Se devi utilizzare una versione a 32 bit della CLI o una versione precedente diversa da quella più recente per gli ambienti dedicati {{site.data.keyword.cloud_notm}}, vedi le [release della CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").
{: note}

## Passo 2. Verifica l'installazione
{: #step2-verify-idt}

Per verificare che la CLI e gli strumenti per sviluppatori siano stati installati correttamente, esegui il comando `help`:
```
ibmcloud dev help
```
{: codeblock}

L'output elenca le istruzioni di utilizzo, la versione corrente e i comandi supportati.

## Passo 3. Configura il tuo ambiente
{: #step3-configure-idt-env}

1. Accedi a {{site.data.keyword.cloud_notm}} con il tuo ID IBM. Se hai più account, ti viene richiesto di selezionare quale account utilizzare. Se non specifichi una regione con l'indicatore `-r`, devi selezionare anche una regione.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Se le tue credenziali vengono rifiutate, è possibile che tu stia utilizzando un ID federato. Per eseguire l'accesso con un ID federato, utilizza l'indicatore `--sso`. Per ulteriori dettagli, vedi [Accesso con un ID federato](/docs/iam/federated_id?topic=iam-federated_id#federated_id).
  {: tip}

2. Per accedere ai servizi Cloud Foundry, devi specificare un'organizzazione e uno spazio Cloud Foundry. Puoi immettere il seguente comando per identificare in modo interattivo l'organizzazione e lo spazio:
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  Oppure, se sai a quale organizzazione e spazio appartiene il servizio, puoi utilizzare il seguente comando:
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## Passi successivi
{: #next-steps}

* Sei ora pronto per sviluppare e distribuire la tua prima applicazione. Per ulteriori informazioni, vedi [Creazione e distribuzione delle applicazioni utilizzando la CLI](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli).

* Puoi essere informato sulle nuove release della CLI {{site.data.keyword.cloud_notm}}. Esegui la sottoscrizione al [repository delle release della CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").
