---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Configuración de {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

{{site.data.keyword.dev_cli_short}} permite una aproximación mediante la interfaz de línea de mandatos para crear, desarrollar y desplegar aplicaciones para desarrolladores que desean utilizar una línea de mandatos para desarrollar aplicaciones web de principio a fin, móviles y de microservicios.
{: shortdesc}

## Requisitos previos
{: #prereq}

Regístrese en [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net).

*  Si está utilizando Microsoft Windows&trade;, debe utilizar Windows 10 o posterior.

* Debe utilizar el canal estable para Docker, con una versión mínima de 1.13.1.

## Instalación
{: #installation}

Para instalar la herramienta, ejecute el mandato relevante para invocar el instalador de IBM. De esta forma instalará dependencias, como IBM Cloud CLI, Kubernetes, Helm y Docker. Para la instalación de estos componentes, utilice estos pasos de instalación:

**Mac y Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Valide la correcta instalación del plugin ejecutando el siguiente mandato:  

```
bx dev
```
{: codeblock}

## Configure su entorno
{: #configure-environment}

1. Conéctese a un punto final de API en su [región de {{site.data.keyword.Bluemix_notm}}](/docs/overview/cf.html#ov_intro_reg). Por ejemplo, escriba el siguiente mandato para conectar con la región de {{site.data.keyword.Bluemix_notm}} EE.UU. Sur:

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Inicie una sesión en {{site.data.keyword.Bluemix_notm}} con su IBMid.

	```
	bx login
	```
	{: codeblock}

	**Nota:** Si se rechazan sus credenciales, puede que esté utilizando un ID federado. Siga estos pasos para autenticarse mediante un ID federado.

	1. Inicie sesión en [{{site.data.keyword.iamshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Seleccione **Crear clave de API**.
		* Especifique un nombre y descripción para la clave de API
	3. Descargue su clave de API.
	4. Abra el archivo y copie el valor del campo `apiKey`.
	5. Inicie sesión utilizando el siguiente mandato:

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. Establezca su organización y espacio utilizando:

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## Más información
{: #learn}

Ahora que ha instalado {{site.data.keyword.dev_cli_short}}, aprenda cómo aprovechar esta potente herramienta:
- [Iniciación a IDT CLI](index.html)
- [Mandatos IDT (bx dev)](commands.html)
- [Herramientas de desarrollador para VS Code](vscode.html)
- [Herramientas de desarrollador para IDE de Jetbrains](jetbrains.html)

Consulte las [guías de aprendizaje](/docs/apps/tutorials/tutorial_bff.html) que muestran cómo crear apps nativas en la nube utilizando {{site.data.keyword.dev_cli_short}}.

## Lectura adicional
{: #learn-more}

Los siguientes recursos pueden ser útiles para desarrollar apps nativas de nube con IBM Developer Tools CLI:

- [Página principal de IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - Página principal del producto IDT CLI
- [Instalador de IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Repositorio GitHub público con instrucciones detalladas de instalación
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - Página de la consola IBM Cloud que junto con las herramientas de IDT permite crear y gestionar apps nativa en la nube
- [IBM Cloud Tech's Slack - canal #developer-tools](https://ibm-cloud-tech.slack.com) - Comente la utilización de las herramientas de IDT, obtenga respuestas, sugiera ideas y mucho más
	- [Solicitar acceso de equipo](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Centrado en el lenguaje**

- [Node,js en IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs y guías de aprendizaje**

- [Despliegue en una instancia de IBM Cloud privada con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Habilitación de proyectos existentes para IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Despliegue en Kubernetes en IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
