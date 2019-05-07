---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Preguntas más frecuentes
{: #ibm-cli-faq}

## ¿Estoy obligado a utilizar la última versión de la CLI de {{site.data.keyword.cloud_notm}}?
{: #cli-latest-version}

Sí, debe utilizar la versión más reciente. Puede comprobar la versión que está utilizando con el mandato siguiente:

```
ibmcloud -v
```
{: codeblock}

## ¿Cómo se actualiza la CLI?
{: #cli-update-version}

Ejecute el mandato siguiente para actualizar a la versión más reciente de la CLI:

```
ibmcloud update
```
{: codeblock}

## ¿Puedo recibir una notificación sobre los nuevos releases de la CLI?
{: #cli-get-notified}

Sí, se le pone al día sobre los nuevos releases de la CLI a medida que se encuentran disponibles. Suscríbase al [repositorio de releases de la CLI de {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo")

## ¿Cuál es la estructura de archivos de las aplicaciones de {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Las aplicaciones que se crean o habilitan desde la CLI vienen con valores preconfigurados encapsulados en el archivo `cli-config.yml`. `cli-config.yml` contiene entradas predeterminadas que utilizan los mandatos de la CLI que pueden sustituirse por valores que se pasan a través de la línea de mandatos.

Las aplicaciones que se hayan desplegado en una cadena de herramientas de DevOps también pueden contener archivos como `toolchain.yml` y `pipeline.yml`. Las aplicaciones que se desplieguen manualmente pueden contener un archivo `manifest.yml` y archivos de diagrama de Helm (para el despliegue en Cloud Foundry o Kubernetes, por ejemplo).

## ¿Cómo se utilizan los contenedores locales?
{: #cli-faq-containers}

El plugin de CLI de {{site.data.keyword.dev_cli_long}} utiliza dos contenedores para facilitar la creación y la realización de pruebas de su aplicación. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la aplicación. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Podría considerarlo como un contenedor de desarrollo, ya que contiene las herramientas que normalmente se utilizan para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución, que imita casi exactamente el entorno de tiempo de ejecución real de la app cuando se ha desplegado en la nube. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.cloud_notm}}. Como resultado, se define un punto de entrada que inicia su aplicación. Al seleccionar ejecutar la aplicación a través del plugin de CLI de {{site.data.keyword.dev_cli_long}}, utiliza este contenedor. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

## ¿Cómo despliego código existente?

Para desplegar una base de código existente, consulte [Generación de activos de habilitación de despliegue y de habilitación de la nube](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

