---



copyright:

  years: 2015, 2017
lastupdated: "2017-010-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Scarica e installa la CLI {{site.data.keyword.Bluemix_notm}}
{: #download_install}

Per installare la CLI {{site.data.keyword.Bluemix_notm}} puoi utilizzare un [programma di installazione](#installers) o puoi [eseguire l'installazione dalla shell](#shell_install).

## Scarica i programmi di installazione
{: #installers}

Vedi la pagina [Programma di installazione della CLI {{site.data.keyword.Bluemix_notm}} (tutte le versioni)](all_versions.html){: new_window} per scaricare il programma di installazione più recente del tuo sistema operativo.

Per macOS e Windows, esegui semplicemente il programma di installazione. 

Per Linux, dopo che hai scaricato il pacchetto del programma di installazione, eseguine l'estrazione ed esegui lo script di installazione con l'autorizzazione root.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```
  
## Installa dalla shell
{: #shell_install}


### macOS

Copia e incolla il seguente comando in un terminale del tuo macOS ed eseguilo:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copia e incolla il seguente comando in un terminale del tuo sistema operativo Linux ed eseguilo:

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
