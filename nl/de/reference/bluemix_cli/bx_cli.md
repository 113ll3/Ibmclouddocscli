---



copyright:

  years: 2015, 2018
lastupdated: "2018-03-05"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}}-Befehle (bx)
{: #bluemix_cli}

Version: 0.6.5

Von der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI) werden Befehle bereitgestellt, die nach Namensbereich für Benutzer zur Interaktion mit {{site.data.keyword.Bluemix_notm}} zusammengefasst sind.

Ab Version 0.5.0 enthält die Installation des {{site.data.keyword.Bluemix_notm}}-Befehlszeilenclients einen Cloud Foundry-Befehlszeilenclient. Wenn Sie eine eigene Cloud Foundry-Befehlszeilenschnittstelle installiert haben, dann verwenden Sie die {{site.data.keyword.Bluemix_notm}}-CLI-Befehle `bx [command]` und die Cloud Foundry-CLI-Befehle `cf [command]` Ihrer eigenen Installation nicht in demselben Kontext. Verwenden Sie stattdessen `bluemix cf [command]`, wenn Sie Cloud Foundry-Ressourcen mit der Cloud Foundry-Befehlszeilenschnittstelle (CF-CLI) im {{site.data.keyword.Bluemix_notm}}-CLI-Kontext verwalten wollen.  Beachten Sie, dass `bluemix cf api/login/logout/target` nicht zulässig ist und dass Sie stattdessen `bluemix api/login/logout/target` verwenden müssen.

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

**Hinweis:** Sie können das Kurzformat für Bluemix-Befehle verwenden. Beispiel: `bx api` ist die Kurzform von `bluemix api`.

Verwenden Sie die Indizes in den folgenden Tabellen als Referenz für die häufig verwendeten Bluemix-Befehle.

