---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

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
{: shortdesc}

El cliente de línea de mandatos de {{site.data.keyword.cloud_notm}} empaqueta un cliente de línea de mandatos de Cloud Foundry en su instalación. Si tiene su propia CLI de Cloud Foundry instalada, no utilice a la vez los mandatos de CLI de {{site.data.keyword.cloud_notm}} y los mandatos de CLI de Cloud Foundry de su propia instalación en el mismo contexto. En su lugar, utilice **`ibmcloud cf [mandato]`** si desea utilizar la CLI de Cloud Foundry para gestionar los recursos de Cloud Foundry en el contexto de CLI de {{site.data.keyword.cloud_notm}}. Tenga en cuenta que **`ibmcloud cf api/login/logout/target`** no está permitido y debe utilizar **`ibmcloud api/login/logout/target`** en su lugar.

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.cloud_notm}} han cambiado de **`bluemix`** y **`bx`** a **`ibmcloud`**. Sin embargo, puede seguir utilizando los mandatos de CLI **`bluemix`** y **`bx`** hasta que se eliminen más adelante.
{: tip}

A continuación se enumeran los mandatos detallados que están soportados por la CLI de {{site.data.keyword.cloud_notm}}, incluidos sus nombres, argumentos, opciones, requisitos previos, descripciones y ejemplos.

Los requisitos previos listan las acciones que son necesarias antes de utilizar el mandato y pueden incluir una o varias de las acciones siguientes:

<dl>
<dt>Docker</dt>
<dd>Instale la CLI de Docker.</dd>
<dt>Punto final</dt>
<dd>Utilice el mandato **`ibmcloud api`** para establecer un punto final de API.</dd>
<dt>Iniciar sesión</dt>
<dd>Utilice el mandato **`ibmcloud login`** para iniciar la sesión. Si inicia sesión con un ID federado, utilice la opción **`--sso`** para autenticarse con un código de acceso de un solo uso o utilice **`--apikey`** para realizar la autenticación con una clave de API.</dd>
<dt>Target</dt>
<dd>Utilice el mandato **`ibmcloud target`** para establecer una organización y espacio como destino.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Muestra la ayuda general para mandatos incorporados de primer nivel y espacios de nombres soportados de la CLI de {{site.data.keyword.cloud_notm}}, o la ayuda para un mandato o un espacio de nombres incorporado específico.

```
ibmcloud help [COMMAND|NAMESPACE]
```

