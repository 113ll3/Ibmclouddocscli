---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Cómo trabajar con recursos y grupos de recursos
{: #ibmcloud_commands_resource}

Un grupo de recursos es una manera de organizar sus recursos de cuenta en agrupaciones personalizables. Utilice los mandatos siguientes para gestionar los recursos y el recurso de {{site.data.keyword.cloud}} en un grupo de recursos.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Listar grupos de recursos.
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--default</dt>
  <dd>Obtener el grupo predeterminado de la cuenta actual.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todos los grupos de recursos de la cuenta de destino actual:
```
ibmcloud resource groups
```
{: codeblock}

Listar el grupo predeterminado de la cuenta de destino actualmente:
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

Mostrar detalles de un grupo de recursos
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Mostrar solo ID</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar grupo de recursos `example-group`:
```
ibmcloud resource group example-group
```
{: codeblock}

Mostrar sólo el ID del grupo de recursos `example-group`:
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Crear un grupo de recursos:
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos</dd>
</dl>

<strong>Ejemplos</strong>:

Crear un grupo de recursos `example-group`:
```
ibmcloud resource group-create example-group
```
{: codeblock}

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
{: codeblock}

Cambie la cuota del grupo de recursos `example-group` a `free`:
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Listar todas las definiciones de cuota.
```
ibmcloud resource quotas
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todas las definiciones de cuota:
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Mostrar detalles de una definición de cuota.
```
ibmcloud resource quota NAME
```
{: codeblock}

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
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrar una instancia de servicio de Cloud Foundry a un grupo de recursos
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

Listar instancias de servicio.
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long] [--output FORMAT]
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
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON. </dd>
</dl>

<strong>Ejemplos</strong>:

Listar las instancias de servicio del servicio `test-service`:
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostrar los detalles de una instancia de servicio.

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
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
  <dt>--output</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON. Esta opción es exclusiva con '--id'.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la instancia de servicio `my-service-instance`:
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Crear una instancia de servicio.
```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre de la instancia de servicio</dd>
  <dt>SERVICE_NAME o SERVICE_ID (necesario)</dt>
  <dd>Nombre o ID del servicio. Para mostrar una lista de ofertas de servicio, utilice el [mandato](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace) `ibmcloud catalog service-marketplace`.</dd>
  <dt>SERVICE_PLAN_NAME o SERVICE_PLAN_ID (necesario)</dt>
  <dd>Nombre o ID del plan de servicio</dd>
  <dt>LOCATION</dt>
  <dd>Ubicación o entorno de destino para crear la instancia de servicio</dd>
  <dt>-p, --parameters</dt>
  <dd>Archivo JSON o serie JSON de parámetros para crear la instancia de servicio</dd>
  <dt>-d, --deployment</dt>
  <dd>Nombre del despliegue</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una instancia de servicio llamada `my-service-instance` que utilice el plan de servicio `test-service-plan` del servicio `test-service` en la ubicación `eu-gb`:
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Actualizar instancia de servicio.
```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [--parameters @JSON_FILE | JSON_STRING] [-f, --force]
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
  <dt>--service-plan-id</dt>
  <dd>Nuevo ID de plan de servicio</dd>
  <dt>--parameters @JSON_FILE | JSON_STRING</dt>
  <dd>Archivo JSON o serie JSON de parámetros para crear la instancia de servicio</dd>
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

Suprimir instancia de servicio.
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
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Mostrar enlaces al alias de servicio.
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar enlaces de recursos con el alias de servicio `my-service-alias`:
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostrar detalles de un enlace de servicio.
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>APP_NAME</dt>
  <dd>Nombre de aplicación de CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Solo se mostrará el ID. Se suprimirá el resto de la salida del enlace de servicio. Esta opción es exclusiva con '--output'.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON. Esta opción es exclusiva con '--id'.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de enlace de servicio entre el alias de servicio `my-service-alias` y la app `my-app`:
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crear un enlace de servicio.
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

Crear un enlace de servicio entre el alias `my-service-alias` y la app `my-app` con el rol de `Administrador`:
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Suprimir un enlace de servicio.
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
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Listar claves de servicio de la instancia de servicio o el alias de servicio.
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
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
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar claves de servicio de la instancia de servicio `my-service-instance`:
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Muestra los detalles de las claves de servicio, donde los *n* primeros caracteres del nombre de la clave de servicio coinciden con el valor proporcionado de KEY_NAME.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NOMBRE</dt>
  <dd>Nombre de la clave</dd>
  <dt>ID</dt>
  <dd>ID de la clave</dd>
  <dt>-g</dt>
  <dd>Nombre de grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Mostrar el ID de clave de servicio. Esta opción es exclusiva con '--output'.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Nombre de grupo de recursos</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON. Esta opción es exclusiva con '--id'.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la clave de servicio `my-service-key`:
```
ibmcloud resource service-key my-service-key
```
<strong>Ejemplos</strong>:
Mostrar detalles de la clave de servicio con ID
`crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79`:

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crear una clave de servicio.
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

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Actualizar una clave de servicio.
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>Nombre o ID de la clave</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>Nuevo nombre de la clave</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>ID del grupo de recursos al que pertenece la clave</dd>
  <dt>-f, --force</dt>
  <dd>Forzar actualización sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar una clave de servicio llamada `my-service-key` y asignarle el nuevo nombre `my-service-key-2`:
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Suprimir una clave de servicio.
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>Nombre de la clave o el ID de la clave</dd>
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

Listar los alias de una instancia de servicio.
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID de la instancia de servicio de pertenencia.</dd>
  <dt>--instance-name</dt>
  <dd>Nombre de la instancia de servicio de pertenencia.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar alias de servicio de la instancia de servicio `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostrar detalles de un alias de servicio.
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>ALIAS_NAME (necesario)</dt>
  <dd>Nombre del alias de servicio</dd>
  <dt>--id</dt>
  <dd>Solo mostrará el ID del alias de servicio proporcionado. Se suprimirá el resto de la salida para el alias. Esta opción es exclusiva con '--output'.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>--output value  Especifique el formato de salida, ahora solo se da soporte a JSON. Esta opción es exclusiva con '--id'.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles del alias de servicio `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crear un alias de una instancia de servicio.
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

Actualizar un alias de servicio.
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

Suprimir un alias de servicio.
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

Buscar recursos utilizando la sintaxis de consultas de Lucene.
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Número de posición del recurso inicial</dd>
  <dt>-l, -limit</dt>
  <dd>Número de recursos que se deben devolver (máximo 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Propiedad por la que ordenar. Las entradas aceptadas son `name`, `family`, `region`, `type`, `crn`.</dd>
  <dt>-p, --provider</dt>
  <dd>Mostrar recursos de infraestructura clásica. El único valor permitido es:classic-infrastructure</dd>
</dl>

<strong>Atributos que se pueden buscar</strong>:
Puede buscar los atributos siguientes:

<dl>
  <dt>name</dt>
  <dd>El nombre del recurso definido por el usuario.</dd>
  <dt>region</dt>
  <dd>La ubicación geográfica en la que se suministra el recurso. Por ejemplo: us-south, us-east, au-syd, eu-gb, eu-de y jp-tok.</dd>
  <dt>service_name</dt>
  <dd>El nombre del servicio, tal como aparece en la columna Nombre de la salida de 'ibmcloud catalog service-marketplace'.</dd>
  <dt>family</dt>
  <dd>El componente de nube al que pertenece el recurso. Los valores permitidos son cloud_foundry, containers, resource_controller, vmware o ims.</dd>
  <dt>organization_id</dt>
  <dd>La GUID de la organización de Cloud Foundry.</dd>
  <dt>doc.space_id</dt>
  <dd>El GUID del espacio de Cloud Foundry.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>El ID del grupo de recursos.</dd>
  <dt>type</dt>
  <dd>El tipo de recurso. Los valores permitidos son k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup.</dd>
  <dt>creation_date</dt>
  <dd>La fecha en que se ha creado el recurso.</dd>
  <dt>modification_date</dt>
  <dd>La fecha de la última modificación del recurso. Tiene el formato aaaa-mm-ddThh:mm:ssZ </dd>
  <dt>_objectType</dt>
  <dd>El tipo del recurso de infraestructura clásica. Los valores permitidos son SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall y SoftLayer_Virtual_Guest. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>La etiqueta adjuntada a un recurso. Utilice tagReferences.tag.name al buscar etiquetas adjuntas para los recursos de infraestructura clásica </dd> 
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
{: codeblock}

Buscar el recurso de invitado virtual de infraestructura clásica con el ID especificado (solo con -p classic-infrastructure):
```
ibmcloud resource search 'id:12345678 _objectType:SoftLayer_Virtual_Guest'
```
{: codeblock}

Buscar el recurso de hardware de infraestructura clásica con el nombre de etiqueta especificado (solo con -p classic-infrastructure):
```
ibmcloud resource search 'tagReferences.tag.name:name _objectType:SoftLayer_Hardware'
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Listar todas las etiquetas en la cuenta de facturación

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Número de posición de etiqueta de inicio</dd>
  <dt>-l, -limit</dt>
  <dd>Número de etiquetas a devolver (10000 como máximo)</dd>
  <dt>-p; --provider</dt> 
  <dd>Especificar classic-infrastructure al buscar etiquetas de infraestructura clásica</dd>
  <dt>-d, --details</dt>
  <dd>Mostrar el número de recursos etiquetados.</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Adjuntar una o más etiquetas a un recurso:
```
ibmcloud resource tag-attach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```
<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-names(obligatorio)</dt>
  <dd>Lista separada por comas de nombres de etiqueta</dd>
  <dt>--resource-id</dt>
  <dd>CRN del recurso al que se van a adjuntar las etiquetas; para recursos de infraestructura clásica, es el ID del recurso</dd>
  <dt>--resource-type</dt>
  <dd>Tipo de recurso del recurso de infraestructura clásica al que se van a adjuntar las etiquetas; este parámetro es necesario si se adjunta una etiqueta a un recurso de infraestructura clásica. Los valores posibles para --resource-type son: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall y SoftLayer_Virtual_Guest. </dd>
</dl>

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Desvincular una o más etiquetas de un recurso:
```
ibmcloud resource tag-detach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-names(obligatorio)</dt>
  <dd>Lista separada por comas de nombres de etiqueta</dd>
  <dt>--resource-id</dt>
  <dd>CRN del recurso del que se van a desvincular las etiquetas; para recursos de infraestructura clásica, es el ID del recurso</dd>
  <dt>--resource-type</dt>
  <dd>Tipo de recurso del recurso de infraestructura clásica del que se van a desvincular las etiquetas; este parámetro es necesario si se adjunta una etiqueta a un recurso de infraestructura clásica. Los valores posibles para --resource-type son: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall y SoftLayer_Virtual_Guest. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Suprimir una etiqueta:
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--tag-name (necesario)</dt>
  <dd>Nombre de la etiqueta a suprimir.</dd>
  <dt>-p; --provider</dt> 
  <dd>Especificar classic-infrastructure al suprimir una etiqueta de infraestructura clásica</dd>
</dl>

Solo se puede suprimir una etiqueta si no se ha adjuntado a ningún recurso.
