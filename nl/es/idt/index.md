---
copyright:

  years: 2018

lastupdated: "2018-04-17"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Uso de la CLI de {{site.data.keyword.dev_cli_notm}}
{: developing}

El desarrollo de apps nativas de nube con la CLI de {{site.data.keyword.dev_cli_notm}} sigue un flujo sencillo:

1. [Crear o habilitar una app](#create)
2. [Codificar, compilar y ejecutar](#build) apps localmente utilizando contenedores
3. [Desplegar](#deploy) la app en {{site.data.keyword.Bluemix_notm}}

## Crear o habilitar una app
{: #create}

Existen varias maneras en las que crear una app de nube.
- [Consola web de App Services](https://console.bluemix.net/developer/appservice) para microservicios y apps web genéricas
- [Watson Dashboard](https://console.bluemix.net/dashboard/watson) para crear apps iniciadoras habilitando una funcionalidad basada en Watson.
    - Hay disponibles paneles de control basados en otras tecnologías y sectores en el icono de menú en la página de inicio de {{site.data.keyword.Bluemix_notm}}. Todos ellos siguen un enfoque similar a los kits de iniciación para crear nuevas apps.
- El mandato de la CLI de {{site.data.keyword.dev_cli_notm}} [`bx dev create`](./commands.html#create) para crear una nueva app.
- El mandato de la CLI de {{site.data.keyword.dev_cli_notm}} [`bx dev enable`](./commands.html#enable) para habilitar rápidamente la nube en una app existente del lado del servidor.

Para cualquiera de los métodos de creación anteriores, el flujo es similar. Puede elegir el tipo de proyecto, el lenguaje de implementación y el patrón de app a utilizar. También puede optar por añadir servicios de valor añadido a la app como, por ejemplo, autenticación o persistencia. Por último, puede elegir habilitar la funcionalidad de DevOps para la app. Esta funcionalidad proporciona una cadena de herramientas completas de control de origen y comunicaciones en equipo y un conducto que se desencadenan en cada confirmación de código para validar, compilar y desplegar su app en IBM Cloud.

![Ejemplo de crear flujo utilizando IDT CLI](create_flow.png "Ejemplo de crear flujo utilizando IDT CLI") <br> Figura 2. Ejemplo de crear flujo utilizando IDT CLI

La CLI de {{site.data.keyword.dev_cli_notm}} funciona de forma integrada para proporcionar una experiencia transparente durante el desarrollo. Los proyectos creados en cualquiera de las consolas web proporcionan un botón "Descargar código" para descargar el código fuente generado en su estación de trabajo para un desarrollo adicional.

### Mandatos de CLI útiles
Los mandatos de CLI siguientes le ayudan a trabajar con el proyecto y las consolas web:
- [`code`](./commands.html#enable) para extraer el código fuente generado de una app en su estación de trabajo
- [`console`](./commands.html#console) para abrir su navegador en la página de proyecto actual de la app en {{site.data.keyword.Bluemix_notm}}
- [`create`](./commands.html#create) para crear una nueva app.
- [`delete`](./commands.html#delete) para suprimir la app actual del área de proyecto de {{site.data.keyword.Bluemix_notm}}.
- [`enable`](./commands.html#enable) para habilitar en la nube una app existente del lado del servidor.
- [`get-credentials`](./commands.html#get-credentials) para obtener las credenciales necesarias para el proyecto para habilitar el uso de los servicios vinculados.
- [`list`](./commands.html#list) para listar todas las apps que ha creado en el espacio/organización seleccionado actualmente, desde la CLI o las consolas.


### Exploración de estructuras de proyecto de apps
{: exploring-project}

Los proyectos creados o habilitados para ser utilizados con la herramienta vienen con valores configurados encapsulados de forma previa en el archivo `config.yml`. `cli-config.yml` contiene entradas predeterminadas que utilizan los mandatos de la herramienta que pueden sustituirse por valores que se pasan a través de la línea de mandatos.

Aquí podrá encontrar más detalles sobre las estructuras de los proyectos:
- [Proyectos Java](/docs/apps/projects/java_project_contents.html)
- [Proyectos NodeJS ](/docs/apps/projects/node_project_contents.html)
- [Proyectos Python ](/docs/apps/projects/python_project_contents.html)
- [Proyectos Swift ](/docs/apps/projects/swift_project_contents.html)


### Vídeos y blogs de referencia
- Vídeo: [Instalación de IDT en Ubuntu (Linux)]()
- Blog: [Habilitación de proyectos existentes para IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## Codificar, compilar y ejecutar
{: #build}


Una vez que el proyecto se ha creado, es el usuario quien lo debe transformar de modo que tenga una utilidad. El flujo general consiste en editar el código fuente, ejecutar un mandato [`bx dev build`](commands.html#build) para compilar la app dentro de un contenedor local específico para su configuración y lenguaje de la app. Dependiendo del lenguaje y generador utilizados por la app, puede haber uno o varios contenedores de forma predeterminada para dar soporte a la compilación y la ejecución local.  Normalmente, habrá un contenedor de herramientas ("tools") para las compilaciones y la depuración local.  Este contenedor normalmente tendrá más herramientas y funcionalidades para ayudarle en el desarrollo.  También habrá un contenedor de ejecución ("run") que imitará el entorno de tiempo de ejecución real de la app una vez desplegada en la nube, ya sea en Cloud Foundry o en un entorno de contenedores basados den Kubernetes de IBM.


Tiene la libertad de utilizar el editor o IDE que prefiera para codificar su aplicación. Ofrecemos una extensión para el editor Microsoft VisualStudio Code (VSCode) que habilita el acceso a todos los mandatos de IDE directamente desde el editor.

Una vez compilado el proyecto, el siguiente paso será ejecutar la app con [`bx dev run`](commands.html#run) o [`bx dev debug`](commands.html#debug), dependiendo de la configuración del generador de la app.  De esta forma ejecutará la app en el contenedor adecuado.  Algunos patrones de apps dan soporte a varios contenedores externos para sus apps, proporcionando persistencia u otras funcionalidades.  Estos se iniciarán y configurarán automáticamente durante la ejecución o depuración.  También hay un mandato [`bx dev test`](commands.html#test) que ejecutará casos de prueba asociados a la app.


### Cómo se utilizan los contenedores locales
{: local-containers}

La CLI de {{site.data.keyword.dev_cli_long}} utiliza dos contenedores para facilitar la creación y la realización de pruebas de su aplicación. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la aplicación. El Dockerfile para este contenedor está definido por el parámetro [`dockerfile-tools`](commands.html#command-parameters). Podría considerarlo como un contenedor de desarrollo que contiene las herramientas normalmente utilizadas para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.Bluemix}}. Como resultado, se define un punto de entrada que inicia su aplicación. Al seleccionar ejecutar la aplicación a través de la CLI de {{site.data.keyword.dev_cli_short}}, utiliza este contenedor. El Dockerfile para este contenedor está definido por el parámetro [`dockerfile-run`](commands.html#run-parameters).


### Mandatos de CLI útiles
Los siguientes mandatos de CLI ayudan a trabajar con el proyecto durante los ciclos de codificación, compilación y ejecución:
- [`build`](./commands.html#build) Compila el proyecto en un contenedor local
- [`debug`](./commands.html#debug) Depura aplicaciones en un contenedor local
- [`run`](./commands.html#run) Ejecuta aplicaciones en un contenedor local
- [`shell`](./commands.html#shell) Abre un shell en un contendedor local
- [`status`](./commands.html#status) Comprueba el estado de contenedores utilizados por la interfaz de línea de mandatos (CLI)
- [`stop`](./commands.html#stop) Detiene un contenedor
- [`test`](./commands.html#test) Prueba la aplicación en un contenedor local

### Vídeos y blogs de referencia
- [Depuración de apps locales](local_debug.html)





## Desplegar
{: deploy}

Bajo un entorno nativo adecuado en la nube, podría querer utilizar un conducto DevOps completamente funcional para gestionar todos los despliegues, así como otras muchas funcionalidades.  Durante la creación del flujo, puede configurar la app para utilizar DevOps en IBM Cloud.  Si no está preparado para utilizar la funcionalidad de DevOps incorporada, puede desplegar manualmente la app con [`bx dev deploy`](./commands.html#deploy) o utilizar el mandato de despliegue dentro de su propio conducto de DevOps.  



### Mandatos de CLI útiles
Los siguientes mandatos de CLI ayudan a trabajar con su proyecto durante el proceso de despliegue:
- [`console`](./commands.html#console) Abre la consola de IBM Cloud para un proyecto
- [`deploy`](./commands.html#deploy) Despliega aplicaciones en IBM Cloud
- [`view`](./commands.html#view) Visualiza el URL de su proyecto


### Vídeos y blogs de referencia
- Blog: [Despliegue en una instancia de IBM Cloud privada con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- Blog: [Despliegue en Kubernetes en IBM Cloud con IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
