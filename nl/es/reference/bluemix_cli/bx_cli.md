---



copyright:

  years: 2015, 2018
lastupdated: "2018-03-05"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Mandatos {{site.data.keyword.Bluemix_notm}} (bx)
{: #bluemix_cli}

Versión: 0.6.5

La interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} proporciona un conjunto de mandatos que se agrupan por espacio de nombres para que los usuarios interactúen con {{site.data.keyword.Bluemix_notm}}.

A partir de la versión 0.5.0, el cliente de línea de mandatos de {{site.data.keyword.Bluemix_notm}} empaqueta un cliente de línea de mandatos de Cloud Foundry en su instalación. Si tiene su propio cf cli instalado, no utilice los mandatos CLI de {{site.data.keyword.Bluemix_notm}} `bx [mandato]` ni los mandatos Cloud Foundry CLI `cf [mandato]` de su propia instalación en el mismo contexto. En su lugar, utilice `bluemix cf [mandato]` si desea utilizar cf cli para gestionar los recursos de Cloud Foundry en el contexto de CLI de {{site.data.keyword.Bluemix_notm}}.  Tenga en cuenta que `bluemix cf api/login/logout/target` no está permitido y debe utilizar `bluemix api/login/logout/target` en su lugar.

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

**Nota:** puede utilizar el formato abreviado de los mandatos de bluemix; por ejemplo, `bx api` es la abreviatura de `bluemix api`.

Utilice los índices de las tablas siguientes para consultar los mandatos de Bluemix que se utilizan con mayor frecuencia.

