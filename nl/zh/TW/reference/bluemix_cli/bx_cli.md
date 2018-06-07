---



copyright:

  years: 2015, 2018
lastupdated: "2018-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} (ibmcloud) 指令
{: #ibmcloud_cli}

版本：0.6.7

{{site.data.keyword.Bluemix_notm}} 指令行介面 (CLI) 提供一組依名稱空間分組的指令，讓使用者與 {{site.data.keyword.Bluemix_notm}} 互動。

從 0.5.0 版開始，{{site.data.keyword.Bluemix_notm}} 指令行用戶端已將 Cloud Foundry 指令行用戶端搭載在其安裝中。如果您已安裝自己的 cf cli，請不要在相同環境定義中使用自己的安裝的 {{site.data.keyword.Bluemix_notm}} CLI 指令 `ibmcloud [command]` 及 Cloud Foundry CLI 指令 `cf [command]`。如果您要使用 cf cli 來管理 {{site.data.keyword.Bluemix_notm}} CLI 環境定義中的 Cloud Foundry 資源，請改為使用 `ibmcloud cf [command]`。請注意，不容許 `ibmcloud cf api/login/logout/target`，必須改為使用 `ibmcloud api/login/logout/target`。

到 2018 年五月為止，{{site.data.keyword.Bluemix_notm}} CLI 指令已從 `bluemix` 和 `bx` 變更為 `ibmcloud`。不過，您仍然可以使用 `bluemix` 和 `bx` CLI 指令，直到未來它們被淘汰為止。
{: tip}

以下列出 {{site.data.keyword.Bluemix_notm}} CLI 所支援的詳細指令，包括其名稱、引數、選項、必要條件、說明及範例。
{:shortdesc}

**附註：***必要條件* 列出使用指令之前需要哪些動作。沒有必要動作的指令會列為**無**。否則，必要條件可能包括下列一個以上的動作：

<dl>
<dt>端點</dt>
<dd>必須透過 <code>ibmcloud api</code> 設定 API 端點後，才能使用這個指令。</dd>
<dt>登入</dt>
<dd>需要使用 <code>ibmcloud login</code> 指令進行登入後，才能使用這個指令。如果是使用聯合 ID 進行登入，請使用 '--sso' 選項以一次性密碼進行鑑別，或使用 '--apikey' 以 API 金鑰進行鑑別。移至 {{site.data.keyword.Bluemix_notm}} 主控台**管理** &gt; **安全** &gt; **平台 API 金鑰**，以建立 API 金鑰。
</dd>
<dt>目標</dt>
<dd>必須使用 <code>ibmcloud target</code> 指令來設定組織及空間後，才能使用這個指令。</dd>
<dt>Docker</dt>
<dd>必須先安裝 Docker CLI (docker)，才能執行這個指令。</dd>
</dl>


請使用下表中的索引來參照常用的 ibmcloud 指令。

## 一般 ibmcloud 指令
{: #ibmcloud_commands_index}

<table summary="一般 ibmcloud 指令。">
<caption>表 1. 一般 ibmcloud 指令</caption>
 <thead>
 <th colspan="5">一般 ibmcloud 指令</th>
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

 ## 用來管理及配置 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構服務的指令 (ibmcloud sl)
  {: #ibmcloud_commands_softlayer}

用來管理 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構的指令已合併至 {{site.data.keyword.Bluemix_notm}} CLI。如需使用 {{site.data.keyword.Bluemix_notm}} CLI 配置及管理 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構服務的相關資訊，請參閱：[{{site.data.keyword.Bluemix_notm}} CLI {{site.data.keyword.BluSoftlayer_notm}} 基礎架構 (ibmcloud sl) 指令](/docs/cli/reference/softlayer/index.md#softlayer_cli)。

 ## 用來管理帳戶、組織及角色的指令
 {: #ibmcloud_commands_account}

<table summary="您可以用來管理帳戶、組織、空間及角色的 ibmcloud 指令。">
<caption>表 2. 用來管理帳戶、組織、空間及角色的指令</caption>
 <thead>
 <th colspan="5">用來管理帳戶、組織、空間及角色的指令</th>
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
 <td>[ibmcloud account users-delete](bx_cli.html#ibmcloud_account_users_delete)</td>
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
  <td>[ibmcloud iam access-group-policy-create](bx_cli.html#ibmcloud_iam_access-group-policy-create)</td>
  <td>[ibmcloud iam access-group-policy-update](bx_cli.html#ibmcloud_iam_access-group-policy-update)</td>
  <td>[ibmcloud iam access-group-policy-delete](bx_cli.html#ibmcloud_iam_access-group-policy-delete)</td>
 </tr>
 </tbody>
 </table>


 ## 用來管理資源群組及資源的指令
{: #ibmcloud_commands_resource}

<table summary="您可以用來管理資源群組及資源的 ibmcloud 指令。">
  <caption>表 3. 用來管理資源群組及資源的指令</caption>
  <thead>
    <th colspan="5">用來管理資源群組及資源的指令</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](bx_cli.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](bx_cli.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-update](bx_cli.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](bx_cli.html#ibmcloud_resource_quotas)</td>
      <td>[ibmcloud resource quota](bx_cli.html#ibmcloud_resource_quota)</td>
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
    </tr>
    <tr>
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
    </tr>
  </tbody>
</table>


 ## 用來管理 API 金鑰及原則的指令
 {: #ibmcloud_commands_iam}
 <table summary="您可以用來管理 API 金鑰及原則的 ibmcloud 指令。">
 <caption>表 3. 用來管理 API 金鑰及原則的指令</caption>
  <thead>
  <th colspan="5">用來管理 API 金鑰及原則的指令</th>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-id](bx_cli.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](bx_cli.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](bx_cli.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](bx_cli.html#ibmcloud_iam_service_id_delete)</td>
   <td>[ibmcloud iam service-ids](bx_cli.html#ibmcloud_iam_service_ids)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-keys](bx_cli.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](bx_cli.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](bx_cli.html#ibmcloud_iam_api_key_delete)</td>
   <td>[ibmcloud iam api-key-update](bx_cli.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam service-api-keys](bx_cli.html#ibmcloud_iam_service_api_keys)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key](bx_cli.html#ibmcloud_iam_service_api_key)</td>
   <td>[ibmcloud iam service-api-key-create](bx_cli.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](bx_cli.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](bx_cli.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-policies](bx_cli.html#ibmcloud_iam_service_policies)</td>
  </tr>
  <tr>
    <td>[ibmcloud iam service-policy](bx_cli.html#ibmcloud_iam_service_policy)</td>
    <td>[ibmcloud iam service-policy-create](bx_cli.html#ibmcloud_iam_service_policy_create)</td>
    <td>[ibmcloud iam service-policy-update](bx_cli.html#ibmcloud_iam_service_policy_update)</td>
    <td>[ibmcloud iam service-policy-delete](bx_cli.html#ibmcloud_iam_service_policy_delete)</td>
    <td>[ibmcloud iam user-policies](bx_cli.html#ibmcloud_iam_user_policies)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policy](bx_cli.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](bx_cli.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](bx_cli.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](bx_cli.html#ibmcloud_iam_user_policy_delete)</td>
   <td>[ibmcloud iam oauth-tokens](bx_cli.html#ibmcloud_iam_oauth_tokens)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam dedicated-id-disconnect](bx_cli.html#ibmcloud_iam_dedicated_id_disconnect)</td>
     <td>[ibmcloud iam authorization-policy-create](bx_cli.html#ibmcloud_iam_authorization_policy_create)</td>
     <td>[ibmcloud iam authorization-policy-delete](bx_cli.html#ibmcloud_iam_authorization_policy_delete)</td>
     <td>[ibmcloud iam authorization-policy](bx_cli.html#ibmcloud_iam_authorization_policy)</td>
     <td>[ibmcloud iam authorization-policies](bx_cli.html#ibmcloud_iam_authorization_policies)</td>
  </tr>
  </tbody>
  </table>

 ## 用來管理 cf 應用程式及應用程式相關網域、路徑和憑證的指令
 {: #ibmcloud_commands_apps}

<table summary="您可以用來管理 cf 應用程式及應用程式相關網域、路徑和憑證的 ibmcloud 指令。">
<caption>表 4. 用來管理 cf 應用程式及應用程式相關網域、路徑和憑證的指令</caption>
 <thead>
 <th colspan="5">用來管理 cf 應用程式及應用程式相關網域、路徑和憑證的指令</th>
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

 ## 用來管理 {{site.data.keyword.Bluemix_notm}} 服務的指令
 {: #ibmcloud_commands_services}

<table summary="您可以用來管理 {{site.data.keyword.Bluemix_notm}} 服務的 ibmcloud 指令。">
<caption>表 5. 用來管理 {{site.data.keyword.Bluemix_notm}} 服務的指令</caption>
 <thead>
 <th colspan="5">用來管理 {{site.data.keyword.Bluemix_notm}} 服務的指令</th>
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


 ## 用來管理型錄、外掛程式及帳單設定的指令
 {: #ibmcloud_commands_settings}

<table summary="您可以用來管理 {{site.data.keyword.Bluemix_notm}} 型錄、外掛程式、帳單及安全設定的 ibmcloud 指令。">
<caption>表 6. 用來管理 {{site.data.keyword.Bluemix_notm}} 型錄、外掛程式、帳單及安全設定的指令</caption>
 <thead>
 <th colspan="5">用來管理 {{site.data.keyword.Bluemix_notm}} 型錄、外掛程式、帳單及安全設定的指令</th>
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
  <td>[ibmcloud billing resource-group-usage](bx_cli.html#ibmcloud_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](bx_cli.html#ibmcloud_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

## ibmcloud help
{: #ibmcloud_help}
顯示 {{site.data.keyword.Bluemix_notm}} CLI 之第一層內建指令及所支援名稱空間的一般說明，或特定內建指令或名稱空間的說明。

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>COMMAND|NAMESPACE（選用）</dt>
   <dd>顯示其說明的指令或名稱空間。如果未指定，則會顯示 {{site.data.keyword.Bluemix_notm}} CLI 的一般說明。</dd>
   </dl>



<strong>範例</strong>：

顯示 {{site.data.keyword.Bluemix_notm}} CLI 的一般說明：

```
ibmcloud help
```

顯示 `info` 指令的說明：

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
設定或檢視 {{site.data.keyword.Bluemix_notm}} API 端點。

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>API_ENDPOINT（選用）</dt>
   <dd>設為目標的 API 端點，例如 `https://api.chinabluemix.net`。 如果未同時指定 *API_ENDPOINT* 及 `--unset` 選項，則會顯示現行 API 端點。</dd>
   <dt>--unset（選用）</dt>
   <dd>移除 API 端點設定。</dd>
   <dt>--skip-ssl-validation（選用）</dt>
   <dd>略過 HTTP 要求的 SSL 驗證。</dd>
   </dl>
<strong>範例</strong>：

將 API 端點設為 api.chinabluemix.net：

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinaibmcloud.net --skip-ssl-validation
```

檢視現行 API 端點：

```
ibmcloud api
```

取消設定 API 端點：

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


將預設值寫入配置檔。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>用於 HTTP 要求的逾時值。預設值為 60 秒。</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>追蹤對終端機或指定檔案的 HTTP 要求。</dd>
   <dt>--color true|false</dt>
   <dd>啟用或停用彩色輸出。依預設，會啟用彩色輸出。</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>設定預設語言環境。如果 LOCALE 為 <i>CLEAR</i>，則會刪除先前的語言環境。</dd>
   <dt>--check-version true|false</dt>
   <dd>啟用或停用 CLI 版本檢查。</dd>
   </dl>

一次只能指定其中一個選項。

<strong>範例</strong>：

將 HTTP 要求逾時值設為 30 秒：

```
ibmcloud config --http-timeout 30
```

啟用 HTTP 要求的追蹤輸出：

```
ibmcloud config --trace true
```

追蹤對指定檔案 */home/usera/my_trace* 的 HTTP 要求：

```
ibmcloud config --trace /home/usera/my_trace
```

停用彩色輸出：

```
ibmcloud config --color false
```

將語言環境設為 zh_Hans：

```
ibmcloud config --locale zh_Hans
```

清除語言環境設定：

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

檢視基本 {{site.data.keyword.Bluemix_notm}} 資訊，包括現行地區、雲端控制器版本以及部分有用端點（例如用於登入及交換存取記號的端點）。

```
ibmcloud info
```

<strong>必要條件</strong>：端點


## ibmcloud cf
{: #ibmcloud_cf}

呼叫內嵌的 CF CLI

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>-q, --quiet</dt>
  <dd>關閉「呼叫 cf 指令...」訊息</dd>
</dl>

<strong>範例</strong>：

列出 cf 應用程式：

```
ibmcloud cf apps
```

列出 cf 服務，但沒有「呼叫 cf 指令...」訊息：

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

登入使用者。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>必要條件</strong>：無

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>指令選項</strong>：
<dl>
  <dt> -a <i>API_ENDPOINT</i>（選用）</dt>
  <dd> API 端點（例如：api.ng.bluemix.net）</dd>
  <dt> --apikey <i>API_KEY 或 @API_KEY_FILE_PATH</i>
  <dd> API 金鑰內容，或透過 @ 指出的 API 金鑰檔案的路徑</dd>
  <dt> --sso（選用）</dt>
  <dd> 使用一次性密碼進行登入</dd>
  <dt> -u <i>USERNAME</i>（選用）</dt>
  <dd> 使用者名稱</dd>
  <dt> -p <i>PASSWORD</i>（選用）</dt>
  <dd> 密碼</dd>
  <dt> -c <i>ACCOUNT_ID</i>（選用）</dt>
  <dd> 目標帳戶的 ID</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional)</dt>
  <dd> 目標資源群組的名稱</dd>
  <dt> -o <i>ORG</i>（選用）</dt>
  <dd> 目標組織的名稱（已淘汰，請使用 'ibmcloud target -o ORG'）</dd>
  <dt> -s <i>SPACE</i>（選用）</dt>
  <dd> 目標空間的名稱（已淘汰，請使用 'ibmcloud target -s SPACE'）</dd>
  <dt> --no-iam </dt>
  <dd> 強制向登入伺服器進行鑑別，而非公用 IAM</dd>
  <dt> --skip-ssl-validation（選用）</dt>
  <dd> 略過 HTTP 要求的 SSL 驗證。不建議使用這個選項。</dd>
</dl>

<strong>範例</strong>：

#### 互動式登入

```
ibmcloud login
```

以使用者名稱及密碼登入，並設定目標帳戶、組織及空間：

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

以一次性密碼登入，並設定目標帳戶、組織及空間：

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

以 API 金鑰登入，並設定目標：

#### API 金鑰具有關聯的帳戶

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API 金鑰沒有關聯的帳戶

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>附註：</strong>如果 API 金鑰具有關聯的帳戶，則不容許切換至另一個帳戶。

#### 使用一次性密碼

```
ibmcloud login -u UserID --sso
```

CLI 接著會提供 URL 鏈結，並要求密碼：
```
一次性密碼（從 https://URL_Link_To_Obtain_Passcode 取得）：
```

在瀏覽器中開啟鏈結，這會引導您取得密碼。在主控台中鍵入給定的密碼，您應該就可以登入。

## ibmcloud logout
{: #ibmcloud_logout}

登出使用者。

```
ibmcloud logout
```

<strong>必要條件</strong>：無

## ibmcloud regions
{: #ibmcloud_regions}

檢視 {{site.data.keyword.Bluemix_notm}} 上所有地區的資訊。

```
ibmcloud regions
```

<strong>必要條件</strong>：端點


## ibmcloud target
{: #ibmcloud_target}


設定或檢視目標帳戶、地區、組織或空間。

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-r <i>REGION_NAME</i>（選用）</dt>
   <dd>要切換至的地區名稱，例如 'us-south' 或 'eu-gb'。</dd>
   <dt>-c <i>ACCOUNT_ID</i>（選用）</dt>
   <dd>要設為目標的帳戶 ID。</dd>
   <dt>-g <i>RESOURCE_GROUP</i>（選用）</dt>
   <dd>資源群組的名稱。</dd>
   <dt>--cf</dt>
   <dd>以互動方式選取目標組織及空間</dd>
   <dt>-o <i>ORG_NAME</i>（選用）</dt>
   <dd>要設為目標的組織名稱。</dd>
   <dt>-s <i>SPACE_NAME</i>（選用）</dt>
   <dd>要設為目標的空間名稱。</dd>
   </dl>
如果未指定選項，則會顯示現行帳戶、地區、組織及空間。



<strong>範例</strong>：

設定現行帳戶、組織及空間：

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

切換至新的地區：

```
ibmcloud target -r eu-gb
```

檢視現行帳戶、地區、組織及空間：

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

將 CLI 更新為最新版本。

```
ibmcloud update [-f]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>-f</dt>
  <dd>強制更新，而不進行確認。需要 root 專用權。</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

列出所有組織

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-r <i>REGION</i>（選用）</dt>
   <dd>顯示其組織資訊的地區。如果設為 'all'，則會列出所有地區中的所有組織。</dd>
   <dt>--guid（選用）</dt>
   <dd>顯示組織的 GUID。</dd>
   </dl>

<strong>範例</strong>：

列出 `us-south` 地區中的所有組織，並顯示 GUID

```
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

顯示所指定組織的資訊。

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>--guid（選用）</dt>
   <dd>顯示組織的 GUID。</dd>
   </dl>

<strong>範例</strong>：

顯示 `IBM` 組織的資訊，並顯示 GUID

```
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

建立新的組織。只有帳戶擁有者才能執行此作業。

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>所要建立之組織的名稱。</dd>
   <dt>-f</dt>
   <dd>強制建立，而不進行確認。</dd>
   </dl>

<strong>範例</strong>：

建立名稱為 `IBM` 的組織。

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

將組織從現行地區抄寫到另一個地區。

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>要抄寫之現有組織的名稱。</dd>
   <dt>REGION_NAME（必要）</dt>
   <dd>管理所抄寫組織的地區名稱。</dd>
   </dl>

<strong>範例</strong>：

將組織 `myorg` 抄寫到地區 `eu-gb`：

```
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

重新命名組織。只有組織管理員才能執行此作業。

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>OLD_ORG_NAME（必要）</dt>
   <dd>要重新命名之組織的舊名稱。</dd>
   <dt>NEW_ORG_NAME（必要）</dt>
   <dd>組織重新命名後的新名稱。</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

列出所有空間

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>指令選項</strong>：
   <dl>
   <dt>-o</dt>
   <dd>組織名稱。列出所指定組織下的空間。如果未指定，則預設為現行組織。</dd>
   <dt>-r</dt>
   <dd>地區名稱。列出所指定地區下的空間。如果未指定，則預設為現行地區。</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

這個指令的功能及選項與 [cf space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} 指令相同。


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

這個指令的功能及選項與 [cf create-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 指令相同。


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


這個指令的功能及選項與 [cf rename-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 指令相同。


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


這個指令的功能及選項與 [cf delete-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 指令相同。

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

依角色顯示指定組織中的使用者。

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>ORG_NAME（必要）</dt>
<dd>組織的名稱。</dd>
<dt>-a（選用）</dt>
<dd>列出指定組織中的所有使用者，而不依角色分組。</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

將使用者新增至組織（需要組織管理員）。

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

從組織移除使用者（僅限組織管理員或使用者自己）

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>指令選項</strong>：
<dl>
<dt>--force, -f</dt>
<dd>強制刪除，而不確認。</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

取得現行使用者的所有組織角色

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>-u</dt>
   <dd>使用者 ID。如果未指定，則預設為現行使用者。</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

將組織角色指派給使用者。只有組織管理員才能執行此作業。

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所指派之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>ORG_ROLE（必要）</dt>
   <dd>獲指派此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
  </dl>

<strong>範例</strong>：

以 `OrgManager` 角色，將使用者 `Mary` 指派給組織 `IBM`：

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**附註**：您可以使用 CLI 設定組織/空間角色，但如果您要設定其他許可權，則必須利用使用者介面。如需進一步詳細資料，請參閱[指派使用者存取權](/docs/iam/assignaccess.html#assignaccess)。<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

移除使用者的組織角色。只有組織管理員才能執行此作業。

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所要移除之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>ORG_ROLE（必要）</dt>
   <dd>從中移除此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
    </dl>

<strong>範例</strong>：

以 `OrgManager` 角色，從組織 `IBM` 移除使用者 `Mary`：

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

依角色顯示指定空間中的使用者。

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>空間的名稱。</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

將空間角色指派給使用者。只有空間管理員才能執行此作業。

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所指派之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>獲指派此使用者之空間的名稱。</dd>
   <dt>SPACE_ROLE（必要）</dt>
   <dd>獲指派此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
    </dl>

<strong>範例</strong>：

以 `SpaceManager` 角色，將使用者 `Mary` 指派給組織 `IBM` 及空間 `Cloud`：

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

移除使用者的空間角色。只有空間管理員才能執行此作業。

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所要移除之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>從中移除此使用者之空間的名稱。</dd>
   <dt>SPACE_ROLE（必要）</dt>
   <dd>從中移除此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
    </dl>


<strong>範例</strong>：

以 `SpaceManager` 角色，從組織 `IBM` 及空間 `Cloud` 移除使用者 `Mary`：

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

列出現行使用者的所有帳戶

```
ibmcloud account list
```

<strong>必要條件</strong>：端點、登入


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

顯示所指定組織的帳戶（需要組織使用者）

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--guid（選用）</dt>
  <dd>僅顯示帳戶 ID</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

顯示與帳戶相關聯的使用者。只有帳戶擁有者才能執行此作業。

```
ibmcloud account users
```

## ibmcloud account user-delete
{: #ibmcloud_account_user_delete}

從現行帳戶刪除使用者（僅限帳戶擁有者）

```
ibmcloud account user-delete USERNAME [-c ACCOUNT_ID] [-f]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>USERNAME（必要）</dt>
<dd>使用者名稱</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>帳戶 ID。如果未指定，則預設為現行帳戶。</dd>
<dt>--force, -f（選用）</dt>
<dd>強制刪除，而不確認。</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

邀請使用者加入帳戶（帳戶管理者）

```
ibmcloud account user-invite USER_EMAIL
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所邀請之使用者的電子郵件。</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

將邀請重新傳送給使用者（帳戶管理者）

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所重新邀請之使用者的電子郵件</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

列出現行帳戶下的存取群組

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-u</dt>
  <dd>列出使用者所屬的存取群組。此旗標與 '-s' 互斥。</dd>
  <dt>-s</dt>
  <dd>列出服務 ID 所屬的存取群組。此旗標與 '-u' 互斥。</dd>
</dl>

<strong>範例</strong>：

列出所有存取群組：

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

顯示存取群組的詳細資料

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-id</dt>
  <dd>僅顯示 ID</dd>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 的詳細資料：

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

建立存取群組

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-d, --description</dt>
  <dd>存取群組的說明</dd>
</dl>

<strong>範例</strong>：

建立存取群組 `example_group`：

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

更新存取群組

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-n, --name</dt>
  <dd>新的存取群組名稱</dd>
  <dt>-d, --description</dt>
  <dd>新的說明</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將存取群組 `example_group` 重新命名為 `hello_world_group`：

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

刪除存取群組

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
  <dt>-r, --recursive</dt>
  <dd>刪除存取群組及其成員</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group`：

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

列出存取群組中的使用者

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有使用者：

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

將使用者新增至存取群組

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 新增至存取群組 `example_group`：

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

從存取群組移除使用者

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

從所有存取群組移除使用者

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除使用者 `name@example.com`：

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

列出存取群組中的服務 ID

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有服務 ID：

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

將服務 ID 新增至存取群組

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 新增至存取群組 `example_group`：

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

從存取群組移除服務 ID

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

從所有存取群組移除服務 ID

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除服務 ID `example-service`：

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

列出存取群組的原則

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 的所有原則：

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

顯示存取群組原則的詳細資料

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 之原則 `51b9717e-76b0-4f6a-bda7-b8132431f926` 的詳細資料：

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

建立存取群組原則

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>-roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-service-instance</dt>
  <dd>原則定義的服務實例。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '-f, --file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '-f, --file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔建立存取群組原則：

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

針對 `us-south` 地區中 `sample-service` 實例 `ServiceId-ade78e9f` 的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

更新存取群組原則

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>-v, --version</dt>
  <dd>原則的版本</dd>
  <dt>-roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-service-instance</dt>
  <dd>原則定義的服務實例。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '-f, --file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '-f, --file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '-f, --file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

以原則 JSON 檔案中的原則來更新存取群組原則：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

更新存取群組原則，以針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

更新存取群組原則，以針對 `us-south` 地區中 `sample-service` 實例 `ServiceId-ade78e9f` 的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south
```

更新存取群組原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新存取群組原則，以針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

更新存取群組原則，以針對具有 ID `dda27e49d2a1efca58083a01dfde18f6` 的資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

刪除存取群組原則

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group` 的原則 `51b9717e-76b0-4f6a-bda7-b8132431f926`：
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

列出所有服務 ID

```
ibmcloud iam service-ids --uuid
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--uuid</dt>
  <dd>僅顯示服務 ID 的 UUID</dd>
</dl>

<strong>範例</strong>：列出現行帳戶下所有服務 ID 的 UUID：

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

顯示服務 ID 的詳細資料

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME|UUID（必要）</dt>
  <dd>服務的名稱或 UUID</dd>
  <dt>--uuid</dt>
  <dd>顯示服務 ID 的 UUID</dd>
</dl>

<strong>範例</strong>：

顯示服務 ID `sample-test` 的詳細資料

```
ibmcloud iam service-id sample-test
```
顯示服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的詳細資料

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

建立服務 ID

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務 ID 的說明</dd>
</dl>

<strong>範例</strong>：

建立服務名稱為 `sample-test` 且說明為 `hello, world!` 的服務 ID

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
更新服務 ID

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME|UUID（必要）</dt>
  <dd>服務的名稱或 UUID</dd>
  <dt>-n, --name</dt>
  <dd>服務的新名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務的新說明</dd>
  <dt>-v, --version</dt>
  <dd>服務 ID 的版本</dd>
  <dt>-f, --force</dt>
  <dd>更新而不進行確認</dd>
</dl>

<strong>範例</strong>：

將服務 ID `sample-test` 重新命名為 `sample-test-2`，而不進行確認

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

更新服務 `sample-test` 版本 `1-0jn39fbefew` 的說明

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!' -v 1-0jn39fbefew
```

將服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 重新命名為 `sample-test-3`，並具有新的說明

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

刪除服務 ID

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME|UUID（必要）</dt>
  <dd>服務的名稱或 UUID</dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務 ID `sample-teset`，而不進行確認

```
ibmcloud iam service-id-delete sample-teset -f
```

刪除服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

列出所有 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰

```
ibmcloud iam api-keys
```

<strong>必要條件</strong>：端點、登入

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

建立新的 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要建立之 API 金鑰的名稱。</dd>
<dt>-d <i>DESCRIPTION</i>（選用）</dt>
<dd>API 金鑰的說明</dd>
<dt>--file <i>FILE</i></dt>
<dd>將 API 金鑰資訊儲存至指定的檔案。如果未設定，則會顯示 JSON 內容。</dd>
</dl>

<strong>範例</strong>：

建立 API 金鑰，並儲存至檔案

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

更新 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰

```
ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要更新之 API 金鑰的舊名稱。</dd>
<dt>-n <i>NAME</i>（選用）</dt>
<dd>API 金鑰的新名稱</dd>
<dt>-d <i>DESCRIPTION</i>（選用）</dt>
<dd>API 金鑰的新說明</dd>
</dl>

<strong>範例</strong>：

更新 API 金鑰的說明：

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_api_key_delete}

刪除 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰

```
ibmcloud iam api-key-delete NAME [-f]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要刪除之 API 金鑰的名稱。</dd>
<dt>-f（選用）</dt>
<dd>強制刪除，而不確認。</dd>
</dl>

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

列出服務的所有 API 金鑰

```
ibmcloud iam service-api-keys SERVICE_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務 API 金鑰而不進行確認</dd>
</dl>

<strong>範例</strong>：

列出服務 `sample-service` 的所有 API 金鑰：

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

列出服務 API 金鑰的詳細資料

```
ibmcloud iam service-api-key NAME SERVICE_ID [--uuid] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>--uuid</dt>
  <dd>顯示服務 API 金鑰的 UUID</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務 API 金鑰而不進行確認</dd>
</dl>

<strong>範例</strong>：

顯示服務 `sample-service` 的服務 API 金鑰 `sample-key` 的詳細資料：

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

建立服務 API 金鑰

```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>-d, --description</dt>
  <dd>API 金鑰的說明</dd>
  <dt>--file</dt>
  <dd>將 API 金鑰資訊儲存至指定的檔案。如果未設定，則會顯示 JSON 內容。</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：

建立服務 `sample-service` 的服務 API 金鑰 `sample-key`，而不進行確認：

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

更新服務 API 金鑰

```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>-n, --name</dt>
  <dd>服務 API 金鑰的新名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務 API 金鑰的新說明</dd>
  <dt>-v, --version</dt>
  <dd>服務 API 金鑰的版本</dd>
  <dt>-f, --force</dt>
  <dd>更新而不進行確認</dd>
</dl>

<strong>範例</strong>：

將服務 API 金鑰 `sample-key` 重新命名為 `new-sample-key`：

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

刪除服務 API 金鑰

```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務 API 金鑰 `sample-key`：

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

列出使用者 `name@example.com` 的原則：

```
ibmcloud iam user-policies name@example.com
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
</dl>

<strong>範例</strong>：

列出使用者 `name@example.com` 的原則：

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

顯示使用者原則的詳細資料

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>POLICY_ID（必要）</dt>
<dd>原則的 ID</dd>
</dl>

<strong>範例</strong>：

列出使用者 `name@example.com` 的原則 `0bb730daa`：

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

建立使用者原則

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>--file <i>FILE</i>（選用）</dt>
<dd>原則定義的 JSON 檔案</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（選用）</dt>
<dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（選用）</dt>
<dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i>（選用）</dt>
<dd>原則定義的服務實例。這與 '--file' 旗標不能同時使用。</dd>
<dt>--region <i>REGION</i>（選用）</dt>
<dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（選用）</dt>
<dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource <i>RESOURCE</i>（選用）</dt>
<dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（選用）</dt>
<dd>資源群組的名稱。這與 '--file'、'--resource' 及 '--resource-group-id' 旗標不能同時使用。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（選用）</dt>
<dd>資源群組的 ID。這與 '--file'、'--resource' 及 '--resource-group-name' 旗標不能同時使用。</dd>
</dl>

<strong>範例</strong>：

從原則 JSON 檔案 `policy.json`，建立使用者 `name@example.com` 的使用者原則：

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

針對 `us-south` 地區中範例服務實例 `ServiceId-ade78e9f` 的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

更新使用者原則

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>POLICY_ID（必要）</dt>
<dd>要更新之原則的 ID</dd>
<dt>-v, --version <i>VERSION</i>（選用）</dt>
<dd>現有原則的版本</dd>
<dt>--file <i>FILE</i>（選用）</dt>
<dd>原則定義的 JSON 檔案</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（選用）</dt>
<dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（選用）</dt>
<dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE</i>（選用）</dt>
<dd>原則定義的服務實例。這與 '--file' 旗標不能同時使用。</dd>
<dt>--region <i>REGION</i>（選用）</dt>
<dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（選用）</dt>
<dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource <i>RESOURCE</i>（選用）</dt>
<dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（選用）</dt>
<dd>資源群組的名稱。這與 '--file'、'--resource' 及 '--resource-group-id' 旗標不能同時使用。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（選用）</dt>
<dd>資源群組的 ID。這與 '--file'、'--resource' 及 '--resource-group-name' 旗標不能同時使用。</dd>
</dl>

<strong>範例</strong>：

將使用者原則更新為 JSON 檔案中的使用者原則：

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

更新使用者原則，以針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 更新使用者原則，以針對 `us-south` 地區中範例服務實例 `ServiceId-ade78e9f` 的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance ServiceId-ade78e9f --region us-south --resource-type key --resource key123
```

更新使用者原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新使用者原則，以針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

更新使用者原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```



## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

列出指定服務的所有服務原則

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>-json</dt>
  <dd>以 JSON 格式顯示原則</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務原則而不進行確認</dd>
</dl>

<strong>範例</strong>：

列出服務 `test` 的原則：

```
ibmcloud iam service-policies test
```
列出服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

顯示服務原則的詳細資料

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>-json</dt>
  <dd>以 JSON 格式顯示原則</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務原則而不進行確認</dd>
</dl>

<strong>範例</strong>：

顯示服務 `test` 的原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
顯示服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

建立服務原則

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案。這與 '-r, --roles'、'--service-name'、'--service-instance'、'--region'、'--resource-type'、'--resource'、'--resource-group-name' 及 '--resource-group-id' 旗標不能同時使用。</dd>
  <dt>-r, --roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>--service-name</dt>
  <dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--service-instance</dt>
  <dd>原則定義的服務實例。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-type</dt>
  <dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource</dt>
  <dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
  <dt>-f, --force</dt>
  <dd>建立服務原則而不進行確認</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，建立服務 `test` 的服務原則：

```
ibmcloud iam service-policy-create test --file @policy.json
```
從 JSON 檔案，建立服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的服務原則：

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

更新服務原則

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>-v, --version</dt>
  <dd>服務原則的版本</dd>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案。這與 '-r, --roles'、'--service-name'、'--service-instance'、'--region'、'--resource-type'、'--resource'、'resource-group-name' 及 'resource-group-id' 旗標不能同時使用。</dd>
  <dt>-r, --roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-service-instance</dt>
  <dd>原則定義的服務實例。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
  <dt>-f, --force</dt>
  <dd>更新服務原則而不進行確認</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，更新服務 `test` 的服務原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
從 JSON 檔案，更新服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的服務原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

刪除服務原則

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除測試 `test` 的原則 `140798e2-8ea7db3`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
刪除服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則 `140798e2-8ea7db3`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

擷取並顯示現行階段作業的 OAuth 記號

```
ibmcloud iam oauth-tokens
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

重新整理並顯示 OAuth 記號

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

中斷公用 IBM ID 與專用非 IBM ID 的連線

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制中斷連線，而不進行確認</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

建立授權原則以容許某個服務實例存取另一個服務實例。

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME] ROLE_NAME1,ROLE_NAME2...
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>可獲得授與存取權的來源服務。</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>可授與來源服務存取權的目標服務。</dd>
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>來源服務實例名稱，如果未指定的話，將會授與所有來源服務實例的存取權。</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>目標服務實例名稱，如果未指定的話，將會授與所有目標服務實例的存取權。</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>提供來源服務存取權的角色。</dd>  
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

刪除授權原則。

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要刪除的授權原則 ID。</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認。</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

顯示授權原則的詳細資料。

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要顯示的授權原則 ID。</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

列出現行帳戶下的授權原則。

```
ibmcloud iam authorization-policies
```

<strong>必要條件</strong>：登入、目標


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

列出資源群組。

```
ibmcloud resource groups [--default]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--default</dt>
  <dd>取得現行帳戶的預設群組。</dd>
</dl>

<strong>範例</strong>：

列出目前設為目標的帳戶下的所有資源群組：

```
ibmcloud resource groups
```

列出目前設為目標的帳戶的預設群組：

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

顯示資源群組的詳細資料

```
ibmcloud resource group NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>資源群組的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID</dd>
</dl>

<strong>範例</strong>：

顯示資源群組 `example-group`：

```
ibmcloud resource group example-group
```

僅顯示資源群組 `example-group` 的 ID：

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

更新現有資源群組

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>目標資源群組的名稱</dd>
  <dt>-n, --name</dt>
  <dd>資源群組的新名稱</dd>
  <dt>-q, --quota</dt>
  <dd>新配額定義的名稱</dd>
  <dt>-f</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將資源群組 `example-group` 重新命名為 `trial-group`：

```
ibmcloud resource group-update example-group -n trial-group
```

將資源群組 `example-group` 的配額變更為 `free`：

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配額定義

```
ibmcloud resource quotas
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出所有配額定義：

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

顯示配額定義的詳細資料

```
ibmcloud resource quota NAME
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>配額名稱</dd>
</dl>

<strong>範例</strong>：顯示配額 `free` 的詳細資料：

```
ibmcloud resource quota free
```


## ibmcloud app push
{: #ibmcloud_app_push}

這個指令的功能及選項與 [cf push ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} 指令相同。


## ibmcloud app list
{: #ibmcloud_app_list}

這個指令的功能及選項與 [cf apps ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} 指令相同。


## ibmcloud app show
{: #ibmcloud_app_show}

這個指令的功能及選項與 [cf app ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} 指令相同。


## ibmcloud app delete
{: #ibmcloud_app_delete}

這個指令的功能及選項與 [cf delete ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} 指令相同。


## ibmcloud app rename
{: #ibmcloud_app_rename}

這個指令的功能及選項與 [cf rename ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} 指令相同。


## ibmcloud app start
{: #ibmcloud_app_start}

這個指令的功能及選項與 [cf start ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} 指令相同。


## ibmcloud app stop
{: #ibmcloud_app_stop}

這個指令的功能及選項與 [cf stop ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} 指令相同。


## ibmcloud app restart
{: #ibmcloud_app_restart}

這個指令的功能及選項與 [cf restart ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} 指令相同。


## ibmcloud app restage
{: #ibmcloud_app_restage}


這個指令的功能及選項與 [cf restage ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} 指令相同。


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


這個指令的功能及選項與 [cf restart-app-instance ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} 指令相同。


## ibmcloud app events
{: #ibmcloud_app_events}

這個指令的功能及選項與 [cf events ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} 指令相同。


## ibmcloud app files
{: #ibmcloud_app_files}

這個指令的功能及選項與 [cf files ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} 指令相同。


## ibmcloud app logs
{: #ibmcloud_app_logs}

這個指令的功能及選項與 [cf logs ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} 指令相同。


## ibmcloud app env
{: #ibmcloud_app_env}

這個指令的功能及選項與 [cf env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} 指令相同。


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

這個指令的功能及選項與 [cf set-env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} 指令相同。


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

這個指令的功能及選項與 [cf unset-env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} 指令相同。


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

這個指令的功能及選項與 [cf stacks ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} 指令相同。


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

這個指令的功能及選項與 [cf stack ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} 指令相同。


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

這個指令的功能及選項與 [cf create-app-manifest ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} 指令相同。

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

列出網域的憑證資訊。

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>DOMAIN_NAME（必要）</dt>
<dd>管理憑證的網域。</dd>
</dl>


<strong>範例</strong>：

檢視網域 `ibmcxo-eventconnect.com` 的憑證資訊：

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

將憑證新增到現行組織中的指定網域。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要新增憑證的網域。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>（必要）</dt>
   <dd>私密金鑰檔案路徑。</dd>
   <dt>-c <i>CERT_FILE</i>（必要）</dt>
   <dd>憑證檔案路徑。</dd>
   <dt>-p <i>PASSWORD</i>（選用）</dt>
   <dd>憑證的密碼。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>（選用）</dt>
   <dd>中繼憑證檔案路徑。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>（選用）</dt>
   <dd>信任儲存庫檔案。</dd>
   </dl>


<strong>範例</strong>：

將憑證新增到網域 `ibmcxo-eventconnect.com`：

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

從現行組織中的指定網域移除憑證。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要從中移除憑證的網域。</dd>
   <dt>-f（選用）</dt>
   <dd>強制刪除，而不確認。</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

這個指令的功能及選項與 [cf routes ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} 指令相同。


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

這個指令的功能及選項與 [cf check-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} 指令相同。


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

將路徑對映到具有所指定網域及主機名稱的現有 cf 應用程式或容器群組。

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必要）</dt>
   <dd>要與路徑對映之 cf 應用程式或容器群組的名稱。</dd>
   <dt>DOMAIN（必要）</dt>
   <dd>路徑的網域。例如，mychinabluemix.net 或 chinabluemix.net。</dd>
   <dt>-n <i>HOST_NAME</i>（選用）</dt>
   <dd>路徑的主機名稱。如果未提供，則依預設會將主機名稱設為應用程式名稱或容器群組名稱。</dd>
   </dl>

<strong>範例</strong>：

將路徑對映到具有指定網域的 `my-app`：

```
ibmcloud app route-map my-app mychinabluemix.net
```

將路徑對映到具有指定網域及主機名稱的 'my-container-group'：

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

從現有的 cf 應用程式或容器群組中取消對映指定的路徑。

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必要）</dt>
   <dd>cf 應用程式或容器群組的名稱。</dd>
   <dt>DOMAIN（必要）</dt>
   <dd>路徑的網域（例如 mychinabluemix.net 或 chinabluemix.net）。</dd>
   <dt>-n <i>HOST_NAME</i>（選用）</dt>
   <dd>路徑的主機名稱。如果未提供，則依預設會將主機名稱設為應用程式名稱或容器群組名稱。</dd>
   </dl>

<strong>範例</strong>：

從 `my-app` 取消對映 `my-app.mychinabluemix.net`：

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

從 `my-container-group` 取消對映 `abc.chinabluexmix.net`：

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

這個指令的功能及選項與 [cf create-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} 指令相同。


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

這個指令的功能及選項與 [cf delete-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} 指令相同。


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

這個指令的功能及選項與 [cf delete-orphaned-routes ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} 指令相同。


## ibmcloud app domains
{: #ibmcloud_app_domains}

這個指令的功能及選項與 [cf domains ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} 指令相同。


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

這個指令的功能及選項與 [cf create-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} 指令相同。


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

這個指令的功能及選項與 [cf delete-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} 指令相同。


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

這個指令的功能及選項與 [cf create-shared-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} 指令相同。


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

這個指令的功能及選項與 [cf delete-shared-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} 指令相同。


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


這個指令的功能及選項與 [cf marketplace ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window} 指令相同。


## ibmcloud service list
{: #ibmcloud_service_list}

這個指令的功能及選項與 [cf services ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window} 指令相同。


## ibmcloud service show
{: #ibmcloud_service_show}

這個指令的功能及選項與 [cf service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window} 指令相同。


## ibmcloud service create
{: #ibmcloud_service_create}

這個指令的功能及選項與 [cf create-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window} 指令相同。


## ibmcloud service update
{: #ibmcloud_service_update}

這個指令的功能及選項與 [cf update-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window} 指令相同。


## ibmcloud service delete
{: #ibmcloud_service_delete}

這個指令的功能及選項與 [cf delete-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window} 指令相同。


## ibmcloud service rename
{: #ibmcloud_service_rename}

這個指令的功能及選項與 [cf rename-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window} 指令相同。


## ibmcloud service bind
{: #ibmcloud_service_bind}

這個指令的功能及選項與 [cf bind-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window} 指令相同。


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

這個指令的功能及選項與 [cf unbind-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window} 指令相同。


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

這個指令的功能及選項與 [cf create-service-key ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window} 指令相同。


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

這個指令的功能及選項與 [cf delete-service-key ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window} 指令相同。


## ibmcloud service keys
{: #ibmcloud_service_keys}

這個指令的功能及選項與 [cf service-keys ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window} 指令相同。


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

這個指令的功能及選項與 [cf service-key ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window} 指令相同。


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

這個指令的功能及選項與 [cf create-user-provided-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window} 指令相同。


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

這個指令的功能及選項與 [cf update-user-provided-service ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window} 指令相同。


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服務實例

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--service-name</dt>
  <dd>隸屬服務的名稱</dd>
  <dt>--location</dt>
  <dd>依位置過濾</dd>
  <dt>--long</dt>
  <dd>顯示輸出中的其他欄位</dd>
</dl>

<strong>範例</strong>：

列出服務 `test-service` 的服務實例：

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

顯示服務實例的詳細資料

```
ibmcloud resource service-instance NAME [--location LOCATION] [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務實例的名稱</dd>
  <dt>--location</dt>
  <dd>依位置過濾</dd>
  <dt>--id</dt>
  <dd>顯示服務實例的 ID</dd>
</dl>

<strong>範例</strong>：顯示服務實例 `my-service-instance` 的詳細資料：

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

建立服務實例

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務實例的名稱</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必要）</dt>
  <dd>服務的名稱或 ID</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必要）</dt>
  <dd>服務方案的名稱或 ID</dd>
  <dt>LOCATION</dt>
  <dd>用於建立服務實例的目標位置或環境</dd>
  <dt>-t, --tags</dt>
  <dd>標籤</dd>
  <dt>-p, --parameters</dt>
  <dd>要建立服務實例之參數的 JSON 檔案或 JSON 字串</dd>
  <dt>-d, --deployment</dt>
  <dd>部署的名稱</dd>
</dl>

<strong>範例</strong>：在位置 `eu-gb` 上使用服務 `test-service` 的服務方案 `test-service-plan`，建立名為 `my-service-instance` 的服務實例：

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服務實例

```
ibmcloud resource service-instance-update SERVICE_INSTANCE_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_INSTANCE_NAME（必要）</dt>
  <dd>服務實例的名稱</dd>
  <dt>-n, --name</dt>
  <dd>新的服務實例名稱</dd>
  <dt>-t, --tags</dt>
  <dd>新標籤</dd>
  <dt>--service-plan-id</dt>
  <dd>新的服務方案 ID</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：更新服務實例 `my-service-instance`，並將其名稱變更為 `new-service-instance`：

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

刪除服務實例

```
ibmcloud resource service-instance-delete NAME [-f, --force] [--recursive]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
  <dt>--recursive</dt>
  <dd>刪除所有隸屬資源</dd>
</dl>

<strong>範例</strong>：刪除資源服務實例 `my-service-instance`：

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

顯示與服務別名的連結

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS（必要）</dt>
  <dd>服務別名</dd>
</dl>

<strong>範例</strong>：顯示與服務別名 `my-service-alias` 的資源連結：

```
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

顯示服務連結的詳細資料

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID。會抑制服務連結的所有其他輸出。</dd>
</dl>

<strong>範例</strong>：顯示服務別名 `my-service-alias` 與應用程式 `my-app` 之間服務連結的詳細資料：

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

建立服務連結

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>ROLE_NAME</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--service-id</dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameter</dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：以 `Administrator` 角色，建立服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

刪除服務連結

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：刪除服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服務實例或服務別名的服務金鑰

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>服務實例 ID</dd>
  <dt>--instance-name</dt>
  <dd>服務實例名稱</dd>
  <dt>--alias-id</dt>
  <dd>服務別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>服務別名</dd>
</dl>

<strong>範例</strong>：列出服務實例 `my-service-instance` 的服務金鑰：

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

顯示服務金鑰的詳細資料

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>--id</dt>
  <dd>顯示服務金鑰的 ID</dd>
</dl>

<strong>範例</strong>：顯示服務金鑰 `my-service-key` 的詳細資料：

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

建立服務金鑰

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>ROLE_NAME</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--instance-id</dt>
  <dd>服務實例 ID</dd>
  <dt>--instance-name</dt>
  <dd>服務實例名稱</dd>
  <dt>--alias-id</dt>
  <dd>服務別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>服務別名</dd>
  <dt>--service-id</dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：以 `Administrator` 角色，為服務實例 `my-service-instance` 建立名為 `my-service-key` 的服務金鑰：

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

刪除服務金鑰

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：刪除服務金鑰 `my-service-key`：

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服務實例的別名

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>隸屬服務實例的 ID。</dd>
  <dt>--instance-name</dt>
  <dd>隸屬服務實例的名稱。</dd>
</dl>

<strong>範例</strong>：列出服務實例 `my-service-instance` 的服務別名：
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

顯示服務別名的詳細資料

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示給定服務別名的 ID。會抑制別名的所有其他輸出。</dd>
</dl>

<strong>範例</strong>：顯示服務別名 `my-service-alias` 的詳細資料：
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

建立服務實例的別名

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>--instance-id</dt>
  <dd>隸屬服務實例的 ID。</dd>
  <dt>--instance-name</dt>
  <dd>隸屬服務實例的名稱。</dd>
  <dt>-s</dt>
  <dd>在其中建立別名的空間名稱。預設為現行空間。</dd>
  <dt>-t, --tags</dt>
  <dd>標籤清單。</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串。</dd>
</dl>

<strong>範例</strong>：為服務實例 `my-service-instance`，建立名為 `my-service-alias` 的服務別名：
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服務別名

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>-n, --name</dt>
  <dd>服務別名的新名稱。</dd>
  <dt>-t, --tags</dt>
  <dd>標籤清單。</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串。</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行使用者確認。</dd>
</dl>

<strong>範例</strong>：更新服務別名 `my-service-alias`，並將其名稱變更為 `new-service-alias`：

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

刪除服務別名

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：刪除服務別名 `my-service-alias`：

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
使用 Lucene 查詢語法來搜尋資源

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-offset, --o</dt>
  <dd>開始的資源位置號碼</dd>
  <dt>-limit, --l</dt>
  <dd>要傳回的資源數（上限為 10000）</dd>
</dl>

<strong>範例</strong>：搜尋名稱開頭為指定文字的 Cloud Foundry 應用程式：

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

搜尋指定服務名稱的 Cloud Foundry 服務實例：

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

在組織中搜尋具有指定 ID 的 Cloud Foundry 服務連結：

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

搜尋具有指定名稱且位於兩個指定地區之一的 Cloud Foundry 空間：

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

在具有指定 ID 的 Cloud Foundry 空間中，搜尋名稱包含 dev 一字的資源：

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

搜尋指定位置（亦即 us-south 地區）中的資源控制器資源：

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

在具有指定 ID 的資源群組中搜尋資源或別名：

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

搜尋名稱為 default 的資源群組：

```
ibmcloud resource search 'name:default AND type:resource-group'
```

搜尋指定服務名稱的資源連結：

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

搜尋具有指定「雲端資源名稱 (CRN)」的資源：

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

搜尋具有指定標籤的資源：

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud catalog search
{: #ibmcloud_catalog_search}

搜尋型錄項目

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-r, --region</dt>
  <dd>指定要在其中搜尋的地理區域。目前僅支援 "us-south" 及 "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>依資源類型過濾。目前僅支援 "service-cf"、"iaas"、"runtime"、"template" 及 "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>依價格過濾。目前僅支援 "free"、"paygo" 及 "bluemix-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>依標籤過濾。</dd>
  <dt>--sort-by</dt>
  <dd>內容排序方式</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"</dd>
  <dt>--reverse</dt>
  <dd>是否反轉排序順序</dd>
  <dt>--json</dt>
  <dd>輸出原始 JSON 回應</dd>
  <dt>--csv</dt>
  <dd>輸出 CSV 檔案</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

搜尋服務 `Automation test`：

```
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

取得型錄項目

```
ibmcloud catalog entry ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--children</dt>
  <dd>取得型錄項目的所有子項</dd>
  <dt>--json</dt>
  <dd>輸出原始 JSON 回應</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

取得 ID 為 `a0ef1-d3b4j0` 的項目：

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
建立新型錄項目（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-p, --parent</dt>
  <dd>物件的母項 ID</dd>
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，建立母項 ID 為 `a0ef1-d3b4j0` 的資源：

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
更新現有型錄項目（僅限帳戶的型錄管理者或編輯者）

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，更新資源 `j402-dnf1i`：

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
刪除型錄項目（僅限帳戶的型錄管理者）
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

刪除資源 `j402-dnf1i`：

```
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
取得型錄項目的可見性（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-json</dt>
  <dd>輸出原始 JSON 回應</dd>
  <dt>-global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

取得廣域範圍中資源 `j402-dnf1i` 的可見性：

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
更新現有型錄項目的可見性（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>

  <dt>--includes-add</dt>
  <dd>將帳戶（或逗點區隔的帳戶清單）新增至 includes 清單，並授與項目的可見性。可接受電子郵件或帳戶 GUID</dd>
  <dt>--includes-remove</dt>
  <dd>從 includes 清單中移除帳戶（或逗點區隔的帳戶清單），並撤銷項目的可見性。可接受電子郵件或帳戶 GUID</dd>  
  <dt>--excludes-add</dt>
  <dd>將帳戶（或逗點區隔的帳戶清單）新增至 excludes 清單。可接受電子郵件或帳戶 GUID</dd>
  <dt>--excludes-remove</dt>
  <dd>從 excludes 清單中移除帳戶（或逗點區隔的帳戶清單），並撤銷項目的可見性。如果帳戶是由廣域管理者所設定，則帳戶管理者無法移除該帳戶。可接受電子郵件或帳戶 GUID</dd>
  <dt>--owner</dt>
  <dd>變更物件的擁有者。可接受電子郵件或帳戶 GUID。</dd>
  <dt>--restrict</dt>
  <dd>將可見性物件的限制變更為「專用」</dd>
  <dt>--unrestrict</dt>
  <dd>將可見性物件的限制變更為「公用」</dd>  
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，設定資源 `j402-dnf1i` 的可見性：

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
列出 Marketplace 中的服務供應項目

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--cf</dt>
  <dd>僅顯示 Cloud Foundry 服務</dd>
  <dt>--rc</dt>
  <dd>僅顯示 RC 相容服務</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

顯示廣域範圍中的服務供應項目：

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

檢視 IBM Cloud 上的樣板範本。

```
ibmcloud catalog templates [-d]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>-d（選用）</dt>
   <dd>如果指定 <i>-d</i> 選項，也會顯示每個範本的說明。否則，只會顯示每一個範本的 ID 及名稱。</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

檢視所指定樣板範本的詳細資訊。

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>TEMPLATE_ID（必要）</dt>
   <dd>樣板範本的 ID。請使用 <i>ibmcloud templates</i> 來檢視所有範本的 ID。</dd>
   </dl>


<strong>範例</strong>：

檢視範本 `mobileBackendStarter` 的詳細資料：

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

以指定的 URL 及說明，建立根據所指定範本的 cf 應用程式。依預設，新的應用程式會自動啟動。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
   <dl>
   <dt>TEMPLATE_ID（必要）</dt>
   <dd>應用程式在建立時將根據的範本。請使用 <i>ibmcloud templates</i> 來查看所有範本 ID。</dd>
   <dt>CF_APP_NAME（必要）</dt>
   <dd>要建立之 cf 應用程式的名稱。</dd>
   <dt>-u <i>URL</i>（選用）</dt>
   <dd>應用程式的路徑。如果未指定，{{site.data.keyword.Bluemix_notm}} 會自動根據應用程式名稱及預設網域來設定路徑。</dd>
   <dt>-d <i>DESCRIPTION</i>（選用）</dt>
   <dd>應用程式的說明。</dd>
   <dt>--no-start（選用）</dt>
   <dd>建立應用程式之後，不要自動將它啟動。如果未指定，應用程式會在建立之後自動啟動。</dd>
   </dl>


<strong>範例</strong>：

根據 `javaHelloWorld` 範本建立 cf 應用程式 `my-app`：

```
ibmcloud catalog template-run javaHelloWorld my-app
```

根據 `rubyHelloWorld` 範本建立應用程式 `my-ruby-app`，路徑為 `myrubyapp.chinabluemix.net`，說明為 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`：

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

根據 `pythonHelloWorld` 範本建立應用程式 `my-python-app`，不自動啟動：

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

以您選擇的格式取得地區的選擇子集。

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>指令選項</strong>：

<dl>
  <dt>-i, --id</dt>
  <dd>依 ID 指定地理位置。</dd>
  <dt>-k, --kind</dt>
  <dd>取得指定類型的項目清單。</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"。</dd>
  <dt>--json</dt>
  <dd>原始 JSON 回應的輸出。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作。</dd>
  <dt>--csv</dt>
  <dd>輸出 CSV 檔案</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

檢視運行環境的詳細資料。這個指令僅適用於公用雲端。

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>範例</strong>：

顯示運行環境 "nodejsHelloWorld" 的詳細資料：

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

列出所有運行環境。這個指令僅適用於公用雲端。

```
ibmcloud catalog runtimes [-d]
```

<strong>指令選項</strong>：

<dl>
  <dt>-d</dt>
  <dd>顯示每個運行環境的說明</dd>
</dl>

<strong>範例</strong>：

列出所有運行環境及其說明：

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

顯示現行帳戶的每月用量（僅限帳戶管理者）

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--json（選用）</dt>
  <dd>以 JSON 格式顯示用量結果。</dd>
</dl>

<strong>範例</strong>：

顯示現行帳戶在 2016-06 的用量和費用報告：

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

顯示組織的每月用量（僅限帳戶管理者或組織帳單管理員）

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>ORG_NAME（必要）</dt>
  <dd>組織的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--json（選用）</dt>
  <dd>以 JSON 格式顯示用量結果。</dd>
</dl>


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

顯示資源群組的每月用量（僅帳戶管理者或資源群組管理者）

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>GROUP_NAME（必要）</dt>
  <dd>資源群組的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--json（選用）</dt>
  <dd>以 JSON 格式顯示用量結果。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

顯示現行帳戶下的每月資源實例用量。

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-o ORG_NAME（選用）</dt>
  <dd>依組織過濾實例。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>依資源群組過濾實例。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示以 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--json（選用）</dt>
  <dd>以 JSON 格式顯示用量結果。</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中登錄的所有外掛程式儲存庫。

```
ibmcloud plugin repos
```

<strong>必要條件</strong>：無


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

將新的外掛程式儲存庫新增至 {{site.data.keyword.Bluemix_notm}} CLI。

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>REPO_NAME（必要）</dt>
   <dd>要新增之儲存庫的名稱。您可以自行為每一個儲存庫定義名稱。</dd>
   <dt>REPO_URL（必要）</dt>
   <dd>要新增之儲存庫的 URL。儲存庫 URL 必須包含通訊協定（例如，http://plugins.ng.bluemix.net 而非 plugins.ng.bluemix.net）。http://plugins.ng.bluemix.net 是 {{site.data.keyword.Bluemix_notm}} CLI 的正式外掛程式儲存庫。</dd>
    </dl>


<strong>範例</strong>：

將 {{site.data.keyword.Bluemix_notm}} CLI 的正式外掛程式儲存庫新增為 `bluemix-repo`：

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

從 {{site.data.keyword.Bluemix_notm}} CLI 移除外掛程式儲存庫。

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>REPO_NAME（必要）</dt>
   <dd>要移除之儲存庫的名稱。</dd>
   </dl>

<strong>範例</strong>：

從 {{site.data.keyword.Bluemix_notm}} CLI 移除 `bluemix-repo` 儲存庫：

```
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

列出所有已新增之儲存庫或特定儲存庫中的所有可用外掛程式。

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>只列出指定儲存庫中的外掛程式。</dd>
   </dl>

<strong>範例</strong>：

列出所有已新增之儲存庫中的所有外掛程式：

```
ibmcloud plugin repo-plugins
```

列出 `bluemix-repo` 儲存庫中的所有外掛程式：

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

顯示儲存庫中外掛程式的詳細資料。

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>儲存庫的名稱。如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫。</dd>
   </dl>

<strong>範例</strong>：

列出儲存庫 "sample-repo" 中外掛程式 "IBM-Containers" 的詳細資料：

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

列出預設儲存庫中外掛程式 "IBM-Containers" 的詳細資料

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中的所有已安裝外掛程式。

```
ibmcloud plugin list
```

<strong>必要條件</strong>：無

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

顯示已安裝外掛程式的詳細資料。

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>必要條件</strong>：無


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

從指定的路徑或儲存庫，將特定版本的外掛程式安裝到 {{site.data.keyword.Bluemix_notm}} CLI 中。

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。如果未指定版本，則指令會選取最新可用的版本來進行安裝。

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME（必要）</dt>
   <dd>如果未指定 -r <i>REPO_NAME</i>，則會從指定的本端路徑或遠端 URL 來安裝外掛程式。</dd>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>外掛程式二進位檔所在儲存庫的名稱。如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。
</dd>
   <dt>-v <i>VERSION</i>（選用）</dt>
   <dd>要安裝之外掛程式的版本。如果未提供，將安裝最新版本的外掛程式。只有從儲存庫安裝外掛程式時，此選項才有效。</dd>
   <dt>-f</dt>
   <dd>強制安裝外掛程式，而不進行確認。</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI 具有的正式儲存庫名稱為 `Bluemix`。

<strong>範例</strong>：

從本端檔案安裝外掛程式：

```
ibmcloud plugin install /downloads/new_plugin
```

從遠端 URL 安裝外掛程式：

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

從 'Bluemix' 儲存庫安裝最新版本的 'container-service' 外掛程式：

```
ibmcloud plugin install container-service -r Bluemix
```

還是只用：

```
ibmcloud plugin install container-service
```

從正式外掛程式儲存庫中安裝 '0.1.425' 版的 'container-service' 外掛程式：

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

從儲存庫升級外掛程式。

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。
如果未指定版本，則指令會選取最新可用的版本來進行安裝。

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>要更新之外掛程式的名稱。如果未指定，則這個指令會檢查所有已安裝外掛程式的升級。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>外掛程式二進位檔所在儲存庫的名稱。如果未指定，則指令會使用預設的外掛程式儲存庫 'Bluemix'。</dd>
 <dt>-v <i>VERSION</i>（選用）</dt>
 <dd>外掛程式要更新到的目標版本。如果未提供，便將外掛程式更新至最新的可用版本。</dd>
 <dt>--all</dt>
 <dd>更新所有可用的外掛程式</dd>
</dl>

<strong>範例</strong>：

檢查正式外掛程式儲存庫 'Bluemix' 中的所有可用升級：

```
ibmcloud plugin update -r Bluemix
```

還是只用：

```
ibmcloud plugin update
```

將正式外掛程式儲存庫中的外掛程式 'container-service' 升級至最新：

```
ibmcloud plugin update container-service
```

將正式外掛程式儲存庫中的外掛程式 'container-service' 更新至 '0.1.440' 版：

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

從 {{site.data.keyword.Bluemix_notm}} CLI 解除安裝指定的外掛程式。

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>PLUGIN_NAME（必要）</dt>
   <dd>要解除安裝之外掛程式的名稱。</dd>
    </dl>

<strong>範例</strong>：

解除安裝先前安裝的 'container-service' 外掛程式：

```
ibmcloud plugin uninstall container-service
```
