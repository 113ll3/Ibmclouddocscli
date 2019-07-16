---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-19"

keywords: cli, docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Uso de {{site.data.keyword.dev_cli_notm}} desde un contenedor de Docker
{: #using-idt-from-docker}

Con el contenedor de Docker de {{site.data.keyword.dev_cli_notm}}, obtiene la CLI de {{site.data.keyword.cloud}}, además de las herramientas siguientes:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in de {{site.data.keyword.dev_cli_notm}}
* Plug-in de {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in de {{site.data.keyword.registrylong_notm}}
* Plug-in de {{site.data.keyword.containerlong_notm}}

## Antes de empezar
{: #idt-docker-prereq}

Necesita una [cuenta de {{site.data.keyword.cloud_notm}}](https://{DomainName}/login){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo") y debe instalar la versión estable más reciente de Docker antes de realizar los pasos siguientes.

## Paso 1. Extraer la imagen de Docker del concentrador de Docker.
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Paso 2. Iniciar el contenedor de Docker.
{: #step2-start-docker}

Utilice el mandato siguiente para iniciar el contenedor de Docker de {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Paso 3. Iniciar sesión en {{site.data.keyword.cloud_notm}} con su IBMid.
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Consulte [Inicio de sesión con un ID federado](/docs/iam?topic=iam-federated_id#federated_id) para obtener más detalles.
{: tip}

El plugin de CLI de {{site.data.keyword.dev_cli_notm}} utiliza dos contenedores para facilitar la creación y la realización de pruebas de su aplicación. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la app. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Podría considerarlo como un contenedor de desarrollo, ya que contiene las herramientas que normalmente se utilizan para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución, que imita casi exactamente el entorno de tiempo de ejecución real de la app cuando se ha desplegado en la nube. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.cloud_notm}}. Como resultado, se define un punto de entrada que inicia su app. Al seleccionar ejecutar la app a través del plugin de CLI de {{site.data.keyword.dev_cli_notm}}, utiliza este contenedor. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

Ahora está listo para utilizar el {{site.data.keyword.dev_cli_notm}} para gestionar los recursos de {{site.data.keyword.cloud_notm}} y desarrollar y desplegar sus apps.