## Allgemeine Bluemix-Befehle
{: #bx_commands_index}

<table summary="Allgemeine Bluemix-Befehle">
<caption>Tabelle 1. Allgemeine Bluemix-Befehle</caption>
 <thead>
 <th colspan="5">Allgemeine Bluemix-Befehle</th>
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

 ## Befehle zur Verwaltung und Konfiguration von Infrastrukturservices für {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)
  {: #bx_commands_softlayer}

Die Befehle zur Verwaltung der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} wurden in die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle integriert. Weitere Informationen zur Verwendung der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle zum Konfigurieren und Verwalten der Infrastrukturservices für {{site.data.keyword.BluSoftlayer_notm}} finden Sie im Abschnitt zu
[{{site.data.keyword.Bluemix_notm}}-CLI - Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)](/docs/cli/reference/softlayer/index.md#softlayer_cli).

 ## Befehle zur Verwaltung von Konten, Organisationen und Rollen
 {: #bx_commands_account}

<table summary="Bluemix-Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen.">
<caption>Tabelle 2. Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen</th>
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


 ## Befehle zur Verwaltung von Ressourcengruppen und Ressourcen
{: #bx_commands_resource}

<table summary="Bluemix-Befehle zur Verwaltung von Ressourcengruppen und Ressourcen.">
  <caption>Tabelle 3. Befehle zur Verwaltung von Ressourcengruppen und Ressourcen</caption>
  <thead>
    <th colspan="5">Befehle zur Verwaltung von Ressourcengruppen und Ressourcen</th>
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


 ## Befehle zur Verwaltung von API-Schlüsseln und Richtlinien
 {: #bx_commands_iam}
 <table summary="Bluemix-Befehle zur Verwaltung von API-Schlüsseln und Richtlinien.">
 <caption>Tabelle 3. Befehle zur Verwaltung von API-Schlüsseln und Richtlinien</caption>
  <thead>
  <th colspan="5">Befehle zur Verwaltung von API-Schlüsseln und Richtlinien</th>
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

 ## Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps
 {: #bx_commands_apps}

<table summary="Bluemix-Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps.">
<caption>Tabelle 4. Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</th>
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

 ## Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services
 {: #bx_commands_services}

<table summary="Bluemix-Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Services.">
<caption>Tabelle 5. Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von {{site.data.keyword.Bluemix_notm}}-Services</th>
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


 ## Befehle zur Verwaltung von Katalogen, Plug-ins und Einstellungen für die Abrechnung
 {: #bx_commands_settings}

<table summary="Bluemix-Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit.">
<caption>Tabelle 6. Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</th>
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
Zeigt die erweiterte Hilfe für integrierte Befehle und unterstützte Namensbereiche der obersten Ebene in der {{site.data.keyword.Bluemix_notm}}-CLI oder die Hilfe für einen bestimmten integrierten Befehl oder Namensbereich an.

```
bluemix help [COMMAND|NAMESPACE]
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
bluemix help
```

Hilfe für den Befehl `info` anzeigen:

```
bluemix help info
```



## bluemix api
{: #bluemix_api}
{{site.data.keyword.Bluemix_notm}}-API-Endpunkt festlegen oder anzeigen.

```
bluemix api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
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
bluemix api api.chinabluemix.net
```

```
bluemix api https://api.chinabluemix.net --skip-ssl-validation
```

Aktuellen API-Endpunkt anzeigen:

```
bluemix api
```

Definition für den API-Endpunkt rückgängig machen:

```
bluemix api --unset
```

## bluemix config
{: #bluemix_config}


Standardwerte in die Konfigurationsdatei schreiben.

```
bluemix config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
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
bluemix config --http-timeout 30
```

Traceausgabe für HTTP-Anforderungen aktivieren:

```
bluemix config --trace true
```

Traceausgabe für HTTP-Anforderungen in eine angegebene Datei */home/usera/my_trace* schreiben:

```
bluemix config --trace /home/usera/my_trace
```

Farbausgabe inaktivieren:

```
bluemix config --color false
```

Ländereinstellung auf 'zh_Hans' setzen:

```
bluemix config --locale zh_Hans
```

Ländereinstellungen löschen:

```
bluemix config --locale CLEAR
```



## bluemix info
{: #bluemix_info}

{{site.data.keyword.Bluemix_notm}}-Basisinformationen einschließlich aktueller Region, Cloud-Controller-Version und einigen nützlichen Endpunkten (zum Beispiel zum Anmelden und Austauschen von Zugriffstoken) anzeigen.

```
bluemix info
```

<strong>Voraussetzungen</strong>: Endpunkt


## bluemix cf
{: #bluemix_cf}

Eingebettete CF-CLI aufrufen

```
bluemix [-q, --quiet] cf COMMAND...
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
bluemix cf apps
```

CF-Services ohne Nachricht "Befehl cf wird aufgerufen..." auflisten:

```
bluemix -q cf services
```


## bluemix login
{: #bluemix_login}

Benutzer anmelden.

```
bluemix login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-o ORG] [-s SPACE]
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
  <dt> -o <i>ORG_NAME</i> (optional) </dt>
  <dd> Der Name der Zielorganisation. </dd>
  <dt> -s <i>SPACE_NAME</i> (optional) </dt>
  <dd> Der Name des Zielbereichs.</dd>
  <dt> --no-iam </dt>
  <dd> Authentifizierung beim Anmeldeserver anstatt beim öffentlichen IAM erzwingen</dd>
  <dt> --skip-ssl-validation (optional) </dt>
  <dd> Umgeht die SSL-Validierung von HTTP-Anforderungen. Diese Option wird nicht empfohlen.</dd>
</dl>

<strong>Beispiele</strong>:

#### Interaktive Anmeldung

```
bluemix login
```

Anmeldung mit einem Benutzernamen und einem Kennwort und Festlegen des Kontos, der Organisation und des Bereichs:

```
bluemix login -u Benutzername -p Kennwort -c MyAccountID -o MyOrg -s MySpace
```

Anmeldung mit einmaligem Kenncode und Festlegen eines Zielkontos, einer Organisation und eines Bereichs:

```
bluemix login --sso -c MyAccountID -o MyOrg -s MySpace
```

Anmeldung mit API-Schlüssel und Festlegen von Zielen:

#### API-Schlüssel hat zugeordnetes Konto.

```
bluemix login --apikey api-key-string -o MyOrg -s MySpace
```

```
bluemix login --apikey @Dateiname -o MyOrg -s MySpace
```

#### API-Schlüssel hat kein zugeordnetes Konto.

```
bluemix login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
bluemix login --apikey @Dateiname -c MyAccountID -o MyOrg -s MySpace
```

<strong>Hinweis:</strong> Wenn der API-Schlüssel ein zugeordnetes Konto hat, ist ein Wechsel zu einem anderen Konto nicht zulässig.

#### Einmaligen Kenncode verwenden

```
bluemix login -u UserID --sso
```

Anschließend stellt die Befehlszeilenschnittstelle einen URL-Link bereit und fordert zur Eingabe eines Kenncodes auf:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Öffnen Sie im Browser den Link, der Sie zu dem Kenncode führt. Wenn Sie an der Konsole den angegebenen Kenncode eingeben, sollten Sie in der Lage sein, sich anmelden.

## bluemix logout
{: #bluemix_logout}

Benutzer abmelden.

```
bluemix logout
```

<strong>Voraussetzungen</strong>: Keine

## bluemix regions
{: #bluemix_regions}

Zeigt die Informationen für alle Regionen in {{site.data.keyword.Bluemix_notm}} an.

```
bluemix regions
```

<strong>Voraussetzungen</strong>: Endpunkt


## bluemix target
{: #bluemix_target}


Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen.

```
bluemix target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>-r <i>REGION_NAME</i> (optional)</dt>
   <dd>Der Name der Region, in die gewechselt werden soll, z. B. 'us-south' oder 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (optional)</dt>
   <dd>Die ID des Zielkontos.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (optional)</dt>
   <dd>Name der Ressourcengruppe.</dd>
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
bluemix target -c MyAccountID -o MyOrg -s MySpace
```

Zu einer neuen Region wechseln:

```
bluemix target -r eu-gb
```

Aktuelles Konto, aktuelle Region, aktuelle Organisation und aktuellen Bereich anzeigen:

```
bluemix target
```

## bluemix update
{: #bluemix_update}

Die Befehlszeilenschnittstelle auf die neueste Version aktualisieren.

```
bluemix update
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>
<dl>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

### bluemix account orgs
{: #bluemix_account_orgs}

Alle Organisationen auflisten

```
bluemix account orgs [-r REGION] [--guid]
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
bluemix account orgs -r us-south --guid
```

## bluemix account org
{: #bluemix_account_org}

Die Informationen für die angegebene Organisation anzeigen

```
bluemix account org ORG_NAME [--guid]
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
bluemix account org IBM --guid
```


## bluemix account org-create
{: #bluemix_account_org_create}

Eine neue Organisation erstellen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
bluemix account org-create ORG_NAME [-f]
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
bluemix account org-create IBM
```

## bluemix account org-replicate
{: #bluemix_account_org_replicate}

Repliziert eine Organisation aus der aktuellen Region in eine andere Region.

```
bluemix account org-replicate ORG_NAME REGION_NAME
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
bluemix account org-replicate myorg eu-gb
```


## bluemix account org-rename
{: #bluemix_account_org_rename}

Eine Organisation umbenennen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
bluemix account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>OLD_ORG_NAME (erforderlich)</dt>
   <dd>Der bisherige Name der Organisation, die umbenannt werden soll.</dd>
   <dt>NEW_ORG_NAME (erforderlich)</dt>
   <dd>Der neue Name für die Organisation, die umbenannt werden soll.</dd>
   </dl>


## bluemix account spaces
{: #bluemix_account_spaces}

Alle Bereiche auflisten

```
bluemix account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>-o</dt>
   <dd>Organisationsname. Die Bereiche unter der angegebenen Organisation auflisten. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-r</dt>
   <dd>Regionsname. Die Bereiche unter der angegebenen Region auflisten. Standardmäßig wird die aktuelle Region verwendet, wenn keine Angabe gemacht wurde.</dd>
   </dl>



## bluemix account space
{: #bluemix_account_space}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}. 


## bluemix account space-create
{: #bluemix_account_space_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}. 


## bluemix account space-rename
{: #bluemix_account_space_rename}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}. 


## bluemix account space-delete
{: #bluemix_account_space_delete}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}. 

## bluemix account org-users
{: #bluemix_account_org_users}

Benutzer in der angegebenen Organisation nach Rolle anzeigen

```
bluemix account org-users ORG_NAME [-a]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>ORG_NAME (erforderlich)</dt>
<dd>Der Name der Organisation.</dd>
<dt>-a (optional)</dt>
<dd>Alle Benutzer in der angegebenen Organisation auflisten (nicht nach Rolle gruppiert).</dd>
</dl>

## bluemix account org-user-add
{: #bluemix_account_org_user_add}

Benutzer zur Organisation hinzufügen (Organisationsmanager erforderlich).

```
 bluemix account org-user-add USER_NAME ORG
```

## bluemix account org-user-remove
{: #bluemix_account_org_user_remove}

Benutzer aus der Organisation entfernen (Organisationsmanager oder nur Benutzer selbst)

```
   bluemix account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--force, -f</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## bluemix account org-roles
{: #bluemix_account_org_roles}

Alle Organisationsrollen des aktuellen Benutzers abrufen

```
bluemix account org-roles [-u USER_ID]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
  <dl>
   <dt>-u</dt>
   <dd>Benutzer-ID. Wenn keine Angabe erfolgt, wird standardmäßig der aktuelle Benutzer verwendet.</dd>
  </dl>

## bluemix account org-role-set
{: #bluemix_account_org_role_set}

Einem Benutzer eine Organisationsrolle zuweisen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
bluemix account org-role-set USER_NAME ORG_NAME ORG_ROLE
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
bluemix account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Hinweis:** Sie können die Organisations-/Bereichsrolle mithilfe der CLI festlegen; zum Festlegen der übrigen Berechtigungen müssen Sie jedoch die Benutzerschnittstelle verwenden. Weitere Informationen finden Sie in [Benutzerzugriff zuweisen](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

## bluemix account org-role-unset
{: #bluemix_account_org_role_unset}

Eine Organisationsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
bluemix account org-role-unset USER_NAME ORG_NAME ORG_ROLE
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
bluemix account org-role-unset Mary IBM OrgManager
```

## bluemix account space-users
{: #bluemix_account_space_users}

Benutzer in dem angegebenen Bereich nach Rolle anzeigen

```
bluemix account space-users ORG_NAME SPACE_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   </dl>


## bluemix account space-role-set
{: #bluemix_account_space_role_set}

Einem Benutzer eine Bereichsrolle zuweisen. Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
bluemix account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
    </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` der Organisation `IBM` und dem Bereich `Cloud` mit der Rolle `SpaceManager` zuweisen:

```
bluemix account space-role-set Mary IBM Cloud SpaceManager
```

## bluemix account space-role-unset
{: #bluemix_account_space_role_unset}

Eine Bereichsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
bluemix account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
bluemix account space-role-unset Mary IBM Cloud SpaceManager
```

## bluemix account list
{: #bluemix_account_list}

Alle Konten des aktuellen Benutzers auflisten

```
bluemix account list
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung


## bluemix account org-account
{: #bluemix_account_org_account}

Das Konto der angegebenen Organisation anzeigen (Organisationsbenutzer erforderlich)

```
bluemix account org-account ORG_NAME [--guid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
  <dt>--guid (optional)</dt>
  <dd>Nur die Konto-ID anzeigen</dd>
</dl>


## bluemix account users
{: #bluemix_account_users}

Dem Konto zugeordnete Benutzer anzeigen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
bluemix account users
```

## bluemix account user-delete
{: #bluemix_account_user_delete}

Benutzer aus dem aktuellen Konto löschen (nur Kontoeigner)

```
bluemix account user-delete USERNAME [-c ACCOUNT_ID] [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USERNAME (erforderlich)</dt>
<dd>Der Benutzername.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Konto-ID. Wenn keine Angabe erfolgt, wird standardmäßig das aktuelle Konto verwendet.</dd>
<dt>--force, -f (optional)</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## bluemix account user-invite
{: #bluemix_account_user_invite}

Lädt einen Benutzer zu dem Konto ein. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
bluemix account user-invite USER_EMAIL
```

## bluemix account user-reinvite
{: #bluemix_account_user_reinvite}

Einladung erneut an einen Benutzer senden (Kontoeigner ist erforderlich).

```
bluemix account user-reinvite USER_EMAIL
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung
  
 <strong>Befehlsoptionen:</strong>
 <dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der erneut eingeladen wird.</dd>
 </dl>



## bluemix iam service-ids
{: #bluemix_iam_service_ids}

Alle Service-IDs auflisten

```
bluemix iam service-ids --uuid
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-uuid</dt>
  <dd>Nur UUID der Service-IDs anzeigen</dd>
</dl>

<strong>Beispiele</strong>:
UUID aller Service-IDs des aktuellen Kontos auflisten

```
bluemix iam service-ids --uuid
```


## bluemix iam service-id
{: #bluemix_iam_service_id}

Details einer Service-ID anzeigen

```
bluemix iam service-id NAME [--uuid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name des Service</dd>
  <dt>-uuid</dt>
  <dd>UUID der Service-ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details der Service-ID `sample-test` anzeigen

```
bluemix iam service-id sample-test
```


## bluemix iam service-id-create
{: #bluemix_iam_service_id_create}

Service-ID erstellen

```
bluemix iam service-id-create NAME [-d, --description DESCRIPTION]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung der Service-ID</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID mit dem Servicenamen `sample-test` und der Beschreibung `hello, world!` erstellen

```
bluemix iam service-id-create sample-test -d 'hello, world!'
```


## bluemix iam service-id-update

{: #bluemix_iam_service_id_update}
Service-ID aktualisieren

```
bluemix iam service-id-update NAME [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name des Service</dd>
  <dt>-n, --name</dt>
  <dd>Neuer Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Neue Beschreibung des Service</dd>
  <dt>-v, --version</dt>
  <dd>Version der Service-ID</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-test` ohne Bestätigung in `sample-test-2` umbenennen

```
bluemix iam service-id-update sample-test -n sample-test-2 -f
```

Beschreibung des Service `sample-test` mit der Version `1-0jn39fbefew` aktualisieren

```
bluemix iam service-id-update sample-test -d 'hello, friend!' -v 1-0jn39fbefew
```


## bluemix iam service-id-delete
{: #bluemix_iam_service_id_delete}

Service-ID löschen

```
bluemix iam service-id-delete NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name des Service</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-teset` ohne Bestätigung löschen

```
bluemix iam service-id-delete sample-teset -f
```


## bluemix iam api-keys
{: #bluemix_iam_api_keys}

Alle API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform auflisten

```
bluemix iam api-keys
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

## bluemix iam api-key-create
{: #bluemix_iam_api_key_create}

Neuen API-Schlüssel für {{site.data.keyword.Bluemix_notm}}-Plattform erstellen

```
bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu erstellenden API-Schlüssels.</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die Beschreibung des API-Schlüssels</dd>
<dt>-f, -- file <i>FILE</i></dt>
<dd>Informationen zu API-Schlüssel in angegebener Datei speichern. Wenn nicht festgelegt, wird der JSON-Inhalt angezeigt.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel erstellen und in einer Datei speichern

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
```

## bluemix iam api-key-update
{: #bluemix_iam_api_key_update}

API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform aktualisieren

```
bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der alte Name des zu aktualisierenden API-Schlüssels.</dd>
<dt>-n <i>NAME</i> (optional)</dt>
<dd>Der neue Name des API-Schlüssels</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die neue Beschreibung des API-Schlüssels</dd>
</dl>

<strong>Beispiele</strong>:

Beschreibung eines API-Schlüssels aktualisieren:

```
bluemix iam api-key-update MyKey -d "the new description of my key"
```

## bluemix api-key-delete
{: #bluemix_api_key_delete}

API-Schlüssel der {{site.data.keyword.Bluemix_notm}}-Plattform löschen

```
bluemix iam api-key-delete NAME [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu löschenden API-Schlüssels.</dd>
<dt>-f  (optional)</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## bluemix iam service-api-keys
{: #bluemix_iam_service_api_keys}

Alle API-Schlüssel eines Service auflisten

```
bluemix iam service-api-keys SERVICE_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle API-Schlüssel des Service `sample-service` auflisten

```
bluemix iam service-api-keys sample-service
```

## bluemix iam service-api-key
{: #bluemix_iam_service_api_key}

Details eines Service-API-Schlüssels auflisten

```
bluemix iam service-api-key NAME SERVICE_ID [--uuid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-uuid</dt>
  <dd>UUID des Service-API-Schlüssels anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details des Service-API-Schlüssels `sample-key` des Service `sample-service` anzeigen:

```
bluemix iam service-api-key sample-key sample-service
```

## bluemix iam service-api-key-create
{: #bluemix_iam_service_api_key_create}

Service-API-Schlüssel erstellen

```
bluemix iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [-f, --file FILE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung des API-Schlüssels</dd>
  <dt>-f, --file</dt>
  <dd>Informationen zu API-Schlüssel in angegebener Datei speichern. Wenn nicht festgelegt, wird der JSON-Inhalt angezeigt.</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` für Service `sample-service` erstellen:

```
bluemix iam service-api-key-create sample-key sample-service
```

## bluemix iam service-api-key-update
{: #bluemix_iam_service_api_key_update}

Service-API-Schlüssel aktualisieren

```
bluemix iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Service-API-Schlüssels</dd>
  <dt>-d, --description</dt>
  <dd>Die neue Beschreibung des Service-API-Schlüssels</dd>
  <dt>-v, --version</dt>
  <dd>Die Version des Service-API-Schlüssels</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` in `new-sample-key` umbenennen:

```
bluemix iam service-api-key-update sample-key sample-service -n new-sample-key
```

## bluemix iam service-api-key-delete
{: #bluemix_iam_service_api_key_delete}

Service-API-Schlüssel löschen

```
bluemix iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` löschen:

```
bluemix iam service-api-key-delete sample-key sample-service
```

## bluemix iam user-policies
{: #bluemix_iam_user_policies}

Richtlinien von Benutzer `name@example.com` auflisten:

```
bluemix iam user-policies name@example.com
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
bluemix iam user-policies name@example.com
```

## bluemix iam user-policy
{: #bluemix_iam_user_policy}

Details zu einer Benutzerrichtlinie anzeigen

```
bluemix iam user-policy USER_NAME POLICY_ID
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
bluemix iam user-policy name@example.com 0bb730daa
```

## bluemix iam user-policy-create
{: #bluemix_iam_user_policy_create}

Benutzerrichtlinie erstellen

```
bluemix iam user-policy-create USER_NAME {-f, --file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>-f, --file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'bluemix iam roles --service SERVICE_NAME' aus. Diese Option kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i> (optional)</dt>
<dd>Die Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Resource der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. Dieser kann nur mit den Flags '-f, --file', '--resource' und '--resource-group-id' verwendet werden.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. Diese kann nur mit den Flags '-f, --file', '--resource' und '--resource-group-name' verwendet werden.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie für Benutzer `name@example.com` aus Richtlinien-JSON-Datei `policy.json` erstellen:

```
bluemix iam user-policy-create name@example.com -f @policy.json
```

`name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuweisen:

```
bluemix iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz `ServiceId-ade78e9f` in der Region `us-south` zuweisen:

```
bluemix iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

`name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:

```
bluemix iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuweisen:

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:

```
bluemix iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## bluemix iam user-policy-update
{: #bluemix_iam_user_policy_update}

Benutzerrichtlinie aktualisieren

```
bluemix iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen:</strong>
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>POLICY_ID (erforderlich)</dt>
<dd>Die ID der zu aktualisierenden Richtlinie</dd>
<dt>-v, --version <i>VERSION</i> (optional)</dt>
<dd>Die Version der vorhandenen Richtlinie</dd>
<dt>-f, --file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>-f, --file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'bluemix iam roles --service SERVICE_NAME' aus. Diese Option ist kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i> (optional)</dt>
<dd>Die Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Resource der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. Dieser kann nur mit den Flags '-f, --file', '--resource' und '--resource-group-id' verwendet werden.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. Diese kann nur mit den Flags '-f, --file', '--resource' und '--resource-group-name' verwendet werden.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie mit der Benutzerrichtlinie in der JSON-Datei aktualisieren

```
bluemix iam user-policy-update name@example.com 0bb730daa -f @policy.json
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zu erteilen

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz `ServiceId-ade78e9f` in der Region `us-south` zuzuweisen:

```
bluemix iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuzuweisen:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:

```
bluemix iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```



## bluemix iam service-policies
{: #bluemix_iam_service_policies}

Alle Servicerichtlinien des angegebenen Service auflisten

```
bluemix iam service-policies SERVICE_ID_NAME [--json] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID</dd>
  <dt>-json</dt>
  <dd>Die Richtlinie im JSON-Format anzeigen</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinien ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinien des Service `test` auflisten:

```
bluemix iam service-policies test
```


## bluemix iam service-policy
{: #bluemix_iam_service_policy}

Details zu einer Servicerichtlinie anzeigen

```
bluemix iam service-policy SERVICE_ID_NAME POLICY_ID [--json] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID</dd>
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
bluemix iam service-policies test 140798e2-8ea7db3
```


## bluemix iam service-policy-create
{: #bluemix_iam_service_policy_create}

Servicerichtlinie erstellen

```
bluemix iam service-policy-create SERVICE_ID_NAME {-f, --file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID</dd>
  <dt>-f, --file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Dies kann nur mit den Flags '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' und '--resource-group-id' verwendet werden.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'bluemix iam roles --service SERVICE_NAME' aus. Diese Option kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--service-instance</dt>
  <dd>Die Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option kann nur mit den Flags '-f, --file' und '--resource-group-id' verwendet werden. </dd>
  <dt>--resource-group-id </dt>
  <dd>ID der Ressourcengruppe. Diese Option kann nur mit den Flags '-f, --file' und '--resource-group-name' verwendet werden.</dd>
  <dt>-F, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung erstellen</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie aus JSON-Datei für Service `test` erstellen:

```
bluemix iam service-policy-create test -f @policy.json
```


## bluemix iam service-policy-update
{: #bluemix_iam_service_policy_update}

Servicerichtlinie aktualisieren

```
bluemix iam service-policy-update SERVICE_ID_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-F, --force]",
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>-v, --version</dt>
  <dd>Die Version der Servicerichtlinie</dd>
  <dt>-f, --file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Diese kann nur mit den Flags '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' und 'resource-group-id' verwendet werden.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Führen Sie für unterstützte Rollen eines bestimmten Service 'bluemix iam roles --service SERVICE_NAME' aus. Diese Option kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-service-instance</dt>
  <dd>Die Serviceinstanz der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Dieser kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese kann nur mit dem Flag '-f, --file' verwendet werden.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name der Ressourcengruppe. Diese Option kann nur mit den Flags '-f, --file' und '--resource-group-id' verwendet werden.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID der Ressourcengruppe. Diese Option kann nur mit den Flags '-f, --file' und '--resource-group-name' verwendet werden.</dd>
  <dt>-F, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung aktualisieren</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie `140798e2-8ea7db3` aus JSON-Datei für Service `test` aktualisieren:

```
bluemix iam service-policy-update test 140798e2-8ea7db3 -f @policy.json
```

## bluemix iam service-policy-delete
{: #bluemix_iam_service_policy_delete}

Servicerichtlinie löschen

```
bluemix iam service-policy-delete SERVICE_ID_NAME POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `140798e2-8ea7db3` des Service `test` löschen

```
bluemix iam service-policy-delete test 140798e2-8ea7db3
```

## bluemix iam oauth-tokens
{: #bluemix_iam_oauth_tokens}

OAuth-Tokens für die aktuelle Sitzung abrufen und anzeigen.

```
bluemix iam oauth-tokens
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

OAuth-Tokens aktualisieren und anzeigen.

```
bluemix iam oauth-tokens
```

## bluemix iam dedicated-id-disconnect
{: #bluemix_iam_dedicated_id_disconnect}

Verbindung zwischen öffentlicher IBMid und dedizierter, von IBM unabhängiger ID trennen.

```
bluemix iam dedicated-id-disconnect [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Trennung der Verbindung ohne Bestätigung erzwingen.</dd>
</dl>

## bluemix iam authorization-policy-create
{: #bluemix_iam_authorization_policy_create}
 
Berechtigungsrichtlinie erstellen, um den Zugriff einer Serviceinstanz auf eine andere Serviceinstanz zu ermöglichen.

```
bluemix iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME] ROLE_NAME1,ROLE_NAME2...
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Quellenservice, der für den Zugriff autorisiert werden kann.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Zielservice, für dessen Zugriff der Quellenservice autorisiert werden kann.</dd>
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Instanzname des Quellenservice. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Quellenservice Zugriffsberechtigung.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Instanzname des Zielservice. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Zielservice Zugriffsberechtigung.   </dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Die Rollen, die Zugriff für den Quellenservice bereitstellen.</dd>  
</dl>

## bluemix iam authorization-policy-delete
{: #bluemix_iam_authorization_policy_delete}

Berechtigungsrichtlinie löschen.

```
bluemix iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID der zu löschenden Berechtigungsrichtlinie.</dd> 
 <dt>-f, --force</dt>
 <dd>Löschen ohne Bestätigung erzwingen.</dd> 
</dl>

## bluemix iam authorization-policy
{: #bluemix_iam_authorization_policy}

Details zu einer Berechtigungsrichtlinie anzeigen.

```
bluemix iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
 <dt>AUTHORIZATION_POLICY_ID</dt>
 <dd>ID der anzuzeigenden Berechtigungsrichtlinie.</dd> 
</dl>


## bluemix iam authorization-policies
{: #bluemix_iam_authorization_policies}

Berechtigungsrichtlinien unter dem aktuellen Konto auflisten.

```
bluemix iam authorization-policies
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

## bluemix resource groups
{: #bluemix_resource_groups}

Ressourcengruppen auflisten.

```
bluemix resource groups [--default]
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
bluemix resource groups
```

Standardgruppe unter aktuellem Zielkonto auflisten:

```
bluemix resource groups --default
```

## bluemix resource group
{: #bluemix_resource_group}

Details einer Ressourcengruppe anzeigen.

```
bluemix resource group NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name der Ressourcengruppe.</dd>
  <dt>--id</dt>
  <dd>Nur ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` anzeigen:

```
bluemix resource group example-group
```

Nur ID der Ressourcengruppe `example-group` anzeigen:

```
bluemix resource group example-group --id
```


## bluemix resource group-update
{: #bluemix_resource_group_update}

Vorhandene Ressourcengruppe aktualisieren.

```
bluemix resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Name der Zielressourcengruppe.</dd>
  <dt>-n, --name</dt>
  <dd>Neuer Name der Ressourcengruppe.</dd>
  <dt>-q, --quota</dt>
  <dd>Name der neuen Kontingentdefinition.</dd>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` in `trial-group` umbenennen:

```
bluemix resource group-update example-group -n trial-group
```

Kontingent der Ressourcengruppe `example-group` in `free` ändern:

```
bluemix resource group-update example-group -q free
```

## bluemix resource quotas
{: #bluemix_resource_quotas}

Alle Kontingentdefinitionen auflisten.

```
bluemix resource quotas
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Kontingentdefinitionen auflisten:

```
bluemix resource quotas
```

## bluemix resource quota
{: #bluemix_resource_quota}

Details einer Kontingentdefinition anzeigen

```
bluemix resource quota NAME
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
bluemix resource quota free
```


## bluemix app push
{: #bluemix_app_push}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf push ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}. 


## bluemix app list
{: #bluemix_app_list}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf apps ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}. 


## bluemix app show
{: #bluemix_app_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf app ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}. 


## bluemix app delete
{: #bluemix_app_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}. 


## bluemix app rename
{: #bluemix_app_rename}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}. 


## bluemix app start
{: #bluemix_app_start}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf start ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}. 


## bluemix app stop
{: #bluemix_app_stop}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stop ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}. 


## bluemix app restart
{: #bluemix_app_restart}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}. 


## bluemix app restage
{: #bluemix_app_restage}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restage ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}. 


## bluemix app instance-restart
{: #bluemix_app_instance_restart}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart-app-instance ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}. 


## bluemix app events
{: #bluemix_app_events}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf events ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}. 


## bluemix app files
{: #bluemix_app_files}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf files ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}. 


## bluemix app logs
{: #bluemix_app_logs}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf logs ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}. 


## bluemix app env
{: #bluemix_app_env}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}. 


## bluemix app env-set
{: #bluemix_app_env_set}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf set-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}. 


## bluemix app env-unset
{: #bluemix_app_env_unset}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf unset-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}. 


## bluemix app stacks
{: #bluemix_app_stacks}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stacks ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}. 


## bluemix app stack-show
{: #bluemix_app_stack_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stack ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}. 


## bluemix app manifest-create
{: #bluemix_app_manifest_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-app-manifest ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}. 

## bluemix app domain-cert
{: #bluemix_app_domain_cert}

Die Zertifikatsinformationen für eine Domäne auflisten

```
bluemix app domain-cert DOMAIN_NAME
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
bluemix app domain-cert ibmcxo-eventconnect.com
```

## bluemix app domain-cert-add
{: #bluemix_app_domain_cert_add}

Der angegebenen Domäne in der aktuellen Organisation ein Zertifikat hinzufügen.

```
bluemix app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
bluemix app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## bluemix app domain-cert-remove
{: #bluemix_app_domain_cert_remove}

Zertifikat aus der angegebenen Domäne in der aktuellen Organisation entfernen.

```
bluemix app domain-cert-remove DOMAIN [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, aus der das Zertifikat entfernt werden soll.</dd>
   <dt>-f  (optional)</dt>
   <dd>Löschung ohne Bestätigung erzwingen.</dd>
   </dl>

## bluemix app routes
{: #bluemix_app_routes}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}. 


## bluemix app route-check
{: #bluemix_app_route_check}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf check-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}. 


## bluemix app route-map
{: #bluemix_app_route_map}

Eine Route einer vorhandenen cf-Anwendung oder -Containergruppe zuordnen, die über die angegebene Domäne oder den angegebenen Hostnamen verfügt.

```
bluemix app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
bluemix app route-map my-app mychinabluemix.net
```

Route zu 'my-container-group' mit angegebener Domäne und angegebenem Hostnamen zuordnen:

```
bluemix app route-map my-container-group chinabluemix.net -n abc
```


## bluemix app route-unmap
{: #bluemix_app_route_unmap}

Zuordnung der angegebenen Route zu einer vorhandenen cf-Anwendung oder -Containergruppe aufheben.

```
bluemix app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
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
bluemix app route-unmap my-app mychianbluemix.net
```

Zuordnung von `abc.chinabluexmix.net` zu `my-container-group` aufheben:

```
bluemix app route-unmap my-container-group chinabluemix.net -n abc
```


## bluemix app route-create
{: #bluemix_app_route_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}. 


## bluemix app route-delete
{: #bluemix_app_route_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}. 


## bluemix app orphaned-routes-delete
{: #bluemix_app_orphaned_routes_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-orphaned-routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}. 


## bluemix app domains
{: #bluemix_app_domains}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf domains ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}. 


## bluemix app domain-create
{: #bluemix_app_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}. 


## bluemix app domain-delete
{: #bluemix_app_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}. 


## bluemix app shared-domain-create
{: #bluemix_app_shared_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}. 


## bluemix app shared-domain-delete
{: #bluemix_app_shared_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}. 


## bluemix service offerings
{: #bluemix_service_offerings}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf marketplace ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}. 


## bluemix service list
{: #bluemix_service_list}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf services ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}. 


## bluemix service show
{: #bluemix_service_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}. 


## bluemix service create
{: #bluemix_service_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}. 


## bluemix service update
{: #bluemix_service_update}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf update-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}. 


## bluemix service delete
{: #bluemix_service_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}. 


## bluemix service rename
{: #bluemix_service_rename}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}. 


## bluemix service bind
{: #bluemix_service_bind}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf bind-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}. 


## bluemix service unbind
{: #bluemix_service_unbind}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf unbind-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}. 


## bluemix service key-create
{: #bluemix_service_key_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}. 


## bluemix service key-delete
{: #bluemix_service_key_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}. 


## bluemix service keys
{: #bluemix_service_keys}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service-keys ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}. 


## bluemix service key-show
{: #bluemix_service_key_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf service-key ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}. 


## bluemix service user-provided-create
{: #bluemix_service_user_provided_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-user-provided-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}. 


## bluemix service user-provided-update
{: #bluemix_service_user_provided_update}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf update-user-provided-service ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}. 


## bluemix resource service-instances
{: #bluemix_resource_service_instances}

Serviceinstanzen auflisten

```
bluemix resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
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
bluemix resource service-instances --service-name test-service
```

## bluemix resource service-instance
{: #bluemix_resource_service_instance}

Details einer Serviceinstanz anzeigen

```
bluemix resource service-instance NAME [--location LOCATION] [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>--location</dt>
  <dd>Nach Position filtern</dd>
  <dt>--id</dt>
  <dd>ID der Serviceinstanz anzeigen</dd>
</dl>

<strong>Beispiele</strong>:
Details der Serviceinstanz `my-service-instance` anzeigen:

```
bluemix resource service-instance my-service-instance
```

## bluemix resource service-instance-create
{: #bluemix_resource_service_instance_create}

Serviceinstanz erstellen

```
bluemix resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
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
</dl>

<strong>Beispiele</strong>:
Eine Serviceinstanz mit dem Namen `my-service-instance` mithilfe des Serviceplans `test-service-plan` des Service `test-service` in der Region `eu-gb` erstellen:

```
bluemix resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## bluemix resource service-instance-update
{: #bluemix_resource_service_instance_update}

Serviceinstanz aktualisieren

```
bluemix resource service-instance-update SERVICE_INSTANCE_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME (erforderlich)</dt>
  <dd>Der Name der Serviceinstanz</dd>
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
bluemix resource service-instance-update my-service-instance -n new-service-instance
```

## bluemix resource service-instance-delete
{: #bluemix_resource_service_instance_delete}

Serviceinstanz löschen

```
bluemix resource service-instance-delete NAME [-f, --force] [--recursive]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
  <dt>--recursive</dt>
  <dd>Alle zugehörigen Ressourcen löschen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceinstanz `my-service-instance` der Ressource löschen:

```
bluemix resource service-instance-delete my-service-instance
```

## bluemix resource service-bindings
{: #bluemix_resource_service_bindings}

Bindungen an Servicealias anzeigen

```
bluemix resource bindings SERVICE_ALIAS
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
bluemix resource bindings my-service-alias
```
## bluemix resource service-binding
{: #bluemix_resource_service_binding}

Details einer Servicebindung anzeigen

```
bluemix resource service-binding ALIAS_NAME APP_NAME [--id]
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
bluemix resource bindings my-service-alias my-app
```

## bluemix resource service-binding-create
{: #bluemix_resource_service_binding_create}

Servicebindung erstellen

```
bluemix resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id-name SERVICE_ID_NAME] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
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
  <dt>--service-id-name</dt>
  <dd>Der Name der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameter</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicebindungen zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` mit der Rolle `Administrator` erstellen:

```
bluemix resource service-binding-create my-service-alias my-app Administrator
```
## bluemix resource service-binding-delete
{: #bluemix_resource_service_binding_delete}

Servicebindung löschen

```
bluemix resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
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
bluemix resource service-binding-delete my-service-alias my-app
```

## bluemix resource service-keys
{: #bluemix_resource_service_keys}

Serviceschlüssel der Serviceinstanz oder des Servicealias auflisten

```
bluemix resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
bluemix resource service-keys --instance-name my-service-instance
```

## bluemix resource service-key
{: #bluemix_resource_service_key}

Details eines Serviceschlüssels anzeigen

```
bluemix resource service-key KEY_NAME [--id]
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
bluemix resource service-key my-service-key
```

## bluemix resource service-key-create
{: #bluemix_resource_service_key_create}

Serviceschlüssel erstellen

```
bluemix resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id-name SERVICE_ID_NAME [-f, --force]]
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
  <dt>-service-id-name</dt>
  <dd>Der Name der Service-ID, zu der die Rolle gehört</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel mit dem Namen `my-service-key` mit der Rolle `Administrator` für die Serviceinstanz `my-service-instance` erstellen:

```
bluemix resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## bluemix resource service-key-delete
{: #bluemix_resource_service_key_delete}

Serviceschlüssel löschen

```
bluemix resource service-key-delete KEY_NAME [-f, --forece]
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
bluemix resource service-key-delete my-service-key
```

## bluemix resource service-aliases
{: #bluemix_resource_service_aliases}

Aliasnamen für eine Serviceinstanz auflisten

```
bluemix resource service-aliases [ --instance-id ID | --instance-name NAME ]
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
bluemix resource service-aliases my-service-instance
```

## bluemix resource service-alias
{: #bluemix_resource_service_alias}

Details eines Servicealias anzeigen

```
bluemix resource service-alias ALIAS_NAME [--id]
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
bluemix resource service-alias  my-service-alias
```

## bluemix resource service-alias-create
{: #bluemix_resource_service_alias_create}

Alias einer Serviceinstanz erstellen

```
bluemix resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
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
bluemix resource service-alias-create my-service-alias --instance-name my-service-instance
```

## bluemix resource service-alias-update
{: #bluemix_resource_service_alias_update}

Servicealias aktualisieren

```
bluemix resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
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
bluemix resource service-alias-update my-service-alias -n new-service-alias
```

## bluemix resource service-alias-delete
{: #bluemix_resource_service_alias_delete}

Servicealias löschen

```
bluemix resource service-alias-delete ALIAS_NAME [-f, --force]
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
bluemix resource service-alias-delete my-service-alias
```

## bluemix catalog search
{: #bluemix_catalog_search}

Katalogeinträge durchsuchen

```
bluemix catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
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
bluemix catalog search -k service -q 'Automation test'
```


## bluemix catalog entry
{: #bluemix_catalog_entry}

Katalogeintrag abrufen

```
bluemix catalog entry ID [--global]
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
bluemix catalog entry 'a0ef1-d3b4j0'
```


## bluemix catalog entry-create
{: #bluemix_catalog_entry_create}
Neuen Katalogeintrag erstellen (nur Katalogadministrator eines Kontos)

```
bluemix catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
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
bluemix catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## bluemix catalog entry-update
{: #bluemix_catalog_entry_update}
Vorhandenen Katalogeintrag aktualisieren (nur Katalogadministrator oder Editor eines Kontos)

```
bluemix catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
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
bluemix update 'j402-dnf1i' -c @update.json
```

## bluemix catalog entry-delete
{: #bluemix_catalog_entry_delete}
Katalogeintrag löschen (nur Katalogadministrator eines Kontos)
```
bluemix catalog entry-delete ID [--global]
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
bluemix catalog delete 'j402-dnf1i'
```


## bluemix catalog entry-visibility
{: #bluemix_catalog_entry_visibility}
Sichtbarkeit eines Katalogeintrags abrufen (nur Katalogadministrator eines Kontos)

```
bluemix catalog entry-visibility ID [--global]
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
bluemix catalog entry-visibility 'j402-dnf1i' --global
```


## bluemix catalog entry-visibility-set
{: #bluemix_catalog_entry_visibility_set}
Sichtbarkeit eines vorhandenen Katalogeintrags aktualisieren (nur Katalogadministrator eines Kontos)

```
bluemix catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
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
bluemix catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## bluemix catalog service-marketplace
{: #bluemix_catalog_service_marketplace}
Serviceangebote im Marktplatz auflisten

```
bluemix catalog service-marketplace [--cf] [--rc] [--global]
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
bluemix catalog service-marketplace --global
```

## bluemix catalog templates
{: #bluemix_catalog_templates}

Zeigt die Boilerplate-Vorlagen in Bluemix an.

```
bluemix catalog templates [-d]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>-d (optional)</dt>
   <dd>Wenn die Option <i>-d</i> angegeben wird, wird auch die Beschreibung jeder Vorlage angezeigt. Andernfalls werden nur die ID und der Name jeder Vorlage angezeigt.</dd>
   </dl>


## bluemix catalog template
{: #bluemix_catalog_template}

Zeigt die detaillierten Informationen einer angegebenen Boilerplate-Vorlage an.

```
bluemix catalog template TEMPLATE_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die ID der Boilerplate-Vorlage. Verwenden Sie <i>bluemix templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   </dl>


<strong>Beispiele</strong>:

Details der Vorlage `mobileBackendStarter` anzeigen:

```
bluemix catalog template mobileBackendStarter
```


## bluemix catalog template-run
{: #bluemix_catalog_template_run}

Erstellt eine cf-Anwendung, die auf der angegebenen Vorlage mit der angegebenen URL und Beschreibung basiert. Die neue App wird standardmäßig automatisch gestartet.

```
bluemix catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen:</strong>
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die Vorlage, auf der die Anwendung bei ihrer Erstellung basiert. Verwenden Sie <i>bluemix templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
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
bluemix catalog template-run javaHelloWorld my-app
```

Anwendung `my-ruby-app` auf der Basis der Vorlage `rubyHelloWorld` mit der Route `myrubyapp.chinabluemix.net` und der Beschreibung `My first ruby app on {{site.data.keyword.Bluemix_notm}}.` erstellen:

```
bluemix catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Anwendung `my-python-app` auf Basis der Vorlage `pythonHelloWorld` ohne automatischen Start erstellen:

```
bluemix catalog template-run pythonHelloWorld my-python-app --no-start
```

## bluemix catalog locations
{: #bluemix_catalog_locations}

Ausgewähltes Subset von Regionen in von Ihnen ausgewähltem Format abrufen.

```
bluemix catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
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

## bluemix billing account-usage
{: #bluemix_billing_account_usage}

Monatliche Nutzung und Kosten des aktuellen Kontos anzeigen.

```
bluemix billing account-usage [-d YYYY-MM] [--json]
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
bluemix billing account-usage -d 2016-06
```

## bluemix billing org-usage
{: #bluemix_billing_org_usage}

Monatliche Nutzung einer Organisation anzeigen. Diese Operation kann vom Kontoeigner oder vom Abrechnungsmanager der Organisation ausgeführt werden.

```
bluemix billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>ORG_NAME (erforderlich)</dt>
  <dd>Name der Organisation.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum durch Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>



## bluemix billing resource-group-usage
{: #bluemix_billing_resource_group_usage}

Monatliche Nutzung einer Ressourcengruppe anzeigen. Diese Operation kann vom Kontoeigner oder vom Abrechnungsmanager der Ressourcengruppe ausgeführt werden.

```
bluemix billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

<dl>
  <dt>GROUP_NAME (erforderlich)</dt>
  <dd>Name der Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum durch Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

## bluemix billing resource-instances-usage
{: #bluemix_billing_resource_instances_usage}
 
 Monatliche Nutzung für Ressourceninstanzen unter dem aktuellen Konto anzeigen
 
 ```
 bluemix billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
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


## bluemix plugin repos
{: #bluemix_plugin_repos}

Alle Plug-in-Repositorys auflisten, die in der Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} registriert sind.

```
bluemix plugin repos
```

<strong>Voraussetzungen</strong>: Keine


## bluemix plugin repo-add
{: #bluemix_plugin_repo_add}

Neues Plug-in-Repository zur Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} hinzufügen.

```
bluemix plugin repo-add REPO_NAME REPO_URL
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
bluemix plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## bluemix plugin repo-remove
{: #bluemix_plugin_repo_remove}

Plug-in-Repository aus der {{site.data.keyword.Bluemix_notm}}-CLI entfernen.

```
bluemix plugin repo-remove REPO_NAME
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
bluemix plugin repo-remove bluemix-repo
```


## bluemix plugin repo-plugins
{: #bluemix_plugin_repo_plugins}

Alle verfügbaren Plug-ins in allen hinzufügten Repositorys oder einem bestimmten Repository auflisten.

```
bluemix plugin repo-plugins [-r REPO_NAME]
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
bluemix plugin repo-plugins
```

Alle Plug-ins im Repository `bluemix-repo` auflisten:

```
bluemix plugin repo-plugins -r bluemix-repo
```

## bluemix plugin repo-plugin
{: #bluemix_plugin_repo_plugin}

Details eines Plug-ins im Repository anzeigen.

```
bluemix plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen:</strong>

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Der Name des Repositorys. Wird kein Repository angegeben, verwendet der Befehl das Standardrepository des Plug-ins.</dd>
   </dl>

<strong>Beispiele</strong>:

Details von Plug-in "container-service" im Repository 'Bluemix' auflisten:

```
bluemix plugin repo-plugin container-service -r Bluemix
```

Details von Plug-in "container-service" im Standardrepository 'Bluemix' auflisten

```
bluemix plugin repo-plugin container-service -r Bluemix
```


## bluemix plugin list
{: #bluemix_plugin_list}

Alle installierten Plug-ins in der {{site.data.keyword.Bluemix_notm}}-CLI auflisten.

```
bluemix plugin list
```

<strong>Voraussetzungen</strong>: Keine

## bluemix plugin show
{: #bluemix_plugin_show}

Details eines installierten Plug-ins anzeigen

```
bluemix plugin show PLUGIN-NAME
```

<strong>Voraussetzungen</strong>: Keine


## bluemix plugin install
{: #bluemix_plugin_install}

Angegebene Version des Plug-ins aus dem angegebenen Pfad oder Repository in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle installieren.

```
bluemix plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
bluemix plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
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
    
    
Die {{site.data.keyword.Bluemix_notm}}-CLI trägt den offiziellen Repository-Namen 'Bluemix'.    

<strong>Beispiele</strong>:

Plug-in von der lokalen Datei installieren:

```
bluemix plugin install /downloads/new_plugin
```

Plug-in von der Remote URL installieren:

```
bluemix plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Plug-in 'container-service' der neuesten Version aus dem Repository 'Bluemix' installieren:

```
bluemix plugin install container-service -r Bluemix
```
Plug-in 'container-service' mit der Version '0.1.425' aus dem offiziellen Plug-in-Repository installieren:

```
bluemix plugin install container-service -v 0.1.425
```

## bluemix plugin update
{: #bluemix_plugin_update}

Upgrade des Plug-ins aus einem Repository durchführen.

```
bluemix plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
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
bluemix plugin update -r Bluemix
```

Upgrade des Plug-ins 'container-service' im offiziellen Plug-in-Repository auf die neueste Version durchführen:

```
bluemix plugin update container-service
```

Plug-in 'container-service' im offiziellen Plug-in-Repository auf Version '0.1.440' aktualisieren:

```
bluemix plugin update container-service -v 0.1.440
```

## bluemix plugin uninstall
{: #bluemix_plugin_uninstall}

Angegebenes Plug-in in der {{site.data.keyword.Bluemix_notm}}-CLI deinstallieren.

```
bluemix plugin uninstall PLUGIN_NAME
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
bluemix plugin uninstall container-service
```