## Mandatos generales bluemix
{: #bx_commands_index}

<table summary="Mandatos generales bluemix">
<caption>Tabla 1. Mandatos generales de bluemix</caption>
 <thead>
 <th colspan="5">Mandatos generales bluemix</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix help](bx_cli.html#bluemix_help)</td>
 <td>[bluemix api](bx_cli.html#bluemix_api)</td>
 <td>[bluemix config](bx_cli.html#bluemix_config)</td>
 <td>[bluemix info](bx_cli.html#bluemix_info)</td>
 <td>[bluemix cf](bx_cli.html#bluemix_cf)</td>
 </tr>
 <tr>
 <td>[bluemix login](bx_cli.html#bluemix_login) </td>
 <td>[bluemix logout](bx_cli.html#bluemix_logout) </td>
 <td>[bluemix regions](bx_cli.html#bluemix_regions)</td>
 <td>[bluemix target](bx_cli.html#bluemix_target)</td>
 <td>[bluemix update](bx_cli.html#bluemix_update)</td>
 </tr>
 </tbody>
 </table>

 ## Mandatos para gestionar y configurar los servicios de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)
  {: #bx_commands_softlayer}

Los mandatos para gestionar la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} se han fusionado en la CLI de {{site.data.keyword.Bluemix_notm}}. Para obtener más información sobre el uso de la CLI de {{site.data.keyword.Bluemix_notm}} para configurar y gestionar los servicios de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}, consulte: [Mandatos de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} de la CLI de {{site.data.keyword.Bluemix_notm}} (bluemix sl)](/docs/cli/reference/softlayer/index.md#softlayer_cli).

 ## Mandatos para gestionar cuentas, organizaciones y roles
 {: #bx_commands_account}

<table summary="Mandatos de Bluemix que puede utilizar para gestionar las cuentas, las organizaciones, los espacios y los roles.">
<caption>Tabla 2. Mandatos para gestionar cuentas, organizaciones, espacios y roles</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar cuentas, organizaciones, espacios y roles</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix account orgs](bx_cli.html#bluemix_account_orgs)</td>
 <td>[bluemix account org](bx_cli.html#bluemix_account_org)</td>
 <td>[bluemix account org-create](bx_cli.html#bluemix_account_org_create)</td>
 <td>[bluemix account org-replicate](bx_cli.html#bluemix_account_org_replicate)</td>
 <td>[bluemix account org-rename](bx_cli.html#bluemix_account_org_rename)</td>
 </tr>
 <tr>
 <td>[bluemix account spaces](bx_cli.html#bluemix_account_spaces)</td>
 <td>[bluemix account space](bx_cli.html#bluemix_account_space)</td>
 <td>[bluemix account space-create](bx_cli.html#bluemix_account_space_create)</td>
 <td>[bluemix account space-rename](bx_cli.html#bluemix_account_space_rename)</td>
 <td>[bluemix account space-delete](bx_cli.html#bluemix_account_space_delete)</td>
 </tr>
 <tr>
 <td>[bluemix account org-users](bx_cli.html#bluemix_account_org_users)</td>
 <td>[bluemix account org-user-add](bx_cli.html#bluemix_account_org_user_add)</td>
 <td>[bluemix account org-user-remove](bx_cli.html#bluemix_account_org_user_remove)</td>
 <td>[bluemix account org-roles](bx_cli.html#bluemix_account_org_roles)</td>
 <td>[bluemix account org-role-set](bx_cli.html#bluemix_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[bluemix account org-role-unset](bx_cli.html#bluemix_account_org_role_unset)</td>
 <td>[bluemix account space-users](bx_cli.html#bluemix_account_space_users)</td>
 <td>[bluemix account space-roles](bx_cli.html#bluemix_account_space_roles)</td>
 <td>[bluemix account space-role-set](bx_cli.html#bluemix_account_space_role_set)</td>
 <td>[bluemix account space-role-unset](bx_cli.html#bluemix_account_space_role_unset)</td>
</tr>
 <td>[bluemix account list](bx_cli.html#bluemix_account_list)</td>
 <td>[bluemix account org-account](bx_cli.html#bluemix_account_org_account)</td>
 <td>[bluemix account users](bx_cli.html#bluemix_account_users)</td>
 <td>[bluemix account users-delete](bx_cli.html#bluemix_account_users_delete)</td>
 <td>[bluemix account user-invite](bx_cli.html#bluemix_account_user_invite)</td>
 </tr>
 <tr>
  <td>[bluemix account user-reinvite](bx_cli.html#bluemix_account_user_reinvite)</td>
 </tr>
 </tbody>
 </table>


 ## Mandatos para gestionar grupos de recursos y recursos
{: #bx_commands_resource}

<table summary="Mandato de Bluemix que puede utilizar para gestionar grupos de recursos y recursos.">
  <caption>Tabla 3. Mandatos para gestionar grupos de recursos y recursos</caption>
  <thead>
    <th colspan="5">Mandatos para gestionar grupos de recursos y recursos</th>
  </thead>
  <tbody>
    <tr>
      <td>[bluemix resource groups](bx_cli.html#bluemix_resource_groups)</td>
      <td>[bluemix resource group](bx_cli.html#bluemix_resource_group)</td>
      <td>[bluemix resource group-update](bx_cli.html#bluemix_resource_group_update)</td>
      <td>[bluemix resource quotas](bx_cli.html#bluemix_resource_quotas)</td>
      <td>[bluemix resource quota](bx_cli.html#bluemix_resource_quota)</td>
    </tr>
    <tr>
      <td>[bluemix resource service-instances](bx_cli.html#bluemix_resource_service_instances)</td>
      <td>[bluemix resource service-instance](bx_cli.html#bluemix_resource_service_instance)</td>
      <td>[bluemix resource service-instance-create](bx_cli.html#bluemix_resource_service_instance_create)</td>
      <td>[bluemix resource service-instance-update](bx_cli.html#bluemix_resource_service_instance_update)</td>
      <td>[bluemix resource service-instance-delete](bx_cli.html#bluemix_resource_service_instance_delete)</td>
    </tr>
    <tr>
      <td>[bluemix resource service-bindings](bx_cli.html#bluemix_resource_service_bindings)</td>
      <td>[bluemix resource service-binding](bx_cli.html#bluemix_resource_service_binding)</td>
      <td>[bluemix resource service-binding-create](bx_cli.html#bluemix_resource_service_binding_create)</td>
      <td>[bluemix resource service-binding-delete](bx_cli.html#bluemix_resource_service_binding_delete)</td>
    </tr>
    <tr>
      <td>[bluemix resource service-keys](bx_cli.html#bluemix_resource_service_keys)</td>
      <td>[bluemix resource service-key](bx_cli.html#bluemix_resource_service_key)</td>
      <td>[bluemix resource service-key-create](bx_cli.html#bluemix_resource_service_key_create)</td>
      <td>[bluemix resource service-key-delete](bx_cli.html#bluemix_resource_service_key_delete)</td>
    </tr>
    <tr>
      <td>[bluemix resource service-aliases](bx_cli.html#bluemix_resource_service_aliases)</td>
      <td>[bluemix resource service-alias](bx_cli.html#bluemix_resource_service_alias)</td>
      <td>[bluemix resource service-alias-create](bx_cli.html#bluemix_resource_service_alias_create)</td>
      <td>[bluemix resource service-alias-update](bx_cli.html#bluemix_resource_service_alias_update)</td>
      <td>[bluemix resource service-alias-delete](bx_cli.html#bluemix_resource_service_alias_delete)</td>
    </tr>
  </tbody>
</table>


 ## Mandatos para gestionar claves de API y políticas
 {: #bx_commands_iam}
 <table summary="Mandatos de Bluemix que puede utilizar para gestionar claves de API y políticas.">
 <caption>Tabla 3. Mandatos para gestionar claves de API y políticas</caption>
  <thead>
  <th colspan="5">Mandatos para gestionar claves de API y políticas</th>
  </thead>
  <tbody>
  <tr>
   <td>[bluemix iam service-id](bx_cli.html#bluemix_iam_service_id)</td>
   <td>[bluemix iam service-id-create](bx_cli.html#bluemix_iam_service_id_create)</td>
   <td>[bluemix iam service-id-update](bx_cli.html#bluemix_iam_service_id_update)</td>
   <td>[bluemix iam service-id-delete](bx_cli.html#bluemix_iam_service_id_delete)</td>
   <td>[bluemix iam service-ids](bx_cli.html#bluemix_iam_service_ids)</td>
  </tr>
  <tr>
   <td>[bluemix iam api-keys](bx_cli.html#bluemix_iam_api_keys)</td>
   <td>[bluemix iam api-key-create](bx_cli.html#bluemix_iam_api_key_create)</td>
   <td>[bluemix iam api-key-delete](bx_cli.html#bluemix_iam_api_key_delete)</td>
   <td>[bluemix iam api-key-update](bx_cli.html#bluemix_iam_api_key_update)</td>
   <td>[bluemix iam service-api-keys](bx_cli.html#bluemix_iam_service_api_keys)</td>
  </tr>
  <tr>
   <td>[bluemix iam service-api-key](bx_cli.html#bluemix_iam_service_api_key)</td>
   <td>[bluemix iam service-api-key-create](bx_cli.html#bluemix_iam_service_api_key_create)</td>
   <td>[bluemix iam service-api-key-update](bx_cli.html#bluemix_iam_service_api_key_update)</td>
   <td>[bluemix iam service-api-key-delete](bx_cli.html#bluemix_iam_service_api_key_delete)</td>
   <td>[bluemix iam service-policies](bx_cli.html#bluemix_iam_service_policies)</td>
  </tr>
  <tr>
   <td>[bluemix iam service-policy](bx_cli.html#bluemix_iam_service_policy)</td>
   <td>[bluemix iam service-policy-create](bx_cli.html#bluemix_iam_service_policy_create)</td>
   <td>[bluemix iam service-policy-update](bx_cli.html#bluemix_iam_service_policy_update)</td>
   <td>[bluemix iam service-policy-delete](bx_cli.html#bluemix_iam_service_policy_delete)</td>
   <td>[bluemix iam user-policies](bx_cli.html#bluemix_iam_user_policies)</td>
  </tr>
  <tr>
   <td>[bluemix iam user-policy](bx_cli.html#bluemix_iam_user_policy)</td>
   <td>[bluemix iam user-policy-create](bx_cli.html#bluemix_iam_user_policy_create)</td>
   <td>[bluemix iam user-policy-update](bx_cli.html#bluemix_iam_user_policy_update)</td>
   <td>[bluemix iam user-policy-delete](bx_cli.html#bluemix_iam_user_policy_delete)</td>
   <td>[bluemix iam oauth-tokens](bx_cli.html#bluemix_iam_oauth_tokens)</td>
  </tr>
   <tr>
   <td>[bluemix iam dedicated-id-disconnect](bx_cli.html#bluemix_iam_dedicated_id_disconnect)</td>
   <td>[bluemix iam authorization-policy-create](bx_cli.html#bluemix_iam_authorization_policy_create)</td>
   <td>[bluemix iam authorization-policy-delete](bx_cli.html#bluemix_iam_authorization_policy_delete)</td>
   <td>[bluemix iam authorization-policy](bx_cli.html#bluemix_iam_authorization_policy)</td>
   <td>[bluemix iam authorization-policies](bx_cli.html#bluemix_iam_authorization_policies)</td>
  </tr>

  </tr>
  </tbody>
  </table>

 ## Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps
 {: #bx_commands_apps}

<table summary="mandatos de bluemix que sirven para gestionar apps cf y dominios, rutas y certificados relacionados con las apps.">
<caption>Tabla 4. Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix app push](bx_cli.html#bluemix_app_push)</td>
 <td>[bluemix app list](bx_cli.html#bluemix_app_list)</td>
 <td>[bluemix app show](bx_cli.html#bluemix_app_show)</td>
 <td>[bluemix app delete](bx_cli.html#bluemix_app_delete)</td>
 <td>[bluemix app rename](bx_cli.html#bluemix_app_rename)</td>
 </tr>
 <tr>
 <td>[bluemix app start](bx_cli.html#bluemix_app_start)</td>
 <td>[bluemix app stop](bx_cli.html#bluemix_app_stop)</td>
 <td>[bluemix app restart](bx_cli.html#bluemix_app_restart)</td>
 <td>[bluemix app restage](bx_cli.html#bluemix_app_restage)</td>
 <td>[bluemix app instance-restart](bx_cli.html#bluemix_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[bluemix app events](bx_cli.html#bluemix_app_events)</td>
 <td>[bluemix app files](bx_cli.html#bluemix_app_files)</td>
 <td>[bluemix app logs](bx_cli.html#bluemix_app_logs)</td>
 <td>[bluemix app env](bx_cli.html#bluemix_app_env)</td>
 <td>[bluemix app env-set](bx_cli.html#bluemix_app_env_set)</td>
 </tr>
 <tr>
 <td>[bluemix app env-unset](bx_cli.html#bluemix_app_env_unset)</td>
 <td>[bluemix app stacks](bx_cli.html#bluemix_app_stacks)</td>
 <td>[bluemix app stack-show](bx_cli.html#bluemix_app_stack_show)</td>
 <td>[bluemix app manifest-create](bx_cli.html#bluemix_app_manifest_create)</td>
 <td>[bluemix app domain-cert](bx_cli.html#bluemix_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[bluemix app domain-cert-add](bx_cli.html#bluemix_app_domain_cert_add)</td>
  <td>[bluemix app domain-cert-remove](bx_cli.html#bluemix_app_domain_cert_remove)</td>
  <td>[bluemix app domains](bx_cli.html#bluemix_app_domains)</td>
  <td>[bluemix app domain-create](bx_cli.html#bluemix_app_domain_create)</td>
  <td>[bluemix app domain-delete](bx_cli.html#bluemix_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[bluemix app shared-domain-create](bx_cli.html#bluemix_app_shared_domain_create)</td>
  <td>[bluemix app shared-domain-delete](bx_cli.html#bluemix_app_shared_domain_delete)</td>
  <td>[bluemix app routes](bx_cli.html#bluemix_app_routes)</td>
  <td>[bluemix app route-check](bx_cli.html#bluemix_app_route_check)</td>
  <td>[bluemix app route-map](bx_cli.html#bluemix_app_route_map)</td>
 </tr>
 <tr>
  <td>[bluemix app route-unmap](bx_cli.html#bluemix_app_route_unmap)</td>
  <td>[bluemix app route-create](bx_cli.html#bluemix_app_route_create)</td>
  <td>[bluemix app route-delete](bx_cli.html#bluemix_app_route_delete)</td>
  <td>[bluemix app orphaned-routes-delete](bx_cli.html#bluemix_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

 ## Mandatos para gestionar servicios de {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="mandatos bluemix que puede utilizar para gestionar servicios de {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabla 5. Mandatos para gestionar servicios {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar servicios de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix service offerings](bx_cli.html#bluemix_service_offerings)</td>
 <td>[bluemix service list](bx_cli.html#bluemix_service_list)</td>
 <td>[bluemix service show](bx_cli.html#bluemix_service_show)</td>
 <td>[bluemix service create](bx_cli.html#bluemix_service_create)</td>
 <td>[bluemix service update](bx_cli.html#bluemix_service_update)</td>
 </tr>
 <tr>
 <td>[bluemix service delete](bx_cli.html#bluemix_service_delete)</td>
 <td>[bluemix service rename](bx_cli.html#bluemix_service_rename)</td>
 <td>[bluemix service bind](bx_cli.html#bluemix_service_bind)</td>
 <td>[bluemix service unbind](bx_cli.html#bluemix_service_unbind)</td>
 <td>[bluemix service key-create](bx_cli.html#bluemix_service_key_create)</td>
 </tr>
 <tr>
 <td>[bluemix service key-delete](bx_cli.html#bluemix_service_key_delete)</td>
 <td>[bluemix service keys](bx_cli.html#bluemix_service_keys)</td>
 <td>[bluemix service key-show](bx_cli.html#bluemix_service_key_show)</td>
 <td>[bluemix service user-provided-create](bx_cli.html#bluemix_service_user_provided_create)</td>
 <td>[bluemix service user-provided-update](bx_cli.html#bluemix_service_user_provided_update)</td>
 </tr>
  </tbody>
 </table>


 ## Mandatos para gestionar los valores de catálogo, plug-ins y facturación
 {: #bx_commands_settings}

<table summary="mandatos bluemix que puede utilizar para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabla 6. Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix catalog search](bx_cli.html#bluemix_catalog_search)</td>
  <td>[bluemix catalog entry](bx_cli.html#bluemix_catalog_entry)</td>
  <td>[bluemix catalog entry-create](bx_cli.html#bluemix_catalog_entry_create)</td>
  <td>[bluemix catalog entry-update](bx_cli.html#bluemix_catalog_entry_update)</td>
  <td>[bluemix catalog entry-delete](bx_cli.html#bluemix_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[bluemix catalog entry-visibility](bx_cli.html#bluemix_catalog_entry_visibility)</td>
  <td>[bluemix catalog service-marketplace](bx_cli.html#bluemix_catalog_service_marketplace)</td>
  <td>[bluemix catalog entry-visibility-set](bx_cli.html#bluemix_catalog_entry_visibility_set)</td>
  <td>[bluemix catalog templates](bx_cli.html#bluemix_catalog_templates)</td>
  <td>[bluemix catalog template](bx_cli.html#bluemix_catalog_template)</td>
 </tr>
 <tr>
  <td>[bluemix catalog template-run](bx_cli.html#bluemix_catalog_template_run)</td>
  <td>[bluemix catalog locations](bx_cli.html#bluemix_catalog_locations)</td>
  <td>[bluemix plugin repos](bx_cli.html#bluemix_plugin_repos)</td>
  <td>[bluemix plugin repo-add](bx_cli.html#bluemix_plugin_repo_add)</td>
  <td>[bluemix plugin repo-remove](bx_cli.html#bluemix_plugin_repo_remove)</td>
  <td>[bluemix plugin repo-plugins](bx_cli.html#bluemix_plugin_repo_plugins)</td>
 </tr>
 <tr>
  <td>[bluemix plugin repo-plugin](bx_cli.html#bluemix_plugin_repo_plugin)</td>
  <td>[bluemix plugin list](bx_cli.html#bluemix_plugin_list)</td>
  <td>[bluemix plugin install](bx_cli.html#bluemix_plugin_install)</td>
  <td>[bluemix plugin uninstall](bx_cli.html#bluemix_plugin_uninstall)</td>
  <td>[bluemix plugin update](bx_cli.html#bluemix_plugin_update)</td>
 </tr>
 <tr>
  <td>[bluemix billing account-usage](bx_cli.html#bluemix_billing_account_usage)</td>
  <td>[bluemix billing org-usage](bx_cli.html#bluemix_billing_org_usage)</td>
  <td>[bluemix billing resource-group-usage](bx_cli.html#bluemix_resource_group_usage)</td>
  <td>[bluemix billing resource-instances-usage](bx_cli.html#bluemix_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

## bluemix help
{: #bluemix_help}
Muestra la ayuda general para mandatos incorporados de primer nivel y espacios de nombres soportados de {{site.data.keyword.Bluemix_notm}} CLI, o la ayuda para un mandato o un espacio de nombres incorporado específico.

```
bluemix help [COMMAND|NAMESPACE]
```

<strong>Requisitos previos</strong>: Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (opcional)</dt>
   <dd>Mandato o espacio de nombres para el que se visualiza ayuda. Si no se especifica, se mostrará la ayuda general para {{site.data.keyword.Bluemix_notm}} CLI.</dd>
   </dl>



<strong>Ejemplos</strong>:

Visualiza ayuda general para {{site.data.keyword.Bluemix_notm}} CLI:

```
bluemix help
```

Muestra ayuda para el mandato `info`:

```
bluemix help info
```



## bluemix api
{: #bluemix_api}
Establezca o visualice el punto final de su API de {{site.data.keyword.Bluemix_notm}}.

```
bluemix api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
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
bluemix api api.chinabluemix.net
```

```
bluemix api https://api.chinabluemix.net --skip-ssl-validation
```

Visualice el punto final de la API actual:

```
bluemix api
```

Desestablecer el punto final de la API:

```
bluemix api --unset
```

## bluemix config
{: #bluemix_config}


Escriba valores predeterminados en el archivo de configuración.

```
bluemix config --http-timeout TIEMPO_ESPERA_EN_SEGUNDOS | --trace (true|false|vía-acceso-archivo) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>--http-timeout <i>TIEMPO_ESPERA_EN_SEGUNDOS</i></dt>
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
bluemix config --http-timeout 30
```

Habilitar la salida de rastreo para las solicitudes HTTP:

```
bluemix config --trace true
```

Rastrear solicitudes HTTP a un archivo determinado */home/usera/my_trace*:

```
bluemix config --trace /home/usera/my_trace
```

Inhabilitar la salida de color:

```
bluemix config --color false
```

Establecer el entorno local en zh_Hans:

```
bluemix config --locale zh_Hans
```

Borrar los valores de entorno local:

```
bluemix config --locale CLEAR
```



## bluemix info
{: #bluemix_info}

Vea la información básica de {{site.data.keyword.Bluemix_notm}}, incluida la región actual, la versión del controlador de nube y algunos puntos finales útiles, como por ejemplo los puntos finales para el inicio de sesión y el intercambio de señales de acceso.

```
bluemix info
```

<strong>Requisitos previos</strong>:  Punto final


## bluemix cf
{: #bluemix_cf}

Invocar CLI CF incluido

```
bluemix [-q, --quiet] cf COMMAND...
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
bluemix cf apps
```

Listar servicios cf sin el mensaje "Invocando el mandato cf...":

```
bluemix -q cf services
```


## bluemix login
{: #bluemix_login}

Inicio de sesión de usuario.

```
bluemix login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-o ORG] [-s SPACE]
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
  <dd> ID de la cuenta de destino</dd>
  <dt> -o <i>ORG_NAME</i> (opcional) </dt>
  <dd> Nombre de la organización de destino </dd>
  <dt> -s <i>SPACE_NAME</i> (opcional) </dt>
  <dd> Nombre del espacio de destino</dd>
  <dt> --no-iam </dt>
  <dd> Forzar la autenticación con el servidor de inicio de sesión en lugar del IAM público</dd>
  <dt> --skip-ssl-validation (opcional) </dt>
  <dd> Omite la validación SSL de solicitudes HTTP. No se recomienda esta opción.</dd>
</dl>

<strong>Ejemplos</strong>:

#### Inicio de sesión interactivo

```
bluemix login
```

Iniciar sesión con un nombre de usuario y su contraseña, estableciendo un espacio, una organización y una cuenta de destino:

```
bluemix login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con un código de acceso de una sola vez, estableciendo una cuenta, una organización y un espacio de destino

```
bluemix login --sso -c MyAccountID -o MyOrg -s MySpace
```

Iniciar sesión con una clave de API y estableciendo destinos:

#### La clave de API tiene asociada una cuenta

```
bluemix login --apikey api-key-string -o MyOrg -s MySpace
```

```
bluemix login --apikey @filename -o MyOrg -s MySpace
```

#### La clave de API no tiene asociada una cuenta

```
bluemix login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
bluemix login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> Si la clave de API tiene asociada una cuenta, no se permite conmutar a otra cuenta.

#### Utilizar un código de acceso de una sola

```
bluemix login -u UserID --sso
```

A continuación, la CLI proporcionará un enlace de URL y pedirá el código de acceso:
```
Código de un solo uso (obtenga uno en https://enlace_URL_para_obtener_código_acceso):
```

Abra el enlace en el navegador, que le guiará para obtener el código de acceso. Escriba el código de acceso en la consola y podrá iniciar la sesión.

## bluemix logout
{: #bluemix_logout}

Cerrar sesión de usuario.

```
bluemix logout
```

<strong>Requisitos previos</strong>:  Ninguno

## bluemix regions
{: #bluemix_regions}

Visualiza la información para todas las regiones en {{site.data.keyword.Bluemix_notm}}.

```
bluemix regions
```

<strong>Requisitos previos</strong>:  Punto final


## bluemix target
{: #bluemix_target}


Establece o visualiza la cuenta, región, organización o espacio de destino.

```
bluemix target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nombre de la región a la que se conmutará, como por ejemplo 'us-south' o 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (opcional)</dt>
   <dd>ID de la cuenta de destino.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (opcional)</dt>
   <dd>Nombre del grupo de recursos.</dd>
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
bluemix target -c MyAccountID -o MyOrg -s MySpace
```

Cambiar a una nueva región:

```
bluemix target -r eu-gb
```

Visualiza la cuenta, región, organización y espacio actual:

```
bluemix target
```

## bluemix update
{: #bluemix_update}

Actualiza la CLI a la última versión.

```
bluemix update
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forzar actualización sin confirmación</dd>
</dl>

### bluemix account orgs
{: #bluemix_account_orgs}

Listar todas las organizaciones

```
bluemix account orgs [-r REGION] [--guid]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-r <i>REGION</i> (opcional)</dt>
   <dd>Indica para qué región se muestra información sobre la organización. Si se establece en 'all', se listan todas las organizaciones de todas las regiones.</dd>
   <dt>--guid (opcional)</dt>
   <dd>Muestra el GUID de las organizaciones.</dd>
   </dl>

<strong>Ejemplos</strong>:

Listar todas las organizaciones de la región: `us-south` con GUID visualizado

```
bluemix account orgs -r us-south --guid
```

## bluemix account org
{: #bluemix_account_org}

Mostrar la información para la organización especificada.

```
bluemix account org ORG_NAME [--guid]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>--guid (opcional)</dt>
   <dd>Muestra el GUID de la organización.</dd>
   </dl>

<strong>Ejemplos</strong>:

Mostrar la información de la organización `IBM` con GUID visualizado

```
bluemix account org IBM --guid
```


## bluemix account org-create
{: #bluemix_account_org_create}

Crear una nueva organización. Esta operación solamente la puede realizar el propietario de cuenta.

```
bluemix account org-create ORG_NAME [-f]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización que se está creando.</dd>
   <dt>-f</dt>
   <dd>Forzar la creación sin confirmación.</dd>
   </dl>

<strong>Ejemplos</strong>:

Cree una organización denominada `IBM`.

```
bluemix account org-create IBM
```

## bluemix account org-replicate
{: #bluemix_account_org_replicate}

Replicar una organización desde la región actual a otra región.

```
bluemix account org-replicate ORG_NAME REGION_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización existente que se debe replicar.</dd>
   <dt>REGION_NAME (necesario)</dt>
   <dd>Nombre de la región que aloja la organización replicada.</dd>
   </dl>

<strong>Ejemplos</strong>:

Replicar la organización `myorg` en la región `eu-gb`:

```
bluemix account org-replicate myorg eu-gb
```


## bluemix account org-rename
{: #bluemix_account_org_rename}

Cambiar el nombre de una organización. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
bluemix account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>OLD_ORG_NAME (necesario)</dt>
   <dd>Nombre antiguo de la organización que se debe renombrar.</dd>
   <dt>NEW_ORG_NAME (necesario)</dt>
   <dd>Nombre de la nueva organización.</dd>
   </dl>


## bluemix account spaces
{: #bluemix_account_spaces}

Listar todos los espacios

```
bluemix account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nombre de la organización. Lista los espacios en la organización especificada. De forma predeterminada toma la organización actual si no se especifica.</dd>
   <dt>-r</dt>
   <dd>Nombre de región. Lista los espacios en la región especificada. De forma predeterminada toma la región actual si no se especifica.</dd>
   </dl>



## bluemix account space
{: #bluemix_account_space}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


## bluemix account space-create
{: #bluemix_account_space_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.


## bluemix account space-rename
{: #bluemix_account_space_rename}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.


## bluemix account space-delete
{: #bluemix_account_space_delete}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## bluemix account org-users
{: #bluemix_account_org_users}

Visualice usuarios en el archivo de organización según el rol.

```
bluemix account org-users ORG_NAME [-a]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>ORG_NAME (necesario)</dt>
<dd>Nombre de la organización.</dd>
<dt>-a (opcional)</dt>
<dd>Lista todos los usuarios de la organización especificada, no agrupada por rol.</dd>
</dl>

## bluemix account org-user-add
{: #bluemix_account_org_user_add}

Añadir un usuario a la organización (es necesario ser gestor de organización).

```
 bluemix account org-user-add USER_NAME ORG
```

## bluemix account org-user-remove
{: #bluemix_account_org_user_remove}

Eliminar un usuario de la organización (gestor de organización o usuario mismo solamente)

```
   bluemix account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## bluemix account org-roles
{: #bluemix_account_org_roles}

Obtiene todos los roles de la organización del usuario actual

```
bluemix account org-roles [-u USER_ID]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID de usuario. Si no se especifica, el valor predeterminado es el usuario actual.</dd>
  </dl>

## bluemix account org-role-set
{: #bluemix_account_org_role_set}

Asignar un rol de organización a un usuario. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
bluemix account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>Nombre del usuario al que se asigna.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>ORG_ROLE (necesario)</dt>
   <dd>Nombre del rol de la organización al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
  </dl>

<strong>Ejemplos</strong>:

Asigne el usuario `Mary` a la organización `IBM` como el rol de `OrgManager`:

```
bluemix account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Nota**: Establezca roles de espacios/organizaciones utilizando la interfaz de línea de mandatos, sin embargo, si desea establecer otros permisos, utilice la interfaz de usuario. Para obtener más información, consulte [Asignación de acceso de usuarios](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## bluemix account org-role-unset
{: #bluemix_account_org_role_unset}

Elimine un rol de organización de un usuario. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
bluemix account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>Nombre del usuario al que se elimina.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>ORG_ROLE (necesario)</dt>
   <dd>Nombre del rol de la organización de la que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
    </dl>

<strong>Ejemplos</strong>:

Elimine el usuario `Mary` de la organización `IBM` como el rol de `OrgManager`:

```
bluemix account org-role-unset Mary IBM OrgManager
```

## bluemix account space-users
{: #bluemix_account_space_users}

Visualice usuarios en el espacio especificado según el rol.

```
bluemix account space-users ORG_NAME SPACE_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>El nombre del espacio.</dd>
   </dl>


## bluemix account space-role-set
{: #bluemix_account_space_role_set}

Asignar un rol de espacio a un usuario. Esta operación solamente la puede llevar a cabo un gestor de espacios.

```
bluemix account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>Nombre del usuario al que se asigna.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>Nombre del espacio al que se asigna a este usuario.</dd>
   <dt>SPACE_ROLE (necesario)</dt>
   <dd>Nombre del rol de espacio al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio dado.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
    </dl>

<strong>Ejemplos</strong>:

Asigne el usuario `Mary` a la organización `IBM` y al espacio `Cloud` como rol `SpaceManager`:

```
bluemix account space-role-set Mary IBM Cloud SpaceManager
```

## bluemix account space-role-unset
{: #bluemix_account_space_role_unset}

Elimine un rol de espacio de un usuario. Esta operación solamente la puede llevar a cabo un gestor de espacios.

```
bluemix account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>Nombre del usuario al que se elimina.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>Nombre del espacio del que se elimina a este usuario.</dd>
   <dt>SPACE_ROLE (necesario)</dt>
   <dd>Nombre del rol del espacio del que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio dado.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
    </dl>


<strong>Ejemplos</strong>:

Elimine el usuario `Mary` de la organización `IBM` y del espacio `Cloud` como rol `SpaceManager`:

```
bluemix account space-role-unset Mary IBM Cloud SpaceManager
```

## bluemix account list
{: #bluemix_account_list}

Lista todas las cuentas del usuario actual

```
bluemix account list
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión


## bluemix account org-account
{: #bluemix_account_org_account}

Visualiza la cuenta de la organización especificada (se necesita un usuario de la organización)

```
bluemix account org-account ORG_NAME [--guid]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--guid (opcional)</dt>
  <dd>Visualiza únicamente el ID de la cuenta</dd>
</dl>


## bluemix account users
{: #bluemix_account_users}

Muestra usuarios asociados con la cuenta. Esta operación solamente puede realizarla el propietario de cuenta.

```
bluemix account users
```

## bluemix account user-delete
{: #bluemix_account_user_delete}

Suprime un usuario de la cuenta actual (sólo el propietario de la cuenta)

```
bluemix account user-delete USERNAME [-c ACCOUNT_ID] [-f]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>USERNAME (necesario)</dt>
<dd>Nombre de usuario</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID de cuenta. Si no se especifica, el valor predeterminado es la cuenta actual.</dd>
<dt>--force, -f (opcional)</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## bluemix account user-invite
{: #bluemix_account_user_invite}

Invita a un usuario a la cuenta. Esta operación solamente puede realizarla el propietario de cuenta.

```
bluemix account user-invite USER_EMAIL
```

## bluemix account user-reinvite
{: #bluemix_account_user_reinvite}

Reenviar invitación a un usuario (es necesario ser propietario de cuenta).

```
bluemix account user-reinvite USER_EMAIL
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión
  
 <strong>Opciones de mandato</strong>:
 <dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>Correo electrónico del usuario al que se vuelve a invitar.</dd>
 </dl>



## bluemix iam service-ids
{: #bluemix_iam_service_ids}

Lista todos los ID de servicio

```
bluemix iam service-ids --uuid
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-uuid</dt>
  <dd>Mostrar UUID solo de los ID de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Lista de UUID de todos los ID de servicio bajo la cuenta actual

```
bluemix iam service-ids --uuid
```


## bluemix iam service-id
{: #bluemix_iam_service_id}

Mostrar detalles de un ID de servicio

```
bluemix iam service-id NAME [--uuid]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio</dd>
  <dt>-uuid</dt>
  <dd>Mostrar el UUID del ID de servicio</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de ID de servicio `sample-test`

```
bluemix iam service-id sample-test
```


## bluemix iam service-id-create
{: #bluemix_iam_service_id_create}

Crear un ID de servicio

```
bluemix iam service-id-create NAME [-d, --description DESCRIPTION]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio</dd>
  <dt>-d, --description</dt>
  <dd>Descripción del ID de servicio</dd>
</dl>

<strong>Ejemplos</strong>:

Crear un ID de servicio con nombre de servicio `sample-test` y descripción `hello, world!`

```
bluemix iam service-id-create sample-test -d 'hello, world!'
```


## bluemix iam service-id-update

{: #bluemix_iam_service_id_update}
Actualizar un ID de servicio

```
bluemix iam service-id-update NAME [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de servicio</dd>
  <dt>-d, --description</dt>
  <dd>Nueva descripción del servicio</dd>
  <dt>-v, --version</dt>
  <dd>Versión del ID de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Actualizar sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Renombrar el ID de servicio `sample-test` a `sample-test-2` sin confirmación

```
bluemix iam service-id-update sample-test -n sample-test-2 -f
```

Actualizar descripción de servicio `sample-test` versión `1-0jn39fbefew`

```
bluemix iam service-id-update sample-test -d 'hello, friend!' -v 1-0jn39fbefew
```


## bluemix iam service-id-delete
{: #bluemix_iam_service_id_delete}

Suprimir un ID de servicio

```
bluemix iam service-id-delete NAME [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio</dd>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir ID de servicio `sample-teset` sin confirmación

```
bluemix iam service-id-delete sample-teset -f
```


## bluemix iam api-keys
{: #bluemix_iam_api_keys}

Lista todas las claves de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-keys
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

## bluemix iam api-key-create
{: #bluemix_iam_api_key_create}

Crear una nueva clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a crear.</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>Descripción de la clave de API</dd>
<dt>-f, -- file <i>FILE</i></dt>
<dd>Guarda la información de la clave de API en un archivo especificado. Si no se establece, se visualiza el contenido JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Crea una clave de API y la guarda en un archivo

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
```

## bluemix iam api-key-update
{: #bluemix_iam_api_key_update}

Actualizar una clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre anterior de la clave de API a actualizar.</dd>
<dt>-n <i>NAME</i> (opcional)</dt>
<dd>Nuevo nombre de la clave de API</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>Nueva descripción de la clave de API</dd>
</dl>

<strong>Ejemplos</strong>:

Actualiza la descripción de una clave de API:

```
bluemix iam api-key-update MyKey -d "the new description of my key"
```

## bluemix api-key-delete
{: #bluemix_api_key_delete}

Suprimir una clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-delete NAME [-f]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la clave de API a suprimir.</dd>
<dt>-f  (opcional)</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## bluemix iam service-api-keys
{: #bluemix_iam_service_api_keys}

Listar todas las claves de API de un servicio

```
bluemix iam service-api-keys SERVICE_ID
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todas las claves de API de un servicio `sample-service` :

```
bluemix iam service-api-keys sample-service
```

## bluemix iam service-api-key
{: #bluemix_iam_service_api_key}

Listar detalles de una clave de API de servicio

```
bluemix iam service-api-key NAME SERVICE_ID [--uuid]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-uuid</dt>
  <dd>Visualice el UUID de la clave de API de servicio</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar los detalles de una clave de API de servicio `sample-key` del servicio `sample-service` :

```
bluemix iam service-api-key sample-key sample-service
```

## bluemix iam service-api-key-create
{: #bluemix_iam_service_api_key_create}

Crear una clave de API de servicio

```
bluemix iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [-f, --file FILE]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descripción de la clave de API</dd>
  <dt>-f, --file</dt>
  <dd>Guarda la información de la clave de API en un archivo especificado. Si no se establece, se visualiza el contenido JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una clave de API de servicio `sample-key` para el servicio `sample-service` :

```
bluemix iam service-api-key-create sample-key sample-service
```

## bluemix iam service-api-key-update
{: #bluemix_iam_service_api_key_update}

Actualizar una clave de API de servicio

```
bluemix iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre de la clave de API de servicio</dd>
  <dt>-d, --description</dt>
  <dd>Nueva descripción de la clave de API de servicio</dd>
  <dt>-v, --version</dt>
  <dd>Versión de la clave de API de servicio</dd>
  <dt>-f, --force</dt>
  <dd>Actualizar sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Renombrar la clave de API de servicio `sample-key` a `new-sample-key`:

```
bluemix iam service-api-key-update sample-key sample-service -n new-sample-key
```

## bluemix iam service-api-key-delete
{: #bluemix_iam_service_api_key_delete}

Suprimir una clave de API de servicio

```
bluemix iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir clave de API de servicio `sample-key`:

```
bluemix iam service-api-key-delete sample-key sample-service
```

## bluemix iam user-policies
{: #bluemix_iam_user_policies}

Lista de políticas de usuario `name@example.com`:

```
bluemix iam user-policies name@example.com
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
bluemix iam user-policies name@example.com
```

## bluemix iam user-policy
{: #bluemix_iam_user_policy}

Mostrar detalles de una política de usuario

```
bluemix iam user-policy USER_NAME POLICY_ID
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
bluemix iam user-policy name@example.com 0bb730daa
```

## bluemix iam user-policy-create
{: #bluemix_iam_user_policy_create}

Crear una política de usuario

```
bluemix iam user-policy-create USER_NAME {-f, --file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenece la política</dd>
<dt>-f, --file <i>FILE</i> (opcional)</dt>
<dd>Archivo JSON de definición de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'bluemix iam roles --service SERVICE_NAME'. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nombre de servicio de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i> (opcional)</dt>
<dd>Instancia de servicio de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Región de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nombre del grupo de recursos. Es exclusivo con los distintivos '-f, --file', '--resource' y '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID del grupo de recursos. Es exclusivo con los distintivos '-f, --file', '--resource' y '--resource-group-name'.</dd>
</dl>

<strong>Ejemplos</strong>:

Crear política de usuario para el usuario `name@example.com` desde el archivo JSON de política `policy.json`:

```
bluemix iam user-policy-create name@example.com -f @policy.json
```

Proporcione a `name@example.com` el rol de `Administrador` para todos los recursos de `sample-service`:

```
bluemix iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Proporcione a `name@example.com` el rol de `Editor` para el recurso `key123` de la instancia de servicio de ejemplo `ServiceId-ade78e9f` en la región `us-south`:

```
bluemix iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

Proporcione a `name@example.com` el rol de `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
bluemix iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Proporcione a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos `sample-resource-group`:

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Proporcione a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## bluemix iam user-policy-update
{: #bluemix_iam_user_policy_update}

Actualizar una política de usuario

```
bluemix iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, cuenta de destino

<strong>Opciones de mandato</strong>:
<dt>USER_NAME (necesario)</dt>
<dd>Nombre de usuario al que pertenece la política</dd>
<dt>POLICY_ID (necesario)</dt>
<dd>ID de la política a actualizar</dd>
<dt>-v, --version <i>VERSION</i> (opcional)</dt>
<dd>Versión de la política existente</dd>
<dt>-f, --file <i>FILE</i> (opcional)</dt>
<dd>Archivo JSON de definición de política</dd>
<dt>-f, --file <i>FILE</i> (opcional)</dt>
<dd>Archivo JSON de definición de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'bluemix iam roles --service SERVICE_NAME'. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nombre de servicio de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i> (opcional)</dt>
<dd>Instancia de servicio de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Región de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso de la definición de política. Es exclusivo con el distintivo '-f, --file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nombre del grupo de recursos. Es exclusivo con los distintivos '-f, --file', '--resource' y '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID del grupo de recursos. Es exclusivo con los distintivos '-f, --file', '--resource' y '--resource-group-name'.</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar la política de usuario con la del archivo JSON：

```
bluemix iam user-policy-update name@example.com 0bb730daa -f @policy.json
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Administrador` para todos los recursos de `sample-service`：

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Actualizar la política de usuario para dar a `name@example.com` el rol de `Editor` para el recurso `key123` de la instancia de servicio de ejemplo `ServiceId-ade78e9f` en la región `us-south`:

```
bluemix iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Operador` para el grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos `sample-resource-group`:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Actualizar la política de usuario para dar a `name@example.com` el rol de `Visor` para los miembros del grupo de recursos con el ID `dda27e49d2a1efca58083a01dfde18f6`:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```



## bluemix iam service-policies
{: #bluemix_iam_service_policies}

Listar todas las políticas de servicio del servicio especificado

```
bluemix iam service-policies SERVICE_ID_NAME [--json] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio</dd>
  <dt>-json</dt>
  <dd>Mostrar política en formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Mostrar las políticas de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Lista de políticas de servicio `test`:

```
bluemix iam service-policies test
```


## bluemix iam service-policy
{: #bluemix_iam_service_policy}

Mostrar detalles de una política de servicio

```
bluemix iam service-policy SERVICE_ID_NAME POLICY_ID [--json] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>-json</dt>
  <dd>Mostrar política en formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Mostrar la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar la política `140798e2-8ea7db3` de servicio `test`:

```
bluemix iam service-policies test 140798e2-8ea7db3
```


## bluemix iam service-policy-create
{: #bluemix_iam_service_policy_create}

Crear una política de servicio

```
bluemix iam service-policy-create SERVICE_ID_NAME {-f, --file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio</dd>
  <dt>-f, --file</dt>
  <dd>Archivo JSON de definición de política. Esta opción y los distintivos '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' y '--resource-group-id' son excluyentes.</dd>
  <dt>-r, --roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'bluemix iam roles --service SERVICE_NAME'. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--service-instance</dt>
  <dd>Instancia de servicio de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y '-f, --file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del grupo de recursos. Esta opción y '-f, --file' y '--resource-group-name' son mutuamente excluyentes.</dd>
  <dt>-F, --force</dt>
  <dd>Crear la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Crear la política de servicio desde el archivo JSON para el servicio `test`:

```
bluemix iam service-policy-create test -f @policy.json
```


## bluemix iam service-policy-update
{: #bluemix_iam_service_policy_update}

Actualizar una política de servicio

```
bluemix iam service-policy-update SERVICE_ID_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>-v, --version</dt>
  <dd>Versión de la política de servicio</dd>
  <dt>-f, --file</dt>
  <dd>Archivo JSON de definición de política. Esta opción y los distintivos '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' y 'resource-group-id' son excluyentes.</dd>
  <dt>-r, --roles</dt>
  <dd>Nombres de rol de la definición de política. Para los roles soportados de un servicio específico, ejecute 'bluemix iam roles --service SERVICE_NAME'. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-service-name</dt>
  <dd>Nombre de servicio de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-service-instance</dt>
  <dd>Instancia de servicio de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-region</dt>
  <dd>Región de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>-resource</dt>
  <dd>Recurso de la definición de política. Esta opción y el distintivo '-f, --file' son mutuamente excluyentes.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nombre del grupo de recursos. Esta opción y '-f, --file' y '--resource-group-id' son mutuamente excluyentes.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del grupo de recursos. Esta opción y '-f, --file' y '--resource-group-name' son mutuamente excluyentes.</dd>
  <dt>-F, --force</dt>
  <dd>Actualizar la política de servicios sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Actualizar la política de servicio `140798e2-8ea7db3` desde el archivo JSON para el servicio `test`:

```
bluemix iam service-policy-update test 140798e2-8ea7db3 -f @policy.json
```

## bluemix iam service-policy-delete
{: #bluemix_iam_service_policy_delete}

Suprimir una política de servicio

```
bluemix iam service-policy-delete SERVICE_ID_NAME POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio</dd>
  <dt>POLICY_ID (necesario)</dt>
  <dd>ID de la política de servicio<dd>
  <dt>-f, --force</dt>
  <dd>Suprimir sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Suprimir la política `140798e2-8ea7db3` del servicio `test`

```
bluemix iam service-policy-delete test 140798e2-8ea7db3
```

## bluemix iam oauth-tokens
{: #bluemix_iam_oauth_tokens}

Recuperar y visualizar las señales OAuth para la sesión actual.

```
bluemix iam oauth-tokens
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Renovar y visualizar señales OAuth.

```
bluemix iam oauth-tokens
```

## bluemix iam dedicated-id-disconnect
{: #bluemix_iam_dedicated_id_disconnect}

Desconectar el IBMid público con el IBMid no de IBM dedicado.

```
bluemix iam dedicated-id-disconnect [-f, --force]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forzar la desconexión sin confirmación.</dd>
</dl>

## bluemix iam authorization-policy-create
{: #bluemix_iam_authorization_policy_create}
 
Crear una política de autorización para permitir a una instancia de servicio acceder a otra instancia de servicio.

```
bluemix iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME] ROLE_NAME1,ROLE_NAME2...
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Servicio de origen que está autorizado para acceder.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Servicio de destino al que el servicio de origen está autorizado para acceder.</dd>
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nombre de instancia de servicio de origen; si no se especifica, todas las instancias de servicio de origen estarán autorizadas para acceder.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nombre de instancia de servicio de destino; si no se especifica, todas las instancias de servicio de destino estarán autorizadas para acceder.   </dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Los roles que dan acceso al servicio de origen.</dd>  
</dl>

## bluemix iam authorization-policy-delete
{: #bluemix_iam_authorization_policy_delete}

Suprimir una política de autorización.

```
bluemix iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID de la política de autorización que se va a suprimir.</dd> 
 <dt>-f, --force</dt>
 <dd>Forzar la eliminación sin confirmación.</dd> 
</dl>

## bluemix iam authorization-policy
{: #bluemix_iam_authorization_policy}

Mostrar los detalles de una política de autorización.

```
bluemix iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID de la política de autorización que se va a mostrar.</dd> 
</dl>


## bluemix iam authorization-policies
{: #bluemix_iam_authorization_policies}

Listar políticas de autorización en la cuenta actual.

```
bluemix iam authorization-policies
```

<strong>Requisitos previos</strong>: Inicio de sesión, destino

## bluemix resource groups
{: #bluemix_resource_groups}

Listar grupos de recursos.

```
bluemix resource groups [--default]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--default</dt>
  <dd>Obtener grupo predeterminado de la cuenta actual.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar todos los grupos de recursos de la cuenta de destino actual:

```
bluemix resource groups
```

Listar el grupo predeterminado de la cuenta de destino actualmente:

```
bluemix resource groups --default
```

## bluemix resource group
{: #bluemix_resource_group}

Mostrar detalles de un grupo de recursos.

```
bluemix resource group NAME [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos.</dd>
  <dt>--id</dt>
  <dd>Mostrar solo ID</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar grupo de recursos `example-group`:

```
bluemix resource group example-group
```

Mostrar sólo el ID del grupo de recursos `example-group`:

```
bluemix resource group example-group --id
```


## bluemix resource group-update
{: #bluemix_resource_group_update}

Actualizar un grupo de recursos existente.

```
bluemix resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos de destino.</dd>
  <dt>-n, --name</dt>
  <dd>Nuevo nombre del grupo de recursos.</dd>
  <dt>-q, --quota</dt>
  <dd>Nombre de la nueva definición de cuota.</dd>
  <dt>-f</dt>
  <dd>Forzar actualización sin confirmación.</dd>
</dl>

<strong>Ejemplos</strong>:

Cambie el nombre del grupo de recursos `example-group` a `trial-group`:

```
bluemix resource group-update example-group -n trial-group
```

Cambie la cuota del grupo de recursos `example-group` a `free`:

```
bluemix resource group-update example-group -q free
```

## bluemix resource quotas
{: #bluemix_resource_quotas}

Listar todas las definiciones de cuota.

```
bluemix resource quotas
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Listar todas las definiciones de cuota:

```
bluemix resource quotas
```

## bluemix resource quota
{: #bluemix_resource_quota}

Mostrar detalles de una definición de cuota

```
bluemix resource quota NAME
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre de la cuota</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles de cuota `free`:

```
bluemix resource quota free
```


## bluemix app push
{: #bluemix_app_push}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf push ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## bluemix app list
{: #bluemix_app_list}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf apps ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## bluemix app show
{: #bluemix_app_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf app ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## bluemix app delete
{: #bluemix_app_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## bluemix app rename
{: #bluemix_app_rename}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## bluemix app start
{: #bluemix_app_start}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf start ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## bluemix app stop
{: #bluemix_app_stop}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stop ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## bluemix app restart
{: #bluemix_app_restart}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## bluemix app restage
{: #bluemix_app_restage}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restage ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## bluemix app instance-restart
{: #bluemix_app_instance_restart}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart-app-instance ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## bluemix app events
{: #bluemix_app_events}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf events ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## bluemix app files
{: #bluemix_app_files}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf files ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## bluemix app logs
{: #bluemix_app_logs}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf logs ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## bluemix app env
{: #bluemix_app_env}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## bluemix app env-set
{: #bluemix_app_env_set}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf set-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## bluemix app env-unset
{: #bluemix_app_env_unset}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf unset-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## bluemix app stacks
{: #bluemix_app_stacks}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stacks ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## bluemix app stack-show
{: #bluemix_app_stack_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stack ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## bluemix app manifest-create
{: #bluemix_app_manifest_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-app-manifest ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## bluemix app domain-cert
{: #bluemix_app_domain_cert}

Liste la información de certificado de un dominio.

```
bluemix app domain-cert DOMAIN_NAME
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
bluemix app domain-cert ibmcxo-eventconnect.com
```

## bluemix app domain-cert-add
{: #bluemix_app_domain_cert_add}

Añadir un certificado para el dominio especificado en la organización actual.

```
bluemix app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
bluemix app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## bluemix app domain-cert-remove
{: #bluemix_app_domain_cert_remove}

Eliminar un certificado del dominio especificado en la organización actual.

```
bluemix app domain-cert-remove DOMAIN [-f]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio a eliminar del certificado.</dd>
   <dt>-f  (opcional)</dt>
   <dd>Forzar la eliminación sin confirmación.</dd>
   </dl>

## bluemix app routes
{: #bluemix_app_routes}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## bluemix app route-check
{: #bluemix_app_route_check}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf check-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## bluemix app route-map
{: #bluemix_app_route_map}

Correlacione una ruta a una app cf o grupo de contenedores que tenga un dominio y nombre de host específicos.

```
bluemix app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
bluemix app route-map my-app mychinabluemix.net
```

Correlacione una ruta a 'my-container-group' con el dominio y el nombre de host especificados:

```
bluemix app route-map my-container-group chinabluemix.net -n abc
```


## bluemix app route-unmap
{: #bluemix_app_route_unmap}

Elimina la correlación entre la ruta específica y una app cf existente o grupo de contenedores.

```
bluemix app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
bluemix app route-unmap my-app mychianbluemix.net
```

Descorrelacionar `abc.chinabluexmix.net` desde `my-container-group`:

```
bluemix app route-unmap my-container-group chinabluemix.net -n abc
```


## bluemix app route-create
{: #bluemix_app_route_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## bluemix app route-delete
{: #bluemix_app_route_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## bluemix app orphaned-routes-delete
{: #bluemix_app_orphaned_routes_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-orphaned-routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## bluemix app domains
{: #bluemix_app_domains}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf domains ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## bluemix app domain-create
{: #bluemix_app_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## bluemix app domain-delete
{: #bluemix_app_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## bluemix app shared-domain-create
{: #bluemix_app_shared_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## bluemix app shared-domain-delete
{: #bluemix_app_shared_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## bluemix service offerings
{: #bluemix_service_offerings}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf marketplace ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## bluemix service list
{: #bluemix_service_list}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf services ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## bluemix service show
{: #bluemix_service_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## bluemix service create
{: #bluemix_service_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## bluemix service update
{: #bluemix_service_update}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf update-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## bluemix service delete
{: #bluemix_service_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## bluemix service rename
{: #bluemix_service_rename}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## bluemix service bind
{: #bluemix_service_bind}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf bind-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## bluemix service unbind
{: #bluemix_service_unbind}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf unbind-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## bluemix service key-create
{: #bluemix_service_key_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## bluemix service key-delete
{: #bluemix_service_key_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## bluemix service keys
{: #bluemix_service_keys}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service-keys ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## bluemix service key-show
{: #bluemix_service_key_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## bluemix service user-provided-create
{: #bluemix_service_user_provided_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-user-provided-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## bluemix service user-provided-update
{: #bluemix_service_user_provided_update}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf update-user-provided-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## bluemix resource service-instances
{: #bluemix_resource_service_instances}

Listar instancias de servicio

```
bluemix resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-instances --service-name test-service
```

## bluemix resource service-instance
{: #bluemix_resource_service_instance}

Mostrar los detalles de una instancia de servicio

```
bluemix resource service-instance NAME [--location LOCATION] [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre de la instancia de servicio</dd>
  <dt>--location</dt>
  <dd>Filtrar por ubicación</dd>
  <dt>--id</dt>
  <dd>Mostrar el ID de la instancia de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar detalles de la instancia de servicio `my-service-instance`:

```
bluemix resource service-instance my-service-instance
```

## bluemix resource service-instance-create
{: #bluemix_resource_service_instance_create}

Crear una instancia de servicio

```
bluemix resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
</dl>

<strong>Ejemplos</strong>:
Crear una instancia de servicio llamada `my-service-instance` utilizando el plan de servicio `test-service-plan` del servicio `test-service` en la ubicación `eu-gb`:

```
bluemix resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## bluemix resource service-instance-update
{: #bluemix_resource_service_instance_update}

Actualizar instancia de servicio

```
bluemix resource service-instance-update SERVICE_INSTANCE_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME (necesario)</dt>
  <dd>Nombre de la instancia de servicio</dd>
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
bluemix resource service-instance-update my-service-instance -n new-service-instance
```

## bluemix resource service-instance-delete
{: #bluemix_resource_service_instance_delete}

Suprimir instancia de servicio

```
bluemix resource service-instance-delete NAME [-f, --force] [--recursive]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forzar la supresión sin confirmación</dd>
  <dt>--recursive</dt>
  <dd>Suprimir todos los recursos de pertenencia</dd>
</dl>

<strong>Ejemplos</strong>:
Suprimir instancia de servicio de recurso `my-service-instance`:

```
bluemix resource service-instance-delete my-service-instance
```

## bluemix resource service-bindings
{: #bluemix_resource_service_bindings}

Mostrar enlaces al alias de servicio

```
bluemix resource bindings SERVICE_ALIAS
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
</dl>

<strong>Ejemplos</strong>:
Mostrar enlaces de recursos con el alias de servicio `my-service-alias`:

```
bluemix resource bindings my-service-alias
```
## bluemix resource service-binding
{: #bluemix_resource_service_binding}

Mostrar detalles de un enlace de servicio

```
bluemix resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource bindings my-service-alias my-app
```

## bluemix resource service-binding-create
{: #bluemix_resource_service_binding_create}

Crear un enlace de servicio

```
bluemix resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id-name SERVICE_ID_NAME] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (necesario)</dt>
  <dd>Nombre de alias de servicio</dd>
  <dt>APP_NAME</dt>
  <dd>Nombre de aplicación de CloudFoundry</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nombre del rol de usuario</dd>
  <dt>--service-id-name</dt>
  <dd>Nombre del ID de servicio al que pertenece el rol</dd>
  <dt>-p, --parameter</dt>
  <dd>Parámetros del archivo JSON o de la serie JSON</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la creación sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Crear enlaces de servicio entre el alias de servicio `my-service-alias` y la app `my-app` con el rol `Administrator`:

```
bluemix resource service-binding-create my-service-alias my-app Administrator
```
## bluemix resource service-binding-delete
{: #bluemix_resource_service_binding_delete}

Suprimir un enlace de servicio

```
bluemix resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
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
bluemix resource service-binding-delete my-service-alias my-app
```

## bluemix resource service-keys
{: #bluemix_resource_service_keys}

Listar claves de servicio de la instancia de servicio o el alias de servicio

```
bluemix resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-keys --instance-name my-service-instance
```

## bluemix resource service-key
{: #bluemix_resource_service_key}

Mostrar detalles de una clave de servicio

```
bluemix resource service-key KEY_NAME [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-key my-service-key
```

## bluemix resource service-key-create
{: #bluemix_resource_service_key_create}

Crear una clave de servicio

```
bluemix resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id-name SERVICE_ID_NAME [-f, --force]]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
  <dt>-service-id-name</dt>
  <dd>Nombre del ID de servicio al que pertenece el rol</dd>
  <dt>-f, --force</dt>
  <dd>Forzar la creación sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:
Crear una clave de servicio llamada `my-service-key` con el rol `Administrator` para la instancia de servicio `my-service-instance`:

```
bluemix resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## bluemix resource service-key-delete
{: #bluemix_resource_service_key_delete}

Suprimir una clave de servicio

```
bluemix resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-key-delete my-service-key
```

## bluemix resource service-aliases
{: #bluemix_resource_service_aliases}

Listar los alias de una instancia de servicio

```
bluemix resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-aliases my-service-instance
```

## bluemix resource service-alias
{: #bluemix_resource_service_alias}

Mostrar detalles de un alias de servicio

```
bluemix resource service-alias ALIAS_NAME [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-aliase  my-service-alias
```

## bluemix resource service-alias-create
{: #bluemix_resource_service_alias_create}

Crear un alias de una instancia de servicio

```
bluemix resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-aliase-create my-service-alias --instance-name my-service-instance
```

## bluemix resource service-alias-update
{: #bluemix_resource_service_alias_update}

Actualizar un alias de servicio

```
bluemix resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-alias-update my-service-alias -n new-service-alias
```

## bluemix resource service-alias-delete
{: #bluemix_resource_service_alias_delete}

Suprimir un alias de servicio

```
bluemix resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bluemix resource service-alias-delete my-service-alias
```

## bluemix catalog search
{: #bluemix_catalog_search}

Buscar entradas de catálogo

```
bluemix catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
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
bluemix catalog search -k service -q 'Automation test'
```


## bluemix catalog entry
{: #bluemix_catalog_entry}

Obtener una entrada de catálogo

```
bluemix catalog entry ID [--global]
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
bluemix catalog entry 'a0ef1-d3b4j0'
```


## bluemix catalog entry-create
{: #bluemix_catalog_entry_create}
Crear una nueva entrada de catálogo (sólo administrador del catálogo de una cuenta)

```
bluemix catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
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
bluemix catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## bluemix catalog entry-update
{: #bluemix_catalog_entry_update}
Actualizar una entrada de catálogo existente (sólo administrador o editor del catálogo de una cuenta)

```
bluemix catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
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
bluemix update 'j402-dnf1i' -c @update.json
```

## bluemix catalog entry-delete
{: #bluemix_catalog_entry_delete}
Suprimir una entrada de catálogo (solo administrador del catálogo de una cuenta)
```
bluemix catalog entry-delete ID [--global]
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
bluemix catalog delete 'j402-dnf1i'
```


## bluemix catalog entry-visibility
{: #bluemix_catalog_entry_visibility}
Obtener la visibilidad para una entrada de catálogo (sólo administrador del catálogo de una cuenta)

```
bluemix catalog entry-visibility ID [--global]
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
bluemix catalog entry-visibility 'j402-dnf1i' --global
```


## bluemix catalog entry-visibility-set
{: #bluemix_catalog_entry_visibility_set}
Actualizar la visibilidad de una entrada de catálogo existente (sólo administrador del catálogo de una cuenta)

```
bluemix catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
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
bluemix catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## bluemix catalog service-marketplace
{: #bluemix_catalog_service_marketplace}
Lista de ofertas de servicios en el mercado

```
bluemix catalog service-marketplace [--cf] [--rc] [--global]
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
bluemix catalog service-marketplace --global
```

## bluemix catalog templates
{: #bluemix_catalog_templates}

Visualizar las plantillas de contenedor modelo en Bluemix.

```
bluemix catalog templates [-d]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Si se especifica la opción <i>-d</i>, también se mostrará la descripción de cada plantilla. De lo contrario, sólo se mostrará el ID y el nombre de cada plantilla.</dd>
   </dl>


## bluemix catalog template
{: #bluemix_catalog_template}

Ver la información detallada de una plantilla de contenedor modelo especificada.

```
bluemix catalog template TEMPLATE_ID
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>TEMPLATE_ID (necesario)</dt>
   <dd>ID de la plantilla de contenedor modelo. Utilice <i>bluemix templates</i> para ver los ID de todas las plantillas.</dd>
   </dl>


<strong>Ejemplos</strong>:

Ver detalles de la plantilla `mobileBackendStarter`:

```
bluemix catalog template mobileBackendStarter
```


## bluemix catalog template-run
{: #bluemix_catalog_template_run}

Crea una app cf que se base en la plantilla específica con el URL y la descripción especificados. De forma predeterminada, la nueva app se iniciará automáticamente.

```
bluemix catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>TEMPLATE_ID (necesario)</dt>
   <dd>Plantilla en la que se basará la app cuando se cree. Utilice <i>bluemix templates</i> para ver el ID de todas las plantillas.</dd>
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
bluemix catalog template-run javaHelloWorld my-app
```

Crear una aplicación `my-ruby-app` en función de la plantilla `rubyHelloWorld` con la ruta `myrubyapp.chinabluemix.net` y la descripción `Mi primera app ruby en {{site.data.keyword.Bluemix_notm}}.`:

```
bluemix catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crear una aplicación `my-python-app` basada en la plantilla `pythonHelloWorld` sin inicio automático:

```
bluemix catalog template-run pythonHelloWorld my-python-app --no-start
```

## bluemix catalog locations
{: #bluemix_catalog_locations}

Obtener un subconjunto determinado de regiones en el formato preferido.

```
bluemix catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
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

## bluemix billing account-usage
{: #bluemix_billing_account_usage}

Mostrar el uso y coste mensual de la cuenta actual.

```
bluemix billing account-usage [-d AAAA-MM] [--json]
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

Mostrar el informe de uso y coste de la cuenta actual en 2016-06:

```
bluemix billing account-usage -d 2016-06
```

## bluemix billing org-usage
{: #bluemix_billing_org_usage}

Mostrar el uso mensual de una organización. Esta operación solo la pueden llevar a cabo el propietario de la cuenta o el gestor de facturación de la organización.

```
bluemix billing org-usage ORG_NAME [-d YYYY-MM] [--json]
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



## bluemix billing resource-group-usage
{: #bluemix_billing_resource_group_usage}

Mostrar el uso mensual de un grupo de recursos. Esta operación solo la pueden llevar a cabo el propietario de la cuenta o el gestor de facturación del grupo de recursos.

```
bluemix billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
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

## bluemix billing resource-instances-usage
{: #bluemix_billing_resource_instances_usage}
 
 Mostrar el uso mensual de las instancias de recursos de la cuenta actual
 
 ```
 bluemix billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
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


## bluemix plugin repos
{: #bluemix_plugin_repos}

Crear una lista de todos los repositorios de plug-in que se registran en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin repos
```

<strong>Requisitos previos</strong>:  Ninguno


## bluemix plugin repo-add
{: #bluemix_plugin_repo_add}

Agrega un nuevo repositorio de plug-in a la CLI de {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin repo-add REPO_NAME REPO_URL
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
bluemix plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## bluemix plugin repo-remove
{: #bluemix_plugin_repo_remove}

Elimina el repositorio de plugins de la CLI de {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin repo-remove REPO_NAME
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>REPO_NAME (necesario)</dt>
   <dd>Nombre del repositorio que se debe eliminar.</dd>
   </dl>

<strong>Ejemplos</strong>:

Eliminar el repositorio `bluemix-repo` de {{site.data.keyword.Bluemix_notm}} CLI:

```
bluemix plugin repo-remove bluemix-repo
```


## bluemix plugin repo-plugins
{: #bluemix_plugin_repo_plugins}

Crear una lista de todos los plug-ins disponibles en todos los repositorios o repositorios específicos.

```
bluemix plugin repo-plugins [-r REPO_NAME]
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Listar únicamente los plug-ins del repositorio indicado.</dd>
   </dl>

<strong>Ejemplos</strong>:

Crear una lista de todos los plug-ins en todos los repositorios añadidos:

```
bluemix plugin repo-plugins
```

Listar todos los plug-ins del repositorio `bluemix-repo`:

```
bluemix plugin repo-plugins -r bluemix-repo
```

## bluemix plugin repo-plugin
{: #bluemix_plugin_repo_plugin}

Mostrar los detalles de un plug-in del repositorio.

```
bluemix plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Nombre del repositorio. Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado.</dd>
   </dl>

<strong>Ejemplos</strong>:

Listar detalles del plugin "container-service" en el repositorio 'Bluemix':

```
bluemix plugin repo-plugin container-service -r Bluemix
```

Listar detalles del plugin "container-service" en el repositorio predeterminado, 'Bluemix'

```
bluemix plugin repo-plugin container-service -r Bluemix
```


## bluemix plugin list
{: #bluemix_plugin_list}

Crea una lista de todos los plug-ins instalados en la CLI de {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin list
```

<strong>Requisitos previos</strong>:  Ninguno

## bluemix plugin show
{: #bluemix_plugin_show}

Mostrar detalles de un plugin instalado

```
bluemix plugin show PLUGIN-NAME
```

<strong>Requisitos previos</strong>:  Ninguno


## bluemix plugin install
{: #bluemix_plugin_install}

Instalar la versión específica del plug-in en {{site.data.keyword.Bluemix_notm}} CLI desde la vía de acceso o el repositorio especificados.

```
bluemix plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
bluemix plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado, 'Bluemix'.
Si no se especifica ninguna versión, el mandato selecciona la versión disponible más reciente para instalar.

<strong>Requisitos previos</strong>:  Ninguno

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (necesario)</dt>
   <dd>Si -r <i>REPO_NAME</i> no se especifica, el plug-in se instala desde la vía de acceso local o el URL remoto indicados.</dd>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Nombre del repositorio en el que se encuentra el binario del plug-in. Si no se especifica ningún repositorio, el mandato utilizará el repositorio de plug-in predeterminado, 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (opcional)</dt>
   <dd>Versión del plug-in que se debe instalar. Si no se proporciona, se instalará la versión más reciente del plug-in. Esta opción sólo es válida al instalar el plug-in desde el repositorio.</dd>
   <dt>-f </dt>
   <dd>Forzar la instalación del plugin sin confirmación.</dd>
    </dl>
    
    
La CLI de {{site.data.keyword.Bluemix_notm}} tiene el nombre de repositorio oficial de 'Bluemix'.    

<strong>Ejemplos</strong>:

Instalar un plug-in desde el archivo local:

```
bluemix plugin install /downloads/new_plugin
```

Instalar un plug-in desde el URL remoto:

```
bluemix plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Instalar el plugin 'container-service' de la versión más reciente del repositorio 'Bluemix':

```
bluemix plugin install container-service -r Bluemix
```
Instalar el plugin 'container-service' con la versión '0.1.425' desde el repositorio oficial de plugins:

```
bluemix plugin install container-service -v 0.1.425
```

## bluemix plugin update
{: #bluemix_plugin_update}

Actualizar el plugin desde un repositorio.

```
bluemix plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
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

Comprobar las actualizaciones disponibles en el repositorio oficial de plugins 'Bluemix':

```
bluemix plugin update -r Bluemix
```

Actualizar el plugin 'container-service' en el repositorio oficial de plugins a la última versión:

```
bluemix plugin update container-service
```

Actualizar el plugin 'container-service' en el repositorio oficial de plugins a la versión '0.1.440':

```
bluemix plugin update container-service -v 0.1.440
```

## bluemix plugin uninstall
{: #bluemix_plugin_uninstall}

Desinstala el plug-in especificado desde la CLI de {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin uninstall PLUGIN_NAME
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
bluemix plugin uninstall container-service
```
