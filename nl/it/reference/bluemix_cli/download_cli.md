---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Scarica e installa la CLI {{site.data.keyword.Bluemix_notm}}
{: #download_install}

Puoi utilizzare il programma di installazione o la shell per scaricare e installare la CLI.

## Utilizza il programma di installazione
{: #installer}

Per installare la CLI {{site.data.keyword.Bluemix_notm}}:
* Vai [qui](all_versions.html) per scaricare il programma di installazione.
* Per macOS e Windows, esegui il programma di installazione.  
* Per Linux, dopo che hai scaricato il pacchetto del programma di installazione, eseguine l'estrazione ed esegui lo script di installazione con l'autorizzazione root.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Installa dalla shell 
{: #shell_install}


### macOS

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
