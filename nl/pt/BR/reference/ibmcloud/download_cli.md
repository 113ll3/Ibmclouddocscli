---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Instalando a CLI  {{site.data.keyword.cloud_notm}}  Independente
{: #install-ibmcloud-cli}

A CLI do {{site.data.keyword.cloud}} fornece a interface da linha de comandos para gerenciar recursos no {{site.data.keyword.cloud_notm}}. Ainda é possível usar a CLI `cf` para efetuar login no {{site.data.keyword.cloud_notm}}, mas ela funciona com um serviço do Cloud Foundry no {{site.data.keyword.cloud_notm}}. 

Se você desejar instalar a CLI mais recente do {{site.data.keyword.cloud}} e outros
plug-ins e ferramentas recomendados para desenvolver aplicativos para o {{site.data.keyword.cloud_notm}}, veja [Introdução
à CLI do {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

## Antes de começar
{: #before-download-cli}

Se for necessário usar uma versão de 32 bits ou uma versão anterior diferente da mais recente para ambientes {{site.data.keyword.cloud_notm}} Dedicados, veja [liberações da CLI do {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").

## Instalando com um instalador
{: #ibmcloud-cli-installer}

Use as etapas a seguir para instalar a CLI do {{site.data.keyword.cloud_notm}} independente mais recente:

1. Selecione o instalador de seu S.O. para fazer download:
  *  macOS X de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * Windows de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * Linux x86 de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * Linux LE de 64 bits (ppc64le): [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")

2. Execute o instalador:
  * Para Mac e Windows&trade;, execute o instalador.
  * Para Linux&trade;, extraia o pacote e execute o script `install`.

3. Efetue login no {{site.data.keyword.cloud_notm}}:
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Agora, você está pronto para gerenciar os recursos do  {{site.data.keyword.cloud_notm}} . Insira `ibmcloud help` para visualizar as descrições do comando.

  Se você estiver usando um ID federado, [efetue login com uma senha descartável ou uma chave de API]((/docs/iam?topic=iam-federated_id#federated_id).
  {: tip}

## Instalando usando o shell
{: #shell_install}

Para instalar a CLI mais recente para seu S.O. usando o shell manualmente, use o comando a seguir para seu S.O.:

* Para **Mac**, copie e cole o comando a seguir em um terminal e execute-o:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* Para **Linux&trade;**, copie e cole o comando a seguir em um terminal e execute-o:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* Para **Windows &trade;**, copie e cole o comando a seguir em um console de terminal do [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") e execute-o:
  ```
  iex (New-Object Net.WebClient). DownloadString ('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Instalando em um diretório customizado
{: #install-custom-dir}

Ao usar os instaladores ou um shell script para instalar a CLI do {{site.data.keyword.cloud_notm}}, ele é instalado em seus diretórios do sistema. Se você desejar especificar um diretório diferente, use as etapas a seguir.

1. Faça download do pacote binário para seu S.O. usando os links a seguir:
  * macOS: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * linux32: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * linux64: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * ppc64le: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * win32: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") /[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")
  * win64: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")

2. Extraia o pacote em um diretório que você especificar.

   É possível ver o conteúdo extraído a seguir:

   Para Linux&trade; e Mac:
   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   UNK -- cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   Para Windows:
   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   UNK -- cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Inclua na variável de ambiente `PATH` e ative a conclusão automática do shell.
  * Inclua o `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` na variável de ambiente `PATH`.
  * Para suporte à conclusão automática de shell (Mac e Linux&trade; somente), consulte [este guia](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Atualizando a CLI do {{site.data.keyword.cloud_notm}}
{: #update-ibmcloud-cli}

Deve-se usar a versão mais recente da CLI. Se você não estiver usando a versão mais recente, execute o comando a seguir para atualizar sua CLI:

```
Atualizar ibmcloud
```
{: codeblock}

Para determinar a versão da CLI do {{site.data.keyword.cloud_notm}}, execute o
comando a seguir:
```
ibmcloud -v
```
{: codeblock}

Se você estiver executando a liberação atual, a saída a seguir será exibida:
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

Para ser notificado sobre novas liberações da CLI do {{site.data.keyword.cloud_notm}},
assine o [repositório de liberações
da CLI do {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "ìcone de link externo").
