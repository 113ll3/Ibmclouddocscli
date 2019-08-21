---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools para IDE de JetBrains
{: #ibm-dev-tools-for-jetbrains}

La extensión de herramientas de desarrollador de {{site.data.keyword.cloud}} para IDE de JetBrains, que incluye `IntelliJ`, `WebStorm`, `Android Studio`, entre otros, proporciona nuevas entradas de menú para acceder directamente a mandatos {{site.data.keyword.dev_cli_notm}} CLI desde dentro del IDE. Puede acceder rápidamente a un subconjunto de mandatos de `ibmcloud dev` para ambos flujos de trabajo de Docker y Cloud Foundry, incluyendo despliegue de aplicaciones, iniciar/detener/reiniciar apps en {{site.data.keyword.cloud_notm}}, visualización de los registros de app remoto, etc. Todo ello sin tener que abandonar el contexto del editor.
{: shortdesc}

![Captura de pantalla de IBM Cloud Developer Tools ejecutándose dentro del IDE de WebStorm.](../images/jetbrains.png "Ejemplo de menú de herramientas de desarrollador de {{site.data.keyword.cloud_notm}} que se ejecuta dentro del IDE de WebStorm")

## Dependencias
{: #jetbrains-dependencies}

Para utilizar la extensión de herramientas de desarrollador de {{site.data.keyword.cloud_notm}} para los IDE basados en JetBrains, necesita tener la [CLI de {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-getting-started) instalada en el sistema.

## Instalación
{: #jetbrains-installation}

La mejor manera de instalar la extensión de herramientas del desarrollador de {{site.data.keyword.cloud_notm}} para el IDE de JetBrains consiste en ir a [página de JetBrains del repositorio GitHub de herramientas del desarrollador de {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y seguir las instrucciones.

## Uso
{: #jetbrains-usage}

Puede empezar con una app existente del lado de servidor y habilitarla para la nube, o bien utilizar la CLI de {{site.data.keyword.dev_cli_notm}} para crear una nueva app a partir de un kit de inicio (`ibmcloud dev create`). Cuando haya creado su proyecto de app, ábralo en su IDE de JetBrains.

Para habilitar para la nube una app genérica del lado del servidor, seleccione **Herramientas** > **Herramientas de desarrollador de IBM Cloud** > **Habilitar app para {{site.data.keyword.cloud_notm}}**. Se comprueban todos los archivos necesarios y se añaden (si es necesario) para el despliegue a {{site.data.keyword.cloud_notm}} utilizando una app de Cloud Foundry o dentro de un clúster Kubernetes.

Desarrolle su app nativa de nube utilizando las acciones básicas de compilar, ejecutar y desplegar desde el menú de herramientas de desarrollador de {{site.data.keyword.cloud_notm}}. Si necesita realizar acciones que no están en el menú, simplemente abra el separador de terminal y especifique los mandatos deseados de forma manual.
