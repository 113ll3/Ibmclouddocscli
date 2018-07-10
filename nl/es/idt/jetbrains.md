---

copyright:

  years: 2018

lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools for Jetbrains IDEs
{: #ibm-dev-tools-for-jetbrains}

IBM Developer Extension for Jetbrains IDEs, que incluye entre otros, IntelliJ, WebStorm o Android Studio proporciona nuevas entradas para acceder directamente a mandatos IDT CLI desde dentro del IDE. Le permite acceder rápidamente a un subconjunto de mandatos de `ibmcloud dev` para ambos flujos de trabajo de Docker y CloudFoundry, incluyendo despliegue de apps, iniciar/detener/reiniciar apps en {{site.data.keyword.Bluemix_notm}}, visualización de los registros de app remoto, etc., todos sin la necesidad de dejar el contexto del editor.
{:shortdesc}

![Captura de pantalla de IBM Developer Tools ejecutándose dentro de un IDE de WebStorm.](jetbrains.png "Ejemplo de menú de IDT que se ejecuta dentro del ID de WebStorm")

## Dependencias
{: #dependencies}

Para utilizar la extensión de IBM Developer Tools para ID basados en Jetbrains, también necesitará tener instalado [IBM Cloud Developer Tools CLI](index.html) en su sistema.

## Instalación
{: #installation}

La forma más simple de instalar la extensión IBM Developers Tools para un IDE de Jetbrains, es ir a la página del [repositorio de GitHub de IDT de jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) y seguir las instrucciones.

## Uso
{: #usage}

Puede empezar con una app existente del lado del servidor, y habilitarla para IBM Cloud, o utilizar IDT CLI para crear una nueva app desde un kit de iniciación (ibmcloud dev create). Una vez haya creado su proyecto de app, ábralo en su IDE de JetBrains.

Si tiene una app genérica del lado del servidor, seleccione Herramientas > IBM Cloud Developer Tools > Habilitar app para IBM Cloud. Esto comprueba todos los archivos necesarios y añade los que faltan, lo que le permite compilar la app localmente, y desplegarla en IBM Cloud utilizando una app de Cloud Foundry, o en un clúster de Kubernetes.

Desarrolle su app nativa de nube utilizando las acciones básicas de compilar/ejecutar/desplegar desde el menú de IDT. Si necesita realizar acciones que no están en el menú, abra el separador Terminal y especifique los mandatos que quiere de forma manual.
