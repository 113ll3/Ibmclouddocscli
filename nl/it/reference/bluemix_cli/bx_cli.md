---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-08"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Comandi {{site.data.keyword.Bluemix_notm}} (ibmcloud)
{: #bluemix_cli}

Versione: 0.7.1

L'interfaccia di riga comando (CLI) {{site.data.keyword.Bluemix_notm}} fornisce una serie di comandi che vengono raggruppati in base allo spazio dei nomi per consentire agli utenti di interagire con {{site.data.keyword.Bluemix_notm}}.

A partire dalla versione 0.5.0, il client riga di comando {{site.data.keyword.Bluemix_notm}} include un client riga di comando Cloud Foundry nella sua installazione. Se hai la tua propria CLI cf installata, non utilizzare i comandi della CLI {{site.data.keyword.Bluemix_notm}} `ibmcloud [comando]` e i comandi della CLI Cloud Foundry `cf [comando]` della tua propria installazione nello stesso contesto. Utilizza invece `ibmcloud cf [comando]` se vuoi utilizzare la CLI cf per gestire le risorse Cloud Foundry nel contesto della CLI {{site.data.keyword.Bluemix_notm}}.  Nota che `ibmcloud cf api/login/logout/target` non è consentito e devi utilizzare invece `ibmcloud api/login/logout/target`.

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.Bluemix_notm}} sono stati modificati da `bluemix` e `bx` a `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono rimossi in una data successiva.
{: tip}

Di seguito sono elencati in dettaglio i comandi supportati dalla CLI {{site.data.keyword.Bluemix_notm}}, compresi i loro nomi, argomenti, opzioni, prerequisiti, descrizioni ed esempi.
{:shortdesc}

**Nota:** i *Prerequisiti* elencano quali azioni sono richieste prima di utilizzare il comando. I comandi che non hanno azioni prerequisite elencano **Nessuno**. Altrimenti, i prerequisiti possono includere una o più delle seguenti azioni:

<dl>
<dt>Endpoint</dt>
<dd>Un endpoint API deve essere impostato mediante <code>bluemix api</code> prima di utilizzare il comando.</dd>
<dt>Accesso</dt>
<dd>L'accesso utilizzando il comando <code>bluemix login</code> è richiesto prima di utilizzare questo comando.
Se stai eseguendo l'accesso con l'ID federato, utilizza l'opzione '--sso' per autenticarti con il passcode monouso o utilizza '--apikey' per autenticarti con la chiave API. Vai alla console {{site.data.keyword.Bluemix_notm}} e fai clic su **Gestisci ** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma** per creare le chiavi API.
</dd>
<dt>Destinazione</dt>
<dd>Il comando <code>bluemix target</code> deve essere utilizzato per impostare un'organizzazione e uno spazio prima di utilizzare questo comando.</dd>
<dt>Docker</dt>
<dd>Per poter eseguire questo comando, è necessario che la CLI Docker (docker) sia installata.</dd>
</dl>


Utilizza gli indici nelle seguenti tabelle per fare riferimento ai comandi ibmcloud usati di frequente.

## Comandi ibmcloud generali
{: #bx_commands_index}

<table summary="Comandi ibmcloud generali.">
<caption>Tabella 1. Comandi ibmcloud generali</caption>
 <thead>
 <th colspan="5">Comandi ibmcloud generali</th>
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

 ## Comandi per la gestione e configurazione dei servizi dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
  {: #bx_commands_softlayer}

I comandi per la gestione dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} sono stati inglobati nella CLI {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni sull'utilizzo della CLI {{site.data.keyword.Bluemix_notm}} per configurare e gestire i servizi dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}, vedi: [Comandi della CLI {{site.data.keyword.Bluemix_notm}} per l'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html#softlayer_cli).

 ## Comandi per la gestione di account, organizzazioni e ruoli
 {: #bx_commands_account}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire account, organizzazioni, spazi e ruoli.">
<caption>Tabella 2. Comandi per gestire account, organizzazioni, spazi e ruoli</caption>
 <thead>
 <th colspan="5">Comandi per gestire account, organizzazioni, spazi e ruoli</th>
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


 ## Comandi per gestire i gruppi di risorse e le risorse
{: #bx_commands_resource}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire i gruppi di risorse e le risorse.">
  <caption>Tabella 3. Comandi per gestire i gruppi di risorse e le risorse</caption>
  <thead>
    <th colspan="5">Comandi per gestire i gruppi di risorse e le risorse</th>
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


 ## Comandi per gestire le politiche e le chiavi API
 {: #bx_commands_iam}
 <table summary="Comandi ibmcloud che puoi utilizzare per gestire le politiche e le chiavi API.">
 <caption>Tabella 4. Comandi per gestire le politiche e le chiavi API</caption>
  <thead>
  <th colspan="5">Comandi per gestire le politiche e le chiavi API</th>
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

 ## Comandi per la gestione di applicazioni cf e di domini, rotte e certificati relativi all'applicazione
 {: #bx_commands_apps}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire le applicazioni cf e i domini, le rotte e i certificati relativi all'applicazione.">
<caption>Tabella 5. Comandi per gestire le applicazioni cf e i domini, le rotte e i certificati correlati alle applicazioni</caption>
 <thead>
 <th colspan="5">Comandi per gestire le applicazioni cf e i domini, le rotte e i certificati correlati alle applicazioni</th>
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

 ## Comandi per la gestione dei servizi {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire i servizi {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabella 6. Comandi per la gestione dei servizi {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Comandi per la gestione dei servizi {{site.data.keyword.Bluemix_notm}}</th>
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


 ## Comandi per la gestione delle impostazioni di fatturazione, plug-in e catalogo
 {: #bx_commands_settings}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire le impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabella 7. Comandi per la gestione delle impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Comandi per la gestione delle impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}</th>
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

 ## Gestisci i Cloud Foundry Enterprise Environment (sperimentale)
{: #bx_commands_cfee}

<table summary="Gestisci i Cloud Foundry Enterprise Environment (sperimentale)">
<caption>Tabella 8. Gestisci i Cloud Foundry Enterprise Environment (sperimentale)</caption>
 <thead>
 <th colspan="5">Gestisci i Cloud Foundry Enterprise Environment (sperimentale)</th>
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
Visualizza la guida generale per i comandi integrati di primo livello e gli spazi dei nomi supportati della CLI {{site.data.keyword.Bluemix_notm}} oppure la guida per un comando o uno spazio dei nomi integrati specifici.

```
ibmcloud help [COMANDO|SPAZIONOMI]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>COMANDO|SPAZIONOMI (facoltativo)</dt>
   <dd>Il comando o lo spazio dei nomi per cui viene visualizzata la guida. Se non viene specificata, viene visualizzata la guida generale per la CLI {{site.data.keyword.Bluemix_notm}}.</dd>
   </dl>



<strong>Esempi</strong>:

