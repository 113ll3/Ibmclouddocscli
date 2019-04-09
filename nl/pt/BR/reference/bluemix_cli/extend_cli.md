---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Ampliando a CLI do {{site.data.keyword.Bluemix_notm}} com plug-ins
{: #plug-ins}

A CLI do {{site.data.keyword.Bluemix_notm}} suporta uma estrutura de plug-in para ampliar sua capacidade. É possível instalar um plug-in de um repositório, uma URL da web ou instalar um binário de plug-in localmente. 

[Repositório de plug-ins do {{site.data.keyword.Bluemix_notm}} CLI](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg) é o repositório oficial no qual os plug-ins estão hospedados.

Para obter mais comandos para gerenciar plug-ins, execute `bluemix plugin` para ver as mensagens de ajuda.
{: tip}

## Instalar um plug-in do repositório da CLI do {{site.data.keyword.Bluemix_notm}}

### Etapa 1: procurar o plug-in

1. Use o comando `bluemix plugin repo-plugins -r REPO_NAME` para procurar um plug-in no repositório.
2. O {{site.data.keyword.Bluemix_notm}} CLI usa o nome `Bluemix` por padrão. É possível listar os plug-ins no repositório oficial do `Bluemix`. Por exemplo:
  
  ```
  $ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Etapa 2: instalar o plug-in

Use o comando `bx plugin install PLUGIN_NAME -r REPO_NAME` para instalar o plug-in. Por exemplo:

  ```
  $ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Instalar um plug-in localmente

Use o comando `bluemix plugin install LOCAL_FILE_NAME` para instalar um binário de plug-in em sua máquina local. Por exemplo:

  ```
  $ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Instalar um plug-in por meio de uma URL da web

Use o comando `bluemix plugin install URL` para instalar um plug-in diretamente de uma URL da web. Por exemplo

  ```
  ~$ bluemix plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
