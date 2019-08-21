---

copyright:
  years: 2019
lastupdated: "2019-08-05"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Disinstallazione della CLI {{site.data.keyword.cloud_notm}} autonoma
{: #uninstall-ibmcloud-cli}

Utilizza la seguente procedura per disinstallare la CLI {{site.data.keyword.cloud_notm}} autonoma su piattaforme specifiche:
{: shortdesc}

## Disinstallazione su Windows
{: #uninstall-cli-windows}

1. Fai clic sul pulsante **Avvia** e seleziona **Pannello di controllo**.
2. Nella finestra a comparsa, fai clic su **Disinstalla un programma**.
3. Nell'elenco delle applicazioni a comparsa, individua **IBM Cloud Command Line Interface**.
4. Fai clic con il tasto destro su **IBM Cloud Command Line Interface** e seleziona **Disinstalla**.
5. Il programma di disinstallazione viene avviato. Segui le istruzioni per completare la disinstallazione.

## Disinstallazione su Linux e macOS
{: #uninstall-cli-linux-macos}

Le istruzioni per la disinstallazione sono diverse a seconda della versione della CLI installata.

Per determinare la tua versione della CLI {{site.data.keyword.cloud_notm}}, immetti:
```
ibmcloud -v
```
{: codeblock}

Per disinstallare le versioni precedenti alla `0.9.0`, immetti i seguenti comandi:
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Elimina gli script di completamento automatico, se li hai configurati. Per ulteriori dettagli, vedi [Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.cloud_notm}} (solo Linux e Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

Per disinstallare le versioni `0.9.0` e successive, immetti il seguente comando:
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Elimina gli eventuali script di completamento automatico personalizzati. Per ulteriori dettagli, vedi [Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.cloud_notm}} (solo Linux e Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
