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

# Plug-in-Komponenten der CLI für {{site.data.keyword.cloud_notm}}-Entwicklertools manuell installieren
{: #install-devtools-manually}

Wenn Sie eine differenziertere Steuerung bei der Installation von Komponenten der Entwicklertools bevorzugen, können Sie die Komponenten mit den folgenden Schritten manuell installieren. Andernfalls werden alle Voraussetzungen für die meisten Benutzer mithilfe der [Plattforminstallationsprogramme](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt) automatisch installiert.
{: shortdesc}

## Vorbereitende Schritte
{: cli-before-you-begin}

* Installieren Sie die eigenständige [{{site.data.keyword.cloud}}-Befehlszeilenschnittstelle (CLI)](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli), damit Sie die Installation von Befehlszeilen-Plug-ins für `ibmcloud` unterstützen können.
* Installieren Sie den Befehl [curl](https://curl.haxx.se/download.html){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") zum Herunterladen von Paketen über die Befehlszeile. 

## Schritt 1. CLI-Plug-in für {{site.data.keyword.cloud_notm}}-Entwicklertools installieren
{: #install-devtools-idt}

Sie können die Befehle der CLI für {{site.data.keyword.cloud_notm}}-Entwicklertools (ibmcloud dev) verwenden, um eine Anwendung zu erstellen, zu verwalten, bereitzustellen, zu debuggen und zu testen.

Installieren Sie das Plug-in `dev`, indem Sie den folgenden Befehl ausführen:  
```
ibmcloud plugin install dev
```
{: codeblock}

## Schritt 2. Docker installieren
{: #install-devtools-docker}

Installieren Sie zum lokalen Ausführen und Debuggen von Apps die Komponente [Docker](https://www.docker.com/get-docker){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").

## Schritt 3. Kubernetes installieren
{: #idt-install-kube}

Kubernetes ist eine Open-Source-Engine für Containerorchestrierung zum Automatisieren der Bereitstellung, Skalierung und Verwaltung von containerbasierten Anwendungen.

Um containerbasierte Bereitstellungen zu unterstützen, installieren Sie Kubernetes für Ihre Plattform:

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

## Schritt 4. Kubernetes-CLI-Plug-ins installieren
{: #idt-install-kubernetes-cli-plugins}

Um Kubernetes-Bereitstellungen über die Befehlszeile zu verwalten, installieren Sie die folgenden Container-Plug-ins:

* Installieren Sie das Plug-in `container-registry`:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* Installieren Sie das Plug-in `container-service`:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Weitere Informationen finden Sie in [CLI und API einrichten](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Schritt 5. Helm installieren
{: #idt-install-helm}

Installieren Sie den auf Kubernetes basierenden Paketmanager [Helm](https://helm.sh/docs/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").

* Benutzer von MacOS und Linux&trade; können die folgenden Befehle ausführen: 
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade;-Benutzer können die Helm-[Binärdatei](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") herunterladen und installieren.

## Schritt 6. {{site.data.keyword.openwhisk_short}}-CLI-Plug-in installieren
{: #idt-install-functions}

Mit dem {{site.data.keyword.openwhisk}}-CLI-Plug-in können Sie Ihre Code-Snippets in Aktionen verwalten sowie Auslöser und Regeln erstellen, damit Ihre Aktionen auf Ereignisse reagieren können, und Aktionen in Paketen bündeln. 

Führen Sie den folgenden Befehl aus, um das Plug-in für die {{site.data.keyword.openwhisk_short}}-CLI zu installieren:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Weitere Informationen finden Sie in [{{site.data.keyword.openwhisk_short}}-CLI-Plug-in einrichten](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Schritt 7. SDK Generator-CLI-Plug-in installieren
{: #idt-install-sdk-gen}

Als Entwickler können Sie dieses Plug-in in {{site.data.keyword.cloud_notm}} verwenden, um SDKs aus Ihrer mit der [Open API-Spezifikation ](https://www.openapis.org/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") kompatiblen REST-API-Definition zu generieren. Wenn Sie Änderungen an Ihrer REST-API-Definition vornehmen, können Sie dieses Plug-in verwenden, um nur das SDK und nicht das gesamte Projekt neu zu erstellen.

Installieren Sie das SDK Generator-CLI-Plug-in:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

Weitere Informationen finden Sie in [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
