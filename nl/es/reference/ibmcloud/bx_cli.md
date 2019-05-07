---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-26"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Mandatos de CLI generales (ibmcloud)
{: #ibmcloud_cli}

La interfaz de línea de mandatos (CLI) de {{site.data.keyword.cloud_notm}} proporciona un conjunto de mandatos que se agrupan por espacio de nombres para que los usuarios interactúen con {{site.data.keyword.cloud_notm}}.

El cliente de línea de mandatos de {{site.data.keyword.cloud_notm}} empaqueta un cliente de línea de mandatos de Cloud Foundry en su instalación. Si tiene su propia cli de cf instalada, no utilice ambos mandatos de CLI de {{site.data.keyword.cloud_notm}} `ibmcloud [mandato]` ni los mandatos Cloud Foundry CLI `cf [mandato]` de su propia instalación en el mismo contexto. En su lugar, utilice `ibmcloud cf [mandato]` si desea utilizar cf cli para gestionar los recursos de Cloud Foundry en el contexto de CLI de {{site.data.keyword.cloud_notm}}. Tenga en cuenta que `ibmcloud cf api/login/logout/target` no está permitido y debe utilizar `ibmcloud api/login/logout/target` en su lugar.

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.cloud_notm}} han cambiado de `bluemix` y `bx` a `ibmcloud`. Sin embargo, puede seguir utilizando los mandatos de CLI `bluemix` y `bx` hasta que se eliminen más adelante.
{: tip}

A continuación se enumeran los mandatos detallados que están soportados por la CLI de {{site.data.keyword.cloud_notm}}, incluidos sus nombres, argumentos, opciones, requisitos previos, descripciones y ejemplos.
{: shortdesc}

*Requisitos previos* lista las acciones que son necesarias antes de utilizar el mandato. Los mandatos que no tienen acciones de requisito previo listan **Ninguno**. De lo contrario, los requisitos previos pueden incluir una o varias de las acciones siguientes:

<dl>
<dt>Punto final</dt>
<dd>Un punto final de API se debe establecer por medio de la <code>ibmcloud api</code> antes de utilizar el mandato.</dd>
<dt>Login</dt>
<dd>El inicio de sesión que utiliza el mandato <code>ibmcloud login</code> es necesario antes de utilizar este mandato.
Si inicia sesión con un ID federado, utilice la opción '--sso' para autenticarse con un código de acceso de un solo uso o utilice '--apikey' para realizar la autenticación con una clave de API.
</dd>
<dt>Target</dt>
<dd>El mandato <code>ibmcloud target</code> debe utilizarse para establecer un punto de extensión org y un espacio antes de utilizar este mandato.</dd>
<dt>Docker</dt>
<dd>La CLI de Docker CLI (docker) debe estar instalada para poder ejecutar este mandato.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Muestra la ayuda general para mandatos incorporados de primer nivel y espacios de nombres soportados de la CLI de {{site.data.keyword.cloud_notm}}, o la ayuda para un mandato o un espacio de nombres incorporado específico.

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

