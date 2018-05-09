---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Descargue e instale la CLI de {{site.data.keyword.Bluemix_notm}}
{: #download_install}

Puede utilizar un instalador o shell para descargar e instalar la CLI.

## Utilice el instalador
{: #installer}

Para instalar la CLI de {{site.data.keyword.Bluemix_notm}}:
* Diríjase [aquí](all_versions.html) para descargar el instalador.
* Para macOS y Windows, ejecute el instalador. 
* Para Linux, tras descargar el paquete instalador, extráigalo y ejecute el script de instalación con permiso de root.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Instalar desde el shell
{: #shell_install}


### macOS

Copie y pegue el mandato siguiente a un terminal de su SO Mac y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copie y pegue el mandato siguiente a un terminal de su SO Linux y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copie y pegue el mandato siguiente a una consola de terminal de [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} y ejecútelo:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
