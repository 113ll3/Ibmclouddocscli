---
copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Configuración de la CLI de {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

La CLI de {{site.data.keyword.dev_cli_short}} permite una aproximación mediante la interfaz de línea de mandatos para crear, desarrollar y desplegar aplicaciones para desarrolladores que desean utilizar una línea de mandatos para desarrollar aplicaciones web de principio a fin, móviles y de microservicios. Comience a trabajar rápidamente con el conjunto de herramientas recomendado ejecutando uno de los scripts siguientes.
{: shortdesc}

## Antes de empezar con {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Regístrese en [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

*  Si está utilizando Microsoft Windows&trade;, debe utilizar Windows 10 o posterior.

* Debe utilizar el canal estable para Docker, con una versión mínima de 1.13.1.

## Cómo instalar {{site.data.keyword.dev_cli_notm}}
{: #installation}

Para instalar el conjunto de herramientas, puede ejecutar el mandato relevante para iniciar el instalador. De esta forma se instalan las siguientes herramientas recomendadas para el desarrollo de {{site.data.keyword.Bluemix_notm}} (si todavía no se ha instalado): `Homebrew` (solo en Mac), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, la CLI de {{site.data.keyword.Bluemix_notm}}, y los plugins de {{site.data.keyword.dev_cli_notm}}, Cloud Functions, Container Registry, Container Service y `sdk-gen`. Para la instalación, utilice estos pasos de instalación:

**Mac y Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: Abra Windows PowerShell pulsando con el botón derecho del ratón el icono de PowerShell y seleccionando "Ejecutar como administrador".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

También puede descargar el script del instalador desde nuestro [repositorio de GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools)

## Verificar la instalación
Para verificar la instalación, ejecute el mandato `help`:

```
ibmcloud dev help
```
{: codeblock}

Si la instalación ha sido satisfactoria, la salida muestra instrucciones de uso, la versión actual y los mandatos soportados.

La sección [Reinstalación de herramientas](/docs/troubleshoot/ts_createapps.html#appendix) contiene información para instalar todas las dependencias individualmente.

## Configure su entorno
{: #configure-environment}

1. Conéctese a un punto final de API en su ubicación de {{site.data.keyword.Bluemix_notm}}. Por ejemplo, escriba el siguiente mandato para conectar con la ubicación Dallas de {{site.data.keyword.Bluemix_notm}}:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Inicie una sesión en {{site.data.keyword.Bluemix_notm}} con su IBMid.

	```
	ibmcloud login
	```
	{: codeblock}

	Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Siga estos pasos para autenticarse mediante un ID federado.
	{: note}

	1. Inicie sesión en [{{site.data.keyword.iamshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Seleccione **Crear clave de API**.
		* Especifique un nombre y descripción para la clave de API
	3. Descargue su clave de API.
	4. Abra el archivo y copie el valor del campo `apiKey`.
	5. Inicie sesión utilizando el siguiente mandato:

		```
		ibmcloud login --apikey <value>
		```
		{: codeblock}

3. Establezca su organización y espacio utilizando:

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Más información
{: #learn}

Ahora que ha instalado la CLI de {{site.data.keyword.dev_cli_short}}, aprenda cómo aprovechar esta potente herramienta:
- [Iniciación a IDT CLI](index.html)
- [Mandatos IDT (ibmcloud dev)](commands.html)
- [Herramientas de desarrollador para VS Code](vscode.html)
- [Herramientas de desarrollador para IDE de Jetbrains](jetbrains.html)

Consulte las [guías de aprendizaje](/docs/apps/tutorials/tutorial_bff.html) que muestran cómo crear apps nativas en la nube que utilizan la CLI de {{site.data.keyword.dev_cli_short}}.

## Lectura adicional
{: #learn-more}

Los siguientes recursos pueden ser útiles para desarrollar apps nativas de nube con IBM Developer Tools CLI:

- [Página principal de IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - Página principal del producto IDT CLI
- [Instalador de IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Repositorio GitHub público con instrucciones detalladas de instalación
- [IBM Cloud App Service](https://{DomainName}/developer/appservice) - Página de la consola IBM Cloud que junto con las herramientas de IDT permite crear y gestionar apps nativa en la nube
- [Informar de problemas en GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech's Slack - canal #developer-tools](https://ibm-cloud-tech.slack.com) - Solicitar acceso de equipo [aquí](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Centrado en el lenguaje**

- [Node.js en IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs y guías de aprendizaje**

- [Despliegue en una instancia de IBM Cloud privada con la CLI de IBM Cloud Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Habilitación de proyectos existentes para IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Despliegue en Kubernetes en IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
