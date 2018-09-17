---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Claves de API, identidad y acceso
{: #ibmcloud_commands_iam}

Utilice los mandatos siguientes para gestionar las claves de API, los ID de servicio, los grupos de acceso y las políticas de acceso/autorización para IAM.
{: shortdesc}

<table summary="Mandatos de Bluemix que puede utilizar para gestionar claves de API y políticas.">
  <thead>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-ids](cli_api_policy.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam service-id](cli_api_policy.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](cli_api_policy.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](cli_api_policy.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](cli_api_policy.html#ibmcloud_iam_service_id_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-id-lock](cli_api_policy.html#ibmcloud_iam_service_id_lock)</td>
   <td>[ibmcloud iam service-id-unlock](cli_api_policy.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam api-keys](cli_api_policy.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](cli_api_policy.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](cli_api_policy.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](cli_api_policy.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](cli_api_policy.html#ibmcloud_iam_api_key_lock)</td>
   <td>[ibmcloud iam api-key-unlock](cli_api_policy.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](cli_api_policy.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](cli_api_policy.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](cli_api_policy.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](cli_api_policy.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](cli_api_policy.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-api-key-lock](cli_api_policy.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[ibmcloud iam service-api-key-unlock](cli_api_policy.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-policies](cli_api_policy.html#ibmcloud_iam_service_policies)</td>
   <td>[ibmcloud iam service-policy](cli_api_policy.html#ibmcloud_iam_service_policy)</td>
   <td>[ibmcloud iam service-policy-create](cli_api_policy.html#ibmcloud_iam_service_policy_create)</td>
   <td>[ibmcloud iam service-policy-update](cli_api_policy.html#ibmcloud_iam_service_policy_update)</td>
   <td>[ibmcloud iam service-policy-delete](cli_api_policy.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](cli_api_policy.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](cli_api_policy.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](cli_api_policy.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](cli_api_policy.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](cli_api_policy.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam oauth-tokens](cli_api_policy.html#ibmcloud_iam_oauth_tokens)</td>
   <td>[ibmcloud iam dedicated-id-disconnect](cli_api_policy.html#ibmcloud_iam_dedicated_id_disconnect)</td>
   <td>[ibmcloud iam authorization-policy-create](cli_api_policy.html#ibmcloud_iam_authorization_policy_create)</td>
   <td>[ibmcloud iam authorization-policy-delete](cli_api_policy.html#ibmcloud_iam_authorization_policy_delete)</td>
   <td>[ibmcloud iam authorization-policy](cli_api_policy.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam authorization-policies](cli_api_policy.html#ibmcloud_iam_authorization_policies)</td>
   <td>[ibmcloud iam access-groups](cli_api_policy.html#ibmcloud_iam_access_groups)</td>
   <td>[ibmcloud iam access-group](cli_api_policy.html#ibmcloud_iam_access_group)</td>
   <td>[ibmcloud iam access-group-create](cli_api_policy.html#ibmcloud_iam_access_group_create)</td>
   <td>[ibmcloud iam access-group-update](cli_api_policy.html#ibmcloud_iam_access_group_update)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-delete](cli_api_policy.html#ibmcloud_iam_access_group_delete)</td>
   <td>[ibmcloud iam access-group-users](cli_api_policy.html#ibmcloud_iam_access_group_users)</td>
   <td>[ibmcloud iam access-group-user-add](cli_api_policy.html#ibmcloud_iam_access_group_user_add)</td>
   <td>[ibmcloud iam access-group-user-remove](cli_api_policy.html#ibmcloud_iam_access_group_user_remove)</td>
   <td>[ibmcloud iam access-group-user-purge](cli_api_policy.html#ibmcloud_iam_access_group_user_purge)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-service-ids](cli_api_policy.html#ibmcloud_iam_access_group_service_ids)</td>
   <td>[ibmcloud iam access-group-service-id-add](cli_api_policy.html#ibmcloud_iam_access_group_service_id_add)</td>
   <td>[ibmcloud iam access-group-service-id-remove](cli_api_policy.html#ibmcloud_iam_access_group_service_id_remove)</td>
   <td>[ibmcloud iam access-group-service-id-purge](cli_api_policy.html#ibmcloud_iam_access_group_service_id_purge)</td>
   <td>[ibmcloud iam access-group-policies](cli_api_policy.html#ibmcloud_iam_access_group_policies)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-policy](cli_api_policy.html#ibmcloud_iam_access_group_policy)</td>
   <td>[ibmcloud iam access-group-policy-create](cli_api_policy.html#ibmcloud_iam_access_group_policy_create)</td>
   <td>[ibmcloud iam access-group-policy-update](cli_api_policy.html#ibmcloud_iam_access_group_policy_update)</td>
   <td>[ibmcloud iam access-group-policy-delete](cli_api_policy.html#ibmcloud_iam_access_group_policy_delete)</td>
  </tr>
  </tbody>
  </table>

  ## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Lista todos los ID de servicio

```
ibmcloud iam service-ids [--uuid]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Mostrar UUID solo de los ID de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Lista de UUID de todos los ID de servicio bajo la cuenta actual

```
ibmcloud iam service-ids --uuid
```

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Mostrar detalles de un ID de servicio

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>--uuid</dt>
  <dd>Mostrar el UUID del ID de servicio</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de ID de servicio `sample-test`

```
ibmcloud iam service-id sample-test
```
Mostrar detalles del ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Crear un ID de servicio

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio</dd>
  <dt>-d, --description</dt>
  <dd>Descripción del ID de servicio</dd>
  <dt>--lock</dt>
  <dd>Bloquear el ID de servicio cuando se cree</dd>
</dl>

<strong>Ejemplos</strong>:

Crear un ID de servicio con nombre de servicio `sample-test` y descripción `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Crear un ID de servicio bloqueado con el nombre de servicio `sample-test` y la descripción `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```

## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Actualizar un ID de servicio

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de servicio</dd>
  <dt>-d, --description</dt>
  <dd>Nueva descripción del servicio</dd>
  <dt>-f, --force</dt>
  <dd>Actualizar sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Renombrar el ID de servicio `sample-test` a `sample-test-2` sin confirmación

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Actualizar descripción de servicio `sample-test`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Renombrar el ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` a `sample-test-3` con una nueva descripción

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Suprimir un ID de servicio

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir ID de servicio `sample-teset` sin confirmación

```
ibmcloud iam service-id-delete sample-teset -f
```

Suprimir el ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Bloquear un ID de servicio

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear ID de servicio `sample-teset` sin confirmación

```
ibmcloud iam service-id-lock sample-teset -f
```

Bloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Desbloquear un ID de servicio

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Desbloquear ID de servicio `sample-teset` sin confirmación

```
ibmcloud iam service-id-unlock sample-teset -f
```

Desbloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Lista todas las claves de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crear una nueva clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a crear.</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>Descripción de la clave de API</dd>
<dt>--file <i>ARCHIVO</i></dt>
<dd>Guarda la información de la clave de API en un archivo especificado. Si no se establece, se visualiza el contenido JSON.</dd>
<dt>--lock</dt>
<dd>Bloquear la clave de API cuando se cree</dd>
</dl>

<strong>Ejemplos</strong>:

Crea una clave de API y la guarda en un archivo

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Crear una clave de API bloqueada con el nombre "test-key"

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Actualizar una clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>El nombre antiguo de la clave de API a actualizar, exclusivo con UUID</dd>
<dt>UUID (necesario)</dt>
<dd>El UUID de la clave de API a actualizar, exclusivo con NAME</dd>
<dt>-n <i>NAME</i> (opcional)</dt>
<dd>Nuevo nombre de la clave de API</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>Nueva descripción de la clave de API</dd>
</dl>

<strong>Ejemplos</strong>:

Actualiza la descripción de una clave de API:

```
ibmcloud iam api-key-update MyKey -d "la nueva descripción de mi clave"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Suprimir una clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a suprimir, exclusivo con UUID</dd>
<dt>UUID (necesario)</dt>
<dd>UUID de la clave de API a suprimir, exclusivo con NAME</dd>
<dt>-f, --force</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

Bloquear una clave de API de plataforma

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a bloquear, exclusivo con UUID</dd>
<dt>UUID (necesario)</dt>
<dd>UUID de la clave de API a bloquear, exclusivo con NAME</dd>
<dt>-f, --force</dt>
<dd>Forzar bloqueo sin confirmación.</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear clave de API test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

Bloquear clave de API con UUID proporcionado sin confirmación

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Desbloquear una clave de API de plataforma

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a desbloquear, exclusivo con UUID</dd>
<dt>UUID (necesario)</dt>
<dd>UUID de la clave de API a desbloquear, exclusivo con NAME</dd>
<dt>-f, --force</dt>
<dd>Forzar desbloqueo sin confirmación.</dd>
</dl>

<strong>Ejemplos</strong>:

Desbloquear la clave de API test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

Desbloquear clave de API con UUID proporcionado sin confirmación

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Listar todas las claves de API de un servicio

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Mostrar las claves de API de servicio sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todas las claves de API de un servicio `sample-service` :

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Listar detalles de una clave de API de servicio

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>Visualice el UUID de la clave de API de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Mostrar las claves de API de servicio sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar los detalles de una clave de API de servicio `sample-key` del servicio `sample-service` :

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Crear una clave de API de servicio

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del ID de servicio o clave de API de servicio recién creada</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Descripción de la clave de API</dd>
  <dt>--file</dt>
  <dd>Guarda la información de la clave de API en un archivo especificado. Si no se establece, se visualiza el contenido JSON.</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la creación sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una clave de API de servicio `sample-key` para el servicio `sample-service` sin confirmación:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Actualizar una clave de API de servicio

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de la clave de API de servicio</dd>
  <dt>-d, --description</dt>
  <dd>Nueva descripción de la clave de API de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Actualizar sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Renombrar la clave de API de servicio `sample-key` a `new-sample-key`:

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Suprimir una clave de API de servicio

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir clave de API de servicio `sample-key` del ID de servicio `sample-service`:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Bloquear una clave de API de servicio

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear clave de API de servicio `sample-key` del ID de servicio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Desbloquear una clave de API de servicio

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Desbloquear clave de API de servicio `sample-key` del ID de servicio `sample-service`:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Lista de políticas de usuario `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenecen las políticas</dd>
</dl>

<strong>Ejemplos</strong>:

Lista de políticas de usuario `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Mostrar detalles de una política de usuario

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenece la política</dd>
<dt>POLICY_ID (necesario)</dt>
<dd>ID de la política</dd>
</dl>

<strong>Ejemplos</strong>:

Lista de política `0bb730daa` de usuario `name@example.com`:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Crear una política de usuario

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenece la política</dd>
<dt>--file <i>ARCHIVO</i> (opcional)</dt>
<dd>Archivo JSON de definición de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nombre de servicio de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (opcional)</dt>
<dd>GUID de la instancia de servicio de la definición de política. Esto es exclusivo con el distintivo '--file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Región de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nombre del grupo de recursos. Es exclusivo con los distintivos '--file', '--resource' y '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID del grupo de recursos. Es exclusivo con los distintivos '--file', '--resource' y '--resource-group-name'.</dd>
</dl>

<strong>Ejemplos</strong>:

Crear política de usuario para el usuario `name@example.com` desde el archivo JSON de política `policy.json`:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

Proporcione a `name@example.com` el rol de `Administrador` para todos los recursos de `sample-service`:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Proporcione a `name@example.com` el rol de `Editor` para el recurso `key123` de la instancia de servicio de ejemplo con el GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` en la región `us-south`:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Proporcione a `name@example.com` el rol de `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Proporcione a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos `sample-resource-group`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Proporcione a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Actualizar una política de usuario

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenece la política</dd>
<dt>POLICY_ID (necesario)</dt>
<dd>ID de la política a actualizar</dd>
<dt>--file <i>ARCHIVO</i> (opcional)</dt>
<dd>Archivo JSON de definición de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nombre de servicio de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (opcional)</dt>
<dd>GUID de la instancia de servicio de la definición de política. Esto es exclusivo con el distintivo '--file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Región de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso de la definición de política. Es exclusivo con el distintivo '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nombre del grupo de recursos. Es exclusivo con los distintivos '--file', '--resource' y '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID del grupo de recursos. Es exclusivo con los distintivos '--file', '--resource' y '--resource-group-name'.</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar la política de usuario con la del archivo JSON：

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Administrador` para todos los recursos de `sample-service`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Actualizar la política de usuario para dar a `name@example.com` el rol de `Editor` para el recurso `key123` de la instancia de servicio de ejemplo con la GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` en la región `us-south`:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos `sample-resource-group`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Suprimir una política de usuario

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Suprimir la política de usuario sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir las políticas `user-policy-id` del usuario `name@example.com`:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Suprimir las políticas `user-policy-id` del usuario `name@example.com` sin confirmación:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Listar todas las políticas de servicio del servicio especificado

```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida de políticas de servicio; actualmente solo se admite JSON.</dd>
  <dt>-f, --force (opcional)</dt>
  <dd>Mostrar las políticas de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Lista de políticas de servicio `test`:

```
ibmcloud iam service-policies test
```
Listar políticas de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Mostrar detalles de una política de servicio

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida de política de servicio; actualmente solo se admite JSON.</dd>
  <dt>-f, --force (opcional)</dt>
  <dd>Mostrar la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar la política `140798e2-8ea7db3` de servicio `test`:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Mostrar la política `140798e2-8ea7db3` del servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Crear una política de servicio

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>--file</dt>
  <dd>Archivo JSON de definición de política. Esta opción y los distintivos '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' y '--resource-group-id' son excluyentes.</dd>
  <dt>-r, --roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID de instancia de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-name' son mutuamente excluyentes.</dd>
  <dt>-f, --force</dt>
  <dd>Crear la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Crear la política de servicio desde el archivo JSON para el servicio `test`:

```
ibmcloud iam service-policy-create test --file @policy.json
```
Crear una política de servicio desde el archivo JSON para el servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Actualizar una política de servicio

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>--file</dt>
  <dd>Archivo JSON de definición de política. Esta opción y los distintivos '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' y 'resource-group-id' son excluyentes.</dd>
  <dt>-r, --roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID de instancia de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-name' son mutuamente excluyentes.</dd>
  <dt>-f, --force</dt>
  <dd>Actualizar la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar la política de servicio `140798e2-8ea7db3` desde el archivo JSON para el servicio `test`:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Actualizar la política de servicio `140798e2-8ea7db3` desde un archivo JSON para el servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Suprimir una política de servicio

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir la política `140798e2-8ea7db3` del servicio `test`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Suprimir la política `140798e2-8ea7db3` del servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Recuperar y visualizar las señales OAuth para la sesión actual

```
ibmcloud iam oauth-tokens
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Actualizar y visualizar las señales OAuth

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Desconectar el IBMid público con el IBMid no de IBM dedicado

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forzar la desconexión sin confirmación</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Crear una política de autorización para permitir a una instancia de servicio acceder a otra instancia de servicio.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Servicio de origen que está autorizado para acceder.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Servicio de destino al que el servicio de origen está autorizado para acceder.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Los roles que dan acceso al servicio de origen.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nombre de instancia de servicio de origen; si no se especifica, todas las instancias de servicio de origen estarán autorizadas para acceder.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nombre de instancia de servicio de destino; si no se especifica, todas las instancias de servicio de destino estarán autorizadas para acceder.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Suprimir una política de autorización.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la política de autorización que se va a suprimir.</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Mostrar detalles de una política de autorización.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de autorización de la política que se va a mostrar.</dd>
</dl>

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Listar políticas de autorización en la cuenta actual.

```
ibmcloud iam authorization-policies
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Listar grupos de acceso en la cuenta actual

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-u</dt>
  <dd>Listar grupos de acceso a los que pertenece el usuario. Este distintivo es exclusivo de '-s'.</dd>
  <dt>-s</dt>
  <dd>Listar grupos de acceso a los que pertenece el ID de servicio. Este distintivo es exclusivo de '-u'.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todos los grupos de acceso:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Mostrar detalles de un grupo de acceso

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-id</dt>
  <dd>Mostrar solo ID</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles del grupo de acceso `example_group`:

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Crear un grupo de acceso

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descripción de un grupo de acceso</dd>
</dl>

<strong>Ejemplos</strong>:

Crear el grupo de acceso `example_group`:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Actualizar un grupo de acceso

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de grupo de acceso</dd>
  <dt>-d, --description</dt>
  <dd>Nueva descripción</dd>
  <dt>-f, --force</dt>
  <dd>Forzar actualización sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Renombrar el grupo de acceso `example_group` como `hello_world_group`:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Suprimir un grupo de acceso

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
  <dt>-r, --recursive</dt>
  <dd>Suprimir el grupo de acceso y sus miembros</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir el grupo de acceso `example_group`:

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Listar usuarios en un grupo de acceso

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todos los usuarios del grupo de acceso `example_group`:

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Agregar usuarios a un grupo de acceso

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Agregar el usuario `name@example.com` al grupo de acceso `example_group`:

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Eliminar un usuario de un grupo de acceso

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Eliminar el usuario `name@example.com` del grupo de acceso `example_group`:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Eliminar un usuario de todos los grupos de acceso

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Eliminar el usuario `name@example.com` de todos los grupos de acceso:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Listar ID de servicio en un grupo de acceso

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todos los ID de servicio del grupo de acceso `example_group`:

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Añadir un ID de servicio a un grupo de acceso

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Añadir el ID de servicio `example-service` al grupo de acceso `example_group`:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Eliminar un ID de servicio de un grupo de acceso

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Eliminar el ID de servicio `example-service` del grupo de acceso `example_group`:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Eliminar el ID de servicio de todos los grupos de acceso

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Eliminar el ID de servicio `example-service` de todos los grupos de acceso:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Listar las políticas de un grupo de acceso

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todas las políticas del grupo de acceso `example_group`:

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Mostrar detalles de una política de grupo de acceso

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la política `51b9717e-76b0-4f6a-bda7-b8132431f926` del grupo de acceso `example_group`:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Crear una política de grupo de acceso

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--file</dt>
  <dd>Archivo JSON de definición de política</dd>
  <dt>-roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID de instancia de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-name' son mutuamente excluyentes.</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una política de grupo de acceso desde un archivo JSON:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Proporcionar a `example_group` el rol `Administrador` para todos los recursos `sample-service`:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Proporcionar a `example_group` el rol `Editor` para el recurso `key123` de la instancia `sample-service` con el GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` en la región `us-south`:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Proporcionar a `example_group` el rol `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Proporcionar a `example_group` el rol de `Visor` para los miembros del grupo de recursos `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Proporcionar a `example_group` el rol `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Actualizar una política de grupo de acceso

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--file</dt>
  <dd>Archivo JSON de definición de política</dd>
  <dt>--roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID de instancia de servicio de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '--file' son mutuamente excluyentes.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del grupo de recursos. Esta opción y los distintivos '--file' y '--resource-group-name' son mutuamente excluyentes.</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar la política de grupo de acceso con la que se encuentra en el archivo JSON de política:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Actualizar la política de grupo de acceso para proporcionar a `example_group` el rol `Administrador` para todos los recursos `sample-service`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Actualizar la política de grupo de acceso para proporcionar a `example_group` el rol `Editor` para el recurso `key123` de la instancia `sample-service` con el GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` en la región `us-south`:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Actualizar la política de grupo de acceso para proporcionar a `example_group` el rol `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Actualizar la política de grupo de acceso para proporcionar a `example_group` el rol `Visor` para los miembros del grupo de recursos `sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Actualizar la política de grupo de acceso para proporcionar a `example_group` el rol `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Suprimir una política de grupo de acceso

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir la política `51b9717e-76b0-4f6a-bda7-b8132431f926` del grupo de acceso `example_group`:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
