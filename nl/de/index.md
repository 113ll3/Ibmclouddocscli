---

copyright:
  years: 2015, 2019
lastupdated: "2019-07-24"

keywords: command line interface, cli, getting started, getting started with IBM Cloud CLI, getting started with IBM Cloud CLI and developer tools tutorial, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# Einführung in die {{site.data.keyword.cloud_notm}}-CLI und {{site.data.keyword.dev_cli_short}}
{: #getting-started}

In diesem Lernprogramm installieren Sie eine Reihe von {{site.data.keyword.cloud}}-Entwicklertools, die die aktuelle {{site.data.keyword.cloud_notm}}-CLI enthalten, und Sie überprüfen die Installation und konfigurieren die Umgebung. Die {{site.data.keyword.dev_cli_notm}} bieten eine Befehlszeilenschnittstellenmethode zum Erstellen, Entwickeln und Bereitstellen von Cloudanwendungen.
{: shortdesc}

Mit dem Installationsbefehl in diesem Lernprogramm werden die aktuelle eigenständige {{site.data.keyword.cloud_notm}}-CLI-Version, die verfügbar ist, sowie die folgenden Tools installiert:

* `Homebrew` (nur Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}}-Plug-in
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}-Plug-in
* {{site.data.keyword.cos_full_notm}}-Plug-in
* {{site.data.keyword.registrylong_notm}}-Plug-in
* {{site.data.keyword.containerlong_notm}}-Plug-in

## Vorbereitende Schritte
{: #idt-prereq}

Sie benötigen ein [{{site.data.keyword.cloud_notm}}-Konto](https://cloud.ibm.com/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") und die folgenden Systemvoraussetzungen:

* Unter Windows&trade werden manche Funktionen nur unterstützt, wenn Sie mit Windows&trade 10 Pro arbeiten.
* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden.

## Schritt 1. Installationsbefehl ausführen
{: #step1-install-idt}

Die aktuellste Version der {{site.data.keyword.cloud_notm}}-CLI wird installiert, wenn Sie den Befehl ausführen.

* Führen Sie für Mac und Linux&trade; den folgenden Befehl aus:
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Führen Sie für Windows&trade; 10 Pro den folgenden Befehl als Administrator aus:
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Klicken Sie mit der rechten Maustaste auf das Symbol für Windows&trade PowerShell und wählen Sie **Als Administrator ausführen** aus.
  {: tip}

Das Installationsscript kann auch aus diesem [GitHub-Repository](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") heruntergeladen werden.

Wenn Sie eine 32-Bit-Version oder eine andere als die aktuelle Version der CLI für {{site.data.keyword.cloud_notm}}-dedizierte Umgebungen verwenden müssen, informieren Sie sich in den [{{site.data.keyword.cloud_notm}}-CLI-Releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").
{: note}

## Schritt 2. Installation verifizieren
{: #step2-verify-idt}

Führen Sie den Befehl `help` aus, um zu überprüfen, dass die CLI und die Entwicklertools erfolgreich installiert wurden:
```
ibmcloud dev help
```
{: codeblock}

Die Ausgabe listet die Verwendungsanweisungen, die aktuelle Version und die unterstützten Befehle auf.

## Schritt 3. Umgebung konfigurieren
{: #step3-configure-idt-env}

1. Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit Ihrer IBMid an. Wenn Sie über mehrere Konten verfügen, werden Sie aufgefordert, das Konto auszuwählen, das verwendet werden soll. Wenn Sie keine Region mit dem Flag `-r` angeben, müssen Sie auch eine Region auswählen.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Verwenden Sie für die Anmeldung mit einer föderierten ID das Flag `--sso`. Weitere Informationen finden Sie unter [Mit föderierter ID anmelden](/docs/iam/federated_id?topic=iam-federated_id#federated_id).
  {: tip}

2. Für den Zugriff auf Cloud Foundry-Services müssen Sie eine Cloud-Foundry-Organisation und einen Cloud Foundry-Bereich angeben. Sie können den folgenden Befehl ausführen, um die Organisation und den Bereich interaktiv anzugeben:
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  Wenn Sie wissen, zu welcher Organisation und zu welchem Bereich der Service gehört, können Sie alternativ auch den folgenden Befehl verwenden:
  ```
  ibmcloud target -o <wert> -s <wert>
  ```
  {: codeblock}

## Nächste Schritte
{: #next-steps}

* Sie können nun Ihre erste App entwickeln und bereitstellen. Weitere Informationen finden Sie in [Apps über die Befehlszeilenschnittstelle erstellen und bereitstellen](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli).

* Sie können Benachrichtigungen zu neuen Releases der {{site.data.keyword.cloud_notm}}-CLI erhalten. Abonnieren Sie das [Release-Repository der {{site.data.keyword.cloud_notm}}-CLI](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").
