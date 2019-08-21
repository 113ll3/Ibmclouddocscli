---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Gestione delle risorse DevOps con la CLI
{: #managing-devops-resources-cli}

Puoi utilizzare la [CLI {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-getting-started) per gestire le risorse DevOps direttamente dalla riga di comando. Impara ad utilizzare la CLI per visualizzare le toolchain, le pipeline e i log di pipeline DevOps.
{: shortdesc}

## Prima di iniziare
{: #set-toolchain-view}

La vista della toolchain dipende dal gruppo di risorse selezionato al momento. Utilizza i seguenti comandi per identificare il tuo gruppo di risorse selezionato al momento e modificalo se lo desideri.

* Per visualizzare il gruppo di risorse selezionato al momento, esegui:
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* Se non viene impostato alcun gruppo di risorse o se desideri modificarlo, esegui: 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Visualizzazione di una toolchain
{: #viewing-toolchains}

Puoi visualizzare le informazioni sulla toolchain dalla riga di comando o visualizzarle in un browser.

* Per visualizzare le toolchain nel gruppo di risorse selezionato, esegui:
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* Per visualizzare i dettagli su tale toolchain, esegui:
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* Per visualizzare i dettagli della toolchain nel browser, esegui:
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Visualizzazione di una pipeline
{: #viewing-pipeline}

Per ottenere i dettagli necessari per richiamare una pipeline, esegui `ibmcloud dev toolchains` per ottenere il nome della toolchain. Se il nome è già noto, esegui `ibmcloud dev toolchain-get [toolchain-name]` per ottenere i dettagli della toolchain. 

* Per ottenere i dettagli di una pipeline e le sue fasi, identifica la pipeline e il suo ID per eseguire il seguente comando:
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* Utilizzando l'ID pipeline dal comando precedente, puoi eseguire la pipeline:
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  Questo comando richiama un'esecuzione della fase e i suoi lavori. Un'esecuzione corretta comporta l'esecuzione del lavoro per ogni lavoro nella fase selezionata.

## Visualizzazione dei log della pipeline
{: #viewing-pipeline-logs}

* Per visualizzare i log dall'esecuzione di una pipeline, esegui:
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* Per filtrare i log per fase, applica il comando precedente e aggiungi l'ID fase:
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Comandi DevOps utili
{: #helpful-devops-commands}

Utilizza i seguenti comandi `ibmcloud dev` per gestire le risorse DevOps.

### Comandi della toolchain
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) Visualizza un elenco di toolchain nel gruppo di risorse selezionato.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) Visualizza i dettagli di una toolchain selezionata nel gruppo di risorse selezionato.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) Apre la toolchain selezionata nel browser.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) Elimina una toolchain.

### Comandi della pipeline
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) Visualizza i dettagli della pipeline di una toolchain.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) Esegue una pipeline.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) Apre la pipeline nel browser.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) Visualizza i log dell'esecuzione di una pipeline.

Per ulteriori informazioni, vedi il [riferimento ai comandi](/docs/cli/idt?topic=idt-cli) `ibmcloud dev` completo.
