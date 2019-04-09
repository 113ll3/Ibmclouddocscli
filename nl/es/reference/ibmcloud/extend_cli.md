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

# Ampliación de la CLI de {{site.data.keyword.cloud_notm}} con plug-ins
{: #plug-ins}

La CLI de {{site.data.keyword.cloud}} da soporte a una infraestructura de plug-in para ampliar su capacidad. Puede instalar un plug-in desde un repositorio, un URL web, o instalar un binario del plug-in de forma local.

[Repositorio de plugins de CLI de {{site.data.keyword.cloud_notm}}](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg) es el repositorio oficial donde se alojan los plugins.

Para obtener más mandatos para gestionar plug-ins, ejecute `ibmcloud plugin` para ver los mensajes de ayuda.
{: tip}

## Instalar un plugin desde el repositorio de la CLI de {{site.data.keyword.cloud_notm}}
{: #install-from-repo}

### Paso 1: Busque el plugin
{: #step1-search-plugin}

1. Utilice el mandato `ibmcloud plugin repo-plugins -r REPO_NAME` para buscar un plug-in en el repositorio.
2. La CLI de {{site.data.keyword.cloud_notm}} tiene el repositorio oficial con el nombre 'IBM Cloud', puede buscar los plug-ins oficiales como se muestra en el ejemplo siguiente:

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Paso 2: Instale el plugin
{: step2-install-plugin}

Utilice el mandato `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` para instalar el plug-in. Por ejemplo, utilice el mandato siguiente para instalar un plug-in desde el repositorio oficial de plugins de IBM 'IBM Cloud':

  ```
  $ ibmcloud plugin install auto-scaling
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Instale un plug-in de forma local
{: #install-plugin-locally}

Utilice el mandato `ibmcloud plugin install LOCAL_FILE_NAME` para instalar el binario de un plugin en su máquina local. Por ejemplo:

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Instalar un plugin desde un URL de web
{: install-plugin-from-url}

Utilice el mandato `ibmcloud plugin install URL` para instalar un plug-in directamente desde el URL de una web. Por ejemplo:

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
