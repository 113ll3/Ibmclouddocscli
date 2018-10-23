---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Uso de {{site.data.keyword.dev_cli_notm}} desde un contenedor de Docker

Con el contenedor de Docker de {{site.data.keyword.dev_cli_notm}}, obtiene la CLI de {{site.data.keyword.Bluemix}}, además de las herramientas siguientes:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in de {{site.data.keyword.dev_cli_notm}}
* Plug-in de {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in de {{site.data.keyword.registrylong_notm}}
* Plug-in de {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Antes de empezar
{: #prereq}

Necesita una [cuenta de {{site.data.keyword.Bluemix_notm}}](https://console.bluemix.net/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo") y debe instalar la última versión de Docker estable antes de realizar los pasos siguientes.

## Paso 1. Extraer la imagen de Docker del concentrador de Docker.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Paso 2. Iniciar el contenedor de Docker.
{: #step2}

Utilice el mandato siguiente para iniciar el contenedor de Docker de {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Paso 3. Iniciar sesión en {{site.data.keyword.Bluemix_notm}} con su IBMid.
{: #step3}

```
ibmcloud login
```
{: codeblock}


Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Consulte [Inicio de sesión con un ID federado](/docs/iam/login_fedid.html#federated_id) para obtener más detalles.
{: tip}

Ahora está listo para utilizar el {{site.data.keyword.dev_cli_notm}} para gestionar los recursos de {{site.data.keyword.Bluemix_notm}} y desarrollar y desplegar sus aplicaciones.
