---

copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Jetbrains IDEs
{: #ibm-dev-tools-for-jetbrains}

La extensión de herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}} para Jetbrains IDEs, que incluye `IntelliJ`, `WebStorm`, `Android Studio`, entre otros, proporciona nuevas entradas de menú para acceder directamente a mandatos {{site.data.keyword.dev_cli_notm}} CLI desde dentro del IDE. Le permite acceder rápidamente a un subconjunto de mandatos de `ibmcloud dev` para ambos flujos de trabajo de Docker y CloudFoundry, incluyendo despliegue de apps, iniciar/detener/reiniciar apps en {{site.data.keyword.Bluemix_notm}}, visualización de los registros de app remoto, etc., todos sin la necesidad de dejar el contexto del editor.
{:shortdesc}

![Captura de pantalla de IBM Cloud Developer Tools ejecutándose dentro de un IDE de WebStorm.](jetbrains.png "Ejemplo de menú de herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}} que se ejecuta dentro del IDE de WebStorm")

## Dependencias
{: #dependencies}

Para utilizar la extensión de herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}} para IDE basados en Jetbrains, también necesitará tener instalada la [CLI de {{site.data.keyword.dev_cli_notm}}](index.html) en su sistema.

## Instalación
{: #installation}

La forma más sencilla de instalar la extensión de herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}} para un IDE de Jetbrains es ir a la página del [repositorio de Github de herramientas de desarrollador de jetbrains de {{site.data.keyword.Bluemix_notm}}](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) y seguir las instrucciones.

## Uso
{: #usage}

Puede empezar con una app existente del lado del servidor, y habilitarla para {{site.data.keyword.Bluemix_notm}}, o utilizar la CLI de {{site.data.keyword.dev_cli_notm}} para crear una nueva app desde un kit de inicio (ibmcloud dev create). Una vez haya creado su proyecto de app, ábralo en su IDE de JetBrains.

Si tiene una app genérica del lado del servidor, seleccione Herramientas > IBM Cloud Developer Tools > Habilitar app para IBM Cloud. Se comprobarán todos los archivos necesarios y se añadirán los que falten, lo que permitirá crear la app localmente, así como desplegarla en {{site.data.keyword.Bluemix_notm}} utilizando una app de Cloud Foundry, o dentro de un clúster de Kubernetes.

Desarrolle su app nativa de nube utilizando las acciones básicas de compilar/ejecutar/desplegar desde el menú de herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}}. Si necesita realizar acciones que no están en el menú, tan solo abra el separador Terminal y especifique los mandatos deseados de forma manual.
