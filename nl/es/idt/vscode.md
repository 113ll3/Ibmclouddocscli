---

copyright:
  years: 2017, 2019
lastupdated: "2019-06-21"

keywords: cli, ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

La extensión de IBM Cloud Developer Tools para Visual Studio Code proporciona acceso a las funciones de la CLI de desarrollador de IBM directamente dentro de la paleta de mandatos del editor de Visual Studio Code. Puede acceder rápidamente a un subconjunto de mandatos de `ibmcloud dev` para ambos flujos de trabajo de Docker y Cloud Foundry, incluyendo despliegue de apps, iniciar/detener/reiniciar apps en {{site.data.keyword.cloud}}, visualización de los registros de app remoto, etc., todos sin la necesidad de dejar el contexto del editor.
{:shortdesc}

![Captura de pantalla de la pantalla de descarga de la extensión de IBM Developer Tools.](../images/vscode.png "Pantalla de descarga de la extensión en Visual Studio Code")

## Dependencias
{: #vscode-dependencies}

Para utilizar la extensión IBM Cloud Developer Tools para Visual Studio Code, necesita la [CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-getting-started) y el plugin de CLI de {{site.data.keyword.cloud_notm}} que está instalado en el sistema.

## Instalación
{: #vscode-installation}

La forma más sencilla para instalar la extensión de {{site.data.keyword.dev_cli_notm}} consiste en utilizar el mandato 'quick open' de Visual Studio Code:

1. Abra la paleta de mandatos 'quick open' mediante las combinaciones de clave siguientes desde el editor:

  * **Mac:** `cmd + p`
  * **Windows / Linux:** `ctrl + p`

2. Especifique el mandato `ext install ibm-developer` y pulse Intro para instalar la extensión de {{site.data.keyword.dev_cli_notm}} dentro del editor de Visual Studio Code.

O bien, puede instalar la extensión de {{site.data.keyword.dev_cli_notm}} a través de la ventana de gestión "Extensiones":

1. Abra la barra lateral de **Extensions** dentro de la ventana del editor de Visual Studio Code, y, a continuación, busque utilizando la serie `publisher:IBM Developer`. La extensión de {{site.data.keyword.dev_cli_notm}} se mostrará en los resultados de la búsqueda.  
2. Pulse **Instalar** para comenzar la instalación.

También puede acceder a la extensión [IBM Cloud Developer Tools directamente desde Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

## Uso
{: #vscode-usage}

Puede iniciar los mandatos de extensión utilizando la paleta de mandatos de Visual Studio Code.

En primer lugar, abra la paleta de mandatos utilizando la siguiente combinación de teclas:

* **Mac:** `cmd + Mayús + p`
* **Windows / Linux:** `ctrl + Mayús + p`

A continuación, escriba o seleccione el mandato que desea invocar. Puede escribir ‘ibmcloud’ dentro de la paleta de mandatos para ver la lista de todos los mandatos disponibles.

### Utilice IBM Developer Extension para flujos de trabajo de Docker (contenedores de Docker)
{: #usage-docker}

Puede empezar con flujos de trabajo de `ibmcloud dev` en unos cuantos pasos:
* Cree un proyecto mediante uno de los dos métodos siguientes:
  * Utilice la [consola web de {{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y descargue el código generado
  * Utilice el plugin {{site.data.keyword.cloud_notm}} Developer Tools CLI y genere un proyecto con el mandato [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create).
* Abra la carpeta del proyecto localmente en la ventana del editor de Visual Studio Code
* Utilice el mandato `ibmcloud dev build` para crear la app en una imagen de Docker
* Utilice el mandato `ibmcloud dev debug` para ejecutar la app en el Docker local para desarrollo
> Nota: para depurar una aplicación Node.js que se ejecuta dentro del contenedor local de Docker, deberá [añadir una configuración de depuración para el contenedor local](https://github.com/IBM-Cloud/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").
* Utilice el mandato `ibmcloud dev run` para ejecutar la app en el Docker local en modo de publicación
* Utilice el mandato `ibmcloud dev deploy` para desplegar la app en un tiempo de ejecución de Cloud Foundry en {{site.data.keyword.cloud_notm}}

### Utilice IBM Developer Extension para flujos de trabajo de Cloud Foundry
{: #usage-cloud-foundry}

Para los usuarios que están actualmente desplegando apps en tiempos de ejecución de Cloud Foundry en {{site.data.keyword.cloud_notm}}, también se ofrece soporte para el conjunto de operaciones `cf`.

Puede empezar con flujos de trabajo de Cloud Foundry en unos cuantos pasos:
* Cree una nueva app de Cloud Foundry
  * Utilice la [consola web de {{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y descargue el código de inicio
  * Cree una nueva app de Cloud Foundry manualmente
* Abra la carpeta del proyecto localmente en el editor de Visual Studio Code
* Utilice `ibmcloud cf apps` para mostrar una lista de todas sus apps
* Utilice `ibmcloud cf push` para enviar una compilación de su app al tiempo de ejecución de Cloud Foundry
* Utilice ibmcloud `cf <start/stop/restage/restart>` para cambiar el estado de la app
* Utilice `ibmcloud cf logs` para ver la corriente de anotaciones cronológicas en directo de su app
  * Utilice `ibmcloud cf logs` para detener la corriente de anotaciones cronológicas
