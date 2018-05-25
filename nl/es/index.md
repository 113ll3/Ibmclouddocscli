---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} Visión general
{: #overview}

{{site.data.keyword.dev_cli_notm}} es una aproximación mediante la interfaz de línea de mandatos para crear, desarrollar y desplegar aplicaciones para desarrolladores que desean utilizar una línea de mandatos para desarrollar aplicaciones web de principio a fin, móviles y de microservicios. Comience a trabajar rápidamente con el conjunto de herramientas recomendado ejecutando uno de los scripts siguientes.
{: shortdesc} 

## Requisitos previos para {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Regístrese en [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* Si está utilizando Microsoft Windows&trade;, debe utilizar Windows 10 o posterior.

* Debe utilizar el canal estable para Docker, con una versión mínima de 1.13.1.

## Cómo instalar {{site.data.keyword.dev_cli_notm}}
{: #installation}

Para instalar el conjunto de herramientas, puede ejecutar el mandato relevante para iniciar el instalador. De esta forma se instalan las siguientes herramientas recomendadas para el desarrollo de {{site.data.keyword.Bluemix_notm}} (si todavía no se ha instalado): `Homebrew` (solo en Mac), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, la CLI de {{site.data.keyword.Bluemix_notm}}, y los plugins de {{site.data.keyword.dev_cli_notm}}, Cloud Functions, Container Registry, Container Service y `sdk-gen`.

**Mac y Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: Abra Windows PowerShell pulsando con el botón derecho y seleccione "Ejecutar como administrador".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## Otros enlaces para explorar más la {{site.data.keyword.dev_cli_notm}}

- [Configuración detallada](/docs/cli/idt/setting_up_idt.html)
- [Uso](/docs/cli/idt/index.html)
- [Mandatos](/docs/cli/idt/commands.html)
- [Plugins de CLI](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [Extensión IDE VSCode](/docs/cli/idt/vscode.html)
- [Instalar la CLI de IBM Cloud de forma manual](/docs/cli/reference/bluemix_cli/get_started.html)
