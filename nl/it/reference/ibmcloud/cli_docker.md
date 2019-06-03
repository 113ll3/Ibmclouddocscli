---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Utilizzo {{site.data.keyword.dev_cli_notm}} da un contenitore Docker
{: #using-idt-from-docker}

Con il contenitore Docker di {{site.data.keyword.dev_cli_notm}}, ottieni la CLI {{site.data.keyword.cloud}}, oltre ai seguenti strumenti:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Prima di iniziare
{: #idt-docker-prereq}

Hai bisogno di un [account {{site.data.keyword.cloud_notm}}](https://{DomainName}/login){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno") e devi installare l'ultima versione stabile di Docker prima di completare la seguente procedura. 

## Passo 1. Estrai l'immagine Docker dall'hub Docker.
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Passo 2. Avvia il contenitore Docker.
{: #step2-start-docker}

Utilizza il seguente comando per avviare il contenitore Docker di {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Passo 3: Accedi a {{site.data.keyword.cloud_notm}} con il tuo ID IBM.
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

Se le tue credenziali vengono rifiutate, è possibile che tu stia utilizzando un ID federato. Per ulteriori dettagli, vedi [Accesso con un ID federato](/docs/iam?topic=iam-federated_id#federated_id).
{: tip}

Il plugin CLI {{site.data.keyword.dev_cli_notm}} utilizza due contenitori per facilitare la creazione e la verifica della tua applicazione. Il primo è il contenitore degli strumenti, che contiene i programmi di utilità necessari per creare e verificare la tua applicazione. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Puoi pensare a esso come un contenitore di sviluppo poiché contiene gli strumenti utilizzati normalmente per lo sviluppo di uno specifico runtime.

Il secondo contenitore è il contenitore di esecuzione, che simula fedelmente l'ambiente di runtime effettivo della tua applicazione quando viene distribuita nel cloud. Questo contenitore è di un formato adeguato per essere distribuito per l'utilizzo, ad esempio, in {{site.data.keyword.cloud_notm}}. Di conseguenza, viene definito un punto di ingresso che avvia la tua applicazione. Quando selezioni di eseguire la tua applicazione tramite il plugin CLI {{site.data.keyword.dev_cli_notm}}, utilizza questo contenitore. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

Sei ora pronto a utilizzare {{site.data.keyword.dev_cli_notm}} per gestire le risorse {{site.data.keyword.cloud_notm}} e per sviluppare e distribuire le tue applicazioni. 
