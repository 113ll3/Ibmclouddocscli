---



copyright:

  years: 2015, 2018
lastupdated: "2018-02-14"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Commandes {{site.data.keyword.Bluemix_notm}} (bx)
{: #bluemix_cli}

Version : 0.6.5

L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} fournit un ensemble de commandes qui sont regroupées par espace de nom pour que les utilisateurs puissent interagir avec {{site.data.keyword.Bluemix_notm}}.

A compter de la version 0.5.0, le client de ligne de commande {{site.data.keyword.Bluemix_notm}} inclut un client de ligne de commande Cloud Foundry dans son installation. Si vous disposez de votre propre installation d'interface CLI cf, n'utilisez pas en même temps les commandes CLI {{site.data.keyword.Bluemix_notm}} `bx [command]` et les commandes CLI Cloud Foundry `cf [command]` de votre installation dans le même contexte. A la place, exécutez `bluemix cf [command]` si vous souhaitez utiliser l'interface CLI cf pour gérer des ressources Cloud Foundry dans le contexte CLI {{site.data.keyword.Bluemix_notm}}.  Notez que `bluemix cf api/login/logout/target` n'est pas admis, vous devez utiliser `bluemix api/login/logout/target` à la place.

Les listes ci-dessous répertorient les commandes prises en charge par l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, en indiquant leurs noms, leurs arguments, leurs options, leurs prérequis, leurs descriptions, et des exemples.
{:shortdesc}

**Remarque :** la zone *Prérequis* répertorie les actions qui sont requises avant l'utilisation de la commande. Les commandes pour lesquelles aucune action n'est requise indiquent **Aucun**. Sinon, les prérequis peuvent inclure une ou plusieurs des actions suivantes :

<dl>
<dt>Noeud final</dt>
<dd>Un noeud final d'API doit être défini via <code>bluemix api</code> avant l'utilisation de la commande.</dd>
<dt>Connexion</dt>
<dd>La connexion avec la commande <code>bluemix login</code> est requise avant l'utilisation de cette commande.
Si vous vous connectez avec un ID fédéré, utilisez l'option '--sso' pour vous authentifier avec un code d'accès unique ou utilisez l'option '--apikey' pour vous authentifier avec une clé d'API. Dans la console {{site.data.keyword.Bluemix_notm}} sélectionnez **Gérer** &gt; **Sécurité** &gt; **Clés d'API de la plateforme** pour créer des clés d'API.
</dd>
<dt>Cible</dt>
<dd>La commande <code>bluemix target</code> doit être utilisée pour définir une organisation et un espace avant l'utilisation de cette commande.</dd>
<dt>Docker</dt>
<dd>L'interface de ligne de commande Docker (docker) doit être installée pour que vous puissiez exécuter cette commande.</dd>
</dl>

**Remarque :** vous pouvez utiliser le format abrégé
des commandes Bluemix. Par exemple, `bx api` est la forme
abrégée de `bluemix api`.

Utilisez les index des tableaux suivants pour examiner les commandes Bluemix fréquemment utilisées.

