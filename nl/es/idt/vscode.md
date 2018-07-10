---

copyright:

  years: 2017, 2018

lastupdated: "2018-06-21"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools para Visual Studio Code
{: #ibm-dev-tools-for-vscode}

IBM Developer Extension para Visual Studio Code es una extensión para el editor que proporciona acceso a las funciones de la CLI de desarrollador de IBM directamente dentro de la paleta de mandatos del editor de Visual Studio Code. Le permite acceder rápidamente a un subconjunto de mandatos de `ibmcloud dev` para ambos flujos de trabajo de Docker y CloudFoundry, incluyendo despliegue de apps, iniciar/detener/reiniciar apps en {{site.data.keyword.Bluemix_notm}}, visualización de los registros de app remoto, etc., todos sin la necesidad de dejar el contexto del editor.
{:shortdesc}

![Captura de pantalla de la pantalla de descarga de la extensión de IBM Developer Tools.](vscode.png "Pantalla de descarga de la extensión en Visual Studio Code")

## Dependencias
{: #dependencies}

Para utilizar IBM Developer Tools Extension para Visual Studio Code, necesita que en el sistema estén instalados [{{site.data.keyword.Bluemix_notm}} CLI](https://plugins.ng.bluemix.net/ui/home.html) y el plugin [IBM Developer CLI](index.html).

## Instalación
{: #installation}

La forma más sencilla para instalar la extensión de IBM Developers Tools consiste en utilizar el mandato 'quick open' de Visual Studio Code:

1. Abra la paleta de mandatos 'quick open' mediante las combinaciones de clave siguientes desde el editor:

  * **Mac:** `cmd + p`
  * **Windows / Linux:** `ctrl + p`

2. Especifique el mandato `ext install ibm-developer` y pulse Intro para instalar la extensión de IBM Developer Tools dentro del editor de Visual Studio Code.

Como alternativa, puede instalar la extensión de IBM Developer Tools a través de la ventana de gestión "Extensiones":

1. Abra la barra lateral de **Extensions** dentro de la ventana del editor de Visual Studio Code, y, a continuación, busque utilizando la serie `publisher:IBM Developer`. La extensión de IBM Developer Tools se mostrará en los resultados de la búsqueda.  
2. Pulse el botón **Instalar** para empezar la instalación.

También puede acceder a la extensión de [IBM Developer Tools directamente dentro de Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer).

## Uso
{: #usage}

Puede iniciar los mandatos de extensión utilizando la paleta de mandatos de Visual Studio Code.

En primer lugar, abra la paleta de mandatos utilizando la siguiente combinación de teclas:

* **Mac:** `cmd + Mayús + p`
* **Windows / Linux:** `ctrl + Mayús + p`

A continuación, escriba o seleccione el mandato que desea invocar. Puede escribir ‘ibmcloud’ dentro de la paleta de mandatos para ver la lista de todos los mandatos disponibles.

### Utilice IBM Developer Extension para flujos de trabajo de Docker (contenedores de Docker)
{: #usage-docker}

Puede empezar con flujos de trabajo de ibmcloud dev, en unos cuantos pasos:
* Cree un proyecto mediante uno de los dos métodos siguientes:
  * Utilice la [consola web de {{site.data.keyword.Bluemix_notm}}](https://console.ng.bluemix.net/developer/getting-started/) y descargue el código generado
  * Utilice [{{site.data.keyword.Bluemix_notm}} Developer CLI](index.html) y genere un proyecto utilizando el mandato `ibmcloud dev create`
* Abra la carpeta del proyecto localmente en la ventana del editor de Visual Studio Code
* Utilice el mandato `ibmcloud dev build` para crear la app en una imagen de Docker
* Utilice el mandato `ibmcloud dev debug` para ejecutar la app en el Docker local para desarrollo
> Nota: para depurar una aplicación Node.js que se ejecuta dentro del contenedor local de Docker, deberá [añadir una configuración de depuración para el contenedor local](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container).
* Utilice el mandato `ibmcloud dev run` para ejecutar la app en el Docker local en modo de publicación
* Utilice el mandato `ibmcloud dev deploy` para desplegar la aplicación en un tiempo de ejecución de Cloud Foundry en {{site.data.keyword.Bluemix_notm}}

### Utilice IBM Developer Extension para flujos de trabajo de Cloud Foundry
{: #usage-cloud-foundry}

Para los usuarios que están actualmente desplegando apps en tiempos de ejecución de Cloud Foundry en IBM {{site.data.keyword.Bluemix_notm}}, también se ofrece soporte para el conjunto de operaciones `cf`.

Puede empezar con flujos de trabajo de CloudFoundry en unos cuantos pasos:
* Cree una nueva aplicación de CloudFoundry
  * Utilice la [consola web](https://console.ng.bluemix.net/dashboard/cf-apps) y descargue el código iniciador
  * Cree una nueva aplicación de CloudFoundry manualmente
* Abra la carpeta del proyecto localmente en el editor de Visual Studio Code
* Utilice `ibmcloud cf apps` para mostrar una lista de todas sus aplicaciones
* Utilice `ibmcloud cf push` para enviar una compilación de su aplicación al tiempo de ejecución de Cloud Foundry
* Utilice `ibmcloud cf <start/stop/restage/restart>` para cambiar el estado de su aplicación
* Utilice `ibmcloud cf logs` para ver la corriente de anotaciones cronológicas en directo de su aplicación
  * Utilice `ibmcloud cf logs` para detener la corriente de anotaciones cronológicas
