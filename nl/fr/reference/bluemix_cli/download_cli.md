---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Téléchargement et installation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}
{: #download_install}

Vous pouvez utiliser un programme d'installation ou un interpréteur de commandes pour télécharger et installer l'interface de ligne de commande. 

## Utilisation du programme d'installation
{: #installer}

Pour installer l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} :
* Rendez-vous [ici](all_versions.html) pour télécharger le programme d'installation. 
* Pour macOS et Windows, exécutez le programme d'installation.  
* Pour Linux, après avoir téléchargé le package du programme d'installation, procédez à l'extraction de son contenu et exécutez le script d'installation avec les droits root.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Installation depuis l'interpréteur de commandes
{: #shell_install}


### Mac OS

Copiez et collez la commande suivante sur un terminal de votre système d'exploitation Mac et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copiez et collez la commande suivante sur un terminal de votre système d'exploitation Linux et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copiez et collez la commande suivante dans une console de terminal [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} et exécutez-la :

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
