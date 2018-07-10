---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI para gestionar los valores de catálogo, plug-ins y facturación
{: #ibmcloud_commands_settings}

<table summary="mandatos ibmcloud que puede utilizar para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabla 1. Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud catalog search
{: #ibmcloud_catalog_search}

Buscar entradas de catálogo

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Especifique la región geográfica en la que buscar. Actualmente sólo están soportadas "us-south" y "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrar por tipo de recursos. Actualmente, sólo están soportados "service-cf", "iaas", "runtime", "template" y "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>Filtrar por precio. Actualmente, sólo están soportados "free", "paygo" y "bluemix-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrar por etiqueta.</dd>
  <dt>--sort-by</dt>
  <dd>Propiedad por la que ordenar</dd>
  <dt>--col</dt>
  <dd>Especifica columnas adicionales para la tabla. Actualmente "group", "provider" y "tags"</dd>
  <dt>--reverse</dt>
  <dd>Indica si debe revertirse el orden de clasificación</dd>
  <dt>--json</dt>
  <dd>Respuesta JSON original de la salida</dd>
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

### ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Obtener una entrada de catálogo

```
ibmcloud catalog entry ID [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--children</dt>
  <dd>Obtener todos los hijos para la entrada de catálogo</dd>
  <dt>--json</dt>
  <dd>Respuesta JSON original de la salida</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Obtener entrada con el ID `a0ef1-d3b4j0`:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

### ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Crear una nueva entrada de catálogo (sólo administrador del catálogo de una cuenta)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

### ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Actualizar una entrada de catálogo existente (sólo administrador o editor del catálogo de una cuenta)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

### ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Suprimir una entrada de catálogo (solo administrador del catálogo de una cuenta)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

### ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Obtener la visibilidad para una entrada de catálogo (sólo administrador del catálogo de una cuenta)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-json</dt>
  <dd>Respuesta JSON original de la salida</dd>
  <dt>-global</dt>
  <dd>Operar en ámbito global</dd>
</dl>

<strong>Ejemplos</strong>:

Obtener la visibilidad de recursos `j402-dnf1i` en el ámbito global:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

### ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Actualizar la visibilidad de una entrada de catálogo existente (sólo administrador del catálogo de una cuenta)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Añadir una cuenta (o lista de cuentas separadas por comas) a la lista de inclusiones, concediendo visibilidad a la entrada. Las GUID de correo electrónico o cuenta son aceptables</dd>
  <dt>--includes-remove</dt>
  <dd>Eliminar una cuenta (o lista de cuentas separadas por comas) de la lista de inclusiones, revocando la visibilidad a la entrada. Las GUID de correo electrónico o cuenta son aceptables</dd>  
  <dt>--excludes-add</dt>
  <dd>Añadir una cuenta (o lista de cuentas separadas por comas) a la lista de exclusiones. Las GUID de correo electrónico o cuenta son aceptables</dd>
  <dt>--excludes-remove</dt>
  <dd>Eliminar una cuenta (o lista de cuentas separadas por comas) de la lista de exclusiones, revocando la visibilidad a la entrada. Si la cuenta se definió por administradores globales, los administradores de cuenta no pueden eliminarla. Las GUID de correo electrónico o cuenta son aceptables</dd>
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

### ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Lista de ofertas de servicios en el mercado

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

### ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualizar las plantillas de contenedor modelo en {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Si se especifica la opción <i>-d</i>, también se mostrará la descripción de cada plantilla. De lo contrario, sólo se mostrará el ID y el nombre de cada plantilla.</dd>
   </dl>

### ibmcloud catalog template
{: #ibmcloud_catalog_template}

Ver la información detallada de una plantilla de contenedor modelo especificada.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

### ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crea una app cf que se base en la plantilla específica con el URL y la descripción especificados. De forma predeterminada, la nueva app se iniciará automáticamente.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>TEMPLATE_ID (necesario)</dt>
   <dd>Plantilla en la que se basará la app cuando se cree. Utilice <i>ibmcloud templates</i> para ver el ID de todas las plantillas.</dd>
   <dt>CF_APP_NAME (necesario)</dt>
   <dd>Nombre de la aplicación cf que se debe crear.</dd>
   <dt>-u <i>URL</i> (opcional)</dt>
   <dd>Ruta de la aplicación. Si no se especifica, la ruta se establece mediante {{site.data.keyword.Bluemix_notm}} que se basa automáticamente en el nombre de la app y en el dominio predeterminado.</dd>
   <dt>-d <i>DESCRIPTION</i> (opcional)</dt>
   <dd>Descripción de la aplicación.</dd>
   <dt>--no-start (opcional)</dt>
   <dd>No inicie la app automáticamente después de crearla. Si no se especifica, la app se iniciará automáticamente una vez que se haya creado.</dd>
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

### ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Obtener un subconjunto determinado de regiones en el formato preferido.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Especificar zona geográfica por id.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtener una lista de entradas del tipo especificado.</dd>
  <dt>--col</dt>
  <dd>Especifica columnas adicionales para la tabla. Actualmente "group", "provider" y "tags".</dd>
  <dt>--json</dt>
  <dd>Salida de la respuesta JSON original.</dd>
  <dt>--global</dt>
  <dd>Operar en ámbito global.</dd>
  <dt>--csv</dt>
  <dd>Saca un archivo CSV</dd>
</dl>

### ibmcloud catalog runtime
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

### ibmcloud catalog runtimes
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

### ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostrar el uso mensual de la cuenta actual (solo el administrador de la cuenta)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--json (opcional)</dt>
  <dd>Mostrar el resultado del uso en formato JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar el informe de uso y de coste de la cuenta actual en 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

### ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostrar el uso mensual de una organización (solo el administrador de la cuenta o el gestor de facturación de la organización)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>ORG_NAME (necesario)</dt>
  <dd>Nombre de la organización.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--json (opcional)</dt>
  <dd>Mostrar el resultado del uso en formato JSON.</dd>
</dl>

### ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostrar el uso mensual de un grupo de recursos (solo el administrador de la cuenta o el administrado del grupo de recursos)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>GROUP_NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--json (opcional)</dt>
  <dd>Mostrar el resultado del uso en formato JSON.</dd>
</dl>

### ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostrar el uso mensual de las instancias de recurso de la cuenta actual.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-o ORG_NAME (opcional)</dt>
  <dd>Filtrar instancias por organización.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrar instancia por grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--json (opcional)</dt>
  <dd>Mostrar el resultado del uso en formato JSON.</dd>
</dl>

### ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Crear una lista de todos los repositorios de plug-in que se registran en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Requisitos previos</strong>:  Ninguno

### ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Agrega un nuevo repositorio de plug-in a la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>REPO_NAME (necesario)</dt>
   <dd>Nombre del repositorio que se debe añadir. Puede volver a definir su propio nombre para cada repositorio.</dd>
   <dt>REPO_URL (necesario)</dt>
   <dd>URL del repositorio que se debe añadir. El URL de repositorio debe contener el protocolo (por ejemplo, http://plugins.ng.bluemix.net en lugar de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net es el repositorio de plugins oficial de la CLI de {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Ejemplos</strong>:

Añadir el repositorio de plugins oficial de la CLI de {{site.data.keyword.Bluemix_notm}} como `bluemix-repo`:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

### ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Elimina el repositorio de plugins de la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>REPO_NAME (necesario)</dt>
   <dd>Nombre del repositorio que se debe eliminar.</dd>
   </dl>

<strong>Ejemplos</strong>:

Eliminar el repositorio `bluemix-repo` desde la CLI de {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud plugin repo-remove bluemix-repo
```

### ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Crear una lista de todos los plug-ins disponibles en todos los repositorios o repositorios específicos.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Listar únicamente los plugins del repositorio indicado.</dd>
   </dl>

<strong>Ejemplos</strong>:

Crea una lista de todos los plugins en todos los repositorios añadidos:

```
ibmcloud plugin repo-plugins
```

Listar todos los plug-ins del repositorio `bluemix-repo`:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

### ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Mostrar los detalles de un plug-in del repositorio.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Nombre del repositorio. Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado.</dd>
   </dl>

<strong>Ejemplos</strong>:

Listar los detalles del plugin "IBM-Containers" en el repositorio "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Listar los detalles del plugin "IBM-Container" en el repositorio predeterminado

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

### ibmcloud plugin list
{: #ibmcloud_plugin_list}

Crea una lista de todos los plug-ins instalados en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Requisitos previos</strong>:  Ninguno

### ibmcloud plugin show
{: #ibmcloud_plugin_show}

Mostrar los detalles de un plugin instalado.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Requisitos previos</strong>:  Ninguno

### ibmcloud plugin install
{: #ibmcloud_plugin_install}

Instalar la versión específica del plug-in en la CLI de {{site.data.keyword.Bluemix_notm}} desde la vía de acceso o el repositorio especificados.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado 'Bluemix'.
Si no se especifica ninguna versión, el mandato selecciona la versión disponible más reciente para instalar.

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (necesario)</dt>
   <dd>Si -r <i>REPO_NAME</i> no se especifica, el plug-in se instala desde la vía de acceso local o el URL remoto indicados.</dd>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Nombre del repositorio en el que se encuentra el binario del plug-in. Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (opcional)</dt>
   <dd>Versión del plug-in que se debe instalar. Si no se proporciona, se instalará la versión más reciente del plug-in. Esta opción sólo es válida al instalar el plug-in desde el repositorio.</dd>
   <dt>-f </dt>
   <dd>Forzar la instalación del plugin sin confirmación.</dd>
    </dl>


La CLI de {{site.data.keyword.Bluemix_notm}} tiene el nombre de repositorio oficial de `Bluemix`.

<strong>Ejemplos</strong>:

Instalar un plug-in desde el archivo local:

```
ibmcloud plugin install /downloads/new_plugin
```

Instalar un plug-in desde el URL remoto:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Instalar el plugin 'container-service' de la versión más reciente del repositorio 'Bluemix':

```
ibmcloud plugin install container-service -r Bluemix
```

o simplemente:

```
ibmcloud plugin install container-service
```

Instalar el plugin 'container-service' con la versión '0.1.425' del repositorio oficial de plugins:

```
ibmcloud plugin install container-service -v 0.1.425
```

### ibmcloud plugin update
{: #ibmcloud_plugin_update}

Actualizar el plugin desde un repositorio.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado 'Bluemix'.
Si no se especifica ninguna versión, el mandato selecciona la versión disponible más reciente para instalar.

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nombre del plug-in que se debe actualizar. Si no se especifica, el mandato comprobará las actualizaciones para todos los plug-ins instalados.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Nombre del repositorio en el que se encuentra el binario del plug-in. Si no se especifica, el mandato utilizará el repositorio de plug-in predeterminado, 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (opcional)</dt>
 <dd>Versión a la que se tiene que actualizar el plug-in. Si no se proporciona, actualiza el plug-in a la última versión disponible.</dd>
 <dt>--all</dt>
 <dd>Actualiza todos los plugins disponibles</dd>
</dl>

<strong>Ejemplos</strong>:

comprobar todas las actualizaciones disponibles en el repositorio de plugins oficial 'Bluemix':

```
ibmcloud plugin update -r Bluemix
```

o simplemente:

```
ibmcloud plugin update
```

Actualizar el plugin 'container-service' en el repositorio oficial de plugins a la última versión:

```
ibmcloud plugin update container-service
```

Actualizar el plugin 'container-service' en el repositorio oficial de plugins a la versión '0.1.440':

```
ibmcloud plugin update container-service -v 0.1.440
```

### ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Desinstala el plug-in especificado desde la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>PLUGIN_NAME (necesario)</dt>
   <dd>Nombre del plug-in que se debe desinstalar.</dd>
    </dl>

<strong>Ejemplos</strong>:

Desinstala el plugin 'container-service' que se ha instalado
previamente:

```
ibmcloud plugin uninstall container-service
```
