---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

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
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                   Versions                       Description
Update Available   container-service/kubernetes-service   0.2.99, 0.2.95, 0.2.80...      IBM Cloud Kubernetes Service for management of Kubernetes clusters
Update Available   cloud-functions                        1.0.30, 1.0.29, 1.0.28...      IBM Cloud CLI plug-in for IBM Cloud Functions
...
```
{: screen}

### Paso 2: Instale el plugin
{: step2-install-plugin}

Utilice el mandato `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` para instalar el plug-in. Por ejemplo, utilice el mandato siguiente para instalar un plug-in desde el repositorio oficial de plugins de IBM 'IBM Cloud':

```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
Looking up 'auto-scaling' from repository 'IBM Cloud'...
Plug-in 'auto-scaling 0.2.7' found in repository 'IBM Cloud'
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
```
{: screen}

## Instale un plug-in de forma local
{: #install-plugin-locally}

Utilice el mandato `ibmcloud plugin install LOCAL_FILE_NAME` para instalar el binario de un plugin en su máquina local. Por ejemplo:

```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}

## Instalar un plugin desde un URL de web
{: install-plugin-from-url}

Utilice el mandato `ibmcloud plugin install URL` para instalar un plug-in directamente desde el URL de una web. Por ejemplo:
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

Salida:
```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}
