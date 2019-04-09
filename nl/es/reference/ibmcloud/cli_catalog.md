---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Búsqueda y gestión de ofertas del catálogo
{: #ibmcloud_catalog}

Utilice los mandatos siguientes para gestionar las entradas de catálogo de {{site.data.keyword.cloud}}, las plantillas de consulta, los tiempos de ejecución y las geolocalizaciones de centros de datos.
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Buscar entradas de catálogo:
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Especifique la región geográfica en la que buscar. Actualmente, solo se admiten "us-south" y "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrar por tipo de recursos. Actualmente, solo se admiten "service-cf", "iaas", "runtime", "template" y "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>Filtrar por precio. Actualmente, solo se da soporte a "free", "paygo" e "ibmcloud-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrar por etiqueta.</dd>
  <dt>--sort-by</dt>
  <dd>Propiedad por la que ordenar</dd>
  <dt>--col</dt>
  <dd>Especifica columnas adicionales para la tabla. Actualmente, "group", "provider" y "tags"</dd>
  <dt>--reverse</dt>
  <dd>Indica si debe revertirse el orden de clasificación</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especifique el tipo de salida, ahora solo se da soporte a JSON. Esta opción es exclusiva con '--id'.</dd>
  <dt>--csv</dt>
  <dd>Saca un archivo CSV</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Busque el servicio `Prueba de automatización`:

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Obtener una entrada de catálogo

```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--children</dt>
  <dd>Obtener todos los hijos para la entrada de catálogo</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especifique el tipo de salida, ahora solo se da soporte a JSON.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Obtener entrada con el ID `a0ef1-d3b4j0`:
```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}

Crear una nueva entrada de catálogo (sólo administrador del catálogo de una cuenta):
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>ID padre del objeto</dd>
  <dt>-c</dt>
  <dd>Objeto JSON válido que contiene parámetros de configuración específicos del catálogo, proporcionados en línea o en un archivo. Para obtener una lista de parámetros de configuración soportados, consulte la documentación para la entrada de catálogo concreta.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Crear recurso desde el archivo JSON con el ID padre `a0ef1-d3b4j0`:
```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}

Actualizar una entrada de catálogo existente (sólo administrador o editor del catálogo de una cuenta):
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-c</dt>
  <dd>Objeto JSON válido que contiene parámetros de configuración específicos del catálogo, proporcionados en línea o en un archivo. Para obtener una lista de parámetros de configuración soportados, consulte la documentación para la entrada de catálogo concreta.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar recurso `j402-dnf1i` desde el archivo JSON:
```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Suprimir una entrada de catálogo (solo administrador del catálogo de una cuenta)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir el recurso `j402-dnf1i`:
```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Obtener la visibilidad para una entrada de catálogo (sólo administrador del catálogo de una cuenta)
```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-json</dt>
  <dd>Respuesta JSON original de la salida</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especifique el tipo de salida, ahora solo se da soporte a JSON.</dd>
  <dt>-global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Obtener la visibilidad de recursos `j402-dnf1i` en el ámbito global:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}

Actualizar la visibilidad de una entrada de catálogo existente (sólo administrador del catálogo de una cuenta):
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Añadir una cuenta (o lista de cuentas separadas por comas) a la lista de inclusiones, concediendo visibilidad a la entrada. Las GUID de correo electrónico o cuenta son aceptables</dd>
  <dt>--includes-remove</dt>
  <dd>Eliminar una cuenta (o lista de cuentas separadas por comas) de la lista de inclusiones, revocando la visibilidad a la entrada. Las GUID de correo electrónico o cuenta son aceptables</dd>  
  <dt>--excludes-add</dt>
  <dd>Añadir una cuenta (o lista de cuentas separadas por comas) a la lista de exclusiones. Las GUID de correo electrónico o cuenta son aceptables</dd>
  <dt>--excludes-remove</dt>
  <dd>Eliminar una cuenta (o lista de cuentas separadas por comas) de la lista de exclusiones, revocando la visibilidad a la entrada. Si la cuenta la definieron administradores globales, los administradores de cuenta no pueden eliminarla. Las GUID de correo electrónico o cuenta son aceptables</dd>
  <dt>--owner</dt>
  <dd>Cambiar el propietario de un objeto. Las GUID de correo electrónico o cuenta son aceptables.</dd>
  <dt>--restrict</dt>
  <dd>Cambiar la restricción del objeto de visibilidad a 'Privada'</dd>
  <dt>--unrestrict</dt>
  <dd>Cambiar la restricción del objeto de visibilidad a 'Pública'</dd>  
  <dt>-c</dt>
  <dd>Objeto JSON válido que contiene parámetros de configuración específicos del catálogo, proporcionados en línea o en un archivo. Para obtener una lista de parámetros de configuración soportados, consulte la documentación para la entrada de catálogo concreta.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Establecer visibilidad del recurso `j402-dnf1i` desde el archivo JSON:
