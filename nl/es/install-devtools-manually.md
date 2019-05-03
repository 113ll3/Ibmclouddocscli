---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Instalación manual de componentes de plugin de CLI de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}}
{: #install-devtools-manually}

Si prefiere un control más preciso para instalar componentes de las herramientas de desarrollador, puede instalarlos de forma manual utilizando los pasos siguientes. De lo contrario, se instalarán automáticamente todos los requisitos previos para la mayoría de los usuarios utilizando los [instaladores de la plataforma](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Antes de empezar
{: cli-before-you-begin}

* Instale la [CLI de {{site.data.keyword.cloud}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autónoma para poder dar soporte a la instalación de plugins de línea de mandatos para `ibmcloud`.
* Instale el mandato [curl](https://curl.haxx.se/download.html){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") para descargar paquetes a través de la línea de mandatos.

## Paso 1. Instalación del plugin de CLI de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}}
{: #install-devtools-idt}

Puede utilizar los mandatos de CLI de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}} (ibmcloud dev) para crear una aplicación, así como gestionarla, desplegarla, depurarla y probarla.

Instale el plugin `dev` ejecutando el mandato siguiente: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Paso 2. Instalación de Docker
{: #install-devtools-docker}

Para ejecutar y depurar apps de manera local, instale [Docker](https://www.docker.com/get-docker){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").

## Paso 3. Instalación de Kubernetes:
{: #idt-install-kube}

Kubernetes es un motor de orquestación de contenedores de código abierto para la automatización del despliegue, escalado y gestión de aplicaciones contenerizadas.

Para dar soporte a los despliegues contenerizados, instale Kubernetes para su plataforma:

* MacOS:
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

## Paso 4. Instalación de los plugins de CLI de Kubernetes
{: #idt-install-kubernetes-cli-plugins}

Para gestionar despliegues de Kubernetes desde la línea de mandatos, instale los plugins de contenedor siguientes:

* Instale el plugin `container-registry`:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* Instale el plugin `container-service`:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Para obtener más información, consulte [Configuración de la CLI y la API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Paso 5. Instalación de Helm:
{: #idt-install-helm}

Instale [Helm](https://helm.sh/docs/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo"), que es un gestor de paquetes basado en Kubernetes.

* Los usuarios de MacOS y Linux&trade; deben ejecutar los mandatos siguientes:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Los usuarios de Windows&trade; pueden descargar e instalar el
[binario](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} de Helm
![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").

## Paso 6. Instalación del plugin de CLI de {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Puede utilizar el plugin de CLI de {{site.data.keyword.openwhisk}} para gestionar sus fragmentos de código en acciones, crear desencadenantes y reglas para permitir que sus acciones puedan responder a sucesos, y agrupar acciones en paquetes.

Para instalar el plugin de CLI de {{site.data.keyword.openwhisk_short}}, ejecute el mandato siguiente:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Para obtener más información, consulte [Configuración del plugin de CLI de {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Paso 7. Instalación del plugin de CLI de SDK Generator
{: #idt-install-sdk-gen}

Como desarrollador en {{site.data.keyword.cloud_notm}}, puede utilizar este plug-in para generar SDK desde su definición de la API REST compatible con la [Especificación de Open API](https://www.openapis.org/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo"). A medida que realiza cambios en la definición de API REST, podrá utilizar este plugin para volver a generar sólo el SDK, en lugar de volver a generar todo el proyecto.

Instale el plugin de CLI de SDK Generator:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

Para obtener más información, consulte [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
