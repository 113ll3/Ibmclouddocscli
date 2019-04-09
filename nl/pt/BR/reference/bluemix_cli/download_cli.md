---



copyright:

  years: 2015, 2018
lastupdated: "2018-02-14"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Fazer download e instalar a CLI do {{site.data.keyword.Bluemix_notm}}
{: #download_install}

É possível usar um [instalador](#installers) ou [instalar no shell](#shell_install) para instalar o {{site.data.keyword.Bluemix_notm}} CLI.

## Fazer download dos instaladores
{: #installers}

Veja a página [Instalador do {{site.data.keyword.Bluemix_notm}} CLI (todas as versões)](all_versions.html){: new_window} para fazer download do instalador mais recente do seu S.O.

Para Mac OS e Windows, apenas execute o instalador. 

Para Linux, após o download do pacote do instalador, extraia-o e execute o script de instalação com permissão raiz.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```
  {: codeblock}
  
## Instalar por meio do shell
{: #shell_install}


### macOS

Copie e cole o comando a seguir em um terminal de seu Mac OS e execute-o:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copie e cole o comando a seguir em um terminal do S.O. Linux e execute-o:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copie e cole o comando a seguir em um console de terminal do [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} e execute-o:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
