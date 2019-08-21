---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-21"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# {{site.data.keyword.cloud_notm}}-CLI mit Plug-ins erweitern
{: #plug-ins}

Die {{site.data.keyword.cloud}}-CLI unterstützt ein Plug-in-Framework zur Erweiterung der verfügbaren Funktionalität. Sie können ein Plug-in aus einem Repository oder über eine Web-URL installieren oder eine Plug-in-Binärdatei lokal installieren.

Das [{{site.data.keyword.cloud_notm}}-CLI-Plug-in-Repository](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg) ist das offizielle Repository zum Hosten von Plug-ins.

Wenn Sie weitere Informationen zu den Befehlen zur Verwaltung von Plug-ins benötigen, dann führen Sie den Befehl `ibmcloud plugin` aus, um die Hilfenachrichten anzuzeigen.
{: tip}

## Plug-in aus dem Repository für die {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren
{: #install-from-repo}

### Nach einem Plug-in suchen
{: #cli-search-plugin}

Verwenden Sie den Befehl `ibmcloud plugin repo-plugins -r REPO_NAME`, um nach einem Plug-in im Repository zu suchen.

Die {{site.data.keyword.cloud_notm}}-CLI stellt ein offizielles Plug-in-Repository mit dem Namen 'IBM Cloud' bereit, das Sie wie im folgenden Beispiel durchsuchen können:
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                        Versionen                      Beschreibung
Update verfügbar   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service für die Verwaltung von Kubernetes-Clustern
Update verfügbar   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Cloud-Funktionen verwalten..
```
{: screen}

### Plug-in installieren
{: #cli-install-plugin}

Verwenden Sie den Befehl `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME`, um das Plug-in zu installieren. Verwenden Sie beispielsweise den folgenden Befehl, um ein Plug-in aus dem offiziellen IBM Plug-in-Repository 'IBM Cloud' zu installieren:
```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
Looking up 'auto-scaling' from repository 'IBM Cloud'...
Plug-in 'auto-scaling 0.2.7' found in repository 'IBM Cloud'
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Mit 'ibmcloud plugin show auto-scaling' können Sie die zugehörigen Details anzeigen.
```
{: screen}

## Plug-in lokal installieren
{: #install-plugin-locally}

Verwenden Sie den Befehl `ibmcloud plugin install LOCAL_FILE_NAME`, um eine Plug-in-Binärdatei auf der lokalen Maschine zu installieren. Beispiel:
```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Mit 'ibmcloud plugin show auto-scaling' können Sie die zugehörigen Details anzeigen.
$
```
{: screen}

## Plug-in über Web-URL installieren
{: #install-plugin-from-url}

Verwenden Sie den Befehl `ibmcloud plugin install URL`, um ein Plug-in direkt über eine Web-URL zu installieren. Beispiel:
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Mit 'ibmcloud plugin show auto-scaling' können Sie die zugehörigen Details anzeigen.
$
```
{: screen}
