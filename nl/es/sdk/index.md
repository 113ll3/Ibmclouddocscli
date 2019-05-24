---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-03"

keywords: cli, sdk generator, open api, ibmcloud sdk, ibmcloud sdk generate, generate, sdk validate, sdk list, cloud foundry, rest api 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK Generator
{: #sdk-cli}

El plugin SDK Generator de {{site.data.keyword.IBM}} se puede instalar en la [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) de {{site.data.keyword.cloud_notm}}.

Como desarrollador en {{site.data.keyword.cloud_notm}}, puede utilizar este plug-in para generar SDK desde su definición de la API REST compatible con la [Especificación de Open API](https://www.openapis.org/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"). A medida que realiza cambios en la definición de API REST, podrá utilizar este plugin para volver a generar sólo el SDK, en lugar de volver a generar todo el proyecto.

También puede ver si las apps de Cloud Foundry en un espacio determinado tienen definiciones de API REST válidas para la generación de SDK. Finalmente, puede utilizar el plugin SDK Generator de {{site.data.keyword.IBM_notm}} para validar cualquier definición de API REST para garantizar que cumpla con los requisitos del generador de SDK.

El plugin SDK Generator de {{site.data.keyword.IBM_notm}} le permite integrar con facilidad los servicios de fondo con la app con un SDK generado. Cuando se produzca un cambio en una API REST, puede volver a generar el SDK y sustituir el antiguo por una actualización de SDK. También puede integrar la CLI en un conducto de devops y garantizar que el SDK sea siempre coherente con la especificación de la API cada vez que se cree la app.

La definición de la API REST debe ser válida y estar alojada en un punto final de servidor activo o en un archivo local en el sistema. Si la definición de la API REST está alojada, el URL relativo debe estar definido en la variable de entorno `OPENAPI_SPEC`.

## Requisitos
{: #prereqs}

Asegúrese de haber satisfecho los siguientes requisitos.

* Tiene una cuenta de [{{site.data.keyword.cloud_notm}}](https://{DomainName}/login){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").
* Una definición de API válida que se ajusta a la [especificación de Open API](https://www.openapis.org/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

## Instalación
{: #sdk-installation}

Instale las [herramientas del desarrollador de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

## Mandatos
{: #commands}

Utilice los siguientes mandatos para generar un SDK, validar los archivos de definición de Open API o listar las apps de Cloud Foundry.

### Generación de un SDK
{: #gen}

Uso `ibmcloud sdk generate [arguments...] [command options]`.

#### Argumentos
{: #gen-args}

* `APP_NAME`: el nombre de la app de Cloud Foundry en el espacio actual
* `OPENAPI_DOC_LOCATION`: un URL o una vía de acceso de archivos relativa al JSON o Yaml de la definición de la API REST sin formato
* `GENERATED_SDK_NAME` (opcional): el nombre del SDK generado


#### Opciones
{: #gen-options}

* `PLATFORM` (required)
   * `--android` - generar un SDK de Android
   * `--ios` - generar un SDK de Swift de iOS
   * `--swift` - generar un SDK de servidor de Swift
   * `--js` - generar un SDK de JavaScript
* `LOCATION` (obligatorio) - especifica el tipo de `OPENAPI_DOC_LOCATION`
   * `-r` - URL remoto
   * `-f` - archivo
   * `-a` - app que se ejecuta en {{site.data.keyword.cloud_notm}}
   * `-l` - URL de localhost
* `--output "YOUR_RELATIVE_PATH"` (opcional): coloca el SDK generado en el directorio especificado por `YOUR_RELATIVE_PATH` (se sobrescribe si hay un SDK existente)
* `--unzip` (opcional): extrae el SDK generado (se sobrescribe si hay artefactos SDK existentes)


#### Uso
{: #gen-usage}

Para generar un SDK desde una app de Cloud Foundry que se está ejecutando en {{site.data.keyword.cloud_notm}}, puede utilizar el nombre de la app como un parámetro para la CLI. El mandato siguiente utiliza el nombre de la app como el `SDK_Name`.

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

Para generar un SDK desde un URL a un archivo de definición de Open API o un archivo JSON o Yaml local, utilice el siguiente mandato.

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Validación de definiciones de Open API
{: #validating}

Utilice `ibmcloud sdk validate [argument]`.


#### Argumentos
{: #val-args}

* `APP_NAME`: el nombre de la app de Cloud Foundry en el espacio actual
* `OPENAPI_DOC_LOCATION`: un URL o una vía de acceso de archivos relativa al JSON o Yaml de la definición de la API REST sin formato


#### Uso
{: #val-usage}

Para validar una especificación de API de la app Cloud Foundry que se está ejecutando en {{site.data.keyword.cloud_notm}}, puede utilizar el nombre de la app como un parámetro para la CLI.

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

Para validar un SDK desde el URL a un documento de especificación de la API o un archivo JSON o Yaml local, utilice el siguiente mandato.

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### List Apps (Cloud Foundry)
{: #list-apps}

Utilice `ibmcloud sdk list [argument] [option]` para listar apps y para validar las especificaciones de API. Debe tener la variable de entorno `OPENAPI_SPEC` establecida en la vía de acceso con el URL relativo que aloja su especificación.


#### Argumentos
{: #list-args}

* `SPACE_NAME` (opcional): el nombre del espacio de Cloud Foundry dentro de la organización actual en la que desea buscar apps. Si no se proporciona, se buscará en el espacio actual.


#### Opciones
{: #list-options}

* `--url` (opcional): para mostrar un URL completamente formado en la definición de Open API para cada app de la lista


#### Uso
{: #list-usage}

Para listar apps en el espacio actual, utilice el siguiente mandato.

```
ibmcloud sdk list
```
{: codeblock}

Para listar apps en el espacio actual y mostrar el URL de especificación de API, utilice el siguiente mandato.

```
ibmcloud sdk list --url
```
{: codeblock}

Para listar apps en un espacio específico, utilice el siguiente mandato.

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

Para listar apps en un espacio específico y mostrar el URL de especificación de API, utilice el siguiente mandato.

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
