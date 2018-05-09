---
copyright:
years: 2017, 2018
lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Mandatos de CLI (bx dev) de {{site.data.keyword.dev_cli_notm}}
{: #idt-cli}

Versión: 1.2.0
Release: 8 de marzo de 2018

Los siguientes mandatos de CLI (bx dev) {{site.data.keyword.dev_cli_notm}} sirven para crear un proyecto, desplegarlo, depurarlo y probarlo.

- [build](#build): Compila el proyecto en un contenedor local
- [code](#code): Descarga el código de un proyecto
- [console](#console): Abre la consola de IBM Cloud para un proyecto
- [create](#create): Crea un nuevo proyecto y proporciona la opción de añadir servicios
- [debug](#debug): Depura aplicaciones en un contenedor local
- [delete](#delete): Suprime proyectos de su espacio
- [deploy](#deploy): Despliega aplicaciones en IBM Cloud
- [enable](#enable): Añade archivos de IBM Cloud a un proyecto existente
- [get-credentials](#get-credentials): Obtiene las credenciales necesarias para el proyecto para habilitar el uso de los servicios enlazados
- [help](#help): Proporciona ayuda para la sintaxis y los argumentos de IDT
- [list](#list): Genera una lista de todos los proyectos de IBM Cloud en un espacio
- [run](#run): Ejecuta aplicaciones en un contenedor local
- [shell](#shell): Abre un shell en un contendedor local
- [status](#status): Comprueba el estado de contenedores utilizados por la interfaz de línea de mandatos (CLI)
- [stop](#stop): Detiene un contenedor
- [test](#test): Prueba la aplicación en un contenedor local
- [view](#view): Visualiza los URL desplegados de la app para pruebas y visualización
- [compound commands](#compound): Ejecuta varios mandatos en una sentencia de línea de mandatos



## build
{: #build}

Compile su aplicación con el mandato `build`. Los mandatos `test`, `debug` y `run` esperan encontrar un proyecto compilado, de forma que primero es necesario ejecutar con anterioridad una operación `build`.  

El elemento de configuración `build-cmd-debug` se utiliza para compilar la aplicación para todos los usos, excepto para `run`. La aplicación se compila para depuración especificando la opción de línea de mandatos `--debug`.  El elemento de configuración `build-cmd-run` se utiliza al compilar la aplicación para utilizarla con el mandato `run`.

Para compilar con varios contenedores, su proyecto debe contener un archivo [Compose](https://docs.docker.com/compose/overview/), que especificado en `cli-config.yml` o puede utilizar el parámetro de mandato `dockerfile-tools` para especificar uno. Consulte [Archivo Compose](/docs/apps/projects/compose_file.html) para obtener más información.

Ejecute el siguiente mandato en el directorio del proyecto actual para crear la aplicación:  

```
bx dev build [--debug]
```
{: codeblock}


[Parámetros del mandato build](#command-parameters)


## code
{: #code}

El mandato `code` sirve para descargar un proyecto creado con anterioridad con los archivos de configuración y el código de plantillas de aplicación para {{site.data.keyword.Bluemix_notm}}.  Esto es útil cuando necesita extraer una segunda copia de un proyecto que haya creado.

Ejecute el siguiente mandato para descargar el código de un proyecto específico.

```
bx dev code <projectName>
```
{: codeblock}


## console
{: #console}

El mandato `console` abre en un navegador web la consola web de su aplicación en IBM Cloud.  Ejecute el mandato `bx dev console` desde la carpeta de su proyecto. El mandato de CLI intenta encontrar un proyecto coincidente en IBM Cloud con el mismo ID de proyecto que el del directorio actual. Si el sistema no puede encontrar un nombre coincidente, en su lugar, abre el panel de control Web y móvil en IBM Cloud en lugar del proyecto específico.

Puede proporcionar un nombre de proyecto y, de esta forma, la CLI omitirá la coincidencia basada en el nombre de carpeta/aplicación. En este caso, la CLI abrirá la consola del proyecto con el nombre que ha indicado en un navegador web.  

Ejecute el siguiente mandato para abrir un navegador web para la consola web de su aplicación.

```
bx dev console [projectName]
```
{: codeblock}


## create
{: #create}

Crea un proyecto, solicitando toda la información, incluido el tipo de recurso, el lenguaje, el kit de iniciación y las opciones de las cadenas de herramientas de DevOps. El proyecto se crea en el directorio actual.

Para crear un proyecto en el directorio actual y asociar servicios a dicho proyecto, ejecute el mandato siguiente:

```
bx dev create
```
{: codeblock}


## debug
{: #debug}

Puede depurar la aplicación a través del mandato `debug`. Primero es necesario completar una compilación con relación al proyecto utilizando el mandato build con el argumento `--debug`. Cuando se inicia el mandato `debug`, se inicia un contenedor que proporciona uno o varios puertos de depuración tal como se defina en el valor `container-port-map-debug` en cli-config.yml o tal como se especifique en la línea de mandatos. Conecte su herramienta de depuración preferida al puerto o puertos y podrá depurar su aplicación como siempre.

En primer lugar, compile su proyecto:

```
bx dev build --debug
```
{: codeblock}

Para empezar, ejecute el siguiente mandato en el directorio del proyecto actual para depurar la aplicación:

```
bx dev debug
```
{: codeblock}

Para depurar, conecte la herramienta de depuración en el puerto especificado.

Para salir de la sesión de depuración, utilice `Control-C`.


### Parámetros del mandato debug
{: #debug-parameters}

Los siguientes parámetros son exclusivos del mandato `debug` y ayudan a depurar una aplicación. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `container-port-map-debug`
{: #port-map-debug}

* Correlaciones de puertos para el puerto de depuración. El primer valor es el puerto que se utilizará en el sistema operativo del host, el segundo es el puerto del contenedor [host-port:container-port].
* Uso: `bx dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parámetro utilizado para generar código para DEBUG.
* Uso: `bx dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parámetro que se utiliza para especificar un mandato para invocar debug en el contenedor de herramientas. Utilice este parámetro si `build-cmd-debug` inicia la aplicación en depuración.
* Uso: `bx dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Utilice el mandato `delete` para eliminar proyectos de su espacio {{site.data.keyword.Bluemix}}. Puede ejecutar el mandato sin parámetros para listar proyectos disponibles y seleccionar el proyecto de la lista numerada para suprimir. El código y los directorios del proyecto no se eliminan del espacio de disco local.

Ejecute el siguiente mandato para suprimir su proyecto de {{site.data.keyword.Bluemix}}:

```
bx dev delete <projectName>
```
{: codeblock}


**Nota:** Los servicios de {{site.data.keyword.Bluemix}} **no** se eliminan.


## deploy
{: #deploy}

Una aplicación se puede desplegar como un contenedor o una aplicación de Cloud Foundry.

Para desplegar como una aplicación Cloud Foundry en {{site.data.keyword.Bluemix}}, el archivo `manifest.yml` debe estar presente en su directorio raíz del proyecto.

Para desplegar una aplicación como un contenedor, debe instalar [Kubernetes](https://kubernetes.io/) y [Helm](https://github.com/kubernetes/helm) localmente. Asegúrese de que la versión del cliente Helm no es más reciente que la versión del servidor de Helm. Puede encontrar ambas versiones ejecutando `helm versión`. La versión recomendada del cliente es v2.4.2.

En `cli-config.yml`, puede elegir definir la ubicación de un diagrama de Helm en la propiedad `chart-path`. Establezca el elemento `deploy-target` en `container` y configure `deploy-image-target` tal como se muestra en el ejemplo. En `cli-config.yml` se utiliza el elemento `deploy-image-target` en lugar de los elementos `repository` y `tag` en el archivo `chart/values.yml`. Para desplegar específicamente en {{site.data.keyword.Bluemix}}, establezca el elemento de configuración `ibm-cluster` con el nombre del clúster Kubernetes creado en {{site.data.keyword.Bluemix}} tal como se describe en la [Guía de aprendizaje: Creación de clústeres](/docs/containers/cs_tutorials.html#cs_cluster_tutorial).

Para obtener más información sobre el suministro, la configuración y el despliegue en un clúster Kubernetes, consulte la guía de aprendizaje [Despliegue de aplicaciones web escalables en Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

Si no los define en cli-config.yml, debe desplegar con el parámetro `-t container` y se le solicitarán todos los otros parámetros.

Ejecute el siguiente mandato en el directorio del proyecto actual para crear la aplicación:  

```
bx dev build
```
{: codeblock}

Ejecute el siguiente mandato en el directorio del proyecto actual para desplegar su proyecto:

```
bx dev deploy
```
{: codeblock}


### Parámetros del mandato deploy
{: #deploy-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `deploy` o
actualizando directamente el archivo `cli-config.yml` del proyecto. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `chart-path`
{: #chart-path}

* Este parámetro se utiliza en el despliegue del contenedor para especificar la ubicación del diagrama Helm utilizado para el despliegue.
* Uso `bx dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* El parámetro opcional utilizado para indicar el tipo de despliegue a completar.  El tipo de despliegue predeterminado es buildpack.
* Uso `bx dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parámetro utilizado con un despliegue de contenedor como el nombre de la imagen de destino para el despliegue (por ejemplo para etiquetar un registro Docker).  El valor no debe incluir una versión, por ejemplo: image-name:{version} porque `deploy` la incrementa y añade de forma automática.
* Uso `bx dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parámetro opcional que define el nombre del clúster Kubernetes para una despliegue de contenedor en {{site.data.keyword.Bluemix}}.
* Uso `bx dev deploy --ibm-cluster [cluster-name]`


## enable
{: #enable}

Habilita un proyecto existente para el despliegue en {{site.data.keyword.Bluemix_notm}}. El mandato `enable` intenta detectar automáticamente el lenguaje de un proyecto existente y luego solicita la información adicional necesaria. Esto genera y añade archivos que pueden utilizarse para contenedores Docker locales, despliegues de CloudFoundry o despliegues de contenedores/Kubernetes.

Ejecute el siguiente mandato para habilitar un proyecto existente en el directorio actual para el despliegue en {{site.data.keyword.Bluemix_notm}}:

```
bx dev enable
```
{: codeblock}

La presencia de los archivos necesarios proporciona la detección del lenguaje de los proyectos con una estructura de proyecto válida.  

* La presencia del archivo `package.json` identifica un proyecto Node.js.
* La presencia del archivo `package.swift` identifica un proyecto Swift.
* La presencia del archivo `setup.py` o `requirements.txt` identifican un proyecto Python.
* La presencia del archivo `pom.xml` o `build.gradle` identifican un proyecto Java.
	* La presencia de un archivo `pom.xml` identifica un proyecto Maven.
	* La presencia de un archivo `build.gradle` identifica un proyecto Gradle.

De forma opcional, puede también modificar el lenguaje de proyecto detectado utilizando el argumento `--language`.  Sin embargo, únicamente se da soporte a proyectos completos y válidos. El mandato enable no modifica el código fuente.

Las opciones de lenguaje incluyen:
* nodo
* swift
* python
* java-ee (interpretado como Java - Java EE)
* java-mp (interpretado como Java - Java MicroProfile)
* java-spring (interpretado como Java - Spring Framework)

Los archivos creados mediante el mandato `bx dev enable` con conflictos de denominación con archivos existentes en la carpeta del proyecto se guardan con una extensión de archivo `.merge`.  

### Parámetros del mandato enable
{: #enable-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `enable` o actualizando directamente el archivo `cli-config.yml` del proyecto. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `language`
{: #enable-language}

* Este parámetro sirve para especificar el lenguaje del proyecto que se tiene que habilitar.
* Uso `bx dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parámetro utilizado para volver a forzar la habilitación de un proyecto que ya ha sido habilitado.
* Uso `bx dev enable -f|--force`


## get-credentials
{: #get-credentials}

Obtiene las credenciales necesarias para el proyecto para habilitar el uso de los servicios enlazados.


## help
{: #help}

De forma predeterminada, si no se pasa ninguna acción ni argumento, o si se proporciona la acción 'help', este mandato muestra un texto de ayuda general. La ayuda general mostrada incluye una descripción de los argumentos base, así como una lista de las acciones disponibles.  

Ejecute el siguiente mandato para visualizar la información de ayuda general:

```
bx dev help
```
{: codeblock}


## list
{: #list}

Sirve para listar todos los proyectos de {{site.data.keyword.Bluemix_notm}} en un espacio.

Ejecute el siguiente mandato para listar sus proyectos:

```
bx dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
bx dev edit
```
{: codeblock}
-->


## run
{: #run}

Puede ejecutar la aplicación mediante el mandato `run`. Se debe completar primero una compilación sobre el proyecto utilizando el mandato `build`. Al invocar el mandato `run`, se inicia el contenedor de ejecución y expone los puertos tal y como se define en el parámetro `container-port-map`. El parámetro `run-cmd` se puede utilizar para invocar la aplicación si el contenedor de ejecución Dockerfile no contiene un punto de entrada para completar este paso.

Para poder ejecutar varios contenedores, su proyecto debería contener un archivo [Compose](https://docs.docker.com/compose/overview/), especificado en `cli-config.yml` o bien debería utilizar el parámetro de mandato `dockerfile-run` para especificar uno. Consulte [Archivo Compose](/docs/apps/projects/compose_file.html) para obtener más información.

En primer lugar, compile su proyecto:

```
bx dev build
```
{: codeblock}

Ejecute el siguiente mandato en el directorio del proyecto actual para iniciar la aplicación:

```
bx dev run
```
{: codeblock}

Para salir de la sesión, utilice `Control-C`.


### Parámetros del mandato run
{: #run-parameters}

Los siguientes parámetros son exclusivos del mandato `run` y ayudan a gestionar la aplicación dentro del contenedor de ejecución.
Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `container-name-run`
{: #container-name-run}

* Nombre del contenedor de ejecución.
* Uso: `bx dev run --container-name-run [<projectName>]`

#### `container-path-run`
{: #container-path-run}

* Ubicación en el contenedor para compartir en ejecución.
* Uso: `bx dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Ubicación en el sistema host para compartir en el contenedor en ejecución.
* Uso: `bx dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile para el contenedor de ejecución.
* Si tiene prevista la ejecución con varios contenedores, este archivo debería ser un archivo Compose.
* Para utilizar varios archivos Compose, delimite con comillas dobles la lista de nombres.
* Uso: `bx dev run --dockerfile-run [/path/to/Dockerfile]`
* Uso: `bx dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Imagen para crear desde `dockerfile-run`.
* Uso: `bx dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parámetro utilizado para ejecutar código en el contenedor de ejecución. Utilice este parámetro si su imagen inicia la aplicación.
* Uso: `bx dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

Puede abrir el shell dentro del contenedor de herramientas o de ejecución con el mandato `shell`.

Simplemente ejecute este mandato

```
bx dev shell
```

la CLI de {{site.data.keyword.dev_cli_short}} abrirá un shell interactivo en el contenedor docker de la aplicación. El contenedor de destino predeterminado para el mandato de shell se define por el valor `container-shell-target` en el `config.yml`, donde los valores válidos son `run` o `tools`. Si este valor no está definido o si se especifica un valor no válido, de forma predeterminada el mandato `shell` afectará al contenedor `tools`. El mandato de shell abre el contenedor en el directorio especificado por la instrucción `WORKDIR` en el Dockerfile correspondiente. Si `WORKDIR` no está en el Dockerfile, Dockerfile se utiliza la raíz del contenedor como el directorio de trabajo. Consulte esta [información de referencia](https://docs.docker.com/engine/reference/builder/#workdir) para más detalles.

Como alternativa, puede decidir pasar `run` o `tools` como argumento para el mandato de forma que el shell se abra y sirva para dicho contenedor. Asimismo, puede utilizar el parámetro `container-name` para pasar el nombre del contenedor en el que desea el shell. Sin embargo, este distintivo debe reservarse para cuando no haya contenedores en ejecución. Los argumentos `run` y `tools` son más flexibles y permiten conmutar entre contenedores cuando alguno de ellos esté en ejecución. Por ejemplo, si el contenedor tools está en ejecución y ejecuta `bx dev shell run`, se detendrá el contenedor `tools` y se reiniciará el contenedor `run`, y viceversa.

Si el contenedor `run` o `tools` de destino no está ya en ejecución al ejecutar el mandato `shell`, se iniciará el contenedor de destino. Sin embargo, se cambiará el valor predeterminado `Cmd` o `Entrypoint` en el Dockerfile para iniciar directamente el shell en lugar de iniciar el proceso del servidor. Esto permite iniciar el contenedor `run` o `tools`, e iniciar manualmente el servidor con sus propios mandatos arbitrarios o personalizados.


También puede especificar el ejecutable del shell que desea abrir utilizando el parámetro `container-shell`. De forma predeterminada, se utiliza `/bin/sh`. Si prefiere utilizar el shell bash, especifique el valor `container-shell` para que sea `/bin/bash`; sin embargo, tenga en cuenta que este bash no está disponible automáticamente en todas las variantes de Linux.

Cualquier otro argumento adicional que pase al mandato más allá de los distintivos se analizarán como si el mandato se ejecutase al abrir el shell. Si proporciona un mandato para ejecutarlo, el shell dentro del contenedor saldrá después de la ejecución del mandato y volverá al terminal.

Por ejemplo, puede ejecutar el mandato Linux `ls` dentro del contenedor shell invocando `bx dev shell tools ls`.   También puede especificar distintivos adicionales para pasar a la ejecución del mandato del shell delimitando los argumentos entre comillas como, por ejemplo, `bx dev shell "ls -la"`.

### Parámetros del mandato shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nombre del contenedor en el que desea utilizar el shell.
* Uso: `bx dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Especifica el shell a ejecutar dentro del contenedor (el predeterminado es /bin/sh)
* Uso: `bx dev shell --container-shell [path/to/shell]`


## status
{: #status}

Puede consultar el estado de los contenedores que utiliza la CLI de {{site.data.keyword.dev_cli_short}}, tal y como se define en `container-name-run` y `container-name-tools`.

Ejecute el siguiente mandato en el directorio del proyecto actual para comprobar el estado de los contenedores:

```
bx dev status
```
{: codeblock}


[Parámetros del mandato status](#command-parameters)


## stop
{: #stop}

Puede detener sus contenedores mediante el mandato `stop`.

Para detener las herramientas y ejecutar los contenedores tal como se define en el archivo `cli-config.yml`, ejecute:

```
bx dev stop
```
{: codeblock}

Para detener un contenedor que no está definido en el archivo `cli-config.yml`, puede especificar un parámetro de línea de mandatos adicional para sustituirlo.  Si no se especifica ningún contenedor en el archivo `cli-config.yml` o en la línea de mandatos, el mandato stop vuelve.

### Parámetros del mandato stop
{: #stop-parameters}

Los parámetros siguientes se utilizan para el mandato `stop`. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `container-name-run`
{: #container-name-run}

* Nombre del contenedor de ejecución.
* Uso: `bx dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* Nombre del contenedor de herramientas.
* Uso: `bx dev stop --container-name-tools [<projectName>]`



## test
{: #test}

Puede probar la aplicación a través del mandato `test`. Se debe completar primero una compilación sobre el proyecto utilizando el mandato `build --debug`. A continuación, el contenedor de herramientas se utiliza para invocar `test-cmd` para la aplicación.

En primer lugar, compile su proyecto:

```
bx dev build --debug
```
{: codeblock}

Ejecute el siguiente mandato para probar la aplicación:

```
bx dev test
```
{: codeblock}


### Parámetros del mandato test
{: #test-parameters}

El siguiente parámetro es exclusivo del mandato `test`.  Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `test-cmd`
{: #test-cmd}

* Parámetro que se utiliza para especificar un mandato para probar código en el contenedor de herramientas.
* Uso: `bx dev test --test-cmd /the/test/command`


## view
{: #view}

Visualice el URL en el que se despliega su aplicación a través del mandato `view`. Ejecute este mandato en el directorio raíz de la aplicación que desea visualizar. El mandato `view` también abrirá el URL en el navegador predeterminado.

Para las aplicaciones desplegadas en Cloud Foundry, el URL consta del nombre de host y el dominio de la aplicación.

Para las aplicaciones desplegadas en Kubernetes, el URL consta de la dirección IP del nodo en que se despliega y el puerto público. Si el mandato determina que la app se desplegó en Kubernetes, la herramienta CLI solicitará confirmación. Si especifica que la aplicación realmente no se desplegó en Kubernetes, se muestra el URL de Cloud Foundry. Si esperaba que el mandato mostrase el URL de una aplicación desplegada en Kubernetes y esto no sucede, asegúrese de que `cli-config.yml` contiene una entrada para `chart-path` o proporciónela a través de la línea de mandatos tal como se muestra [aquí](#chart-path).

Ejecute el siguiente mandato para ver su aplicación:

```
bx dev view
```
{: codeblock}

### Parámetros del mandato view
{: #view-parameters}

Los siguientes parámetros son exclusivos del mandato `view`.

#### `deploy-target`

* Parámetro opcional utilizado para indicar el tipo de despliegue para omitir la solicitud
* Uso `bx dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Parámetro que se utiliza para especificar que no se desea abrir el navegador.
* Uso: `bx dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Raíz de proyecto para añadir al URL de la app de Kubernetes
* Uso: `bx dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster}

* Parámetro opcional que define el nombre el clúster Kubernetes en el que desplegar un contenedor.
* Uso `bx dev view --ibm-cluster [cluster-name]`


## Mandatos compuestos
{: #compound}

Ejecute varios mandatos en una sentencia de línea de mandatos separando los mandatos IDT con el delimitador `/`. Se pueden especificar distintivos de línea de mandatos adicionales después de especificar los mandatos compuestos.  A continuación se muestran algunos ejemplos de mandatos compuestos:

```
bx dev build/run
bx dev build/deploy --trace -t buildpack
bx dev build/debug --debug --trace
bx dev build/deploy/view -t container --trace
```
{: codeblock}

Todos los distintivos deben estar al final del mandato y se aplicarán a todos los mandatos asociados a dicho distintivo. En el ejemplo anterior, el distintivo `--trace` se aplica a los 3 mandatos, sin embargo, `-t` únicamente de aplica a los 2 últimos mandatos, de forma que no se aplicará al mandato `build`.

Los mandatos que se pueden utilizar con esta característica son:
`build, debug, deploy, get-credentials, run, stop, test, view`

Si un mandato falla por algún motivo, los mandatos subsiguientes no se ejecutarán. Si hay más mandatos que sigan a `debug` o `run`, la ejecución solo continuará si `debug` o `run` son interrumpidos por cualquier forma que no sea interrumpir el proceso desde la ventana de terminal actual. `Control+C` interrumpirá el proceso y los mandatos subsiguientes no se ejecutarán. Por ejemplo, puede ejecutar `bx dev stop` desde otra ventana de terminal para detener el contenedor en ejecución y continuar la ejecución del siguiente mandato.


## Parámetros para build, debug, run y test
{: #command-parameters}

Los siguientes parámetros se pueden utilizar con los mandatos `build|debug|run|test` o actualizando directamente el archivo `cli-config.yml` del proyecto. Dispone de parámetros adicionales para los mandatos [`debug`](#debug-parameters) y [`run`](#run-parameters).

**Nota**: Los parámetros de mandatos especificados en la línea de mandatos tienen prioridad sobre la configuración `cli-config.yml`.

#### `config-file`  
{: #config-file}

* Especifique un archivo cli-config.yml para utilizar con un mandato.
* Uso: `bx dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run}

* Nombre del contenedor de ejecución.
* Uso: `bx dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools}

* Nombre del contenedor de herramientas.
* Uso: `bx dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

#### `host-path-tools`
{: #host-path-tools}

* Ubicación en el host para compartir para la compilación, depuración, pruebas.
* Uso: `bx dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Ubicación en el contenedor para compartir para la compilación, depuración, pruebas.
* Uso: `bx dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Correlaciones de puertos para el contenedor. El primer valor es el puerto que se utilizará en el sistema operativo del host, el segundo es el puerto del contenedor [host-port:container-port].
* Uso: `bx dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile para el contenedor de herramientas.
* Uso: `bx dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Imagen para crear desde `dockerfile-tools`.
* Uso: `bx dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilice esta opción para definir montajes entre el sistema host y el contenedor de ejecución.
* Los valores de `host-path-run` y `container-path-run` se insertan al principio de la lista.
* El procedimiento recomendado para evitar resultados inesperados, es compilar y ejecutar utilizando los mismos valores de montaje.
* Uso: `bx dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilice esta opción para definir montajes entre el sistema host y el contenedor de herramientas.
* Los valores de `host-path-tools` y `container-path-tools` se insertan al principio de esta lista.* El procedimiento recomendado para evitar resultados inesperados, es compilar y depurar utilizando los mismos valores de montaje.
* Uso: `bx dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parámetro que se utiliza para especificar un mandato para generar código para todos los usos menos DEBUG.
* Uso: `bx dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilice este parámetro para proporcionar una salida detallada.
* Uso: `bx dev <build|debug|run|test> --trace`

