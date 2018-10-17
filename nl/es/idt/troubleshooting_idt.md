---
copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Resolución de problema de IBM Cloud Developer Tools
{: #ts}

Se documentan algunos problemas conocidos con el {{site.data.keyword.dev_cli_notm}}, junto con sus soluciones temporales.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Problemas conocidos
{: #knownissues}

En las secciones siguientes se describen problemas conocidos y posibles soluciones.


### El nombre de host da un error cuando se crea un proyecto con un patrón no móvil
{: #hostname}

Es posible que le aparezca el siguiente error si utiliza {{site.data.keyword.dev_cli_short}} para crear un proyecto desde los patrones de app web, BFF o microservicio:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Causa
{: #hostname-cause}

Este error se debe a una señal de inicio de sesión caducada.


#### Resolución
{: #hostname-resolution}

Inicie de nuevo una sesión.

```
ibmcloud login
```
{: codeblock}


### Anomalías generales con {{site.data.keyword.dev_cli_short}}
{: #general}

Es posible que le aparezca el siguiente error si utiliza los mandatos crear, suprimir, listar o codificar de {{site.data.keyword.dev_cli_short}}:

```
Failed to <command> project.
```
{: codeblock}


#### Causa
{: #general-cause}

Este error se debe a una señal de inicio de sesión caducada.


#### Resolución
{: #general-resolution}

Inicie de nuevo una sesión.

```
ibmcloud login
```
{: codeblock}


### Error de que no existe la imagen cuando se ejecuta un proyecto nuevo
{: #nosuchimage}

Es posible que le aparezca el siguiente error cuando ejecute un proyecto sin compilarlo con anterioridad.

```
$ ibmcloud dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### Causa
{: #nosuchimage-cause}

Debe compilar un proyecto antes de ejecutarlo.


#### Resolución
{: #nosuchimage-resolution}

Ejecute el siguiente mandato en el directorio del proyecto actual para crear la aplicación:

```
ibmcloud dev build
```
{: codeblock}

Ejecute el siguiente mandato en el directorio del proyecto actual para iniciar la aplicación:

```
ibmcloud dev run
```


### Error de intermediario de servicio cuando se añade la prestación de {{site.data.keyword.objectstorageshort}}
{: #os}

Es posible que le aparezca el siguiente error si utiliza {{site.data.keyword.dev_cli_short}} para crear dos proyectos con la prestación {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Causa
{: #os-cause}

Este error se debe al servicio {{site.data.keyword.objectstorageshort}}, que solo proporciona una instancia del plan gratuito de {{site.data.keyword.objectstorageshort}}.


#### Resolución
{: #os-resolution}

Se le solicitará que elija otro plan para evitar este error.


### Erro al obtener el código durante la creación del proyecto
{: #code}

Es posible que le aparezca el siguiente error si utiliza {{site.data.keyword.dev_cli_short}} para crear un proyecto:

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### Causa
{: #code-cause}

Este error se debe a un tiempo de espera interno excedido.


#### Resolución
{: #code-resolution}

Puede obtener el código de una de las siguientes formas:

* Ejecute el siguiente mandato utilizando la CLI:

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   Sustituya `<your-project-name>` por el nombre del proyecto que ha especificado durante la creación del proyecto.

* Utilice la {{site.data.keyword.dev_console}}.

	1. Seleccione el [proyecto ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://console.{DomainName}/developer/projects) en la {{site.data.keyword.dev_console}} y pulse **Obtener el código**.

	2. Pulse **Generar código**.

	3. Después de generar el código, pulse **Descargar código**.


### Error al ejecutar `ibmcloud dev run` para proyectos de Node.js
{: #node}

Es posible que le aparezca el siguiente error si ejecuta `ibmcloud dev run` con {{site.data.keyword.dev_cli_short}} para proyectos web o BFF de Node.js:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### Causa
{: #node-cause}

Este error se produce cuando el módulo `appmetrics` se ha instalado en otra arquitectura. Los módulos npm nativos instalados en una arquitectura no funcionan en otra. Las imágenes de Docker incluidas se basan en el kernel de Linux.


#### Resolución
{: #node-resolution}

Suprima la carpeta `node_modules` y vuelva a ejecutar `ibmcloud dev run`.


### Anomalía al desplegar en {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

Puede intentar desplegar en {{site.data.keyword.Bluemix_notm}} con la {{site.data.keyword.dev_cli_short}} y verá que no se realiza el despliegue en {{site.data.keyword.Bluemix_notm}}, pero tampoco aparece ningún error.


#### Causa
{: #cause1}

Puede ser debido a que no ha iniciado sesión en su cuenta.

#### Resolución
{: #resolution1}

Inicie la sesión y vuélvalo a intentar.

```
ibmcloud login
```


### Se ha producido una anomalía al desplegar en Kubernetes en {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploytokube}

Es posible que vea esta anomalía tras la solicitud inicial del nombre de clúster:

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### Causa
{: #cause2}

Probablemente se debe a un nombre de clúster no válido y puede confirmarse ejecutando el mismo mandato con `--trace` y puede verlo en la salida de error:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Resolución
{: #resolution2}

Asegúrese de que utiliza el clúster correcto y de que ha configurado el clúster para el despliegue ejecutando

```
ibmcloud cs cluster-config <cluster-name>
```


### Se ha producido una anomalía al desplegar en Kubernetes en {{site.data.keyword.Bluemix_notm}}

Puede que vea esta anomalía tras la solicitud del destino de imagen de despliegue:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### Causa
{: #cause3}

Lo más probable es que esto se deba a un destino de imagen de despliegue. Más concretamente, podría ser un espacio de nombre no válido, el valor medio del destino de imagen de despliegue


#### Resolución
{: #resolution3}

Asegúrese de que el espacio de nombres en el destino de imagen de despliegue coincide con uno de los espacios de nombres que se ha encontrado en la ejecución

```
ibmcloud cr namespaces
```



## APÉNDICE
{: #appendix}

Se han instalado todos los requisitos previos para la mayoría de los usuarios que están ejecutando los instaladores de la plataforma. Si necesita instalar cualquier componente manualmente, aquí encontrará las instrucciones:

Para instalar el plug-in de desarrollo, primero debe estar instalada la [CLI de IBM Cloud](../reference/bluemix_cli/get_started.md#getting-started).

Para utilizar el plug-in de desarrollo, debe instalarlo ejecutando el mandato siguiente: `ibmcloud plugin install dev -r Bluemix`

Para ejecutar y depurar aplicaciones localmente, también debe instalar [Docker ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://www.docker.com/get-docker).

Para desplegar una aplicación como un contenedor, también deberá instalar `Kubernetes`, `Helm` y los siguientes plug-ins de la CLI de IBM Cloud:

Para instalar Kubernetes:
* Usuarios de Mac:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Usuarios de Linux:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Usuarios de Windows:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Para instalar Helm:
* Usuarios de Mac y Linux:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Usuarios de Windows:
Descargue e instale el binario de https://github.com/kubernetes/helm/releases/tag/v2.6.0

Para instalar el plug-in container-registry:
`ibmcloud plugin install container-registry`

Para instalar el plug-in container-service:
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Obtención de ayuda y soporte
{: #gettinghelp}

Si tiene problemas o preguntas sobre la {{site.data.keyword.dev_console}} de {{site.data.keyword.Bluemix_notm}} o {{site.data.keyword.dev_cli_notm}}, obtenga ayuda buscando información o formulando preguntas a través de un foro. También puede abrir una incidencia de soporte.

Cuando publique en foros, puede etiquetar sus preguntas para que se notifique a los equipos de desarrollo de {{site.data.keyword.Bluemix_notm}}.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Si tiene preguntas técnicas sobre el desarrollo o el despliegue de una app con la {{site.data.keyword.dev_console}} o {{site.data.keyword.dev_cli_notm}}:

* Publique la pregunta en [Stack Overflow ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) y etiquete la pregunta con `bluemix-dev-services` e `ibm-bluemix`.
* Publique la pregunta en [Slack ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://ibm-cloud-tech.slack.com/) en el canal `bluemix-dev-services`. [Inicie sesión en ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://ibm.biz/IBMCloudNativeSlack) hoy mismo.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Consulte [Obtención de ayuda ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/support/index.html#getting-help) para obtener más información detallada sobre el uso de los foros.

Para obtener información sobre cómo abrir una incidencia de soporte de {{site.data.keyword.IBM}}, o sobre los niveles de soporte y gravedades de las incidencias, consulte [Cómo obtener soporte ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
