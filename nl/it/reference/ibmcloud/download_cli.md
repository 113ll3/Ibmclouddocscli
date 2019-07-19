---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma
{: #install-ibmcloud-cli}

La CLI {{site.data.keyword.cloud}} fornisce l'interfaccia della riga di comando per la gestione delle risorse in {{site.data.keyword.cloud_notm}}. Puoi ancora utilizzare la CLI `cf` per accedere a {{site.data.keyword.cloud_notm}} ma funziona con un servizio Cloud Foundry in {{site.data.keyword.cloud_notm}}. 

Se desideri installare sia la CLI {{site.data.keyword.cloud}} sia altri plugin e strumenti consigliati per lo sviluppo di applicazioni per {{site.data.keyword.cloud_notm}}, vedi [Introduzione alla CLI {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Utilizza la seguente procedura per installare la CLI {{site.data.keyword.cloud_notm}} autonoma:

1. Seleziona il programma di installazione del tuo sistema operativo da scaricare.

   Mac OS X a 64 bit: [programma di installazione](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows a 64 bit: [programma di installazione](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 a 64 bit: [programma di installazione](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE a 64 bit (ppc64le): [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Per le versioni a 32 bit e precedenti, vai alla pagina delle [release della CLI {{site.data.keyword.cloud_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) per il download.

2. Esegui il programma di installazione
   * Per MacOS e Windows&trade;, esegui il programma di installazione.
   * Per Linux&trade;, estrai il pacchetto ed esegui lo script `install`

3. Indica come destinazione un endpoint API ed esegui l'accesso a {{site.data.keyword.cloud_notm}}:
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Ora sei pronto a gestire le risorse {{site.data.keyword.cloud_notm}}. Immetti `ibmcloud help` per visualizzare le descrizioni dei comandi.

Se stai utilizzando un ID federato, segui le istruzioni riportate [qui](/docs/iam?topic=iam-federated_id#federated_id) per accedere con un passcode monouso o una chiave API.  
{: tip}

Oltre ai programmi di installazione, puoi avere altre opzioni per installare la CLI {{site.data.keyword.cloud_notm}}.

* Installa dalla shell
* Scarica il pacchetto binario ed esegui l'installazione in una directory personalizzata.

## Installa dalla shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Copia e incolla il seguente comando in un terminale del tuo SO Mac ed eseguilo:
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Copia e incolla il seguente comando in un terminale del tuo SO Linux&trade; ed eseguilo:
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Copia e incolla il seguente comando in una console del terminale [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno") ed eseguilo:
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Esegui l'installazione in una directory personalizzata
{: #install-custom-dir}

Quando utilizzi i programmi di installazione o uno script di shell per installare la CLI {{site.data.keyword.Bluemix_notm}}, i file binari vanno alle directory di sistema. Se vuoi specificare una directory differente, utilizza la seguente procedura.

### Passo 1: scarica il pacchetto binario in base al tuo sistema operativo utilizzando i seguenti link:
{: #step1-custom-dir}

| Piattaforma | Download | Checksum |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Passo 2: estrai il pacchetto in una directory da te specificata.
{: #step2-custom-dir}

   Dopo l'estrazione del pacchetto, puoi vedere il seguente contenuto:

   Per Linux&trade; e macOS:

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
   {: codeblock}

   Per Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Passo 3: aggiungi alla variabile di ambiente `PATH` e abilita il completamento automatico della shell.
{: #step3-custom-dir}

   * Aggiungi la `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` alla variabile di ambiente `PATH`.
   * Per il supporto del completamento automatico della shell (solo MacOS e Linux&trade;), fai riferimento a [questa guida](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Disinstallazione della CLI {{site.data.keyword.cloud_notm}} autonoma
{: #uninstall-ibmcloud-cli}

Le seguenti sezioni forniscono i dettagli su come disinstallare la CLI {{site.data.keyword.cloud_notm}} autonoma su piattaforme specifiche.

### Disinstallazione su Windows
{: #uninstall-cli-windows}

1. Fai clic sul pulsante `Avvia` e seleziona `Pannello di controllo`.
2. Nella finestra a comparsa, fai clic su `Disinstalla un programma`.
3. Nell'elenco delle applicazioni a comparsa, individua `IBM Cloud Command Line Interface`.
4. Fai clic con il tasto destro su `IBM Cloud Command Line Interface` e seleziona `Disinstalla`.
5. Il programma di disinstallazione viene avviato. Segui le istruzioni per completare la disinstallazione.

### Disinstallazione su Linux e macOS
{: #uninstall-cli-linux-macos}

#### Versioni antecedenti alla `0.9.0`

1. Apri un terminale ed esegui i seguenti comandi:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Elimina gli script di completamento automatico, se li hai configurati. Per ulteriori dettagli, vedi [Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.cloud_notm}} (solo Linux e macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Versione `0.9.0` e successive

1. Apri un terminale ed esegui il seguente comando:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Elimina gli eventuali script di completamento automatico personalizzati. Per ulteriori dettagli, vedi [Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.cloud_notm}} (solo Linux e macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Altri link per esplorare ulteriormente la CLI {{site.data.keyword.cloud_notm}}
{: #other-cli-links}

* [Estendi la CLI {{site.data.keyword.cloud_notm}} con i plug-in](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [Comandi generali della CLI (ibmcloud)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Segnala problemi e inoltra un feedback
{: #issues}

Utilizza le seguenti opzioni per segnalare problemi o inoltrare richieste di nuove funzioni:
* Crea i problemi in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").
* Lascia i messaggi in [Slack di {{site.data.keyword.cloud_notm}} Tech - Canale #developer-tools](https://ibm-cloud-tech.slack.com){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno") - Richiedi l'accesso del team [qui](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").
