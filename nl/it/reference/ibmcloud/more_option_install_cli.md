---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Ulteriori opzioni per installare la CLI {{site.data.keyword.Bluemix_notm}}
{: #more_options_install}

Oltre ai [programmi di installazione](install_use_cli.html#getting_started), puoi avere altre opzioni per installare la CLI {{site.data.keyword.Bluemix_notm}}.

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

Quando utilizzi i programmi di installazione oppure uno script shell per installare la CLI {{site.data.keyword.Bluemix_notm}}, i file binari andranno alle tue directory di sistema. Se vuoi specificare una directory differente, utilizza la seguente procedura.

1. Scarica i binari. 

   Utilizza i seguenti link e scarica il pacchetto binario in base al tuo sistema operativo.

   | Piattaforma | Download | checksum |
   |----|----| --- |
   | macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. Estrai il pacchetto in una directory da te specificata. 

   Dopo l'estrazione del pacchetto, il contenuto si presenterà come qui di seguito indicato:

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

1. Aggiungi alla variabile di ambiente `PATH` e abilita il completamento automatico della shell. 

   * Aggiungi la `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` alla variabile di ambiente `PATH`.
   * Per il supporto del completamento automatico della shell (solo MacOS e Linux), fai riferimento a [questa guida](enable_cli_autocompletion.html).

