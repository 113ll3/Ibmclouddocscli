---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-08"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Commandes {{site.data.keyword.Bluemix_notm}} (ibmcloud)
{: #bluemix_cli}

Version : 0.7.1

L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} fournit un ensemble de commandes qui sont regroupées par espace de nom pour que les utilisateurs puissent interagir avec {{site.data.keyword.Bluemix_notm}}.

A compter de la version 0.5.0, le client de ligne de commande {{site.data.keyword.Bluemix_notm}} inclut un client de ligne de commande Cloud Foundry dans son installation. Si vous avez installé votre propre interface CLI cf, n'utilisez pas à la fois les commandes CLI d'{{site.data.keyword.Bluemix_notm}},(`ibmcloud [commande]`, et les commandes CLI de Cloud Foundry, `cf [commande]`, de votre propre installation dans le même contexte. Utilisez à la place `ibmcloud cf [commande]` si vous désirez utiliser cf cli pour gérer les ressources Cloud Foundry dans le contexte CLI d'{{site.data.keyword.Bluemix_notm}}.  Notez que `ibmcloud cf api/login/logout/target` n'est pas admis et que vous devez utiliser `ibmcloud api/login/logout/target` à la place.

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.Bluemix_notm}} ont été changées de `bluemix` et `bx` en `ibmcloud`. Vous pouvez toutefois continuer à utiliser les commandes de l'interface CLI `bluemix` et `bx` jusqu'à ce qu'elles soient retirées.
{: tip}

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


Utilisez les index des tableaux suivants pour examiner les commandes ibmcloud fréquemment utilisées.

