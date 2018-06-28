---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-18"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Mandatos {{site.data.keyword.Bluemix_notm}} (ibmcloud)
{: #bluemix_cli}

Versión: 0.7.1

La interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} proporciona un conjunto de mandatos que se agrupan por espacio de nombres para que los usuarios interactúen con {{site.data.keyword.Bluemix_notm}}.

A partir de la versión 0.5.0, el cliente de línea de mandatos de {{site.data.keyword.Bluemix_notm}} empaqueta un cliente de línea de mandatos de Cloud Foundry en su instalación. Si tiene su propio cf cli instalado, no utilice los mandatos CLI de {{site.data.keyword.Bluemix_notm}} `ibmcloud [mandato]` ni los mandatos Cloud Foundry CLI `cf [mandato]` de su propia instalación en el mismo contexto. En su lugar, utilice `ibmcloud cf [mandato]` si desea utilizar cf cli para gestionar los recursos de Cloud Foundry en el contexto de CLI de {{site.data.keyword.Bluemix_notm}}.  Tenga en cuenta que `ibmcloud cf api/login/logout/target` no está permitido y debe utilizar `ibmcloud api/login/logout/target` en su lugar.

A partir de mayo de 2018, los mandatos de la CLI de {{site.data.keyword.Bluemix_notm}} han cambiado de `bluemix` y `bx` a `ibmcloud`. Sin embargo, todavía puede utilizar los mandatos de CLI `bluemix` y `bx` hasta que se dejen de utilizar en una fecha posterior.
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


Utilice los índices de las tablas siguientes para consultar los mandatos de Bluemix que se utilizan con mayor frecuencia.

