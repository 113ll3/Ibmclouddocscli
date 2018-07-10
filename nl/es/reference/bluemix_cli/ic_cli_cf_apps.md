---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI para gestionar apps cf y dominios, rutas y certificados relacionados con las apps
{: #ibmcloud_commands_apps}

<table summary="mandatos de ibmcloud que sirven para gestionar apps cf y dominios, rutas y certificados relacionados con las apps.">
<caption>Tabla 1. Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](ic_cli_cf_apps.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](ic_cli_cf_apps.html#ibmcloud_app_list)</td>
 <td>[ibmcloud app show](ic_cli_cf_apps.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](ic_cli_cf_apps.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](ic_cli_cf_apps.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](ic_cli_cf_apps.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](ic_cli_cf_apps.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](ic_cli_cf_apps.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](ic_cli_cf_apps.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](ic_cli_cf_apps.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app events](ic_cli_cf_apps.html#ibmcloud_app_events)</td>
 <td>[ibmcloud app files](ic_cli_cf_apps.html#ibmcloud_app_files)</td>
 <td>[ibmcloud app logs](ic_cli_cf_apps.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](ic_cli_cf_apps.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](ic_cli_cf_apps.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](ic_cli_cf_apps.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](ic_cli_cf_apps.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](ic_cli_cf_apps.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](ic_cli_cf_apps.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](ic_cli_cf_apps.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](ic_cli_cf_apps.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](ic_cli_cf_apps.html#ibmcloud_app_domain_cert_remove)</td>
  <td>[ibmcloud app domains](ic_cli_cf_apps.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](ic_cli_cf_apps.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](ic_cli_cf_apps.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](ic_cli_cf_apps.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](ic_cli_cf_apps.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app routes](ic_cli_cf_apps.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](ic_cli_cf_apps.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](ic_cli_cf_apps.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](ic_cli_cf_apps.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](ic_cli_cf_apps.html#ibmcloud_app_route_create)</td>
  <td>[ibmcloud app route-delete](ic_cli_cf_apps.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](ic_cli_cf_apps.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>
 
 ### ibmcloud app push
{: #ibmcloud_app_push}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf push ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.

### ibmcloud app list
{: #ibmcloud_app_list}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf apps ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.

### ibmcloud app show
{: #ibmcloud_app_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf app ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.

### ibmcloud app delete
{: #ibmcloud_app_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.

### ibmcloud app rename
{: #ibmcloud_app_rename}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.

### ibmcloud app start
{: #ibmcloud_app_start}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf start ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.

### ibmcloud app stop
{: #ibmcloud_app_stop}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stop ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.

### ibmcloud app restart
{: #ibmcloud_app_restart}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.

### ibmcloud app restage
{: #ibmcloud_app_restage}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restage ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.

### ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart-app-instance ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.

### ibmcloud app events
{: #ibmcloud_app_events}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf events ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.

### ibmcloud app files
{: #ibmcloud_app_files}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf files ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.

### ibmcloud app logs
{: #ibmcloud_app_logs}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf logs ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.

### ibmcloud app env
{: #ibmcloud_app_env}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.

### ibmcloud app env-set
{: #ibmcloud_app_env_set}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf set-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.

### ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf unset-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.

### ibmcloud app stacks
{: #ibmcloud_app_stacks}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stacks ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.

### ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stack ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.

### ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-app-manifest ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

### ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Liste la información de certificado de un dominio.

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>DOMAIN_NAME (necesario)</dt>
<dd>Nombre del dominio que aloja el certificado.</dd>
</dl>


<strong>Ejemplos</strong>:

Ver la información de certificado del dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

### ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Añadir un certificado para el dominio especificado en la organización actual.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio al que se añade el certificado.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (necesario)</dt>
   <dd>Vía de acceso del archivo de claves privado.</dd>
   <dt>-c <i>CERT_FILE</i> (necesario)</dt>
   <dd>Vía de acceso del archivo de certificado.</dd>
   <dt>-p <i>PASSWORD</i> (opcional)</dt>
   <dd>Contraseña del certificado.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (opcional)</dt>
   <dd>Vía de acceso del archivo de certificado intermedio.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (opcional)</dt>
   <dd>Archivo del almacén de confianza.</dd>
   </dl>


<strong>Ejemplos</strong>:

Añadir un certificado al dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

### ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Eliminar un certificado del dominio especificado en la organización actual.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio a eliminar del certificado.</dd>
   <dt>-f  (opcional)</dt>
   <dd>Forzar la eliminación sin confirmación.</dd>
   </dl>

### ibmcloud app routes
{: #ibmcloud_app_routes}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.

### ibmcloud app route-check
{: #ibmcloud_app_route_check}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf check-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.

### ibmcloud app route-map
{: #ibmcloud_app_route_map}

Correlacione una ruta a una app cf o grupo de contenedores que tenga un dominio y nombre de host específicos.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (necesario)</dt>
   <dd>Nombre de la aplicación cf o del grupo de contenedores que debe correlacionarse con una ruta.</dd>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio de la ruta. Por ejemplo, mychinabluemix.net o chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (opcional)</dt>
   <dd>Nombre de host de la ruta. Si no se facilita, el nombre de host se establece en el nombre de la app o grupo de contenedores de forma predeterminada.</dd>
   </dl>

<strong>Ejemplos</strong>:

Correlacionar una ruta a `my-app` con un dominio especificado:

```
ibmcloud app route-map my-app mychinabluemix.net
```

Correlacione una ruta a 'my-container-group' con el dominio y el nombre de host especificados:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

### ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Elimina la correlación entre la ruta específica y una app cf existente o grupo de contenedores.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (necesario)</dt>
   <dd>Nombre de la aplicación cf o del grupo de contenedores.</dd>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio de la ruta (por ejemplo, mychinabluemix.net o chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (opcional)</dt>
   <dd>Nombre de host de la ruta. Si no se proporciona, el nombre de host se establece en el nombre de la app o en el nombre de grupo de contenedores de forma predeterminada.</dd>
   </dl>

<strong>Ejemplos</strong>:

Descorrelacionar `my-app.mychinabluemix.net` desde `my-app`:

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Descorrelacionar `abc.chinabluexmix.net` desde `my-container-group`:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

### ibmcloud app route-create
{: #ibmcloud_app_route_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.

### ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.

### ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-orphaned-routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.

### ibmcloud app domains
{: #ibmcloud_app_domains}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf domains ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.

### ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.

### ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.

### ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.

### ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.
