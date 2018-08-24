---

copyright:

  years: 2018


lastupdated: "2018-08-15"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI generales (ibmcloud)
{: #ibmcloud_cli}


La interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} proporciona un conjunto de mandatos que se agrupan por espacio de nombres para que los usuarios interactúen con {{site.data.keyword.Bluemix_notm}}.

El cliente de línea de mandatos de {{site.data.keyword.Bluemix_notm}} empaqueta un cliente de línea de mandatos de Cloud Foundry en su instalación. Si tiene su propio cf cli instalado, no utilice los mandatos CLI de {{site.data.keyword.Bluemix_notm}} `ibmcloud [mandato]` ni los mandatos Cloud Foundry CLI `cf [mandato]` de su propia instalación en el mismo contexto. En su lugar, utilice `ibmcloud cf [mandato]` si desea utilizar cf cli para gestionar los recursos de Cloud Foundry en el contexto de CLI de {{site.data.keyword.Bluemix_notm}}.  Tenga en cuenta que `ibmcloud cf api/login/logout/target` no está permitido y debe utilizar `ibmcloud api/login/logout/target` en su lugar.

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.Bluemix_notm}} han cambiado de `bluemix` y `bx` a `ibmcloud`. Sin embargo, todavía puede utilizar los mandatos de CLI `bluemix` y `bx` hasta que se dejen de utilizar en una fecha posterior.
{: tip}

A continuación se enumeran los mandatos detallados que están soportados por la CLI de {{site.data.keyword.Bluemix_notm}}, incluidos sus nombres, argumentos, opciones, requisitos previos, descripciones y ejemplos.
{:shortdesc}

**Nota:** *Requisitos previos* lista las acciones que son necesarias antes de utilizar el mandato. Los mandatos que no tienen acciones de requisito previo listan **Ninguno**. De lo contrario, los requisitos previos pueden incluir una o varias de las acciones siguientes:

<dl>
<dt>Punto final</dt>
<dd>Un punto final de API se debe establecer por medio de la <code>bluemix api</code> antes de utilizar el mandato.</dd>
<dt>Login</dt>
<dd>El inicio de sesión que utiliza el mandato <code>bluemix login</code> es necesario antes de utilizar este mandato.
Si inicia sesión con un ID federado, utilice la opción '--sso' para autenticarse con un código de acceso de una sola vez o utilice '--apikey' para realizar la autenticación con una clave de API. Vaya a la consola de {{site.data.keyword.Bluemix_notm}} **Gestionar** &gt; **Seguridad** &gt; **Claves de API de plataforma** para crear claves de API.
</dd>
<dt>Target</dt>
<dd>El mandato <code>bluemix target</code> debe utilizarse para establecer un punto de extensión org y un espacio antes de utilizar este mandato.</dd>
<dt>Docker</dt>
<dd>La CLI de Docker CLI (docker) debe estar instalada para poder ejecutar este mandato.</dd>
</dl>


Utilice los índices de la tabla siguiente para hacer referencia a los mandatos ibmcloud.

