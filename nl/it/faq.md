---

copyright:
  years: 2019
lastupdated: "2019-08-07"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:external: target="_blank" .external}

# Domande frequenti
{: #ibm-cli-faq}

## È necessario utilizzare l'ultima versione della CLI {{site.data.keyword.cloud_notm}}?
{: #cli-latest-version}

Sì, devi utilizzare l'ultima versione. Puoi controllare quale versione stai utilizzando immettendo il seguente comando:

```
ibmcloud -v
```
{: codeblock}

## Come aggiornare la CLI
{: #cli-update-version}

Immetti il seguente comando per eseguire l'aggiornamento all'ultima versione della CLI:

```
ibmcloud update
```
{: codeblock}

## Come ricevo notifiche sulle nuove release della CLI?
{: #cli-get-notified}

Sì, puoi essere informato sulle nuove release della CLI come sono disponibili. Esegui la sottoscrizione al [repository delle release della CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}

## Qual è la struttura dei file per le applicazioni {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Le applicazioni create o abilitate dalla CLI sono fornite con impostazioni preconfigurate incapsulate nel file `cli-config.yml`. Il file `cli-config.yml` contiene le voci predefinite utilizzate dai comandi della CLI che possono essere sovrascritte dai valori passati attraverso la riga di comando.

Le applicazioni che sono state distribuite in una toolchain DevOps possono anche contenere file come `toolchain.yml` e `pipeline.yml`. Le applicazioni che vengono distribuite manualmente possono contenere un file `manifest.yml` e i file di grafico Helm (ad esempio, per le distribuzioni in Cloud Foundry o Kubernetes).

## Come vengono utilizzati i contenitori locali?
{: #cli-faq-containers}

Il plugin della CLI {{site.data.keyword.dev_cli_long}} utilizza due contenitori per facilitare la creazione e la verifica della tua applicazione. Il primo è il contenitore degli strumenti, che contiene i programmi di utilità necessari per creare e verificare la tua applicazione. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Puoi pensare a esso come un contenitore di sviluppo poiché contiene gli strumenti utilizzati normalmente per lo sviluppo di uno specifico runtime.

Il secondo contenitore è il contenitore di esecuzione, che imita da vicino l'ambiente di runtime effettivo della tua applicazione una volta distribuita al cloud. Questo contenitore è di un formato adeguato per essere distribuito per l'utilizzo, ad esempio, in {{site.data.keyword.cloud_notm}}. Di conseguenza, viene definito un punto di ingresso che avvia la tua applicazione. Quando selezioni di eseguire la tua applicazione tramite il plugin CLI {{site.data.keyword.dev_cli_long}}, utilizza questo contenitore. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

## Come distribuisco il codice esistente?

Per distribuire una base di codice esistente, vedi [Generazione di asset di abilitazione di distribuzione e cloud](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

