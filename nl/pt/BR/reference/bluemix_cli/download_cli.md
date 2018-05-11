---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Fazer download e instalar a CLI do {{site.data.keyword.Bluemix_notm}}
{: #download_install}

É possível usar um instalador ou shell para fazer download e instalar a CLI.

## Usar o instalador
{: #installer}

Para instalar a CLI do {{site.data.keyword.Bluemix_notm}}:
* Acesse [aqui](all_versions.html) para fazer download do instalador.
* Para macOS e Windows, execute o instalador. 
* Para Linux, após o download do pacote do instalador, extraia-o e execute o script de instalação com permissão raiz.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Instalar por meio do shell
{: #shell_install}


### macOS

Copie e cole o comando a seguir em um terminal de seu Mac OS e execute-o:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copie e cole o comando a seguir em um terminal de seu S.O. Linux e execute-o:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copie e cole o comando a seguir em um console de terminal
[Windows
PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} e execute-o:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
