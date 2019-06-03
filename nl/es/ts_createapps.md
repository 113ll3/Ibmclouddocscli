---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Resolución de problemas del plugin de CLI de herramientas del desarrollador de {{site.data.keyword.cloud_notm}}
{: #troubleshoot}

Consulte las soluciones a problemas comunes con la interfaz de línea de mandatos (CLI) de {{site.data.keyword.dev_cli_short}}. En muchos de los casos, puede solucionar estos problemas siguiendo unos sencillos pasos.
{: shortdesc}

## ¿Por qué recibo un error de nombre de host cuando creo una aplicación con un patrón no móvil?
{: #ts-cli-hostname-error}
{: troubleshoot}

Es posible que aparezca el siguiente error si utiliza la CLI de {{site.data.keyword.dev_cli_short}} para desplegar una aplicación en Cloud Foundry. Aunque especifique un nombre de host exclusivo, es posible que siga viendo el mensaje.
```
The hostname <myHostname> is taken.
```
{: screen}
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
{: #ts-cli-general-failures}
{: troubleshoot}

Es posible que se muestre el siguiente error si utiliza los mandatos `create`, `delete`, `list` o `code`:
```
Failed to <command> app.
```
{: screen}
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
{: #ts-cli-nosuchimage}
{: troubleshoot}

Cuando intenta ejecutar una app con `ibmcloud dev run` sin antes compilarla, es posible que se muestre el error siguiente.
```
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
{: screen}
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
{: #ts-cli-object-storage}
{: troubleshoot}

Es posible que se visualice el siguiente error si utiliza la CLI para crear dos apps con la función {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

Este error se debe al servicio {{site.data.keyword.objectstorageshort}}, que solo proporciona una instancia del plan gratuito de {{site.data.keyword.objectstorageshort}}.
{: tsCauses}

Seleccione otro plan.
{: tsResolve}

## ¿Por qué no se recupera mi código cuando creo una app?
{: #retrieve-code-error}
{: troubleshoot}

Es posible que se muestre el siguiente error cuando se utiliza la CLI para crear una app:
```
FAILED
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

Este error se debe a un tiempo de espera interno excedido.
{: tsCauses}

Utilice uno de los métodos siguientes para obtener el código:

* Ejecute el mandato siguiente:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Sustituya `<your-app-name>` por el nombre de app que haya especificado durante la creación de la app.

* Utilice la {{site.data.keyword.dev_console}}.

	1. Seleccione la [app](https://cloud.ibm.com/resources){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") en la {{site.data.keyword.dev_console}}.

	2. Pulse **Descargar código**.
{: tsResolve}

## ¿Por qué no puedo ejecutar el mandato `ibmcloud dev run` para las apps Node.js?
{: #ts-cli-node}
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
{: screen}
{: tsSymptoms}

Este error se produce cuando el módulo `appmetrics` se ha instalado en otra arquitectura. Los módulos npm nativos instalados en una arquitectura no funcionan en otra. Las imágenes de Docker incluidas se basan en el kernel de Linux&trade;.
{: tsCauses}

Suprima la carpeta `node_modules` y ejecute de nuevo el mandato `ibmcloud dev run`.
{: tsResolve}

## ¿Por qué no puedo realizar el despliegue en {{site.data.keyword.cloud_notm}}?
{: #ts-cli-deploy-issues}
{: troubleshoot}

Se produce una anomalía cuando intenta realizar el despliegue en {{site.data.keyword.cloud_notm}}, pero no se muestra ningún error.
{: tsSymptoms}

Es posible que no haya iniciado una sesión con su cuenta.
{: tsCauses}

Ejecute el mandato siguiente para iniciar la sesión y vuelva a intentarlo.
```
ibmcloud login
```
{: tsResolve}

## ¿Por qué no puedo realizar el despliegue en Kubernetes en {{site.data.keyword.cloud_notm}}?
{: #ts-cli-kube-deploy}
{: troubleshoot}

Se podría visualizar la siguiente anomalía después de que se le solicitase el nombre de su clúster:
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

La causa más probable del problema es que el nombre del clúster no sea válido. Lo puede confirmar ejecutando el mismo mandato con `--trace`. Los siguientes detalles podría incluirse en la salida del error:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Asegúrese de que utiliza el clúster correcto y de que está configurado para el despliegue ejecutando:
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## ¿Por qué no puedo desplegar un destino de imagen?
{: #ts-deploy-image-target}
{: troubleshoot}

Se podría visualizar la siguiente anomalía después de que se le solicite el destino de imagen de despliegue:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

La causa más probable del problema es que el destino de la imagen del despliegue no sea válido. Más concretamente, el espacio de nombres, que es el valor de en medio del destino de imagen de despliegue, podría no ser válido.
{: tsCauses}

Asegúrese de que el espacio de nombres en el destino de la imagen de despliegue coincida con uno de los espacios de nombres que se muestran cuando ejecuta el siguiente mandato:
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## ¿Por qué no se puede determinar el idioma de mi app?
{: #ts-cli-determine-language}
{: troubleshoot}

Es posible que se muestre el siguiente error al iniciar la app:
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app
directly. 
```
{: screen}
{: tsSymptoms}

Este error puede deberse a una de las causas siguientes:
- Se ha ejecutado el mandato [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) desde un directorio que no es el directorio de origen de la app.
- Se ha ejecutado el mandato [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) para una app de un idioma que no se reconoce.
{: tsCauses}

Asegúrese de ejecutar el mandato desde el directorio de la app que contiene el código fuente de la app. Si el problema no se soluciona y el idioma es uno de los [idiomas soportados](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options), utilice el parámetro `--language` para especificar el idioma.
{: tsResolve}

## ¿Por qué no puedo crear o ejecutar una app que está habilitada para el despliegue en la nube?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

Es posible que se produzcan varias anomalías al [crear](/docs/cli/idt?topic=cloud-cli-idt-cli#build) o [ejecutar](/docs/cli/idt?topic=cloud-cli-idt-cli#run) una app que se ha habilitado para el despliegue en la nube.
{: tsSymptoms}

En los siguientes enlaces encontrará muchas de las posibles causas.
{: tsCauses}

- Para obtener más información sobre cómo resolver estos problemas con una app Spring, consulte [Habilitación de apps Spring Boot existentes para el despliegue en la nube](/docs/java-spring?topic=java-spring-enable_existing#enable_existing).
- Para obtener más información sobre cómo resolver estos problemas con una app `Node.js`, consulte [Habilitación de apps Node.js existentes para el despliegue en la nube](/docs/node?topic=nodejs-enable_existing#enable_existing).
{: tsResolve}

## Cómo instalar manualmente los componentes de la CLI de {{site.data.keyword.dev_cli_notm}} de forma independiente
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

Para instalar manualmente los componentes de la CLI de {{site.data.keyword.dev_cli_notm}} de manera independiente, puede seguir estos
[pasos](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).

## ¿Por qué no puedo crear la imagen de Docker?
{: $ts-cli-docker}
{: troubleshoot}

Si aparece el error siguiente: 
```
FAILED
An error exit status 1 was encountered while building the Docker
image.
```
{: screen}

Este error puede deberse a una de las causas siguientes:
- Docker no está instalado.
- El daemon de Docker no está en ejecución.
{: tsCauses}

Asegúrese de que Docker está instalado y en ejecución:
- Para instalar o iniciar [Docker for Mac](https://docs.docker.com/docker-for-mac/install/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")
- Para instalar o iniciar [Docker for Windows&trade;](https://docs.docker.com/docker-for-windows/install/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")
- Para instalar o iniciar [Docker for Linux&trade;](https://docs.docker.com/v17.12/install/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")
{: tsResolve}

## ¿Cómo resolver la incompatibilidad de versiones de Helm?
{: ts-cli-helm}
{: troubleshoot}

Si las versiones de Helm de cliente y servidor no están sincronizadas, es posible que aparezcan los errores siguientes:
```
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED:
configmaps is forbidden: User "system:serviceaccount:kube-system:default"
cannot list resource "configmaps" in API group "" in the namespace
"kube-system"
```
{: screen}

```
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

Para resolver el problema, establezca la versión del cliente en la misma que la versión del clúster. Por ejemplo, para instalar la versión de Helm 2.8.1, ejecute los mandatos siguientes:
{: tsResolve}

* Para Mac y Linux&trade;, ejecute los mandatos siguientes:
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* Para Windows&trade;: como administrador, descargue e instale el binario de `helm` de [https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").
  
  Desde el terminal PowerShell, utilice los mandatos siguientes:
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```
  {: codeblock}

## ¿Por qué falla ibmcloud dev build con un nombre de usuario que incluye "@"?
{: ts-cli-username}
{: troubleshoot}
Durante el proceso de creación de la imagen, se utiliza su nombre de usuario para el usuario de la imagen de las herramientas de Docker. Si el nombre de usuario contiene caracteres especiales como '@' o '-', el proceso de creación de la imagen de Docker falla y con el error siguiente:
```
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Dumping output from the command:
```
{: screen}

Para resolver el problema, cambie su nombre de usuario para que no incluya ningún carácter especial, o especifique el distintivo siguiente para utilizar el usuario root en su lugar:
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
