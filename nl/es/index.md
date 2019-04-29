---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-10"

keywords: cli, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# Iniciación a la CLI de {{site.data.keyword.cloud_notm}}
{: #ibmcloud-cli}

En esta guía de aprendizaje, instalará un conjunto de herramientas de desarrollador de {{site.data.keyword.cloud}}, verificará la instalación y configurará el entorno. Las herramientas de desarrollador de {{site.data.keyword.cloud_notm}} incluyen una interfaz de línea de mandatos para crear, desarrollar y desplegar aplicaciones web, móviles y de microservicios.
{: shortdesc}

Asegúrese de utilizar siempre la versión más reciente de la CLI autónoma de {{site.data.keyword.cloud_notm}} para
{{site.data.keyword.cloud_notm}} público. Si necesita utilizar una versión de 32 bits o una versión anterior a la más reciente para los entornos dedicados de {{site.data.keyword.cloud_notm}}, consulte [Releases de CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-cli-releases).
{: note}

El mandato de instalación de esta guía de aprendizaje instala la versión más reciente de la CLI autónoma de
{{site.data.keyword.cloud_notm}} que esté disponible, además de las herramientas siguientes:

* `Homebrew` (solo Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in de {{site.data.keyword.dev_cli_notm}}
* Plug-in de {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in de {{site.data.keyword.registrylong_notm}}
* Plug-in de {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Antes de empezar
{: #idt-prereq}

Necesita una [cuenta de {{site.data.keyword.cloud_notm}}](https://cloud.ibm.com/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") y los siguientes requisitos del sistema:

* Si ejecuta Windows, algunas funciones no reciben soporte a menos que utilice Windows 10 Pro.
* Debe utilizar el canal estable para Docker con una versión mínima de 1.13.1.

## Paso 1. Ejecutar el mandato de instalación
{: #step1-install-idt}

* Para Mac y Linux, ejecute el mandato siguiente:
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Para Windows 10 Pro, ejecute el mandato siguiente como administrador:
  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Pulse con el botón derecho del ratón el icono de Windows PowerShell y seleccione **Ejecutar como administrador**.
  {: tip}

También puede descargar el script del instalador desde este [repositorio de GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").

Para ver los pasos para instalar estas herramientas de manera manual, consulte
[Instalación manual de componentes de plugin de CLI de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).

## Paso 2. Verificar la instalación
{: #step2-verify-idt}

Para verificar que las herramientas de desarrollador y la CLI se han instalado correctamente, ejecute el mandato `help`:
```
ibmcloud dev help
```
{: codeblock}

La salida lista las instrucciones de uso, la versión actual y los mandatos admitidos.

## Paso 3. Configurar el entorno
{: #step3-configure-idt-env}

1. Inicie una sesión en {{site.data.keyword.cloud_notm}} con su IBMid. Si tiene varias cuentas, se le solicitará que seleccione qué cuenta desea utilizar. Si no especifica una región con el distintivo `-r`, también deberá seleccionar una región.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Para iniciar sesión con un ID federado, utilice el distintivo
`--sso`. Consulte [Inicio de sesión con un ID federado](/docs/iam/federated_id?topic=iam-federated_id#federated_id) para obtener más detalles.
  {: tip}

2. Para acceder a los servicios de Cloud Foundry, debe especificar una organización y un espacio de Cloud Foundry. Puede ejecutar el mandato siguiente para identificar la organización y el espacio de forma interactiva:
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  O bien, si conoce a qué organización y espacio pertenece el servicio, puede utilizar el mandato siguiente:
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## Pasos siguientes
{: #next-steps}

Ahora está listo para desarrollar y desplegar su primera aplicación. Consulte [Creación y despliegue de apps utilizando la CLI](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli) para obtener más información.
