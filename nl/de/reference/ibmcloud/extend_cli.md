---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# {{site.data.keyword.Bluemix_notm}}-CLI mit Plug-ins erweitern
{: #plug-ins}

Die {{site.data.keyword.Bluemix_notm}}-CLI unterstützt ein Plug-in-Framework zur Erweiterung der verfügbaren Funktionalität. Sie können ein Plug-in aus einem Repository oder über eine Web-URL installieren oder eine Plug-in-Binärdatei lokal installieren.

Das [{{site.data.keyword.Bluemix_notm}}-CLI-Plug-in-Repository](https://tools.ng.bluemix.net){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg) ist das offizielle Repository zum Hosten von Plug-ins.

Wenn Sie weitere Informationen zu den Befehlen zur Verwaltung von Plug-ins benötigen, dann führen Sie den Befehl `ibmcloud plugin` aus, um die Hilfenachrichten anzuzeigen.
{: tip}

## Plug-in aus dem Repository für {{site.data.keyword.Bluemix_notm}} CLI installieren

### Schritt 1: Plug-in suchen

1. Verwenden Sie den Befehl `ibmcloud plugin repo-plugins -r REPO_NAME`, um nach einem Plug-in im Repository zu suchen.
2. Die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle enthält das offizielle Repository mit dem Namen 'IBM Cloud'. Die offiziellen Plug-ins können Sie wie im folgenden Beispiel beschrieben durchsuchen:

  ```
  $ ibmcloud plugin repo-plugins -r IBM Cloud
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Schritt 2: Plug-in installieren

Verwenden Sie den Befehl `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME`, um das Plug-in zu installieren. Verwenden Sie beispielsweise den folgenden Befehl, um ein Plug-in aus dem offiziellen IBM Plug-in-Repository 'IBM Cloud' zu installieren:

  ```
  $ ibmcloud plugin install auto-scaling -r IBM Cloud
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/IBMCLoudFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Plug-in lokal installieren

Verwenden Sie den Befehl `ibmcloud plugin install LOCAL_FILE_NAME`, um eine Plug-in-Binärdatei auf der lokalen Maschine zu installieren. Beispiel:

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Plug-in über Web-URL installieren

Verwenden Sie den Befehl `ibmcloud plugin install URL`, um ein Plug-in direkt über eine Web-URL zu installieren. Beispiel:

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/IBMCloudFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
