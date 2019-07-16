---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Preguntas más frecuentes
{: #ibm-cli-faq}

## ¿Es obligatorio utilizar la última versión de la CLI de {{site.data.keyword.cloud_notm}}?
{: #cli-latest-version}

Sí, debe utilizar la versión más reciente. Puede comprobar la versión que está utilizando con el mandato siguiente:

```
ibmcloud -v
```
{: codeblock}

## Cómo actualizar la CLI
{: #cli-update-version}

Ejecute el mandato siguiente para actualizar a la versión más reciente de la CLI:

```
ibmcloud update
```
{: codeblock}

## ¿Cómo puedo hacer para que se me notifiquen los nuevos releases de la CLI?
{: #cli-get-notified}

Sí, para estar al día de los nuevos releases de la CLI y recibir notificaciones a medida que se encuentren disponibles, suscríbase al [repositorio de releases de la CLI de {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo")

## ¿Cuál es la estructura de archivos de las aplicaciones de {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Las aplicaciones que se crean o habilitan desde la CLI vienen con valores preconfigurados encapsulados en el archivo `cli-config.yml`. `cli-config.yml` contiene entradas predeterminadas que utilizan los mandatos de la CLI que pueden sustituirse por valores que se pasan a través de la línea de mandatos.

Las apps que se despliegan en una cadena de herramientas de DevOps también pueden contener archivos como `toolchain.yml` y `pipeline.yml`. Las apps que se desplieguen manualmente pueden contener un archivo `manifest.yml` y archivos de diagrama de Helm (para el despliegue en Cloud Foundry o Kubernetes, por ejemplo).

## ¿Cómo se utilizan los contenedores locales?
{: #cli-faq-containers}

El plugin de CLI de {{site.data.keyword.dev_cli_long}} utiliza dos contenedores para facilitar la creación y la realización de pruebas de su app. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la app. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Podría considerarlo como un contenedor de desarrollo, ya que contiene las herramientas que normalmente se utilizan para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución, que imita casi exactamente el entorno de tiempo de ejecución real de la app una vez que se ha desplegado en la nube. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.cloud_notm}}. Como resultado, se define un punto de entrada que inicia su app. Al seleccionar ejecutar la app a través del plugin de CLI de {{site.data.keyword.dev_cli_long}}, utiliza este contenedor. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

## ¿Cómo desplegar código existente?

Para desplegar una base de código existente, consulte [Generación de activos de habilitación de despliegue y de habilitación de la nube](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

