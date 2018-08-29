---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de grupos de recursos y recursos
{: #ibmcloud_commands_resource}

<table summary="Mandato de Bluemix que puede utilizar para gestionar grupos de recursos y recursos.">
  <caption>Tabla 1. Mandatos para gestionar grupos de recursos y recursos</caption>
  <thead>
    <th colspan="5">Mandatos para gestionar grupos de recursos y recursos</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Listar grupos de recursos.

```
ibmcloud resource groups [--default]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--default</dt>
  <dd>Obtener el grupo predeterminado de la cuenta actual.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todos los grupos de recursos de la cuenta de destino actual:

```
ibmcloud resource groups
```

Listar el grupo predeterminado de la cuenta de destino actualmente:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Mostrar detalles de un grupo de recursos

```
ibmcloud resource group NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Mostrar solo ID</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar grupo de recursos `example-group`:

```
ibmcloud resource group example-group
```

Mostrar sólo el ID del grupo de recursos `example-group`:

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Crear un grupo de recursos

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

<strong>Ejemplos</strong>:

Crear un grupo de recursos `example-group` con la cuota `free`:

```
ibmcloud resource group-create example-group free
```

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Actualizar un grupo de recursos existente

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos de destino</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de grupo de recursos</dd>
  <dt>-q, --quota</dt>
  <dd>Nombre de la nueva definición de cuota</dd>
  <dt>-f</dt>
  <dd>Forzar actualización sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Cambie el nombre del grupo de recursos `example-group` a `trial-group`:

```
ibmcloud resource group-update example-group -n trial-group
```

Cambie la cuota del grupo de recursos `example-group` a `free`:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Listar todas las definiciones de cuota

```
ibmcloud resource quotas
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todas las definiciones de cuota:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Mostrar detalles de una definición de cuota

```
ibmcloud resource quota NAME
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre de la cuota</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles de cuota `free`:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrar una instancia de servicio Cloudfoundry en un grupo de recursos

```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME o SERVICE_INSTANCE_ID (necesario)</dt>
  <dd>Nombre o ID de la instancia de servicio</dd>
  <dt>--resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción es exclusiva con '--resource-group-id'. Si no se especifica ninguna de ellas, se tendrá como valor predeterminado el grupo de recursos de destino actual.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID del grupo de recursos. Esta opción es exclusiva con '--resource-group-name'. Si no se especifica ninguna de ellas, se tendrá como valor predeterminado el grupo de recursos de destino actual.</dd>
  <dt>-f, --force</dt>
  <dd>Migrar sin confirmación</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Listar instancias de servicio

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Nombre del servicio de pertenencia</dd>
  <dt>--location</dt>
  <dd>Filtrar por ubicación</dd>
  <dt>--long</dt>
  <dd>Mostrar campos adicionales en la salida</dd>
</dl>

<strong>Ejemplos</strong>:

Listar las instancias de servicio del servicio `test-service`:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostrar los detalles de una instancia de servicio

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario), exclusivo con ID</dt>
  <dd>Nombre de la instancia de servicio</dd>
  <dt>ID (necesario), exclusivo con NAME</dt>
  <dd>ID de la instancia de servicio</dd>
  <dt>--location</dt>
  <dd>Filtrar por ubicación</dd>
  <dt>--id</dt>
  <dd>Mostrar el ID de la instancia de servicio</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la instancia de servicio `my-service-instance`:

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Crear una instancia de servicio

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre de la instancia de servicio</dd>
  <dt>SERVICE_NAME o SERVICE_ID (necesario)</dt>
  <dd>Nombre o ID del servicio</dd>
  <dt>SERVICE_PLAN_NAME o SERVICE_PLAN_ID (necesario)</dt>
  <dd>Nombre o ID del plan de servicio</dd>
  <dt>LOCATION</dt>
  <dd>Ubicación o entorno de destino para crear la instancia de servicio</dd>
  <dt>-t, --tags</dt>
  <dd>Etiquetas</dd>
  <dt>-p, --parameters</dt>
  <dd>Archivo JSON o serie JSON de parámetros para crear la instancia de servicio</dd>
  <dt>-d, --deployment</dt>
  <dd>Nombre del despliegue</dd>
</dl>

<strong>Ejemplos</strong>:
Crear una instancia de servicio llamada `my-service-instance` utilizando el plan de servicio `test-service-plan` del servicio `test-service` en la ubicación `eu-gb`:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Actualizar instancia de servicio

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>Nombre (necesario)</dt>
  <dd>Nombre de la instancia de servicio, exclusivo con ID</dd>
  <dt>ID (necesario)</dt>
  <dd>ID de la instancia de servicio, exclusivo con NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de instancia de servicio</dd>
  <dt>-t, --tags</dt>
  <dd>Etiquetas nuevas</dd>
  <dt>--service-plan-id</dt>
  <dd>Nuevo ID de plan de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Forzar actualización sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Actualizar la instancia de servicio `my-service-instance`, cambiar su nombre a `new-service-instance`:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Suprimir instancia de servicio

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>Nombre (necesario)</dt>
  <dd>Nombre de la instancia de servicio, exclusivo con ID</dd>
  <dt>ID (necesario)</dt>
  <dd>ID de la instancia de servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
  <dt>--recursive</dt>
  <dd>Suprimir todos los recursos de pertenencia</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir instancia de servicio de recurso `my-service-instance`:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Mostrar enlaces al alias de servicio

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar enlaces de recursos con el alias de servicio `my-service-alias`:

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostrar detalles de un enlace de servicio

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>APP_NAME</dt>
  <dd>Nombre de aplicación de CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Solo se mostrará el ID. Se suprimirá el resto de la salida del enlace de servicio.</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles de enlace de servicio entre el alias de servicio `my-service-alias` y la app `my-app`:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crear un enlace de servicio

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>APP_NAME</dt>
  <dd>Nombre de aplicación de CloudFoundry</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nombre del rol de usuario</dd>
  <dt>--service-id</dt>
  <dd>Nombre o UUID del ID de servicio al que pertenece el rol</dd>
  <dt>-p, --parameter</dt>
  <dd>Parámetros del archivo JSON o de la serie JSON</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la creación sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Crear enlaces de servicio entre el alias de servicio `my-service-alias` y la app `my-app` con el rol `Administrator`:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Suprimir un enlace de servicio

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>APP_NAME</dt>
  <dd>Nombre de aplicación de CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir el enlace de servicio entre el alias de servicio `my-service-alias` y la app `my-app`:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Listar claves de servicio de la instancia de servicio o el alias de servicio

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID de instancia de servicio</dd>
  <dt>--instance-name</dt>
  <dd>Nombre de instancia de servicio</dd>
  <dt>--alias-id</dt>
  <dd>ID de alias de servicio</dd>
  <dt>--alias-name</dt>
  <dd>Nombre de alias de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Listar claves de servicio de la instancia de servicio `my-service-instance`:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Mostrar detalles de una clave de servicio

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nombre de la clave</dd>
  <dt>--id</dt>
  <dd>Mostrar el ID de la clave de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles de la clave de servicio `my-service-key`:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crear una clave de servicio

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NOMBRE</dt>
  <dd>Nombre de la clave</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nombre del rol de usuario</dd>
  <dt>--instance-id</dt>
  <dd>ID de instancia de servicio</dd>
  <dt>--instance-name</dt>
  <dd>Nombre de instancia de servicio</dd>
  <dt>--alias-id</dt>
  <dd>ID de alias de servicio</dd>
  <dt>--alias-name</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>--service-id</dt>
  <dd>Nombre o UUID del ID de servicio al que pertenece el rol</dd>
  <dt>-p, --parameters</dt>
  <dd>Parámetros del archivo JSON o de la serie JSON</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la creación sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Crear una clave de servicio llamada `my-service-key` con el rol `Administrator` para la instancia de servicio `my-service-instance`:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Suprimir una clave de servicio

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nombre de la clave</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir la clave de servicio `my-service-key`:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Listar los alias de una instancia de servicio

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID de la instancia de servicio de pertenencia.</dd>
  <dt>--instance-name</dt>
  <dd>Nombre de la instancia de servicio de pertenencia.</dd>
</dl>

<strong>Ejemplos</strong>:
Listar alias de servicio de la instancia de servicio `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostrar detalles de un alias de servicio

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre del alias de servicio</dd>
  <dt>--id</dt>
  <dd>Solo mostrará el ID del alias de servicio proporcionado. Se suprimirá el resto de la salida para el alias.</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles del alias de servicio `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crear un alias de una instancia de servicio

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre del alias de servicio</dd>
  <dt>--instance-id</dt>
  <dd>ID de la instancia de servicio de pertenencia.</dd>
  <dt>--instance-name</dt>
  <dd>Nombre de la instancia de servicio de pertenencia.</dd>
  <dt>-s</dt>
  <dd>Nombre del espacio en el que se ha creado el alias. El valor predeterminado es el espacio actual.</dd>
  <dt>-t, --tags</dt>
  <dd>Lista de etiquetas.</dd>
  <dt>-p, --parameters</dt>
  <dd>Parámetros del archivo JSON o de la serie JSON.</dd>
</dl>

<strong>Ejemplos</strong>:
Crear un alias de servicio llamado `my-service-alias` de la instancia de servicio `my-service-instance`:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Actualizar un alias de servicio

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre del alias de servicio</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre del alias de servicio.</dd>
  <dt>-t, --tags</dt>
  <dd>Lista de etiquetas.</dd>
  <dt>-p, --parameters</dt>
  <dd>Parámetros del archivo JSON o de la serie JSON.</dd>
  <dt>-f, --force</dt>
  <dd>Forzar actualización sin confirmación del usuario.</dd>
</dl>

<strong>Ejemplos</strong>:
Actualizar el alias de servicio `my-service-alias` y cambiar el nombre a `new-service-alias`:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Suprimir un alias de servicio

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre del alias de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir el alias de servicio `my-service-alias`:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Buscar recursos utilizando la sintaxis de consultas de Lucene

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-offset, --o</dt>
  <dd>Número de posición del recurso inicial</dd>
  <dt>-limit, --l</dt>
  <dd>Número de recursos que se deben devolver (máximo 10000)</dd>
</dl>

<strong>Ejemplos</strong>:
Buscar aplicaciones de Cloud Foundry cuyo nombre comience con un texto especificado:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Buscar instancias de servicio de Cloud Foundry del nombre de servicio especificado:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Buscar enlaces de servicio de Cloud Foundry en la organización con el ID especificado:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Buscar espacios de Cloud Foundry con el nombre especificado y ubicados en una de las dos regiones especificadas:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Buscar recursos cuyo nombre contenga la palabra dev en el espacio de Cloud Foundry con el ID especificado:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Buscar recursos de Resource Controller en la ubicación especificada (p.ej. en la región del sur de EE.UU.):

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Buscar recursos o alias en el grupo de recursos con el ID especificado:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Buscar grupos de recursos con el nombre default:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Buscar entre los enlaces de servicio el nombre de servicio especificado:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Buscar un recurso con el nombre de Recurso de Nube (CRN) especificado:

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Buscar un recurso con la etiqueta especificada:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Listar todas las etiquetas

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Tipo de etiqueta (valores soportados: usuario, restringido)</dd>
  <dt>-o, --offset</dt>
  <dd>Iniciando el número de posición de recurso (valor predeterminado: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Número de recursos a devolver (máximo 10000) (valor predeterminado: 10000)</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todas las etiquetas

```
ibmcloud resource tags
```

Listar todas las etiquetas restringidas

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Mostrar detalles de una etiqueta

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Tag Name, exclusivo con --tag-crn</dd>
  <dt>--tag-crn (necesario)</dt>
  <dd>Tag CRN, exclusivo con --tag-name</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la etiqueta "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Crear una etiqueta

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Nombre de etiqueta</dd>
  <dt>--tag-type</dt>
  <dd>Tipo de etiqueta (valores soportados: usuario, restringido; valor predeterminado: usuario)</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una etiqueta de usuario con el nombre think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Crear una etiqueta restringida con el nombre department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Crear una etiqueta de usuario con el nombre "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Crear una etiqueta restringida con el nombre "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Suprimir una etiqueta

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Tag Name, exclusivo con --tag-crn</dd>
  <dt>--tag-crn (necesario)</dt>
  <dd>Tag CRN, exclusivo con --tag-name</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir etiqueta "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Añadir una etiqueta a un recurso

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Tag Name, exclusivo con --tag-crn</dd>
  <dt>--tag-crn (necesario)</dt>
  <dd>Tag CRN, exclusivo con --tag-name</dd>
  <dt>--resource-crn (necesario)</dt>
  <dd>CRN de recurso</dd>
</dl>

<strong>Ejemplos</strong>:

Añadir etiqueta "Ray Brown" al recurso cuyo crn es resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Eliminar una etiqueta de un recurso

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Tag Name, exclusivo con --tag-crn</dd>
  <dt>--tag-crn (necesario)</dt>
  <dd>Tag CRN, exclusivo con --tag-name</dd>
  <dt>--resource-crn (necesario)</dt>
  <dd>CRN de recurso</dd>
</dl>

<strong>Ejemplos</strong>:

Eliminar etiqueta "Ray Brown" del recurso cuyo crn es resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Cambiar etiqueta de usuario a etiqueta restringida y viceversa

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Tag Name, exclusivo con --tag-crn</dd>
  <dt>--tag-crn (necesario)</dt>
  <dd>Tag CRN, exclusivo con --tag-name</dd>
  <dt>--tag-type (necesario)</dt>
  <dd>Tipo de etiqueta</dd>
</dl>

<strong>Ejemplos</strong>:

Cambiar etiqueta "Ray Brown" a etiqueta restringida

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