Visualizza la guida generale per la CLI {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud help
```

Visualizza la guida per il comando `info`:

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
Imposta o visualizza l'endpoint API {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [ENDPOINT_API] [--unset] [--skip-ssl-validation]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ENDPOINT_API (facoltativo)</dt>
   <dd>L'endpoint API di destinazione, ad esempio `https://api.chinabluemix.net`. Se non vengono specificate entrambe le opzioni *ENDPOINT_API* e `--unset`, viene visualizzato l'endpoint API corrente.</dd>
   <dt>--unset (facoltativo)</dt>
   <dd>Rimuove l'impostazione di endpoint API.</dd>
   <dt>--skip-ssl-validation (facoltativo)</dt>
   <dd>Tralascia la convalida SSL delle richieste HTTP.</dd>
   </dl>
<strong>Esempi</strong>:

Imposta l'endpoint API su api.chinabluemix.net:

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

Visualizza l'endpoint API corrente:

```
ibmcloud api
```

Annulla l'impostazione dell'endpoint API:

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


Scrive i valori predefiniti nel file di configurazione.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDI | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDI</i></dt>
   <dd>Il valore di timeout per le richieste HTTP. Il valore predefinito è 60 secondi.</dd>
   <dt>--trace true|false|<i>percorso-al-file</i></dt>
   <dd>Traccia le richieste HTTP nel terminale o file specificato.</dd>
   <dt>--color true|false</dt>
   <dd>Abilita o disabilita l'output a colori. L'output a colori è abilitato per impostazione predefinita.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Imposta una locale predefinita. Se LOCALE è <i>CLEAR</i>, la locale precedente viene eliminata.</dd>
   <dt>--check-version true|false</dt>
   <dd>Abilita o disabilita il controllo della versione della CLI.</dd>
   </dl>

È possibile specificare solo una di queste opzioni alla volta.

<strong>Esempi</strong>:

Imposta il timeout della richiesta HTTP su 30 secondi:

```
ibmcloud config --http-timeout 30
```

Abilita l'output di traccia per le richieste HTTP:

```
ibmcloud config --trace true
```

Traccia le richieste HTTP in un file specificato */home/usera/my_trace*:

```
ibmcloud config --trace /home/usera/my_trace
```

Disabilita l'output a colori:

```
ibmcloud config --color false
```

Imposta la locale su zh_Hans:

```
ibmcloud config --locale zh_Hans
```

Cancella le impostazioni della locale:

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

Visualizza le informazioni su {{site.data.keyword.Bluemix_notm}} di base, compresi la regione corrente, la versione controller cloud e alcuni utili endpoint, quali gli endpoint per l'accesso e per lo scambio di token di accesso.

```
ibmcloud info
```

<strong>Prerequisiti</strong>:  Endpoint


## ibmcloud cf
{: #ibmcloud_cf}

Richiama la CLI CF integrata

```
ibmcloud [-q, --quiet] cf COMANDO...
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Disattiva il messaggio "Richiamo di comando cf..."</dd>
</dl>

<strong>Esempi</strong>:

Elenca le applicazioni cf:

```
ibmcloud cf apps
```

Elenca i servizi cf senza messaggio "Richiamo di comando cf...":

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

Esegue l'accesso dell'utente.

```
ibmcloud login [-a ENDPOINT_API] [--sso] [-u NOMEUTENTE] [-p PASSWORD] [--apikey CHIAVE | @FILE_CHIAVI] [--no-iam] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE] [-o ORGANIZZAZIONE] [-s SPAZIO]
```

<strong>Prerequisiti</strong>:  Nessuno

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opzioni del comando</strong>:
<dl>
  <dt> -a <i>ENDPOINT_API</i> (facoltativo)</dt>
  <dd> Endpoint API (ad esempio: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>CHIAVE_API o @PERCORSO_FILE_CHIAVI_API</i>
  <dd> Contenuto della chiave API o percorso del file della chiave API indicato da @</dd>
  <dt> --sso (facoltativo) </dt>
  <dd> Utilizza un passcode monouso per effettuare l'accesso </dd>
  <dt> -u <i>NOMEUTENTE</i> (facoltativo)</dt>
  <dd> Nome utente</dd>
  <dt> -p <i>PASSWORD</i> (facoltativo)</dt>
  <dd> Password</dd>
  <dt> -c <i>ID_ACCOUNT</i> (facoltativo) </dt>
  <dd> ID dell'account di destinazione</dd>
  <dt> -g <i>GRUPPO_RISORSE</i> (facoltativo) </dt>
  <dd> Nome del gruppo di risorse di destinazione</dd>
  <dt> -o <i>ORGANIZZAZIONE</i> (facoltativo)</dt>
  <dd> Nome dell'organizzazione di destinazione (obsoleto, utilizza 'ibmcloud target -o ORGANIZZAZIONE')</dd>
  <dt> -s <i>SPAZIO</i> (facoltativo) </dt>
  <dd> Nome dello spazio di destinazione (obsoleto, utilizza 'ibmcloud target -s SPAZIO')</dd>
  <dt> --no-iam </dt>
  <dd> Forza l'autenticazione con il server di accesso invece di IAM pubblico</dd>
  <dt> --skip-ssl-validation (facoltativo) </dt>
  <dd> Tralascia la convalida SSL delle richieste HTTP. Questa opzione non è consigliata.</dd>
</dl>

<strong>Esempi</strong>:

#### Accesso interattivo

```
ibmcloud login
```

Accesso con nome utente e password e imposta l'account, l'organizzazione e lo spazio di destinazione:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Accesso con il passcode monouso e imposta l'account, l'organizzazione e lo spazio di destinazione

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Accesso con la chiave API e imposta le destinazioni:

#### La chiave API ha un account associato

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### La chiave API non ha un account associato

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se la chiave API ha un account associato, il passaggio a un altro account non è consentito.

#### Utilizza un passcode monouso

```
ibmcloud login -u UserID --sso
```

La CLI fornirà un link all'URL e richiederà il passcode:
```
Codice monouso (Ottienine uno in https://Link_URL_per_ottenere_il_passcode):
```

Apri il link in un browser per ottenere il passcode. Digita il passcode fornito nella console e dovresti essere in grado di accedere.

## ibmcloud logout
{: #ibmcloud_logout}

Disconnette l'utente.

```
ibmcloud logout
```

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud regions
{: #ibmcloud_regions}

Visualizza le informazioni per tutte le regioni su {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Prerequisiti</strong>:  Endpoint


## ibmcloud target
{: #ibmcloud_target}


Imposta o visualizza l'account, la regione, l'organizzazione o lo spazio di destinazione.

```
ibmcloud target [-r NOME_REGIONE] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE] [--cf] [-o ORGANIZZAZIONE] [-s SPAZIO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-r <i>NOME_REGIONE</i> (facoltativo)</dt>
   <dd>Nome della regione a cui essere passati, come 'us-south' o 'eu-gb'.</dd>
   <dt>-c <i>ID_ACCOUNT</i> (facoltativo)</dt>
   <dd>L'ID dell'account di destinazione.</dd>
   <dt>-g <i>GRUPPO_RISORSE</i> (facoltativo)</dt>
   <dd>Nome del gruppo di risorse</dd>
   <dt>--cf</dt>
   <dd>Seleziona interattivamente l'organizzazione e lo spazio di destinazione</dd>
   <dt>-o <i>NOME_ORGANIZZAZIONE</i> (facoltativo)</dt>
   <dd>Il nome dell'organizzazione di destinazione.</dd>
   <dt>-s <i>NOME_SPAZIO</i> (facoltativo)</dt>
   <dd>Il nome dello spazio di destinazione.</dd>
   </dl>
Se nessuna delle opzioni viene specificata, vengono visualizzati l'account, la regione, l'organizzazione e lo spazio correnti.

<strong>Esempi</strong>:

Imposta l'account, l'organizzazione e lo spazio correnti:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Passa a una nuova regione:

```
ibmcloud target -r eu-gb
```

Visualizza l'account, la regione, l'organizzazione e lo spazio correnti:

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

Aggiorna la CLI alla versione più recente.

```
ibmcloud update [-f]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forza l'aggiornamento senza conferma. Il privilegio root è obbligatorio.</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Elenca tutte le organizzazioni

```
ibmcloud account orgs [-r REGIONE] [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-r <i>REGIONE</i> (facoltativo)</dt>
   <dd>Regione per cui vengono visualizzare le informazioni sull'organizzazione. Se impostato su 'all', vengono elencate tutte le organizzazioni in tutte le regioni.</dd>
   <dt>--guid (facoltativo)</dt>
   <dd>Visualizza il GUID delle organizzazioni.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutte le organizzazioni della regione: `us-south` con il GUID visualizzato

```
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

Visualizza le informazioni per l'organizzazione specificata.

```
ibmcloud account org NOME_ORGANIZZAZIONE [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>--guid (facoltativo)</dt>
   <dd>Visualizza il GUID dell'organizzazione.</dd>
   </dl>

<strong>Esempi</strong>:

Mostra le informazioni dell'organizzazione `IBM` con il GUID visualizzato

```
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crea una nuova organizzazione. Questa operazione può essere eseguita solo dal proprietario dell'account.

```
ibmcloud account org-create NOME_ORGANIZZAZIONE [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione in fase di creazione.</dd>
   <dt>-f</dt>
   <dd>Forza la creazione senza conferma.</dd>
   </dl>

<strong>Esempi</strong>:

Crea un'organizzazione denominata `IBM`.

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replica un'organizzazione dalla regione corrente in un'altra regione.

```
ibmcloud account org-replicate NOME_ORGANIZZAZIONE NOME_REGIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione esistente che deve essere replicata.</dd>
   <dt>NOME_REGIONE (obbligatorio)</dt>
   <dd>Il nome della regione che ospita l'organizzazione replicata.</dd>
   </dl>

<strong>Esempi</strong>:

Replica l'organizzazione `myorg` nella regione `eu-gb`:

```
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rinomina un'organizzazione. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-rename VECCHIO_NOME_ORGANIZZAZIONE NUOVO_NOME_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE_PRECEDENTE (obbligatorio)</dt>
   <dd>Il vecchio nome dell'organizzazione da rinominare.</dd>
   <dt>NUOVO_NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nuovo nome con cui viene rinominata l'organizzazione.</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Elenca tutti gli spazi

```
ibmcloud account spaces [-o NOME_ORGANIZZAZIONE] [-r NOME-REGIONE]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nome dell'organizzazione. Elenca gli spazi nell'organizzazione specificata. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>-r</dt>
   <dd>Nome della regione. Elenca gli spazi nella regione specificata. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualizza gli utenti nell'organizzazione specificata per il ruolo.

```
ibmcloud account org-users NOME_ORGANIZZAZIONE [-a]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
<dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
<dd>Il nome dell'organizzazione.</dd>
<dt>-a (facoltativo)</dt>
<dd>Elenca tutti gli utenti dell'organizzazione specificata, non raggruppati per ruolo.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Aggiunge un utente nell'organizzazione (è richiesto il gestore organizzazione).

```
 ibmcloud account org-user-add NOME_UTENTE ORGANIZZAZIONE
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Rimuove un utente dall'organizzazione (gestore organizzazione o solo l'utente)

```
   ibmcloud account org-user-remove NOME_UTENTE ORGANIZZAZIONE [-f, --force]
```

<strong>Opzioni comando</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Ottiene tutti i ruoli organizzazione dell'utente corrente

```
ibmcloud account org-roles [-u ID_UTENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID utente. Se non specificato, il valore predefinito è l'utente corrente.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assegna un ruolo dell'organizzazione ad un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-role-set NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di assegnazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>RUOLO_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione a cui viene assegnato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
  </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` con il ruolo `OrgManager`:

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Nota**: puoi impostare i ruoli org/space utilizzando la CLI ma, se vuoi impostare le altre autorizzazioni, devi utilizzare l'IU. Per ulteriori dettagli, vedi [Assegnazione dell'accesso utente](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Rimuove un ruolo dell'organizzazione da un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di eliminazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>RUOLO_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
    </dl>

<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` con il ruolo `OrgManager`:

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Visualizza gli utenti nello spazio specificato per il ruolo.

```
ibmcloud account space-users NOME_ORGANIZZAZIONE NOME_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio.</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assegna un ruolo dello spazio ad un utente. Questa operazione può essere eseguita solo da un gestore spazio.

```
ibmcloud account space-role-set NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di assegnazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio a cui è assegnato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio a cui è assegnato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
    </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` e allo spazio `Cloud` con il ruolo `SpaceManager`:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Rimuove un ruolo dello spazio da un utente. Questa operazione può essere eseguita solo da un gestore spazio.

```
ibmcloud account space-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di eliminazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio da cui viene eliminato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
    </dl>


<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` e dall spazio `Cloud` con il ruolo `SpaceManager`:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Elenca tutti gli account dell'utente corrente

```
ibmcloud account list
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualizza l'account dell'organizzazione specificata (utente dell'organizzazione obbligatorio)

```
ibmcloud account org-account NOME_ORGANIZZAZIONE [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--guid (facoltativo)</dt>
  <dd>Visualizza solo l'ID account</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

Visualizza gli utenti associati con l'account. Questa operazione può essere eseguita solo dal proprietario dell'account.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Rimuovi un utente da un account (solo il proprietario dell'account)

```
ibmcloud account user-remove ID_UTENTE [-c ID_ACCOUNT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>ID_UTENTE (obbligatorio)</dt>
<dd>ID utente</dd>
<dt>-c ID_ACCOUNT</dt>
<dd>ID account. Se non specificato, il valore predefinito è l'account corrente.</dd>
<dt>-f, --force</dt>
<dd>Forza la rimozione senza conferma.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invita un utente nell'account

```
ibmcloud account user-invite EMAIL_UTENTE [-o ORG [--org-role RUOLO_ORG] [-s SPAZIO, --space-role RUOLO_SPAZIO]]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'email dell'utente invitato.</dd>
   <dt>-o ORG</dt>
   <dd>Organizzazione a cui invitare l'utente</dd>
   <dt>--org-role RUOLO_ORG</dt>
   <dd>Ruolo organizzazione. Gli input validi sono: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omesso, verrà impostato il ruolo OrgUser.</dd>
   <dt>-s SPAZIO</dt>
   <dd>Spazio a cui invitare l'utente</dd>
   <dt>--space-role RUOLO_SPAZIO</dt>
   <dd>Ruolo spazio. Gli input validi sono: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Invia di nuovo l'invito a un utente (amministratore dell'account)

```
ibmcloud account user-reinvite EMAIL_UTENTE
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene nuovamente invitato.</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Elenca i gruppi di accesso nell'account corrente

```
ibmcloud iam access-groups [-u NOME_UTENTE | -s NOME_ID_SERVIZIO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-u</dt>
  <dd>Elenca i gruppi di accesso a cui appartiene l'utente. Questo indicatore è esclusivo per '-s'.</dd>
  <dt>-s</dt>
  <dd>Elenca i gruppi di accesso a cui appartienel'ID del servizio. Questo indicatore è esclusivo per '-u'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di accesso:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Mostra i dettagli di un gruppo di accesso

```
ibmcloud iam access-group NOME_GRUPPO [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-id</dt>
  <dd>Mostra solo l'ID</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli del gruppo di accesso `example_group`:

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Crea un gruppo di accesso

```
ibmcloud iam access-group-create NOME_GRUPPO [-d, --description DESCRIZIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descrizione del gruppo di accesso</dd>
</dl>

<strong>Esempi</strong>:

Crea un gruppo di accesso `example_group`:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Aggiorna un gruppo di accesso

```
ibmcloud iam access-group-update NOME_GRUPPO [-n, --name NUOVO_NOME] [-d, --description NUOVA_DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del gruppo di accesso</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Ridenomina il gruppo di accesso `example_group` con `hello_world_group`:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Elimina un gruppo di accesso

```
ibmcloud iam access-group-delete NOME_GRUPPO [-f, --force] [-r, --recursive]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
  <dt>-r, --recursive</dt>
  <dd>Elimina il gruppo di accesso e i relativi membri</dd>
</dl>

<strong>Esempi</strong>:

Elimina il gruppo di accesso `example_group`:

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Elenca gli utenti in un gruppo di accesso

```
ibmcloud iam access-group-users NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli utenti nel gruppo di accesso `example_group`:

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Aggiunge gli utenti a un gruppo di accesso

```
ibmcloud iam access-group-user-add NOME_GRUPPO NOME_UTENTE [NOME_UTENTE2...]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiunge l'utente `name@example.com` al gruppo di accesso `example_group`:

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Rimuove un utente da un gruppo di accesso

```
ibmcloud iam access-group-user-remove NOME_GRUPPO NOME_UTENTE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Rimuove l'utente `name@example.com` dal gruppo di accesso `example_group`:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Rimuove l'utente da tutti i gruppi di accesso

```
ibmcloud iam access-group-user-purge NOME_UTENTE [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rimuove l'utente `name@example.com` da tutti i gruppi di accesso:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Elenca gli ID del servizio in un gruppo di accesso

```
ibmcloud iam access-group-service-ids NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli ID del servizio nel gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Aggiungi l'ID del servizio a un gruppo di accesso

```
ibmcloud iam access-group-service-id-add NOME_GRUPPO NOME_ID_SERVIZIO [NOME_ID_SERVIZIO2...]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiunge l'ID del servizio `example-service` al gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Rimuove un utente da un ID del servizio di accesso

```
ibmcloud iam access-group-service-id-remove NOME_GRUPPO NOME_ID_SERVIZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Rimuove l'ID del servizio `example-service` dal gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Rimuove l'ID del servizio da tutti i gruppi di accesso

```
ibmcloud iam access-group-service-id-purge NOME_ID_SERVIZIO [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rimuove l'ID del servizio `example-service` da tutti i gruppi di accesso:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Elenca le politiche di un gruppo di accesso

```
ibmcloud iam access-group-policies NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutte le politiche del gruppo di accesso `example_group`:

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Mostra i dettagli di una politica del gruppo di accesso

```
ibmcloud iam access-group-policy NOME_GRUPPO ID_POLITICA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della politica `51b9717e-76b0-4f6a-bda7-b8132431f926` del gruppo di accesso `example_group`:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Crea una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-create NOME_GRUPPO {--file @FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSA] [--resource-group-id ID_GRUPPO_RISORSA]}
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>-roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Crea una politica del gruppo di accesso da un file JSON:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Assegna a `example_group` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Assegna a `example_group` il ruolo `Editor` per la risorsa `key123` dell'istanza `sample-service` con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Assegna a `example_group` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Assegna a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Assegna a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Aggiorna una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-update ID_POLITICA_NOME_GRUPPO {--file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSA] [--resource-group-id ID_GRUPPO_RISORSA]}
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>--roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica del gruppo di accesso con quella nel file JSON della politica:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Aggiorna la politica del gruppo di accesso per assegnare a `example_group` il ruolo `Editor` per la risorsa `key123` dell'istanza `sample-service` con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`.
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Elimina a una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-delete NOME_GRUPPO ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la politica `51b9717e-76b0-4f6a-bda7-b8132431f926` del gruppo di accesso `example_group`:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Elenca tutti gli ID servizio

```
ibmcloud iam service-ids [--uuid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Mostra l'UUID solo degli ID servizio</dd>
</dl>

<strong>Esempi</strong>:
elenca l'UUID di tutti gli ID servizio sotto l'account corrente

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Visualizza i dettagli di un ID servizio

```
ibmcloud iam service-id (NOME|UUID) [--uuid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>--uuid</dt>
  <dd>Visualizza l'UUID dell'ID servizio</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'ID servizio `sample-test`

```
ibmcloud iam service-id sample-test
```
Mostra i dettagli dell'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Crea un ID servizio

```
ibmcloud iam service-id-create NOME [-d, --description DESCRIZIONE] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione dell'ID servizio</dd>
  <dt>--lock</dt>
  <dd>Blocca l'ID servizio quando è in fase di creazione</dd>
</dl>

<strong>Esempi</strong>:

Crea un ID servizio con il nome servizio `sample-test` e la descrizione `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Crea un ID servizio bloccato con il nome servizio `sample-test` e la descrizione `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Aggiorna un ID servizio

```
ibmcloud iam service-id-update (NOME|UUID) [-n, --name NUOVO_NOME] [-d, --description DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione del servizio</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina l'ID servizio `sample-test` come `sample-test-2` senza conferma

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Aggiorna la descrizione del servizio `sample-test`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Rinomina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` con `sample-test-3` con una nuova descrizione

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Elimina un ID servizio

```
ibmcloud iam service-id-delete (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina l'ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-delete sample-teset -f
```

Elimina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Blocca un ID servizio

```
ibmcloud iam service-id-lock (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-lock sample-teset -f
```

Blocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Sblocca un ID servizio

```
ibmcloud iam service-id-unlock (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-unlock sample-teset -f
```

Sblocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Elenca tutte le chiavi API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crea una nuova chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NOME [-d DESCRIZIONE] [--file FILE] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da creare.</dd>
<dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
<dd>Descrizione della chiave API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Salva le informazioni della chiave API nel file specificato. Se non impostato, verrà visualizzato il contenuto JSON.</dd>
<dt>--lock</dt>
<dd>Blocca la chiave API quando è in fase di creazione</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API e salva in un file

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Crea una chiave API bloccata con il nome "test-key"

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Aggiorna una chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NOME|UUID) [-n name] [-d description]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Il vecchio nome della chiave API da aggiornare, esclusivo con UUID,</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da aggiornare, esclusivo con NOME</dd>
<dt>-n <i>NOME</i> (facoltativo)</dt>
<dd>Il nuovo nome della chiave API</dd>
<dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
<dd>La nuova descrizione della chiave API</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la descrizione di una chiave API:

```
ibmcloud iam api-key-update MyKey -d "la nuova descrizione della mia chiave"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Elimina una chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-delete (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da eliminare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da eliminare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

Blocca una chiave API della piattaforma

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da bloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da bloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza blocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

Blocca la chiave API con l'UUID fornito senza conferma

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Sblocca una chiave API della piattaforma

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da sbloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da sbloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza sblocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Sblocca la chiave API test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

Sblocca la chiave API con l'UUID fornito senza conferma

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Elenca tutte le chiavi API di un servizio

```
ibmcloud iam service-api-keys (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza le chiavi API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le chiavi API del servizio `sample-service` :

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Elenca i dettagli di una chiave API di servizio

```
ibmcloud iam service-api-key (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [--uuid] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>--uuid</dt>
  <dd>Visualizza l'UUID della chiave API di servizio</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza la chiave API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della chiave API `sample-key` del servizio `sample-service` :

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Crea una chiave API di servizio

```
ibmcloud iam service-api-key-create NOME (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-d, --description DESCRIZIONE] [--file FILE] [-f, --force] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome o chiave API del servizio appena creata</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione della chiave API</dd>
  <dt>--file</dt>
  <dd>Salva le informazioni della chiave API nel file specificato. Se non impostato, verrà visualizzato il contenuto JSON.</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API `sample-key` per il servizio `sample-service` senza conferma:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Aggiorna una chiave API di servizio

```
ibmcloud iam service-api-key-update (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO)  [-n, --name NUOVO_NOME] [-d, --description DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome della chiave API di servizio</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione della chiave API di servizio</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina la chiave API di servizio `sample-key` come `new-sample-key` :

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Elimina una chiave API di servizio

```
ibmcloud iam service-api-key-delete (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Blocca una chiave API del servizio

```
ibmcloud iam service-api-key-lock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Sblocca una chiave API del servizio

```
ibmcloud iam service-api-key-unlock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Elenca le politiche dell'utente `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartengono le politiche</dd>
</dl>

<strong>Esempi</strong>:

Elenca le politiche dell'utente `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Visualizza i dettagli di una politica utente

```
ibmcloud iam user-policy NOME_UTENTE ID_POLITICA
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica</dd>
</dl>

<strong>Esempi</strong>:

Elenca la politica `0bb730daa` dell'utente `name@example.com`:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Crea una politica utente

```
ibmcloud iam user-policy-create NOME_UTENTE {--file FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSA] [--resource-group-id ID_GRUPPO_RISORSA]}
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Crea la politica utente per l'utente `name@example.com` dal file JSON di politiche `policy.json`:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

Assegna a `name@example.com` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Assegna a `name@example.com` il ruolo `Editor` per la risorsa `key123` dell'istanza del servizio di esempio con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Assegna a `name@example.com` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Assegna a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Assegna a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Aggiorna una politica utente

```
ibmcloud iam user-policy-update NOME_UTENTE ID_POLITICA {--file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSA] [--resource-group-id ID_GRUPPO_RISORSA]}
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica da aggiornare</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica utente con quella nel file JSON

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Aggiorna la politica utente per assegnare a `name@example.com` il ruolo `Editor` per la risorsa `key123` dell'istanza del servizio di esempio con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Elimina una politica utente

```
ibmcloud iam user-policy-delete ID_UTENTE ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina la politica utente senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina le politiche `user-policy-id` dell'utente `name@example.com`:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Elimina le politiche `user-policy-id` dell'utente `name@example.com` senza conferma:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Elenca tutte le politiche di servizio del servizio specificato

```
ibmcloud iam service-policies ID_SERVIZIO [--json] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>-json</dt>
  <dd>Visualizza la politica in formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza le politiche di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elenca le politiche del servizio `test`:

```
ibmcloud iam service-policies test
```
Elenca le politiche del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Visualizza i dettagli di una politica di servizio

```
ibmcloud iam service-policy ID_SERVIZIO ID_POLITICA [--json] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>-json</dt>
  <dd>Visualizza la politica in formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza la politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Mostra la politica `140798e2-8ea7db3` del servizio `test`:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Mostra la politica `140798e2-8ea7db3` del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Crea una politica di servizio

```
ibmcloud iam service-policy-create ID_SERVIZIO {--file FILE_JSON | -r, --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]} [-f, --force]",
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. È esclusivo con gli indicatori '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' e '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Nome del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource</dt>
  <dd>Risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Crea politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Crea la politica di servizio dal file JSON per il servizio `test`:

```
ibmcloud iam service-policy-create test --file @policy.json
```
Crea la politica di servizio dal file JSON per il servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Aggiorna una politica di servizio

```
ibmcloud iam service-policy-update ID_SERVIZIO ID_POLITICA {--file FILE_JSON | [-r, --roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]} [-f, --force]",
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. È esclusivo con gli indicatori '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' e 'resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna la politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `test`:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Elimina una politica di servizio

```
ibmcloud iam service-policy-delete ID_SERVIZIO ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la politica `140798e2-8ea7db3` del servizio `test`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Elimina la politica `140798e2-8ea7db3` del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Richiama e visualizza i token OAuth per la sessione corrente

```
ibmcloud iam oauth-tokens
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiorna e visualizza i token OAuth

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Scollega l'ID IBM pubblico dall'ID non IBM dedicato

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza la disconnessione senza conferma</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Creare una politica di autorizzazione per consentire a un'istanza del servizio di accedere a un'altra istanza del servizio.

```
ibmcloud iam authorization-policy-create NOME_SERVIZIO_ORIGINE NOME_SERVIZIO_DESTINAZIONE NOME_RUOLO1,NOME_RUOLO2... [—-source-service-instance NOME_ISTANZA_SERVIZIO_ORIGINE] [—-target-service-instance NOME_ISTANZA_SERVIZIO_DESTINAZIONE]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_SERVIZIO_ORIGINE</dt>
  <dd>Servizio di origine che può essere autorizzato ad accedere.</dd>
  <dt>NOME_SERVIZIO_DESTINAZIONE</dt>
  <dd>Servizio di destinazione a cui il servizio di origine può essere autorizzate ad accedere.</dd>
  <dt>NOME_RUOLO1,NOME_RUOLO2...</dt>
  <dd>I ruoli che forniscono l'accesso per il servizio di origine.</dd>  
  <dt>—-source-service-instance NOME_ISTANZA_SERVIZIO_ORIGINE</dt>
  <dd>Nome dell'istanza del servizio di origine, se non specificato, tutte le istanza del servizio di origine saranno autorizzate ad accedere.</dd>
  <dt>—-target-service-instance NOME_ISTANZA_SERVIZIO_DESTINAZIONE</dt>
  <dd>Nome dell'istanza del servizio di destinazione, se non specificato, tutte le istanza del servizio di destinazione saranno autorizzate ad accedere.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Elimina una politica di autorizzazione.

```
ibmcloud iam authorization-policy-delete ID_POLITICA_AUTORIZZAZIONE [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_POLITICA_AUTORIZZAZIONE</dt>
  <dd>ID della politica di autorizzazione da eliminare.</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Mostra i dettagli di una politica di autorizzazione.

```
ibmcloud iam authorization-policy ID_POLITICA_AUTORIZZAZIONE
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ID_POLITICA_AUTORIZZAZIONE</dt>
  <dd>ID della politica di autorizzazione da mostrare.</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Elenca le politiche di autorizzazione nell'account corrente.

```
ibmcloud iam authorization-policies
```

<strong>Prerequisiti</strong>: Accesso, Destinazione


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Elenca i gruppi di risorse.

```
ibmcloud resource groups [--default]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--default</dt>
  <dd>Richiama il gruppo predefinito dell'account corrente.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di risorse nell'account attualmente selezionato:

```
ibmcloud resource groups
```

Elenca il gruppo predefinito dell'account attualmente selezionato:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Mostra i dettagli di un gruppo di risorse

```
ibmcloud resource group NOME [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse</dd>
  <dt>--id</dt>
  <dd>Mostra solo l'ID</dd>
</dl>

<strong>Esempi</strong>:

Mostra il gruppo di risorse `example-group`:

```
ibmcloud resource group example-group
```

Mostra solo l'ID del gruppo di risorse `example-group`:

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Crea un gruppo di risorse

```
ibmcloud resource group-create NOME NOME_QUOTA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:

<strong>Esempi</strong>:

Crea un gruppo di risorse `example-group` con quota `free`:

```
ibmcloud resource group-create example-group free
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Aggiorna un gruppo di risorse esistente

```
ibmcloud resource group-update NOME [-n, --name NUOVO_NOME] [-q, --quota NOME_NUOVA_QUOTA]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse di destinazione</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del gruppo di risorse</dd>
  <dt>-q, --quota</dt>
  <dd>Nome della nuova definizione di quota</dd>
  <dt>-f</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina il gruppo di risorse `example-group` come `trial-group`:

```
ibmcloud resource group-update example-group -n trial-group
```

Modifica la quota del gruppo di risorse `example-group` come `free`:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Elenca tutte le definizioni di quota

```
ibmcloud resource quotas
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutte le definizioni di quota:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Mostra i dettagli di una definizione di quota

```
ibmcloud resource quota NOME
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome della quota</dd>
</dl>

<strong>Esempi</strong>:
mostra i dettagli della quota `free`:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migra una istanza del servizio Cloudfoundry nel gruppo di risorse

```
bx resource cf-service-instance-migrate (NOME_ISTANZA_SERVIZIO | ID_ISTANZA_SERVIZIO) [--resource-group-name NOME_GRUPPO_RISORSA | --resource-group-id ID_GRUPPO_RISORSA] [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ISTANZA_SERVIZIO o ID_ISTANZA_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID dell'istanza del servizio</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--resource-group-id'. Se non viene specificata alcuna di tali opzioni, viene utilizzato come valore predefinito il gruppo di risorse attualmente di destinazione.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--resource-group-name'. Se non viene specificata alcuna di tali opzioni, viene utilizzato come valore predefinito il gruppo di risorse attualmente di destinazione.</dd>
  <dt>-f, --force</dt>
  <dd>Migra senza conferma</dd>
</dl>


## ibmcloud app push
{: #ibmcloud_app_push}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf push ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## ibmcloud app list
{: #ibmcloud_app_list}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf apps ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## ibmcloud app show
{: #ibmcloud_app_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf app ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## ibmcloud app delete
{: #ibmcloud_app_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## ibmcloud app rename
{: #ibmcloud_app_rename}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## ibmcloud app start
{: #ibmcloud_app_start}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf start ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## ibmcloud app stop
{: #ibmcloud_app_stop}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stop ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## ibmcloud app restart
{: #ibmcloud_app_restart}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restart ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## ibmcloud app restage
{: #ibmcloud_app_restage}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restage ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restart-app-instance ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## ibmcloud app events
{: #ibmcloud_app_events}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf events ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## ibmcloud app files
{: #ibmcloud_app_files}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf files ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## ibmcloud app logs
{: #ibmcloud_app_logs}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf logs ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## ibmcloud app env
{: #ibmcloud_app_env}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf set-env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf unset-env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stacks ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stack ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-app-manifest ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Elenca le informazioni sul certificato di un dominio.

```
ibmcloud app domain-cert NOME_DOMINIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_DOMINIO (obbligatorio)</dt>
<dd>Il dominio che ospita il certificato.</dd>
</dl>


<strong>Esempi</strong>:

Visualizza le informazioni sul certificato del dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Aggiunge un certificato al dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-add DOMINIO -k FILE_CHIAVE PRIVATA -c FILE_CERTIFICATO [-p PASSWORD] [-i FILE_CERTIFICATO_INTERMEDIO] [-t FILE_TRUSTSTORE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio a cui viene aggiunto il certificato.</dd>
   <dt>-k <i>FILE_CHIAVE PRIVATA</i> (obbligatorio)</dt>
   <dd>Il percorso del file della chiave privata.</dd>
   <dt>-c <i>FILE_CERTIFICATO</i> (obbligatorio)</dt>
   <dd>Il percorso del file del certificato.</dd>
   <dt>-p <i>PASSWORD</i> (facoltativo)</dt>
   <dd>La password per il certificato.</dd>
   <dt>-i <i>FILE_CERTIFICATO_INTERMEDIO</i> (optional)</dt>
   <dd>Il percorso del file di certificato intermedio.</dd>
   <dt>-t <i>FILE_TRUSTSTORE</i> (facoltativo)</dt>
   <dd>Il file truststore.</dd>
   </dl>


<strong>Esempi</strong>:

Aggiunge un certificato al dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Rimuove un certificato dal dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-remove DOMINIO [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio da cui rimuovere il certificato.</dd>
   <dt>-f (facoltativo)</dt>
   <dd>Forza l'eliminazione senza conferma.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf routes ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf check-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Associa una rotta a un'applicazione cf o a un gruppo di contenitori esistenti che hanno il dominio e il nome host specificati.

```
ibmcloud app route-map NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORE  DOMINIO  [-n NOME_HOST]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORI (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf o del gruppo di contenitori da associare a una rotta.</dd>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio della rotta. Ad esempio, mychinabluemix.net o chinabluemix.net. </dd>
   <dt>-n <i>NOME_HOST</i> (facoltativo)</dt>
   <dd>Il nome host della rotta. Se non viene fornito, il nome host è impostato sul nome applicazione o sul nome gruppo di contenitori per impostazione predefinita.</dd>
   </dl>

<strong>Esempi</strong>:

Associa una rotta `my-app` con il dominio specificato:

```
ibmcloud app route-map my-app mychinabluemix.net
```

Associa una rotta a 'my-container-group' con il dominio e il nome host specificati:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Annulla l'associazione della rotta specificata a un'applicazione cf o a un gruppo di contenitori esistenti.

```
ibmcloud app route-unmap NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORE  DOMINIO  [-n NOME_HOST]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORI (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf o del gruppo di contenitori.</dd>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio della rotta (ad esempio, mychinabluemix.net o chinabluemix.net).</dd>
   <dt>-n <i>NOME_HOST</i> (facoltativo)</dt>
   <dd>Il nome host della rotta. Se non viene fornito, il nome host è impostato sul nome applicazione o sul nome gruppo di contenitori per impostazione predefinita.</dd>
   </dl>

<strong>Esempi</strong>:

Annulla l'associazione di `my-app.mychinabluemix.net` da `my-app`:

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Annulla l'associazione di `abc.chinabluexmix.net` da `my-container-group`:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-orphaned-routes ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## ibmcloud app domains
{: #ibmcloud_app_domains}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf domains ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-shared-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-shared-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf marketplace ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## ibmcloud service list
{: #ibmcloud_service_list}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf services ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## ibmcloud service show
{: #ibmcloud_service_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## ibmcloud service create
{: #ibmcloud_service_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## ibmcloud service update
{: #ibmcloud_service_update}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf update-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## ibmcloud service delete
{: #ibmcloud_service_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## ibmcloud service rename
{: #ibmcloud_service_rename}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## ibmcloud service bind
{: #ibmcloud_service_bind}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf bind-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf unbind-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-service-key ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-service-key ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## ibmcloud service keys
{: #ibmcloud_service_keys}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf service-keys ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf service-key ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-user-provided-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf update-user-provided-service ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Elenca le istanze del servizio

```
ibmcloud resource service-instances [--service-name NOME_SERVIZIO] [--location UBICAZIONE] [--long]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Nome del servizio di appartenenza</dd>
  <dt>--location</dt>
  <dd>Filtra per ubicazione</dd>
  <dt>--long</dt>
  <dd>Mostra dei campi aggiuntivi nell'output</dd>
</dl>

<strong>Esempi</strong>:

Elenca le istanze del servizio `test-service`:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostra di dettagli di un'istanza del servizio

```
ibmcloud resource service-instance (NOME|ID) [--location UBICAZIONE] [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio), esclusivo con ID</dt>
  <dd>Nome dell'istanza del servizio</dd>
  <dt>ID (obbligatorio), esclusivo con NOME</dt>
  <dd>ID dell'istanza del servizio</dd>
  <dt>--location</dt>
  <dd>Filtra per ubicazione</dd>
  <dt>--id</dt>
  <dd>Visualizza l'ID dell'istanza del servizio</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-instance my-service-instance
``` 

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Crea un'istanza del servizio

```
ibmcloud resource service-instance-create NOME NOME_SERVIZIO|ID_SERVIZIO NOME_PIANO_SERVIZIO|ID_PIANO_SERVIZIO UBICAZIONE [-d, --deployment NOME_DISTRIBUZIONE] [-t, --tags TAG] [-p, --parameters @FILE_JSON | STRINGA_JSON ]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio</dd>
  <dt>NOME_SERVIZIO o ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID del servizio</dd>
  <dt>NOME_PIANO_SERVIZIO o ID_PIANO_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID del piano di servizio</dd>
  <dt>UBICAZIONE</dt>
  <dd>Ubicazione o ambiente di destinazione per creare l'istanza del servizio</dd>
  <dt>-t, --tags</dt>
  <dd>Tag</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON di parametri per creare l'istanza del servizio</dd>
  <dt>-d, --deployment</dt>
  <dd>Nome della distribuzione</dd>
</dl>

<strong>Esempi</strong>:
Crea un'istanza del servizio denominata `my-service-instance` che utilizza il piano di servizio `test-service-plan` del servizio `test-service` nell'ubicazione `eu-gb`:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Aggiorna l'istanza del servizio

```
ibmcloud resource service-instance-update (NOME|ID) [-n, --name NUOVO_NOME] [-t, --tags TAG] [--service-plan-id ID_PIANO_SERVIZIO] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>Nome (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio, esclusivo con ID</dd>
  <dt>ID (obbligatorio)</dt>
  <dd>ID dell'istanza del servizio, esclusivo con NOME</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome dell'istanza del servizio</dd>
  <dt>-t, --tags</dt>
  <dd>Nuove tag</dd>
  <dt>--service-plan-id</dt>
  <dd>Nuovo ID del piano di servizio</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Aggiorna l'istanza del servizio `my-service-instance`, modifica il suo nome in `new-service-instance`:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Elimina l'istanza del servizio

```
ibmcloud resource service-instance-delete (NOME|ID) [-f, --force] [--recursive]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>Nome (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio, esclusivo con ID</dd>
  <dt>ID (obbligatorio)</dt>
  <dd>ID dell'istanza del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
  <dt>--recursive</dt>
  <dd>Elimina tutte le risorse di appartenenza</dd>
</dl>

<strong>Esempi</strong>:
Elimina la risorsa istanza-servizio `my-service-instance`:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Mostra i bind all'alias del servizio

```
ibmcloud resource service-bindings ALIAS_SERVIZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
</dl>

<strong>Esempi</strong>:
Mostra i bind della risorsa all'alias del servizio `my-service-alias`:

```
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostra i dettagli di un bind del servizio

```
ibmcloud resource service-binding NOME_ALIAS NOME_APPLICAZIONE [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Visualizza solo l'ID. Tutto l'altro output per il bind del servizio viene eliminato.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli del bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app`:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crea un bind del servizio

```
ibmcloud resource service-binding-create NOME_ALIAS_SERVIZIO NOME_APPLICAZIONE NOME_RUOLO [--service-id ID_SERVIZIO] [-p, --parameters @FILE_JSON | TESTO_JSON] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>NOME_RUOLO</dt>
  <dd>Nome del ruolo utente</dd>
  <dt>--service-id</dt>
  <dd>Nome o UUID dell'ID del servizio a cui appartiene il ruolo</dd>
  <dt>-p, --parameter</dt>
  <dd>File JSON o stringa JSON dei parametri</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Crea un bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app` con i ruolo `Administrator`:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Elimina un bind del servizio

```
ibmcloud resource service-binding-delete ALIAS_SERVIZIO NOME_APPLICAZIONE [-f, --force]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina il bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app`:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Elenca le chiavi dell'istanza o dell'alias del servizio

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NOME | --alias-id ID | --alias-name NOME ]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID istanza del servizio</dd>
  <dt>--instance-name</dt>
  <dd>Nome istanza del servizio</dd>
  <dt>--alias-id</dt>
  <dd>ID alias del servizio</dd>
  <dt>--alias-name</dt>
  <dd>Nome alias del servizio</dd>
</dl>

<strong>Esempi</strong>:
Elenca le chiavi dell'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Mostra i dettagli di una chiave del servizio

```
ibmcloud resource service-key NOME_CHIAVE [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE</dt>
  <dd>Nome della chiave</dd>
  <dt>--id</dt>
  <dd>Visualizza l'ID della chiave del servizio</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli delle chiavi del servizio `my-service-key`:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crea una chiave del servizio

```
ibmcloud resource service-key-create NOME NOME_RUOLO ( --instance-id ID_ISTANZA_SERVIZIO | --instance-name NOME_ISTANZA_SERVIZIO | --alias-id ID_ALIAS_SERVIZIO | --alias-name NOME_ALIAS_SERVIZIO ) [--service-id ID_SERVIZIO] [-p, --parameters @FILE_JSON | TESTO_JSON] [-f, --force]]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME</dt>
  <dd>Nome della chiave</dd>
  <dt>NOME_RUOLO</dt>
  <dd>Nome del ruolo utente</dd>
  <dt>--instance-id</dt>
  <dd>ID istanza del servizio</dd>
  <dt>--instance-name</dt>
  <dd>Nome istanza del servizio</dd>
  <dt>--alias-id</dt>
  <dd>ID alias del servizio</dd>
  <dt>--alias-name</dt>
  <dd>Nome alias del servizio</dd>
  <dt>--service-id</dt>
  <dd>Nome o UUID dell'ID del servizio a cui appartiene il ruolo</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Crea una chiave del servizio denominata `my-service-key` con il ruolo `Administrator` per l'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Elimina una chiave del servizio

```
ibmcloud resource service-key-delete NOME_CHIAVE [-f, --forece]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE</dt>
  <dd>Nome della chiave</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina la chiave del servizio `my-service-key`:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Elenca gli alias per un'istanza del servizio

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NOME ]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID dell'istanza del servizio di appartenenza.</dd>
  <dt>--instance-name</dt>
  <dd>Nome dell'istanza del servizio di appartenenza.</dd>
</dl>

<strong>Esempi</strong>:
Elenca gli alias per l'istanza del servizio `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostra i dettagli di un alias del servizio

```
ibmcloud resource service-alias NOME_ALIAS [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>--id</dt>
  <dd>Visualizza solo l'ID dell'alias del servizio fornito. Tutto l'altro output per l'alias viene eliminato.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli dell'alias del servizio `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crea un alias di un'istanza del servizio

```
ibmcloud resource service-alias-create NOME_ALIAS ( --instance-id ID | --instance-name NOME ) [-s NOME_SPAZIO] [-t, --tags TAG] [-p, --parameters @FILE_JSON | TESTO_JSON]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>--instance-id</dt>
  <dd>ID dell'istanza del servizio di appartenenza.</dd>
  <dt>--instance-name</dt>
  <dd>Nome dell'istanza del servizio di appartenenza.</dd>
  <dt>-s</dt>
  <dd>Nome dello spazio in cui l'alias viene creato. Il valore predefinito è lo spazio corrente.</dd>
  <dt>-t, --tags</dt>
  <dd>Elenco delle tag.</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri.</dd>
</dl>

<strong>Esempi</strong>:
Crea un alias del servizio denominato `my-service-alias` dell'istanza del servizio `my-service-instance`:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Aggiorna un alias del servizio

```
ibmcloud resource service-alias-update NOME_ALIAS [-n, --name NUOVO_NOME] [-t, --tags TAG] [-p, --parameters @FILE_JSON | STRINGA_JSON ][-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome dell'alias del servizio.</dd>
  <dt>-t, --tags</dt>
  <dd>Elenco delle tag.</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri.</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma dell'utente.</dd>
</dl>

<strong>Esempi</strong>:
Aggiorna l'alias del servizio `my-service-alias`, modifica il suo nome in `new-service-alias`:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Elimina un alias del servizio

```
ibmcloud resource service-alias-delete NOME_ALIAS [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina l'alias del servizio `my-service-alias`:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Ricerca le risorse utilizzando la sintassi di query Lucene

```
ibmcloud search QUERY_LUCENE [-o, --offset OFFSET] [-l, --limit LIMITE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-offset, --o</dt>
  <dd>Avvio numero posizione risorsa</dd>
  <dt>-limit, --l</dt>
  <dd>Numero di risorse da restituire (massimo 10000)</dd>
</dl>

<strong>Esempi</strong>:
Ricerca le applicazioni Cloud Foundry i cui nomi iniziano con un testo specifico:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Ricerca le istanze del servizio Cloud Foundry del servizio del nome servizio specificato:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Ricerca i bind del servizio Cloud Foundry nell'organizzazione con l'ID specificato:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Ricerca gli spazi Cloud Foundry con il nome specificato e ubicati in una delle due regioni specificate:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Ricerca le risorse il cui nome contiene la parola dev nello spazio Cloud Foundry con l'ID specificato:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Ricerca le risorse del controller delle risorse nell'ubicazione specificata (ad esempio la regione us-south):

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Ricerca le risorse o gli alias nel gruppo di risorse con l'ID specificato:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Ricerca i gruppi di risorse con il nome predefinito:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Ricerca i bind della risorsa per il nome servizio specificato:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Ricerca una risorsa con il CRN (Cloud Resource Name) specificato:

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Ricerca una risorsa con la tag specificata:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Elenca tutte le tag

```
ibmcloud resource tags [--tag-type TIPO_TAG] [-o, --offset OFFSET] [-l, --limit LIMITE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Il tipo di tag (valori supportati: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>Numero posizione risorsa iniziale (valore predefinito: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Numero di risorse da restituire (massimo 10000) (valore predefinito: 10000)</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le tag

```
ibmcloud resource tags
```

Elenca tutte le tag limitate

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Mostra i dettagli di una tag

```
ibmcloud resource tag (--tag-name NOME_TAG | --tag-crn CRN_TAG)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della tag "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Crea una tag

```
ibmcloud resource tag-create --tag-name NOME_TAG [--tag-type TIPO_TAG]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag</dd>
  <dt>--tag-type</dt>
  <dd>Tipo di tag (valori supportati: user, restricted; default: user)</dd>
</dl>

<strong>Esempi</strong>:

Crea una tag utente con il nome think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Crea una tag limitata con il nome department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Crea una tag utente con il nome "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Crea una tag limitata con il nome "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Elimina una tag

```
ibmcloud resource tag-delete (--tag-name NOME_TAG | --tag-crn CRN_TAG)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
</dl>

<strong>Esempi</strong>:

Elimina la tag "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Aggiungi una tag a una risorsa

```
ibmcloud resource tag-attach (--tag-name NOME_TAG | --tag-crn CRN_TAG ) --resource-crn CRN_RISORSA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--resource-crn (obbligatorio)</dt>
  <dd>CRN risorsa</dd>
</dl>

<strong>Esempi</strong>:

Aggiungi la tag "Ray Brown" alla risorse il cui crn è resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Rimuovi una tag da una risorsa

```
ibmcloud  tag-detach (--tag-name NOME_TAG | --tag-crn CRN_TAG) --resource-crn CRN_RISORSA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--resource-crn (obbligatorio)</dt>
  <dd>CRN risorsa</dd>
</dl>

<strong>Esempi</strong>:

Rimuovi la tag "Ray Brown" dalla risorse il cui crn è resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Commuta la tag utente alla tag limitata e viceversa

```
ibmcloud tag-update (--tag-name NOME_TAG | --tag-crn CRN_TAG) --tag-type TIPO_TAG
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--tag-type (obbligatorio)</dt>
  <dd>Tipo di tag</dd>
</dl>

<strong>Esempi</strong>:

Commuta la tag "Ray Brown" alla tag limitata

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```


## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Cerca voci del catalogo

```
ibmcloud catalog search <QUERY> [-r, --region REGIONE] [-k, --kind TIPO] [-p, --price PREZZO] [-t, --tag TAG] [--sort-by PROPRIETÀ] [--col COLONNE] [--reverse] [--json] [--csv] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Specifica la regione geografica in cui cercare. Attualmente sono supportate solo "us-south" e "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>Filtra in base al tipo di risorse. Attualmente sono supportati solo "service-cf", "iaas", "runtime", "template" e "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>Filtra in base al prezzo. Attualmente sono supportati solo "free", "paygo" e "bluemix-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>Filtra in base alla tag.</dd>
  <dt>--sort-by</dt>
  <dd>Proprietà in base a cui ordinare</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags"</dd>
  <dt>--reverse</dt>
  <dd>Indica se invertire la sequenza di ordinamento</dd>
  <dt>--json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>--csv</dt>
  <dd>File CSV di output</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Cerca il servizio `Automation test`:

```
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Ottiene una voce di catalogo

```
ibmcloud catalog entry ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--children</dt>
  <dd>Ottieni tutti gli elementi secondari per la voce di catalogo</dd>
  <dt>--json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Ottieni la voce con ID `a0ef1-d3b4j0`:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Crea una nuova voce di catalogo (solo amministratore catalogo di un account)

```
ibmcloud catalog entry-create [-c PARAMETERI_COME_JSON] [-p, --parent ELEMENTO_PRINCIPALE] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>ID elemento principale dell'oggetto</dd>
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Crea risorsa dal file JSON con l'ID di elemento principale `a0ef1-d3b4j0`:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Aggiorna una voce di catalogo esistente (solo editor o amministratore di catalogo di un account)

```
ibmcloud catalog entry-update ID [-c PARAMETRI_COME_JSON] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la risorsa `j402-dnf1i` dal file JSON:

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Elimina una voce di catalogo (solo amministratore di catalogo di un account)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Elimina risorsa `j402-dnf1i`:

```
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Ottieni la visibilità per una voce di catalogo (solo amministratore di catalogo di un account)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>-json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>-global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Ottiene la visibilità della risorsa `j402-dnf1i` in ambito globale:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Aggiorna la visibilità di una voce di catalogo esistente (solo amministratore di catalogo di un account)

```
ibmcloud catalog entry-visibility-set ID [--includes-add ELENCO] [--includes-remove ELENCO] [--excludes-add ELENCO] [--excludes-remove ELENCO] [--owner ID o Email] [--restrict] [--unrestrict] [-c PARAMETRI_COME_JSON] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Aggiunta di un account (o elenco di account separati da virgole) all'elenco di inclusione, concedendo la visibilità alla voce. GUID Email o Account sono accettabili</dd>
  <dt>--includes-remove</dt>
  <dd>Rimozione di un account (o elenco di account separati da virgole) dall'elenco di inclusione, revocando la visibilità alla voce. GUID Email o Account sono accettabili</dd>  
  <dt>--excludes-add</dt>
  <dd>Aggiunta di un account (o elenco di account separati da virgole) all'elenco di esclusione. GUID Email o Account sono accettabili</dd>
  <dt>--excludes-remove</dt>
  <dd>Rimozione di un account (o elenco di account separati da virgole) dall'elenco di esclusione, revocando la visibilità alla voce. Se l'account è stato impostato dagli amministratori globali, gli amministratori dell'account non possono rimuovere l'account. GUID Email o Account sono accettabili</dd>
  <dt>--owner</dt>
  <dd>Modifica del proprietario di un oggetto. GUID Email o Account sono accettabili.</dd>
  <dt>--restrict</dt>
  <dd>Modifica della restrizione della visibilità dell'oggetto su 'Privato'</dd>
  <dt>--unrestrict</dt>
  <dd>Modifica della restrizione della visibilità dell'oggetto su 'Pubblico'</dd>  
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Imposta la visibilità della risorsa `j402-dnf1i` dal file JSON:

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Elenca le offerte di servizio nel marketplace

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Mostra solo i servizi Cloud Foundry</dd>
  <dt>--rc</dt>
  <dd>Mostra solo i servizi compatibili con RC</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Mostra le offerte del servizio in ambito globale:

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualizza i modelli di contenitore tipo su {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-d (facoltativo)</dt>
   <dd>Se viene specificata l'opzione <i>-d</i>, viene visualizzata anche la descrizione di ciascun modello. Altrimenti, vengono visualizzati solo l'ID e il nome di ciascun modello.</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Visualizza le informazioni dettagliate di un modello contenitore tipo specificato.

```
ibmcloud catalog template ID_MODELLO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ID_MODELLO (obbligatorio)</dt>
   <dd>L'ID del modello contenitore tipo. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i modelli.</dd>
   </dl>


<strong>Esempi</strong>:

Visualizza i dettagli del modello `mobileBackendStarter`:

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crea un'applicazione cf basata sul modello specificato con l'URL e la descrizione specificati. Per impostazione predefinita, la nuova applicazione viene avviata automaticamente.

```
ibmcloud catalog template-run ID_MODELLO NOME_APPLICAZIONE_CF [-u URL] [-d DESCRIZIONE] [--no-start]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ID_MODELLO (obbligatorio)</dt>
   <dd>Il modello su cui verrà basata l'applicazione quando verrà creata. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i modelli.</dd>
   <dt>NOME_APPLICAZIONE_CF (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf da creare.</dd>
   <dt>-u <i>URL</i> (facoltativo)</dt>
   <dd>La rotta dell'applicazione. Se non specificata, la rotta viene impostata automaticamente da {{site.data.keyword.Bluemix_notm}} in base al nome della tua applicazione e al dominio predefinito.</dd>
   <dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
   <dd>Descrizione dell'applicazione.</dd>
   <dt>--no-start (facoltativo)</dt>
   <dd>Non avviare l'applicazione automaticamente una volta creata. Se non viene specificata, l'applicazione viene avviata automaticamente dopo la sua creazione.</dd>
   </dl>


<strong>Esempi</strong>:

Crea un'applicazione `my-app` basata sul modello `javaHelloWorld`:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Crea un'applicazione `my-ruby-app` basata sul modello `rubyHelloWorld` con la rotta `myrubyapp.chinabluemix.net` e la descrizione `La mia prima applicazione ruby su {{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crea un'applicazione `my-python-app` basata sul modello `pythonHelloWorld` senza l'avvio automatico:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ottieni un sottoinsieme scelto di regioni nel formato di tua scelta.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind TIPO] [--col COLONNE] [--json] [--global] [--csv]
```

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Specifica l'area geografica per ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Ottieni un elenco di voci per il tipo specificato.</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags".</dd>
  <dt>--json</dt>
  <dd>Output della risposta JSON originale.</dd>
  <dt>--global</dt>
  <dd>Opera in un ambito globale.</dd>
  <dt>--csv</dt>
  <dd>File CSV di output</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Visualizza i dettagli di un runtime. Questo comando è disponibile solo per il cloud pubblico.

```
ibmcloud catalog runtime ID_RUNTIME
```

<strong>Esempi</strong>:

Mostra i dettagli del runtime "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Elenca tutti i runtime. Questo comando è disponibile solo per il cloud pubblico.

```
ibmcloud catalog runtimes [-d]
```

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-d</dt>
  <dd>Mostra la descrizione di ogni runtime</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i runtime con le loro descrizioni:

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostra l'utilizzo mensile dell'account corrente (solo amministratore dell'account)

```
ibmcloud billing account-usage [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

<strong>Esempi</strong>:

Mostra il report su costo e utilizzo dell'account corrente per 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostra l'utilizzo mensile di un'organizzazione (solo il gestore della fatturazione dell'organizzazione o l'amministratore dell'account)

```
ibmcloud billing org-usage NOME_ORGANIZZAZIONE [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
  <dd>Nome dell'organizzazione.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostra l'utilizzo mensile di un gruppo di risorse (solo l'amministratore del gruppo di risorse o l'amministratore dell'account)

```
ibmcloud billing resource-group-usage NOME_GRUPPO [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>GROUP_NAME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostra l'utilizzo mensile delle istanze della risorsa nell'account corrente.

```
ibmcloud billing resource-instances-usage [-o ORGANIZZAZIONE] [-g GRUPPO_RISORSE] [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-o NOME_ORGANIZZAZIONE (facoltativo)</dt>
  <dd>Filtra istanze per organizzazione.</dd>
  <dt>-g NOME_GRUPPO</dt>
  <dd>Filtra istanza per gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata tramite l'utilizzo nel formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Elenca tutti i repository di plug-in registrati nella CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Prerequisiti</strong>:  Nessuno


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Aggiungi un nuovo repository di plug-in alla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add NOME_REPOSITORY URL_REPOSITORY
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da aggiungere. Puoi definire un tuo nome per ciascun repository.</dd>
   <dt>URL_REPOSITORY (obbligatorio)</dt>
   <dd>L'URL del repository da aggiungere. L'URL del repository deve contenere il protocollo (ad esempio, http://plugins.ng.bluemix.net invece di plugins.ng.bluemix.net). http://plugins.ng.bluemix.net è il repository di plug-in ufficiale della CLI {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Esempi</strong>:

Aggiungi il repository di plug-in ufficiale della CLI {{site.data.keyword.Bluemix_notm}} come `bluemix-repo`:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Rimuovi un repository di plug-in dalla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove NOME_REPOSITORY
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da rimuovere.</dd>
   </dl>

<strong>Esempi</strong>:

Rimuove il repository `bluemix-repo` dalla CLI {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Elenca tutti i plug-in disponibili in tutti i repository aggiunti o in uno specifico repository.

```
ibmcloud plugin repo-plugins [-r NOME_REPOSITORY]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Elenca solo i plug-in del repository specificato.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutti i plug-in in tutti i repository aggiunti:

```
ibmcloud plugin repo-plugins
```

Elenca tutti i plug-in nel repository `bluemix-repo`:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Mostra i dettagli di un plug-in nel repository.

```
ibmcloud plugin repo-plugin NOME_PLUGIN [-r NOME_REPOSITORY]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Il nome del repository. Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca i dettagli del plugin "IBM-Containers" nel repository "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Elenca i dettagli del plugin "IBM-Containers" nel repository predefinito.

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Elenca tutti i plug-in installati nella CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Visualizza i dettagli di un plugin installato.

```
ibmcloud plugin show NOME-PLUGIN
```

<strong>Prerequisiti</strong>:  Nessuno


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Installa la versione specifica del plug-in nella CLI {{site.data.keyword.Bluemix_notm}} dal percorso o repository specificato.

```
ibmcloud plugin install PERCORSO_PLUGIN|NOME_PLUGIN [-r NOME_REPOSITORY] [-v VERSIONE]
```

```
ibmcloud plugin install PERCORSO-LOCALE/A/PLUGIN | URL [-f]
```

Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.
Se non viene specificata alcuna versione, il comando seleziona l'ultima versione disponibile da installare.

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>PERCORSO_PLUGIN|NOME_PLUGIN (obbligatorio)</dt>
   <dd>Se -r <i>NOME_REPOSITORY</i> non viene specificato, il plug-in viene installato dal percorso locale o dall'URL remoto specificato.</dd>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Il nome del repository in cui si trova il file binario del plug-in. Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.</dd>
   <dt>-v <i>VERSIONE</i> (facoltativo)</dt>
   <dd>La versione del plug-in da installare. Se non fornita, viene installata l'ultima versione del plug-in. Questa opzione è valida solo quando si installa il plug-in dal repository.</dd>
   <dt>-f </dt>
   <dd>Forza l'installazione del plug-in senza conferma.</dd>
    </dl>


La CLI {{site.data.keyword.Bluemix_notm}} ha il nome repository ufficiale di `Bluemix`.

<strong>Esempi</strong>:

Installa un plug-in dal file locale:

```
ibmcloud plugin install /downloads/new_plugin
```

Installa un plug-in dall'URL remoto:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Installa il plug-in 'container-service' dell'ultima versione dal repository 'Bluemix':

```
ibmcloud plugin install container-service -r Bluemix
```

o semplicemente:

```
ibmcloud plugin install container-service
```

Installa il plug-in 'container-service' con la versione '0.1.425' dal repository di plugin ufficiale:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Aggiorna il plug-in da un repository.

```
ibmcloud plugin update [NOME PLUGIN] [-r NOME_REPOSITORY] [-v VERSIONE] [--all]
```

Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.
Se non viene specificata alcuna versione, il comando seleziona l'ultima versione disponibile da installare.

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
 <dt>NOME PLUGIN</dt>
 <dd>Nome del plug-in da aggiornare. Se non specificato, il comando ricerca gli aggiornamenti per tutti i plug-in installati.</dd>
 <dt>-r NOME_REPOSITORY</dt>
 <dd>Il nome del repository in cui si trova il file binario del plug-in. Se non specificato, il comando utilizza il repository di plugin predefinito 'Bluemix'.</dd>
 <dt>-v <i>VERSIONE</i> (facoltativo)</dt>
 <dd>La versione a cui aggiornare il plug-in. Se non viene fornita, aggiorna il plug-in all'ultima versione disponibile.</dd>
 <dt>--all</dt>
 <dd>Aggiorna tutti i plug-in disponibili.</dd>
</dl>

<strong>Esempi</strong>:

controlla tutti gli aggiornamenti disponibili nel repository di plugin 'Bluemix':

```
ibmcloud plugin update -r Bluemix
```

o semplicemente:

```
ibmcloud plugin update
```

Aggiorna il plug-in 'container-service' nel repository di plug-in ufficiale all'ultima versione:

```
ibmcloud plugin update container-service
```

Aggiorna il plug-in 'container-service' nel repository di plug-in ufficiale alla versione '0.1.440':

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Disinstalla il plug-in specificato dalla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall NOME_PLUGIN
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_PLUGIN (obbligatorio)</dt>
   <dd>Il nome del plug-in da disinstallare.</dd>
    </dl>

<strong>Esempi</strong>:

Disinstalla il plug-in 'container-service' precedentemente installato:

```
ibmcloud plugin uninstall container-service
```

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Elenca gli ambienti CFEE.

```
bx cfee environments
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostra i dettagli di un ambiente CFEE.

```
bx cfee environment NOME [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostra solo l'ID.</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di un ambiente CFEE env_example:

```
bx cfee environment env_example
```

Mostra l'ID di un ambiente CFEE env_example:

```
bx cfee environment env_example --id
```
