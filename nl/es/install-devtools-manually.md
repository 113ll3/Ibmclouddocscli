---

copyright:
  years: 2019
lastupdated: "2019-06-19"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Instalación manual del plugin de CLI de herramientas de desarrollador de {{site.data.keyword.cloud_notm}}
{: #install-devtools-manually}

Puede instalar de forma manual el plugin de la interfaz de línea de mandatos (CLI) de herramientas de desarrollador de
{{site.data.keyword.cloud}} si prefiere un control más preciso en la instalación de los componentes. De lo contrario, se instalarán automáticamente todos los requisitos previos para la mayoría de los usuarios utilizando los [instaladores de la plataforma](/docs/cli?topic=cloud-cli-getting-started#step1-install-idt).
{: shortdesc}

## Antes de empezar
{: cli-before-you-begin}

* Instale la [CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autónoma para obtener soporte para la instalación de plugins de línea de mandatos para {{site.data.keyword.cloud_notm}}.
* Instale el mandato [curl](https://curl.haxx.se/download.html){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") para descargar paquetes a través de la línea de mandatos.

## Instalación del plugin de CLI de herramientas de desarrollador de {{site.data.keyword.cloud_notm}}
{: #install-devtools-idt}

Puede utilizar los mandatos de CLI de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}} para crear una aplicación, así como gestionarla, desplegarla, depurarla y probarla.

Para instalar el plugin de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}}, ejecute el mandato siguiente: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Instalación de Docker
{: #install-devtools-docker}

Para ejecutar y depurar apps de manera local, instale [Docker](https://www.docker.com/get-started){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").

## Instalación de la herramienta de línea de mandatos de Kubernetes
{: #idt-install-kube}

Para ver una versión local del panel de control de Kubernetes y para desplegar apps en los clústeres, instale la
[herramienta de línea de mandatos de Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") para su plataforma:

* Mac:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux&trade;:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows&trade;:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

El prefijo para ejecutar mandatos utilizando la herramienta de línea de mandatos de Kubernetes es
`kubectl`. Para obtener más información, consulte [Configuración de la CLI y la API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Instalación del plugin de CLI de {{site.data.keyword.cos_full_notm}}

El plug-in {{site.data.keyword.cos_full_notm}} amplía la interfaz de línea de mandatos (CLI) de {{site.data.keyword.cloud_notm}} con un derivador de API para trabajar con recursos de Object Storage.

* Para instalar el plugin de {{site.data.keyword.cos_full_notm}}, ejecute el mandato siguiente:
  ```
  ibmcloud plugin install cloud-object-storage
  ```
  {: codeblock}

Para obtener más información, consulte la [referencia de mandatos de {{site.data.keyword.cos_full_notm}}](/docs/cloud-object-storage-cli-plugin?topic=cloud-object-storage-cli-ic-cos-cli).

## Instalación del plugin de CLI de {{site.data.keyword.registrylong_notm}}
{: #idt-install-container-registry-cli-plugin}

Puede utilizar el plugin de la CLI `container-registry` para configurar su propio espacio de nombres de imagen en un registro privado alojado y gestionado por IBM. Allí puede almacenar y compartir imágenes de Docker con todos los usuarios de la cuenta de {{site.data.keyword.cloud_notm}}.

* Para instalar el plugin de {{site.data.keyword.registrylong}}, ejecute el mandato siguiente:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

Para obtener más información, consulte la [referencia de mandatos de {{site.data.keyword.registrylong}}](/docs/services/Registry?topic=container-registry-cli-plugin-containerregcli).

## Instalación del plugin de CLI de {{site.data.keyword.containerlong_notm}}
{: #idt-install-kubernetes-cli-plugin}

Para crear y gestionar clústeres de Kubernetes en {{site.data.keyword.containerlong}}:

* Para instalar el plugin de {{site.data.keyword.registryshort_notm}}, ejecute el mandato siguiente:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Para obtener más información, consulte la
[referencia de mandatos de {{site.data.keyword.registryshort_notm}}](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Instalación de Helm
{: #idt-install-helm}

Instale [Helm](https://helm.sh/docs/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo"), que es un gestor de paquetes basado en Kubernetes.

* Los usuarios de Mac y Linux&trade; deben ejecutar los mandatos siguientes:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Los usuarios de Windows&trade; pueden descargar e instalar el
[binario](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} de Helm
![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").

## Instalación del plugin de CLI de {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Puede utilizar el plugin de CLI de {{site.data.keyword.openwhisk}} para gestionar sus fragmentos de código en acciones, empaquetar acciones en paquetes y crear desencadenantes y reglas para permitir que las acciones puedan responder a sucesos.

Para instalar el plugin de CLI de {{site.data.keyword.openwhisk_short}}, ejecute el mandato siguiente:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Para obtener más información, consulte [Instalación del plugin de CLI de {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cli_install).