## Commandes générales ibmcloud
{: #bx_commands_index}

<table summary="Commandes générales ibmcloud.">
<caption>Tableau 1. Commandes générales ibmcloud</caption>
 <thead>
 <th colspan="5">Commandes générales ibmcloud</th>
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

 ## Commandes de gestion et de configuration des services d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
  {: #bx_commands_softlayer}

Les commandes de gestion d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} ont été fusionnées dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations sur l'utilisation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} dans le but de configurer et gérer des services d'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, voir : [{{site.data.keyword.Bluemix_notm}} Commandes d'infrastructure {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html#softlayer_cli).

 ## Commandes de gestion des comptes, des organisations et des rôles
 {: #bx_commands_account}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les comptes, les organisations , les espaces et les rôles.">
<caption>Tableau 2. Commandes de gestion des comptes, des organisations, des espaces et des rôles</caption>
 <thead>
 <th colspan="5">Commandes de gestion des comptes, des organisations, des espaces et des rôles</th>
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


 ## Commandes de gestion des groupes de ressources et des ressources
{: #bx_commands_resource}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les groupes de ressources et les ressources.">
  <caption>Tableau 3. Commandes de gestion des groupes de ressources et des ressources</caption>
  <thead>
    <th colspan="5">Commandes de gestion des groupes de ressources et des ressources</th>
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


 ## Commandes de gestion des clés d'API et des règles
 {: #bx_commands_iam}
 <table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les clés d'API et les règles.">
 <caption>Tableau 4. Commandes de gestion des clés d'API et des règles</caption>
  <thead>
  <th colspan="5">Commandes de gestion des clés d'API et des règles</th>
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

 ## Commandes de gestion des applications CF et des domaines, routes et certificats liés aux applications
 {: #bx_commands_apps}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les applications cf et les domaines, les routes et les certificats liés aux applications.">
<caption>Tableau 5. Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</caption>
 <thead>
 <th colspan="5">Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</th>
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

 ## Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les services {{site.data.keyword.Bluemix_notm}}.">
<caption>Tableau 6. Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de gestion des services {{site.data.keyword.Bluemix_notm}}</th>
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


 ## Commandes de gestion des paramètres de catalogue, de plug-in et de facturation
 {: #bx_commands_settings}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer le catalogue, les plug-ins, la facturation et les paramètres de sécurité {{site.data.keyword.Bluemix_notm}}.">
<caption>Tableau 7. Commandes de gestion des paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de gestion des paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}</th>
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

 ## Gestion des services Cloud Foundry Enterprise Environment (expérimental)
{: #bx_commands_cfee}

<table summary="Gestion des services Cloud Foundry Enterprise Environment (expérimental)">
<caption>Tableau 8. Gestion des services Cloud Foundry Enterprise Environment (expérimental)</caption>
 <thead>
 <th colspan="5">Gestion des services Cloud Foundry Enterprise Environment (expérimental)</th>
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
Afficher l'aide générale pour les commandes intégrées de premier niveau et les espaces de nom pris en charge de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, ou l'aide d'une commande intégrée ou d'un espace de nom spécifique.

```
ibmcloud help [COMMAND|NAMESPACE]
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
ibmcloud help
```

Afficher l'aide pour la commande `info` :

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
Définir ou afficher le noeud final d'API {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>API_ENDPOINT (facultatif)</dt>
   <dd>Noeud final d'API ciblé. Par exemple, `https://api.chinabluemix.net`. Si l'option *API_ENDPOINT* et l'option `--unset` sont toutes les deux spécifiées, le noeud final d'API en cours est affiché.</dd>
   <dt>--unset (facultatif)</dt>
   <dd>Supprimer le paramètre de noeud final d'API.</dd>
   <dt>--skip-ssl-validation (facultatif)</dt>
   <dd>Ignorer la validation SSL des demandes HTTP.</dd>
   </dl>
<strong>Exemples</strong> :

Définir le noeud final d'API api.chinabluemix.net :

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

Afficher le noeud final d'API en cours :

```
ibmcloud api
```

Annuler la définition du noeud final d'API :

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


Ecrire les valeurs par défaut dans le fichier de configuration.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
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
ibmcloud config --http-timeout 30
```

Activer la sortie de trace pour les demandes HTTP :

```
ibmcloud config --trace true
```

Consigner la trace des demandes HTTP dans le fichier spécifié */home/usera/my_trace* :

```
ibmcloud config --trace /home/usera/my_trace
```

Désactiver la sortie couleur :

```
ibmcloud config --color false
```

Définir l'environnement local zh_Hans :

```
ibmcloud config --locale zh_Hans
```

Effacer les paramètres d'environnement local :

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

Afficher les informations {{site.data.keyword.Bluemix_notm}} de base, notamment la région en cours, la version du contrôleur de cloud et certains noeuds finaux utiles tels que les noeuds finaux pour la connexion et l'échange de jeton d'accès.

```
ibmcloud info
```

<strong>Prérequis</strong> : Noeud final


## ibmcloud cf
{: #ibmcloud_cf}

Appeler l'interface CLI CF imbriquée

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-q, --quiet</dt>
  <dd>Désactiver le message "Appel de commande cf..."</dd>
</dl>

<strong>Exemples</strong> :

Liste d'applications CF :

```
ibmcloud cf apps
```

Répertorier les services CF sans le message "Appel de commande cf...":

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

Connecter l'utilisateur.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
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
  <dt> -g <i>RESOURCE_GROUP</i> (facultatif) </dt>
  <dd> Nom du groupe de ressources cible</dd>
  <dt> -o <i>ORG</i> (facultatif)</dt>
  <dd> Nom de l'organisation cible (obsolète, utilisez 'ibmcloud target -o ORGANISATION')</dd>
  <dt> -s <i>SPACE</i> (facultatif) </dt>
  <dd> Nom de l'espace cible (obsolète, utilisez 'ibmcloud target -s ESPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Imposer une authentification avec un serveur de connexion plutôt qu'avec un système IAM public</dd>
  <dt> --skip-ssl-validation (facultatif) </dt>
  <dd> Ignorer la validation SSL des demandes HTTP. Cette option n'est pas recommandée.</dd>
</dl>

<strong>Exemples</strong> :

#### Connexion en mode interactif

```
ibmcloud login
```

Connectez-vous avec un nom d'utilisateur et un mot de passe, puis définissez un compte, une organisation et un espace cible :

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Connectez-vous avec un code d'accès unique et définissez un compte, une organisation et un espace cible

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Connectez-vous avec une clé d'API et définissez des cibles :

#### Un compte est associé à une clé d'API

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### Aucun compte n'est associé à une clé d'API

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Remarque :</strong> si un compte est associé à la clé d'API, le passage à un autre compte n'est pas autorisé.

#### Utilisez un code d'accès unique

```
ibmcloud login -u UserID --sso
```

L'interface de ligne de commande fournira ensuite un lien d'URL et demandera un code d'accès :
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Ouvrez le lien dans un navigateur et laissez-vous guider pour obtenir le code secret. Entrez le code d'accès qui vous a été fourni dans la console. Vous devriez pouvoir vous connecter.

## ibmcloud logout
{: #ibmcloud_logout}

Déconnectez l'utilisateur.

```
ibmcloud logout
```

<strong>Prérequis</strong> : Aucun

## ibmcloud regions
{: #ibmcloud_regions}

Afficher les informations pour toutes les régions dans {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Prérequis</strong> : Noeud final


## ibmcloud target
{: #ibmcloud_target}


Définir ou afficher le compte, la région, l'organisation ou l'espace cible :

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r <i>REGION_NAME</i> (facultatif)</dt>
   <dd>Nom de la région vers laquelle commuter, par exemple 'us-south' ou 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (facultatif)</dt>
   <dd>ID du compte à cibler.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (facultatif)</dt>
   <dd>Nom du groupe de ressources</dd>
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
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Basculer vers une nouvelle région :

```
ibmcloud target -r eu-gb
```

Afficher le compte, la région, l'organisation et l'espace en cours :

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

Mettre à jour l'interface de ligne de commande vers la version la plus récente.

```
ibmcloud update [-f]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation. Privilège de superutilisateur (root) requis.</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Répertorier toutes les organisations

```
ibmcloud account orgs [-r REGION] [--guid]
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
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

Affiche des informations sur l'organisation spécifiée.

```
ibmcloud account org ORG_NAME [--guid]
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
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crée une nouvelle organisation. Cette opération ne peut être effectuée que par un propriétaire de compte.

```
ibmcloud account org-create ORG_NAME [-f]
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
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Répliquez une organisation de la région en cours dans une autre région.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
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
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Attribue un nouveau nom à une organisation. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>OLD_ORG_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'organisation qui sera renommée.</dd>
   <dt>NEW_ORG_NAME (obligatoire)</dt>
   <dd>Nouveau nom à affecter à l'organisation.</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Répertorier tous les espaces

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-o</dt>
   <dd>Nom de l'organisation. Liste des espaces sous l'organisation spécifiée. Valeur par défaut sur l'organisation actuelle si rien n'est indiqué.</dd>
   <dt>-r</dt>
   <dd>Nom de région. Liste des espaces sous la région spécifiée. Valeur par défaut sur la région actuelle si rien n'est indiqué.</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

Cette commande possède la même fonction et les mêmes options que la commande [cf space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Cette commande possède la même fonction et les mêmes options que la commande [cf rename-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Cette commande possède la même fonction et les mêmes options que la commande [cf delete-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Affiche les utilisateurs dans l'organisation spécifiée, par rôle.

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>ORG_NAME (obligatoire)</dt>
<dd>Nom de l'organisation.</dd>
<dt>-a (facultatif)</dt>
<dd>Recense tous les utilisateurs de l'organisation spécifiés, sans les regrouper par rôle.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Ajouter un utilisateur à une organisation (un responsable d'organisation est requis).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Retirer un utilisateur d'une organisation (responsable d'organisation ou utilisateur/utilisatrice proprement dit(e))

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Options de commande</strong> :
<dl>
<dt>--force, -f</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Extraire tous les rôles d'organisation de l'utilisateur en cours

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>-u</dt>
   <dd>ID utilisateur. S'il n'est pas spécifié, la valeur par défaut est l'utilisateur en cours.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Affecte un rôle de l'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
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
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Remarque **: vous pouvez définir des rôles d'organisation ou d'espace via l'interface CLI, mais pour les autres autorisations, il vous utiliser l'interface utilisateur. Pour plus d'informations, voir [Octroi d'un accès utilisateur](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Supprime l'affectation d'un rôle d'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
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
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Affichage des utilisateurs, par rôle, dans l'espace spécifié.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace.</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Affecte un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Suppression de l'affectation d'un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Afficher la liste de tous les comptes de l'utilisateur en cours

```
ibmcloud account list
```

<strong>Prérequis</strong> : Noeud final, Connexion


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Afficher le compte de l'organisation spécifiée (utilisateur d'organisation requis).

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--guid (facultatif)</dt>
  <dd>Affiche uniquement l'ID de compte</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

Affiche les utilisateurs associés au compte. Cette opération ne peut être effectuée que par le propriétaire de compte.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Retirer un utilisateur d'un compte (propriétaire de compte uniquement)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>USER_ID (obligatoire)</dt>
<dd>ID utilisateur</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID compte. Si ce paramètre n'est pas spécifié, le compte en cours est pris par défaut.</dd>
<dt>-f, --force</dt>
<dd>Forcer le retrait sans confirmation.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Inviter un utilisateur à rejoindre le compte

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur invité.</dd>
   <dt>-o ORG</dt>
   <dd>Organisation dans laquelle inviter l'utilisateur</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Rôle organisationnel. Les entrées valides sont les suivantes : OrgManager, BillingManager, OrgAuditor et OrgUser. Si aucun élément n'est indiqué, le rôle OrgUser est défini.</dd>
   <dt>-s SPACE</dt>
   <dd>Espace dans lequel inviter l'utilisateur</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Rôle d'espace. Les valeurs valides sont les suivantes : SpaceManager, SpaceDeveloper et SpaceAuditor.</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Renvoyer l'invitation à un utilisateur (administrateur de compte).

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur invité.</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Afficher les groupes d'accès du compte en cours.

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-u</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'utilisateur appartient. Cette option est propre à '-s'.</dd>
  <dt>-s</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'ID de service appartient. Cette option est propre à '-u'.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes d'accès :

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Afficher les détails d'un groupe d'accès

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-id</dt>
  <dd>Afficher l'ID uniquement</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails du groupe d'accès `example_group` :

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Créer un groupe d'accès

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-d, --description</dt>
  <dd>Description de groupe d'accès</dd>
</dl>

<strong>Exemples</strong> :

Créer un groupe d'accès `example_group` :

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Mettre à jour un groupe d'accès

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-n, --name</dt>
  <dd>Nom du nouveau groupe d'accès</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe d'accès `example_group` en `hello_world_group` :

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Supprimer un groupe d'accès

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
  <dt>-r, --recursive</dt>
  <dd>Supprimer un groupe d'accès et ses membres</dd>
</dl>

<strong>Exemples</strong> :

Supprimer le groupe d'accès `example_group` :

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Afficher la liste des utilisateurs d'un groupe d'accès

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste de tous les utilisateurs du groupe d'accès `example_group` :

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Ajouter un ou plusieurs utilisateurs à un groupe d'accès

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Ajouter l'utilisateur `name@example.com` au groupe d'accès `example_group` :

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Retirer un utilisateur d'un groupe d'accès

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Retirer l'utilisateur `name@example.com` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Retirer l'utilisateur de tous les groupes d'accès

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Retirer l'utilisateur `name@example.com` de tous les groupes d'accès :

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Afficher la liste des ID de service d'un groupe d'accès

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste des ID de service du groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Ajouter un ID de service à un groupe d'accès

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Ajouter l'ID de service `example-service` au groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Retirer un ID de service d'un groupe d'accès

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Retirer l'ID de service `example-service` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Retirer un ID de service de tous les groupes d'accès

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Retirer l'ID de service `example-service` de tous les groupes d'accès :

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Afficher la liste des règles d'un groupe d'accès

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste de toutes les règles du groupe d'accès `example_group` :

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Afficher les détails d'une règle de groupe d'accès

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la règle `51b9717e-76b0-4f6a-bda7-b8132431f926` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Créer une règle de groupe d'accès

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>-roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Créer une règle de groupe d'accès à partir d'un fichier JSON :

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Accorder le rôle `Administrateur` à `example_group` pour toutes les ressources `sample-service` :
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Accorder le rôle `Editeur` à `example_group` pour la ressource `key123` de l'instance `sample-service` ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Accorder le rôle `Opérateur` à `example_group` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Mettre à jour une règle de groupe d'accès

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>--roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle de groupe d'accès avec celle d'un fichier JSON de règles :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Administrator` à `example_group` pour toutes les ressources `sample-service` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Editor` à `example_group` pour la ressource `key123` de l'instance `sample-service` ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Operator` à `example_group` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Viewer` à `example_group` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Viewer` à `example_group` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Supprimer une règle de groupe d'accès

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la règle `51b9717e-76b0-4f6a-bda7-b8132431f926` du groupe d'accès `example_group` :
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Répertorier tous les ID de service

```
ibmcloud iam service-ids [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel des ID de service uniquement</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les identificateurs uniques universels de tous les ID de service sous le compte en cours

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Afficher les détails d'un ID de service

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de l'ID de service</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'ID de service `sample-test`

```
ibmcloud iam service-id sample-test
```
Afficher les détails de l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Créez un ID de service

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Description de l'ID de service</dd>
  <dt>--lock</dt>
  <dd>Verrouiller l'ID de service lors de la création</dd>
</dl>

<strong>Exemples</strong> :

Créez un ID de service avec le nom `sample-test` et la description `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Créer un ID de service verrouillé ayant le nom de service `sample-test` et la description `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Mettre à jour un ID de service

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description du service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez l'ID de service `sample-test` en `sample-test-2` sans demander de confirmation

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Mettre à jour la description du service `sample-test`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Renommer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` en `sample-test-3` avec une nouvelle description

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Supprimer un ID de service

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'ID de service `sample-teset` sans demander de confirmation

```
ibmcloud iam service-id-delete sample-teset -f
```

Supprimer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Verrouiller un ID de service

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller l'ID de service `sample-teset` sans confirmation

```
ibmcloud iam service-id-lock sample-teset -f
```

Verrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Déverrouiller un ID de service

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller l'ID de service `sample-teset` sans confirmation

```
ibmcloud iam service-id-unlock sample-teset -f
```

Déverrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Répertorier toutes les clés d'API de la plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Prérequis</strong> : Noeud final, Connexion

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Créez une nouvelle clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à créer.</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Description de la clé d'API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
<dt>--lock</dt>
<dd>Verrouiller la clé d'API lors de la création</dd>
</dl>

<strong>Exemples</strong> :

Créez une clé d'API et de la sauvegarder dans un fichier

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Créer une clé d'API verrouillée portant le nom "test-key"

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Mettre à jour une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Ancien nom de la clé d'API à mettre à jour, s'utilise exclusivement avec UUID </dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à mettre à jour, s'utilise exclusivement avec NAME</dd>
<dt>-n <i>NAME</i> (facultatif)</dt>
<dd>Nouveau nom de la clé d'API</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Nouvelle description de la clé d'API</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la description d'une clé d'API :

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Supprimer une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à supprimer, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

Verrouiller une clé d'API de plateforme

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à verrouiller, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le verrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

Verrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Déverrouiller une clé d'API de plateforme

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à déverrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à déverrouiller, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le déverrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

Déverrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Répertorier toutes les clés d'API d'un service

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les clés d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les clés d'API du service `sample-service` :

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Répertorier les détails d'une clé d'API de service

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de la clé d'API de service</dd>
  <dt>-f, --force</dt>
  <dd>Afficher la clé d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la clé d'API de service `sample-key` du service `sample-service` :

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Créez une clé d'API de service

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API de service nouvellement créée</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Description de la clé d'API</dd>
  <dt>--file</dt>
  <dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer la clé d'API de service `sample-key` pour le service `sample-service` sans confirmation :

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Mettre à jour une clé d'API de service

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de la clé d'API de service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description de la clé d'API de service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez la clé d'API de service `sample-key` en `new-sample-key` :

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Supprimer une clé d'API de service

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Verrouiller une clé d'API de service

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Déverrouiller une clé d'API de service

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Afficher les règles de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policies name@example.com
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
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Afficher les détails d'une règle utilisateur

```
ibmcloud iam user-policy USER_NAME POLICY_ID
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
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Créez une règle utilisateur

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>--file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Créez une règle utilisateur pour l'utilisateur `name@example.com` à partir du fichier JSON de règles `policy.json` :

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

Accorder le rôle `Administrateur` à `name@example.com` pour toutes les ressources `sample-service` :

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Accorder le rôle `Editeur` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Accorder le rôle `Opérateur` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Mettre à jour une règle utilisateur

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle à mettre à jour</dd>
<dt>--file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle utilisateur avec celle définie dans le fichier JSON

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Administrator` à `name@example.com` pour toutes les ressources `sample-service` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Mettre à jour une règle d'utilisateur afin d'accorder le rôle `Editor` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Operator` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Supprimer une règle utilisateur

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation la règle utilisateur</dd>
</dl>

<strong>Exemples</strong> :
Supprimer les règles `user-policy-id` de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Supprimer sans confirmation les règles `user-policy-id` de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Répertorier toutes les règles de service du service spécifié

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>-json</dt>
  <dd>Afficher la règle au format JSON</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les règles de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les règles du service `test` :

```
ibmcloud iam service-policies test
```
Répertorier les règles du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Afficher les détails d'une règle de service

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
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
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Afficher la règle `140798e2-8ea7db3` du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Créer une règle de service

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. S'utilise exclusivement avec les options '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' et '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource</dt>
  <dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Créer la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une règle de service à partir du fichier JSON pour le service `test` :

```
ibmcloud iam service-policy-create test --file @policy.json
```
Créer une règle de service à partir du fichier JSON pour le service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Mettre à jour une règle de service

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. S'utilise exclusivement avec les options -r, --roles, --service-name, --service-instance, --region, --resource-type, --resource, resource-group-name et resource-group-id.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `test` :

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Supprimer une règle de service

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la règle `140798e2-8ea7db3` du service `test`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Supprimer la règle `140798e2-8ea7db3` du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Extraire et afficher les jetons OAuth de la session en cours.

```
ibmcloud iam oauth-tokens
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Actualiser et afficher les jetons OAuth.

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Déconnecter l'IBMid public de l'ID non IBMid dédié.

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la déconnexion sans confirmation</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Créer une règle d'autorisation permettant à une instance de service d'accéder à une autre instance de service.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Service source dont l'accès peut être autorisé.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Service cible auquel le service source peut être autorisé à accéder.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Rôles permettant d'accéder au service source.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service source ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service source.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service cible ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service cible.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Supprimer une règle d'autorisation.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la règle d'autorisation à supprimer.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Afficher les détails d'une règle d'autorisation.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la règle d'autorisation à afficher.</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Répertorier les règles d'autorisation du compte en cours.

```
ibmcloud iam authorization-policies
```

<strong>Prérequis</strong> : Noeud final, Connexion


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Répertorier les groupes de ressources.

```
ibmcloud resource groups [--default]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--default</dt>
  <dd>Obtenir le groupe par défaut du compte en cours.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes de ressources du compte actuellement ciblé :

```
ibmcloud resource groups
```

Répertorier le groupe par défaut du compte actuellement ciblé :

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Afficher les détails d'un groupe de ressources

```
ibmcloud resource group NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID uniquement</dd>
</dl>

<strong>Exemples</strong> :

Afficher le groupe de ressources `example-group` :

```
ibmcloud resource group example-group
```

Afficher uniquement le groupe de ressources `example-group` :

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Créer un groupe de ressources

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

<strong>Exemples</strong> :

Créer un groupe de ressources `example-group` avec le quota `free` :

```
ibmcloud resource group-create example-group free
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Mettre à jour un groupe de ressources existant

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources cible</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du groupe de ressources</dd>
  <dt>-q, --quota</dt>
  <dd>Nom de la nouvelle définition de quota.</dd>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe de ressources `example-group` en `trial-group` :

```
ibmcloud resource group-update example-group -n trial-group
```

Modifier le quota du groupe de ressources `example-group` et le remplacer par `free` :

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Répertorier toutes les définitions de quota

```
ibmcloud resource quotas
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les définitions de quota :

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Afficher les détails d'une définition de quota

```
ibmcloud resource quota NAME
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
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrer une instance de service Cloudfoundry dans le groupe de ressources

```
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_INSTANCE_NAME ou SERVICE_INSTANCE_ID (obligatoire)</dt>
  <dd>Nom ou ID de l'instance de service</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--resource-group-id'. Si aucun de ces éléments n'est indiqué, le groupe de ressources actuellement ciblé est utilisé par défaut.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--resource-group-name'. Si aucun de ces éléments n'est indiqué, le groupe de ressources actuellement ciblé est utilisé par défaut.</dd>
  <dt>-f, --force</dt>
  <dd>Migrer sans confirmation</dd>
</dl>


## ibmcloud app push
{: #ibmcloud_app_push}

Cette commande possède la même fonction et les mêmes options que la commande [cf push ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## ibmcloud app list
{: #ibmcloud_app_list}

Cette commande possède la même fonction et les mêmes options que la commande [cf apps ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## ibmcloud app show
{: #ibmcloud_app_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf app ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## ibmcloud app delete
{: #ibmcloud_app_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## ibmcloud app rename
{: #ibmcloud_app_rename}

Cette commande possède la même fonction et les mêmes options que la commande [cf rename ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## ibmcloud app start
{: #ibmcloud_app_start}

Cette commande possède la même fonction et les mêmes options que la commande [cf start ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## ibmcloud app stop
{: #ibmcloud_app_stop}

Cette commande possède la même fonction et les mêmes options que la commande [cf stop ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## ibmcloud app restart
{: #ibmcloud_app_restart}

Cette commande possède la même fonction et les mêmes options que la commande [cf restart ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## ibmcloud app restage
{: #ibmcloud_app_restage}


Cette commande possède la même fonction et les mêmes options que la commande [cf restage ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Cette commande possède la même fonction et les mêmes options que la commande [cf restart-app-instance ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## ibmcloud app events
{: #ibmcloud_app_events}

Cette commande possède la même fonction et les mêmes options que la commande [cf events ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## ibmcloud app files
{: #ibmcloud_app_files}

Cette commande possède la même fonction et les mêmes options que la commande [cf files ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## ibmcloud app logs
{: #ibmcloud_app_logs}

Cette commande possède la même fonction et les mêmes options que la commande [cf logs ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## ibmcloud app env
{: #ibmcloud_app_env}

Cette commande possède la même fonction et les mêmes options que la commande [cf env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Cette commande possède la même fonction et les mêmes options que la commande [cf set-env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Cette commande possède la même fonction et les mêmes options que la commande [cf unset-env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Cette commande possède la même fonction et les mêmes options que la commande [cf stacks ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf stack ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-app-manifest ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Afficher les informations de certificat d'un domaine.

```
ibmcloud app domain-cert DOMAIN_NAME
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
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Ajouter un certificat au domaine indiqué dans l'organisation en cours.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Supprimer un certificat du domaine spécifié dans l'organisation en cours.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine duquel supprimer le certificat.</dd>
   <dt>-f (facultatif)</dt>
   <dd>Force une suppression sans demander de confirmation.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

Cette commande possède la même fonction et les mêmes options que la commande [cf routes ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Cette commande possède la même fonction et les mêmes options que la commande [cf check-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Mappez une route à une application cf ou un groupe de conteneurs existant associé au domaine et au nom d'hôte spécifiés.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
ibmcloud app route-map my-app mychinabluemix.net
```

Mappez une route à 'mon-groupe-conteneurs' avec le domaine et le nom d'hôte spécifiés :

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Supprimer le mappage de la route spécifiée à une application cf ou un groupe de conteneurs existant.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
ibmcloud app route-unmap my-app mychianbluemix.net
```

Supprimer le mappage de la route `abc.chinabluexmix.net` de `mon-groupe-conteneurs` :

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-orphaned-routes ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## ibmcloud app domains
{: #ibmcloud_app_domains}

Cette commande possède la même fonction et les mêmes options que la commande [cf domains ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-shared-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-shared-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


Cette commande possède la même fonction et les mêmes options que la commande [cf marketplace ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## ibmcloud service list
{: #ibmcloud_service_list}

Cette commande possède la même fonction et les mêmes options que la commande [cf services ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## ibmcloud service show
{: #ibmcloud_service_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## ibmcloud service create
{: #ibmcloud_service_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## ibmcloud service update
{: #ibmcloud_service_update}

Cette commande possède la même fonction et les mêmes options que la commande [cf update-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## ibmcloud service delete
{: #ibmcloud_service_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## ibmcloud service rename
{: #ibmcloud_service_rename}

Cette commande possède la même fonction et les mêmes options que la commande [cf rename-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## ibmcloud service bind
{: #ibmcloud_service_bind}

Cette commande possède la même fonction et les mêmes options que la commande [cf bind-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

Cette commande possède la même fonction et les mêmes options que la commande [cf unbind-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-service-key ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-service-key ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## ibmcloud service keys
{: #ibmcloud_service_keys}

Cette commande possède la même fonction et les mêmes options que la commande [cf service-keys ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf service-key ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-user-provided-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

Cette commande possède la même fonction et les mêmes options que la commande [cf update-user-provided-service ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Répertorier les instances de service

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
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
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Afficher les détails d'une instance de service

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire), s'utilise exclusivement avec ID</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>ID (obligatoire), s'utilise exclusivement avec NAME</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--location</dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID de l'instance de service</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'instance de service `my-service-instance` :

```
ibmcloud resource service-instance my-service-instance
``` 

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Créer une instance de service

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
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
  <dt>-d, --deployment</dt>
  <dd>Nom du déploiement</dd>
</dl>

<strong>Exemples</strong>:
Créer une instance de service `my-service-instance` en utilisant le plan de service `test-service-plan` du service `test-service` sur l'emplacement `eu-gb` :

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Mettre à jour une instance de service

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>Name (obligatoire)</dt>
  <dd>Nom de l'instance de service, s'utilise exclusivement avec ID</dd>
  <dt>ID (obligatoire)</dt>
  <dd>ID de l'instance de service, s'utilise exclusivement avec NAME</dd>
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
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Supprimer une instance de service

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>Name (obligatoire)</dt>
  <dd>Nom de l'instance de service, s'utilise exclusivement avec ID</dd>
  <dt>ID (obligatoire)</dt>
  <dd>ID de l'instance de service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
  <dt>--recursive</dt>
  <dd>Supprimer toutes les ressources membres</dd>
</dl>

<strong>Exemples</strong> :
Supprimer l'instance de service `my-service-instance` :

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Afficher les liaisons vers l'alias de service

```
ibmcloud resource service-bindings SERVICE_ALIAS
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
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Afficher les détails d'une liaison de service

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
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
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Créer une liaison de service

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
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
  <dt>--service-id</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameter</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une liaison de service entre l'alias de ressource `my-service-alias` et l'application `my-app` avec le rôle `Administrateur` :

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Supprimer une liaison de service

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
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
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Répertorier les clés de service de l'instance de service ou de l'alias de service

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Afficher les détails d'une clé de service

```
ibmcloud resource service-key KEY_NAME [--id]
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
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Créer une clé de service

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
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
  <dt>--service-id</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une clé de service nommée `my-service-key` avec le rôle `Administrateur` pour l'instance de service `my-service-instance` :

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Supprimer une clé de service

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
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
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Répertorier les alias d'une instance de service

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
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
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Afficher les détails d'un alias de service

```
ibmcloud resource service-alias ALIAS_NAME [--id]
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
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Créer un alias d'une instance de service

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
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
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Mettre à jour un alias de service

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
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
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Supprimer un alias de service

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
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
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Rechercher des ressources à l'aide de la syntaxe de requête Lucene

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-offset, --o</dt>
  <dd>Numéro de position de ressource de début</dd>
  <dt>-limit, --l</dt>
  <dd>Nombre de ressources à renvoyer (10000 au maximum)</dd>
</dl>

<strong>Exemples</strong> :
Rechercher les applications Cloud Foundry dont le nom commence par un texte indiqué :

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Rechercher les instances de service Cloud Foundry portant le nom de service indiqué :

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Rechercher les liaisons de service Cloud Foundry dans l'organisation portant l'ID indiqué :

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Rechercher les espaces Cloud Foundry portant le nom indiqué et situés dans l'une des deux régions spécifiées :

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Rechercher les ressources dont le nom contient le mot dev dans l'espace Cloud Foundry portant l'ID indiqué :

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Rechercher les ressources Resource Controller dans l'emplacement indiqué (par exemple, dans la région us-south :

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Rechercher les ressources ou les alias dans le groupe de ressources portant l'ID indiqué :

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Rechercher les groupes de ressources portant le nom default :

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Rechercher les liaisons de ressources pour le nom de service indiqué :

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Rechercher une ressource portant le nom de ressource de cloud indiqué :

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Rechercher une ressource avec la balise indiqué :

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Répertorier toutes les étiquettes

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-type</dt>
  <dd>Type d'étiquette (valeurs prises en charge : utilisateur, restreinte)</dd>
  <dt>-o, --offset</dt>
  <dd>Numéro de position de ressource de départ (valeur par défaut : 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Nombre de ressources à renvoyer (valeur maximale et valeur par défaut : 10 000)</dd>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les étiquettes

```
ibmcloud resource tags 
```

Répertorier toutes les étiquettes restreintes

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Afficher les détails d'une étiquette

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, s'utilise exclusivement avec --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, s'utilise exclusivement avec --tag-name</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'étiquette "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Créer une étiquette

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom de l'étiquette</dd>
  <dt>--tag-type</dt>
  <dd>Type d'étiquette (valeurs prises en charge : utilisateur, restreinte ; valeur par défaut : utilisateur)</dd>
</dl>

<strong>Exemples</strong> :

Créer une étiquette utilisateur ayant le nom think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Créer une étiquette restreinte ayant le nom department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Créer une étiquette utilisateur portant le nom "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Créer une étiquette restreinte portant le nom "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Supprimer une étiquette

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, s'utilise exclusivement avec --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, s'utilise exclusivement avec --tag-name</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'étiquette "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Ajouter une étiquette à une ressource

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, s'utilise exclusivement avec --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, s'utilise exclusivement avec --tag-name</dd>
  <dt>--resource-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de la ressource </dd>
</dl>

<strong>Exemples</strong> :

Ajouter l'étiquette "Ray Brown" à la ressource dont le nom de ressource de cloud est resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Retirer une étiquette d'une ressource

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, s'utilise exclusivement avec --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, s'utilise exclusivement avec --tag-name</dd>
  <dt>--resource-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de la ressource </dd>
</dl>

<strong>Exemples</strong> :

Retirer l'étiquette "Ray Brown" de la ressource dont le nom de ressource de cloud est resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Basculer l'étiquette utilisateur vers une étiquette restreinte et inversement 

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, s'utilise exclusivement avec --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, s'utilise exclusivement avec --tag-name</dd>
  <dt>--tag-type (obligatoire)</dt>
  <dd>Type d'étiquette</dd>
</dl>

<strong>Exemples</strong> :

Basculer l'étiquette "Ray Brown" vers une étiquette restreinte

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```


## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Effectuer des recherches dans des entrées de catalogue

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
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
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Obtenir une entrée de catalogue

```
ibmcloud catalog entry ID [--global]
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
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Créer une nouvelle entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
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
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Mettre à jour une entrée de catalogue existante (administrateur ou éditeur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
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
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Supprimer une entrée de catalogue (administrateur de catalogue d'un compte uniquement)
```
ibmcloud catalog entry-delete ID [--global]
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
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Obtenir la visibilité pour une entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-visibility ID [--global]
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
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Mettre à jour la visibilité d'une entrée de catalogue existante (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
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
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Répertorier les offres de services de la place du marché

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
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
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Afficher les modèles de conteneur boilerplate dans {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>-d (facultatif)</dt>
   <dd>Si l'option <i>-d</i> est spécifiée, la description de chaque modèle est également affichée. Sinon, seul l'ID et le nom des modèles sont affichés.</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Afficher les informations détaillées d'un modèle de conteneur boilerplate spécifié.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>ID du modèle de conteneur boilerplate. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
   </dl>


<strong>Exemples</strong> :

Afficher les détails du modèle `mobileBackendStarter` :

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Créez une application cf reposant sur le modèle spécifié avec l'adresse URL et la description indiquées. Par défaut, la nouvelle application est démarrée automatiquement.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>Modèle sur lequel sera basée l'application lors de sa création. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
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
ibmcloud catalog template-run javaHelloWorld my-app
```

Créez une application `my-ruby-app` d'après le modèle `rubyHelloWorld` avec la route
`myrubyapp.chinabluemix.net` et la description `Ma première application Ruby dans {{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Créez l'application `mon-app-python` d'après le modèle `pythonHelloWorld` sans démarrage automatique :

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Obtenir un sous-ensemble de choix de régions dans le format de votre choix.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-i, --id</dt>
  <dd>Indiquer la géographie par ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtenir une liste d'entrées pour le type indiqué.</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. Actuellement "groupe", "fournisseur" et "balises".</dd>
  <dt>--json</dt>
  <dd>Sortie de la réponse JSON d'origine.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale.</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Afficher les détails d'un contexte d'exécution. Cette commande est uniquement disponible dans un cloud public.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Exemples</strong> :

Afficher les détails du contexte d'exécution "nodejsHelloWorld" :

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Afficher tous les contextes d'exécution. Cette commande est uniquement disponible dans un cloud public.

```
ibmcloud catalog runtimes [-d]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-d</dt>
  <dd>Afficher la description de chaque contexte d'exécution</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les contextes d'exécution ainsi que leurs descriptions :

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Afficher l'utilisation mensuelle du compte en cours (administrateur de compte seulement)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
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
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Afficher l'utilisation mensuelle pour une organisation (administrateur de compte ou gestionnaire de facturation d'organisation seulement)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
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


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Afficher l'utilisation mensuelle pour un groupe de ressources (administrateur de compte ou administrateur de groupe de ressources seulement)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
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

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Afficher l'utilisation mensuelle des instances de ressource sous le compte en cours.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
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

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Répertorier tous les référentiels de plug-in enregistrés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Prérequis</strong> : Aucun


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Ajouter un nouveau référentiel de plug-in dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à ajouter. Vous pouvez définir votre propre nom pour chaque référentiel.</dd>
   <dt>REPO_URL (obligatoire)</dt>
   <dd>URL du référentiel à ajouter. Elle doit contenir le protocole (par exemple http://plugins.ng.bluemix.net au lieu de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net est le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Exemples</strong> :

Ajouter le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} sous la forme `bluemix-repo` :

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Retirer un référentiel de plug-in de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove REPO_NAME
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
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Répertorier tous les plug-in disponibles dans tous les référentiels ajoutés ou dans un référentiel spécifique.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
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
ibmcloud plugin repo-plugins
```

Répertorier tous les plug-in du référentiel `bluemix-repo` :

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Afficher les détails d'un plug-in dans le référentiel

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les détails du plug-in "IBM-Containers" dans le référentiel "sample-repo" :

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Afficher les détails du plug-in "IBM-Containers" dans le référentiel par défaut

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Répertorier tous les plug-in installés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Prérequis</strong> : Aucun

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Afficher les détails d'un plug-in installé

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Prérequis</strong> : Aucun


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Installer la version de plug-in spécifique dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} à partir du chemin ou du référentiel spécifié.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obligatoire)</dt>
   <dd>Si -r <i>REPO_NAME</i> n'est pas spécifié, le plug-in est installé depuis le chemin local spécifié ou depuis l'URL distante.</dd>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (facultatif)</dt>
   <dd>Version du plug-in à installer. Si elle n'est pas fournie, la dernière version du plug-in est installée. Cette option n'est valide que si vous installez le plug-in à partir du référentiel.</dd>
   <dt>-f </dt>
   <dd>Forcer l'installation du plug-in sans confirmation.</dd>
    </dl>


Le nom de référentiel officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est `Bluemix`.

<strong>Exemples</strong> :

Installer un plug-in depuis le fichier local :

```
ibmcloud plugin install /downloads/new_plugin
```

Installer un plug-in depuis l'adresse URL distante :

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Installer la dernière version du plug-in 'container-service' à partir du référentiel 'Bluemix' :

```
ibmcloud plugin install container-service -r Bluemix
```

ou simplement :

```
ibmcloud plugin install container-service
```

Installer la version '0.1.425' du plug-in 'container-service' à partir du référentiel de plug-in officiel :

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Mettre à niveau le plug-in à partir d'un référentiel

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nom du plug-in à mettre à jour. Si ce paramètre n'est pas spécifié, la commande recherche des mises à niveau pour tous les plug-ins installés.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (facultatif)</dt>
 <dd>Version du plug-in vers laquelle effectuer la mise à jour. Si elle n'est pas indiquée, le plug-in est mis à jour vers la version disponible la plus récente.</dd>
 <dt>--all</dt>
 <dd>Mettre à jour tous les plug-in disponibles</dd>
</dl>

<strong>Exemples</strong> :

Rechercher toutes les mises à niveau disponibles dans le référentiel de plug-in officiel 'Bluemix' :

```
ibmcloud plugin update -r Bluemix
```

ou simplement :

```
ibmcloud plugin update
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la dernière version :

```
ibmcloud plugin update container-service
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la version '0.1.440' :

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Désinstaller le plug-in spécifié de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall PLUGIN_NAME
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
ibmcloud plugin uninstall container-service
```

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Répertorier les environnements CFEE.

```
bx cfee environments
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Afficher les détails d'un environnement CFEE.

```
bx cfee environment NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>--id</dt>
   <dd>Afficher l'ID uniquement.</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les détails d'un environnement CFEE env_example :

```
bx cfee environment env_example
```

Afficher l'ID d'un environnement CFEE env_example :

```
bx cfee environment env_example --id
```
