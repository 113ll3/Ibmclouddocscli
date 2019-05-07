---

copyright:
  years: 2019
lastupdated: "2019-04-29"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installazione manuale del plugin della CLI {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-manually}

Puoi installare manualmente il plugin della CLI (command line interface) {{site.data.keyword.cloud}} Developer Tools se preferisci un controllo più granulare per l'installazione dei componenti. Altrimenti, tutti i prerequisiti vengono installati automaticamente per la maggior parte degli utenti utilizzando i [programmi di installazione della piattaforma](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Prima di iniziare
{: cli-before-you-begin}

* Installa la [CLI {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autonoma per ottenere supporto per l'installazione dei plugin della riga di comando per {{site.data.keyword.cloud_notm}}.
* Installa il comando [curl](https://curl.haxx.se/download.html){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") per scaricare i pacchetti tramite la riga di comando.

## Installazione del plugin della CLI {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-idt}

Puoi utilizzare i comandi della CLI {{site.data.keyword.cloud_notm}} Developer Tools per creare un'applicazione, gestirla, distribuirla, eseguirne il debug e verificarla.

Per installare il plugin {{site.data.keyword.cloud_notm}} Developer Tools, immetti il seguente comando: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Installazione di Docker
{: #install-devtools-docker}

Per l'esecuzione e il debug in locale delle applicazioni, installa [Docker](https://www.docker.com/get-started){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

## Installazione dello strumento della riga di comando Kubernetes
{: #idt-install-kube}

Per visualizzare una versione locale del dashboard Kubernetes e per distribuire le applicazioni nei tuoi cluster, installa lo [strumento della riga di comando Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") per la tua piattaforma:

* Mac:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux&trade;:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows&trade;:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

Il prefisso per l'esecuzione di comandi utilizzando lo strumento della riga di comando Kubernetes è `kubectl`. Per ulteriori informazioni, vedi [Configurazione della CLI e della API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Installazione del plugin della CLI {{site.data.keyword.registrylong_notm}}
{: #idt-install-container-registry-cli-plugin}

Puoi utilizzare il plugin della CLI `container-registry` per configurare il tuo spazio dei nomi di immagini in un registro privato, gestito e ospitato da IBM. In cui puoi memorizzare e condividere le immagini Docker con tutti gli utenti nel tuo account {{site.data.keyword.cloud_notm}}. 

* Per installare il plugin {{site.data.keyword.registrylong}}, immetti il seguente comando:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

Per ulteriori informazioni, vedi il [riferimento ai comandi {{site.data.keyword.registrylong}}](/docs/services/Registry?topic=registry-registry_cli_reference).

## Installazione del plugin della CLI {{site.data.keyword.containerlong_notm}}
{: #idt-install-kubernetes-cli-plugin}

Per creare e gestire i cluster Kubernetes in {{site.data.keyword.containerlong}}:

* Per installare il plugin {{site.data.keyword.registryshort_notm}}, immetti il seguente comando:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Per ulteriori informazioni, vedi il [riferimento ai comandi {{site.data.keyword.registryshort_notm}}](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Installazione di Helm
{: #idt-install-helm}

Installa [Helm](https://helm.sh/docs/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno"), che è un gestore pacchetti basato su Kubernetes.

* Gli utenti Mac e Linux&trade; eseguono i seguenti comandi:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Gli utenti Windows&trade; possono scaricare e installare il [file binario](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") di Helm.

## Installazione del plugin della CLI {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Puoi utilizzare il plugin della CLI {{site.data.keyword.openwhisk}} per gestire i tuoi frammenti di codice nelle azioni, raggruppare le azioni in pacchetti e creare trigger e regole per consentire alle azioni di rispondere agli eventi.

Per installare il plugin della CLI {{site.data.keyword.openwhisk_short}}, immetti il seguente comando:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Per ulteriori informazioni, vedi [Configurazione del plugin CLI {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Installazione del plugin della CLI SDK Generator
{: #idt-install-sdk-gen}

Come sviluppatore di {{site.data.keyword.cloud_notm}}, puoi utilizzare il plugin per generare SDK dalla tua definizione dell'API REST conforme alla [Open API Specification](https://www.openapis.org/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno"). Quando è coinvolta la tua definizione API REST, puoi utilizzare il plugin per rigenerare solo il SDK anziché rigenerare l'intero progetto.

Per installare il plugin della CLI SDK Generator, immetti il seguente comando:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

Per ulteriori informazioni, vedi [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
