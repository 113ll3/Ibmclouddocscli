---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma
{: #install-ibmcloud-cli}

La CLI {{site.data.keyword.cloud}} fornisce l'interfaccia riga di comando per la gestione delle risorse in {{site.data.keyword.cloud_notm}}. Puoi ancora utilizzare la CLI `cf` per accedere a {{site.data.keyword.cloud_notm}} ma funziona con un servizio Cloud Foundry in {{site.data.keyword.cloud_notm}}. 

Se desideri installare la CLI {{site.data.keyword.cloud}} più recente che gli altri plugin e strumenti consigliati per lo sviluppo di applicazioni per {{site.data.keyword.cloud_notm}}, vedi [Introduzione alla CLI {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-getting-started).
{: tip}

## Prima di iniziare
{: #before-download-cli}

Se devi utilizzare una versione a 32 bit o una versione precedente diversa da quella più recente per gli ambienti dedicati {{site.data.keyword.cloud_notm}}, vedi le [release della CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## Installazione tramite un programma di installazione
{: #ibmcloud-cli-installer}

Utilizza la seguente procedura per installare la CLI {{site.data.keyword.cloud_notm}} autonoma più recente:

1. Utilizza un browser per accedere al repository GitHub [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) ufficiale e **seleziona** il programma di installazione del tuo sistema operativo per avviare il download. Sono supportati i seguenti sistemi operativi: macOS X 64-bit, Windows&trade; 64-bit, Linux&trade; x86 64-bit e Linux&trade; LE 64-bit (ppc64le).

2. Esegui il programma di installazione:
  * Per Mac e Windows&trade;, esegui il programma di installazione.
  * Per Linux&trade;, estrai il pacchetto ed esegui lo script `install`.

3. Accedi a {{site.data.keyword.cloud_notm}}:
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Ora sei pronto a gestire le risorse {{site.data.keyword.cloud_notm}}. Immetti `ibmcloud help` per visualizzare le descrizioni dei comandi.

  Se stai utilizzando un ID federato, [accedi con un passcode monouso o una chiave API](/docs/iam?topic=iam-federated_id).
  {: tip}

## Installazione dalla shell
{: #shell_install}

Per installare l'ultima CLI per il tuo SO dalla shell manualmente, utilizza il seguente comando per il tuo SO:

* Per **Mac**, copia e incolla il seguente comando in un terminale ed eseguilo:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* Per **Linux&trade;**, copia e incolla il seguente comando in un terminale ed eseguilo:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* Per **Windows&trade;**, copia e incolla il seguente comando nella console del terminale [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno") ed eseguilo:
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Installazione in una directory personalizzata
{: #install-custom-dir}

Quando utilizzi i programmi di installazione o uno script di shell per installare la CLI {{site.data.keyword.cloud_notm}}, vengono installati nelle tue directory di sistema. Se vuoi specificare una directory differente, utilizza la seguente procedura.

1. Utilizza un browser per accedere al repository GitHub [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) ufficiale e **seleziona** il file binario corrispondente della tua piattaforma per avviare il download. Sono supportate le seguenti piattaforme: macOS, linux32, linux64, ppc64le, win32 e win64.

2. Estrai il pacchetto in una directory da te specificata.

   Puoi visualizzare il seguente contenuto estratto:

   Per Linux&trade; e Mac:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   Per Windows&trade;:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Aggiungi alla variabile di ambiente `PATH` e abilita il completamento automatico della shell.
  * Aggiungi la `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` alla variabile di ambiente `PATH`.
  * Per il supporto del completamento automatico della shell (solo Mac e Linux&trade;), vedi [Abilitazione del completamento automatico della shell per la CLI IBM Cloud](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Aggiornamento della CLI {{site.data.keyword.cloud_notm}}
{: #update-ibmcloud-cli}

Devi utilizzare l'ultima versione della CLI. Se non utilizzi l'ultima versione, immetti il seguente comando per aggiornare la tua CLI:

```
ibmcloud update
```
{: codeblock}

Per determinare la tua versione della CLI {{site.data.keyword.cloud_notm}}, immetti il seguente comando:
```
ibmcloud -v
```
{: codeblock}

Se stai eseguendo la release corrente, viene visualizzato il seguente output:
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

Per venire informato sulle nuove release della CLI {{site.data.keyword.cloud_notm}}, esegui la sottoscrizione al [repository delle release della CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").