## Mandatos generales ibmcloud
{: #bx_commands_index}

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

 ## Mandatos para gestionar y configurar los servicios de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
  {: #bx_commands_softlayer}

Los mandatos para gestionar la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} se han fusionado en la CLI de {{site.data.keyword.Bluemix_notm}}. Para obtener más información sobre el uso de la CLI de {{site.data.keyword.Bluemix_notm}} para configurar y gestionar los servicios de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}, consulte: [Mandatos de la infraestructura de {{site.data.keyword.Bluemix_notm}} de la CLI de {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html#softlayer_cli).

 ## Mandatos para gestionar cuentas, organizaciones y roles
 {: #bx_commands_account}

<table summary="Mandatos de Bluemix que puede utilizar para gestionar las cuentas, las organizaciones, los espacios y los roles.">
<caption>Tabla 2. Mandatos para gestionar cuentas, organizaciones, espacios y roles</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar cuentas, organizaciones, espacios y roles</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](bx_cli.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](bx_cli.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](bx_cli.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](bx_cli.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](bx_cli.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](bx_cli.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](bx_cli.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](bx_cli.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](bx_cli.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](bx_cli.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](bx_cli.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](bx_cli.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](bx_cli.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](bx_cli.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](bx_cli.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](bx_cli.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](bx_cli.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](bx_cli.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](bx_cli.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](bx_cli.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](bx_cli.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](bx_cli.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](bx_cli.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](bx_cli.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](bx_cli.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](bx_cli.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](bx_cli.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](bx_cli.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](bx_cli.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](bx_cli.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](bx_cli.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](bx_cli.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](bx_cli.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](bx_cli.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](bx_cli.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](bx_cli.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](bx_cli.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](bx_cli.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](bx_cli.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](bx_cli.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](bx_cli.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](bx_cli.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](bx_cli.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](bx_cli.html#ibmcloud_iam_access_group_policy_delete)</td>
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
      <td>[ibmcloud resource groups](bx_cli.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](bx_cli.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](bx_cli.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](bx_cli.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](bx_cli.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-instances](bx_cli.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](bx_cli.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](bx_cli.html#ibmcloud_resource_service_instance_create)</td>
      <td>[ibmcloud resource service-instance-update](bx_cli.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](bx_cli.html#ibmcloud_resource_service_instance_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-bindings](bx_cli.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](bx_cli.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](bx_cli.html#ibmcloud_resource_service_binding_create)</td>
      <td>[ibmcloud resource service-binding-delete](bx_cli.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource cf-service-instance-migrate](bx_cli.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quota](bx_cli.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](bx_cli.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](bx_cli.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](bx_cli.html#ibmcloud_resource_service_key_create)</td>
      <td>[ibmcloud resource service-key-delete](bx_cli.html#ibmcloud_resource_service_key_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-aliases](bx_cli.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](bx_cli.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](bx_cli.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](bx_cli.html#ibmcloud_resource_service_alias_update)</td>
      <td>[ibmcloud resource service-alias-delete](bx_cli.html#ibmcloud_resource_service_alias_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource search](bx_cli.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](bx_cli.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](bx_cli.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](bx_cli.html#ibmcloud_resource_tag_create)</td>
      <td>[ibmcloud resource tag-delete](bx_cli.html#ibmcloud_resource_tag_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-attach](bx_cli.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](bx_cli.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](bx_cli.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>


 ## Mandatos para gestionar claves de API y políticas
 {: #bx_commands_iam}
 <table summary="Mandatos de Bluemix que puede utilizar para gestionar claves de API y políticas.">
 <caption>Tabla 4. Mandatos para gestionar claves de API y políticas</caption>
  <thead>
  <th colspan="5">Mandatos para gestionar claves de API y políticas</th>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-id](bx_cli.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](bx_cli.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](bx_cli.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](bx_cli.html#ibmcloud_iam_service_id_delete)</td>
   <td>[ibmcloud iam service-id-lock](bx_cli.html#ibmcloud_iam_service_id_lock)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-id-unlock](bx_cli.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam service-ids](bx_cli.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam api-keys](bx_cli.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](bx_cli.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](bx_cli.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](bx_cli.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](bx_cli.html#ibmcloud_iam_api_key_lock)</td>
   <td>[ibmcloud iam api-key-unlock](bx_cli.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](bx_cli.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](bx_cli.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](bx_cli.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](bx_cli.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](bx_cli.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-api-key-lock](bx_cli.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[ibmcloud iam service-api-key-unlock](bx_cli.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
    <td>[ibmcloud iam service-policies](bx_cli.html#ibmcloud_iam_service_policies)</td>
    <td>[ibmcloud iam service-policy](bx_cli.html#ibmcloud_iam_service_policy)</td>
    <td>[ibmcloud iam service-policy-create](bx_cli.html#ibmcloud_iam_service_policy_create)</td>
    <td>[ibmcloud iam service-policy-update](bx_cli.html#ibmcloud_iam_service_policy_update)</td>
    <td>[ibmcloud iam service-policy-delete](bx_cli.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](bx_cli.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](bx_cli.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](bx_cli.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](bx_cli.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](bx_cli.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam oauth-tokens](bx_cli.html#ibmcloud_iam_oauth_tokens)</td>
     <td>[ibmcloud iam dedicated-id-disconnect](bx_cli.html#ibmcloud_iam_dedicated_id_disconnect)</td>
     <td>[ibmcloud iam authorization-policy-create](bx_cli.html#ibmcloud_iam_authorization_policy_create)</td>
     <td>[ibmcloud iam authorization-policy-delete](bx_cli.html#ibmcloud_iam_authorization_policy_delete)</td>
     <td>[ibmcloud iam authorization-policy](bx_cli.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam authorization-policies](bx_cli.html#ibmcloud_iam_authorization_policies)</td>
  </tr>
  </tbody>
  </table>

 ## Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps
 {: #bx_commands_apps}

<table summary="mandatos de ibmcloud que sirven para gestionar apps cf y dominios, rutas y certificados relacionados con las apps.">
<caption>Tabla 5. Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar apps cf y dominios, rutas y certificados relacionados con las apps</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](bx_cli.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](bx_cli.html#ibmcloud_app_list)</td>
 <td>[ibmcloud app show](bx_cli.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](bx_cli.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](bx_cli.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](bx_cli.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](bx_cli.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](bx_cli.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](bx_cli.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](bx_cli.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app events](bx_cli.html#ibmcloud_app_events)</td>
 <td>[ibmcloud app files](bx_cli.html#ibmcloud_app_files)</td>
 <td>[ibmcloud app logs](bx_cli.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](bx_cli.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](bx_cli.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](bx_cli.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](bx_cli.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](bx_cli.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](bx_cli.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](bx_cli.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](bx_cli.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](bx_cli.html#ibmcloud_app_domain_cert_remove)</td>
  <td>[ibmcloud app domains](bx_cli.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](bx_cli.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](bx_cli.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](bx_cli.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](bx_cli.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app routes](bx_cli.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](bx_cli.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](bx_cli.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](bx_cli.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](bx_cli.html#ibmcloud_app_route_create)</td>
  <td>[ibmcloud app route-delete](bx_cli.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](bx_cli.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

 ## Mandatos para gestionar servicios de {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="mandatos ibmcloud que puede utilizar para gestionar servicios de {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabla 6. Mandatos para gestionar servicios de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar servicios de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud service offerings](bx_cli.html#ibmcloud_service_offerings)</td>
 <td>[ibmcloud service list](bx_cli.html#ibmcloud_service_list)</td>
 <td>[ibmcloud service show](bx_cli.html#ibmcloud_service_show)</td>
 <td>[ibmcloud service create](bx_cli.html#ibmcloud_service_create)</td>
 <td>[ibmcloud service update](bx_cli.html#ibmcloud_service_update)</td>
 </tr>
 <tr>
 <td>[ibmcloud service delete](bx_cli.html#ibmcloud_service_delete)</td>
 <td>[ibmcloud service rename](bx_cli.html#ibmcloud_service_rename)</td>
 <td>[ibmcloud service bind](bx_cli.html#ibmcloud_service_bind)</td>
 <td>[ibmcloud service unbind](bx_cli.html#ibmcloud_service_unbind)</td>
 <td>[ibmcloud service key-create](bx_cli.html#ibmcloud_service_key_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud service key-delete](bx_cli.html#ibmcloud_service_key_delete)</td>
 <td>[ibmcloud service keys](bx_cli.html#ibmcloud_service_keys)</td>
 <td>[ibmcloud service key-show](bx_cli.html#ibmcloud_service_key_show)</td>
 <td>[ibmcloud service user-provided-create](bx_cli.html#ibmcloud_service_user_provided_create)</td>
 <td>[ibmcloud service user-provided-update](bx_cli.html#ibmcloud_service_user_provided_update)</td>
 </tr>
  </tbody>
 </table>


 ## Mandatos para gestionar los valores de catálogo, plug-ins y facturación
 {: #bx_commands_settings}

<table summary="mandatos ibmcloud que puede utilizar para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabla 7. Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos para gestionar los valores de catálogo, plug-ins, facturación y seguridad de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](bx_cli.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](bx_cli.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](bx_cli.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](bx_cli.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](bx_cli.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](bx_cli.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](bx_cli.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](bx_cli.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](bx_cli.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](bx_cli.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](bx_cli.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](bx_cli.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](bx_cli.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](bx_cli.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](bx_cli.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](bx_cli.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](bx_cli.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](bx_cli.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](bx_cli.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](bx_cli.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin install](bx_cli.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](bx_cli.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](bx_cli.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](bx_cli.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](bx_cli.html#ibmcloud_billing_org_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing resource-group-usage](bx_cli.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](bx_cli.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ## Gestionar entornos de empresa de Cloud Foundry (experimental)
{: #bx_commands_cfee}

<table summary="Gestionar entornos de empresa de Cloud Foundry (experimental)">
<caption>Tabla 8. Gestionar entornos de empresa de Cloud Foundry (experimental)</caption>
 <thead>
 <th colspan="5">Gestionar entornos de empresa de Cloud Foundry (experimental)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](bx_cli.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](bx_cli.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

## ibmcloud help
{: #ibmcloud_help}
Muestra la ayuda general para mandatos incorporados de primer nivel y espacios de nombres soportados de {{site.data.keyword.Bluemix_notm}} CLI, o la ayuda para un mandato o un espacio de nombres incorporado específico.

```
ibmcloud help [COMMAND|NAMESPACE]
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

<strong>Requisitos previos</strong>:  Punto final


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
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
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

#### Inicio de sesión interactivo

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

#### La clave de API tiene asociada una cuenta

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### La clave de API no tiene asociada una cuenta

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> Si la clave de API tiene asociada una cuenta, no se permite conmutar a otra cuenta.

#### Utilizar un código de acceso de una sola

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

<strong>Requisitos previos</strong>:  Punto final


## ibmcloud target
{: #ibmcloud_target}


Establece o visualiza la cuenta, región, organización o espacio de destino.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Listar todas las organizaciones

```
ibmcloud account orgs [-r REGION] [--guid]
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
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

Mostrar la información para la organización especificada.

```
ibmcloud account org ORG_NAME [--guid]
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
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crear una nueva organización. Esta operación solamente la puede realizar el propietario de cuenta.

```
ibmcloud account org-create ORG_NAME [-f]
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
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replicar una organización desde la región actual a otra región.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
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
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Cambiar el nombre de una organización. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>OLD_ORG_NAME (necesario)</dt>
   <dd>Nombre antiguo de la organización que se debe renombrar.</dd>
   <dt>NEW_ORG_NAME (necesario)</dt>
   <dd>Nombre de la nueva organización.</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Listar todos los espacios

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nombre de la organización. Lista los espacios en la organización especificada. De forma predeterminada toma la organización actual si no se especifica.</dd>
   <dt>-r</dt>
   <dd>Nombre de región. Lista los espacios en la región especificada. De forma predeterminada toma la región actual si no se especifica.</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-space ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualice usuarios en el archivo de organización según el rol.

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>ORG_NAME (necesario)</dt>
<dd>Nombre de la organización.</dd>
<dt>-a (opcional)</dt>
<dd>Lista todos los usuarios de la organización especificada, no agrupada por rol.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Añadir un usuario a la organización (es necesario ser gestor de organización).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Eliminar un usuario de la organización (gestor de organización o usuario mismo solamente)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Obtiene todos los roles de la organización del usuario actual

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID de usuario. Si no se especifica, el valor predeterminado es el usuario actual.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Asignar un rol de organización a un usuario. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
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
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Nota**: Establezca roles de espacios/organizaciones utilizando la interfaz de línea de mandatos, sin embargo, si desea establecer otros permisos, utilice la interfaz de usuario. Para obtener más información, consulte [Asignación de acceso de usuarios](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Elimine un rol de organización de un usuario. Esta operación solamente la puede llevar a cabo un gestor de la organización.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
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
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Visualice usuarios en el espacio especificado según el rol.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>El nombre del espacio.</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Asignar un rol de espacio a un usuario. Esta operación solamente la puede llevar a cabo un gestor de espacios.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Elimine un rol de espacio de un usuario. Esta operación solamente la puede llevar a cabo un gestor de espacios.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Lista todas las cuentas del usuario actual

```
ibmcloud account list
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualiza la cuenta de la organización especificada (se necesita un usuario de la organización)

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--guid (opcional)</dt>
  <dd>Visualiza únicamente el ID de la cuenta</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

Muestra usuarios asociados con la cuenta. Esta operación solamente puede realizarla el propietario de cuenta.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Eliminar un usuario de una cuenta (solo propietario de cuenta)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_ID (necesario)</dt>
<dd>ID de usuario</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID de cuenta. Si no se especifica, el valor predeterminado es la cuenta actual.</dd>
<dt>-f, --force</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invitar a un usuario a la cuenta

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario al que se invita.</dd>
   <dt>-o ORG</dt>
   <dd>Organización a la que invitar a un usuario</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Rol de organización. Las entradas válidas son: OrgManager, BillingManager, OrgAuditor y OrgUser. Si se omite, se establecerá el rol OrgUser.</dd>
   <dt>-s SPACE</dt>
   <dd>Espacio al que invitar al usuario</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Rol de espacio. Las entradas válidas son: SpaceManager, SpaceDeveloper y SpaceAuditor.</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Reenviar la invitación a un usuario (administrador de cuenta)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>Correo electrónico del usuario al que se vuelve a invitar.</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Listar grupos de acceso en la cuenta actual

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Lista todos los ID de servicio

```
ibmcloud iam service-ids [--uuid]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crear una nueva clave de API de la plataforma de {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
  <dt>-json</dt>
  <dd>Mostrar política en formato JSON</dd>
  <dt>-f, --force</dt>
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
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>SERVICE_ID (necesario)</dt>
  <dd>Nombre o UUID del ID de servicio</dd>
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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Listar grupos de recursos.

```
ibmcloud resource groups [--default]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
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


## ibmcloud app push
{: #ibmcloud_app_push}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf push ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## ibmcloud app list
{: #ibmcloud_app_list}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf apps ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## ibmcloud app show
{: #ibmcloud_app_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf app ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## ibmcloud app delete
{: #ibmcloud_app_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## ibmcloud app rename
{: #ibmcloud_app_rename}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## ibmcloud app start
{: #ibmcloud_app_start}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf start ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## ibmcloud app stop
{: #ibmcloud_app_stop}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stop ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## ibmcloud app restart
{: #ibmcloud_app_restart}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## ibmcloud app restage
{: #ibmcloud_app_restage}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restage ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf restart-app-instance ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## ibmcloud app events
{: #ibmcloud_app_events}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf events ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## ibmcloud app files
{: #ibmcloud_app_files}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf files ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## ibmcloud app logs
{: #ibmcloud_app_logs}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf logs ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## ibmcloud app env
{: #ibmcloud_app_env}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf set-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf unset-env ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stacks ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf stack ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-app-manifest ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
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

## ibmcloud app domain-cert-add
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

## ibmcloud app domain-cert-remove
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

## ibmcloud app routes
{: #ibmcloud_app_routes}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf check-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## ibmcloud app route-map
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


## ibmcloud app route-unmap
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


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-route ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-orphaned-routes ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## ibmcloud app domains
{: #ibmcloud_app_domains}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf domains ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-shared-domain ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


Este mandato tiene la misma función y las mismas opciones que el mandato [cf marketplace ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## ibmcloud service list
{: #ibmcloud_service_list}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf services ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## ibmcloud service show
{: #ibmcloud_service_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## ibmcloud service create
{: #ibmcloud_service_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## ibmcloud service update
{: #ibmcloud_service_update}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf update-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## ibmcloud service delete
{: #ibmcloud_service_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## ibmcloud service rename
{: #ibmcloud_service_rename}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf rename-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## ibmcloud service bind
{: #ibmcloud_service_bind}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf bind-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf unbind-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf delete-service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## ibmcloud service keys
{: #ibmcloud_service_keys}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service-keys ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf service-key ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf create-user-provided-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

Este mandato tiene la misma función y las mismas opciones que el mandato [cf update-user-provided-service ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Listar instancias de servicio

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
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
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostrar los detalles de una instancia de servicio

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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

<strong>Requisitos previos</strong>:  Punto final, inicio de sesión, destino

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
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crear un enlace de servicio

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
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
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Mostrar detalles de una clave de servicio

```
ibmcloud resource service-key KEY_NAME [--id]
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
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crear una clave de servicio

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
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
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Listar los alias de una instancia de servicio

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
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
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostrar detalles de un alias de servicio

```
ibmcloud resource service-alias ALIAS_NAME [--id]
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
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crear un alias de una instancia de servicio

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
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
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Actualizar un alias de servicio

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
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
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Suprimir un alias de servicio

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
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
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Buscar recursos utilizando la sintaxis de consultas de Lucene

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

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


## ibmcloud catalog search
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


## ibmcloud catalog entry
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


## ibmcloud catalog entry-create
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


## ibmcloud catalog entry-update
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

## ibmcloud catalog entry-delete
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


## ibmcloud catalog entry-visibility
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


## ibmcloud catalog entry-visibility-set
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


## ibmcloud catalog service-marketplace
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

## ibmcloud catalog templates
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


## ibmcloud catalog template
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


## ibmcloud catalog template-run
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

## ibmcloud catalog locations
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

## ibmcloud catalog runtime
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

## ibmcloud catalog runtimes
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

## ibmcloud billing account-usage
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

## ibmcloud billing org-usage
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


## ibmcloud billing resource-group-usage
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

## ibmcloud billing resource-instances-usage
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

Eliminar el repositorio `bluemix-repo` de {{site.data.keyword.Bluemix_notm}} CLI:

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

Instalar la versión específica del plug-in en {{site.data.keyword.Bluemix_notm}} CLI desde la vía de acceso o el repositorio especificados.

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

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Listar entornos de CFEE.

```
bx cfee environments
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostrar detalles de un entorno CFEE.

```
bx cfee environment NAME [--id]
```

<strong>Requisitos previos</strong>:  Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostrar solo ID.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar detalles de un entorno CFEE env_example:

```
bx cfee environment env_example
```

Mostrar ID de un entorno CFEE env_example:

```
bx cfee environment env_example --id
```
