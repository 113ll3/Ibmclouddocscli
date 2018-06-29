---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-18"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}}-Befehle (ibmcloud)
{: #bluemix_cli}

Version: 0.7.1

Von der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI) werden Befehle bereitgestellt, die nach Namensbereich für Benutzer zur Interaktion mit {{site.data.keyword.Bluemix_notm}} zusammengefasst sind.

Ab Version 0.5.0 enthält die Installation des {{site.data.keyword.Bluemix_notm}}-Befehlszeilenclients einen Cloud Foundry-Befehlszeilenclient. Wenn Sie eine eigene Cloud Foundry-Befehlszeilenschnittstelle installiert haben, dann verwenden Sie die Befehle der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI) vom Typ `ibmcloud [command]` und die Befehle der Cloud Foundry-Befehlszeilenschnittstelle (CLI) vom Typ `cf [command]` Ihrer eigenen Installation nicht in demselben Kontext. Verwenden Sie stattdessen  `ibmcloud cf [command]`, wenn Sie Cloud Foundry-Ressourcen mit der Cloud Foundry-Befehlszeilenschnittstelle (CF-CLI) im Kontext der {{site.data.keyword.Bluemix_notm}}-CLI verwalten wollen.  Beachten Sie, dass `ibmcloud cf api/login/logout/target` nicht zulässig ist und Sie stattdessen `ibmcloud api/login/logout/target` verwenden müssen.

Ab Mai 2018 wird an Stelle der {{site.data.keyword.Bluemix_notm}}-CLI-Befehle `bluemix` und `bx` künftig der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch auch weiterhin noch so lange verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

In der nachfolgenden Liste finden Sie detaillierte Angaben zu den von der {{site.data.keyword.Bluemix_notm}}-CLI unterstützten Befehlen mit zugehörigen Namen, Argumenten, Optionen, Voraussetzungen, Beschreibungen und Beispielen.
{:shortdesc}

**Hinweis:** Unter *Voraussetzungen* wird aufgelistet, welche Aktionen vor der Verwendung des Befehls ausgeführt werden müssen. Für Befehle, für die keine Voraussetzungen erfüllt sein müssen, ist **Keine** angegeben. Andernfalls kann mindestens eine der folgenden Aktionen eine Voraussetzung sein:

<dl>
<dt>Endpunkt</dt>
<dd>Vor dem Verwenden des Befehls muss ein API-Endpunkt durch Absetzen des Befehls <code>bluemix api</code> definiert werden.</dd>
<dt>Anmeldung</dt>
<dd>Vor der Verwendung des Befehls ist die Anmeldung über den Befehl <code>bluemix login</code> erforderlich.
Verwenden Sie beim Anmelden mit einer eingebundenen ID die Option '--sso' für die Anmeldung mit einmaligem Kenncode oder verwenden Sie die Option '--apikey' für die Authentifizierung mit einem API-Schlüssel. Wechseln Sie in der {{site.data.keyword.Bluemix_notm}}-Konsole zum Erstellen von API-Schlüsseln zu **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel**.
</dd>
<dt>Ziel</dt>
<dd>Vor dem Verwenden des Befehls muss der Befehl <code>bluemix target</code> zum Definieren einer Organisation und eines Bereichs ausgeführt werden.</dd>
<dt>Docker</dt>
<dd>Die Docker-CLI (docker) muss installiert werden, um diesen Befehl auszuführen.</dd>
</dl>


Verwenden Sie die Indizes in den folgenden Tabellen als Referenz für die häufig verwendeten ibmcloud-Befehle.

