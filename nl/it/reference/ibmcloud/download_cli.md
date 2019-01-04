---



copyright:

  years: 2015, 2018
lastupdated: "2018-11-15"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Installazione della CLI {{site.data.keyword.Bluemix_notm}} autonoma
{: #install_use}

La CLI {{site.data.keyword.Bluemix_notm}} fornisce l'interfaccia riga di comando per la gestione delle risorse in {{site.data.keyword.Bluemix_notm}}. Puoi ancora utilizzare la CLI `cf` per accedere a {{site.data.keyword.Bluemix_notm}}, ma funziona solo con un servizio Cloud Foundry in {{site.data.keyword.Bluemix_notm}}. 

Se vuoi installare la CLI {{site.data.keyword.Bluemix}} e altri plug-in e strumenti consigliati per sviluppare le applicazioni per {{site.data.keyword.Bluemix_notm}}, segui il metodo descritto [qui](/docs/cli/index.html).
{: tip}

Utilizza la seguente procedura per installare la CLI {{site.data.keyword.Bluemix_notm}} autonoma:

1. Seleziona il programma di installazione del tuo sistema operativo per il download

   Mac OS X a 64 bit: [programma di installazione](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows a 64 bit: [programma di installazione](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 a 64 bit: [programma di installazione](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE a 64 bit (ppc64le): [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Per le versioni a 32 bit o precedenti, passa alla pagina [tutte le versioni](/docs/cli/reference/ibmcloud/all_versions.html) per lo scaricamento

1. Esegui il programma di installazione
   * Per macOS e Windows, esegui il programma di installazione.
   * Per Linux, estrai il pacchetto ed esegui lo script `install`.

1. Specifica un endpoint API e accedi a {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Ora sei pronto a gestire le risorse {{site.data.keyword.Bluemix_notm}}. Immetti `ibmcloud help` per visualizzare le descrizioni dei comandi.

Se stai utilizzando un ID federato, segui le istruzioni riportate [qui](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) per accedere con un passcode monouso o una chiave API.  
{: tip}

Oltre ai programmi di installazione, puoi avere altre opzioni per installare la CLI {{site.data.keyword.Bluemix_notm}}:

* Installa dalla shell
* Scarica il pacchetto binario ed esegui l'installazione in una directory personalizzata.

## Installa dalla shell
{: #shell_install}

### MacOS

Copia e incolla il seguente comando in un terminale del tuo SO Mac ed eseguilo:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copia e incolla il seguente comando in un terminale del tuo SO Linux ed eseguilo:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copia e incolla il seguente comando in una console del terminale [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ed eseguilo:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Esegui l'installazione in una directory personalizzata

Quando utilizzi i programmi di installazione o uno script di shell per installare la CLI {{site.data.keyword.Bluemix_notm}}, i file binari vanno alle directory di sistema. Se vuoi specificare una directory differente, utilizza la seguente procedura.

### Passo 1: scarica il pacchetto binario in base al tuo sistema operativo utilizzando i seguenti link:

| Piattaforma | Download | Checksum |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### Passo 2: estrai il pacchetto in una directory da te specificata.

   Dopo aver estratto il pacchetto, il contenuto sarà simile al seguente esempio:

   Per Linux e MacOS

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

   * Aggiungi la `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` alla variabile di ambiente `PATH`.
   * Per il supporto del completamento automatico della shell (solo MacOS e Linux), consulta [Abilita completamento automatico della CLI](enable_cli_autocompletion.html).
   
## Disinstallazione della CLI {{site.data.keyword.Bluemix_notm}} autonoma

Le seguenti sezioni forniscono i dettagli su come disinstallare la CLI {{site.data.keyword.Bluemix_notm}} autonoma su piattaforme specifiche.

### Disinstallazione su Windows

1. Fai clic sul pulsante `Avvia` e seleziona `Pannello di controllo`.
2. Nella finestra a comparsa, fai clic su `Disinstalla un programma`.
3. Nell'elenco delle applicazioni a comparsa, individua `IBM Cloud Command Line Interface`.
4. Fai clic con il tasto destro su `IBM Cloud Command Line Interface` e seleziona `Disinstalla`.
5. Il programma di disinstallazione viene avviato. Segui le istruzioni per completare la disinstallazione.

### Disinstallazione su Linux/macOS

#### Prima della versione `0.9.0`

1. Apri un terminale ed esegui i seguenti comandi:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. Elimina gli script di completamento automatico, se li hai configurati. Per ulteriori informazioni, vedi [Abilita completamento automatico della CLI](enable_cli_autocompletion.html).

#### Versione `0.9.0` e successive

1. Apri un terminale ed esegui il seguente comando:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Elimina gli script di completamento automatico, se li hai configurati. Per ulteriori informazioni, vedi [Abilita completamento automatico della CLI](enable_cli_autocompletion.html).


## Altri link per esplorare ulteriormente la CLI {{site.data.keyword.Bluemix_notm}}

* [Amplia le funzionalità della CLI {{site.data.keyword.Bluemix_notm}} con i plug-in](/docs/cli/reference/ibmcloud/extend_cli.html)
* [Guida di riferimento alla CLI {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud/bx_cli.html)

## Segnala problemi e inoltra un feedback
{: #issues}

Utilizza le seguenti opzioni per segnalare problemi o inoltrare richieste di nuove funzioni:
 * Crea i problemi in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg).
 * Lascia i messaggi in [Slack di IBM Cloud Tech - Canale #developer-tools](https://ibm-cloud-tech.slack.com) - Richiedi l'accesso del team [qui](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg).
