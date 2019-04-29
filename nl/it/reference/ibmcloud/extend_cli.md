---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

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

# Estensione della CLI {{site.data.keyword.cloud_notm}} con i plugin
{: #plug-ins}

La CLI {{site.data.keyword.cloud}} supporta un framework di plugin per estenderne la funzionalità. Puoi installare un plugin da un repository, un URL web o installare un file binario del plugin localmente.

Il [repository di plugin della CLI {{site.data.keyword.cloud_notm}} ](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg) è il repository ufficiale in cui sono ospitati i plugin.

Per ulteriori comandi per gestire i plugin, esegui `ibmcloud plugin` per visualizzare i messaggi della guida.
{: tip}

## Installa un plugin dal repository della CLI {{site.data.keyword.cloud_notm}}
{: #install-from-repo}

### Passo 1: cerca il plugin
{: #step1-search-plugin}

1. Utilizza il comando `ibmcloud plugin repo-plugins -r REPO_NAME` per cercare un plugin nel repository.
2. La CLI {{site.data.keyword.cloud_notm}} ha il repository ufficiale denominato 'IBM Cloud', puoi cercare i plugin ufficiali come mostrato nel seguente esempio:
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                   Versions                       Description   
Update Available   container-service/kubernetes-service   0.2.99, 0.2.95, 0.2.80...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                        1.0.30, 1.0.29, 1.0.28...      IBM Cloud CLI plug-in for IBM Cloud Functions   
...
```
{: screen}

### Passo 2: installa il plugin
{: step2-install-plugin}

Utilizza il comando `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` per installare il plugin. Ad esempio, utilizza il seguente comando per installare un plugin dal repository di plugin ufficiale di IBM 'IBM Cloud':

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
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
```
{: screen}

## Installa un plugin localmente
{: #install-plugin-locally}

Utilizza il comando `ibmcloud plugin install LOCAL_FILE_NAME` per installare un file binario del plugin sulla macchina locale. Ad esempio:

```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}

## Installa un plugin da un URL web
{: install-plugin-from-url}

Utilizza il comando `ibmcloud plugin install URL` per installare un plugin direttamente da un URL web. Ad esempio:
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

Output:
```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}
