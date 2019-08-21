---

copyright:
   years: 2017, 2019
lastupdated: "2019-07-12"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer plugin cli, dev plugin commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Mandatos del plugin de CLI de {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Versión: 2.1.18
Publicación: 28 de marzo de 2019

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.cloud}} `bluemix` y
`bx` ahora son `ibmcloud`. Sin embargo, puede seguir utilizando los mandatos de CLI `bluemix` y `bx` hasta que se eliminen más adelante.
{: tip}

Utilice los mandatos de CLI de {{site.data.keyword.dev_cli_notm}} (`ibmcloud dev`) para crear una aplicación, gestionarla, desplegarla, depurarla y probarla.

Ejecute varios mandatos en una única sentencia de línea de mandatos mediante [mandatos compuestos](#compound).
{: tip}

## build
{: #build}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Compile su app con el mandato `build`. Los mandatos `test`, `debug` y `run` esperan encontrar una app compilada, de forma que deba ejecutar una operación `build` con anterioridad.

El elemento de configuración `build-cmd-debug` se utiliza para compilar la app para todos los usos, excepto para `run`. La app se compila para depuración especificando la opción de línea de mandatos `--debug`. El elemento de configuración `build-cmd-run` se utiliza al compilar la app para utilizarla con el mandato `run`.

Para compilar con varios contenedores, su app debe tener un archivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"), que se especifica en `cli-config.yml`, o bien puede utilizar el parámetro de mandato `dockerfile-tools` para proporcionar uno.

Ejecute el mandato siguiente en el directorio de app actual para empezar a crear:  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

Utilice el mandato `code` para descargar una app creada previamente con el código de plantilla de app y los archivos de configuración para {{site.data.keyword.cloud_notm}}. Puede utilizar este mandato cuando necesite extraer una segunda copia de una app.

Ejecute el mandato siguiente para descargar el código desde una app especificada.
```
ibmcloud dev code <appName>
```
{: codeblock}

## console
{: #console}

El mandato `console` abre en un navegador web la consola web de su app en {{site.data.keyword.cloud_notm}}. Puede ejecutar el mandato `ibmcloud dev console` desde la carpeta de su app. La CLI intenta encontrar una app coincidente en {{site.data.keyword.cloud_notm}} con el mismo ID de app que el directorio actual. Si el sistema no puede encontrar un nombre coincidente, en su lugar, abre el panel de control **Web y móvil** en {{site.data.keyword.cloud_notm}} en lugar de la app específica.

Puede proporcionar un nombre de app y, de esta forma, la CLI omitirá la coincidencia basada en el nombre de carpeta o app. En este caso, la CLI abrirá la consola de la app con el nombre que ha indicado en un navegador web.  

Ejecute el siguiente mandato para abrir un navegador web para la consola web de su app.
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

Cree una app que solicite toda la información, incluido el tipo de recurso, el lenguaje, el kit de inicio y las opciones de la cadena de herramientas de DevOps. Esto incluye IBM Cloud Foundry o Cloud Foundry Enterprise Environment y Kubernetes. La app se crea en el directorio actual.

Para crear una app en el directorio actual y para asociar servicios con ella, ejecute el mandato siguiente:
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede depurar la app a través del mandato `debug`. Primero es necesario completar una compilación con relación a la app utilizando el mandato build con el argumento `--debug`. Cuando se inicia el mandato `debug`, se inicia un contenedor que proporciona uno o varios puertos de depuración tal como se defina en el valor `container-port-map-debug` en cli-config.yml o tal como se especifique en la línea de mandatos. Conecte su herramienta de depuración preferida al puerto o puertos y podrá depurar su app como siempre.

En primer lugar, compile la app:
```
ibmcloud dev build --debug
```
{: codeblock}

Para empezar, ejecute el mandato siguiente en el directorio de apps actual para empezar a depurar:
```
ibmcloud dev debug
```
{: codeblock}

Para depurar, conecte la herramienta de depuración en el puerto especificado.

Para salir de la sesión de depuración, utilice `Control-C`.

### Parámetros del mandato debug
{: #debug-parameters}

Los siguientes parámetros son exclusivos del mandato `debug` y ayudan a depurar una app. Hay [más parámetros](#command-parameters) que se comparten con otros mandatos.

#### `container-port-map-debug`
{: #port-map-debug}

* Correlaciones de puertos para el puerto de depuración. El primer valor es el puerto que se utilizará en el sistema operativo del host, el segundo es el puerto del contenedor [`host-port:container-port`].
* Uso: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parámetro utilizado para generar código para DEBUG.
* Uso: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parámetro que se utiliza para especificar un mandato para iniciar debug en el contenedor de herramientas. Utilice este parámetro si `build-cmd-debug` inicia la app en depuración.
* Uso: `ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

Utilice el mandato `delete` para eliminar apps del espacio de {{site.data.keyword.cloud_notm}}. Puede ejecutar el mandato sin parámetros para listar las apps disponibles y seleccionar la app de la lista numerada para suprimirla. El código de app y los directorios no se eliminan del espacio de disco local.

Ejecute el mandato siguiente para suprimir la app de {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete [appName] [--force,-f]
```
{: codeblock}

Los servicios de {{site.data.keyword.cloud_notm}} no se eliminan.
{: note}


### Parámetros del mandato delete
{: #delete-command-parameters}

#### `force`
{: #delete-force}

* Parámetro que se utiliza opcionalmente para omitir la confirmación de solicitud para suprimir una aplicación
* Uso `ibmcloud dev delete [appName] --force`

## deploy
{: #deploy}

Una app se puede desplegar como un contenedor o una app de Cloud Foundry.

Antes de desplegar una app Cloud Foundry en {{site.data.keyword.cloud_notm}}, el archivo `manifest.yml` debe estar presente en su directorio raíz de la app.

Antes de desplegar una app como un contenedor, debe instalar localmente [Kubernetes](https://kubernetes.io/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y [Helm](https://github.com/helm/helm){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"). La versión del cliente de Helm no debe ser más reciente que la versión del servidor de Helm. Puede encontrar ambas versiones ejecutando `helm version`. Se recomienda que utilice v2.4.2 para la versión del cliente.

Para desplegar la app en Kubernetes, debe especificar `deploy-target` como `container` en `cli-config.yml` o utilizar el parámetro `-t container`.

Otros parámetros necesarios para configurar el despliegue de Kubernetes también se pueden especificar en `cli-config.yml` utilizando los argumentos de línea de mandatos. Si no define estos parámetros en `cli-config.yml`, debe desplegar con el parámetro
`-t container`. A continuación, se le solicitarán los demás valores.

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

En `cli-config.yml`, puede definir la ubicación de un diagrama de Helm en la propiedad `chart-path` y configurar `deploy-image-target` tal como se muestra en el ejemplo. En `cli-config.yml` se utiliza el elemento `deploy-image-target` en lugar de los elementos `repository` y `tag` en el archivo `chart/values.yml`. Para desplegar en {{site.data.keyword.cloud_notm}} concretamente, establezca el elemento de configuración `ibm-cluster` en el nombre del clúster de Kubernetes que ha creado en {{site.data.keyword.cloud_notm}}.

Ejecute el mandato siguiente en el directorio de app actual para crear la app:  
```
ibmcloud dev build
```
{: codeblock}

Ejecute el mandato siguiente en el directorio de app actual para desplegar la app:
```
ibmcloud dev deploy
```
{: codeblock}

### deploy en {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

Puede desplegar en un entorno {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment. Para ello, configure el entorno local para este entorno utilizando `ibmcloud target --cf` y, a continuación, seleccione el entorno correcto en la lista. Luego puede utilizar el mandato `deploy` como lo haría para {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### Parámetros del mandato deploy
{: #deploy-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `deploy` o actualizando el archivo `cli-config.yml` de la app directamente. Hay [más parámetros](#command-parameters) que se comparten con otros mandatos.

#### `chart-path`
{: #chart-path}

* Este parámetro se utiliza en el despliegue del contenedor para especificar la ubicación del diagrama Helm utilizado para el despliegue.
* Uso `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* El parámetro utilizado para indicar el tipo de despliegue a completar. El tipo de despliegue predeterminado es buildpack.
* Uso `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parámetro utilizado con un despliegue de contenedor como el nombre de la imagen de destino para el despliegue. El valor no debe incluir la versión. Por ejemplo: image-name:{version}, debido a que `deploy` incrementa y añade automáticamente la versión.
* Uso `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parámetro que define el nombre del clúster de Kubernetes para una despliegue de contenedor en {{site.data.keyword.cloud_notm}}.
* Uso `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Parámetro para definir el nombre de host de la app cuando se despliega en Cloud Foundry.
* Uso `ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* Parámetro para definir el dominio de la app cuando se despliega en Cloud Foundry.
* Uso `ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

El mandato `diag` se utiliza como un diagnóstico para visualizar la información de versión de las dependencias instaladas para la CLI de {{site.data.keyword.dev_cli_notm}}. Ejecutar `diag` resulta útil para determinar si faltan dependencias o para ayudar a depurar problemas.

Ejecute el mandato siguiente para visualizar las versiones de las dependencias instaladas:
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

Edite la app con opciones, como por ejemplo para conectarla con una app de {{site.data.keyword.cloud_notm}} existente, gestionar {{site.data.keyword.cloud_notm}} y su cadena de herramientas de {{site.data.keyword.cloud_notm}} que se despliega en {{site.data.keyword.cloud_notm}} Kubernetes, Cloud Foundry o Cloud Foundry Enterprise Environment. Si tiene una app local conectada a una app de {{site.data.keyword.cloud_notm}}, utilice `edit` para añadir nuevos servicios, conectar y desconectar los servicios existentes o eliminar servicios existentes de la cuenta. Además, puede crear o ver una cadena de herramientas de {{site.data.keyword.cloud_notm}} para la app. Ejecute el mandato siguiente en la raíz del directorio de la app:
```
ibmcloud dev edit
```
{: codeblock}

Si no dispone de servicios existentes en su cuenta, este mandato le muestra una lista de los grupos de servicios desde los que puede seleccionar un servicio para conectarse a su app.

Sin embargo, si tiene algún servicio existente en su cuenta, este mandato le muestra una lista de estos servicios y si cada servicio está conectado a la app o no.

* Un servicio conectado le proporciona opciones para desconectar el servicio de la app o para suprimir el servicio de su cuenta, lo que la desconecta de todas las apps.

* Un servicio desconectado le ofrece opciones para conectar ese servicio a su app o para suprimir el servicio de su cuenta. La conexión de un servicio existente también descarga archivos, como credenciales o código fuente.

También puede añadir un servicio a la app, donde se le guiará a través de solicitudes de selección de servicios para descargar archivos adicionales como archivos de credenciales o código fuente.

## enable
{: #enable}

Habilite una app existente para el despliegue de {{site.data.keyword.cloud_notm}}. El mandato `enable` intenta detectar automáticamente el lenguaje de una app existente y, a continuación, solicitar la información adicional necesaria. Los archivos se generan para ser utilizados para los contenedores Docker locales, el despliegue de Cloud Foundry, el despliegue de Cloud Foundry Enterprise Environment o el despliegue de contenedores Kubernetes. Todos los entornos de despliegue se pueden utilizar a través de un mandato
`deploy` manual o utilizando una cadena de herramientas de DevOps.

Con la sesión iniciada en {{site.data.keyword.cloud_notm}}, puede conectar esta app local a una app que ya esté en {{site.data.keyword.cloud_notm}} o crear una nueva app de {{site.data.keyword.cloud_notm}}. Para aprovechar las características de {{site.data.keyword.cloud_notm}}, como sus servicios y cadenas de herramientas de DevOps, se necesita una app en {{site.data.keyword.cloud_notm}}. Cuando se crea una app de {{site.data.keyword.cloud_notm}} para una app que se ha clonado de un repositorio Git, la app de {{site.data.keyword.cloud_notm}} incluirá este repositorio en su configuración. 

El mandato `enable` es una característica Beta. Si tiene problemas con el mandato `enable`, consulte el apartado sobre [resolución de problemas](/docs/cli?topic=cloud-cli-troubleshoot). En concreto, `enable` no está pensado para apps o entornos de trabajo móviles. Para apps complejas que generen varios activos desplegables, cada componente de la app se debe habilitar individualmente. 

Ejecute el mandato siguiente para habilitar una app existente en el directorio actual:
```
ibmcloud dev enable
```
{: codeblock}

La presencia de los archivos necesarios proporciona la detección del lenguaje de la app para una estructura de proyecto válida.  

* La presencia de un archivo `package.json` identifica una app Node.js.
* La presencia de un archivo `package.swift` identifica una app Swift.
* La presencia de un archivo `setup.py` o `requirements.txt` identifica una app Python.
* La presencia de un archivo `pom.xml` o `build.gradle` identifica una app Java&trade;.
	* La presencia de un archivo `pom.xml` identifica una app Maven.
	* La presencia de un archivo `build.gradle` identifica una app Gradle.

También puede modificar el lenguaje de la app detectado utilizando el argumento `--language`. Únicamente se da soporte a las apps válidas y completas. El mandato enable no modifica el código fuente.

### Opciones de lenguaje del mandato enable
{: #enable-language-options}

Las opciones de lenguaje incluyen:
* Node
* Swift
* Python
* Java EE (equivale a Java&trade; - Java&trade; EE)
* Java-mp (equivale a Java&trade; - Java&trade; MicroProfile)
* Java-spring (equivale a Java&trade; - Spring Framework)

Los archivos creados mediante el mandato `ibmcloud dev enable` se guardan con la extensión de archivo `.merge` si hay conflictos de nombres con archivos existentes en la carpeta de la app.

### Parámetros del mandato enable
{: #enable-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `enable` o actualizando el archivo `cli-config.yml` de la app directamente. Hay [más parámetros](#command-parameters) que se comparten con otros mandatos.

#### `language`
{: #enable-language}

* Parámetro utilizado para especificar el lenguaje de la app que se va a habilitar.
* Uso `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parámetro utilizado para forzar que se vuelva a habilitar una app ya habilitada.
* Uso `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Parámetro para evitar que se cree una app en {{site.data.keyword.cloud_notm}} y crear los archivos de habilitación localmente.
* Uso: `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

Obtiene las credenciales necesarias para la app para habilitar el uso de servicios conectados.

## help
{: #help}

De forma predeterminada, si no se pasa ninguna acción ni argumento, o si se proporciona la acción 'help', este mandato muestra un texto de ayuda general. La ayuda general mostrada incluye una descripción de los argumentos base, así como una lista de las acciones disponibles.  

Ejecute el siguiente mandato para visualizar la información de ayuda general:
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

Puede listar todas las apps de {{site.data.keyword.cloud_notm}} en un grupo de recursos.

Ejecute el mandato siguiente para listar las apps:
```
ibmcloud dev list
```
{: codeblock}

## pipeline-get
{: #pipeline-get}

Ver los detalles de un conducto.

```
ibmcloud dev pipeline-get [pipelineID] [--json]
```
{: codeblock}

### Parámetros del mandato pipeline-get
{: #pipeline-get-command-parameters}

#### `json`
{: #json-get}

* Parámetro que sirve para mostrar los detalles del conducto en formato JSON.
* Uso `ibmcloud dev pipeline-get [pipelineID] --json`

## pipeline-run
{: #pipeline-run}

Ejecutar un conducto.
```
ibmcloud dev pipeline-run [pipelineID] [--stage-id stageID] [--json] 
```
{: codeblock}

### Parámetros del mandato pipeline-run
{: #pipeline-run-command-parameters}

#### `stage-id`
{: #run-stage-id}

* Parámetro que se utiliza opcionalmente para seleccionar la etapa del conducto que se va a ejecutar
* Uso `ibmcloud dev pipeline-run [pipelineID] --stage-id [stageID]`

#### `json`
{: #json-run}

* Parámetro que sirve para mostrar los detalles de invocación del conducto en formato JSON.
* Uso `ibmcloud dev pipeline-run [pipelineID] --json`

## pipeline-log
{: #pipeline-log}

Ver los registros recientes del conducto mediante el mandato `pipeline-log`. 

* Si se especifica el ID del conducto como argumento, se muestran todos los registros de todos los trabajos de todas las etapas para dicho conducto.
* Si el distintivo de ID de etapa contiene información, los registros se filtran por dicha etapa en el conducto. 
* Si el ID de trabajo se especifica con el ID de etapa, los registros se limitan al trabajo de la etapa. 
* Si se especifica el ID de ejecución de trabajo junto con el ID de etapa y el ID de trabajo, se realiza una búsqueda entre todos los registros disponibles que coinciden con el ID de ejecución de trabajo especificado.

Uso:
```
ibmcloud dev pipeline-log [pipelineID] [--stage-id stageID] [--job-id jobID] [--job-exec-id jobExecutionID]
```
{: codeblock}

### Parámetros del mandato pipeline-log
{: #pipeline-log-command-parameters}

#### `stage-id`
{: #log-stage-id}

* Parámetro utilizado para filtrar los registros por el ID de etapa.
* Uso `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID]`

#### `job-id`
{: #job-id}

* Parámetro utilizado para filtrar los registros por el ID de trabajo.
* Necesita el distintivo `stage-id`.
* Uso `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID]`

#### `job-exec-id`
{: #job-exec-id}

* Parámetro utilizado para filtrar los registros por el ID de ejecución de trabajo.
* Necesita el distintivo `stage-id`.
* Necesita el distintivo `job-id`.
* Uso `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID] --job-exec-id [jobExecutionID]`

## pipeline-open
{: #pipeline-open}

Ver el URL correspondiente al conducto mediante el mandato `pipeline-open`. El mandato `pipeline-open` también abre el URL en el navegador predeterminado.
```
ibmcloud dev pipeline-open [pipelineID]
```
{: codeblock}

## run
{: #run}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede ejecutar la app mediante el mandato `run`. Se debe completar primero una compilación sobre la app utilizando el mandato `build`. Al ejecutar el mandato `run`, se inicia el contenedor de ejecución y expone los puertos tal y como se define en el parámetro `container-port-map`. El parámetro `run-cmd` se utiliza para invocar la app si el contenedor de ejecución `Dockerfile` no contiene un punto de entrada para completar este paso.

Para ejecutar con varios contenedores, su app debe contener un archivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"), que se especifica en `cli-config.yml`, o bien puede utilizar el parámetro de mandato `dockerfile-run` para proporcionar uno.

En primer lugar, compile la app:
```
ibmcloud dev build
```
{: codeblock}

Ejecute el mandato siguiente en el directorio de app actual para iniciar la app:
```
ibmcloud dev run
```
{: codeblock}

Para salir de la sesión, utilice `Control-C`.

### Parámetros del mandato run
{: #run-parameters}

Los siguientes parámetros son exclusivos del mandato `run` y ayudan a gestionar la app dentro del contenedor de ejecución. Hay [parámetros](#command-parameters) que se comparten con otros mandatos.

#### `container-name-run`
{: #container-name-run2}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev run --container-name-run [<appName>]`

#### `container-path-run`
{: #container-path-run}

* Ubicación en el contenedor para compartir en ejecución.
* Uso: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Ubicación en el sistema host para compartir en el contenedor en ejecución.
* Uso: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile para el contenedor de ejecución.
* Si desea ejecutar con varios contenedores, utilice un archivo Compose.
* Para utilizar varios archivos Compose, delimite la lista de nombres con signos de comillas dobles.
* Uso: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Uso: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Imagen para crear desde `dockerfile-run`.
* Uso: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parámetro utilizado para ejecutar código en el contenedor de ejecución. Utilice este parámetro si su imagen inicia la app.
* Uso: `ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede abrir el shell dentro del contenedor de herramientas o de ejecución con el mandato `shell`.

Mediante la ejecución del mandato siguiente:
```
ibmcloud dev shell
```
{: codeblock}

La CLI de {{site.data.keyword.dev_cli_short}} abre un shell interactivo en el contenedor docker de la app. El contenedor de destino predeterminado para el mandato de shell se define por el valor `container-shell-target` en el `config.yml`, donde los valores válidos son `run` o `tools`. Si este valor no está definido o si se especifica un valor no válido, de forma predeterminada el mandato `shell` tiene como objetivo el contenedor `tools`. El mandato de shell abre el contenedor en el directorio especificado por la instrucción `WORKDIR` en el Dockerfile correspondiente. Si `WORKDIR` no está en el Dockerfile, Dockerfile se utiliza la raíz del contenedor como el directorio de trabajo. Para obtener más información, consulte [esta referencia](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

Como alternativa, puede decidir pasar `run` o `tools` como argumento para el mandato de forma que el shell se abra y sirva para dicho contenedor. Asimismo, puede utilizar el parámetro `container-name` para pasar el nombre del contenedor en el que desea el shell. Sin embargo, este distintivo se reserva para cuando no haya contenedores en ejecución. Los argumentos `run` y `tools` son más flexibles y le permiten conmutar entre contenedores cuando se esté ejecutando uno. Por ejemplo, si el contenedor tools está en ejecución y ejecuta `ibmcloud dev shell run`, se detiene el contenedor `tools` y se inicia el contenedor `run`, y viceversa.

Si el contenedor `run` o `tools` de destino no está ya en ejecución al ejecutar el mandato `shell`, se inicia el contenedor de destino. Sin embargo, se cambiará el valor predeterminado `Cmd` o `Entrypoint` en el Dockerfile para iniciar directamente el shell en lugar de iniciar el proceso del servidor. Puede iniciar el contenedor `run` o `tools` y luego iniciar manualmente el servidor con sus propios mandatos arbitrarios o personalizados.

También puede especificar el shell que desee abrir mediante el parámetro `container-shell`. De forma predeterminada, se utiliza `/bin/sh`. Si prefiere utilizar el shell bash, especifique el valor `container-shell` para que sea `/bin/bash`; sin embargo, tenga en cuenta que este bash no está disponible automáticamente en todas las variantes de Linux&trade;.

Cualquier otro argumento adicional que pase al mandato más allá de los distintivos se analizará como si el mandato se ejecutase al abrir el shell. Si proporciona un mandato, el shell dentro del contenedor saldrá después de la ejecución del mandato y volverá al terminal.

Por ejemplo, puede ejecutar el mandato Linux &trade; `ls` dentro del contenedor shell invocando `ibmcloud dev shell tools ls`. También puede especificar distintivos para pasar a la ejecución del mandato shell delimitando los argumentos entre comillas como, por ejemplo, `ibmcloud dev shell "ls -la"`.

### Parámetros del mandato shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nombre del contenedor en el que desea utilizar el shell.
* Uso: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Especifica el shell a ejecutar dentro del contenedor (el predeterminado es /bin/sh).
* Uso: `ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede consultar el estado de los contenedores que utiliza la CLI de {{site.data.keyword.dev_cli_short}}, tal y como se define en `container-name-run` y `container-name-tools`.

Ejecute el mandato siguiente en el directorio de app actual para comprobar el estado del contenedor:
```
ibmcloud dev status
```
{: codeblock}

[Parámetros del mandato status](#command-parameters)

## stop
{: #stop}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede detener sus contenedores mediante el mandato `stop`.

Para detener las herramientas y ejecutar los contenedores tal como se define en el archivo `cli-config.yml`, ejecute:
```
ibmcloud dev stop
```
{: codeblock}

Para detener un contenedor que no está definido en el archivo `cli-config.yml`, puede especificar un parámetro de línea de mandatos adicional para sustituirlo. Si no se especifica ningún contenedor en el archivo `cli-config.yml` o en la línea de mandatos, el mandato stop vuelve.

### Parámetros del mandato stop
{: #stop-parameters}

Los parámetros siguientes se utilizan para el mandato `stop`. Hay [parámetros](#command-parameters) que se comparten con otros mandatos.

#### `container-name-run`
{: #container-name-run}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`
{: #container-name-tools}

* Nombre del contenedor de herramientas.
* Uso: `ibmcloud dev stop --container-name-tools [<appName>]`

## test
{: #test}

Si utiliza Windows&trade;, debe ejecutar Windows&trade; 10 Pro o posterior.

Puede probar la app a través del mandato `test`. Se debe completar primero una compilación sobre la app utilizando el mandato `build --debug`. A continuación, el contenedor de herramientas se utiliza para iniciar `test-cmd` para la app.

En primer lugar, compile la app:
```
ibmcloud dev build --debug
```
{: codeblock}

Ejecute el siguiente mandato para probar la app:
```
ibmcloud dev test
```
{: codeblock}

### Parámetros del mandato test
{: #test-parameters}

El siguiente parámetro es exclusivo del mandato `test`. Hay [parámetros](#command-parameters) que se comparten con otros mandatos.

#### `test-cmd`
{: #test-cmd}

* Parámetro que se utiliza para especificar un mandato para probar código en el contenedor de herramientas.
* Uso: `ibmcloud dev test --test-cmd /the/test/command`

## toolchain-delete
{: #toolchain-delete}

Suprimir una cadena de herramientas. Si no se proporciona ningún nombre de cadena de herramientas, puede seleccionar uno en una lista. La lista de cadenas de herramientas depende del grupo de recursos y de la región de destino actuales.

El grupo de recursos de destino se encuentra en la `clave de API de IBMCLOUD`. Para obtener más información, consulte [Establecimiento o visualización de la cuenta, la región o el grupo de recursos de destino](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target).
```
ibmcloud dev toolchain-delete [toolchainName] [--force,-f]
```
{: codeblock}

### Parámetros del mandato toolchain-delete
{: #toolchain-delete-command-parameters}

#### `force`
{: #force}

* Parámetro que se utiliza para omitir la confirmación de solicitud para suprimir una cadena de herramientas.
* Uso `ibmcloud dev toolchain-delete [toolchainName] --force`

## toolchain-get
{: #toolchain-get}

Ver los detalles de una cadena de herramientas. Si no se proporciona ningún nombre de cadena de herramientas, puede seleccionar uno en una lista. 

Utiliza el grupo de recursos de destino de la `clave de API de IBMCLOUD`. Para obtener más información, consulte [Establecimiento o visualización de la cuenta, la región o el grupo de recursos de destino](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target). Es posible que algunas cadenas de herramientas basadas en Cloud Foundry no sean compatibles con este mandato.
```
ibmcloud dev toolchain-get [toolchainName] [--json]
```
{: codeblock}

### Parámetros del mandato toolchain-get
{: #toolchain-get-command-parameters}

#### `json`
{: #json-toolchain-get}

* Parámetro que sirve para mostrar los detalles de la cadena de herramientas en formato JSON.
* Uso `ibmcloud dev toolchain-get [toolchainName] --json`.

## toolchain-open
{: #toolchain-open}

Ver el URL correspondiente a la cadena de herramientas mediante el mandato `toolchain-open`. El mandato `toolchain-open` también abre el URL en el navegador predeterminado. Si no se proporciona ningún nombre de cadena de herramientas, se proporciona una lista de cadenas de herramientas para que pueda seleccionar una.
```
ibmcloud dev toolchain-open [toolchainName]
```
{: codeblock}

## toolchains
{: #toolchains}

Visualice una lista de las cadenas de herramientas del grupo de recursos actual. 

Utiliza el grupo de recursos de destino de la `clave de API de IBMCLOUD`. Para obtener más información, consulte [Establecimiento o visualización de la cuenta, la región o el grupo de recursos de destino](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target). Es posible que algunas cadenas de herramientas basadas en Cloud Foundry no sean compatibles con este mandato.
```
ibmcloud dev toolchains [--json]
```
{: codeblock}

### Parámetros del mandato toolchains
{: #toolchains-command-parameters}

#### `json`
{: #json-toolchains}

* Parámetro que sirve para mostrar las cadenas de herramientas en formato JSON.
* Uso `ibmcloud dev toolchains --json`

## view
{: #view}

Visualice el URL en el que se despliega su app a través del mandato `view`. Ejecute este mandato en el directorio raíz de la app que desea visualizar. El mandato `view` también abre el URL en el navegador predeterminado.

Para las apps desplegadas en Cloud Foundry, el URL consta del nombre de host y el dominio de la app.

Para las apps desplegadas en Kubernetes, el URL consta de la dirección IP del nodo en el que se despliega y el puerto público. Si el mandato determina que la app se ha desplegado en Kubernetes, la herramienta CLI solicita confirmación. Si especifica que la app no se ha desplegado en Kubernetes, se muestra el URL de Cloud Foundry. Si esperaba que el mandato mostrase el URL de una app desplegada en Kubernetes, asegúrese de que `cli-config.yml` contiene una entrada para `chart-path` o proporciónela a través de la línea de mandatos tal como se muestra [aquí](#chart-path).

Ejecute el siguiente mandato para ver su app:
```
ibmcloud dev view
```
{: codeblock}

### Parámetros del mandato view
{: #view-parameters}

Los siguientes parámetros son exclusivos del mandato `view`.

#### `deploy-target`
{: #commands-deploy-target}

* Parámetro utilizado para indicar el tipo de despliegue para omitir la solicitud.
* Uso `ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* Parámetro que se utiliza para especificar que no se desea abrir el navegador.
* Uso: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Raíz de proyecto para añadir al URL de la app de Kubernetes y de Cloud Foundry.
* Uso: `ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parámetro que define el nombre del clúster de Kubernetes cuando se elige como destino un despliegue de contenedor.
* Uso `ibmcloud dev view --ibm-cluster [cluster-name]`

## Mandatos compuestos
{: #compound}

Puede ejecutar varios mandatos en una sentencia de línea de mandatos separando los mandatos de las herramientas de desarrollador de {{site.data.keyword.cloud_notm}} con el delimitador `/`. Se pueden utilizar otros distintivos de línea de mandatos después de especificar los mandatos compuestos. A continuación se muestran algunos ejemplos de mandatos compuestos:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Todos los distintivos deben estar al final del mandato y se aplicarán a todos los mandatos asociados a dicho distintivo. Utilizando
`ibmcloud dev build/deploy/view -t container --trace` como ejemplo, se aplica el distintivo `--trace` a los tres mandatos, pero `-t` solo es aplicable a los dos últimos mandatos, y no se aplica al mandato `build`.

Los mandatos siguientes se pueden utilizar con esta característica:
`build, debug, deploy, get-credentials, run, stop, test, view`

Si un mandato falla por algún motivo, los mandatos subsiguientes no se ejecutan.

Si hay más mandatos que sigan a `debug` o `run`, la ejecución continúa si `debug` o `run` son interrumpidos por cualquier forma que no sea interrumpir el proceso desde la ventana de terminal actual. Especifique `Control+C` para interrumpir el proceso y no ejecutar los mandatos siguientes. Por ejemplo, puede ejecutar `ibmcloud dev stop` desde otra ventana de terminal para detener el contenedor en ejecución y continuar la ejecución del siguiente mandato.

## Parámetros para build, debug, run y test
{: #command-parameters}

Los siguientes parámetros se pueden utilizar con los mandatos `build|debug|run|test` o actualizando directamente el archivo `cli-config.yml` de la app. Dispone de parámetros adicionales para los mandatos [`debug`](#debug-parameters) y [`run`](#run-parameters).

Los parámetros de mandatos especificados en la línea de mandatos tienen prioridad sobre la configuración `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Especifique el archivo `cli-config.yml` que se utilizará para un mandato.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev <run|status|stop> --container-name-run [<appName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Nombre del contenedor de herramientas.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<appName>]`

#### `host-path-tools`
{: #host-path-tools}

* Ubicación en el host para compartir para la compilación, depuración, pruebas.
* Uso: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Ubicación en el contenedor para compartir para la compilación, depuración, pruebas.
* Uso: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Correlaciones de puertos para el contenedor. El primer valor es el puerto que se utilizará en el sistema operativo del host, el segundo es el puerto del contenedor [`host-port:container-port`].
* Uso: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile para el contenedor de herramientas.
* Uso: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Imagen para crear desde `dockerfile-tools`.
* Uso: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilice esta opción para definir montajes entre el sistema host y el contenedor de ejecución.
* Los valores de `host-path-run` y `container-path-run` se insertan al principio de la lista.
* El procedimiento recomendado para evitar resultados inesperados es compilar y ejecutar utilizando los mismos valores de montaje.
* Uso: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilice esta opción para definir montajes entre el sistema host y el contenedor de herramientas.
* Los valores de `host-path-tools` y `container-path-tools` se insertan al principio de esta lista.* El procedimiento recomendado para evitar resultados inesperados es compilar y depurar utilizando los mismos valores de montaje.
* Uso: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parámetro que se utiliza para especificar un mandato para generar código para todos los usos menos DEBUG.
* Uso: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilice este parámetro para proporcionar una salida detallada.
* Uso: `ibmcloud dev <build|debug|run|test> --trace`
