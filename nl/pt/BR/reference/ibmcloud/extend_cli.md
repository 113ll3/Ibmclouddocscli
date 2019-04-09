---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Ampliando a CLI do {{site.data.keyword.cloud_notm}} com plug-ins
{: #plug-ins}

A CLI do {{site.data.keyword.cloud}} suporta uma estrutura de plug-in para ampliar sua capacidade. É possível instalar um plug-in de um repositório, uma URL da web ou instalar um binário de plug-in localmente.

[Repositório de plug-ins da CLI do {{site.data.keyword.cloud_notm}} ](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg) é o repositório oficial no qual os plug-ins são hospedados.

Para obter mais comandos para gerenciar plug-ins, execute `ibmcloud plugin` para ver as mensagens de ajuda.
{: tip}

## Instalar um plug-in do repositório da CLI do {{site.data.keyword.cloud_notm}}
{: #install-from-repo}

### Etapa 1: procurar o plug-in
{: #step1-search-plugin}

1. Use o comando `ibmcloud plugin repo-plugins -r REPO_NAME` para procurar um plug-in no repositório.
2. A CLI do {{site.data.keyword.cloud_notm}} tem o repositório oficial com o nome 'IBM Cloud'. É possível procurar os plug-ins oficiais conforme mostrado no exemplo a seguir:

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Etapa 2: instalar o plug-in
{: step2-install-plugin}

Use o comando `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` para instalar o plug-in. Por exemplo, use o seguinte comando para instalar um plug-in do repositório de plug-in oficial da IBM 'IBM Cloud':

  ```
  $ ibmcloud plugin install auto-scaling 
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Instalar um plug-in localmente
{: #install-plugin-locally}

Use o comando `ibmcloud plugin install LOCAL_FILE_NAME` para instalar um binário de plug-in em sua máquina local. Por exemplo:

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Instalar um plug-in por meio de uma URL da web
{: install-plugin-from-url}

Use o comando `ibmcloud plugin install URL` para instalar um plug-in diretamente de uma URL da web. Por exemplo:

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
