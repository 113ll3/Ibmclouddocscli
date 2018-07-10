---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Iniciación a la CLI de {{site.data.keyword.Bluemix_notm}}
{: #overview}

En esta guía de aprendizaje, instalará un conjunto de herramientas de desarrollador de {{site.data.keyword.Bluemix}}, verificará la instalación y configurará el entorno. Las herramientas de desarrollador de {{site.data.keyword.Bluemix}} permite una aproximación mediante la interfaz de línea de mandatos para crear, desarrollar y desplegar aplicaciones web de principio a fin, móviles y de microservicios. 
{:shortdesc}

Con está instalación, obtendrá la CLI de {{site.data.keyword.Bluemix_notm}}, además de las herramientas siguientes: 

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
{: #prereq}

Necesita una cuenta de [{{site.data.keyword.Bluemix_notm}} ](https://console.bluemix.net/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") y los siguientes requisitos del sistema:

* Si está utilizando Microsoft Windows&trade;, debe utilizar Windows 10 o posterior.
* Debe utilizar el canal estable para Docker con una versión mínima de 1.13.1.

## Paso 1: Ejecutar el mandato de instalación
{: #step1}

* Para Mac y Linux, ejecute el mandato siguiente:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br><br>

* Para Windows 10, ejecute el mandato siguiente como administrador:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br><br>
  Pulse con el botón derecho del ratón el icono de Windows PowerShell y seleccione **Ejecutar como administrador**.
  {: tip}

## Paso 2: Verificar la instalación
{: #step2}

Para verificar que las herramientas de desarrollador y la CLI se han instalado correctamente, ejecute el mandato `help`:

```
ibmcloud dev help
```
{: codeblock}
<br><br>
La salida lista las instrucciones de uso, la versión actual y los mandatos admitidos.

## Paso 3: Configurar el entorno
{: #step3}

1. Conéctese a un punto final de API en su región de {{site.data.keyword.Bluemix_notm}}. Por ejemplo, escriba el siguiente mandato para conectar con la región de {{site.data.keyword.Bluemix_notm}} EE.UU. Sur:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Inicie una sesión en {{site.data.keyword.Bluemix_notm}} con su IBMid.

	```
	ibmcloud login
	```
	{: codeblock}
<br><br>
	Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Consulte [Inicio de sesión con un ID federado](/docs/iam/login_fedid.html#using-an-api-key) para obtener más detalles.
	{: tip}

3. Establezca su organización y espacio.

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Pasos siguientes
{: #next-steps}

Ahora está listo para desarrollar y desplegar su primera app. Consulte [Creación de una aplicación web básica con un kit de iniciadores](/docs/apps/tutorials/tutorial_web.html) para obtener más información.