### Requisitos previos
{: #help-prereqs}

Ninguno.

### Opciones de mandatos
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>Mandato o espacio de nombres para el que se visualiza ayuda. Si no se especifica, se mostrará la ayuda general de la CLI de {{site.data.keyword.Bluemix_notm}}. Opcional.</dd>
</dl>

### Ejemplos
{: #help-examples}

Visualiza ayuda general de la CLI de {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Muestra ayuda para el mandato **`dev`**:
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

### Requisitos previos
{: #api-prereqs}

Ninguno.

### Opciones de mandatos
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>Punto final de API de destino, por ejemplo, `https://cloud.ibm.com`. Si no se especifican ambas opciones **`API_ENDPOINT`** y **`--unset`**, se mostrará el punto final de API actual. Opcional.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Omite la validación SSL de solicitudes HTTP. Opcional.</dd>
<dt>--unset</dt>
<dd>Elimina la configuración del punto final de la API.</dd>
</dl>

### Ejemplos
{: #api-examples}

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

Elimina el punto final de la API:
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Escribe valores predeterminados en el archivo de configuración.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Requisitos previos
{: #config-prereqs}

Ninguno.

### Opciones de mandatos
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>Habilitar o inhabilitar la comprobación de la versión de la CLI. Los valores válidos son `true` o `false`.</dd>
<dt>--color</dt>
<dd>Habilitar o inhabilitar la salida de color. Esta opción está inhabilitada de forma predeterminada. Los valores válidos son `true` o `false`.</dd>
<dt>--http-timeout</dt>
<dd>Valor de tiempo de espera para solicitudes HTTP en segundos. El valor predeterminado es de 60 segundos.</dd>
<dt>--locale</dt>
<dd>Establecer un entorno local predeterminado. Si no se especifica ningún valor, se suprime el entorno local anterior. </dd>
<dt>--trace </dt>
<dd>Rastrear solicitudes HTTP al terminal o archivo especificado. Los valores válidos son `true` o `false`.</dd>
</dl>

Solo puede especificar una de las opciones a la vez.
{: tip}

### Ejemplos
{: #config-examples}

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

Rastrear solicitudes HTTP en el archivo `/home/usera/my_trace`:
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

El mandato **`ibmcloud info`** ya no está disponible a partir de la versión 0.14 de la CLI. Para instalar la versión más reciente de la CLI, consulte [Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).

## ibmcloud cf
{: #ibmcloud_cf}

Invocar la CLI de Cloud Foundry integrada.
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### Requisitos previos
{: #info-prereqs}

Ninguno.

### Opciones de mandatos
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>No mostrar el mensaje de invocación.</dd>
</dl>

### Ejemplos
{: #info-examples}

Listar las aplicaciones de Cloud Foundry:
```
ibmcloud cf apps
```
{: codeblock}

Listar los servicios de Cloud Foundry sin mostrar el mensaje `Invocando el mandato cf...`:
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

Instalar una CLI de Cloud Foundry para la CLI de IBM Cloud
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### Requisitos previos
{: #cfinstall-prereqs}

Ninguno.

### Opciones de mandatos
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>Especifique la versión de la CLI de Cloud Foundry que desea instalar</dd>
  <dt>--restore</dt>
  <dd>Restaurar la versión previamente incorporada de la CLI de Cloud Foundry</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la instalación sin confirmación</dd>
</dl>

### Ejemplos
{: #cfinstall-examples}

Instalae la CLI de Cloud Foundry `6.44.1`:

```
ibmcloud cf install -v 6.44.1
```

Instalar la versión más reciente de la CLI de Cloud Foundry sin confirmación:

```
ibmcloud cf install -f
```

Recuperar la CLI de Cloud Foundry incluida de forma predeterminada:

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

Inicie la sesión en la CLI de {{site.data.keyword.cloud_notm}}.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### Requisitos previos
{: #login-prereqs}

Ninguno.

### Opciones de mandatos
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>Punto final de API, por ejemplo, `cloud.ibm.com`. </dd>
<dt>--apikey API_KEY o @API_KEY_FILE_PATH</dt>
<dd>Contenido de clave de API o la vía de acceso a un archivo de clave de API indicado mediante el símbolo @.</dd>
<dt>-u USER_NAME</dt>
<dd>Nombre de usuario. Opcional.</dd>
<dt>-p PASS_WORD</dt>
<dd>Contraseña del usuario. Opcional.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID de la cuenta de destino. Esta opción es excluyente con la opción **`--no account`**.</dd>
<dt>--no-account</dt>
<dd>Inicio de sesión forzado sin la cuenta. Esta opción no se recomienda, y es excluyente con la opción **`-c`**.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Nombre del grupo de recursos de destino. Opcional.</dd>
<dt>-r REGION</dt>
<dd>Nombre de la región de destino, por ejemplo, us-south o eu-gb.</dd>
<dt>--no-region</dt>
<dd>Inicio de sesión forzado sin definir una región como destino.</dd>
<dt>-o ORG</dt>
<dd>Nombre de la organización de destino. Esta opción está en desuso. En su lugar, utilice **`ibmcloud target -o org_name`**. Opcional.</dd>
<dt>-s SPACE</dt>
<dd>Nombre del espacio de destino. Esta opción está en desuso. En su lugar, utilice **`ibmcloud target -s space_name`**. Opcional.</dd>
<dt>--no-iam</dt>
<dd>Forzar la autenticación con el servidor de inicio de sesión en lugar del IAM público.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Ignorar la validación SSL de las solicitudes HTTP. No se recomienda esta opción.</dd>
</dl>

### Ejemplos
{: #login-examples}

Iniciar sesión de forma interactiva.

```
ibmcloud login
```
{: codeblock}

Iniciar sesión con un nombre de usuario y su contraseña, estableciendo un espacio, una organización y una cuenta de destino:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con un código de acceso de un solo uso, estableciendo una cuenta, una organización y un espacio de destino:
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Establecer su organización y espacio de Cloud Foundry. Puede ejecutar el mandato siguiente para identificar la organización y el espacio de forma interactiva:

```
ibmcloud target --cf
```
{: codeblock}

O bien, si conoce a qué organización y espacio pertenece el servicio, puede utilizar el mandato siguiente:

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

Utilizar una clave de API con una cuenta asociada:

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

Utilizar una clave de API sin una cuenta asociada:

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

Si la clave de API tiene asociada una cuenta, no se permite conmutar a otra cuenta.
{ :note}

Utilizar un código de acceso de un solo uso:

```
ibmcloud login -u UserID --sso
```
{: codeblock}

A continuación, la CLI proporcionará un enlace de URL y le solicitará el código de acceso:

```
Código de un solo uso (obtenga uno en https://enlace_URL_para_obtener_código_acceso):
```
{: screen}

Abra el enlace en un navegador para obtener un código de acceso. Especifique el código de acceso en la consola para iniciar la sesión.

## ibmcloud logout
{: #ibmcloud_logout}

Finalizar la sesión de la CLI.

```
ibmcloud logout
```
{: codeblock}

### Requisitos previos
{: #logout-prereqs}

Ninguno.

## ibmcloud regions
{: #ibmcloud_regions}

Visualiza la información para todas las regiones en {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```
{: codeblock}

### Requisitos previos
{: #regions-prereqs}

Utilice el mandato **`ibmcloud api`** para establecer un punto final de API.

## ibmcloud target
{: #ibmcloud_target}

Establece o visualiza la cuenta, región, organización o espacio de destino.

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### Requisitos previos
{: #target-prereqs}

* Utilice el mandato **`ibmcloud api`** para establecer un punto final de API.
* Utilice el mandato **`ibmcloud login`** para iniciar la sesión. Si inicia sesión con un ID federado, utilice la opción **`--sso`** para autenticarse con un código de acceso de un solo uso o utilice **`--apikey`** para realizar la autenticación con una clave de API.

### Opciones de mandatos
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>ID de la cuenta de destino. Opcional.</dd>
<dt>-r REGION</dt>
<dd>Nombre de la región de destino, por ejemplo, us-south o eu-gb. Opcional.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Nombre del grupo de recursos de destino. Opcional.</dd>
<dt>--cf</dt>
<dd>Especificar el espacio o la organización de destino de forma interactiva.</dd>
<dt>--cf-api</dt>
<dd>Punto final de API de Cloud Foundry.</dd>
<dt>-o ORG</dt>
<dd>Nombre de la organización de destino. Opcional.</dd>
<dt>-s SPACE</dt>
<dd>Nombre del espacio de destino. Opcional.</dd>
<dt>--unset-region</dt>
<dd>Borrar la región de destino.</dd>
<dt>--unset-resource-group</dt>
<dd>Borrar el grupo de recursos de destino.</dd>
<dt>--output FORMAT</dt>
<dd>Formato de salida especificado. JSON es el único formato soportado actualmente.</dd>
</dl>

Si no se especifica ninguna opción, se visualiza la cuenta, la región, la organización y el espacio actuales.
{: note}

### Ejemplos
{: #target-examples}

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
### Requisitos previos
{: #update-prereqs}

### Opciones de mandatos
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>Forzar una actualización sin confirmación. Se necesita el privilegio raíz.</dd>
</dl>

## Mandatos generales de servicio de la infraestructura clásica
{: #softlayer_cli}

Utilice los mandatos de la infraestructura clásica en la CLI de {{site.data.keyword.cloud_notm}} para configurar y gestionar los servicios de infraestructura.

Ejecute el mandato **`ibmcloud sl`** para ver la lista de mandatos disponibles:
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

Para ver información de ayuda acerca de un mandato, ejecute el siguiente mandato:
```
ibmcloud sl [command] -h
```

El mandato **`ibmcloud sl init`** ya no está disponible a partir de la versión `0.14` de la CLI. Para instalar la versión más reciente de la CLI, consulte [Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Ver la información de ayuda para todos los mandatos que funcionan en el entorno de la infraestructura clásica.
```
ibmcloud sl help
```
{: codeblock}

