---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-30"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Resolución de problemas del plugin de CLI de herramientas del desarrollador de {{site.data.keyword.Bluemix_notm}}
{: #troubleshoot}

Los problemas más habituales al utilizar la interfaz de línea de mandatos (CLI) de {{site.data.keyword.dev_cli_short}} para crear apps pueden incluir anomalías en el despliegue o en el código que no es posible recuperar. En muchos de los casos, puede solucionar estos problemas siguiendo unos sencillos pasos.
{:shortdesc}

## ¿Por qué recibo un error de nombre de host cuando creo una app con un patrón no móvil?
{: #hostname-error}
{: troubleshoot}

Es posible que aparezca el siguiente error si utiliza la CLI de {{site.data.keyword.dev_cli_short}} para desplegar una app en Cloud Foundry. Aunque especifique un nombre de host exclusivo, es posible que siga viendo el mensaje.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Este error viene originado por una señal de inicio de sesión caducada.
{: tsCauses}

Vuelva a iniciar la sesión con el siguiente mandato:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## ¿Por qué se producen errores de mandatos generales?
{: #general}
{: troubleshoot}

Es posible que se muestre el siguiente error si utiliza los mandatos `create`, `delete`, `list` o `code`:

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

Este error viene originado por una señal de inicio de sesión caducada.
{: tsCauses}

Vuelva a iniciar la sesión con el siguiente mandato:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## ¿Por qué no se reconoce la imagen de mi nueva app?
{: #nosuchimage}
{: troubleshoot}

Cuando intenta ejecutar una app sin antes compilarla, es posible que se muestre el error siguiente.

```
$ ibmcloud dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: tsSymptoms}

Debe crear una app antes de ejecutarla. Ejecute el mandato siguiente en el directorio de la app actual:
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Ejecute el mandato siguiente en el directorio de app actual para iniciar la app:
```
ibmcloud dev run
```
{: tsResolve}

## ¿Por qué recibo un error de intermediario de servicio cuando añado la función {{site.data.keyword.objectstorageshort}}?
{: #os}
{: troubleshoot}

Es posible que se visualice el siguiente error si utiliza la CLI para crear dos apps con la función {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Este error se debe al servicio {{site.data.keyword.objectstorageshort}}, que solo proporciona una instancia del plan gratuito de {{site.data.keyword.objectstorageshort}}.
{: tsCauses}

Seleccione otro plan.
{: tsResolve}

## ¿Por qué no se recupera mi código cuando creo una app?
{: #code}
{: troubleshoot}

Es posible que se muestre el siguiente error cuando se utiliza la CLI para crear una app:

```
FAILED
Application created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Este error se debe a un tiempo de espera interno excedido.
{: tsCauses}

Utilice uno de los métodos siguientes para obtener el código:

* Ejecute el mandato siguiente:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Sustituya `<your-app-name>` por el nombre de la app que ha especificado durante la creación de la app.

* Utilice la {{site.data.keyword.dev_console}}.

	1. Seleccione la [app ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://console.bluemix.net/developer/appservice/apps) en la {{site.data.keyword.dev_console}}.

	2. Pulse **Descargar código**.
{: tsResolve}

## ¿Por qué no puedo ejecutar el mandato `ibmcloud dev run` para las apps Node.js?
{: #node}
{: troubleshoot}

Es posible que se muestre el siguiente error si ejecuta el mandato `ibmcloud dev run` para apps web Node.js o BFF:

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
{: tsSymptoms}

Este error se produce cuando el módulo `appmetrics` se ha instalado en otra arquitectura. Los módulos npm nativos instalados en una arquitectura no funcionan en otra. Las imágenes de Docker incluidas se basan en el kernel de Linux.
{: tsCauses}

Suprima la carpeta `node_modules` y ejecute de nuevo el mandato `ibmcloud dev run`.
{: tsResolve}

## ¿Por qué no puedo realizar el despliegue en {{site.data.keyword.Bluemix_notm}}?
{: troubleshoot}

Se produce una anomalía cuando intenta realizar el despliegue en {{site.data.keyword.Bluemix_notm}}, pero no se muestra ningún error.
{: tsSymptoms}

Es posible que no haya iniciado una sesión con su cuenta.
{: tsCauses}

Ejecute el mandato siguiente para iniciar la sesión y vuelva a intentarlo.
```
ibmcloud login
```
{: tsResolve}

## ¿Por qué no puedo realizar el despliegue en Kubernetes en {{site.data.keyword.Bluemix_notm}}?
{: troubleshoot}

Se podría visualizar la siguiente anomalía después de que se le solicitase el nombre de su clúster:
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

La causa más probable es que el nombre del clúster no sea válido. Lo puede confirmar ejecutando el mismo mandato con `-- trace`. Los siguientes detalles podría incluirse en la salida del error:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Asegúrese de que utiliza el clúster correcto y de que ha configurado el clúster para el despliegue ejecutando:
```
ibmcloud cs cluster-config <cluster-name>
```
{: tsResolve}

## ¿Por qué no puedo desplegar un destino de imagen?
{: troubleshoot}

Se podría visualizar la siguiente anomalía después de que se le solicitase el destino de imagen de despliegue:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

La causa más probable es que la imagen de destino de despliegue no sea válida. Más concretamente, el espacio de nombres, que se encuentra en medio en el destino de imagen de despliegue, podría no ser válido.
{: tsCauses}

Asegúrese de que el espacio de nombres en el destino de la imagen de despliegue coincide con uno de los espacios de nombres que se muestran cuando ejecuta el siguiente mandato:
```
ibmcloud cr namespaces
```
{: tsResolve}

## ¿Por qué no se puede determinar el idioma de mi app?
{: troubleshoot}

Es posible que se muestre el siguiente error al intentar iniciar la app:
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application
directly. 
```
{: tsSymptoms}

Este error puede deberse a una de las causas siguientes:
- Se ha ejecutado el mandato [enable](/docs/cli/idt/commands.html#enable) desde un directorio que no es el directorio de origen de la aplicación.
- Se ha ejecutado el mandato [enable](/docs/cli/idt/commands.html#enable) para una app de un idioma que no se reconoce en este momento.
{: tsCauses}

Asegúrese de ejecutar el mandato desde el directorio de la app que contiene el código fuente de la app. Si esto no resuelve el problema y el idioma es uno de los [idiomas soportados](/docs/cli/idt/commands.html#enable-language-options), utilice el parámetro `--language` para especificar el idioma.
{: tsResolve}

## ¿Por qué no puedo crear o ejecutar una app que se ha habilitado para el despliegue en la nube?
{: troubleshoot}

Es posible que se produzcan varias anomalías al intentar [crear](/docs/cli/idt/commands.html#build) o [ejecutar](/docs/cli/idt/commands.html#run) una app que se ha habilitado.
{: tsSymptoms}


En los siguientes enlaces encontrará muchas de las posibles causas.
{: tsCauses}

- Para obtener más información sobre cómo resolver estos problemas con una app Spring, consulte [Habilitación de aplicaciones Spring Boot existentes para el despliegue en la nube](/docs/java-spring/enable_existing.html#enable_existing).
- Para obtener más información sobre cómo resolver estos problemas con una app `Node.js`, consulte [Habilitación de aplicaciones Node.js existentes para el despliegue en la nube](/docs/node/enable_existing.html#enable_existing).
{: tsResolve}

## ¿Cómo se instalan manualmente las herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}}?
{: #appendix}
Todos los requisitos previos se instalan para la mayoría utilizando los instaladores de la plataforma. Si necesita instalar cualquier componente manualmente, aquí encontrará las instrucciones para cada uno.
Para instalar el plugin de desarrollo, primero debe instalar la [CLI de IBM Cloud](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use).
Para utilizar el propio plugin de desarrollo, debe instalarlo ejecutando el mandato siguiente: 
```
ibmcloud plugin install dev
```
{: codeblock}
 
Para ejecutar y depurar apps localmente, también debe instalar [Docker](https://www.docker.com/get-docker).
 
Para desplegar una app como contenedor, también debe instalar Kubernetes, Helm y los siguientes plugins de la CLI de IBM Cloud.
 
### Para instalar Kubernetes:
Usuarios de Mac:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Usuarios de Linux:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Usuarios de Windows:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### Para instalar Helm:
Usuarios de Mac y Linux:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Usuarios de Windows:
Descargue e instale el archivo [binario](https://github.com/kubernetes/helm/releases/tag/v2.7.2).

### Para instalar el plugin container-registry:
```
ibmcloud plugin install container-registry
```
{: codeblock}

### Para instalar el plugin container-service:
```
ibmcloud plugin install container-service
```
{: codeblock}
