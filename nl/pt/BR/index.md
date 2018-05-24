---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} Visão geral
{: #overview}

{{site.data.keyword.dev_cli_notm}} é uma abordagem de linha de comandos para criação, desenvolvimento e implementação de aplicativos para desenvolvedores que desejam usar uma linha de comandos para desenvolver aplicativos da web, de dispositivos móveis e de microsserviço de ponta a ponta. Comece a usar rapidamente o conjunto de ferramentas recomendado executando um dos scripts a seguir.
{: shortdesc} 

## Pré-requisitos para o {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Inscreva-se para o [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* Se você está usando o Microsoft Windows&trade;, deve-se usar o Windows 10 ou mais recente.

* Use o canal estável para Docker, com uma versão mínima de 1.13.1.

## Como instalar o {{site.data.keyword.dev_cli_notm}}
{: #installation}

Para instalar o conjunto de ferramentas, é possível executar o comando relevante para iniciar o instalador. Isso instala as ferramentas recomendadas a seguir para desenvolvimento do {{site.data.keyword.Bluemix_notm}} (caso ainda não estejam instaladas): `Homebrew` (Mac somente), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, CLI do {{site.data.keyword.Bluemix_notm}}, plug-in {{site.data.keyword.dev_cli_notm}}, plug-in Cloud Functions, plug-in Container Registry, plug-in Container Service e plug-in `sdk-gen`.

**Mac e Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: abra o Windows PowerShell clicando com o botão direito e selecionando "Executar como
administrador".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## Outros links para explorar ainda mais o {{site.data.keyword.dev_cli_notm}}

- [Configuração detalhada](/docs/cli/idt/setting_up_idt.html)
- [Uso ](/docs/cli/idt/index.html)
- [Comandos](/docs/cli/idt/commands.html)
- [Plug-ins da CLI](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [Extensão IDE de VSCode](/docs/cli/idt/vscode.html)
- [Instalar a CLI do IBM Cloud manualmente](/docs/cli/reference/bluemix_cli/get_started.html)
