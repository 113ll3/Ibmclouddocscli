---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Preguntas más frecuentes (FAQ)
{: #ibm-cli-faq}

## ¿Cuál es la estructura de archivos de las aplicaciones de {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Las aplicaciones que se crean o habilitan desde la CLI vienen con valores preconfigurados encapsulados en el archivo `cli-config.yml`. `cli-config.yml` contiene entradas predeterminadas que utilizan los mandatos de la CLI que pueden sustituirse por valores que se pasan a través de la línea de mandatos.

Las aplicaciones que se hayan desplegado en una cadena de herramientas de DevOps también pueden contener archivos como `toolchain.yml` y `pipeline.yml`. Las aplicaciones que se desplieguen manualmente pueden contener un archivo `manifest.yml` y archivos de diagrama de Helm (para el despliegue en Cloud Foundry o Kubernetes, por ejemplo).

## ¿Cómo se utilizan los contenedores locales?
{: #cli-faq-containers}

El plugin de CLI de {{site.data.keyword.dev_cli_long}} utiliza dos contenedores para facilitar la creación y la realización de pruebas de su aplicación. El primero es el contenedor de herramientas que contiene los programas de utilidad necesarios para crear y probar la aplicación. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Podría considerarlo como un contenedor de desarrollo, ya que contiene las herramientas que normalmente se utilizan para el desarrollo de un tiempo de ejecución concreto.

El segundo contenedor es el contenedor de ejecución, que imita casi exactamente el entorno de tiempo de ejecución real de la app cuando se ha desplegado en la nube. El formato de este contenedor es adecuado para desplegarlo y utilizarlo en, por ejemplo, {{site.data.keyword.cloud_notm}}. Como resultado, se define un punto de entrada que inicia su aplicación. Al seleccionar ejecutar la aplicación a través del plugin de CLI de {{site.data.keyword.dev_cli_long}}, utiliza este contenedor. El `Dockerfile` correspondiente a este contenedor se define mediante el parámetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

# ¿Cómo despliego código existente?
Para desplegar un código base existente, siga estos pasos para [habilitar la app](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Blogs, vídeos y documentación de referencia
{: #cli-faq-reference}

### Blogs
{: #cli-blogs}

- [Despliegue en {{site.data.keyword.cloud_notm}} privado con el plugin de CLI de {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Despliegue en Kubernetes en {{site.data.keyword.cloud_notm}} con el plugin de CLI de {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Habilitar proyectos existentes para {{site.data.keyword.cloud_notm}} con el plugin de CLI de {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Vídeos
{: #cli-videos}

- [Cómo desplegar en Kubernetes en {{site.data.keyword.cloud_notm}} con el plugin de CLI de {{site.data.keyword.dev_cli_long}}](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [Cómo desplegar proyectos existentes en {{site.data.keyword.cloud_notm}} con el plugin de CLI de {{site.data.keyword.dev_cli_long}}](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Crear, depurar y desplegar una app Node.js con el plugin de CLI de {{site.data.keyword.dev_cli_long}} y VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Documentación y guías de aprendizaje
- [Despliegue continuo en Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Resolución de problemas del plugin de CLI de {{site.data.keyword.dev_cli_long}}](/docs/cli?topic=cloud-cli-troubleshoot)
- [Mandatos del plugin de CLI de {{site.data.keyword.dev_cli_long}} (ibmcloud dev)](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Depuración de aplicaciones locales para el plugin de CLI de {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-local-debug)

**Para notificar problemas o enviar comentarios, puede utilizar [el canal #developer-tools de Slack de {{site.data.keyword.cloud_notm}} Tech](https://ibm-cloud-tech.slack.com) - Solicite acceso al equipo [aquí](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**