## Commandes générales Bluemix
{: #bx_commands_index}

<table summary="Commandes générales Bluemix.">
<caption>Tableau 1. Commandes générales Bluemix</caption>
 <thead>
 <th colspan="5">Commandes générales Bluemix</th>
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

 ## Commandes de gestion et de configuration des services d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)
  {: #bx_commands_softlayer}

Les commandes de gestion d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} ont été fusionnées dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations sur l'utilisation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} dans le but de configurer et gérer des services d'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, voir : [{{site.data.keyword.Bluemix_notm}} Commandes d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)](/docs/cli/reference/softlayer/index.md#softlayer_cli).

 ## Commandes de gestion des comptes, des organisations et des rôles
 {: #bx_commands_account}

<table summary="Commandes Bluemix que vous pouvez utiliser pour gérer des comptes, des organisations, des espaces et des rôles.">
<caption>Tableau 2. Commandes de gestion des comptes, des organisations, des espaces et des rôles</caption>
 <thead>
 <th colspan="5">Commandes de gestion des comptes, des organisations, des espaces et des rôles</th>
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


 ## Commandes de gestion des groupes de ressources et des ressources
{: #bx_commands_resource}

<table summary="Commandes Bluemix que vous pouvez utiliser pour gérer des groupes de ressources et des ressources.">
  <caption>Tableau 3. Commandes de gestion des groupes de ressources et des ressources</caption>
  <thead>
    <th colspan="5">Commandes de gestion des groupes de ressources et des ressources</th>
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


 ## Commandes de gestion des clés d'API et des règles
 {: #bx_commands_iam}
 <table summary="Commandes Bluemix que vous pouvez utiliser pour gérer des clés d'API et des règles.">
 <caption>Tableau 3. Commandes de gestion des clés d'API et des règles</caption>
  <thead>
  <th colspan="5">Commandes de gestion des clés d'API et des règles</th>
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

 ## Commandes de gestion des applications CF et des domaines, routes et certificats liés aux applications
 {: #bx_commands_apps}

<table summary="Commandes Bluemix que vous pouvez utiliser pour gérer des applications CF et des domaines, des routes et des certificats liés aux applications.">
<caption>Tableau 4. Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</caption>
 <thead>
 <th colspan="5">Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</th>
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

 ## Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="Commandes Bluemix que vous pouvez utiliser pour gérer des services {{site.data.keyword.Bluemix_notm}}.">
<caption>Tableau 5. Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}</th>
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


 ## Commandes de gestion des paramètres de catalogue, de plug-in et de facturation
 {: #bx_commands_settings}

<table summary="Commandes Bluemix que vous pouvez utiliser pour gérer les paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}.">
<caption>Tableau 6. Commandes de gestion des paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de gestion des paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}</th>
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
Afficher l'aide générale pour les commandes intégrées de premier niveau et les espaces de nom pris en charge de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, ou l'aide d'une commande intégrée ou d'un espace de nom spécifique.

```
bluemix help [COMMAND|NAMESPACE]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>COMMAND|NAMESPACE (facultatif))</dt>
   <dd>Commande ou espace de nom pour lequel afficher l'aide. Si la commande ou l'espace de nom n'est pas spécifié, l'aide générale de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est affichée.</dd>
   </dl>



<strong>Exemples</strong> :

Afficher l'aide générale pour l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} :

```
bluemix help
```

Afficher l'aide pour la commande `info` :

```
bluemix help info
```



## bluemix api
{: #bluemix_api}
Définir ou afficher le noeud final d'API {{site.data.keyword.Bluemix_notm}}.

```
bluemix api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>API_ENDPOINT (facultatif)</dt>
   <dd>Noeud final d'API ciblé. Par exemple, `https://api.chinabluemix.net`. Si l'option *NOEUD_FINAL_API* et l'option `--unset` sont toutes les deux spécifiées, le noeud final d'API en cours est affiché.</dd>
   <dt>--unset (facultatif)</dt>
   <dd>Supprimer le paramètre de noeud final d'API.</dd>
   <dt>--skip-ssl-validation (facultatif)</dt>
   <dd>Ignorer la validation SSL des demandes HTTP.</dd>
   </dl>
<strong>Exemples</strong> :

Définir le noeud final d'API api.chinabluemix.net :

```
bluemix api api.chinabluemix.net
```

```
bluemix api https://api.chinabluemix.net --skip-ssl-validation
```

Afficher le noeud final d'API en cours :

```
bluemix api
```

Annulez la définition du noeud final d'API :

```
bluemix api --unset
```

## bluemix config
{: #bluemix_config}


Ecrire les valeurs par défaut dans le fichier de configuration.

```
bluemix config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Délai d'attente pour les demandes HTTP. La valeur par défaut est 60 secondes.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Consigne la trace des demandes HTTP sur le terminal ou dans le fichier spécifié.</dd>
   <dt>--color true|false</dt>
   <dd>Active ou désactive la sortie en couleurs. Elle est activée par défaut.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Définit un environnement local par défaut. Si LOCALE a pour valeur <i>CLEAR</i>, l'environnement local précédent est supprimé.</dd>
   <dt>--check-version true|false</dt>
   <dd>Active ou désactive la vérification de la version de l'interface de ligne de commande.</dd>
   </dl>

Une seule de ces options peut être indiquée à la fois.

<strong>Exemples</strong> :

Définir le délai d'attente des demandes HTTP à 30 secondes :

```
bluemix config --http-timeout 30
```

Activez la sortie de trace pour les demandes HTTP :

```
bluemix config --trace true
```

Consigner la trace des demandes HTTP dans le fichier spécifié */home/usera/my_trace* :

```
bluemix config --trace /home/usera/my_trace
```

Désactivez la sortie couleur :

```
bluemix config --color false
```

Définir l'environnement local zh_Hans :

```
bluemix config --locale zh_Hans
```

Effacer les paramètres d'environnement local :

```
bluemix config --locale CLEAR
```



## bluemix info
{: #bluemix_info}

Afficher les informations {{site.data.keyword.Bluemix_notm}} de base, notamment la région en cours, la version du contrôleur de cloud et certains noeuds finaux utiles tels que les noeuds finaux pour la connexion et l'échange de jeton d'accès.

```
bluemix info
```

<strong>Prérequis</strong> : Noeud final


## bluemix cf
{: #bluemix_cf}

Appelez l'interface CLI CF imbriquée

```
bluemix [-q, --quiet] cf COMMAND...
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-q, --quiet</dt>
  <dd>Désactivez le message "Appel de commande cf..."</dd>
</dl>

<strong>Exemples</strong> :

Liste d'applications CF :

```
bluemix cf apps
```

Liste de services CF sans le message "Appel de commande cf...":

```
bluemix -q cf services
```


## bluemix login
{: #bluemix_login}

Connectez l'utilisateur.

```
bluemix login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-o ORG] [-s SPACE]
```

<strong>Prérequis</strong> : Aucun

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Options de commande</strong> :
<dl>
  <dt> -a <i>API_ENDPOINT</i> (facultatif)</dt>
  <dd> Noeud final de l'API (par exemple : api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY ou @API_KEY_FILE_PATH</i>
  <dd> Contenu de clé d'API ou chemin d'un fichier de clés d'API indiqué par @</dd>
  <dt> --sso (facultatif) </dt>
  <dd> Utiliser un code d'accès unique pour se connecter </dd>
  <dt> -u <i>USERNAME</i> (facultatif)</dt>
  <dd> Nom d'utilisateur</dd>
  <dt> -p <i>PASSWORD</i> (facultatif)</dt>
  <dd> Mot de passe</dd>
  <dt> -c <i>ACCOUNT_ID</i> (facultatif) </dt>
  <dd> ID du compte cible</dd>
  <dt> -o <i>ORG_NAME</i> (facultatif) </dt>
  <dd> Nom de l'organisation cible </dd>
  <dt> -s <i>SPACE_NAME</i> (facultatif) </dt>
  <dd> Nom de l'espace cible</dd>
  <dt> --no-iam </dt>
  <dd> Imposer une authentification avec un serveur de connexion plutôt qu'avec un système IAM public</dd>
  <dt> --skip-ssl-validation (facultatif) </dt>
  <dd> Ignorer la validation SSL des demandes HTTP. Cette option n'est pas recommandée.</dd>
</dl>

<strong>Exemples</strong> :

#### Connexion en mode interactif

```
bluemix login
```

Connectez-vous avec un nom d'utilisateur et un mot de passe, puis définissez un compte, une organisation et un espace cible :

```
bluemix login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Connectez-vous avec un code d'accès unique et définissez un compte, une organisation et un espace cible

```
bluemix login --sso -c MyAccountID -o MyOrg -s MySpace
```

Connectez-vous avec une clé d'API et définissez des cibles :

#### Un compte est associé à une clé d'API

```
bluemix login --apikey api-key-string -o MyOrg -s MySpace
```

```
bluemix login --apikey @filename -o MyOrg -s MySpace
```

#### Aucun compte n'est associé à une clé d'API

```
bluemix login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
bluemix login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Remarque :</strong> si un compte est associé à la clé d'API, le passage à un autre compte n'est pas autorisé.

#### Utilisez un code d'accès unique

```
bluemix login -u UserID --sso
```

L'interface de ligne de commande fournira ensuite un lien d'URL et demandera un code d'accès :
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Ouvrez le lien dans un navigateur et laissez-vous guider pour obtenir le code secret. Entrez le code d'accès qui vous a été fourni dans la console. Vous devriez pouvoir vous connecter.

## bluemix logout
{: #bluemix_logout}

Déconnectez l'utilisateur.

```
bluemix logout
```

<strong>Prérequis</strong> : Aucun

## bluemix regions
{: #bluemix_regions}

Afficher les informations pour toutes les régions dans {{site.data.keyword.Bluemix_notm}}.

```
bluemix regions
```

<strong>Prérequis</strong> : Noeud final


## bluemix target
{: #bluemix_target}


Définir ou afficher le compte, la région, l'organisation ou l'espace cible :

```
bluemix target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r <i>REGION_NAME</i> (facultatif)</dt>
   <dd>Nom de la région vers laquelle commuter, par exemple 'us-south' ou 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (facultatif)</dt>
   <dd>ID du compte à cibler.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (facultatif)</dt>
   <dd>Nom du groupe de ressources.</dd>
   <dt>--cf</dt>
   <dd>Sélectionner l'organisation et l'espace cible de manière interactive</dd>
   <dt>-o <i>ORG_NAME</i> (facultatif)</dt>
   <dd>Nom de l'organisation à cibler.</dd>
   <dt>-s <i>SPACE_NAME</i> (facultatif)</dt>
   <dd>Nom de l'espace à cibler.</dd>
   </dl>
Si aucune de ces options n'est spécifiée, le compte, la région, l'organisation et l'espace en cours s'affichent.

<strong>Exemples</strong> :

Définir le compte, l'organisation et l'espace en cours :

```
bluemix target -c MyAccountID -o MyOrg -s MySpace
```

Basculez vers une nouvelle région :

```
bluemix target -r eu-gb
```

Afficher le compte, la région, l'organisation et l'espace en cours :

```
bluemix target
```

## bluemix update
{: #bluemix_update}

Mettre à jour l'interface de ligne de commande vers la version la plus récente.

```
bluemix update
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

### bluemix account orgs
{: #bluemix_account_orgs}

Répertorier toutes les organisations

```
bluemix account orgs [-r REGION] [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r <i>REGION</i> (facultatif)</dt>
   <dd>Spécifie la région pour laquelle afficher les informations de l'organisation. Si vous spécifiez 'all', toutes les
organisations de toutes les régions sont répertoriées.</dd>
   <dt>--guid (facultatif)</dt>
   <dd>Affiche l'identificateur global unique (GUID) des organisations.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier toutes les organisations dans la région `us-south` en affichant leur identificateur global unique

```
bluemix account orgs -r us-south --guid
```

## bluemix account org
{: #bluemix_account_org}

Affiche des informations sur l'organisation spécifiée.

```
bluemix account org ORG_NAME [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>--guid (facultatif)</dt>
   <dd>Affiche l'identificateur global unique (GUID) de l'organisation.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les informations de l'organisation `IBM` en indiquant son identificateur global unique (GUID)

```
bluemix account org IBM --guid
```


## bluemix account org-create
{: #bluemix_account_org_create}

Crée une nouvelle organisation. Cette opération ne peut être effectuée que par un propriétaire de compte.

```
bluemix account org-create ORG_NAME [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à créer.</dd>
   <dt>-f</dt>
   <dd>Forcer la création sans confirmation.</dd>
   </dl>

<strong>Exemples</strong> :

Création d'une organisation nommée `IBM`.

```
bluemix account org-create IBM
```

## bluemix account org-replicate
{: #bluemix_account_org_replicate}

Répliquez une organisation de la région en cours dans une autre région.

```
bluemix account org-replicate ORG_NAME REGION_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation existante à répliquer.</dd>
   <dt>REGION_NAME (obligatoire)</dt>
   <dd>Nom de la région hébergeant l'organisation répliquée.</dd>
   </dl>

<strong>Exemples</strong> :

Réplication de l'organisation `mon_org` dans la région `eu-gb`:

```
bluemix account org-replicate myorg eu-gb
```


## bluemix account org-rename
{: #bluemix_account_org_rename}

Attribue un nouveau nom à une organisation. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
bluemix account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>OLD_ORG_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'organisation qui sera renommée.</dd>
   <dt>NEW_ORG_NAME (obligatoire)</dt>
   <dd>Nouveau nom à affecter à l'organisation.</dd>
   </dl>


## bluemix account spaces
{: #bluemix_account_spaces}

Répertorier tous les espaces

```
bluemix account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-o</dt>
   <dd>Nom de l'organisation. Liste des espaces sous l'organisation spécifiée. Valeur par défaut sur l'organisation actuelle si rien n'est indiqué.</dd>
   <dt>-r</dt>
   <dd>Nom de région. Liste des espaces sous la région spécifiée. Valeur par défaut sur la région actuelle si rien n'est indiqué.</dd>
   </dl>



## bluemix account space
{: #bluemix_account_space}

Cette commande possède la même fonction et les mêmes options que la commande `cf space`.


## bluemix account space-create
{: #bluemix_account_space_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-space`.


## bluemix account space-rename
{: #bluemix_account_space_rename}


Cette commande possède la même fonction et les mêmes options que la commande `cf rename-space`.


## bluemix account space-delete
{: #bluemix_account_space_delete}


Cette commande possède la même fonction et les mêmes options que la commande `cf delete-space`.

## bluemix account org-users
{: #bluemix_account_org_users}

Affiche les utilisateurs dans l'organisation spécifiée, par rôle.

```
bluemix account org-users ORG_NAME [-a]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>ORG_NAME (obligatoire)</dt>
<dd>Nom de l'organisation.</dd>
<dt>-a (facultatif)</dt>
<dd>Recense tous les utilisateurs de l'organisation spécifiés, sans les regrouper par rôle.</dd>
</dl>

## bluemix account org-user-add
{: #bluemix_account_org_user_add}

Ajouter un utilisateur à une organisation (un responsable d'organisation est requis).

```
 bluemix account org-user-add USER_NAME ORG
```

## bluemix account org-user-remove
{: #bluemix_account_org_user_remove}

Retirer un utilisateur d'une organisation (responsable d'organisation ou utilisateur/utilisatrice proprement dit(e))

```
   bluemix account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Options de commande</strong> :
<dl>
<dt>--force, -f</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## bluemix account org-roles
{: #bluemix_account_org_roles}

Extraire tous les rôles d'organisation de l'utilisateur en cours

```
bluemix account org-roles [-u USER_ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>-u</dt>
   <dd>ID utilisateur. S'il n'est pas spécifié, la valeur par défaut est l'utilisateur en cours.</dd>
  </dl>

## bluemix account org-role-set
{: #bluemix_account_org_role_set}

Affecte un rôle de l'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
bluemix account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à affecter.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>ORG_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation auquel cet utilisateur est affecté. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
  </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` sous le rôle `OrgManager` :

```
bluemix account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Remarque **: vous pouvez définir des rôles d'organisation ou d'espace via l'interface CLI, mais pour les autres autorisations, il vous utiliser l'interface utilisateur. Pour plus d'informations, voir [Octroi d'un accès utilisateur](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## bluemix account org-role-unset
{: #bluemix_account_org_role_unset}

Supprime l'affectation d'un rôle d'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
bluemix account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à supprimer.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>ORG_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
    </dl>

<strong>Exemples</strong> :

Retirer l'utilisatrice `Mary` de l'organisation `IBM` sous le rôle `OrgManager` :

```
bluemix account org-role-unset Mary IBM OrgManager
```

## bluemix account space-users
{: #bluemix_account_space_users}

Affichage des utilisateurs, par rôle, dans l'espace spécifié.

```
bluemix account space-users ORG_NAME SPACE_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace.</dd>
   </dl>


## bluemix account space-role-set
{: #bluemix_account_space_role_set}

Affecte un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
bluemix account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à affecter.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace auquel affecter cet utilisateur.</dd>
   <dt>SPACE_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace auquel affecter cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
    </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` et à l'espace `Cloud` sous le rôle `SpaceManager` :

```
bluemix account space-role-set Mary IBM Cloud SpaceManager
```

## bluemix account space-role-unset
{: #bluemix_account_space_role_unset}

Suppression de l'affectation d'un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
bluemix account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à supprimer.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace dans lequel supprimer cet utilisateur.</dd>
   <dt>SPACE_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
    </dl>


<strong>Exemples</strong> :

Retirer l'utilisatrice `Mary` de l'organisation `IBM` et de l'espace `Cloud` sous le rôle `SpaceManager` :

```
bluemix account space-role-unset Mary IBM Cloud SpaceManager
```

## bluemix account list
{: #bluemix_account_list}

Afficher la liste de tous les comptes de l'utilisateur en cours

```
bluemix account list
```

<strong>Prérequis</strong> : Noeud final, Connexion


## bluemix account org-account
{: #bluemix_account_org_account}

Afficher le compte de l'organisation spécifiée (utilisateur d'organisation requis).

```
bluemix account org-account ORG_NAME [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--guid (facultatif)</dt>
  <dd>Affiche uniquement l'ID de compte</dd>
</dl>


## bluemix account users
{: #bluemix_account_users}

Affiche les utilisateurs associés au compte. Cette opération ne peut être effectuée que par le propriétaire de compte.

```
bluemix account users
```

## bluemix account user-delete
{: #bluemix_account_user_delete}

Supprimer un utilisateur dans le compte en cours (propriétaire de compte seulement).

```
bluemix account user-delete USERNAME [-c ACCOUNT_ID] [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>USERNAME (obligatoire)</dt>
<dd>Nom d'utilisateur</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID compte. Si ce paramètre n'est pas spécifié, le compte en cours est pris par défaut.</dd>
<dt>--force, -f (facultatif)</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## bluemix account user-invite
{: #bluemix_account_user_invite}

Invite un utilisateur à rejoindre le compte. Cette opération ne peut être effectuée que par le propriétaire de compte.

```
bluemix account user-invite USER_EMAIL
```

## bluemix account user-reinvite
{: #bluemix_account_user_reinvite}

Renvoie l'invitation à un utilisateur (propriétaire du compte requis).

```
bluemix account user-reinvite USER_EMAIL
```

<strong>Prérequis</strong> : Noeud final, Connexion
  
 <strong>Options de commande</strong> :
 <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur invité.</dd>
 </dl>



## bluemix iam service-ids
{: #bluemix_iam_service_ids}

Répertorier tous les ID de service

```
bluemix iam service-ids --uuid
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-uuid</dt>
  <dd>Afficher l'identificateur unique universel des ID de service uniquement</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les identificateurs uniques universels de tous les ID de service sous le compte en cours

```
bluemix iam service-ids --uuid
```


## bluemix iam service-id
{: #bluemix_iam_service_id}

Afficher les détails d'un ID de service

```
bluemix iam service-id NAME [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-uuid</dt>
  <dd>Afficher l'identificateur unique universel de l'ID de service</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'ID de service `sample-test`

```
bluemix iam service-id sample-test
```


## bluemix iam service-id-create
{: #bluemix_iam_service_id_create}

Créez un ID de service

```
bluemix iam service-id-create NAME [-d, --description DESCRIPTION]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Description de l'ID de service</dd>
</dl>

<strong>Exemples</strong> :

Créez un ID de service avec le nom `sample-test` et la description `hello, world!`

```
bluemix iam service-id-create sample-test -d 'hello, world!'
```


## bluemix iam service-id-update

{: #bluemix_iam_service_id_update}
Mettre à jour un ID de service

```
bluemix iam service-id-update NAME [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description du service</dd>
  <dt>-v, --version</dt>
  <dd>Version de l'ID de service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez l'ID de service `sample-test` en `sample-test-2` sans demander de confirmation

```
bluemix iam service-id-update sample-test -n sample-test-2 -f
```

Mettre à jour la description of service `sample-test` version `1-0jn39fbefew`

```
bluemix iam service-id-update sample-test -d 'hello, friend!' -v 1-0jn39fbefew
```


## bluemix iam service-id-delete
{: #bluemix_iam_service_id_delete}

Supprimer un ID de service

```
bluemix iam service-id-delete NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'ID de service `sample-teset` sans demander de confirmation

```
bluemix iam service-id-delete sample-teset -f
```


## bluemix iam api-keys
{: #bluemix_iam_api_keys}

Répertorier toutes les clés d'API de la plateforme {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-keys
```

<strong>Prérequis</strong> : Noeud final, Connexion

## bluemix iam api-key-create
{: #bluemix_iam_api_key_create}

Créez une nouvelle clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à créer.</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Description de la clé d'API</dd>
<dt>-f, -- file <i>FILE</i></dt>
<dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
</dl>

<strong>Exemples</strong> :

Créez une clé d'API et de la sauvegarder dans un fichier

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
```

## bluemix iam api-key-update
{: #bluemix_iam_api_key_update}

Mettre à jour une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Ancien nom de la clé d'API qui doit être mise à jour</dd>
<dt>-n <i>NAME</i> (facultatif)</dt>
<dd>Nouveau nom de la clé d'API</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Nouvelle description de la clé d'API</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la description d'une clé d'API :

```
bluemix iam api-key-update MyKey -d "the new description of my key"
```

## bluemix api-key-delete
{: #bluemix_api_key_delete}

Supprimer une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
bluemix iam api-key-delete NAME [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à supprimer.</dd>
<dt>-f (facultatif)</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## bluemix iam service-api-keys
{: #bluemix_iam_service_api_keys}

Répertorier toutes les clés d'API d'un service

```
bluemix iam service-api-keys SERVICE_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les clés d'API du service `sample-service` :

```
bluemix iam service-api-keys sample-service
```

## bluemix iam service-api-key
{: #bluemix_iam_service_api_key}

Répertorier les détails d'une clé d'API de service

```
bluemix iam service-api-key NAME SERVICE_ID [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-uuid</dt>
  <dd>Afficher l'identificateur unique universel de la clé d'API de service</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la clé d'API de service `sample-key` du service `sample-service` :

```
bluemix iam service-api-key sample-key sample-service
```

## bluemix iam service-api-key-create
{: #bluemix_iam_service_api_key_create}

Créez une clé d'API de service

```
bluemix iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [-f, --file FILE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-d, --description</dt>
  <dd>Description de la clé d'API</dd>
  <dt>-f, --file</dt>
  <dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
</dl>

<strong>Exemples</strong> :

Créez la clé d'API de service `sample-key` pour le service `sample-service` :

```
bluemix iam service-api-key-create sample-key sample-service
```

## bluemix iam service-api-key-update
{: #bluemix_iam_service_api_key_update}

Mettre à jour une clé d'API de service

```
bluemix iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de la clé d'API de service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description de la clé d'API de service</dd>
  <dt>-v, --version</dt>
  <dd>Version de la clé d'API de service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez la clé d'API de service `sample-key` en `new-sample-key` :

```
bluemix iam service-api-key-update sample-key sample-service -n new-sample-key
```

## bluemix iam service-api-key-delete
{: #bluemix_iam_service_api_key_delete}

Supprimer une clé d'API de service

```
bluemix iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la clé d'API de service `sample-key` :

```
bluemix iam service-api-key-delete sample-key sample-service
```

## bluemix iam user-policies
{: #bluemix_iam_user_policies}

Afficher les règles de l'utilisateur `name@example.com` :

```
bluemix iam user-policies name@example.com
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel les règles appartiennent</dd>
</dl>

<strong>Exemples</strong> :

Afficher les règles de l'utilisateur `name@example.com` :

```
bluemix iam user-policies name@example.com
```

## bluemix iam user-policy
{: #bluemix_iam_user_policy}

Afficher les détails d'une règle utilisateur

```
bluemix iam user-policy USER_NAME POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle</dd>
</dl>

<strong>Exemples</strong> :

Afficher la règle `0bb730daa` de l'utilisateur `name@example.com` :

```
bluemix iam user-policy name@example.com 0bb730daa
```

## bluemix iam user-policy-create
{: #bluemix_iam_user_policy_create}

Créez une règle utilisateur

```
bluemix iam user-policy-create USER_NAME {-f, --file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>-f, --file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour les rôles pris en charge d'un service spécifique, exécutez 'bluemix iam roles --service SERVICE_NAME'. Cette option exclut '-f, --file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE</i> (facultatif)</dt>
<dd>Instance de service de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. Exclusif avec les indicateurs '-f, --file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. Exclusif avec les indicateurs '-f, --file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Créez une règle utilisateur pour l'utilisateur `name@example.com` à partir du fichier JSON de règles `policy.json` :

```
bluemix iam user-policy-create name@example.com -f @policy.json
```

Accordez le rôle `Administrator` à `name@example.com` pour toutes les ressources `sample-service` :

```
bluemix iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Accordez le rôle `Editor` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service`ServiceId-ade78e9f` dans la région `us-south` :

```
bluemix iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

Accordez le rôle `Operator` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
bluemix iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Accordez le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Accordez le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## bluemix iam user-policy-update
{: #bluemix_iam_user_policy_update}

Mettre à jour une règle utilisateur

```
bluemix iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle à mettre à jour</dd>
<dt>-v, --version <i>VERSION</i> (facultatif)</dt>
<dd>Version de règle existante</dd>
<dt>-f, --file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>-f, --file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour les rôles pris en charge d'un service spécifique, exécutez 'bluemix iam roles --service SERVICE_NAME'. Cette option exclut '-f, --file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE</i> (facultatif)</dt>
<dd>Instance de service de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. Exclusif avec l'indicateur '-f, --file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. Exclusif avec les indicateurs '-f, --file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. Exclusif avec les indicateurs '-f, --file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle utilisateur avec celle définie dans le fichier JSON

```
bluemix iam user-policy-update name@example.com 0bb730daa -f @policy.json
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Administrator` à `name@example.com` pour toutes les ressources `sample-service` :

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Mettre à jour une règle utilisateur afin d'accorder le rôle `Editor` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service `ServiceId-ade78e9f` dans la région `us-south` :

```
bluemix iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Operator` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```



## bluemix iam service-policies
{: #bluemix_iam_service_policies}

Répertorier toutes les règles de service du service spécifié

```
bluemix iam service-policies SERVICE_ID_NAME [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom d'ID de service</dd>
  <dt>-json</dt>
  <dd>Afficher la règle au format JSON</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les règles de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les règles du service `test` :

```
bluemix iam service-policies test
```


## bluemix iam service-policy
{: #bluemix_iam_service_policy}

Afficher les détails d'une règle de service

```
bluemix iam service-policy SERVICE_ID_NAME POLICY_ID [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom d'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-json</dt>
  <dd>Afficher la règle au format JSON</dd>
  <dt>-f, --force</dt>
  <dd>Afficher la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Afficher la règle `140798e2-8ea7db3` du service `test` :

```
bluemix iam service-policies test 140798e2-8ea7db3
```


## bluemix iam service-policy-create
{: #bluemix_iam_service_policy_create}

Créer une règle de service

```
bluemix iam service-policy-create SERVICE_ID_NAME {-f, --file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom d'ID de service</dd>
  <dt>-f, --file</dt>
  <dd>Fichier JSON de définition de règle. Exclut les indicateurs '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' et '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour les rôles pris en charge d'un service spécifique, exécutez 'bluemix iam roles --service SERVICE_NAME'. Cette option exclut '-f, --file'.</dd>
  <dt>--service-name</dt>
  <dd>Nom de service de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>--service-instance</dt>
  <dd>Instance de service de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>--resource-type</dt>
  <dd>Type de ressource de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>--resource</dt>
  <dd>Ressource de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option exclut '-f, --file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option exclut '-f, --file' et '--resource-group-name'.</dd>
  <dt>-F, --force</dt>
  <dd>Créer la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une règle de service à partir du fichier JSON pour le service `test` :

```
bluemix iam service-policy-create test -f @policy.json
```


## bluemix iam service-policy-update
{: #bluemix_iam_service_policy_update}

Mettre à jour une règle de service

```
bluemix iam service-policy-update SERVICE_ID_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom d'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-v, --version</dt>
  <dd>Version de la règle de service</dd>
  <dt>-f, --file</dt>
  <dd>Fichier JSON de définition de règle. Exclut les indicateurs -r, --roles, --service-name, --service-instance, --region, --resource-type, --resource, resource-group-name et resource-group-id.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour les rôles pris en charge d'un service spécifique, exécutez 'bluemix iam roles --service SERVICE_NAME'. Cette option exclut '-f, --file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>-service-instance</dt>
  <dd>Instance de service de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Exclut l'indicateur '-f, --file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option exclut '-f, --file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option exclut '-f, --file' et '--resource-group-name'.</dd>
  <dt>-F, --force</dt>
  <dd>Mettre à jour la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `test` :

```
bluemix iam service-policy-update test 140798e2-8ea7db3 -f @policy.json
```

## bluemix iam service-policy-delete
{: #bluemix_iam_service_policy_delete}

Supprimer une règle de service

```
bluemix iam service-policy-delete SERVICE_ID_NAME POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom d'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la règle `140798e2-8ea7db3` du service `test`

```
bluemix iam service-policy-delete test 140798e2-8ea7db3
```

## bluemix iam oauth-tokens
{: #bluemix_iam_oauth_tokens}

Extraire et afficher les jetons OAuth de la session en cours. 

```
bluemix iam oauth-tokens
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Actualiser et afficher les jetons OAuth.

```
bluemix iam oauth-tokens
```

## bluemix iam dedicated-id-disconnect
{: #bluemix_iam_dedicated_id_disconnect}

Déconnecter l'IBMid public de l'ID non IBMid dédié.

```
bluemix iam dedicated-id-disconnect [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la déconnexion sans confirmation.</dd>
</dl>

## bluemix iam authorization-policy-create
{: #bluemix_iam_authorization_policy_create}
 
Créer une règle d'autorisation permettant à une instance de service d'accéder à une autre instance de service. 

```
bluemix iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME] ROLE_NAME1,ROLE_NAME2...
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Service source dont l'accès peut être autorisé.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Service cible auquel le service source peut être autorisé à accéder. </dd>
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service source ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service source. </dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service cible ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service cible.    </dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Rôles permettant d'accéder au service source. </dd>  
</dl>

## bluemix iam authorization-policy-delete
{: #bluemix_iam_authorization_policy_delete}

Supprimer une règle d'autorisation.

```
bluemix iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID de la règle d'autorisation à supprimer.</dd> 
 <dt>-f, --force</dt>
 <dd>Forcer la suppression sans confirmation.</dd> 
</dl>

## bluemix iam authorization-policy
{: #bluemix_iam_authorization_policy}

Afficher les détails d'une règle d'autorisation.

```
bluemix iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID de la règle d'autorisation à afficher.</dd> 
</dl>


## bluemix iam authorization-policies
{: #bluemix_iam_authorization_policies}

Répertorier les règles d'autorisation du compte en cours. 

```
bluemix iam authorization-policies
```

<strong>Prérequis</strong> : Noeud final, Connexion

## bluemix resource groups
{: #bluemix_resource_groups}

Répertorier les groupes de ressources.

```
bluemix resource groups [--default]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--default</dt>
  <dd>Obtenir le groupe par défaut du compte en cours. </dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes de ressources du compte actuellement ciblé : 

```
bluemix resource groups
```

Répertorier le groupe par défaut du compte actuellement ciblé :

```
bluemix resource groups --default
```

## bluemix resource group
{: #bluemix_resource_group}

Afficher les détails d'un groupe de ressources.

```
bluemix resource group NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources.</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID uniquement</dd>
</dl>

<strong>Exemples</strong> :

Afficher le groupe de ressources `example-group` :

```
bluemix resource group example-group
```

Afficher uniquement le groupe de ressources `example-group` :

```
bluemix resource group example-group --id
```


## bluemix resource group-update
{: #bluemix_resource_group_update}

Mettre à jour un groupe de ressources existant.

```
bluemix resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources cible.</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du groupe de ressources.</dd>
  <dt>-q, --quota</dt>
  <dd>Nom de la nouvelle définition de quota.</dd>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe de ressources `example-group` en `trial-group` :

```
bluemix resource group-update example-group -n trial-group
```

Modifier le quota du groupe de ressources `example-group` et le remplacer par `free` :

```
bluemix resource group-update example-group -q free
```

## bluemix resource quotas
{: #bluemix_resource_quotas}

Répertorier toutes les définitions de quota.

```
bluemix resource quotas
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les définitions de quota :

```
bluemix resource quotas
```

## bluemix resource quota
{: #bluemix_resource_quota}

Afficher les détails d'une définition de quota

```
bluemix resource quota NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du quota</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails du quota `free` :

```
bluemix resource quota free
```


## bluemix app push
{: #bluemix_app_push}

Cette commande possède la même fonction et les mêmes options que la commande `cf push`.


## bluemix app list
{: #bluemix_app_list}

Cette commande possède la même fonction et les mêmes options que la commande `cf apps`.


## bluemix app show
{: #bluemix_app_show}

Cette commande possède la même fonction et les mêmes options que la commande `cf app`.


## bluemix app delete
{: #bluemix_app_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete`.


## bluemix app rename
{: #bluemix_app_rename}

Cette commande possède la même fonction et les mêmes options que la commande `cf rename`.


## bluemix app start
{: #bluemix_app_start}

Cette commande possède la même fonction et les mêmes options que la commande `cf start`.


## bluemix app stop
{: #bluemix_app_stop}

Cette commande possède la même fonction et les mêmes options que la commande `cf stop`.


## bluemix app restart
{: #bluemix_app_restart}

Cette commande possède la même fonction et les mêmes options que la commande `cf restart`.


## bluemix app restage
{: #bluemix_app_restage}


Cette commande possède la même fonction et les mêmes options que la commande `cf restage`.


## bluemix app instance-restart
{: #bluemix_app_instance_restart}


Cette commande possède la même fonction et les mêmes options que la commande `cf restart-app-instance`.


## bluemix app events
{: #bluemix_app_events}

Cette commande possède la même fonction et les mêmes options que la commande `cf events`.


## bluemix app files
{: #bluemix_app_files}

Cette commande possède la même fonction et les mêmes options que la commande `cf files`.


## bluemix app logs
{: #bluemix_app_logs}

Cette commande possède la même fonction et les mêmes options que la commande `cf logs`.


## bluemix app env
{: #bluemix_app_env}

Cette commande possède la même fonction et les mêmes options que la commande `cf env`.


## bluemix app env-set
{: #bluemix_app_env_set}

Cette commande possède la même fonction et les mêmes options que la commande `cf set-env`.


## bluemix app env-unset
{: #bluemix_app_env_unset}

Cette commande possède la même fonction et les mêmes options que la commande `cf unset-env`.


## bluemix app stacks
{: #bluemix_app_stacks}

Cette commande possède la même fonction et les mêmes options que la commande `cf stacks`.


## bluemix app stack-show
{: #bluemix_app_stack_show}

Cette commande possède la même fonction et les mêmes options que la commande `cf stack`.


## bluemix app manifest-create
{: #bluemix_app_manifest_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-app-manifest`.

## bluemix app domain-cert
{: #bluemix_app_domain_cert}

Afficher les informations de certificat d'un domaine.

```
bluemix app domain-cert DOMAIN_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>DOMAIN_NAME (obligatoire)</dt>
<dd>Domaine hébergeant le certificat.</dd>
</dl>


<strong>Exemples</strong> :

Affichage des informations de certificat du domaine `ibmcxo-eventconnect.com`:

```
bluemix app domain-cert ibmcxo-eventconnect.com
```

## bluemix app domain-cert-add
{: #bluemix_app_domain_cert_add}

Ajouter un certificat au domaine indiqué dans l'organisation en cours.

```
bluemix app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine auquel ajouter le certificat.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de clé privée.</dd>
   <dt>-c <i>CERT_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de certificat.</dd>
   <dt>-p <i>PASSWORD</i> (facultatif)</dt>
   <dd>Mot de passe du certificat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (facultatif)</dt>
   <dd>Chemin du fichier de certificat intermédiaire.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (facultatif)</dt>
   <dd>Fichier de clés certifiées.</dd>
   </dl>


<strong>Exemples</strong> :

Ajouter un certificat au domaine `ibmcxo-eventconnect.com` :

```
bluemix app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## bluemix app domain-cert-remove
{: #bluemix_app_domain_cert_remove}

Supprimer un certificat du domaine spécifié dans l'organisation en cours.

```
bluemix app domain-cert-remove DOMAIN [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine duquel supprimer le certificat.</dd>
   <dt>-f (facultatif)</dt>
   <dd>Force une suppression sans demander de confirmation.</dd>
   </dl>

## bluemix app routes
{: #bluemix_app_routes}

Cette commande possède la même fonction et les mêmes options que la commande `cf routes`.


## bluemix app route-check
{: #bluemix_app_route_check}

Cette commande possède la même fonction et les mêmes options que la commande `cf check-route`.


## bluemix app route-map
{: #bluemix_app_route_map}

Mappez une route à une application cf ou un groupe de conteneurs existant associé au domaine et au nom d'hôte spécifiés.

```
bluemix app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf ou du groupe de conteneur à mapper à une route.</dd>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine de la route. Par exemple, mychinabluemix.net ou chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (facultatif)</dt>
   <dd>Nom d'hôte de la route. S'il n'est pas spécifié, le nom d'hôte est le nom de l'application ou le nom du groupe de conteneurs par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Mappez une route à `mon-app` avec le domaine spécifié :

```
bluemix app route-map my-app mychinabluemix.net
```

Mappez une route à 'mon-groupe-conteneurs' avec le domaine et le nom d'hôte spécifiés :

```
bluemix app route-map my-container-group chinabluemix.net -n abc
```


## bluemix app route-unmap
{: #bluemix_app_route_unmap}

Supprimer le mappage de la route spécifiée à une application cf ou un groupe de conteneurs existant.

```
bluemix app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf ou du groupe de conteneurs.</dd>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine de la route (par exemple, mychinabluemix.net ou chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (facultatif)</dt>
   <dd>Nom d'hôte de la route. S'il n'est pas spécifié, le nom d'hôte est le nom de l'application ou le nom du groupe de conteneurs par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Supprimer le mappage de la route `mon-app.mychinabluemix.net` de `mon-app` :

```
bluemix app route-unmap my-app mychianbluemix.net
```

Supprimer le mappage de la route `abc.chinabluexmix.net` de `mon-groupe-conteneurs` :

```
bluemix app route-unmap my-container-group chinabluemix.net -n abc
```


## bluemix app route-create
{: #bluemix_app_route_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-route`.


## bluemix app route-delete
{: #bluemix_app_route_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-route`.


## bluemix app orphaned-routes-delete
{: #bluemix_app_orphaned_routes_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-orphaned-routes`.


## bluemix app domains
{: #bluemix_app_domains}

Cette commande possède la même fonction et les mêmes options que la commande `cf domains`.


## bluemix app domain-create
{: #bluemix_app_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-domain`.


## bluemix app domain-delete
{: #bluemix_app_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-domain`.


## bluemix app shared-domain-create
{: #bluemix_app_shared_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-shared-domain`.


## bluemix app shared-domain-delete
{: #bluemix_app_shared_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-shared-domain`.


## bluemix service offerings
{: #bluemix_service_offerings}


Cette commande possède la même fonction et les mêmes options que la commande `cf marketplace`.


## bluemix service list
{: #bluemix_service_list}

Cette commande possède la même fonction et les mêmes options que la commande `cf services`.


## bluemix service show
{: #bluemix_service_show}

Cette commande possède la même fonction et les mêmes options que la commande `cf service`.


## bluemix service create
{: #bluemix_service_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-service`.


## bluemix service update
{: #bluemix_service_update}

Cette commande possède la même fonction et les mêmes options que la commande `cf update-service`.


## bluemix service delete
{: #bluemix_service_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-service`.


## bluemix service rename
{: #bluemix_service_rename}

Cette commande possède la même fonction et les mêmes options que la commande `cf rename-service`.


## bluemix service bind
{: #bluemix_service_bind}

Cette commande possède la même fonction et les mêmes options que la commande `cf bind-service`.


## bluemix service unbind
{: #bluemix_service_unbind}

Cette commande possède la même fonction et les mêmes options que la commande `cf unbind-service`.


## bluemix service key-create
{: #bluemix_service_key_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-service-key`.


## bluemix service key-delete
{: #bluemix_service_key_delete}

Cette commande possède la même fonction et les mêmes options que la commande `cf delete-service-key`.


## bluemix service keys
{: #bluemix_service_keys}

Cette commande possède la même fonction et les mêmes options que la commande `cf service-keys`.


## bluemix service key-show
{: #bluemix_service_key_show}

Cette commande possède la même fonction et les mêmes options que la commande `cf service-key`.


## bluemix service user-provided-create
{: #bluemix_service_user_provided_create}

Cette commande possède la même fonction et les mêmes options que la commande `cf create-user-provided-service`.


## bluemix service user-provided-update
{: #bluemix_service_user_provided_update}

Cette commande possède la même fonction et les mêmes options que la commande `cf update-user-provided-service`.


## bluemix resource service-instances
{: #bluemix_resource_service_instances}

Répertorier les instances de service

```
bluemix resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--service-name</dt>
  <dd>Nom du service membre</dd>
  <dt>--location</dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--long</dt>
  <dd>Afficher des zones supplémentaires dans la sortie</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les instances de service du service `test-service` :

```
bluemix resource service-instances --service-name test-service
```

## bluemix resource service-instance
{: #bluemix_resource_service_instance}

Afficher les détails d'une instance de service

```
bluemix resource service-instance NAME [--location LOCATION] [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--location</dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID de l'instance de service</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de l'instance de service `my-service-instance` :

```
bluemix resource service-instance my-service-instance
```

## bluemix resource service-instance-create
{: #bluemix_resource_service_instance_create}

Créer une instance de service

```
bluemix resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>SERVICE_NAME ou SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou ID du service</dd>
  <dt>SERVICE_PLAN_NAME ou SERVICE_PLAN_ID (obligatoire)</dt>
  <dd>Nom ou ID du plan de service</dd>
  <dt>LOCATION</dt>
  <dd>Environnement ou emplacement cible pour créer l'instance de service</dd>
  <dt>-t, --tags</dt>
  <dd>Etiquettes</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaînes de paramètres JSON pour la création de l'instance de service</dd>
</dl>

<strong>Exemples</strong>:
Créer une instance de service `my-service-instance` en utilisant le plan de service `test-service-plan` du service `test-service` sur l'emplacement `eu-gb` :

```
bluemix resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## bluemix resource service-instance-update
{: #bluemix_resource_service_instance_update}

Mettre à jour une instance de service

```
bluemix resource service-instance-update SERVICE_INSTANCE_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_INSTANCE_NAME (obligatoire)</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de l'instance de service</dd>
  <dt>-t, --tags</dt>
  <dd>Nouvelles étiquettes</dd>
  <dt>--service-plan-id</dt>
  <dd>Nouvel ID du plan de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Mettre à jour l'instance de service `my-service-instance` et remplacer son nom par `new-service-instance` :

```
bluemix resource service-instance-update my-service-instance -n new-service-instance
```

## bluemix resource service-instance-delete
{: #bluemix_resource_service_instance_delete}

Supprimer une instance de service

```
bluemix resource service-instance-delete NAME [-f, --force] [--recursive]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
  <dt>--recursive</dt>
  <dd>Supprimer toutes les ressources membres</dd>
</dl>

<strong>Exemples</strong> :
Supprimer l'instance de service `my-service-instance` :

```
bluemix resource service-instance-delete my-service-instance
```

## bluemix resource service-bindings
{: #bluemix_resource_service_bindings}

Afficher les liaisons vers l'alias de service

```
bluemix resource bindings SERVICE_ALIAS
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
</dl>

<strong>Exemples</strong> :
Afficher les liaisons de ressources à l'alias de service `my-service-alias`:

```
bluemix resource bindings my-service-alias
```
## bluemix resource service-binding
{: #bluemix_resource_service_binding}

Afficher les détails d'une liaison de service

```
bluemix resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Seul l'ID s'affiche. Toute autre sortie pour la liaison de service est supprimée.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de liaison de service entre l'alias de service `my-service-alias` et l'application `my-app` :

```
bluemix resource bindings my-service-alias my-app
```

## bluemix resource service-binding-create
{: #bluemix_resource_service_binding_create}

Créer une liaison de service

```
bluemix resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id-name SERVICE_ID_NAME] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--service-id-name</dt>
  <dd>Nom de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameter</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une liaison de service entre l'alias de ressource `my-service-alias` et l'application `my-app` avec le rôle `Administrateur` :

```
bluemix resource service-binding-create my-service-alias my-app Administrator
```
## bluemix resource service-binding-delete
{: #bluemix_resource_service_binding_delete}

Supprimer une liaison de service

```
bluemix resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer une liaison de service entre l'alias de service `my-service-alias` et l'application `my-app` :

```
bluemix resource service-binding-delete my-service-alias my-app
```

## bluemix resource service-keys
{: #bluemix_resource_service_keys}

Répertorier les clés de service de l'instance de service ou de l'alias de service

```
bluemix resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--alias-id</dt>
  <dd>ID de l'alias de service</dd>
  <dt>--alias-name</dt>
  <dd>Nom de l'alias de service</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les clés de service de l'instance de service `my-service-instance` :

```
bluemix resource service-keys --instance-name my-service-instance
```

## bluemix resource service-key
{: #bluemix_resource_service_key}

Afficher les détails d'une clé de service

```
bluemix resource service-key KEY_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID de la clé de service</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de la clé de service `my-service-key` :

```
bluemix resource service-key my-service-key
```

## bluemix resource service-key-create
{: #bluemix_resource_service_key_create}

Créer une clé de service

```
bluemix resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id-name SERVICE_ID_NAME [-f, --force]]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--alias-id</dt>
  <dd>ID de l'alias de service</dd>
  <dt>--alias-name</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>-service-id-name</dt>
  <dd>Nom de l'ID de service auquel le rôle appartient</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une clé de service nommée `my-service-key` avec le rôle `Administrateur` pour l'instance de service `my-service-instance` :

```
bluemix resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## bluemix resource service-key-delete
{: #bluemix_resource_service_key_delete}

Supprimer une clé de service

```
bluemix resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer la clé de service `my-service-key` :

```
bluemix resource service-key-delete my-service-key
```

## bluemix resource service-aliases
{: #bluemix_resource_service_aliases}

Répertorier les alias d'une instance de service

```
bluemix resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service membre.</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service membre.</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les alias de l'instance de service `my-service-instance` :
```
bluemix resource service-aliases my-service-instance
```

## bluemix resource service-alias
{: #bluemix_resource_service_alias}

Afficher les détails d'un alias de service

```
bluemix resource service-alias ALIAS_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--id</dt>
  <dd>Seul l'ID de l'alias du service donné s'affiche. Toute autre sortie de l'alias est supprimée.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de l'alias de service `my-service-alias` :
```
bluemix resource service-aliase  my-service-alias
```

## bluemix resource service-alias-create
{: #bluemix_resource_service_alias_create}

Créer un alias d'une instance de service

```
bluemix resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service membre.</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service membre.</dd>
  <dt>-s</dt>
  <dd>Nom de l'espace dans lequel l'alias est créé. Il s'agit de l'espace en cours par défaut.</dd>
  <dt>-t, --tags</dt>
  <dd>Liste d'étiquettes.</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres.</dd>
</dl>

<strong>Exemples</strong> :
Créer un alias de service nommé `my-service-alias` pour l'instance de service `my-service-instance` :
```
bluemix resource service-aliase-create my-service-alias --instance-name my-service-instance
```

## bluemix resource service-alias-update
{: #bluemix_resource_service_alias_update}

Mettre à jour un alias de service

```
bluemix resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de l'alias de service.</dd>
  <dt>-t, --tags</dt>
  <dd>Liste d'étiquettes.</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation de l'utilisateur</dd>
</dl>

<strong>Exemples</strong> :
Mettre à jour l'alias de service `my-service-alias`  et remplacer son nom par `new-service-alias` :

```
bluemix resource service-alias-update my-service-alias -n new-service-alias
```

## bluemix resource service-alias-delete
{: #bluemix_resource_service_alias_delete}

Supprimer un alias de service

```
bluemix resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer l'alias de service `my-service-alias` :

```
bluemix resource service-alias-delete my-service-alias
```

## bluemix catalog search
{: #bluemix_catalog_search}

Effectuer des recherches dans des entrées de catalogue

```
bluemix catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-r, --region</dt>
  <dd>Spécifier la région géographique dans laquelle effectuer la recherche. Actuellement, seules les régions "us-south" et "united-kingdom" sont prises en charge.</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrer par type de ressource. Actuellement, seules les options "service-cf", "iaas", "runtime", "template" et "dashboard" sont prises en charge.</dd>
  <dt>-p, --price</dt>
  <dd>Filtrer par prix. Actuellement, seuls les options "free", "paygo", "bluemix-subscription" sont prises en charge.</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrer par étiquette.</dd>
  <dt>--sort-by</dt>
  <dd>Propriétés de tri</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. En général, "groupe", "fournisseur" et "étiquettes"</dd>
  <dt>--reverse</dt>
  <dd>Inverser l'ordre de tri</dd>
  <dt>--json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Effectuer une recherche dans le service `Automation test` :

```
bluemix catalog search -k service -q 'Automation test'
```


## bluemix catalog entry
{: #bluemix_catalog_entry}

Obtenir une entrée de catalogue

```
bluemix catalog entry ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--children</dt>
  <dd>Obtenir tous les enfants de l'entrée de catalogue</dd>
  <dt>--json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Obtenir l'entrée portant l'ID `a0ef1-d3b4j0` :

```
bluemix catalog entry 'a0ef1-d3b4j0'
```


## bluemix catalog entry-create
{: #bluemix_catalog_entry_create}
Créer une nouvelle entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
bluemix catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-p, --parent</dt>
  <dd>ID parent de l'objet</dd>
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Créer une ressource à partir du fichier JSON portant l'ID parent `a0ef1-d3b4j0` :

```
bluemix catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## bluemix catalog entry-update
{: #bluemix_catalog_entry_update}
Mettre à jour une entrée de catalogue existante (administrateur ou éditeur de catalogue d'un compte uniquement)

```
bluemix catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la ressource `j402-dnf1i` à partir d'un fichier JSON :

```
bluemix update 'j402-dnf1i' -c @update.json
```

## bluemix catalog entry-delete
{: #bluemix_catalog_entry_delete}
Supprimer une entrée de catalogue (administrateur de catalogue d'un compte uniquement)
```
bluemix catalog entry-delete ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la ressource `j402-dnf1i`:

```
bluemix catalog delete 'j402-dnf1i'
```


## bluemix catalog entry-visibility
{: #bluemix_catalog_entry_visibility}
Obtenir la visibilité pour une entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
bluemix catalog entry-visibility ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>-global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Obtenir la visibilité de la ressource `j402-dnf1i` dans une portée globale :

```
bluemix catalog entry-visibility 'j402-dnf1i' --global
```


## bluemix catalog entry-visibility-set
{: #bluemix_catalog_entry_visibility_set}
Mettre à jour la visibilité d'une entrée de catalogue existante (administrateur de catalogue d'un compte uniquement)

```
bluemix catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>

  <dt>--includes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par une virgule) à la liste d'inclusions de manière à accorder à la visibilité à l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--includes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par une virgule) de la liste d'inclusions, de manière à révoquer la visibilité de l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>  
  <dt>--excludes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par une virgule) à la liste d'exclusions. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--excludes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par une virgule) de la liste d'exclusions, de manière à révoquer la visibilité de l'entrée. Si la liste a été définie par des administrateurs globaux, ces derniers ne peuvent pas supprimer le compte. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--owner</dt>
  <dd>Changement de propriétaire d'un objet. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--restrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Privé'</dd>
  <dt>--unrestrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Public'</dd>  
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Définir la visibilité de la ressource `j402-dnf1i` à partir d'un fichier JSON :

```
bluemix catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## bluemix catalog service-marketplace
{: #bluemix_catalog_service_marketplace}
Répertorier les offres de services de la place du marché

```
bluemix catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--cf</dt>
  <dd>Afficher les services Cloud Foundry uniquement</dd>
  <dt>--rc</dt>
  <dd>Afficher les services RC compatibles uniquement</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Afficher les offres de services dans une portée globale :

```
bluemix catalog service-marketplace --global
```

## bluemix catalog templates
{: #bluemix_catalog_templates}

Afficher les modèles de conteneur boilerplate dans Bluemix.

```
bluemix catalog templates [-d]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>-d (facultatif)</dt>
   <dd>Si l'option <i>-d</i> est spécifiée, la description de chaque modèle est également affichée. Sinon, seul l'ID et le nom des modèles sont affichés.</dd>
   </dl>


## bluemix catalog template
{: #bluemix_catalog_template}

Afficher les informations détaillées d'un modèle de conteneur boilerplate spécifié.

```
bluemix catalog template TEMPLATE_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>ID du modèle de conteneur boilerplate. Utilisez <i>bluemix templates</i> pour afficher tous les ID de modèles.</dd>
   </dl>


<strong>Exemples</strong> :

Afficher les détails du modèle `mobileBackendStarter` :

```
bluemix catalog template mobileBackendStarter
```


## bluemix catalog template-run
{: #bluemix_catalog_template_run}

Créez une application cf reposant sur le modèle spécifié avec l'adresse URL et la description indiquées. Par défaut, la nouvelle application est démarrée automatiquement.

```
bluemix catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>Modèle sur lequel sera basée l'application lors de sa création. Utilisez <i>bluemix templates</i> pour voir tous les ID des modèles.</dd>
   <dt>CF_APP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf à créer.</dd>
   <dt>-u <i>URL</i> (facultatif)</dt>
   <dd>Route de l'application. Si elle n'est pas spécifiée, la route est définie automatiquement par {{site.data.keyword.Bluemix_notm}} d'après le nom de votre application et le domaine par défaut.</dd>
   <dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
   <dd>Description de l'application.</dd>
   <dt>--no-start (facultatif)</dt>
   <dd>Indique de ne pas démarrer automatiquement l'application après sa création. Si cette option n'est pas spécifiée, l'application est démarrée automatiquement après sa création.</dd>
   </dl>


<strong>Exemples</strong> :

Créez l'application cf `mon-app` d'après le modèle `javaHelloWorld` :

```
bluemix catalog template-run javaHelloWorld mon-app
```

Créez une application `my-ruby-app` d'après le modèle `rubyHelloWorld` avec la route
`myrubyapp.chinabluemix.net` et la description `Ma première application Ruby dans {{site.data.keyword.Bluemix_notm}}.`:

```
bluemix catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "Ma première application Ruby dans {{site.data.keyword.Bluemix_notm}}."
```

Créez l'application `mon-app-python` d'après le modèle `pythonHelloWorld` sans démarrage automatique :

```
bluemix catalog template-run pythonHelloWorld mon-app-python --no-start
```

## bluemix catalog locations
{: #bluemix_catalog_locations}

Obtenir un sous-ensemble de choix de régions dans le format de votre choix. 

```
bluemix catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-i, --id</dt>
  <dd>Indiquer la géographie par ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtenir une liste d'entrées pour le type indiqué. </dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. Actuellement "groupe", "fournisseur" et "balises".</dd>
  <dt>--json</dt>
  <dd>Sortie de la réponse JSON d'origine.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale.</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
</dl>

## bluemix billing account-usage
{: #bluemix_billing_account_usage}

Afficher l'utilisation mensuelle et les coûts liés au compte en cours. 

```
bluemix billing account-usage [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

<strong>Exemples</strong> :

Afficher le rapport d'utilisation et des coûts du compte en cours pour 2016-06 :

```
bluemix billing account-usage -d 2016-06
```

## bluemix billing org-usage
{: #bluemix_billing_org_usage}

Afficher l'utilisation mensuelle d'une organisation. Cette opération ne peut être réalisée que par le propriétaire de compte ou le responsable de la facturation de l'organisation.

```
bluemix billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>ORG_NAME (obligatoire)</dt>
  <dd>Nom de l'organisation.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>



## bluemix billing resource-group-usage
{: #bluemix_billing_resource_group_usage}

Afficher l'utilisation mensuelle d'un groupe de ressources. Cette opération peut être effectuée par le propriétaire du compte ou le responsable de la facturation du groupe de ressources. 

```
bluemix billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>GROUP_NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

## bluemix billing resource-instances-usage
{: #bluemix_billing_resource_instances_usage}
 
 Afficher l'utilisation mensuelle des instances de ressource du compte en cours. 
 
 ```
 bluemix billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
 ```
 
 <strong>Prérequis</strong> : Noeud final, Connexion
 
 <strong>Options de commande</strong> :
 
 <dl>
   <dt>-o ORG_NAME (facultatif)</dt>
   <dd>Filtrer les instances par organisation.</dd>
   <dt>-g GROUP_NAME</dt>
   <dd>Filtrer l'instance par groupe de ressources.</dd>
   <dt>-d MONTH_DATE (facultatif)</dt>
   <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
   <dt>--json (facultatif)</dt>
   <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
 </dl>


## bluemix plugin repos
{: #bluemix_plugin_repos}

Répertorier tous les référentiels de plug-in enregistrés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin repos
```

<strong>Prérequis</strong> : Aucun


## bluemix plugin repo-add
{: #bluemix_plugin_repo_add}

Ajouter un nouveau référentiel de plug-in dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. 

```
bluemix plugin repo-add REPO_NAME REPO_URL
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à ajouter. Vous pouvez définir votre propre nom pour chaque référentiel.</dd>
   <dt>REPO_URL (obligatoire)</dt>
   <dd>URL du référentiel à ajouter. Elle doit contenir le protocole (par exemple http://plugins.ng.bluemix.net au lieu de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net est le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. </dd>
    </dl>


<strong>Exemples</strong> :

Ajouter le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} sous la forme `bluemix-repo` :

```
bluemix plugin repo-add référentiel-bluemix http://plugins.ng.bluemix.net
```


## bluemix plugin repo-remove
{: #bluemix_plugin_repo_remove}

Retirer un référentiel de plug-in de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
bluemix plugin repo-remove REPO_NAME
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à supprimer.</dd>
   </dl>

<strong>Exemples</strong> :

Supprimer `référentiel-bluemix` de l'interface de ligne de commande (CLI) {{site.data.keyword.Bluemix_notm}} :

```
bluemix plugin repo-remove référentiel-bluemix
```


## bluemix plugin repo-plugins
{: #bluemix_plugin_repo_plugins}

Répertorier tous les plug-in disponibles dans tous les référentiels ajoutés ou dans un référentiel spécifique.

```
bluemix plugin repo-plugins [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Répertorier uniquement les plug-in dans le référentiel spécifié.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier tous les plug-in dans tous les référentiels ajoutés :

```
bluemix plugin repo-plugins
```

Répertorier tous les plug-in du référentiel `bluemix-repo` :

```
bluemix plugin repo-plugins -r bluemix-repo
```

## bluemix plugin repo-plugin
{: #bluemix_plugin_repo_plugin}

Afficher les détails d'un plug-in dans le référentiel

```
bluemix plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier les détails du plug-in "container-service" dans le référentiel 'Bluemix' :

```
bluemix plugin repo-plugin container-service -r Bluemix
```

Répertorier les détails du plug-in "container-service" dans le référentiel par défaut 'Bluemix'

```
bluemix plugin repo-plugin container-service -r Bluemix
```


## bluemix plugin list
{: #bluemix_plugin_list}

Répertorier tous les plug-in installés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. 

```
bluemix plugin list
```

<strong>Prérequis</strong> : Aucun

## bluemix plugin show
{: #bluemix_plugin_show}

Afficher les détails d'un plug-in installé

```
bluemix plugin show PLUGIN-NAME
```

<strong>Prérequis</strong> : Aucun


## bluemix plugin install
{: #bluemix_plugin_install}

Installer la version de plug-in spécifique dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} à partir du chemin ou du référentiel spécifié.

```
bluemix plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
bluemix plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obligatoire)</dt>
   <dd>Si -r <i>REPO_NAME</i> n'est pas spécifié, le plug-in est installé depuis le chemin local spécifié ou depuis l'URL distante.</dd>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
</dd>
   <dt>-v <i>VERSION</i> (facultatif)</dt>
   <dd>Version du plug-in à installer. Si elle n'est pas fournie, la dernière version du plug-in est installée. Cette option n'est valide que si vous installez le plug-in à partir du référentiel.</dd>
   <dt>-f </dt>
   <dd>Forcer l'installation du plug-in sans confirmation.</dd>
    </dl>
    
    
Le nom de référentiel officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est 'Bluemix'.    

<strong>Exemples</strong> :

Installer un plug-in depuis le fichier local :

```
bluemix plugin install /downloads/new_plugin
```

Installer un plug-in depuis l'adresse URL distante :

```
bluemix plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Installer la dernière version du plug-in 'container-service' à partir du référentiel 'Bluemix' : 

```
bluemix plugin install container-service -r Bluemix
```
Installer la version '0.1.425' du plug-in 'container-service' à partir du référentiel de plug-in officiel : 

```
bluemix plugin install container-service -v 0.1.425
```

## bluemix plugin update
{: #bluemix_plugin_update}

Mettre à niveau le plug-in à partir d'un référentiel

```
bluemix plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nom du plug-in à mettre à jour. Si ce paramètre n'est pas spécifié, la commande recherche des mises à niveau pour tous les plug-ins installés.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
</dd>
 <dt>-v <i>VERSION</i> (facultatif)</dt>
 <dd>Version du plug-in vers laquelle effectuer la mise à jour. Si elle n'est pas indiquée, le plug-in est mis à jour vers la version disponible la plus récente. </dd>
 <dt>--all</dt>
 <dd>Mettre à jour tous les plug-in disponibles</dd>
</dl>

<strong>Exemples</strong> :

Rechercher toutes les mises à niveau disponibles dans le référentiel de plug-in officiel 'Bluemix' :

```
bluemix plugin update -r Bluemix
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la dernière version : 

```
bluemix plugin update container-service
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la version '0.1.440' :

```
bluemix plugin update container-service -v 0.1.440
```

## bluemix plugin uninstall
{: #bluemix_plugin_uninstall}

Désinstaller le plug-in spécifié de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. 

```
bluemix plugin uninstall PLUGIN_NAME
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_NAME (obligatoire)</dt>
   <dd>Nom du plug-in à désinstaller.</dd>
    </dl>

<strong>Exemples</strong> :

Désinstaller le plug-in 'container-service' précédemment installé :

```
bluemix plugin uninstall container-service
```