Visualiza ayuda general de la CLI de {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Muestra ayuda para el mandato `dev`:
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Establezca o visualice el punto final de su API de {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>API_ENDPOINT (opcional)</dt>
   <dd>Punto final de API de destino, por ejemplo, `https://cloud.ibm.com`. Si no se especifican ambas opciones *API_ENDPOINT* y `--unset`, se mostrará el punto final de API actual.</dd>
   <dt>--unset (opcional)</dt>
   <dd>Elimina la configuración del punto final de la API.</dd>
   <dt>--skip-ssl-validation (opcional)</dt>
   <dd>Omite la validación SSL de solicitudes HTTP.</dd>
   </dl>
<strong>Ejemplos</strong>:

Establecer el punto final de la API en cloud.ibm.com:
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

Visualice el punto final de la API actual:
```
ibmcloud api
```
{: codeblock}

Desestablecer el punto final de la API:
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Escriba valores predeterminados en el archivo de configuración.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Valor de tiempo de espera para solicitudes HTTP. El valor predeterminado es de 60 segundos.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Rastrear solicitudes HTTP al terminal o archivo especificado.</dd>
   <dt>--color true|false</dt>
   <dd>Habilitar o inhabilitar la salida de color. La salida de color está habilitada de forma predeterminada.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Establecer un entorno local predeterminado. Si LOCALE es <i>CLEAR</i>, el entorno local anterior se suprime.</dd>
   <dt>--check-version true|false</dt>
   <dd>Habilitar o inhabilitar la comprobación de la versión de la CLI.</dd>
   </dl>

Sólo se puede especificar una de estas opciones a la vez.

<strong>Ejemplos</strong>:

Establezca el tiempo de espera de solicitud HTTP en 30 segundos:
```
ibmcloud config --http-timeout 30
```
{: codeblock}

Habilitar la salida de rastreo para las solicitudes HTTP:
```
ibmcloud config --trace true
```
{: codeblock}

Rastrear solicitudes HTTP a un archivo determinado */home/usera/my_trace*:
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Inhabilitar la salida de color:
```
ibmcloud config --color false
```
{: codeblock}

Establecer el entorno local en zh_Hans:
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

Borrar los valores de entorno local:
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

El mandato `ibmcloud info` ya no está disponible a partir de la versión `0.14` de la CLI. Para instalar la versión más reciente de la CLI, consulte [Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

Invocar CLI CF incluido
```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Requisitos previos</strong>: Ninguno

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
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Inicio de sesión de usuario.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>Requisitos previos</strong>: Ninguno

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opciones de mandato</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (opcional)</dt>
  <dd> Punto final de la API (por ejemplo: cloud.ibm.com)</dd>
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
  <dt> -r REGION</dt>
  <dd> Nombre de la región, como por ejemplo 'us- south' o 'eu- gb'</dt>
  <dt> --no-region</dt>
  <dd> Forzar inicio de sesión sin una región objetivo.</dd>
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
{: codeblock}

Iniciar sesión con un nombre de usuario y su contraseña, estableciendo un espacio, una organización y una cuenta de destino:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con un código de acceso de un solo uso, estableciendo una cuenta, una organización y un espacio de destino
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### Para utilizar servicios de Cloud Foundry

Para utilizar servicios de Cloud Foundry, debe establecer como objetivo una organización y un espacio de Cloud Foundry. Puede ejecutar el mandato siguiente para elegir la organización y el espacio de forma interactiva:
```
ibmcloud target --cf
```
{: codeblock}

Si lo desea, también puede utilizar la salida del mandato anterior para establecer manualmente su organización y espacio con el siguiente mandato:
```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

### La clave de API tiene una cuenta asociada

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### La clave de API no tiene una cuenta asociada

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> si la clave de API tiene asociada una cuenta, no se permite conmutar a otra cuenta.

### Utilizar un código de acceso de un solo uso
```
ibmcloud login -u UserID --sso
```
{: codeblock}

A continuación, la CLI proporcionará un enlace de URL y pedirá el código de acceso:
```
Código de un solo uso (obtenga uno en https://enlace_URL_para_obtener_código_acceso):
```
{: screen}

Abra el enlace en el navegador para obtener un código de acceso. Escriba el código de acceso en la consola y podrá iniciar la sesión.

## ibmcloud logout
{: #ibmcloud_logout}

Cerrar sesión de usuario.
```
ibmcloud logout
```
{: codeblock}

<strong>Requisitos previos</strong>: Ninguno

## ibmcloud regions
{: #ibmcloud_regions}

Visualiza la información para todas las regiones en {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud regions
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final

## ibmcloud target
{: #ibmcloud_target}


Establece o visualiza la cuenta, región, organización o espacio de destino.
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
   <dt>-c <i>ACCOUNT_ID</i> (opcional)</dt>
   <dd>ID de la cuenta de destino.</dd>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nombre de la región a la que se conmutará, como por ejemplo 'us-south' o 'eu-gb'.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (opcional)</dt>
   <dd>Nombre de grupo de recursos</dd>
   <dt>--cf</dt>
   <dd>Seleccionar interactivamente la organización y el espacio de destino</dd>
   <dt>--cf-api</dt>
   <dd>Punto final de API de Cloud Foundry</dd>
   <dt>-o <i>ORG_NAME</i> (opcional)</dt>
   <dd>Nombre de la organización de destino.</dd>
   <dt>-s <i>SPACE_NAME</i> (opcional)</dt>
   <dd>Nombre del espacio de destino.</dd>
   <dt>--unset-region</dt>
   <dd>Desestablecer región de destino</dd>
   <dt>--unset-resource-group</dt>
   <dd>Desestablecer grupo de recursos de destino</dd>
   <dt>--output <i>FORMAT</i></dt>
   <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>
Si no se especifica ninguna opción, se visualiza la cuenta, la región, la organización y el espacio actuales.

<strong>Ejemplos</strong>:

Establecer la cuenta, organización y espacio actuales:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Cambiar a una nueva región:
```
ibmcloud target -r eu-gb
```
{: codeblock}

Visualiza la cuenta, región, organización y espacio actual:
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Actualiza la CLI a la última versión.
```
ibmcloud update [-f]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forzar actualización sin confirmación. Se necesita el privilegio raíz.</dd>
</dl>


## Mandatos generales de servicio de la infraestructura clásica
{: #softlayer_cli}

Utilice los mandatos de la infraestructura clásica en la interfaz de línea de mandatos (CLI) de {{site.data.keyword.cloud_notm}} para configurar y gestionar los servicios de infraestructura.

Ejecute el mandato `ibmcloud sl` para ver la lista de mandatos disponibles:
```
USO:
   ibmcloud sl command [argumentos...] [opciones...]

MANDATOS:
   block           Infraestructura Gen1 Almacenamiento en bloque
   cdn             Infraestructura Gen1 Red de entrega de contenido
   file            Infraestructura Gen1 Almacenamiento de archivos
   dns             Infraestructura Gen1 Sistema de nombres de dominio
   globalip        Infraestructura Gen1 Direcciones IP globales
   hardware        Infraestructura Gen1 Servidores de hardware
   image           Infraestructura Gen1 Imágenes de cálculo
   ipsec           Infraestructura Gen1 VPN IPSEC
   loadbal         Infraestructura Gen1 Equilibradores de carga
   security        Infraestructura Gen1 Claves SSH y certificados SSL
   securitygroup   Infraestructura Gen1 Grupos de seguridad de red
   subnet          Infraestructura Gen1 Subredes de la red
   ticket          Infraestructura Gen1 Gestionar incidencias
   vlan            Infraestructura Gen1 VLAN de la red
   vs              Infraestructura Gen1 Servidores virtuales
   order           Infraestructura Gen1 Pedidos
   user            Infraestructura Gen1 Gestionar usuarios
   call-api        Llamar puntos finales de API arbitrarios.
   help            Imprimir mensaje de uso de mandato
```
{: screen}

Para ver información de ayuda acerca de un mandato, ejecute:
```
ibmcloud sl [command] -h
```

El mandato `ibmcloud sl init` ya no está disponible a partir de la versión `0.14` de la CLI. Para instalar la versión más reciente de la CLI, consulte [Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Ver la información de ayuda para todos los mandatos que funcionan en el entorno de la infraestructura clásica.
```
ibmcloud sl help
```
{: codeblock}

