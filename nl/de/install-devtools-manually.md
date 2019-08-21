---

copyright:
  years: 2019
lastupdated: "2019-06-19"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# CLI-Plug-in für {{site.data.keyword.cloud_notm}}-Entwicklertools manuell installieren
{: #install-devtools-manually}

Wenn Sie eine differenziertere Steuerung der Komponenteninstallation bevorzugen, können Sie das Befehlszeilenschnittstellen-Plug-in für die {{site.data.keyword.cloud}}-Entwicklertools manuell installieren. Andernfalls werden alle Voraussetzungen für die meisten Benutzer mithilfe der [Plattforminstallationsprogramme](/docs/cli?topic=cloud-cli-getting-started#step1-install-idt) automatisch installiert.
{: shortdesc}

## Vorbereitende Schritte
{: cli-before-you-begin}

* Installieren Sie die eigenständige [{{site.data.keyword.cloud_notm}}-CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli), um Unterstützung bei der Installation des Befehlszeilen-Plug-ins für {{site.data.keyword.cloud_notm}} zu erhalten.
* Installieren Sie den Befehl [curl](https://curl.haxx.se/download.html){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") zum Herunterladen von Paketen über die Befehlszeile.

## CLI-Plug-in für {{site.data.keyword.cloud_notm}}-Entwicklertools installieren
{: #install-devtools-idt}

Über die Befehle der CLI für {{site.data.keyword.cloud_notm}}-Entwicklertools können Sie eine Anwendung erstellen, sie verwalten, bereitstellen, debuggen und testen.

Führen Sie den folgenden Befehl aus, um das Plug-in für die {{site.data.keyword.cloud_notm}}-Entwicklertools zu installieren: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Docker installieren
{: #install-devtools-docker}

Installieren Sie zum lokalen Ausführen und Debuggen von Apps die Komponente [Docker](https://www.docker.com/get-started){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").

## Kubernetes-Befehlszeilentool installieren
{: #idt-install-kube}

Zur Anzeige einer lokalen Version des Kubernetes-Dashboards und zur Bereitstellung von Anwendungen in Ihren Clustern installieren Sie das [Kubernetes-Befehlszeilentool](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window}![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") für Ihre Plattform:

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

Das Präfix für die Ausführung von Befehlen über das Kubernetes-Befehlszeilentool ist `kubectl`. Weitere Informationen finden Sie in [CLI und API einrichten](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## CLI-Plug-in für {{site.data.keyword.cos_full_notm}} installieren

Das {{site.data.keyword.cos_full_notm}}-Plug-in erweitert die {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle (CLI) mit einem API-Wrapper für die Arbeit mit Objektspeicherressourcen.

* Führen Sie den folgenden Befehl aus, um das {{site.data.keyword.cos_full_notm}}-Plug-in zu installieren:
  ```
  ibmcloud plugin install cloud-object-storage
  ```
  {: codeblock}

Weitere Informationen finden Sie in der [{{site.data.keyword.cos_full_notm}}-Befehlsreferenz](/docs/cloud-object-storage-cli-plugin?topic=cloud-object-storage-cli-ic-cos-cli).

## CLI-Plug-in für {{site.data.keyword.registrylong_notm}} installieren
{: #idt-install-container-registry-cli-plugin}

Sie können das CLI-Plug-in `container-registry` verwenden, um Ihren eigenen Image-Namensbereich in einer von IBM gehosteten und verwalteten privaten Registry zu konfigurieren. Dort können Sie Docker-Images speichern und mit allen Benutzern in Ihrem {{site.data.keyword.cloud_notm}}-Konto gemeinsam nutzen.

* Führen Sie den folgenden Befehl aus, um das {{site.data.keyword.registrylong}}-Plug-in zu installieren:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

Weitere Informationen finden Sie in der [{{site.data.keyword.registrylong}}-Befehlsreferenz](/docs/services/Registry?topic=container-registry-cli-plugin-containerregcli).

## CLI-Plug-in für {{site.data.keyword.containerlong_notm}} installieren
{: #idt-install-kubernetes-cli-plugin}

Gehen Sie wie folgt vor, um Kubernetes-Cluster in {{site.data.keyword.containerlong}} zu erstellen und zu verwalten:

* Führen Sie den folgenden Befehl aus, um das {{site.data.keyword.registryshort_notm}}-Plug-in zu installieren:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Weitere Informationen finden Sie in der [{{site.data.keyword.registryshort_notm}}-Befehlsreferenz](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Helm installieren
{: #idt-install-helm}

Installieren Sie den auf Kubernetes basierenden Paketmanager [Helm](https://helm.sh/docs/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").

* Benutzer von Mac und Linux&trade; können die folgenden Befehle ausführen:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade;-Benutzer können die Helm-[Binärdatei](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") herunterladen und installieren.

## {{site.data.keyword.openwhisk_short}}-CLI-Plug-in installieren
{: #idt-install-functions}

Mit dem {{site.data.keyword.openwhisk}}-CLI-Plug-in können Sie Ihre Code-Snippets in Aktionen verwalten, Aktionen in Pakete packen sowie Auslöser und Regeln erstellen, um Ihre Aktionen für die Reaktion auf Ereignisse zu aktivieren.

Führen Sie den folgenden Befehl aus, um das Plug-in für die {{site.data.keyword.openwhisk_short}}-CLI zu installieren:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Weitere Informationen hierzu finden Sie im Abschnitt [Das {{site.data.keyword.openwhisk_short}}-CLI-Plug-in installieren](/docs/openwhisk?topic=cloud-functions-cli_install).

