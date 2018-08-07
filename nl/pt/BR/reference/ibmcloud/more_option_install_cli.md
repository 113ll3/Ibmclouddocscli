---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Mais opções para instalar a CLI do {{site.data.keyword.Bluemix_notm}}
{: #more_options_install}

Além de [instaladores](install_use_cli.html#getting_started), é possível ter outras opções para instalar a CLI do {{site.data.keyword.Bluemix_notm}}:

* Instalar por meio do shell
* Fazer download do pacote binário e instalar em um diretório customizado

## Instalar por meio do shell
{: #shell_install}

### MacOS

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

## Instalar em um diretório customizado

Ao usar os instaladores ou um shell script para instalar a CLI do {{site.data.keyword.Bluemix_notm}}, os binários irão para seus diretórios do sistema. Se você desejar especificar um diretório diferente, use as etapas a seguir.

1. Faça download dos binários.

   Use os links a seguir e faça download do pacote binário com base em seu S.O.

   | Plataforma | Downloads | soma de verificação |
   |----|----| --- |
   | macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. Extraia o pacote em um diretório que você especificar.

   Após extrair o pacote, o conteúdo será semelhante ao seguinte:

   Para Linux e MacOS

   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   UNK -- autocomplete
   | UNK -- bash_autocomplete
   | UNK -- zsh_autocomplete
   UNK -- cfcli
   | UNK -- cf
   UNK -- ibmcloud
   UNK -- ibmcloud-analytics
   ```
   {: codeblock}

   Para Windows

   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   UNK -- cfcli
   | UNK -- cf.exe
   UNK -- ibmcloud-analytics.exe
   UNK -- ibmcloud.exe
   ```
   {: codeblock}

1. Inclua na variável de ambiente `PATH` e ative a conclusão automática do shell.

   * Inclua o `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` na variável de ambiente `PATH`.
   * Para suporte à conclusão automática do shell (somente MacOS e Linux), consulte [este guia](enable_cli_autocompletion.html).