## Allgemeine ibmcloud-Befehle
{: #bx_commands_index}

<table summary="Allgemeine ibmcloud-Befehle">
<caption>Tabelle 1. Allgemeine ibmcloud-Befehle</caption>
 <thead>
 <th colspan="5">Allgemeine ibmcloud-Befehle</th>
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

 ## Befehle zur Verwaltung und Konfiguration von Infrastrukturservices für {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
  {: #bx_commands_softlayer}

Die Befehle zur Verwaltung der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} wurden in die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle integriert. Weitere Informationen zur Verwendung der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle zum Konfigurieren und Verwalten der Infrastrukturservices für {{site.data.keyword.BluSoftlayer_notm}} finden Sie im Abschnitt zu [{{site.data.keyword.Bluemix_notm}}-CLI - Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html#softlayer_cli).

 ## Befehle zur Verwaltung von Konten, Organisationen und Rollen
 {: #bx_commands_account}

<table summary="ibmcloud-Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen.">
<caption>Tabelle 2. Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen</th>
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


 ## Befehle zur Verwaltung von Ressourcengruppen und Ressourcen
{: #bx_commands_resource}

<table summary="ibmcloud-Befehle zur Verwaltung von Ressourcengruppen und Ressourcen.">
  <caption>Tabelle 3. Befehle zur Verwaltung von Ressourcengruppen und Ressourcen</caption>
  <thead>
    <th colspan="5">Befehle zur Verwaltung von Ressourcengruppen und Ressourcen</th>
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


 ## Befehle zur Verwaltung von API-Schlüsseln und Richtlinien
 {: #bx_commands_iam}
 <table summary="ibmcloud-Befehle zur Verwaltung von API-Schlüsseln und Richtlinien.">
 <caption>Tabelle 4. Befehle zur Verwaltung von API-Schlüsseln und Richtlinien</caption>
  <thead>
  <th colspan="5">Befehle zur Verwaltung von API-Schlüsseln und Richtlinien</th>
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

 ## Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps
 {: #bx_commands_apps}

<table summary="ibmcloud-Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps.">
<caption>Tabelle 5. Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</th>
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

 ## Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services
 {: #bx_commands_services}

<table summary="ibmcloud-Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services.">
<caption>Tabelle 6. Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services</th>
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


 ## Befehle zur Verwaltung von Katalogen, Plug-ins und Einstellungen für die Abrechnung
 {: #bx_commands_settings}

<table summary="ibmcloud-Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit.">
<caption>Tabelle 7. Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</th>
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

 ## Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)
{: #bx_commands_cfee}

<table summary="Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)">
<caption>Tabelle 8. Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)</caption>
 <thead>
 <th colspan="5">Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)</th>
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
Zeigt die erweiterte Hilfe für integrierte Befehle und unterstützte Namensbereiche der obersten Ebene in der {{site.data.keyword.Bluemix_notm}}-CLI oder die Hilfe für einen bestimmten integrierten Befehl oder Namensbereich an.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>COMMAND|NAMESPACE (optional)</dt>
   <dd>Der Befehl oder Namensbereich, für den die Hilfe angezeigt wird. Wenn nichts angegeben ist, wird die erweiterte Hilfe für die {{site.data.keyword.Bluemix_notm}}-CLI angezeigt.</dd>
   </dl>



<strong>Beispiele</strong>:

Erweiterte Hilfe für die {{site.data.keyword.Bluemix_notm}}-CLI anzeigen:

```
ibmcloud help
```

Hilfe für den Befehl `info` anzeigen:

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
{{site.data.keyword.Bluemix_notm}}-API-Endpunkt festlegen oder anzeigen.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>API_ENDPOINT (optional)</dt>
   <dd>Der API-Endpunkt, der als Ziel verwendet wird, zum Beispiel `https://api.chinabluemix.net`. Wenn weder die Option *API_ENDPOINT* noch die Option `--unset` angegeben wird, wird der aktuelle API-Endpunkt angezeigt.</dd>
   <dt>--unset (optional)</dt>
   <dd>Entfernt die Einstellung für den API-Endpunkt.</dd>
   <dt>--skip-ssl-validation (optional)</dt>
   <dd>Umgeht die SSL-Validierung von HTTP-Anforderungen.</dd>
   </dl>
<strong>Beispiele</strong>:

Für den API-Endpunkt api.chinabluemix.net festlegen:

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

Aktuellen API-Endpunkt anzeigen:

```
ibmcloud api
```

Definition für den API-Endpunkt rückgängig machen:

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


Standardwerte in die Konfigurationsdatei schreiben.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Der Zeitlimitwert für HTTP-Anforderungen. Der Standardwert ist 60 Sekunden.</dd>
   <dt>--trace true|false|<i>Dateipfad</i></dt>
   <dd>Trace für HTTP-Anforderungen mit Ausgabe auf Terminal oder in angegebener Datei aktivieren.</dd>
   <dt>--color true|false</dt>
   <dd>Farbausgabe aktivieren oder inaktivieren. Die Farbausgabe ist standardmäßig aktiviert.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Eine Standardländereinstellung festlegen. Wenn LOCALE den Wert <i>CLEAR</i> hat, wird die vorherige Ländereinstellung gelöscht.</dd>
   <dt>--check-version true|false</dt>
   <dd>CLI-Versionsprüfung aktivieren oder inaktivieren.</dd>
   </dl>

Es kann jeweils nur eine dieser Optionen gleichzeitig angegeben werden.

<strong>Beispiele</strong>:

HTTP-Anforderungszeitlimit auf 30 Sekunden setzen:

```
ibmcloud config --http-timeout 30
```

Traceausgabe für HTTP-Anforderungen aktivieren:

```
ibmcloud config --trace true
```

Traceausgabe für HTTP-Anforderungen in eine angegebene Datei */home/usera/my_trace* schreiben:

```
ibmcloud config --trace /home/usera/my_trace
```

Farbausgabe inaktivieren:

```
ibmcloud config --color false
```

Ländereinstellung auf 'zh_Hans' setzen:

```
ibmcloud config --locale zh_Hans
```

Ländereinstellungen löschen:

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

{{site.data.keyword.Bluemix_notm}}-Basisinformationen einschließlich aktueller Region, Cloud-Controller-Version und einigen nützlichen Endpunkten (zum Beispiel zum Anmelden und Austauschen von Zugriffstoken) anzeigen.

```
ibmcloud info
```

<strong>Voraussetzungen</strong>: Endpunkt


## ibmcloud cf
{: #ibmcloud_cf}

Eingebettete CF-CLI aufrufen

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
<dl>
  <dt>-q, --quiet</dt>
  <dd>Nachricht "Befehl cf wird aufgerufen..." inaktivieren</dd>
</dl>

<strong>Beispiele</strong>:

CF-Apps auflisten

```
ibmcloud cf apps
```

CF-Services ohne Nachricht "Befehl cf wird aufgerufen..." auflisten:

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

Benutzer anmelden.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>Voraussetzungen</strong>: Keine

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Befehlsoptionen:</strong>
<dl>
  <dt> -a <i>API_ENDPOINT</i> (optional)</dt>
  <dd> API-Endpunkt (z. B.: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY oder @API_KEY_FILE_PATH</i>
  <dd> API-Schlüsselinhalt oder der Pfad einer API-Schlüsseldatei, die durch @ angegeben wird.</dd>
  <dt> --sso (optional) </dt>
  <dd> Einmaligen Kenncode zum Anmelden verwenden. </dd>
  <dt> -u <i>USERNAME</i> (optional)</dt>
  <dd> Der Benutzername.</dd>
  <dt> -p <i>PASSWORD</i> (optional)</dt>
  <dd> Das Kennwort.</dd>
  <dt> -c <i>ACCOUNT_ID</i> (optional) </dt>
  <dd> Die ID des Zielkontos.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional) </dt>
  <dd> Der Name der Zielressourcengruppe</dd>
  <dt> -o <i>ORG</i> (optional)</dt>
  <dd> Der Name der Zielorganisation (veraltet, 'ibmcloud target -o ORG' verwenden)</dd>
  <dt> -s <i>SPACE</i> (optional) </dt>
  <dd> Der Name des Zielbereichs (veraltet, 'ibmcloud target -s SPACE' verwenden)</dd>
  <dt> --no-iam </dt>
  <dd> Authentifizierung beim Anmeldeserver anstatt beim öffentlichen IAM erzwingen</dd>
  <dt> --skip-ssl-validation (optional) </dt>
  <dd> Umgeht die SSL-Validierung von HTTP-Anforderungen. Diese Option wird nicht empfohlen.</dd>
</dl>

<strong>Beispiele</strong>:

#### Interaktive Anmeldung

```
ibmcloud login
```

Anmeldung mit einem Benutzernamen und einem Kennwort und Festlegen des Kontos, der Organisation und des Bereichs:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Anmeldung mit einmaligem Kenncode und Festlegen eines Zielkontos, einer Organisation und eines Bereichs:

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Anmeldung mit API-Schlüssel und Festlegen von Zielen:

#### API-Schlüssel hat zugeordnetes Konto.

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API-Schlüssel hat kein zugeordnetes Konto.

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Hinweis:</strong> Wenn der API-Schlüssel ein zugeordnetes Konto hat, ist ein Wechsel zu einem anderen Konto nicht zulässig.

#### Einmaligen Kenncode verwenden

```
ibmcloud login -u UserID --sso
```

Anschließend stellt die Befehlszeilenschnittstelle einen URL-Link bereit und fordert zur Eingabe eines Kenncodes auf:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Öffnen Sie im Browser den Link, der Sie zu dem Kenncode führt. Wenn Sie an der Konsole den angegebenen Kenncode eingeben, sollten Sie in der Lage sein, sich anmelden.

## ibmcloud logout
{: #ibmcloud_logout}

Benutzer abmelden.

```
ibmcloud logout
```

<strong>Voraussetzungen</strong>: Keine

## ibmcloud regions
{: #ibmcloud_regions}

Zeigt die Informationen für alle Regionen in {{site.data.keyword.Bluemix_notm}} an.

```
ibmcloud regions
```

<strong>Voraussetzungen</strong>: Endpunkt


## ibmcloud target
{: #ibmcloud_target}


Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>-r <i>REGION_NAME</i> (optional)</dt>
   <dd>Der Name der Region, in die gewechselt werden soll, z. B. 'us-south' oder 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (optional)</dt>
   <dd>Die ID des Zielkontos.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (optional)</dt>
   <dd>Der Name der Ressourcengruppe.</dd>
   <dt>--cf</dt>
   <dd>Interaktive Auswahl der Zielorganisation und des Zielbereichs</dd>
   <dt>-o <i>ORG_NAME</i> (optional)</dt>
   <dd>Der Name der Zielorganisation.</dd>
   <dt>-s <i>SPACE_NAME</i> (optional)</dt>
   <dd>Der Name des Zielbereichs.</dd>
   </dl>
Wenn keine der Optionen angegeben wird, werden das aktuelle Konto, die aktuelle Region, die aktuelle Organisation und der aktuelle Bereich angezeigt.

<strong>Beispiele</strong>:

Aktuelles Konto, aktuelle Organisation und aktuellen Bereich festlegen:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Zu einer neuen Region wechseln:

```
ibmcloud target -r eu-gb
```

Aktuelles Konto, aktuelle Region, aktuelle Organisation und aktuellen Bereich anzeigen:

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

Die Befehlszeilenschnittstelle auf die neueste Version aktualisieren.

```
ibmcloud update [-f]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
<dl>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen. Rootberechtigung ist erforderlich.</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Alle Organisationen auflisten

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>-r <i>REGION</i> (optional)</dt>
   <dd>Für welche Region die Organisationsinformationen angezeigt werden sollen. Wenn 'all' angegeben ist, werden alle Organisationen in allen Regionen aufgelistet.</dd>
   <dt>--guid (optional)</dt>
   <dd>GUID der Organisationen anzeigen.</dd>
   </dl>

<strong>Beispiele</strong>:

Alle Organisationen in der Region: `us-south` auflisten und GUID anzeigen

```
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

Die Informationen für die angegebene Organisation anzeigen

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>--guid (optional)</dt>
   <dd>GUID der Organisationen anzeigen.</dd>
   </dl>

<strong>Beispiele</strong>:

Informationen für die Organisation `IBM` mit der GUID anzeigen

```
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Eine neue Organisation erstellen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, die erstellt wird.</dd>
   <dt>-f</dt>
   <dd>Erstellung ohne Bestätigung erzwingen.</dd>
   </dl>

<strong>Beispiele</strong>:

Organisation mit dem Namen `IBM` erstellen:

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Repliziert eine Organisation aus der aktuellen Region in eine andere Region.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der vorhandenen Organisation, die repliziert werden soll.</dd>
   <dt>REGION_NAME (erforderlich)</dt>
   <dd>Der Name der Region, die die replizierte Organisation hostet.</dd>
   </dl>

<strong>Beispiele</strong>:

Die Organisation `myorg` in die Region `eu-gb` replizieren:

```
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Eine Organisation umbenennen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>OLD_ORG_NAME (erforderlich)</dt>
   <dd>Der bisherige Name der Organisation, die umbenannt werden soll.</dd>
   <dt>NEW_ORG_NAME (erforderlich)</dt>
   <dd>Der neue Name für die Organisation, die umbenannt werden soll.</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Alle Bereiche auflisten

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>-o</dt>
   <dd>Organisationsname. Die Bereiche unter der angegebenen Organisation auflisten. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-r</dt>
   <dd>Regionsname. Die Bereiche unter der angegebenen Region auflisten. Standardmäßig wird die aktuelle Region verwendet, wenn keine Angabe gemacht wurde.</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Benutzer in der angegebenen Organisation nach Rolle anzeigen

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>ORG_NAME (erforderlich)</dt>
<dd>Der Name der Organisation.</dd>
<dt>-a (optional)</dt>
<dd>Alle Benutzer in der angegebenen Organisation auflisten (nicht nach Rolle gruppiert).</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Benutzer zur Organisation hinzufügen (Organisationsmanager erforderlich).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Benutzer aus der Organisation entfernen (Organisationsmanager oder nur Benutzer selbst)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--force, -f</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Alle Organisationsrollen des aktuellen Benutzers abrufen

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
  <dl>
   <dt>-u</dt>
   <dd>Benutzer-ID. Wenn keine Angabe erfolgt, wird standardmäßig der aktuelle Benutzer verwendet.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Einem Benutzer eine Organisationsrolle zuweisen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
  <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der zugeordnet wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugeordnet wird.</dd>
   <dt>ORG_ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, der dieser Benutzer zugeordnet wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
  </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` der Organisation `IBM` mit der Rolle `OrgManager` zuweisen:

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Hinweis:** Sie können die Organisations-/Bereichsrolle mithilfe der CLI festlegen; zum Festlegen der übrigen Berechtigungen müssen Sie jedoch die Benutzerschnittstelle verwenden. Weitere Informationen finden Sie in [Benutzerzugriff zuweisen](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Eine Organisationsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der entfernt wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>ORG_ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
    </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` aus der Organisation `IBM` und der Rolle `OrgManager` entfernen:

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Benutzer in dem angegebenen Bereich nach Rolle anzeigen

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Einem Benutzer eine Bereichsrolle zuweisen. Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der zugeordnet wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugeordnet wird.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs, dem dieser Benutzer zugeordnet wird.</dd>
   <dt>SPACE_ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, der dieser Benutzer zugeordnet wird. Beispiel:
   <ul>
   <li>Bereichsmanager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>Bereichsentwickler: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>Bereichsauditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
    </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` der Organisation `IBM` und dem Bereich `Cloud` mit der Rolle `SpaceManager` zuweisen:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Eine Bereichsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der entfernt wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs, aus dem dieser Benutzer entfernt wird.</dd>
   <dt>SPACE_ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
    </dl>


<strong>Beispiele</strong>:

Die Benutzerin `Mary` aus der Organisation `IBM` und dem Bereich `Cloud` mit der Rolle `SpaceManager` entfernen:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Alle Konten des aktuellen Benutzers auflisten

```
ibmcloud account list
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Das Konto der angegebenen Organisation anzeigen (Organisationsbenutzer erforderlich)

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
  <dt>--guid (optional)</dt>
  <dd>Nur die Konto-ID anzeigen</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

Dem Konto zugeordnete Benutzer anzeigen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Benutzer von einem Konto entfernen (nur Kontoeigner)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USER_ID (erforderlich)</dt>
<dd>Benutzer-ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Konto-ID. Wenn keine Angabe erfolgt, wird standardmäßig das aktuelle Konto verwendet.</dd>
<dt>-f, --force</dt>
<dd>Entfernen ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Benutzer für das Konto einladen

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der eingeladen wird.</dd>
   <dt>-o ORG</dt>
   <dd>Organisation, in die der Benutzer eingeladen werden soll</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Organisationsrolle. Gültige Eingabe: OrgManager, BillingManager, OrgAuditor und OrgUser. Wenn keine Angabe erfolgt, wird die Organisationsbenutzerrolle festgelegt.</dd>
   <dt>-s SPACE</dt>
   <dd>Bereich, in den der Benutzer eingeladen werden soll</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Bereichsrolle. Gültige Eingabe: SpaceManager, SpaceDeveloper und SpaceAuditor.</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Einladung erneut an einen Benutzer senden (Kontoadministrator)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der erneut eingeladen wird.</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Zugriffsgruppen unter dem aktuellen Konto auflisten

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-u</dt>
  <dd>Listet die Zugriffsgruppen auf, zu denen der Benutzer gehört. Dieses Flag wird ausschließlich mit '-s' verwendet.</dd>
  <dt>-s</dt>
  <dd>Listet die Zugriffsgruppen auf, zu denen die Service-ID gehört. Dieses Flag wird ausschließlich mit '-u' verwendet.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Zugriffsgruppen auflisten:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Details einer Zugriffsgruppe anzeigen

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-id</dt>
  <dd>Nur ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details der Zugriffsgruppe `example_group` anzeigen:

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Zugriffsgruppe erstellen

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Beschreibung der Zugriffsgruppe</dd>
</dl>

<strong>Beispiele</strong>:

Eine Zugriffsgruppe namens `example_group` erstellen:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Zugriffsgruppe aktualisieren

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Name der neuen Zugriffsgruppe</dd>
  <dt>-d, --description</dt>
  <dd>Neue Beschreibung</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppe `example_group` in `hello_world_group` umbenennen:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Zugriffsgruppe löschen

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
  <dt>-r, --recursive</dt>
  <dd>Zugriffsgruppe und deren Mitglieder löschen</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppe `example_group` löschen:

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Benutzer in einer Zugriffsgruppe auflisten

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Benutzer in der Zugriffsgruppe `example_group` auflisten:

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Benutzer zu einer Zugriffsgruppe hinzufügen

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` zur Zugriffsgruppe `example_group` hinzufügen:

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Benutzer aus einer Zugriffsgruppe entfernen

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` aus der Zugriffsgruppe `example_group` entfernen:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Benutzer aus allen Zugriffsgruppen entfernen

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` aus allen Zugriffsgruppen entfernen:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Service-IDs in einer Zugriffsgruppe auflisten

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Service-IDs in der Zugriffsgruppe `example_group` auflisten:

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Service-ID zu einer Zugriffsgruppe hinzufügen

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` zur Zugriffsgruppe `example_group` hinzufügen:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Service-ID aus einer Zugriffsgruppe entfernen

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` aus der Zugriffsgruppe `example_group` entfernen:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Service-ID aus allen Zugriffsgruppen entfernen

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` aus allen Zugriffsgruppen entfernen:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Richtlinien einer Zugriffsgruppe auflisten

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Richtlinien der Zugriffsgruppe `example_group` auflisten:

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Details einer Zugriffsgruppenrichtlinie anzeigen

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Details der Richtlinie `51b9717e-76b0-4f6a-bda7-b8132431f926` der Zugriffsgruppe `example_group` anzeigen:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Zugriffsgruppenrichtlinie erstellen

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition</dd>
  <dt>-roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-name'.</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppenrichtlinie aus einer JSON-Datei erstellen:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

`example_group` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`example_group` die Rolle `Editor` für die Ressource `key123` der Instanz `sample-service` mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`example_group` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

`example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Zugriffsgruppenrichtlinie aktualisieren

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition</dd>
  <dt>--roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-name'.</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppenrichtlinie mit der Richtlinie in der Richtlinien-JSON-Datei aktualisieren:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Editor` für die Ressource `key123` der Instanz `sample-service` mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Anzeigeberechtigter` für Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Zugriffsgruppenrichtlinie löschen

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `51b9717e-76b0-4f6a-bda7-b8132431f926` der Zugriffsgruppe `example_group` löschen:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Alle Service-IDs auflisten

```
ibmcloud iam service-ids [--uuid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Nur UUID der Service-IDs anzeigen</dd>
</dl>

<strong>Beispiele</strong>:
UUID aller Service-IDs des aktuellen Kontos auflisten

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Details einer Service-ID anzeigen

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>--uuid</dt>
  <dd>Die UUID der Service-ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details der Service-ID `sample-test` anzeigen

```
ibmcloud iam service-id sample-test
```
Details der Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` anzeigen

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Service-ID erstellen

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung der Service-ID</dd>
  <dt>--lock</dt>
  <dd>Die Service-ID bei der Erstellung sperren</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID mit dem Servicenamen `sample-test` und der Beschreibung `hello, world!` erstellen

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Gesperrte Service-ID mit dem Servicenamen `sample-test` und der Beschreibung `hello, world!` erstellen

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Service-ID aktualisieren

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Die neue Beschreibung des Service</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-test` ohne Bestätigung in `sample-test-2` umbenennen

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Beschreibung des Service `sample-test` aktualisieren

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` mit neuer Beschreibung in `sample-test-3` umbenennen

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Service-ID löschen

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-teset` ohne Bestätigung löschen

```
ibmcloud iam service-id-delete sample-teset -f
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` löschen

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Service-ID sperren

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-teset` ohne Bestätigung sperren

```
ibmcloud iam service-id-lock sample-teset -f
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` sperren

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Service-ID entsperren

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-teset` ohne Bestätigung entsperren

```
ibmcloud iam service-id-unlock sample-teset -f
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` entsperren

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Alle API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform auflisten

```
ibmcloud iam api-keys
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Neuen API-Schlüssel für {{site.data.keyword.Bluemix_notm}}-Plattform erstellen

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu erstellenden API-Schlüssels.</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die Beschreibung des API-Schlüssels</dd>
<dt>--file <i>FILE</i></dt>
<dd>Informationen zu API-Schlüssel in angegebener Datei speichern. Wenn nicht festgelegt, wird der JSON-Inhalt angezeigt.</dd>
<dt>--lock</dt>
<dd>API-Schlüssel bei der Erstellung sperren</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel erstellen und in einer Datei speichern

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Gesperrten API-Schlüssel mit dem Namen "test-key" erstellen

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform aktualisieren

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der alte Name des zu aktualisierenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu aktualisierenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-n <i>NAME</i> (optional)</dt>
<dd>Der neue Name des API-Schlüssels</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die neue Beschreibung des API-Schlüssels</dd>
</dl>

<strong>Beispiele</strong>:

Beschreibung eines API-Schlüssels aktualisieren:

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform löschen

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu löschenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu löschenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

API-Schlüssel der Plattform sperren

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Sperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel "test-api-key" sperren

```
ibmcloud iam api-key-lock test-api-key
```

API-Schlüssel mit der angegebenen UUID ohne Bestätigung sperren

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

API-Schlüssel der Plattform entsperren

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Entsperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel "test-api-key" entsperren

```
ibmcloud iam api-key-unlock test-api-key
```

API-Schlüssel mit der angegebenen UUID ohne Bestätigung entsperren

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Alle API-Schlüssel eines Service auflisten

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Die Service-API-Schlüssel ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Alle API-Schlüssel des Service `sample-service` auflisten

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Details eines Service-API-Schlüssels auflisten

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>UUID des Service-API-Schlüssels anzeigen</dd>
  <dt>-f, --force</dt>
  <dd>Den Service-API-Schlüssel ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details des Service-API-Schlüssels `sample-key` des Service `sample-service` anzeigen:

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Service-API-Schlüssel erstellen

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID oder des neu erstellten Service-API-Schlüssels</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung des API-Schlüssels</dd>
  <dt>--file</dt>
  <dd>Informationen zu API-Schlüssel in angegebener Datei speichern. Wenn nicht festgelegt, wird der JSON-Inhalt angezeigt.</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` für Service `sample-service` ohne Bestätigung erstellen:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Service-API-Schlüssel aktualisieren

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Service-API-Schlüssels</dd>
  <dt>-d, --description</dt>
  <dd>Die neue Beschreibung des Service-API-Schlüssels</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` in `new-sample-key` umbenennen:

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Service-API-Schlüssel löschen

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` löschen:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Service-API-Schlüssel sperren

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` sperren:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Service-API-Schlüssel entsperren

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` entsperren:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Richtlinien von Benutzer `name@example.com` auflisten:

```
ibmcloud iam user-policies name@example.com
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Benutzername, zu dem die Richtlinien gehören</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinien von Benutzer `name@example.com` auflisten:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Details zu einer Benutzerrichtlinie anzeigen

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Benutzername, zu dem die Richtlinie gehört</dd>
<dt>POLICY_ID (erforderlich)</dt>
<dd>Die ID der Richtlinie</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `0bb730daa` des Benutzers `name@example.com` auflisten:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Benutzerrichtlinie erstellen

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Ressource der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. Dieser kann nur mit den Flags '--file', '--resource' und '--resource-group-id' verwendet werden.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. Diese kann nur mit den Flags '--file', '--resource' und '--resource-group-name' verwendet werden.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie für Benutzer `name@example.com` aus Richtlinien-JSON-Datei `policy.json` erstellen:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

`name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuweisen:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuweisen:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuweisen:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Benutzerrichtlinie aktualisieren

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>POLICY_ID (erforderlich)</dt>
<dd>Die ID der zu aktualisierenden Richtlinie</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Ressource der Richtliniendefinition. Diese kann nur mit dem Flag '--file' verwendet werden.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. Dieser kann nur mit den Flags '--file', '--resource' und '--resource-group-id' verwendet werden.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. Diese kann nur mit den Flags '--file', '--resource' und '--resource-group-name' verwendet werden.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie mit der Benutzerrichtlinie in der JSON-Datei aktualisieren

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zu erteilen

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuzuweisen:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuzuweisen:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Benutzerrichtlinie löschen

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Benutzerrichtlinie ohne Bestätigung löschen</dd>
</dl>

<strong>Beispiele</strong>:
Richtlinie `user-policy-id` des Benutzers `name@example.com` löschen:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Richtlinie `user-policy-id` des Benutzers `name@example.com` ohne Bestätigung löschen:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Alle Servicerichtlinien des angegebenen Service auflisten

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>-json</dt>
  <dd>Die Richtlinie im JSON-Format anzeigen</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinien ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinien des Service `test` auflisten:

```
ibmcloud iam service-policies test
```
Richtlinien des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` auflisten:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Details zu einer Servicerichtlinie anzeigen

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>-json</dt>
  <dd>Die Richtlinie im JSON-Format anzeigen</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `140798e2-8ea7db3` des Service `test` anzeigen:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Richtlinie `140798e2-8ea7db3` des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` anzeigen:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Servicerichtlinie erstellen

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Dies kann nur mit den Flags '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' und '--resource-group-id' verwendet werden.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung erstellen</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie aus JSON-Datei für Service `test` erstellen:

```
ibmcloud iam service-policy-create test --file @policy.json
```
Servicerichtlinie aus JSON-Datei für Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` erstellen:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Servicerichtlinie aktualisieren

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Diese kann nur mit den Flags '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' und 'resource-group-id' verwendet werden.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'ibmcloud iam roles --service SERVICE_NAME' aus. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit '--file' und '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung aktualisieren</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie `140798e2-8ea7db3` aus JSON-Datei für Service `test` aktualisieren:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Servicerichtlinie `140798e2-8ea7db3` aus JSON-Datei für Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` aktualisieren:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Servicerichtlinie löschen

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `140798e2-8ea7db3` des Service `test` löschen

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Richtlinie `140798e2-8ea7db3` des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` löschen

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

OAuth-Tokens für die aktuelle Sitzung abrufen und anzeigen

```
ibmcloud iam oauth-tokens
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

OAuth-Tokens aktualisieren und anzeigen

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Verbindung zwischen öffentlicher IBMid und dedizierter, von IBM unabhängiger ID trennen

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Trennen ohne Bestätigung erzwingen</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Berechtigungsrichtlinie erstellen, um den Zugriff einer Serviceinstanz auf eine andere Serviceinstanz zu ermöglichen.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Quellenservice, der für den Zugriff autorisiert werden kann.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Zielservice, für dessen Zugriff der Quellenservice autorisiert werden kann.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Die Rollen, die Zugriff für den Quellenservice bereitstellen.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Instanzname des Quellenservice. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Quellenservice Zugriffsberechtigung.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Instanzname des Zielservice. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Zielservice Zugriffsberechtigung.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Berechtigungsrichtlinie löschen.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID der zu löschenden Berechtigungsrichtlinie.</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Details zu einer Berechtigungsrichtlinie anzeigen.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID der anzuzeigenden Berechtigungsrichtlinie.</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Berechtigungsrichtlinien unter dem aktuellen Konto auflisten.

```
ibmcloud iam authorization-policies
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Ressourcengruppen auflisten.

```
ibmcloud resource groups [--default]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--default</dt>
  <dd>Standardgruppe des aktuellen Kontos abrufen.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Ressourcengruppen unter aktuellem Zielkonto auflisten:

```
ibmcloud resource groups
```

Standardgruppe unter aktuellem Zielkonto auflisten:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Details einer Ressourcengruppe anzeigen

```
ibmcloud resource group NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Ressourcengruppe</dd>
  <dt>--id</dt>
  <dd>Nur ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` anzeigen:

```
ibmcloud resource group example-group
```

Nur ID der Ressourcengruppe `example-group` anzeigen:

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Ressourcengruppe erstellen

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` mit Kontingent `free` erstellen:

```
ibmcloud resource group-create example-group free
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Vorhandene Ressourcengruppe aktualisieren

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Zielressourcengruppe</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name der Ressourcengruppe</dd>
  <dt>-q, --quota</dt>
  <dd>Name der neuen Kontingentdefinition</dd>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` in `trial-group` umbenennen:

```
ibmcloud resource group-update example-group -n trial-group
```

Kontingent der Ressourcengruppe `example-group` in `free` ändern:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Alle Kontingentdefinitionen auflisten

```
ibmcloud resource quotas
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Kontingentdefinitionen auflisten:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Details einer Kontingentdefinition anzeigen

```
ibmcloud resource quota NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Kontingents</dd>
</dl>

<strong>Beispiele</strong>:
Details des Kontingents `free` anzeigen:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloud Foundry-Serviceinstanz in eine Ressourcengruppe migrieren

```
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME oder SERVICE_INSTANCE_ID (erforderlich)</dt>
  <dd>Der Name oder die ID der Serviceinstanz</dd>
  <dt>--resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit dem Flag '--resource-group-id'. Wenn keine der beiden Optionen angegeben wird, wird standardmäßig die aktuell als Ziel angegebene Ressourcengruppe verwendet.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit dem Flag '--resource-group-name'. Wenn keine der beiden Optionen angegeben wird, wird standardmäßig die aktuell als Ziel angegebene Ressourcengruppe verwendet.</dd>
  <dt>-f, --force</dt>
  <dd>Migrieren ohne Bestätigung</dd>
</dl>


## ibmcloud app push
{: #ibmcloud_app_push}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf push ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## ibmcloud app list
{: #ibmcloud_app_list}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf apps ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## ibmcloud app show
{: #ibmcloud_app_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf app ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## ibmcloud app delete
{: #ibmcloud_app_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## ibmcloud app rename
{: #ibmcloud_app_rename}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## ibmcloud app start
{: #ibmcloud_app_start}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf start ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## ibmcloud app stop
{: #ibmcloud_app_stop}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stop ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## ibmcloud app restart
{: #ibmcloud_app_restart}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## ibmcloud app restage
{: #ibmcloud_app_restage}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restage ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart-app-instance ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## ibmcloud app events
{: #ibmcloud_app_events}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf events ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## ibmcloud app files
{: #ibmcloud_app_files}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf files ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## ibmcloud app logs
{: #ibmcloud_app_logs}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf logs ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## ibmcloud app env
{: #ibmcloud_app_env}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf set-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf unset-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stacks ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stack ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-app-manifest ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Die Zertifikatsinformationen für eine Domäne auflisten

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>DOMAIN_NAME (erforderlich)</dt>
<dd>Die Domäne, in der das Zertifikat gehostet wird.</dd>
</dl>


<strong>Beispiele</strong>:

Die Zertifikatsinformationen für die Domäne `ibmcxo-eventconnect.com` anzeigen:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Der angegebenen Domäne in der aktuellen Organisation ein Zertifikat hinzufügen.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, der das Zertifikat hinzugefügt wird.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Datei mit dem privaten Schlüssel.</dd>
   <dt>-c <i>CERT_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Zertifikatsdatei.</dd>
   <dt>-p <i>PASSWORD</i> (optional)</dt>
   <dd>Das Kennwort für das Zertifikat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (optional)</dt>
   <dd>Der Pfad für die Zwischenzertifikatsdatei.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (optional)</dt>
   <dd>Die Truststore-Datei.</dd>
   </dl>


<strong>Beispiele</strong>:

Zertifikat der Domäne `ibmcxo-eventconnect.com` hinzufügen:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Zertifikat aus der angegebenen Domäne in der aktuellen Organisation entfernen.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, aus der das Zertifikat entfernt werden soll.</dd>
   <dt>-f  (optional)</dt>
   <dd>Löschung ohne Bestätigung erzwingen.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf check-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Eine Route einer vorhandenen cf-Anwendung oder -Containergruppe zuordnen, die über die angegebene Domäne oder den angegebenen Hostnamen verfügt.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung oder -Containergruppe für die Zuordnung der Route.</dd>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne der Route. Beispiele: mychinabluemix.net oder chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (optional)</dt>
   <dd>Der Hostname der Route. Wenn der Hostname nicht angegeben wird, wird standardmäßig der Anwendungsname oder der Containergruppenname festgelegt.</dd>
   </dl>

<strong>Beispiele</strong>:

Route zu `my-app` mit angegebener Domäne zuordnen:

```
ibmcloud app route-map my-app mychinabluemix.net
```

Route zu 'my-container-group' mit angegebener Domäne und angegebenem Hostnamen zuordnen:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Zuordnung der angegebenen Route zu einer vorhandenen cf-Anwendung oder -Containergruppe aufheben.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung oder -Containergruppe.</dd>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne der Route (Beispiele: mychinabluemix.net oder chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (optional)</dt>
   <dd>Der Hostname der Route. Wenn der Hostname nicht angegeben wird, wird standardmäßig der Anwendungsname oder der Containergruppenname festgelegt.</dd>
   </dl>

<strong>Beispiele</strong>:

Zuordnung von `my-app.mychinabluemix.net` zu `my-app` aufheben:

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Zuordnung von `abc.chinabluexmix.net` zu `my-container-group` aufheben:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-orphaned-routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## ibmcloud app domains
{: #ibmcloud_app_domains}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf domains ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf marketplace ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## ibmcloud service list
{: #ibmcloud_service_list}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf services ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## ibmcloud service show
{: #ibmcloud_service_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## ibmcloud service create
{: #ibmcloud_service_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## ibmcloud service update
{: #ibmcloud_service_update}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf update-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## ibmcloud service delete
{: #ibmcloud_service_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## ibmcloud service rename
{: #ibmcloud_service_rename}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## ibmcloud service bind
{: #ibmcloud_service_bind}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf bind-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf unbind-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## ibmcloud service keys
{: #ibmcloud_service_keys}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service-keys ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-user-provided-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf update-user-provided-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Serviceinstanzen auflisten

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Der Name des zugehörigen Service</dd>
  <dt>--location</dt>
  <dd>Nach Position filtern</dd>
  <dt>--long</dt>
  <dd>Weitere Felder in Ausgabe anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceinstanzen des Service `test-service` auflisten:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Details einer Serviceinstanz anzeigen

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich), gegenseitig ausschließend mit ID</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>ID (erforderlich), gegenseitig ausschließend mit NAME</dt>
  <dd>ID der Serviceinstanz</dd>
  <dt>--location</dt>
  <dd>Nach Position filtern</dd>
  <dt>--id</dt>
  <dd>ID der Serviceinstanz anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details der Serviceinstanz `my-service-instance` anzeigen:

```
ibmcloud resource service-instance my-service-instance
``` 

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Serviceinstanz erstellen

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>SERVICE_NAME oder SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Service</dd>
  <dt>SERVICE_PLAN_NAME oder SERVICE_PLAN_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Serviceplans</dd>
  <dt>LOCATION</dt>
  <dd>Zielposition oder -umgebung zum Erstellen der Serviceinstanz</dd>
  <dt>-t, --tags</dt>
  <dd>Tags</dd>
  <dt>-p, --parameters</dt>
  <dd>Die JSON-Datei oder JSON-Zeichenfolge von Parametern zum Erstellen einer Serviceinstanz</dd>
  <dt>-d, --deployment</dt>
  <dd>Name der Bereitstellung</dd>
</dl>

<strong>Beispiele</strong>:
Eine Serviceinstanz mit dem Namen `my-service-instance` mithilfe des Serviceplans `test-service-plan` des Service `test-service` in der Region `eu-gb` erstellen:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Serviceinstanz aktualisieren

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>Name (erforderlich)</dt>
  <dd>Name der Serviceinstanz, gegenseitig ausschließend mit ID</dd>
  <dt>ID (erforderlich)</dt>
  <dd>ID der Serviceinstanz, gegenseitig ausschließend mit NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name der Serviceinstanz</dd>
  <dt>-t, --tags</dt>
  <dd>Neue Tags</dd>
  <dt>--service-plan-id</dt>
  <dd>Die neue ID des Serviceplans</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceinstanz `my-service-instance` aktualisieren und ihren Namen in `new-service-instance` ändern:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Serviceinstanz löschen

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>Name (erforderlich)</dt>
  <dd>Name der Serviceinstanz, gegenseitig ausschließend mit ID</dd>
  <dt>ID (erforderlich)</dt>
  <dd>ID der Serviceinstanz, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
  <dt>--recursive</dt>
  <dd>Alle zugehörigen Ressourcen löschen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceinstanz `my-service-instance` der Ressource löschen:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Bindungen an Servicealias anzeigen

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
</dl>

<strong>Beispiele</strong>:
Ressourcenbindungen an Servicealiasnamen `my-service-alias` anzeigen:

```
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Details einer Servicebindung anzeigen

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>--id</dt>
  <dd>Nur die ID anzeigen. Alle anderen Ausgaben für diese Servicebindung werden unterdrückt.</dd>
</dl>

<strong>Beispiele</strong>:
Details der Servicebindung zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` anzeigen:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Servicebindung erstellen

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>ROLE_NAME</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--service-id</dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameter</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicebindungen zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` mit der Rolle `Administrator` erstellen:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Servicebindung löschen

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicebindung zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` löschen:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Serviceschlüssel der Serviceinstanz oder des Servicealias auflisten

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Die Serviceinstanz-ID</dd>
  <dt>--instance-name</dt>
  <dd>Der Serviceinstanzname</dd>
  <dt>--alias-id</dt>
  <dd>Die Servicealias-ID</dd>
  <dt>--alias-name</dt>
  <dd>Der Servicealiasname</dd>
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel der Serviceinstanz `my-service-instance` auflisten:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Details eines Serviceschlüssels anzeigen

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>--id</dt>
  <dd>ID des Serviceschlüssels anzeigen</dd>
</dl>

<strong>Beispiele</strong>:
Details der Serviceschlüssel `my-service-key` anzeigen:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Serviceschlüssel erstellen

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>ROLE_NAME</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--instance-id</dt>
  <dd>Die Serviceinstanz-ID</dd>
  <dt>--instance-name</dt>
  <dd>Der Serviceinstanzname</dd>
  <dt>--alias-id</dt>
  <dd>Die Servicealias-ID</dd>
  <dt>--alias-name</dt>
  <dd>Der Servicealiasname</dd>
  <dt>--service-id</dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel mit dem Namen `my-service-key` mit der Rolle `Administrator` für die Serviceinstanz `my-service-instance` erstellen:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Serviceschlüssel löschen

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel `my-service-key` löschen:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Aliasnamen für eine Serviceinstanz auflisten

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Die ID der zugehörigen Serviceinstanz.</dd>
  <dt>--instance-name</dt>
  <dd>Der Name der zugehörigen Serviceinstanz.</dd>
</dl>

<strong>Beispiele</strong>:
Servicealiasnamen für Serviceinstanz `my-service-instance` auflisten:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Details eines Servicealias anzeigen

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>--id</dt>
  <dd>Nur die ID des angegebenen Servicealias anzeigen. Alle anderen Ausgaben für diesen Alias werden unterdrückt.</dd>
</dl>

<strong>Beispiele</strong>:
Details des Servicealias `my-service-alias` anzeigen:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Alias einer Serviceinstanz erstellen

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>--instance-id</dt>
  <dd>Die ID der zugehörigen Serviceinstanz.</dd>
  <dt>--instance-name</dt>
  <dd>Der Name der zugehörigen Serviceinstanz.</dd>
  <dt>-s</dt>
  <dd>Der Name des Bereichs, in dem der Alias erstellt wird. Der Standardwert ist der aktuelle Bereich.</dd>
  <dt>-t, --tags</dt>
  <dd>Tagaufzählung</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
</dl>

<strong>Beispiele</strong>:
Servicealias mit dem Namen `my-service-alias` der Serviceinstanz `my-service-instance` erstellen:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Servicealias aktualisieren

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Servicealias</dd>
  <dt>-t, --tags</dt>
  <dd>Tagaufzählung</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung durch Benutzer erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicealias `my-service-alias` aktualisieren und seinen Namen in `new-service-alias` ändern:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Servicealias löschen

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicealias `my-service-alias` löschen:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Mit der Lucene-Abfragesyntax nach Ressourcen suchen

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-offset, --o</dt>
  <dd>Anfangspositionsnummer der Ressource</dd>
  <dt>-limit, --l</dt>
  <dd>Anzahl zurückzugebender Ressourcen (maximal 10000)</dd>
</dl>

<strong>Beispiele</strong>:
Nach Cloud Foundry-Anwendungen suchen, deren Name mit einem angegebenen Text beginnt:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Nach Cloud Foundry-Serviceinstanzen des angegebenen Servicenamens suchen:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Nach Cloud Foundry-Servicebindungen in der Organisation mit der angegebenen ID suchen:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Nach Cloud Foundry-Bereichen mit dem angegebenen Namen in einer der zwei angegebenen Regionen suchen:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Nach Ressourcen, deren Name die Zeichenfolge dev enthält, im Cloud Foundry-Bereich mit der angegebenen ID suchen:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Nach Resource Controller-Ressourcen an der angegebenen Position suchen (d. h. in der Region Vereinigte Staaten (Süden)):

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Nach Ressourcen oder Aliasnamen in der Ressourcengruppe mit der angegebenen ID suchen:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Nach Ressourcengruppen mit dem Namen 'default' suchen:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Nach Ressourcenbindungen für den angegebenen Servicenamen suchen:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Nach einer Ressource mit dem angegebenen CRN (Cloud Resource Name) suchen:

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Nach einer Ressource mit dem angegebenen Tag suchen:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Alle Tags auflisten

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Tagtyp (unterstützte Werte: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>Anfangspositionsnummer der Ressource (Standardwert: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Anzahl zurückzugebender Ressourcen (maximal 10000) (Standardwert: 10000)</dd>
</dl>

<strong>Beispiele</strong>:

Alle Tags auflisten

```
ibmcloud resource tags 
```

Alle eingeschränkten Tags auflisten

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Details eines Tags anzeigen

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
</dl>

<strong>Beispiele</strong>:

Details des Tags "Ray Brown" anzeigen

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Tag erstellen

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname</dd>
  <dt>--tag-type</dt>
  <dd>Tagtyp (unterstützte Werte: user, restricted; Standardwert: user)</dd>
</dl>

<strong>Beispiele</strong>:

Benutzertag mit dem Namen "think:2018" erstellen

```
ibmcloud resource tag-create --tag-name think:2018
```

Eingeschränkten Tag mit dem Namen "department:marketing" erstellen

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Benutzertag mit dem Namen "Ray Brown" erstellen

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Eingeschränkten Tag mit dem Namen "environment:My Development" erstellen

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Tag löschen

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" löschen

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Tag zu einer Ressource hinzufügen

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--resource-crn (erforderlich)</dt>
  <dd>Ressourcen-CRN</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" zur Ressource mit dem CRN "resource_example_crn" hinzufügen

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Tag von einer Ressource entfernen

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--resource-crn (erforderlich)</dt>
  <dd>Ressourcen-CRN</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" von der Ressource mit dem CRN "resource_example_crn" entfernen

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Benutzertag in eingeschränkten Tag ändern und umgekehrt

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--tag-type (erforderlich)</dt>
  <dd>Tagtyp</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" in eingeschränkten Tag ändern

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```


## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Katalogeinträge durchsuchen

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Die geografische Region angeben, in der gesucht werden soll. Momentan werden nur "us-south" und "united-kingdom" unterstützt</dd>
  <dt>-k, --kind</dt>
  <dd>Nach Art der Ressourcen filtern. Momentan werden nur "service-cf", "iaas", "runtime", "template" und "dashboard" unterstützt</dd>
  <dt>-p, --price</dt>
  <dd>Nach Preis filtern. Momentan werden nur "free", "paygo" und "bluemix-subscription" unterstützt</dd>
  <dt>-t, --tag</dt>
  <dd>Nach Tag filtern.</dd>
  <dt>--sort-by</dt>
  <dd>Für Sortierung zu verwendende Eigenschaft</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Momentan "group", "provider" und "tags".</dd>
  <dt>--reverse</dt>
  <dd>Gibt an, ob die Sortierreihenfolge umgekehrt werden soll</dd>
  <dt>--json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>--csv</dt>
  <dd>CSV-Ausgabedatei</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Service `Automation test` suchen:

```
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Katalogeintrag abrufen

```
ibmcloud catalog entry ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--children</dt>
  <dd>Alle untergeordneten Elemente für Katalogeintrag abrufen</dd>
  <dt>--json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Eintrag mit ID `a0ef1-d3b4j0` abrufen:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Neuen Katalogeintrag erstellen (nur Katalogadministrator eines Kontos)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>Die übergeordnete ID des Objekts</dd>
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource aus JSON-Datei mit der übergeordneten ID `a0ef1-d3b4j0` erstellen:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Vorhandenen Katalogeintrag aktualisieren (nur Katalogadministrator oder Editor eines Kontos)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource `j402-dnf1i` aus JSON-Datei aktualisieren:

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Katalogeintrag löschen (nur Katalogadministrator eines Kontos)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource `j402-dnf1i` löschen:

```
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Sichtbarkeit eines Katalogeintrags abrufen (nur Katalogadministrator eines Kontos)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>-global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Sichtbarkeit der Ressource `j402-dnf1i` im globalen Bereich abrufen:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Sichtbarkeit eines vorhandenen Katalogeintrags aktualisieren (nur Katalogadministrator eines Kontos)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) zur Einschlussliste hinzufügen und für den Eintrag Sichtbarkeit erteilen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--includes-remove</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) aus der Einschlussliste entfernen und für den Eintrag die Sichtbarkeit widerrufen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>  
  <dt>--excludes-add</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) zur Ausschlussliste hinzufügen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--excludes-remove</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) aus der Ausschlussliste entfernen und für den Eintrag die Sichtbarkeit widerrufen. Wenn das Konto von globalen Administratoren eingerichtet wurde, dann können die Kontoadministratoren das Konto nicht löschen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--owner</dt>
  <dd>Den Eigner eines Objekts ändern. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--restrict</dt>
  <dd>Die Einschränkung des Sichtbarkeitsobjekts in 'Privat' ändern.</dd>
  <dt>--unrestrict</dt>
  <dd>Die Einschränkung des Sichtbarkeitsobjekts in 'Öffentlich' ändern.</dd>  
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Sichtbarkeit der Ressource `j402-dnf1i` aus JSON-Datei festlegen:

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Serviceangebote im Marktplatz auflisten

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Nur Cloud Foundry-Services anzeigen</dd>
  <dt>--rc</dt>
  <dd>Nur RC-kompatible Services anzeigen</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Serviceangebote im globalen Bereich anzeigen:

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Boilerplate-Vorlagen in {{site.data.keyword.Bluemix_notm}} anzeigen

```
ibmcloud catalog templates [-d]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>-d (optional)</dt>
   <dd>Wenn die Option <i>-d</i> angegeben wird, wird auch die Beschreibung jeder Vorlage angezeigt. Andernfalls werden nur die ID und der Name jeder Vorlage angezeigt.</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Zeigt die detaillierten Informationen einer angegebenen Boilerplate-Vorlage an.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die ID der Boilerplate-Vorlage. Verwenden Sie <i>ibmcloud templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   </dl>


<strong>Beispiele</strong>:

Details der Vorlage `mobileBackendStarter` anzeigen:

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Erstellt eine cf-Anwendung, die auf der angegebenen Vorlage mit der angegebenen URL und Beschreibung basiert. Die neue App wird standardmäßig automatisch gestartet.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die Vorlage, auf der die Anwendung bei ihrer Erstellung basiert. Verwenden Sie <i>ibmcloud templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   <dt>CF_APP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung, die erstellt werden soll.</dd>
   <dt>-u <i>URL</i> (optional)</dt>
   <dd>Die Route der Anwendung. Wenn sie nicht angegeben ist, wird die Route von {{site.data.keyword.Bluemix_notm}} automatisch auf der Grundlage des App-Namens und der Standarddomäne festgelegt.</dd>
   <dt>-d <i>DESCRIPTION</i> (optional)</dt>
   <dd>Die Beschreibung für die Anwendung.</dd>
   <dt>--no-start (optional)</dt>
   <dd>Startet die Anwendung nach ihrer Erstellung nicht automatisch. Wenn diese Option nicht angegeben wird, wird die Anwendung nach ihrer Erstellung automatisch gestartet.</dd>
   </dl>


<strong>Beispiele</strong>:

cf-Anwendung `my-app` auf der Basis der Vorlage `javaHelloWorld` erstellen:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Anwendung `my-ruby-app` auf der Basis der Vorlage `rubyHelloWorld` mit der Route `myrubyapp.chinabluemix.net` und der Beschreibung `My first ruby app on {{site.data.keyword.Bluemix_notm}}.` erstellen:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Anwendung `my-python-app` auf Basis der Vorlage `pythonHelloWorld` ohne automatischen Start erstellen:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ausgewähltes Subset von Regionen in von Ihnen ausgewähltem Format abrufen.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>-i, --id</dt>
  <dd>Geografie nach ID angeben.</dd>
  <dt>-k, --kind</dt>
  <dd>Liste mit Einträgen für die angegebene Art abrufen.</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Momentan "group", "provider" und "tags".</dd>
  <dt>--json</dt>
  <dd>Ausgabe der ursprünglichen JSON-Antwort.</dd>
  <dt>--global</dt>
  <dd>In globalem Bereich arbeiten.</dd>
  <dt>--csv</dt>
  <dd>CSV-Ausgabedatei</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Details einer Laufzeit anzeigen. Dieser Befehl steht nur für die öffentliche Cloud zur Verfügung.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Beispiele</strong>:

Details der Laufzeit "nodejsHelloWorld" anzeigen:

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Alle Laufzeiten auflisten. Dieser Befehl steht nur für die öffentliche Cloud zur Verfügung.

```
ibmcloud catalog runtimes [-d]
```

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>-d</dt>
  <dd>Beschreibung der einzelnen Laufzeiten anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Alle Laufzeiten und deren Beschreibung auflisten:

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Monatliche Nutzungsinformationen des aktuellen Kontos anzeigen (nur Kontoadministrator)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

<strong>Beispiele</strong>:

Nutzungs- und Kostenbericht des aktuellen Kontos für 06/2016 anzeigen:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Monatliche Nutzungsinformationen für eine Organisation anzeigen (nur Kontoadministrator oder Abrechnungsmanager der Organisation)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>ORG_NAME (erforderlich)</dt>
  <dd>Name der Organisation.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Monatliche Nutzungsinformationen für eine Ressourcengruppe anzeigen (nur Kontoadministrator oder Ressourcengruppenadministrator)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>GROUP_NAME (erforderlich)</dt>
  <dd>Name der Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Monatliche Nutzung für Ressourceninstanzen unter dem aktuellen Konto anzeigen.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>-o ORG_NAME (optional)</dt>
  <dd>Filterinstanzen nach Organisation.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filterinstanzen nach Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für Monat und Datum durch Angeben des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Alle Plug-in-Repositorys auflisten, die in der Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} registriert sind.

```
ibmcloud plugin repos
```

<strong>Voraussetzungen</strong>: Keine


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Neues Plug-in-Repository zur Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} hinzufügen.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das hinzugefügt werden soll. Sie können einen eigenen Namen für jedes Repository definieren.</dd>
   <dt>REPO_URL (erforderlich)</dt>
   <dd>Die URL des Repositorys, das hinzugefügt werden soll. Die URL des Repositorys muss das Protokoll (zum Beispiel 'http://plugins.ng.bluemix.net' anstatt 'plugins.ng.bluemix.net') enthalten. http://plugins.ng.bluemix.net ist das offizielle Plug-in-Repository der {{site.data.keyword.Bluemix_notm}}-CLI.</dd>
    </dl>


<strong>Beispiele</strong>:

Offizielles Plug-in-Repository der {{site.data.keyword.Bluemix_notm}}-CLI als `bluemix-repo` hinzufügen:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Plug-in-Repository aus der {{site.data.keyword.Bluemix_notm}}-CLI entfernen.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das entfernt werden soll.</dd>
   </dl>

<strong>Beispiele</strong>:

Repository `bluemix-repo` aus der Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} entfernen:

```
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Alle verfügbaren Plug-ins in allen hinzufügten Repositorys oder einem bestimmten Repository auflisten.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Nur die Plug-ins im angegebenen Repository auflisten.</dd>
   </dl>

<strong>Beispiele</strong>:

Alle Plug-ins in allen hinzugefügten Repositorys auflisten:

```
ibmcloud plugin repo-plugins
```

Alle Plug-ins im Repository `bluemix-repo` auflisten:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Details eines Plug-ins im Repository anzeigen.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Der Name des Repositorys. Wird kein Repository angegeben, verwendet der Befehl das Standardrepository des Plug-ins.</dd>
   </dl>

<strong>Beispiele</strong>:

Details des Plug-ins "IBM-Containers" im Repository "sample-repo" auflisten:

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Details des Plug-ins "IBM-Containers" im Standardrepository auflisten

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Alle installierten Plug-ins in der {{site.data.keyword.Bluemix_notm}}-CLI auflisten.

```
ibmcloud plugin list
```

<strong>Voraussetzungen</strong>: Keine

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Details eines installierten Plug-ins anzeigen.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Voraussetzungen</strong>: Keine


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Angegebene Version des Plug-ins aus dem angegebenen Pfad oder Repository in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle installieren.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.
Wenn keine Version angegeben wird, wählt der Befehl die neueste verfügbare Version zur Installation aus.

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (erforderlich)</dt>
   <dd>Wenn -r <i>REPO_NAME</i> nicht angegeben wird, wird das Plug-in vom angegebenen lokalen Pfad oder der Remote URL installiert.</dd>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Der Name des Repositorys, in dem sich die Plug-in-Binärdatei befindet. Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.</dd>
   <dt>-v <i>VERSION</i> (optional)</dt>
   <dd>Die Version des Plug-ins, die installiert werden soll. Wird keine Angabe gemacht, wird die neueste Version des Plug-ins installiert. Diese Option ist nur gültig, wenn Sie das Plug-in aus dem Repository installieren.</dd>
   <dt>-f </dt>
   <dd>Installieren des Plug-ins ohne Bestätigung erzwingen.</dd>
    </dl>


Die {{site.data.keyword.Bluemix_notm}}-CLI trägt den offiziellen Repository-Namen `Bluemix`.

<strong>Beispiele</strong>:

Plug-in von der lokalen Datei installieren:

```
ibmcloud plugin install /downloads/new_plugin
```

Plug-in von der Remote URL installieren:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Plug-in 'container-service' der neuesten Version aus dem Repository 'Bluemix' installieren:

```
ibmcloud plugin install container-service -r Bluemix
```

oder einfach:

```
ibmcloud plugin install container-service
```

Plug-in 'container-service' mit der Version '0.1.425' aus dem offiziellen Plug-in-Repository installieren:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Upgrade des Plug-ins aus einem Repository durchführen.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.
Wenn keine Version angegeben wird, wählt der Befehl die neueste verfügbare Version zur Installation aus.

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Name des zu aktualisierenden Plug-ins. Wenn keine Angabe erfolgt, prüft der Befehl Upgrades für alle installierten Befehle.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Der Name des Repositorys, in dem sich die Plug-in-Binärdatei befindet. Wenn keine Angabe gemacht wird, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.</dd>
 <dt>-v <i>VERSION</i> (optional)</dt>
 <dd>Die Version des Plug-ins, auf die aktualisiert werden soll. Wenn keine Version angegeben wird, wird das Plug-in auf die neueste verfügbare Version aktualisiert.</dd>
 <dt>--all</dt>
 <dd>Alle verfügbaren Plug-ins aktualisieren</dd>
</dl>

<strong>Beispiele</strong>:

Offizielles Plug-in-Repository 'Bluemix' auf alle verfügbaren Upgrades prüfen:

```
ibmcloud plugin update -r Bluemix
```

oder einfach:

```
ibmcloud plugin update
```

Upgrade des Plug-ins 'container-service' im offiziellen Plug-in-Repository auf die neueste Version durchführen:

```
ibmcloud plugin update container-service
```

Plug-in 'container-service' im offiziellen Plug-in-Repository auf Version '0.1.440' aktualisieren:

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Angegebenes Plug-in in der {{site.data.keyword.Bluemix_notm}}-CLI deinstallieren.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>PLUGIN_NAME (erforderlich)</dt>
   <dd>Der Name des Plug-ins, das deinstalliert werden soll.</dd>
    </dl>

<strong>Beispiele</strong>:

Plug-in 'container-service' deinstallieren, das zuvor installiert wurde:

```
ibmcloud plugin uninstall container-service
```

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE-Umgebungen auflisten

```
bx cfee environments
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Details einer CFEE-Umgebung anzeigen

```
bx cfee environment NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
  <dl>
   <dt>--id</dt>
   <dd>Nur ID anzeigen</dd>
  </dl>

<strong>Beispiele</strong>:

Details der CFEE-Umgebung "env_example" anzeigen

```
bx cfee environment env_example
```

ID der CFEE-Umgebung "env_example" anzeigen

```
bx cfee environment env_example --id
```