## Mandatos generales ibmcloud
{: #ibmcloud_commands_index}

<table summary="Mandatos generales ibmcloud">
<caption>Tabla 1. Mandatos generales de ibmcloud</caption>
 <thead>
 <th colspan="5">Mandatos generales ibmcloud</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](bx_cli.html#ibmcloud_help)</td>
 <td>[ibmcloud api](bx_cli.html#ibmcloud_api)</td>
 <td>[ibmcloud config](bx_cli.html#ibmcloud_config)</td>
 <td>[ibmcloud info](bx_cli.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](bx_cli.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](bx_cli.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](bx_cli.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](bx_cli.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](bx_cli.html#ibmcloud_target)</td>
 <td>[ibmcloud update](bx_cli.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud help
{: #ibmcloud_help}
Muestra la ayuda general para mandatos incorporados de primer nivel y espacios de nombres soportados de la CLI de {{site.data.keyword.Bluemix_notm}}, o la ayuda para un mandato o un espacio de nombres incorporado específico.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (opcional)</dt>
   <dd>Mandato o espacio de nombres para el que se visualiza ayuda. Si no se especifica, se mostrará la ayuda general de la CLI de {{site.data.keyword.Bluemix_notm}}.</dd>
   </dl>



<strong>Ejemplos</strong>:

Visualiza ayuda general de la CLI de {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud help
```

Muestra ayuda para el mandato `info`:

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
Establezca o visualice el punto final de su API de {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>API_ENDPOINT (opcional)</dt>
   <dd>Punto final de API de destino, por ejemplo, `https://api.chinabluemix.net`. Si no se especifican ambas opciones *API_ENDPOINT* y `--unset`, se mostrará el punto final de API actual.</dd>
   <dt>--unset (opcional)</dt>
   <dd>Elimina la configuración del punto final de la API.</dd>
   <dt>--skip-ssl-validation (opcional)</dt>
   <dd>Omite la validación SSL de solicitudes HTTP.</dd>
   </dl>
<strong>Ejemplos</strong>:

Establecer el punto final de la API en api.chinabluemix.net:

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

Visualice el punto final de la API actual:

```
ibmcloud api
```

Desestablecer el punto final de la API:

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


Escriba valores predeterminados en el archivo de configuración.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Valor de tiempo de espera para solicitudes HTTP. El valor predeterminado es de 60 segundos.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Rastrear solicitudes HTTP al terminal o archivo especificado.</dd>
   <dt>--color true|false</dt>
   <dd>Habilitar o inhabilitar la salida de color. La salida de color está habilitada de forma predeterminada.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Establecer un entorno local predeterminado. Si LOCALE es <i>CLEAR</i>, el entorno local anterior se elimina.</dd>
   <dt>--check-version true|false</dt>
   <dd>Habilitar o inhabilitar la comprobación de la versión de la CLI.</dd>
   </dl>

Sólo se puede especificar una de estas opciones a la vez.

<strong>Ejemplos</strong>:

Establezca el tiempo de espera de solicitud HTTP en 30 segundos:

```
ibmcloud config --http-timeout 30
```

Habilitar la salida de rastreo para las solicitudes HTTP:

```
ibmcloud config --trace true
```

Rastrear solicitudes HTTP a un archivo determinado */home/usera/my_trace*:

```
ibmcloud config --trace /home/usera/my_trace
```

Inhabilitar la salida de color:

```
ibmcloud config --color false
```

Establecer el entorno local en zh_Hans:

```
ibmcloud config --locale zh_Hans
```

Borrar los valores de entorno local:

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

Vea la información básica de {{site.data.keyword.Bluemix_notm}}, incluida la región actual, la versión del controlador de nube y algunos puntos finales útiles, como por ejemplo los puntos finales para el inicio de sesión y el intercambio de señales de acceso.

```
ibmcloud info
```

<strong>Requisitos previos</strong>: Punto final

## ibmcloud cf
{: #ibmcloud_cf}

Invocar CLI CF incluido

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Desactivar el mensaje "Invocando el mandato cf..."</dd>
</dl>

<strong>Ejemplos</strong>:

Listar apps cf:

```
ibmcloud cf apps
```

Listar servicios cf sin el mensaje "Invocando el mandato cf...":

```
ibmcloud -q cf services
```

## ibmcloud login
{: #ibmcloud_login}

Inicio de sesión de usuario.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>Requisitos previos</strong>:  Ninguno

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opciones de mandato</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (opcional)</dt>
  <dd> Punto final de la API (por ejemplo: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY o @API_KEY_FILE_PATH</i>
  <dd> Contenido de clave de API o la vía de acceso a un archivo de clave de API indicado mediante @</dd>
  <dt> --sso (opcional) </dt>
  <dd> Utilizar un código de acceso de un solo uso para iniciar sesión </dd>
  <dt> -u <i>USERNAME</i> (opcional)</dt>
  <dd> Nombre de usuario</dd>
  <dt> -p <i>PASSWORD</i> (opcional)</dt>
  <dd> Contraseña</dd>
  <dt> -c <i>ACCOUNT_ID</i> (opcional) </dt>
  <dd> ID de la cuenta de destino. Esta opción es exclusiva con --no-account</dd>
  <dt> --no-account (opcional) </dt>
  <dd> Forzar inicio de sesión sin una cuenta. No se recomienda esta opción. Esta opción es exclusiva con -c.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (opcional) </dt>
  <dd> Nombre del grupo de recursos de destino</dd>
  <dt> -o <i>ORG</i> (opcional)</dt>
  <dd> Nombre de la organización de destino (en desuso, utilizar 'ibmcloud target -o ORG')</dd>
  <dt> -s <i>SPACE</i> (opcional) </dt>
  <dd> Nombre del espacio de destino (en desuso, utilizar 'ibmcloud target -s SPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Forzar la autenticación con el servidor de inicio de sesión en lugar del IAM público</dd>
  <dt> --skip-ssl-validation (opcional) </dt>
  <dd> Omite la validación SSL de solicitudes HTTP. No se recomienda esta opción.</dd>
</dl>

<strong>Ejemplos</strong>:

### Inicio de sesión interactivo

```
ibmcloud login
```

Iniciar sesión con un nombre de usuario y su contraseña, estableciendo un espacio, una organización y una cuenta de destino:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con un código de acceso de una sola vez, estableciendo una cuenta, una organización y un espacio de destino

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con una clave de API y estableciendo destinos:

### La clave de API tiene asociada una cuenta

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### La clave de API no tiene asociada una cuenta

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> Si la clave de API tiene asociada una cuenta, no se permite conmutar a otra cuenta.

### Utilizar un código de acceso de una sola

```
ibmcloud login -u UserID --sso
```

A continuación, la CLI proporcionará un enlace de URL y pedirá el código de acceso:
```
Código de un solo uso (obtenga uno en https://enlace_URL_para_obtener_código_acceso):
```

Abra el enlace en el navegador, que le guiará para obtener el código de acceso. Escriba el código de acceso en la consola y podrá iniciar la sesión.

## ibmcloud logout
{: #ibmcloud_logout}

Cerrar sesión de usuario.

```
ibmcloud logout
```

<strong>Requisitos previos</strong>:  Ninguno

## ibmcloud regions
{: #ibmcloud_regions}

Visualiza la información para todas las regiones en {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Requisitos previos</strong>: Punto final

## ibmcloud target
{: #ibmcloud_target}


Establece o visualiza la cuenta, región, organización o espacio de destino.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nombre de la región a la que se conmutará, como por ejemplo 'us-south' o 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (opcional)</dt>
   <dd>ID de la cuenta de destino.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (opcional)</dt>
   <dd>Nombre de grupo de recursos</dd>
   <dt>--cf</dt>
   <dd>Seleccionar interactivamente la organización y el espacio de destino</dd>
   <dt>-o <i>ORG_NAME</i> (opcional)</dt>
   <dd>Nombre de la organización de destino.</dd>
   <dt>-s <i>SPACE_NAME</i> (opcional)</dt>
   <dd>Nombre del espacio de destino.</dd>
   </dl>
Si no se especifica ninguna opción, se visualiza la cuenta, la región, la organización y el espacio actuales.

<strong>Ejemplos</strong>:

Establecer la cuenta, organización y espacio actuales:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Cambiar a una nueva región:

```
ibmcloud target -r eu-gb
```

Visualiza la cuenta, región, organización y espacio actual:

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

Actualiza la CLI a la última versión.

```
ibmcloud update [-f]
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forzar actualización sin confirmación. Se necesita el privilegio raíz.</dd>
</dl>


## Mandatos de CLI generales (ibmcloud sl)
{: #softlayer_cli}


Utilice los mandatos de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} en la interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} para configurar y gestionar los servicios de SoftLayer.

Se da soporte a los mandatos siguientes. Utilice el mandato `ibmcloud sl` para ver la lista de mandatos disponibles:

<table summary="Mandatos ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/ibmcloud/bx_cli.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/ibmcloud/bx_cli.html#sl_help)</td>
   </tbody>
 </table>

 Para ver la información de ayuda de los mandatos, ejecute: `ibmcloud sl [command] -h`

 ## ibmcloud sl init
{: #sl_init}

Inicialice los valores de configuración que se utilizan para conectarse al entorno de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}. La configuración incluye nombre de usuario, contraseña o una clave de API, cuenta y punto final.
```
ibmcloud sl init [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL de punto final de API de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}, el valor predeterminado es: https://api.softlayer.com/rest/v3.1 para la autenticación de claves de API, https://api.softlayer.com/mobile/v3.1 para la autenticación de IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nombre de usuario de infraestructura Gen1.</dd>
<dt>-p, --sl-password</dt>
<dd>contraseña o clave de API.</dd>
<dt>-c, --account-id</dt>
<dd>ID de cuenta.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID de pregunta de seguridad utilizado para autenticar. Pregunte al propietario de la cuenta si no lo conoce.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Respuesta a la pregunta de seguridad utilizada para autenticar. Pregunte al propietario de la cuenta si no la conoce.</dd>
<dt>-s, --security-code</dt>
<dd>Código de seguridad generado por el proveedor de seguridad cuando está habilitada la autenticación de 2 factores.</dd>
<dt>-v, --security-vendor</dt>
<dd>Proveedor de seguridad que proporciona código de seguridad para la autenticación. Las opciones son: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Señal de autenticación cuando se habilita la autenticación telefónica.</dd>
</dl>

Por ejemplo, inicie la sesión con nombre de usuario y contraseña/clave de API de {{site.data.keyword.BluSoftlayer_notm}}
```
$ ibmcloud sl init
Elija cómo configurar la autenticación de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}:
1. Iniciar sesión con nombre de usuario y contraseña/clave de API de {{site.data.keyword.BluSoftlayer_notm}}
2. Utilizar inicio de sesión único de {{site.data.keyword.Bluemix_notm}}
Escriba un número>1
URL de punto final de API de Softlayer: [https://api.softlayer.com/rest/v3.1]>
Nombre de usuario: []> user@example.com
Clave de API o contraseña: []> abcd

Punto final de API:    https://api.softlayer.com/rest/v3.1
Nombre de usuario:       user@example.com
Clave de API:         xxxxxxxxxx
```
Por ejemplo, utilice el inicio de sesión único de {{site.data.keyword.Bluemix_notm}} para iniciar la sesión en Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
Punto final de API: api.ng.bluemix.net
Autenticando...
OK

Cuenta de usuario de ejemplo de cuenta de destino (65ce8074c6c62b5)

Punto final de la API:   https://api.ng.bluemix.net (Versión de la API: 2.54.0)   
Región:         us-south
Usuario:           user@example.com
Cuenta:        Cuenta de usuario example (65ce8074c6c62b5)   
Ninguna organización ni espacio de destino. Utilice 'ibmcloud target --cf o ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Elija cómo configurar la autenticación de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}:

1. Iniciar sesión con nombre de usuario y contraseña/clave de API de Softlayer
2. Utilice inicio de sesión único de IBM Cloud
Especifique un número> 2
URL de punto final de API de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}: [https://api.softlayer.com/mobile/v3.1]>
Estableciendo la cuenta en: 123456
OK

Punto final de API de {{site.data.keyword.BluSoftlayer_notm}}:    https://api.softlayer.com/mobile/v3.1   

ID de cuenta:                123456
ID de usuario:                   user@example.com
Señal de IMS:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Ver la información de ayuda para que todos los mandatos operen en el entorno de {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help
```
