---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installazione manuale dei componenti del plug-in CLI {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-manually}

Se preferisci un controllo più dettagliato per l'installazione dei componenti degli strumenti per gli sviluppatori, puoi installarli manualmente attenendoti alla seguente procedura. Altrimenti, tutti i prerequisiti vengono installati automaticamente per la maggior parte degli utenti utilizzando i [programmi di installazione della piattaforma](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Prima di iniziare
{: cli-before-you-begin}

* Installa la [CLI {{site.data.keyword.cloud}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autonoma in modo da poter supportare l'installazione dei plugin di riga di comando per `ibmcloud`.
* Installa il comando [curl](https://curl.haxx.se/download.html){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") per scaricare i pacchetti tramite la riga di comando.

## Passo 1. Installazione del plugin CLI {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-idt}

Puoi utilizzare i comandi della CLI {{site.data.keyword.cloud_notm}} Developer Tools (ibmcloud dev) per creare un'applicazione ed eseguirne la gestione, la distribuzione, il debug e la verifica.

Installa il plugin `dev` eseguendo questo comando: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Passo 2: Installazione di Docker
{: #install-devtools-docker}

Per l'esecuzione e il debug in locale delle applicazioni, installa [Docker](https://www.docker.com/get-docker){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

## Passo 3. Installazione di Kubernetes:
{: #idt-install-kube}

Kubernetes è un motore di orchestrazione dei contenitori open source per automatizzare la distribuzione, il ridimensionamento e la gestione di applicazioni inserite in contenitori.

Per supportare le distribuzioni inserite in contenitori, installa Kubernetes per la tua piattaforma:

* MacOS:
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

## Passo 4: Installazione dei plugin CLI Kubernetes
{: #idt-install-kubernetes-cli-plugins}

Per gestire le distribuzioni Kubernetes dalla riga di comando, installa i seguenti plugin di contenitore:

* Installa il plugin `container-registry`:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* Installa il plugin `container-service`:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Per ulteriori informazioni, vedi [Configurazione della CLI e della API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Passo 5. Installazione di Helm:
{: #idt-install-helm}

Installa [Helm](https://helm.sh/docs/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno"), che è un gestore pacchetti basato su Kubernetes.

* Gli utenti MacOS e Linux&trade; eseguono i seguenti comandi:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Gli utenti Windows&trade; possono scaricare e installare il [file binario](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} di Helm ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").

## Passo 6. Installazione del plugin CLI {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Puoi utilizzare il plugin CLI {{site.data.keyword.openwhisk}} per gestire i tuoi frammenti di codice nelle azioni, creare trigger e regole per abilitare le tue azioni a rispondere agli eventi e raccogliere le azioni in pacchetti.

Per installare il plug-in della CLI {{site.data.keyword.openwhisk_short}}, immetti il seguente comando:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Per ulteriori informazioni, vedi [Configurazione del plugin CLI {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Passo 7. Installazione del plugin CLI SDK Generator
{: #idt-install-sdk-gen}

Come sviluppatore in {{site.data.keyword.cloud_notm}}, puoi utilizzare questo plugin per generare gli SDK dalla tua definizione API REST conforme con la [Open API Specification ](https://www.openapis.org/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno"). Quando apporti le modifiche alla tua definizione API REST, puoi utilizzare questo plugin per rigenerare solo il SDK anziché rigenerare l'intero progetto.

Installa il plugin CLI SDK Generator:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

Per ulteriori informazioni, vedi [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
