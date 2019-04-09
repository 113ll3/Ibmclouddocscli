---

copyright:

  years: 2015, 2018
lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Estensione della CLI {{site.data.keyword.Bluemix_notm}} con i plug-in
{: #plug-ins}

La CLI {{site.data.keyword.Bluemix_notm}} supporta un framework di plug-in per estenderne la funzionalità. Puoi installare un plug-in da un repository, un URL web o installare un file binario del plug-in localmente.

Il [repository di plug-in della CLI {{site.data.keyword.Bluemix_notm}} ](https://tools.ng.bluemix.net){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg) è il repository ufficiale in cui sono ospitati i plug-in.

Per ulteriori comandi per gestire i plug-in, esegui `ibmcloud plugin` per visualizzare i messaggi della guida.
{: tip}

## Installa un plug-in dal repository CLI {{site.data.keyword.Bluemix_notm}}

### Passo 1: cerca il plug-in

1. Utilizza il comando `ibmcloud plugin repo-plugins -r REPO_NAME` per cercare un plug-in nel repository.
2. La CLI {{site.data.keyword.Bluemix_notm}} ha il repository ufficiale denominato 'IBM Cloud', puoi cercare i plug-in ufficiali come mostrato nel seguente esempio:

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Passo 2: installa il plug-in

Utilizza il comando `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` per installare il plug-in. Ad esempio, utilizza il seguente comando per installare un plug-in dal repository di plug-in ufficiale di IBM 'IBM Cloud':

  ```
  $ ibmcloud plugin install auto-scaling
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 byte scaricati
  Installazione del plug-in '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2' in corso...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Installa un plug-in localmente

Utilizza il comando `ibmcloud plugin install LOCAL_FILE_NAME` per installare un file binario del plug-in sulla macchina locale. Ad esempio:

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Installa un plug-in da un URL web

Utilizza il comando `ibmcloud plugin install URL` per installare un plug-in direttamente da un URL web. Ad esempio

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Tentativo di scaricare il file binario in corso...
  9857792 byte scaricati
  Installazione del plug-in '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2' in corso...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
