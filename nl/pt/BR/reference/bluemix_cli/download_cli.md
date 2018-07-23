---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-09"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Instalando a CLI  {{site.data.keyword.Bluemix_notm}}  Independente
{: #install_use}

O {{site.data.keyword.Bluemix_notm}} CLI fornece a interface da linha de comandos para gerenciar aplicativos, contêineres, infraestruturas, serviços e outros recursos no {{site.data.keyword.Bluemix_notm}}.

Se você desejar instalar a CLI do {{site.data.keyword.Bluemix}} e outros plug-ins e ferramentas recomendadas para
desenvolver aplicativos para o {{site.data.keyword.Bluemix_notm}}, siga o método descrito
[aqui](/docs/cli/index.html).
{: tip}

Use as etapas a seguir para instalar a CLI do {{site.data.keyword.Bluemix_notm}} independente:

1. Selecione o instalador do OS para download

   Mac OS X de 64 bits:
[instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} /
[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows de 64 bits:
[instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} /
[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 de 64 bits:
[instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window}
/ [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le): [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **As liberações de 32 bits e versões anteriores podem ser localizadas [aqui](all_versions.html)

1. Execute o instalador
   * Para Mac OS e Windows, apenas execute o instalador.
   * Para Linux, extraia o pacote e execute o script `install_bluemix_cli`

1. Destinar um terminal de API e login para o {{site.data.keyword.Bluemix_notm}}

  ![Exemplo](example.gif){: gif}

Agora você está pronto para gerenciar recursos do {{site.data.keyword.Bluemix_notm}}. Digite `ibmcloud help` para ver as descrições dos comandos.

Se você estiver usando um ID federado, siga as instruções
[aqui](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) para efetuar login com uma senha única
ou uma chave API.  
{: tip}

## Mais opções para instalar a CLI do {{site.data.keyword.Bluemix_notm}}
{: #more_options_install}


Além do [instalador](install_use_cli.html#getting_started), também é possível usar shell para fazer download e instalar a CLI. 


### Instalar por meio do shell
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

## Outros links para explorar ainda mais a CLI do {{site.data.keyword.Bluemix_notm}}

* [Ampliar os recursos da CLI do {{site.data.keyword.Bluemix_notm}} com plug-ins](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [Uso de comandos gerais da CLI do {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [Uso de comandos gerais do {{site.data.keyword.Bluemix_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html)


## Relatar problemas e enviar feedback
{: #issues}

Use as opções a seguir para relatar problemas ou enviar novas solicitações de recursos:
 * Criar problemas no [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg)
 * Deixe mensagens no [canal Slack](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg)
