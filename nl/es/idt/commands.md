---

copyright:

   years: 2017, 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Mandatos del plug-in de CLI de {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Versión: 2.1.4
Release: 31 de agosto de 2018

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.Bluemix}} han cambiado de `bluemix` y `bx` a `ibmcloud`. Sin embargo, todavía puede utilizar los mandatos de CLI `bluemix` y `bx` hasta que se dejen de utilizar en una fecha posterior.
{: tip}

Utilice los siguientes mandatos de CLI de {{site.data.keyword.dev_cli_notm}} (ibmcloud dev) para crear una aplicación, gestionarla, desplegarla, depurarla y probarla.

- [build](#build): Compilar la aplicación en un contenedor local
- [code](#code): Descargar el código para una aplicación
- [console](#console): Abre la consola de IBM Cloud para una aplicación
- [create](#create): Crea una aplicación nueva y le ofrece la opción de añadir servicios
- [debug](#debug): Depura aplicaciones en un contenedor local
- [delete](#delete): Suprime una aplicación del espacio
- [deploy](#deploy): Despliega aplicaciones en IBM Cloud
- [diag](#diag): Muestra información de versión sobre las dependencias instaladas
- [edit](#edit): Añadir o eliminar servicios desde una aplicación existente
- [enable](#enable): Actualizar una aplicación existente para utilizarla con IBM Cloud Developer Tools
- [get-credentials](#get-credentials): Obtiene las credenciales que necesita la aplicación para habilitar el uso de los servicios de IBM Cloud conectados
- [help](#help): Ayuda sobre la sintaxis y los argumentos de la CLI
- [list](#list): Listar todas las aplicaciones de IBM Cloud en un grupo de recursos
- [run](#run): Ejecuta aplicaciones en un contenedor local
- [shell](#shell): Abre un shell en un contendedor local
- [status](#status): Comprueba el estado de contenedores utilizados por la interfaz de línea de mandatos (CLI)
- [stop](#stop): Detiene un contenedor
- [test](#test): Prueba la aplicación en un contenedor local
- [view](#view): Ver el URL desplegado de la aplicación para pruebas y visualización
- [mandatos compuestos](#compound): Ejecutar varios mandatos en una única sentencia de línea de mandatos



## build
{: #build}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Compile su aplicación con el mandato `build`. Los mandatos `test`, `debug` y `run` esperan encontrar una aplicación compilada, de forma que deba ejecutar una operación `build` con anterioridad.  

El elemento de configuración `build-cmd-debug` se utiliza para compilar la aplicación para todos los usos, excepto para `run`. La aplicación se compila para depuración especificando la opción de línea de mandatos `--debug`.  El elemento de configuración `build-cmd-run` se utiliza al compilar la aplicación para utilizarla con el mandato `run`.

Para compilar con varios contenedores, su aplicación debe contener un archivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"), que se especifica en `cli-config.yml`, o bien puede utilizar el parámetro de mandato `dockerfile-tools` para proporcionar uno. Consulte [Archivo Compose](/docs/apps/projects/compose_file.html) para obtener más información.

Ejecute el mandato siguiente en el directorio de aplicación actual para crear la aplicación:  

```
ibmcloud dev build [--debug]
```
{: codeblock}



## code
{: #code}

Utilice el mandato `code` para descargar una aplicación creada previamente con el código de plantilla de aplicación y los archivos de configuración para {{site.data.keyword.Bluemix_notm}}.  Esto es útil cuando necesita extraer una segunda copia de una aplicación que haya creado.

Ejecute el mandato siguiente para descargar el código desde una aplicación especificada.

```
ibmcloud dev code <applicationName>
```
{: codeblock}


## console
{: #console}

El mandato `console` abre en un navegador web la consola web de su aplicación en IBM Cloud.  Puede ejecutar el mandato `ibmcloud dev console` desde la carpeta de su aplicación. El mandato de CLI intenta encontrar una aplicación coincidente en IBM Cloud con el mismo ID de aplicación que el directorio actual. Si el sistema no puede encontrar un nombre coincidente, en su lugar, abre el panel de control Web y móvil en IBM Cloud en lugar de la aplicación específica.

Puede proporcionar un nombre de aplicación y, de esta forma, la CLI omitirá la coincidencia basada en el nombre de carpeta/aplicación. En este caso, la CLI abrirá la consola de la aplicación con el nombre que ha indicado en un navegador web.  

Ejecute el siguiente mandato para abrir un navegador web para la consola web de su aplicación.

```
ibmcloud dev console [applicationName]
```
{: codeblock}


## create
{: #create}

Cree una aplicación, solicitando toda la información, incluido el tipo de recurso, el idioma, el kit de inicio y las opciones de la cadena de herramientas de DevOps. La aplicación se crea en el directorio actual.

Para crear una aplicación en el directorio actual y para asociar servicios con ella, ejecute el mandato siguiente:

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede depurar la aplicación a través del mandato `debug`. Primero es necesario completar una compilación con relación a la aplicación utilizando el mandato build con el argumento `--debug`. Cuando se inicia el mandato `debug`, se inicia un contenedor que proporciona uno o varios puertos de depuración tal como se defina en el valor `container-port-map-debug` en cli-config.yml o tal como se especifique en la línea de mandatos. Conecte su herramienta de depuración preferida al puerto o puertos y podrá depurar su aplicación como siempre.

En primer lugar, compile la aplicación:

```
ibmcloud dev build --debug
```
{: codeblock}

Para empezar, ejecute el mandato siguiente en el directorio de aplicaciones actual para depurar la aplicación:

```
ibmcloud dev debug
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
* Uso: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parámetro utilizado para generar código para DEBUG.
* Uso: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parámetro que se utiliza para especificar un mandato para invocar debug en el contenedor de herramientas. Utilice este parámetro si `build-cmd-debug` inicia la aplicación en depuración.
* Uso: `ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Utilice el mandato `delete` para eliminar aplicaciones del espacio de {{site.data.keyword.Bluemix_notm}}. Puede ejecutar el mandato sin parámetros para listar las aplicaciones disponibles y seleccionar la aplicación de la lista numerada para suprimirla. El código de aplicación y los directorios no se eliminan del espacio de disco local.

Ejecute el mandato siguiente para suprimir la aplicación de {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud dev delete <applicationName>
```
{: codeblock}


Los servicios de {{site.data.keyword.Bluemix_notm}} **no** se eliminan.
{: note}

## deploy
{: #deploy}

Una aplicación se puede desplegar como un contenedor o una aplicación de Cloud Foundry.

Antes de desplegar como una aplicación Cloud Foundry en {{site.data.keyword.Bluemix_notm}}, el archivo `manifest.yml` debe estar presente en su directorio raíz de la aplicación.

Antes de desplegar una aplicación como un contenedor, debe instalar localmente [Kubernetes](https://kubernetes.io/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y [Helm](https://github.com/kubernetes/helm){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"). Asegúrese de que la versión del cliente Helm no es más reciente que la versión del servidor de Helm. Puede encontrar ambas versiones ejecutando `helm versión`. La versión recomendada del cliente es v2.4.2.

Para desplegar la aplicación en Kubernetes, debe especificar `deploy-target` como `container` en `cli-config.yml` o utilizar el parámetro `-t container`.

Otros parámetros necesarios para configurar el despliegue de Kubernetes también se pueden especificar en `cli-config.yml` tal como se ve a continuación o utilizando los argumentos de línea de mandatos. Si no los define en `cli-config.yml`, debe desplegar con el parámetro `-t container` y se le solicitarán el resto de los valores.

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

En `cli-config.yml`, puede elegir definir la ubicación de un diagrama de Helm en la propiedad `chart-path` y configurar `deploy-image-target` tal como se muestra en el ejemplo. En `cli-config.yml` se utiliza el elemento `deploy-image-target` en lugar de los elementos `repository` y `tag` en el archivo `chart/values.yml`. Para desplegar en {{site.data.keyword.Bluemix_notm}} concretamente, establezca el elemento de configuración `ibm-cluster` en el nombre del clúster de Kubernetes que ha creado en {{site.data.keyword.Bluemix_notm}}.


Ejecute el mandato siguiente en el directorio de aplicación actual para crear la aplicación:  

```
ibmcloud dev build
```
{: codeblock}

Ejecute el mandato siguiente en el directorio de aplicación actual para desplegar la aplicación:

```
ibmcloud dev deploy
```
{: codeblock}


### Parámetros del mandato deploy
{: #deploy-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `deploy` o actualizando el archivo `cli-config.yml` de la aplicación directamente. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `chart-path`
{: #chart-path}

* Este parámetro se utiliza en el despliegue del contenedor para especificar la ubicación del diagrama Helm utilizado para el despliegue.
* Uso `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* El parámetro opcional utilizado para indicar el tipo de despliegue a completar.  El tipo de despliegue predeterminado es buildpack.
* Uso `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parámetro utilizado con un despliegue de contenedor como el nombre de la imagen de destino para el despliegue (por ejemplo para etiquetar un registro Docker).  El valor no debe incluir una versión, por ejemplo: image-name:{version} porque `deploy` la incrementa y añade de forma automática.
* Uso `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parámetro opcional que define el nombre del clúster Kubernetes para una despliegue de contenedor en {{site.data.keyword.Bluemix_notm}}.
* Uso `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Parámetro opcional que define el nombre de host de la aplicación cuando se despliega en Cloud Foundry
* Uso `ibmcloud dev deploy --host [hostname]`

#### `dominio`
{: #domain}

* Parámetro opcional para definir el dominio de la aplicación cuando se despliega en Cloud Foundry
* Uso `ibmcloud dev deploy --domain [domain]`


## diag
{: #diag}

Este mandato se utiliza como un diagnóstico para visualizar la información de versión de las dependencias instaladas para la CLI de {{site.data.keyword.dev_cli_notm}}. Esto resultará especialmente útil para determinar si le faltan dependencias o para ayudar a depurar problemas.

Ejecute el mandato siguiente para visualizar las versiones de las dependencias instaladas:

```
ibmcloud dev diag
```
{: codeblock}


## editar
{: #edit}

Edite la aplicación con opciones como por ejemplo conectarla con una aplicación que ya esté en {{site.data.keyword.Bluemix_notm}}, gestionar los servicios de {{site.data.keyword.Bluemix_notm}} de la aplicación y su cadena de herramientas de {{site.data.keyword.Bluemix_notm}}. Si tiene una aplicación local conectada a una aplicación de {{site.data.keyword.Bluemix_notm}}, utilice `edit` para añadir nuevos servicios, conectar y desconectar los servicios existentes o eliminar servicios existentes de la cuenta. Además, puede crear o ver una cadena de herramientas de {{site.data.keyword.Bluemix_notm}} para la aplicación.  Ejecute el mandato siguiente en la raíz del directorio de la aplicación:

```
ibmcloud dev edit
```
{: codeblock}

Si no dispone de servicios existentes en su cuenta, este mandato le mostrará una lista de los grupos de servicios desde los que puede seleccionar un servicio para conectarse a su aplicación.

Sin embargo, si tiene algún servicio existente en su cuenta, este mandato le mostrará una lista de estos servicios y si cada servicio está conectado a la aplicación o no.

La selección de un servicio conectado le proporciona opciones para desconectar el servicio de la aplicación o para suprimir el servicio de su cuenta, desconectándola de todas las aplicaciones a las que está conectada.

La selección de un servicio desconectado le ofrece opciones para conectar ese servicio a su aplicación o para suprimir el servicio de su cuenta. La conexión de un servicio existente también descargará archivos como, por ejemplo, los archivos de credenciales o el código fuente para empezar a utilizar dicho servicio.

También puede añadir un nuevo servicio a la aplicación. En esta guía se muestran las solicitudes de selección de servicios y se descargan archivos adicionales como, por ejemplo, archivos de credenciales o código fuente para empezar a utilizar el nuevo servicio.



## enable
{: #enable}

Habilite una aplicación existente para el despliegue de {{site.data.keyword.Bluemix_notm}}. El mandato `enable` intenta detectar automáticamente el idioma de una aplicación existente y, a continuación, solicitar la información adicional necesaria. Esto genera y añade archivos que pueden utilizarse para contenedores Docker locales, despliegues de CloudFoundry o despliegues de contenedores/Kubernetes.

Cuando haya iniciado una sesión en {{site.data.keyword.Bluemix_notm}}, puede optar por conectar esta aplicación local a una aplicación que ya esté en {{site.data.keyword.Bluemix_notm}} o por crear una nueva aplicación de {{site.data.keyword.Bluemix_notm}}. Para aprovechar las características de {{site.data.keyword.Bluemix_notm}}, como sus servicios y cadenas de herramientas de DevOps, se necesita una aplicación en {{site.data.keyword.Bluemix_notm}}. Cuando se crea una app de {{site.data.keyword.Bluemix_notm}} para una app que se ha clonado de un repositorio git, la app de {{site.data.keyword.Bluemix_notm}} incluirá este repositorio en su configuración. 

La función `enable` es una característica Beta; si tiene problemas para habilitar su aplicación, consulte nuestra [página de resolución de problemas](/docs/cli/ts_createapps.html#troubleshoot) para obtener ayuda. En concreto, `enable` no está pensado para aplicaciones o entornos de trabajo móviles. Para aplicaciones complejas que generen varios activos desplegables, cada componente de la aplicación se debe habilitar individualmente. 

Ejecute el mandato siguiente para habilitar una aplicación existente en el directorio actual:

```
ibmcloud dev enable
```
{: codeblock}

La presencia de los archivos necesarios proporciona la detección de idioma de aplicación para una estructura de proyecto válida.  

* La presencia de un archivo `package.json` identifica una aplicación Node.js.
* La presencia de un archivo `package.swift` identifica una aplicación Swift.
* La presencia de un archivo `setup.py` o `requirements.txt` identifica una aplicación Python.
* La presencia de un archivo `pom.xml` o `build.gradle` identifica una aplicación Java.
	* La presencia de un archivo `pom.xml` identifica una aplicación Maven.
	* La presencia de un archivo `build.gradle` identifica una aplicación Gradle.

Opcionalmente, también puede modificar el idioma de aplicación detectado utilizando el argumento `--language`.  Sin embargo, únicamente se da soporte a las aplicaciones válidas y completas. El mandato enable no modifica el código fuente.

{: #enable-language-options}

Las opciones de lenguaje incluyen:
* nodo
* swift
* python
* java-ee (interpretado como Java - Java EE)
* java-mp (interpretado como Java - Java MicroProfile)
* java-spring (interpretado como Java - Spring Framework)

Los archivos creados mediante el mandato `ibmcloud dev enable` con conflictos de denominación con archivos existentes en la carpeta de aplicación se guardan con una extensión de archivo `.merge`.  

### Parámetros del mandato enable
{: #enable-parameters}

Los siguientes parámetros se pueden utilizar con el mandato `enable` o actualizando el archivo `cli-config.yml` de la aplicación directamente. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `language`
{: #enable-language}

* Parámetro utilizado para especificar el idioma de la aplicación que se va a habilitar.
* Uso `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parámetro utilizado para forzar la rehabilitación de una aplicación ya habilitada.
* Uso `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Parámetro para evitar que se cree una app en {{site.data.keyword.Bluemix_notm}} mientras se crean los archivos de habilitación localmente.
* Uso: `ibmcloud dev enable --no-create`


## get-credentials
{: #get-credentials}

Obtiene las credenciales necesarias para la aplicación para habilitar el uso de servicios conectados.


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

Puede listar todas las aplicaciones de {{site.data.keyword.Bluemix_notm}} en un grupo de recursos.

Ejecute el mandato siguiente para listar las aplicaciones:

```
ibmcloud dev list
```
{: codeblock}


## run
{: #run}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede ejecutar la aplicación mediante el mandato `run`. Se debe completar primero una compilación sobre la aplicación utilizando el mandato `build`. Al invocar el mandato `run`, se inicia el contenedor de ejecución y expone los puertos tal y como se define en el parámetro `container-port-map`. El parámetro `run-cmd` se puede utilizar para invocar la aplicación si el contenedor de ejecución Dockerfile no contiene un punto de entrada para completar este paso.

Para poder ejecutar varios contenedores, la aplicación debería contener un archivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"), especificado en `cli-config.yml`, o bien debería utilizar el parámetro de mandato `dockerfile-run` para especificar uno. Consulte [Archivo Compose](/docs/apps/projects/compose_file.html) para obtener más información.

En primer lugar, compile la aplicación:

```
ibmcloud dev build
```
{: codeblock}

Ejecute el mandato siguiente en el directorio de aplicación actual para iniciar la aplicación:

```
ibmcloud dev run
```
{: codeblock}

Para salir de la sesión, utilice `Control-C`.


### Parámetros del mandato run
{: #run-parameters}

Los siguientes parámetros son exclusivos del mandato `run` y ayudan a gestionar la aplicación dentro del contenedor de ejecución.
Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `container-name-run`
{: #container-name-run2}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev run --container-name-run [<applicationName>]`

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
* Si tiene prevista la ejecución con varios contenedores, este archivo debería ser un archivo Compose.
* Para utilizar varios archivos Compose, delimite con comillas dobles la lista de nombres.
* Uso: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Uso: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Imagen para crear desde `dockerfile-run`.
* Uso: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parámetro utilizado para ejecutar código en el contenedor de ejecución. Utilice este parámetro si su imagen inicia la aplicación.
* Uso: `ibmcloud dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede abrir el shell dentro del contenedor de herramientas o de ejecución con el mandato `shell`.

Simplemente ejecute este mandato

```
ibmcloud dev shell
```

la CLI de {{site.data.keyword.dev_cli_short}} abrirá un shell interactivo en el contenedor docker de la aplicación. El contenedor de destino predeterminado para el mandato de shell se define por el valor `container-shell-target` en el `config.yml`, donde los valores válidos son `run` o `tools`. Si este valor no está definido o si se especifica un valor no válido, de forma predeterminada el mandato `shell` afectará al contenedor `tools`. El mandato de shell abre el contenedor en el directorio especificado por la instrucción `WORKDIR` en el Dockerfile correspondiente. Si `WORKDIR` no está en el Dockerfile, Dockerfile se utiliza la raíz del contenedor como el directorio de trabajo. Consulte [esta referencia](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") para obtener más información.

Como alternativa, puede decidir pasar `run` o `tools` como argumento para el mandato de forma que el shell se abra y sirva para dicho contenedor. Asimismo, puede utilizar el parámetro `container-name` para pasar el nombre del contenedor en el que desea el shell. Sin embargo, este distintivo debe reservarse para cuando no haya contenedores en ejecución. Los argumentos `run` y `tools` son más flexibles y permiten conmutar entre contenedores cuando alguno de ellos esté en ejecución. Por ejemplo, si el contenedor tools está en ejecución y ejecuta `ibmcloud dev shell run`, se detendrá el contenedor `tools` y se reiniciará el contenedor `run`, y viceversa.

Si el contenedor `run` o `tools` de destino no está ya en ejecución al ejecutar el mandato `shell`, se iniciará el contenedor de destino. Sin embargo, se cambiará el valor predeterminado `Cmd` o `Entrypoint` en el Dockerfile para iniciar directamente el shell en lugar de iniciar el proceso del servidor. Esto permite iniciar el contenedor `run` o `tools`, e iniciar manualmente el servidor con sus propios mandatos arbitrarios o personalizados.


También puede especificar el ejecutable del shell que desea abrir utilizando el parámetro `container-shell`. De forma predeterminada, se utiliza `/bin/sh`. Si prefiere utilizar el shell bash, especifique el valor `container-shell` para que sea `/bin/bash`; sin embargo, tenga en cuenta que este bash no está disponible automáticamente en todas las variantes de Linux.

Cualquier otro argumento adicional que pase al mandato más allá de los distintivos se analizarán como si el mandato se ejecutase al abrir el shell. Si proporciona un mandato para ejecutarlo, el shell dentro del contenedor saldrá después de la ejecución del mandato y volverá al terminal.

Por ejemplo, puede ejecutar el mandato Linux `ls` dentro del contenedor shell invocando `ibmcloud dev shell tools ls`.   También puede especificar distintivos adicionales para pasar a la ejecución del mandato del shell delimitando los argumentos entre comillas como, por ejemplo, `ibmcloud dev shell "ls -la"`.

### Parámetros del mandato shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nombre del contenedor en el que desea utilizar el shell.
* Uso: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Especifica el shell a ejecutar dentro del contenedor (el predeterminado es /bin/sh)
* Uso: `ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede consultar el estado de los contenedores que utiliza la CLI de {{site.data.keyword.dev_cli_short}}, tal y como se define en `container-name-run` y `container-name-tools`.

Ejecute el mandato siguiente en el directorio de aplicación actual para comprobar el estado del contenedor:

```
ibmcloud dev status
```
{: codeblock}


[Parámetros del mandato status](#command-parameters)


## stop
{: #stop}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede detener sus contenedores mediante el mandato `stop`.

Para detener las herramientas y ejecutar los contenedores tal como se define en el archivo `cli-config.yml`, ejecute:

```
ibmcloud dev stop
```
{: codeblock}

Para detener un contenedor que no está definido en el archivo `cli-config.yml`, puede especificar un parámetro de línea de mandatos adicional para sustituirlo.  Si no se especifica ningún contenedor en el archivo `cli-config.yml` o en la línea de mandatos, el mandato stop vuelve.

### Parámetros del mandato stop
{: #stop-parameters}

Los parámetros siguientes se utilizan para el mandato `stop`. Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `container-name-run`
{: #container-name-run}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* Nombre del contenedor de herramientas.
* Uso: `ibmcloud dev stop --container-name-tools [<applicationName>]`



## test
{: #test}

Si utiliza Windows &trade;, debe ejecutar Windows 10 Pro o posterior.

Puede probar la aplicación a través del mandato `test`. Se debe completar primero una compilación sobre la aplicación utilizando el mandato `build --debug`. A continuación, el contenedor de herramientas se utiliza para invocar `test-cmd` para la aplicación.

En primer lugar, compile la aplicación:

```
ibmcloud dev build --debug
```
{: codeblock}

Ejecute el siguiente mandato para probar la aplicación:

```
ibmcloud dev test
```
{: codeblock}


### Parámetros del mandato test
{: #test-parameters}

El siguiente parámetro es exclusivo del mandato `test`.  Hay [parámetros adicionales](#command-parameters) compartidos con otros mandatos.

#### `test-cmd`
{: #test-cmd}

* Parámetro que se utiliza para especificar un mandato para probar código en el contenedor de herramientas.
* Uso: `ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

Visualice el URL en el que se despliega su aplicación a través del mandato `view`. Ejecute este mandato en el directorio raíz de la aplicación que desea visualizar. El mandato `view` también abrirá el URL en el navegador predeterminado.

Para las aplicaciones desplegadas en Cloud Foundry, el URL consta del nombre de host y el dominio de la aplicación.

Para las aplicaciones desplegadas en Kubernetes, el URL consta de la dirección IP del nodo en que se despliega y el puerto público. Si el mandato determina que la aplicación se ha desplegado en Kubernetes, la herramienta CLI solicitará confirmación. Si especifica que la aplicación realmente no se desplegó en Kubernetes, se muestra el URL de Cloud Foundry. Si esperaba que el mandato mostrase el URL de una aplicación desplegada en Kubernetes y esto no sucede, asegúrese de que `cli-config.yml` contiene una entrada para `chart-path` o proporciónela a través de la línea de mandatos tal como se muestra [aquí](#chart-path).

Ejecute el siguiente mandato para ver su aplicación:

```
ibmcloud dev view
```
{: codeblock}

### Parámetros del mandato view
{: #view-parameters}

Los siguientes parámetros son exclusivos del mandato `view`.

#### `deploy-target`

* Parámetro opcional utilizado para indicar el tipo de despliegue para omitir la solicitud
* Uso `ibmcloud dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Parámetro que se utiliza para especificar que no se desea abrir el navegador.
* Uso: `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Raíz de proyecto para añadir al URL de la aplicación de Kubernetes y de Cloud Foundry
* Uso: `ibmcloud dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* Parámetro opcional que define el nombre el clúster Kubernetes en el que desplegar un contenedor.
* Uso `ibmcloud dev view --ibm-cluster [cluster-name]`


## Mandatos compuestos
{: #compound}

Puede ejecutar varios mandatos en una sentencia de línea de mandatos separando los mandatos de las herramientas de desarrollador de {{site.data.keyword.Bluemix_notm}} con el delimitador `/`. Se pueden especificar distintivos de línea de mandatos adicionales después de especificar los mandatos compuestos.  A continuación se muestran algunos ejemplos de mandatos compuestos:

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Todos los distintivos deben estar al final del mandato y se aplicarán a todos los mandatos asociados a dicho distintivo. En el ejemplo final anterior, el distintivo `--trace` se aplica a los 3 mandatos, sin embargo, `-t` únicamente se aplica a los 2 últimos mandatos, de forma que no se aplicará al mandato `build`.

Los mandatos que se pueden utilizar con esta característica son:
`build, debug, deploy, get-credentials, run, stop, test, view`

Si un mandato falla por algún motivo, los mandatos subsiguientes no se ejecutarán.

Si hay más mandatos que sigan a `debug` o `run`, la ejecución solo continuará si `debug` o `run` son interrumpidos por cualquier forma que no sea interrumpir el proceso desde la ventana de terminal actual. `Control+C` interrumpirá el proceso y los mandatos subsiguientes no se ejecutarán. Por ejemplo, puede ejecutar `ibmcloud dev stop` desde otra ventana de terminal para detener el contenedor en ejecución y continuar la ejecución del siguiente mandato.


## Parámetros para build, debug, run y test
{: #command-parameters}

Los siguientes parámetros se pueden utilizar con los mandatos `build|debug|run|test` o actualizando directamente el archivo `cli-config.yml` de la aplicación. Dispone de parámetros adicionales para los mandatos [`debug`](#debug-parameters) y [`run`](#run-parameters).

Los parámetros de mandatos especificados en la línea de mandatos tienen prioridad sobre la configuración `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Especifique un archivo cli-config.yml para utilizar con un mandato.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nombre del contenedor de ejecución.
* Uso: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Nombre del contenedor de herramientas.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

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

* Correlaciones de puertos para el contenedor. El primer valor es el puerto que se utilizará en el sistema operativo del host, el segundo es el puerto del contenedor [host-port:container-port].
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
* El procedimiento recomendado para evitar resultados inesperados, es compilar y ejecutar utilizando los mismos valores de montaje.
* Uso: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilice esta opción para definir montajes entre el sistema host y el contenedor de herramientas.
* Los valores de `host-path-tools` y `container-path-tools` se insertan al principio de esta lista.* El procedimiento recomendado para evitar resultados inesperados, es compilar y depurar utilizando los mismos valores de montaje.
* Uso: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parámetro que se utiliza para especificar un mandato para generar código para todos los usos menos DEBUG.
* Uso: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilice este parámetro para proporcionar una salida detallada.
* Uso: `ibmcloud dev <build|debug|run|test> --trace`
