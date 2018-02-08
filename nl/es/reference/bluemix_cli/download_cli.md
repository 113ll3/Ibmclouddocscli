---



copyright:

  years: 2015, 2018
lastupdated: "2017-010-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Descargue e instale la CLI de {{site.data.keyword.Bluemix_notm}}
{: #download_install}

Puede utilizar un [instalador](#installers) o [instalar desde shell](#shell_install) para instalar la CLI de {{site.data.keyword.Bluemix_notm}}.

## Descargar instaladores
{: #installers}

Consulte la página [Instalador de la CLI de {{site.data.keyword.Bluemix_notm}} (todas las versiones)](all_versions.html){: new_window} para descargar el último instalador para su SO.

Para macOS y Windows, simplemente ejecute el instalador. 

Para Linux, tras descargar el paquete instalador, extráigalo y ejecute el script de instalación con permiso de root.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```
  
## Instalar desde shell
{: #shell_install}


### macOS

Copie y pegue el mandato siguiente a un terminal de su SO mac y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copie y pegue el mandato siguiente a un terminal de su sistema operativo Linux y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copie y pegue el mandato siguiente en una consola de terminal de [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} y ejecútelo:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
