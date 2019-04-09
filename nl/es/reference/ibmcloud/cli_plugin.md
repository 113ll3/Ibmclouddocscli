---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Adición y eliminación de plugins de CLI de {{site.data.keyword.Bluemix_notm}}
{: #ibmcloud_commands_settings}

{{site.data.keyword.Bluemix}} da soporte a una infraestructura de plug-in para ampliar su capacidad. Utilice los mandatos siguientes para gestionar los plug-ins CLI de {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="mandatos ibmcloud que puede utilizar para gestionar los plug-ins de CLI de {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud plugin repo-add](cli_plugin.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_plugin.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_plugin.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_plugin.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_plugin.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_plugin.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_plugin.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_plugin.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_plugin.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud plugin repos](cli_plugin.html#ibmcloud_plugin_repos)</td>
</tr>
 </tbody>
 </table>
 
 
 ## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Crear una lista de todos los repositorios de plug-in que se registran en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Requisitos previos</strong>:  Ninguno

## ibmcloud plugin repo-add
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

## ibmcloud plugin repo-remove
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

## ibmcloud plugin repo-plugins
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

## ibmcloud plugin repo-plugin
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

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Crea una lista de todos los plug-ins instalados en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Requisitos previos</strong>:  Ninguno

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Mostrar los detalles de un plugin instalado.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Requisitos previos</strong>:  Ninguno

## ibmcloud plugin install
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

## ibmcloud plugin update
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

## ibmcloud plugin uninstall
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