```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}

Lista de ofertas de servicios en el mercado:
```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Mostrar sólo servicios de Cloud Foundry</dd>
  <dt>--rc</dt>
  <dd>Mostrar sólo servicios compatibles con RC</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar ofertas de servicio en el ámbito global:
```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualizar las plantillas de contenedor modelo en {{site.data.keyword.cloud_notm}}.
```
ibmcloud catalog templates [-d]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Si se especifica la opción <i>-d</i>, también se mostrará la descripción de cada plantilla. De lo contrario, sólo se mostrará el ID y el nombre de cada plantilla.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Ver la información detallada de una plantilla de contenedor modelo especificada.
```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>TEMPLATE_ID (necesario)</dt>
   <dd>ID de la plantilla de contenedor modelo. Utilice <i>ibmcloud templates</i> para ver los ID de todas las plantillas.</dd>
   </dl>


<strong>Ejemplos</strong>:

Ver detalles de la plantilla `mobileBackendStarter`:
```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crea una aplicación cf que se base en la plantilla específica con el URL y la descripción especificados. De forma predeterminada, la nueva app se iniciará automáticamente.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>TEMPLATE_ID (necesario)</dt>
   <dd>Plantilla en la que se basa la aplicación cuando se crea. Utilice <i>ibmcloud templates</i> para ver el ID de todas las plantillas.</dd>
   <dt>CF_APP_NAME (necesario)</dt>
   <dd>Nombre de la aplicación cf que se debe crear.</dd>
   <dt>-u <i>URL</i> (opcional)</dt>
   <dd>Ruta de la aplicación. Si no se especifica, la ruta se establece mediante {{site.data.keyword.Bluemix_notm}} que se basa automáticamente en el nombre de la app y en el dominio predeterminado.</dd>
   <dt>-d <i>DESCRIPTION</i> (opcional)</dt>
   <dd>Descripción de la aplicación.</dd>
   <dt>--no-start (opcional)</dt>
   <dd>No iniciar la aplicación automáticamente después de su creación. Si no se especifica, la aplicación se iniciará automáticamente una vez que se haya creado.</dd>
   </dl>


<strong>Ejemplos</strong>:

Crear una aplicación cf `my-app` basada en la plantilla `javaHelloWorld`:
```
ibmcloud catalog template-run javaHelloWorld my-app
```

Crear una aplicación `my-ruby-app` en función de la plantilla `rubyHelloWorld` con la ruta `myrubyapp.chinabluemix.net` y la descripción `Mi primera app ruby en {{site.data.keyword.Bluemix_notm}}.`:
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crear una aplicación `my-python-app` basada en la plantilla `pythonHelloWorld` sin inicio automático:
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Obtener un subconjunto determinado de regiones en el formato preferido.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Especificar zona geográfica por id.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtener una lista de entradas del tipo especificado.</dd>
  <dt>--col</dt>
  <dd>Especifica columnas adicionales para la tabla. Actualmente "group", "provider" y "tags".</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especifique el tipo de salida, ahora solo se da soporte a JSON. Esta opción es exclusiva con '--id'.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global.</dd>
  <dt>--csv</dt>
  <dd>Saca un archivo CSV</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Visualice los detalles de un tiempo de ejecución. Este mandato solo está disponible para nube pública.
```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Ejemplos</strong>:

Mostrar los detalles del tiempo de ejecución "nodejsHelloWorld":
```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Listar todos los tiempos de ejecución. Este mandato solo está disponible para nube pública.
```
ibmcloud catalog runtimes [-d]
```

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-d</dt>
  <dd>Mostrar la descripción de cada tiempo de ejecución</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todos los tiempos de ejecución junto con sus descripciones:
```
ibmcloud catalog runtimes -d
```
