---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Despliegue y desarrollo de apps
{: #developing}

El desarrollo de apps nativas de nube con la CLI de {{site.data.keyword.dev_cli_notm}} sigue un flujo sencillo:

1. [Crear o habilitar una app](#idt-create).
2. [Codificar, compilar y ejecutar](#code-build-run) apps localmente utilizando contenedores.
3. [Desplegar](#cli-deploy) la app en {{site.data.keyword.cloud_notm}}.

## Crear o habilitar una app
{: #idt-create}

Existen varias maneras en las que crear una app.
- [Consola web de App Services](https://cloud.ibm.com/developer/appservice/dashboard) para microservicios y apps web genéricas
- [Watson Dashboard](https://cloud.ibm.com/developer/watson/dashboard) para crear apps iniciadoras habilitando una funcionalidad basada en Watson.
    - Hay disponibles paneles de control basados en otras tecnologías y sectores en el icono de menú en la página de inicio de {{site.data.keyword.cloud_notm}}. Todos ellos siguen un enfoque similar a los kits de inicio para crear nuevas apps.
- El mandato de la CLI de {{site.data.keyword.dev_cli_notm}} [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) para crear una nueva app.
- El mandato de la CLI de {{site.data.keyword.dev_cli_notm}} [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) para habilitar rápidamente la nube en una app existente del lado del servidor.

Para cualquiera de los métodos de creación anteriores, el flujo es similar. Puede elegir el tipo de proyecto, el lenguaje de implementación y el patrón de app a utilizar. También puede optar por añadir servicios a la app como, por ejemplo, autenticación o persistencia. Por último, puede elegir habilitar la funcionalidad de DevOps para la app. Esta funcionalidad proporciona una cadena de herramientas completas de control de origen y comunicaciones en equipo y un conducto que se desencadenan en cada confirmación de código para validar, compilar y desplegar su app en {{site.data.keyword.cloud_notm}}.

![Ejemplo de crear flujo utilizando {{site.data.keyword.dev_cli_notm}} CLI](create_flow.png "Ejemplo de crear flujo utilizando {{site.data.keyword.dev_cli_notm}} CLI") <br> Figura 2. Ejemplo de crear flujo utilizando {{site.data.keyword.dev_cli_notm}} CLI

La CLI de {{site.data.keyword.dev_cli_notm}} funciona de forma integrada para proporcionar una experiencia transparente durante el desarrollo. Los proyectos creados en cualquiera de las consolas web proporcionan un botón **Descargar código** para descargar el código fuente generado en su estación de trabajo para un desarrollo adicional.

### Mandatos de CLI útiles
{: #helpful}

Los mandatos de CLI siguientes le ayudan a trabajar con el proyecto y las consolas web:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) para extraer el código fuente generado de una app en su estación de trabajo
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) para abrir su navegador en la página de proyecto actual de la app en {{site.data.keyword.cloud_notm}}
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) para crear una nueva app.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) para suprimir la app actual del área de proyecto de {{site.data.keyword.cloud_notm}}.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) para habilitar en la nube una app existente del lado del servidor.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) para obtener las credenciales necesarias para el proyecto para habilitar el uso de los servicios vinculados.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) para listar todas las apps que ha creado en el espacio/organización seleccionado actualmente, desde la CLI o las consolas.

### Exploración de estructuras de proyecto de apps
{: #exploring-project}

Los proyectos creados o habilitados para ser utilizados con la herramienta vienen con valores configurados encapsulados de forma previa en el archivo `config.yml`. `cli-config.yml` tiene entradas predeterminadas que utilizan los mandatos de la herramienta que pueden sustituirse por valores que se pasan a través de la línea de mandatos.

### Vídeos y blogs de referencia
{: #ref1}

- Vídeo: [Instalación de herramientas de desarrollador de {{site.data.keyword.cloud_notm}} en Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
- Blog: [Habilitar proyectos existentes para IBM Cloud con la CLI de herramientas de desarrollador de IBM Cloud](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

## Codificar, compilar y ejecutar
{: #code-build-run}

Una vez que el proyecto se haya creado, es el usuario quien lo debe transformar de modo que tenga una utilidad. El flujo general consiste en editar el código fuente, ejecutar un mandato [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) para compilar la app dentro de un contenedor local específico para su configuración y lenguaje de la app. Dependiendo del lenguaje y generador utilizados por la app, puede haber uno o varios contenedores de forma predeterminada para dar soporte a la compilación y la ejecución local. Normalmente, hay un contenedor de herramientas ("tools") para las compilaciones y la depuración local. Este contenedor normalmente tiene más herramientas y funcionalidades para ayudarle en el desarrollo. También hay un contenedor de ejecución ("run") que imita el entorno de tiempo de ejecución real de la app cuando se despliega en la nube, ya sea en Cloud Foundry o en un entorno de contenedores basados en Kubernetes de IBM.

Tiene la libertad de utilizar el editor o IDE que prefiera para codificar su aplicación. Ofrecemos una extensión para el editor Microsoft Visual Studio Code (VSCode) que habilita el acceso a todos los mandatos de IDE directamente desde el editor.

Cuando se compile el proyecto, ejecute la app utilizando
[`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) o [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). De esta forma se ejecuta la app en el contenedor adecuado. Algunos patrones de apps dan soporte a varios contenedores externos para sus apps. Estos se inician y configuran automáticamente durante la ejecución o la depuración. También hay un mandato [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) que ejecuta casos de prueba asociados a la app.

### Cómo se utilizan los contenedores locales
{: #local-containers}

La CLI de {{site.data.keyword.dev_cli_long}} utiliza dos contenedores para la creación y la realización de pruebas de su aplicación. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la aplicación. El Dockerfile para este contenedor está definido por el parámetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Podría considerarlo como un contenedor de desarrollo, ya que contiene las herramientas que normalmente se utilizan para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.cloud}}. Como resultado, se define un punto de entrada que inicia su aplicación. Al seleccionar ejecutar la aplicación a través de la CLI de {{site.data.keyword.dev_cli_short}}, utiliza este contenedor. El Dockerfile para este contenedor está definido por el parámetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

### Mandatos de CLI útiles
{: #helpful2}

Los siguientes mandatos de CLI le ayudan a trabajar con el proyecto durante los ciclos de codificación, compilación y ejecución:
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) Compila el proyecto en un contenedor local.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) Depura aplicaciones en un contenedor local.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) Ejecuta aplicaciones en un contenedor local.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) Abre un shell en un contenedor local.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) Comprueba el estado de contenedores utilizados por la interfaz de línea de mandatos (CLI) de {{site.data.keyword.dev_cli_notm}}.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) Detiene un contenedor
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) Prueba la aplicación en un contenedor local.

### Depuración de apps locales
{: #ref2}

- [Depuración de apps locales](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Desplegar
{: #cli-deploy}

Bajo un entorno nativo adecuado en la nube, utilizará un conducto DevOps completamente funcional para gestionar todos los despliegues, así como otras muchas funcionalidades. Durante la creación del flujo, puede configurar la app para utilizar DevOps en IBM Cloud. Si no está preparado para utilizar la funcionalidad de DevOps incorporada, puede desplegar manualmente la app con [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) o utilizar el mandato de despliegue dentro de su propio conducto de DevOps.  

### Mandatos de CLI útiles
{: #helpful3}

Los siguientes mandatos de CLI ayudan a trabajar con su proyecto durante el proceso de despliegue:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Abre la consola de {{site.data.keyword.cloud_notm}} para un proyecto.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) Despliega aplicaciones en {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) Visualiza el URL de su proyecto.

### Vídeos y blogs de referencia
{: #ref3}

- Blog: [Despliegue en {{site.data.keyword.cloud_notm}} privado con la CLI de herramientas de desarrollo de {{site.data.keyword.cloud_notm}}](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
- Blog: [Despliegue en Kubernetes en {{site.data.keyword.cloud_notm}} con la CLI de herramientas de desarrollador de {{site.data.keyword.cloud_notm}}](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
