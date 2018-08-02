---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-13"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} (ibmcloud) 命令
{: #bluemix_cli}


{{site.data.keyword.Bluemix_notm}} 命令行界面 (CLI) 提供了一组按名称空间分组的命令，供用户用于与 {{site.data.keyword.Bluemix_notm}} 进行交互。

{{site.data.keyword.Bluemix_notm}} 命令行客户机在其安装中捆绑了 Cloud Foundry 命令行客户机。如果您已安装 cf CLI，请勿在同一上下文中同时使用 {{site.data.keyword.Bluemix_notm}} CLI 命令 `ibmcloud [command]` 和您自己安装的 Cloud Foundry CLI 命令 `cf [command]`。如果要在 {{site.data.keyword.Bluemix_notm}} CLI 上下文中使用 cf CLI 来管理 Cloud Foundry 资源，请改为使用 `ibmcloud cf [command]`。请注意，不允许使用 `ibmcloud cf api/login/logout/target`，必须改为使用 `ibmcloud api/login/logout/target`。

从 2018 年 5 月起，{{site.data.keyword.Bluemix_notm}} CLI 命令已从 `bluemix` 和 `bx` 更改为 `ibmcloud`。但是，您仍然可以使用 `bluemix` 和 `bx` CLI 命令，直到未来某个日期这些命令被除去为止。
{: tip}

下面列出了 {{site.data.keyword.Bluemix_notm}} CLI 支持的命令的详细用法，包括命令名称、自变量、选项、先决条件、描述和示例。
{:shortdesc}

**注：***先决条件*列出使用命令前必须执行的操作。没有任何先决条件操作的命令会列出**无**。否则，先决条件可能会包含以下一个或多个操作：

<dl>
<dt>端点</dt>
<dd>使用此命令之前，必须通过 <code>bluemix api</code> 设置 API 端点。</dd>
<dt>登录</dt>
<dd>使用此命令之前，必须使用 <code>bluemix login</code> 命令登录。如果使用联合标识登录，请使用“--sso”选项通过一次性密码进行认证，或者使用“--apikey”通过 API 密钥进行认证。转至 {{site.data.keyword.Bluemix_notm}} 控制台的**管理** &gt; **安全性** &gt; **平台 API 密钥**以创建 API 密钥。
</dd>
<dt>目标</dt>
<dd>使用此命令之前，必须使用 <code>bluemix target</code> 命令来设置组织和空间。</dd>
<dt>Docker</dt>
<dd>必须安装 Docker CLI (docker) 才能运行此命令。</dd>
</dl>


使用下表中的索引可查看常用 ibmcloud 命令。

## 常规 ibmcloud 命令
{: #bx_commands_index}

<table summary="常规 ibmcloud 命令。">
<caption>表 1. 常规 ibmcloud 命令</caption>
 <thead>
 <th colspan="5">常规 ibmcloud 命令</th>
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

 ## 用于管理和配置 {{site.data.keyword.BluSoftlayer_notm}} 基础架构服务 (ibmcloud sl) 的命令
  {: #bx_commands_softlayer}

用于管理 {{site.data.keyword.BluSoftlayer_notm}} 基础架构的命令已合并到 {{site.data.keyword.Bluemix_notm}} CLI 中。有关使用 {{site.data.keyword.Bluemix_notm}} CLI 来配置和管理 {{site.data.keyword.BluSoftlayer_notm}} 基础架构服务的更多信息，请参阅：[{{site.data.keyword.Bluemix_notm}} CLI {{site.data.keyword.BluSoftlayer_notm}} 基础架构 (ibmcloud sl) 命令](/docs/cli/reference/softlayer/index.html#softlayer_cli)。

 ## 用于管理帐户、组织和角色的命令
 {: #bx_commands_account}

<table summary="可用于管理帐户、组织、空间和角色的 ibmcloud 命令。">
<caption>表 2. 用于管理帐户、组织、空间和角色的命令</caption>
 <thead>
 <th colspan="5">用于管理帐户、组织、空间和角色的命令</th>
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


 ## 用于管理资源组和资源的命令
{: #bx_commands_resource}

<table summary="可用于管理资源组和资源的 ibmcloud 命令。">
  <caption>表 3. 用于管理资源组和资源的命令</caption>
  <thead>
    <th colspan="5">用于管理资源组和资源的命令</th>
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


 ## 用于管理 API 密钥和策略的命令
 {: #bx_commands_iam}
 <table summary="可用于管理 API 密钥和策略的 ibmcloud 命令。">
 <caption>表 4. 用于管理 API 密钥和策略的命令</caption>
  <thead>
  <th colspan="5">用于管理 API 密钥和策略的命令</th>
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

 ## 用于管理 CF 应用程序及与应用程序相关的域、路径和证书的命令
 {: #bx_commands_apps}

<table summary="可用于管理 CF 应用程序及与应用程序相关的域、路径和证书的 ibmcloud 命令。">
<caption>表 5. 用于管理 CF 应用程序及与应用程序相关的域、路径和证书的命令</caption>
 <thead>
 <th colspan="5">用于管理 CF 应用程序及与应用程序相关的域、路径和证书的命令</th>
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

 ## 用于管理 {{site.data.keyword.Bluemix_notm}} 服务的命令
 {: #bx_commands_services}

<table summary="可用于管理 {{site.data.keyword.Bluemix_notm}} 服务的 ibmcloud 命令。">
<caption>表 6. 用于管理 {{site.data.keyword.Bluemix_notm}} 服务的命令</caption>
 <thead>
 <th colspan="5">用于管理 {{site.data.keyword.Bluemix_notm}} 服务的命令</th>
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


 ## 用于管理目录、插件和帐单设置的命令
 {: #bx_commands_settings}

<table summary="可用于管理 {{site.data.keyword.Bluemix_notm}} 目录、插件、帐单和安全设置的 ibmcloud 命令。">
<caption>表 7. 用于管理 {{site.data.keyword.Bluemix_notm}} 目录、插件、帐单和安全设置的命令</caption>
 <thead>
 <th colspan="5">用于管理 {{site.data.keyword.Bluemix_notm}} 目录、插件、帐单和安全设置的命令</th>
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

 ## 管理 Cloud Foundry Enterprise Environments（试验性）
{: #bx_commands_cfee}

<table summary="管理 Cloud Foundry Enterprise Environments（试验性）">
<caption>表 8. 管理 Cloud Foundry Enterprise Environments（试验性）</caption>
 <thead>
 <th colspan="5">管理 Cloud Foundry Enterprise Environments（试验性）</th>
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
显示 {{site.data.keyword.Bluemix_notm}} CLI 第一级内置命令和受支持名称空间的一般帮助，或者显示特定内置命令或名称空间的帮助。

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>COMMAND|NAMESPACE（可选）</dt>
   <dd>显示其帮助信息的命令或名称空间。如果未指定，将显示 {{site.data.keyword.Bluemix_notm}} CLI 的一般帮助。</dd>
   </dl>



<strong>示例</strong>：

显示 {{site.data.keyword.Bluemix_notm}} CLI 的一般帮助：

```
ibmcloud help
```

显示 `info` 命令的帮助：

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
设置或查看 {{site.data.keyword.Bluemix_notm}} API 端点。

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
   <dl>
   <dt>API_ENDPOINT（可选）</dt>
   <dd>作为目标的 API 端点，例如 `https://api.chinabluemix.net`。如果未指定 *API_ENDPOINT* 和 `--unset` 选项，将显示当前 API 端点。</dd>
   <dt>--unset（可选）</dt>
   <dd>除去 API 端点设置。</dd>
   <dt>--skip-ssl-validation（可选）</dt>
   <dd>绕过 HTTP 请求的 SSL 验证。</dd>
   </dl>
<strong>示例</strong>：

将 API 端点设置为 api.chinabluemix.net：

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

查看当前 API 端点：

```
ibmcloud api
```

取消设置 API 端点：

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


将缺省值写入配置文件。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>HTTP 请求的超时值。缺省值为 60 秒。</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>跟踪对终端或指定文件的 HTTP 请求。</dd>
   <dt>--color true|false</dt>
   <dd>启用或禁用颜色输出。缺省情况下，会启用颜色输出。</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>设置缺省语言环境。如果 LOCALE 为 <i>CLEAR</i>，将删除先前的语言环境。</dd>
   <dt>--check-version true|false</dt>
   <dd>启用或禁用 CLI 版本检查。</dd>
   </dl>

一次只能指定其中一个选项。

<strong>示例</strong>：

将 HTTP 请求超时设置为 30 秒：

```
ibmcloud config --http-timeout 30
```

启用 HTTP 请求的跟踪输出：

```
ibmcloud config --trace true
```

跟踪对指定文件 */home/usera/my_trace* 的 HTTP 请求：

```
ibmcloud config --trace /home/usera/my_trace
```

禁用颜色输出：

```
ibmcloud config --color false
```

将语言环境设置为 zh_Hans：

```
ibmcloud config --locale zh_Hans
```

清除语言环境设置：

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

查看基本 {{site.data.keyword.Bluemix_notm}} 信息，包括当前区域、云控制器版本以及一些有用的端点，例如用于登录和交换访问令牌的端点。

```
ibmcloud info
```

<strong>先决条件</strong>：端点


## ibmcloud cf
{: #ibmcloud_cf}

调用嵌入式 CF CLI

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>-q, --quiet</dt>
  <dd>关闭消息“正在调用 cf 命令...”</dd>
</dl>

<strong>示例</strong>：

列出 CF 应用程序：

```
ibmcloud cf apps
```

列出 CF 服务，而不显示消息“正在调用 cf 命令...”：

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

用户登录。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>先决条件</strong>：无

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>命令选项</strong>：
<dl>
  <dt> -a <i>API_ENDPOINT</i>（可选）</dt>
  <dd> API 端点（例如：api.ng.bluemix.net）</dd>
  <dt> --apikey <i>API_KEY 或 @API_KEY_FILE_PATH</i>
  <dd> API 密钥内容或用 @ 指示的 API 密钥文件路径</dd>
  <dt> --sso（可选）</dt>
  <dd> 使用一次性密码登录</dd>
  <dt> -u <i>USERNAME</i>（可选）</dt>
  <dd> 用户名</dd>
  <dt> -p <i>PASSWORD</i>（可选）</dt>
  <dd> 密码</dd>
  <dt> -c <i>ACCOUNT_ID</i>（可选）</dt>
  <dd> 目标帐户的标识。此选项与 --no-account 互斥</dd>
  <dt> --no-account（可选）</dt>
  <dd> 强制在不使用帐户的情况下登录。建议不要使用此选项。此选项与 -c 互斥。</dd>
  <dt> -g <i>RESOURCE_GROUP</i>（可选）</dt>
  <dd> 目标资源组的名称</dd>
  <dt> -o <i>ORG</i>（可选）</dt>
  <dd> 目标组织的名称（不推荐，请使用“ibmcloud target -o ORG”）</dd>
  <dt> -s <i>SPACE</i>（可选）</dt>
  <dd> 目标空间的名称（不推荐，请使用“ibmcloud target -s SPACE”）</dd>
  <dt> --no-iam</dt>
  <dd> 强制向登录服务器（而不是公共 IAM）进行认证</dd>
  <dt> --skip-ssl-validation（可选）</dt>
  <dd> 绕过 HTTP 请求的 SSL 验证。建议不要使用此选项。</dd>
</dl>

<strong>示例</strong>：

#### 交互式登录

```
ibmcloud login
```

使用用户名和密码登录，并设置目标帐户、组织和空间：

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

使用一次性密码登录，并设置目标帐户、组织和空间

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

使用 API 密钥登录并设置目标：

#### API 密钥具有关联的帐户

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API 密钥没有关联的帐户

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>注：</strong>如果 API 密钥具有关联的帐户，那么不允许切换到其他帐户。

#### 使用一次性密码

```
ibmcloud login -u UserID --sso
```

然后，CLI 将提供一个 URL 链接并要求输入密码：
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

在浏览器中打开链接，该链接将引导您获取密码。在控制台中输入提供的密码，然后您应该能够登录。

## ibmcloud logout
{: #ibmcloud_logout}

注销用户。

```
ibmcloud logout
```

<strong>先决条件</strong>：无

## ibmcloud regions
{: #ibmcloud_regions}

查看 {{site.data.keyword.Bluemix_notm}} 上所有区域的信息。

```
ibmcloud regions
```

<strong>先决条件</strong>：端点


## ibmcloud target
{: #ibmcloud_target}


设置或查看目标帐户、区域、组织或空间。

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>-r <i>REGION_NAME</i>（可选）</dt>
   <dd>要切换到的区域的名称，例如“us-south”或“eu-gb”。</dd>
   <dt>-c <i>ACCOUNT_ID</i>（可选）</dt>
   <dd>要作为目标的帐户的标识。</dd>
   <dt>-g <i>RESOURCE_GROUP</i>（可选）</dt>
   <dd>资源组的名称</dd>
   <dt>--cf</dt>
   <dd>以交互方式选择目标组织和空间</dd>
   <dt>-o <i>ORG_NAME</i>（可选）</dt>
   <dd>要作为目标的组织的名称。</dd>
   <dt>-s <i>SPACE_NAME</i>（可选）</dt>
   <dd>要作为目标的空间的名称。</dd>
   </dl>
如果未指定任何选项，那么将显示当前帐户、区域、组织和空间。


<strong>示例</strong>：

设置当前帐户、组织和空间：

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

切换到新区域：

```
ibmcloud target -r eu-gb
```

查看当前帐户、区域、组织和空间：

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

将 CLI 更新到最新版本。

```
ibmcloud update [-f]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>-f</dt>
  <dd>强制更新而不确认。需要具备 root 用户特权。</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

列出所有组织

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>-r <i>REGION</i>（可选）</dt>
   <dd>显示其组织信息的区域。如果设置为“all”，将列出所有区域中的所有组织。</dd>
   <dt>--guid（可选）</dt>
   <dd>显示组织的 GUID。</dd>
   </dl>

<strong>示例</strong>：

列出区域 `us-south` 中的所有组织并显示 GUID

```
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

显示指定组织的信息。

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>--guid（可选）</dt>
   <dd>显示组织的 GUID。</dd>
   </dl>

<strong>示例</strong>：

显示组织 `IBM` 的信息并显示 GUID

```
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

创建新组织。此操作只能由帐户所有者执行。

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>要创建的组织的名称。</dd>
   <dt>-f</dt>
   <dd>强制创建而不确认。</dd>
   </dl>

<strong>示例</strong>：

创建名为 `IBM` 的组织。

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

将组织从当前区域复制到其他区域。

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>要复制的现有组织的名称。</dd>
   <dt>REGION_NAME（必需）</dt>
   <dd>托管所复制组织的区域的名称。</dd>
   </dl>

<strong>示例</strong>：

将组织 `myorg` 复制到区域 `eu-gb`：

```
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

重命名组织。此操作只能由组织管理员执行。

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>OLD_ORG_NAME（必需）</dt>
   <dd>要重命名的组织的旧名称。</dd>
   <dt>NEW_ORG_NAME（必需）</dt>
   <dd>组织要重命名为的新名称。</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

列出所有空间

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-o </dt>
   <dd>组织名称。列出指定组织下的空间。如果未指定，将缺省为当前组织。</dd>
   <dt>-r</dt>
   <dd>区域名称。列出指定区域下的空间。如果未指定，将缺省为当前区域。</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

此命令的功能和选项与 [cf space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} 命令的相同。


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

此命令的功能和选项与 [cf create-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 命令的相同。


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


此命令的功能和选项与 [cf rename-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 命令的相同。


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


此命令的功能和选项与 [cf delete-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 命令的相同。

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

按角色显示指定组织中的用户。

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>ORG_NAME（必需）</dt>
<dd>组织的名称。</dd>
<dt>-a（可选）</dt>
<dd>列出指定组织中的所有用户，但不按角色分组。</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

将用户添加到组织（需要组织管理员）。

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

从组织除去用户（仅限组织管理员或用户自己）

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>命令选项</strong>：
<dl>
<dt>--force, -f</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

获取当前用户的所有组织角色

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>-u</dt>
   <dd>用户标识。如果未指定，将缺省为当前用户。</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

向用户分配组织角色。此操作只能由组织管理员执行。

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要分配的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>ORG_ROLE（必需）</dt>
   <dd>要将此用户分配到的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
  </dl>

<strong>示例</strong>：

将用户 `Mary` 以 `OrgManager` 角色分配给组织 `IBM`：

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**注**：您可以使用 CLI 设置组织/空间角色，但是如果您想要设置其他许可权，那么必须使用 UI。有关进一步的详细信息，请参阅[分配用户访问权](/docs/iam/assignaccess.html#assignaccess)。<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

除去用户的组织角色。此操作只能由组织管理员执行。

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要除去的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>ORG_ROLE（必需）</dt>
   <dd>要将此用户从中除去的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
    </dl>

<strong>示例</strong>：

从组织 `IBM` 中除去用户 `Mary` 的 `OrgManager` 角色：

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

按角色显示指定空间中的用户。

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>空间的名称。</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

向用户分配空间角色。此操作只能由空间管理员执行。

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要分配的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>要将此用户分配到的空间的名称。</dd>
   <dt>SPACE_ROLE（必需）</dt>
   <dd>要将此用户分配到的空间角色的名称。例如：
   <ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
    </dl>

<strong>示例</strong>：

将用户 `Mary` 以 `SpaceManager` 角色分配给组织 `IBM` 和空间 `Cloud`：

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

除去用户的空间角色。此操作只能由空间管理员执行。

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要除去的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>要将此用户从中除去的空间的名称。</dd>
   <dt>SPACE_ROLE（必需）</dt>
   <dd>要将此用户从中除去的空间角色的名称。例如：
   <ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
    </dl>


<strong>示例</strong>：

从组织 `IBM` 和空间 `Cloud` 中除去用户 `Mary` 的 `SpaceManager` 角色：

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

列出当前用户的所有帐户

```
ibmcloud account list
```

<strong>先决条件</strong>：端点和登录


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

显示指定组织的帐户（需要组织用户）

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--guid（可选）</dt>
  <dd>仅显示帐户标识</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

显示与帐户关联的用户。此操作只能由帐户所有者执行。

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

从帐户中除去用户（仅帐户所有者）

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>USER_ID（必填）</dt>
<dd>用户标识</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>帐户标识。如果未指定，缺省值为当前帐户。</dd>
<dt>-f, --force</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

邀请用户加入帐户

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要邀请的用户的电子邮件。</dd>
   <dt>-o ORG</dt>
   <dd>邀请用户加入的组织</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>组织角色。有效输入为：OrgManager、BillingManager、OrgAuditor 和 OrgUser。如果省略，将设置 OrgUser 角色。</dd>
   <dt>-s SPACE</dt>
   <dd>邀请用户加入的空间</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>空间角色。有效输入为：SpaceManager、SpaceDeveloper 和 SpaceAuditor。</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

向用户重新发送邀请（帐户管理员）

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要重新邀请的用户的电子邮件。</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

列出当前帐户下的访问组

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-u</dt>
  <dd>列出用户所属的访问组。此标志与“-s”互斥。</dd>
  <dt>-s</dt>
  <dd>列出服务标识所属的访问组。此标志与“-u”互斥。</dd>
</dl>

<strong>示例</strong>：

列出所有访问组：

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

显示访问组的详细信息

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-id</dt>
  <dd>仅显示标识</dd>
</dl>

<strong>示例</strong>：

显示访问组 `example_group` 的详细信息：

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

创建访问组

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-d, --description</dt>
  <dd>访问组的描述</dd>
</dl>

<strong>示例</strong>：

创建访问组 `example_group`：

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

更新访问组

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-n, --name</dt>
  <dd>新访问组名称</dd>
  <dt>-d, --description</dt>
  <dd>新描述</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

将访问组 `example_group` 重命名为 `hello_word_group`：

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

删除访问组

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
  <dt>-r, --recursive</dt>
  <dd>删除访问组及其成员</dd>
</dl>

<strong>示例</strong>：

删除访问组 `example_group`：

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

列出访问组中的用户

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有用户：

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

将用户添加到访问组

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

将用户 `name@example.com` 添加到访问组 `example_group`：

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

从访问组中除去用户

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

从访问组 `example_group` 中除去用户 `name@example.com`：

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

从所有访问组中除去用户

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

从所有访问组中除去用户 `name@example.com`：

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

列出访问组中的服务标识

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有服务标识：

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

将服务标识添加到访问组

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

将服务标识 `example-service` 添加到访问组 `example_group`：

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

从访问组中除去服务标识

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

从访问组 `example_group` 中除去服务标识 `example-service`：

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

从所有访问组中除去服务标识

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

从所有访问组中除去服务标识 `example-service`：

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

列出访问组的策略

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有策略：

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

显示访问组策略的详细信息

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

显示访问组 `example_group` 的策略 `51b9717e-76b0-4f6a-bda7-b8132431f926` 的详细信息：

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

创建访问组策略

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件</dd>
  <dt>-roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此选项与“--file”互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与“--file”互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与“--file”互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此选项与“--file”互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此选项与“--file”互斥。</dd>
  <dt>-resource-group-name</dt>
  <dd>资源组的名称。此选项与“--file”和“--resource-group-id”互斥。</dd>
  <dt>-resource-group-id</dt>
  <dd>资源组的标识。此选项与“--file”和“--resource-group-name”互斥。</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件创建访问组策略：

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

授予 `example_group` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

授予 `example_group` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的 `sample-service` 实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

授予 `example_group` 对资源组 `sample-resource-group` 中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

更新访问组策略

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件</dd>
  <dt>--roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此选项与“--file”互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与“--file”互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与“--file”互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此选项与“--file”互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此选项与“--file”互斥。</dd>
  <dt>-resource-group-name</dt>
  <dd>资源组的名称。此选项与“--file”和“--resource-group-id”互斥。</dd>
  <dt>-resource-group-id</dt>
  <dd>资源组的标识。此选项与“--file”和“--resource-group-name”互斥。</dd>
</dl>

<strong>示例</strong>：

使用策略 JSON 文件中的访问组策略来更新访问组策略：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

更新访问组策略，以授予 `example_group` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

更新访问组策略，以授予 `example_group` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的 `sample-service` 实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

更新访问组策略，以授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新访问组策略，以授予 `example_group` 对资源组 `sample-resource-group` 中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

更新访问组策略，以授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

删除访问组策略

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除访问组 `example_group` 的策略 `51b9717e-76b0-4f6a-bda7-b8132431f926`：
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

列出所有服务标识

```
ibmcloud iam service-ids [--uuid]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--uuid</dt>
  <dd>仅显示服务标识的 UUID</dd>
</dl>

<strong>示例</strong>：列出当前帐户下所有服务标识的 UUID

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

显示服务标识的详细信息

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>--uuid</dt>
  <dd>显示服务标识的 UUID</dd>
</dl>

<strong>示例</strong>：

显示服务标识 `sample-test` 的详细信息

```
ibmcloud iam service-id sample-test
```
显示服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的详细信息

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

创建服务标识

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称</dd>
  <dt>-d, --description</dt>
  <dd>服务标识的描述</dd>
  <dt>--lock</dt>
  <dd>锁定创建的服务标识</dd>
</dl>

<strong>示例</strong>：

创建服务名称为 `sample-test` 且描述为 `hello, world!` 的服务标识

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

创建服务名称为 `sample-test` 且描述为 `hello, world!` 的锁定服务标识

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
更新服务标识

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-n, --name</dt>
  <dd>服务的新名称</dd>
  <dt>-d, --description</dt>
  <dd>服务的新描述</dd>
  <dt>-f, --force</dt>
  <dd>更新而不确认</dd>
</dl>

<strong>示例</strong>：

将服务标识 `sample-test` 重命名为 `sample-test2` 而不确认

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

更新服务 `sample-test` 的描述 

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

使用新描述将服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 重命名为 `sample-test3`

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

删除服务标识

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务标识 `sample-teset` 而不确认

```
ibmcloud iam service-id-delete sample-teset -f
```

删除服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

锁定服务标识

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>锁定而不确认</dd>
</dl>

<strong>示例</strong>：

锁定服务标识 `sample-teset` 而不确认

```
ibmcloud iam service-id-lock sample-teset -f
```

锁定服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

解锁服务标识

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>解锁而不确认</dd>
</dl>

<strong>示例</strong>：

解锁服务标识 `sample-teset` 而不确认

```
ibmcloud iam service-id-unlock sample-teset -f
```

解锁服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

列出所有 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥

```
ibmcloud iam api-keys
```

<strong>先决条件</strong>：端点和登录

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

创建新的 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要创建的 API 密钥的名称。</dd>
<dt>-d <i>DESCRIPTION</i>（可选）</dt>
<dd>API 密钥的描述</dd>
<dt>--file <i>FILE</i></dt>
<dd>将 API 密钥信息保存到指定的文件。如果未设置，将显示 JSON 内容。</dd>
<dt>--lock</dt>
<dd>锁定创建的 API 密钥</dd>
</dl>

<strong>示例</strong>：

创建 API 密钥并将其保存到文件

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

创建名称为“test-key”的锁定 API 密钥

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

更新 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要更新的 API 密钥的旧名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要更新的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-n <i>NAME</i>（可选）</dt>
<dd>API 密钥的新名称</dd>
<dt>-d <i>DESCRIPTION</i>（可选）</dt>
<dd>API 密钥的新描述</dd>
</dl>

<strong>示例</strong>：

更新 API 密钥的描述：

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

删除 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要删除的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要删除的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

锁定平台 API 密钥

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要锁定的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要锁定的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制锁定而不确认。</dd>
</dl>

<strong>示例</strong>：

锁定 API 密钥 test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

锁定给定 UUID 的 API 密钥而不确认

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

解锁平台 API 密钥

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要解锁的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要解锁的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制解锁而不确认。</dd>
</dl>

<strong>示例</strong>：

解锁 API 密钥 test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

解锁给定 UUID 的 API 密钥而不确认

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

列出服务的所有 API 密钥

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>显示服务 API 密钥而不确认</dd>
</dl>

<strong>示例</strong>：

列出服务 `sample-service` 的所有 API 密钥：

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

列出服务 API 密钥的详细信息

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>--uuid</dt>
  <dd>显示服务 API 密钥的 UUID</dd>
  <dt>-f, --force</dt>
  <dd>显示服务 API 密钥而不确认</dd>
</dl>

<strong>示例</strong>：

显示服务 `sample-service` 的服务 API 密钥 `sample-key` 的详细信息：

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

创建服务 API 密钥

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务标识的名称或新创建的服务 API 密钥的名称</dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-d, --description</dt>
  <dd>API 密钥的描述</dd>
  <dt>--file</dt>
  <dd>将 API 密钥信息保存到指定的文件。如果未设置，将显示 JSON 内容。</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：

为服务 `sample-service` 创建服务 API 密钥 `sample-key` 而不确认：

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

更新服务 API 密钥

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-n, --name</dt>
  <dd>服务 API 密钥的新名称</dd>
  <dt>-d, --description</dt>
  <dd>服务 API 密钥的新描述</dd>
  <dt>-f, --force</dt>
  <dd>更新而不确认</dd>
</dl>

<strong>示例</strong>：

将服务 API 密钥 `sample-key` 重命名为 `new-sample-key`：

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

删除服务 API 密钥

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务标识 `sample-service` 的服务 API 密钥 `sample-key`：

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

锁定服务 API 密钥

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>锁定而不确认</dd>
</dl>

<strong>示例</strong>：

锁定服务标识 `sample-service` 的服务 API 密钥 `sample-key`：

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

解锁服务 API 密钥

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>解锁而不确认</dd>
</dl>

<strong>示例</strong>：

解锁服务标识 `sample-service` 的服务 API 密钥 `sample-key`：

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

列出用户 `name@example.com` 的策略：

```
ibmcloud iam user-policies name@example.com
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
</dl>

<strong>示例</strong>：

列出用户 `name@example.com` 的策略：

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

显示用户策略的详细信息

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>POLICY_ID（必需）</dt>
<dd>策略的标识</dd>
</dl>

<strong>示例</strong>：

列出用户 `name@example.com` 的策略 `0bb730daa`：

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

创建用户策略

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>--file <i>FILE</i>（可选）</dt>
<dd>策略定义的 JSON 文件</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（可选）</dt>
<dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（可选）</dt>
<dd>策略定义的服务名称，此项与“--file”标志互斥。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>（可选）</dt>
<dd>策略定义的服务实例的 GUID，此项与“--file”标志互斥。</dd>
<dt>--region <i>REGION</i>（可选）</dt>
<dd>策略定义的区域，此项与“--file”标志互斥。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（可选）</dt>
<dd>策略定义的资源类型，此项与“--file”标志互斥。</dd>
<dt>--resource <i>RESOURCE</i>（可选）</dt>
<dd>策略定义的资源，此项与“--file”标志互斥。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（可选）</dt>
<dd>资源组的名称，此项与“--file”、“--resource”和“--resource-group-id”标志互斥。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（可选）</dt>
<dd>资源组的标识，此项与“--file”、“--resource”和“--resource-group-name”标志互斥。</dd>
</dl>

<strong>示例</strong>：

通过策略 JSON 文件 `policy.json` 为用户 `name@example.com` 创建用户策略：

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

授予 `name@example.com` 对所有 `sample-service` 资源的 `Administrator` 角色：

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

授予 `name@example.com` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的样本服务实例的资源 `key123` 的 `Editor` 角色：

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

授予 `name@example.com` 对资源组 `sample-resource-group` 的成员的 `Viewer` 角色：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组成员的 `Viewer` 角色：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

更新用户策略

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>POLICY_ID（必需）</dt>
<dd>要更新的策略的标识</dd>
<dt>--file <i>FILE</i>（可选）</dt>
<dd>策略定义的 JSON 文件</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（可选）</dt>
<dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（可选）</dt>
<dd>策略定义的服务名称，此项与“--file”标志互斥。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>（可选）</dt>
<dd>策略定义的服务实例的 GUID，此项与“--file”标志互斥。</dd>
<dt>--region <i>REGION</i>（可选）</dt>
<dd>策略定义的区域，此项与“--file”标志互斥。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（可选）</dt>
<dd>策略定义的资源类型，此项与“--file”标志互斥。</dd>
<dt>--resource <i>RESOURCE</i>（可选）</dt>
<dd>策略定义的资源，此项与“--file”标志互斥。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（可选）</dt>
<dd>资源组的名称，此项与“--file”、“--resource”和“--resource-group-id”标志互斥。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（可选）</dt>
<dd>资源组的标识，此项与“--file”、“--resource”和“--resource-group-name”标志互斥。</dd>
</dl>

<strong>示例</strong>：

使用 JSON 文件中的用户策略来更新用户策略：

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

更新用户策略以授予 `name@example.com` 对所有 `sample-service` 资源的 `Administrator` 角色：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 更新用户策略以授予 `name@example.com` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的样本服务实例的资源 `key123` 的 `Editor` 角色：

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

更新用户策略以授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新用户策略以授予 `name@example.com` 对资源组 `sample-resource-group` 的成员的 `Viewer` 角色：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

更新用户策略以授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组成员的 `Viewer` 角色：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

删除用户策略

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除用户策略而不确认</dd>
</dl>

<strong>示例</strong>：删除用户 `name@example.com` 的策略 `user-policy-id`：

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

删除用户 `name@example.com` 的策略 `user-policy-id` 而不确认：

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

列出指定服务的所有服务策略

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>-json</dt>
  <dd>以 JSON 格式显示策略</dd>
  <dt>-f, --force</dt>
  <dd>显示服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

列出服务 `test` 的策略：

```
ibmcloud iam service-policies test
```
列出服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

显示服务策略的详细信息

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>-json</dt>
  <dd>以 JSON 格式显示策略</dd>
  <dt>-f, --force</dt>
  <dd>显示服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

显示服务 `test` 的策略 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
显示服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

创建服务策略

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件。此选项与“-r, --roles”、“--service-name”、“--service-instance”、“--region”、“--resource-type”、“--resource”、“--resource-group-name”和“--resource-group-id”标志互斥。</dd>
  <dt>-r, --roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
  <dt>--service-name</dt>
  <dd>策略定义的服务名称。此项与“--file”标志互斥。</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此项与“--file”标志互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此项与“--file”标志互斥。</dd>
  <dt>--resource-type</dt>
  <dd>策略定义的资源类型。此项与“--file”标志互斥。</dd>
  <dt>--resource</dt>
  <dd>策略定义的资源。此项与“--file”标志互斥。</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。此选项与“--file”和“--resource-group-id”互斥。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。此选项与“--file”和“--resource-group-name”互斥。</dd>
  <dt>-f, --force</dt>
  <dd>创建服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件为服务 `test` 创建服务策略：

```
ibmcloud iam service-policy-create test --file @policy.json
```
通过 JSON 文件为服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 创建服务策略：

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

更新服务策略

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件。此选项与“-r, --roles”、“--service-name”、“--service-instance”、“--region”、“--resource-type”、“--resource”、“resource-group-name”和“resource-group-id”标志互斥。</dd>
  <dt>-r, --roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行“ibmcloud iam roles --service SERVICE_NAME”。此选项与“--file”互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此项与“--file”标志互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此项与“--file”标志互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此项与“--file”标志互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此项与“--file”标志互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此项与“--file”标志互斥。</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。此选项与“--file”和“--resource-group-id”互斥。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。此选项与“--file”和“--resource-group-name”互斥。</dd>
  <dt>-f, --force</dt>
  <dd>更新服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件更新服务 `test` 的服务策略 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
通过 JSON 文件更新服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的服务策略 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

删除服务策略

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务 `test` 的策略 `140798e2-8ea7db3`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
删除服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略 `140798e2-8ea7db3`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

检索并显示当前会话的 OAuth 令牌

```
ibmcloud iam oauth-tokens
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

刷新并显示 OAuth 令牌

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

断开公共 IBM 标识与专用非 IBM 标识的连接

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制断开连接而不确认</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

创建授权策略以允许服务实例访问其他服务实例。

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>可对其授予访问权的源服务。</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>可授权源服务访问的目标服务。</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>为源服务提供访问权的角色。</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>源服务实例名称，如果未指定该名称，将对源服务的所有实例授予访问权。</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>目标服务实例名称，如果未指定该名称，将对目标服务的所有实例授予访问权。</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

删除授权策略。

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要删除的授权策略的标识。</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认。</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

显示授权策略的详细信息。

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要显示的授权策略的标识。</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

列出当前帐户下的授权策略。

```
ibmcloud iam authorization-policies
```

<strong>先决条件</strong>：登录和目标


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

列出资源组。

```
ibmcloud resource groups [--default]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--default</dt>
  <dd>获取当前帐户的缺省组。</dd>
</dl>

<strong>示例</strong>：

列出当前目标帐户下的所有资源组：

```
ibmcloud resource groups
```

列出当前目标帐户的缺省组：

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

显示资源组的详细信息

```
ibmcloud resource group NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>资源组的名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识</dd>
</dl>

<strong>示例</strong>：

显示资源组 `example-group`：

```
ibmcloud resource group example-group
```

仅显示资源组 `example-group` 的标识：

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

创建资源组

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：

<strong>示例</strong>：

创建配额为 `free` 的资源组 `example-group`：

```
ibmcloud resource group-create example-group free
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

更新现有资源组

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>目标资源组的名称</dd>
  <dt>-n, --name</dt>
  <dd>资源组的新名称</dd>
  <dt>-q, --quota</dt>
  <dd>新配额定义的名称</dd>
  <dt>-f</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

将资源组 `example-group` 重命名为 `trial-group`：

```
ibmcloud resource group-update example-group -n trial-group
```

将资源组 `example-group` 的配额更改为 `free`：

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配额定义

```
ibmcloud resource quotas
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出所有配额定义：

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

显示配额定义的详细信息

```
ibmcloud resource quota NAME
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>配额的名称</dd>
</dl>

<strong>示例</strong>：显示配额 `free` 的详细信息：

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

将 Cloudfoundry 服务实例迁移到资源组

```
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_INSTANCE_NAME or SERVICE_INSTANCE_ID（必需）</dt>
  <dd>服务实例的名称或标识</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。此选项与“--resource-group-id”互斥。如果未指定其中任何选项，缺省情况下为当前的目标资源组。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。此选项与“--resource-group-name”互斥。如果未指定其中任何选项，缺省情况下为当前的目标资源组。</dd>
  <dt>-f, --force</dt>
  <dd>迁移而不确认</dd>
</dl>


## ibmcloud app push
{: #ibmcloud_app_push}

此命令的功能和选项与 [cf push ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} 命令的相同。


## ibmcloud app list
{: #ibmcloud_app_list}

此命令的功能和选项与 [cf apps ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} 命令的相同。


## ibmcloud app show
{: #ibmcloud_app_show}

此命令的功能和选项与 [cf app ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} 命令的相同。


## ibmcloud app delete
{: #ibmcloud_app_delete}

此命令的功能和选项与 [cf delete ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} 命令的相同。


## ibmcloud app rename
{: #ibmcloud_app_rename}

此命令的功能和选项与 [cf rename ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} 命令的相同。


## ibmcloud app start
{: #ibmcloud_app_start}

此命令的功能和选项与 [cf start ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} 命令的相同。


## ibmcloud app stop
{: #ibmcloud_app_stop}

此命令的功能和选项与 [cf stop ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} 命令的相同。


## ibmcloud app restart
{: #ibmcloud_app_restart}

此命令的功能和选项与 [cf restart ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} 命令的相同。


## ibmcloud app restage
{: #ibmcloud_app_restage}


此命令的功能和选项与 [cf restage ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} 命令的相同。


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


此命令的功能和选项与 [cf restart-app-instance ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} 命令的相同。


## ibmcloud app events
{: #ibmcloud_app_events}

此命令的功能和选项与 [cf events ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} 命令的相同。


## ibmcloud app files
{: #ibmcloud_app_files}

此命令的功能和选项与 [cf files ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} 命令的相同。


## ibmcloud app logs
{: #ibmcloud_app_logs}

此命令的功能和选项与 [cf logs ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} 命令的相同。


## ibmcloud app env
{: #ibmcloud_app_env}

此命令的功能和选项与 [cf env ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} 命令的相同。


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

此命令的功能和选项与 [cf set-env ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} 命令的相同。


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

此命令的功能和选项与 [cf unset-env ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} 命令的相同。


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

此命令的功能和选项与 [cf stacks ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} 命令的相同。


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

此命令的功能和选项与 [cf stack ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} 命令的相同。


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

此命令的功能和选项与 [cf create-app-manifest ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} 命令的相同。

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

列出域的证书信息。

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>DOMAIN_NAME（必需）</dt>
<dd>托管证书的域。</dd>
</dl>


<strong>示例</strong>：

查看域 `ibmcxo-eventconnect.com` 的证书信息：

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

将证书添加到当前组织中的指定域。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
   <dl>
   <dt>DOMAIN（必需）</dt>
   <dd>将证书添加到其中的域。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>（必需）</dt>
   <dd>专用密钥文件路径。</dd>
   <dt>-c <i>CERT_FILE</i>（必需）</dt>
   <dd>证书文件路径。</dd>
   <dt>-p <i>PASSWORD</i>（可选）</dt>
   <dd>证书的密码。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>（可选）</dt>
   <dd>中间证书文件路径。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>（可选）</dt>
   <dd>信任库文件。</dd>
   </dl>


<strong>示例</strong>：

将证书添加到域 `ibmcxo-eventconnect.com`：

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

从当前组织中的指定域除去证书。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：

   <dl>
   <dt>DOMAIN（必需）</dt>
   <dd>要从中除去证书的域。</dd>
   <dt>-f（可选）</dt>
   <dd>强制删除而不确认。</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

此命令的功能和选项与 [cf routes ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} 命令的相同。


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

此命令的功能和选项与 [cf check-route ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} 命令的相同。


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

将路径映射到具有指定域和主机名的现有 cf 应用程序或容器组。

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必需）</dt>
   <dd>要使用路径映射到的 cf 应用程序或容器组的名称。</dd>
   <dt>DOMAIN（必需）</dt>
   <dd>路径的域。例如，mychinabluemix.net 或 chinabluemix.net。</dd>
   <dt>-n <i>HOST_NAME</i>（可选）</dt>
   <dd>路径的主机名。如果未提供，缺省情况下主机名将设置为应用程序名称或容器组名称。</dd>
   </dl>

<strong>示例</strong>：

使用指定的域将路径映射到 `my-app`：

```
ibmcloud app route-map my-app mychinabluemix.net
```

使用指定域和主机名将路径映射到“my-container-group”：

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

取消来自现有 cf 应用程序或容器组中的指定路径映射。

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必需）</dt>
   <dd>cf 应用程序或容器组的名称。</dd>
   <dt>DOMAIN（必需）</dt>
   <dd>路径的域（例如，mychinabluemix.net 或 chinabluemix.net）。</dd>
   <dt>-n <i>HOST_NAME</i>（可选）</dt>
   <dd>路径的主机名。如果未提供，缺省情况下主机名将设置为应用程序名称或容器组名称。</dd>
   </dl>

<strong>示例</strong>：

从 `my-app` 取消 `my-app.mychinabluemix.net` 的映射：

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

从 `my-container-group` 取消 `abc.chinabluexmix.net` 的映射：

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

此命令的功能和选项与 [cf create-route ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} 命令的相同。


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

此命令的功能和选项与 [cf delete-route ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} 命令的相同。


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

此命令的功能和选项与 [cf delete-orphaned-routes ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} 命令的相同。


## ibmcloud app domains
{: #ibmcloud_app_domains}

此命令的功能和选项与 [cf domains ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} 命令的相同。


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

此命令的功能和选项与 [cf create-domain ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} 命令的相同。


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

此命令的功能和选项与 [cf delete-domain ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} 命令的相同。


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

此命令的功能和选项与 [cf create-shared-domain ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} 命令的相同。


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

此命令的功能和选项与 [cf delete-shared-domain ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} 命令的相同。


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


此命令的功能和选项与 [cf marketplace ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window} 命令的相同。


## ibmcloud service list
{: #ibmcloud_service_list}

此命令的功能和选项与 [cf services ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window} 命令的相同。


## ibmcloud service show
{: #ibmcloud_service_show}

此命令的功能和选项与 [cf service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window} 命令的相同。


## ibmcloud service create
{: #ibmcloud_service_create}

此命令的功能和选项与 [cf create-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window} 命令的相同。


## ibmcloud service update
{: #ibmcloud_service_update}

此命令的功能和选项与 [cf update-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window} 命令的相同。


## ibmcloud service delete
{: #ibmcloud_service_delete}

此命令的功能和选项与 [cf delete-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window} 命令的相同。


## ibmcloud service rename
{: #ibmcloud_service_rename}

此命令的功能和选项与 [cf rename-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window} 命令的相同。


## ibmcloud service bind
{: #ibmcloud_service_bind}

此命令的功能和选项与 [cf bind-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window} 命令的相同。


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

此命令的功能和选项与 [cf unbind-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window} 命令的相同。


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

此命令的功能和选项与 [cf create-service-key ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window} 命令的相同。


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

此命令的功能和选项与 [cf delete-service-key ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window} 命令的相同。


## ibmcloud service keys
{: #ibmcloud_service_keys}

此命令的功能和选项与 [cf service-keys ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window} 命令的相同。


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

此命令的功能和选项与 [cf service-key ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window} 命令的相同。


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

此命令的功能和选项与 [cf create-user-provided-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window} 命令的相同。


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

此命令的功能和选项与 [cf update-user-provided-service ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window} 命令的相同。


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服务实例

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--service-name</dt>
  <dd>所属服务的名称</dd>
  <dt>--location</dt>
  <dd>按位置过滤</dd>
  <dt>--long</dt>
  <dd>在输出中显示更多字段</dd>
</dl>

<strong>示例</strong>：

列出服务 `test-service` 的服务实例：

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

显示服务实例的详细信息

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需），与 ID 互斥</dt>
  <dd>服务实例的名称</dd>
  <dt>ID（必需），与 NAME 互斥</dt>
  <dd>服务实例的标识</dd>
  <dt>--location</dt>
  <dd>按位置过滤</dd>
  <dt>--id</dt>
  <dd>显示服务实例的标识</dd>
</dl>

<strong>示例</strong>：

显示服务实例 `my-service-instance` 的详细信息：

```
ibmcloud resource service-instance my-service-instance
``` 

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

创建服务实例

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务实例的名称</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必需）</dt>
  <dd>服务的名称或标识</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必需）</dt>
  <dd>服务套餐的名称或标识</dd>
  <dt>LOCATION</dt>
  <dd>用于创建服务实例的目标位置或环境</dd>
  <dt>-t, --tags</dt>
  <dd>标记</dd>
  <dt>-p, --parameters</dt>
  <dd>用于创建服务实例的参数的 JSON 文件或 JSON 字符串</dd>
  <dt>-d, --deployment</dt>
  <dd>部署的名称</dd>
</dl>

<strong>示例</strong>：
使用服务 `test-service` 的服务套餐 `test-service-plan` 在位置 `eu-gb` 中创建名为 `my-service-instance` 的服务实例：

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服务实例

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必填）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必填）</dt>
  <dd>服务实例的 ID，与 NAME 互斥 </dd>
  <dt>-n, --name</dt>
  <dd>新服务实例名称</dd>
  <dt>-t, --tags</dt>
  <dd>新标记</dd>
  <dt>--service-plan-id</dt>
  <dd>新服务套餐标识</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：
更新服务实例 `my-service-instance`，将其名称更改为 `new-service-instance`：

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

删除服务实例

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必填）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必填）</dt>
  <dd>服务实例的 ID，与 NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
  <dt>--recursive</dt>
  <dd>删除全部所属资源</dd>
</dl>

<strong>示例</strong>：
删除资源服务实例 `my-service-instance`：

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

显示与服务别名的绑定

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS（必需）</dt>
  <dd>服务别名</dd>
</dl>

<strong>示例</strong>：
显示与服务别名 `my-service-alias` 的资源绑定：

```
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

显示服务绑定的详细信息

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识。将禁止服务绑定的所有其他输出。</dd>
</dl>

<strong>示例</strong>：
显示服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定的详细信息：

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

创建服务绑定

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>ROLE_NAME</dt>
  <dd>用户角色的名称</dd>
  <dt>--service-id</dt>
  <dd>角色所属的服务标识的名称或 UUID</dd>
  <dt>-p, --parameter</dt>
  <dd>参数 JSON 文件或 JSON 字符串</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：
使用角色 `Administrator` 创建服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定：

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

删除服务绑定

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：
删除服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定：

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服务实例或服务别名的服务密钥

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>服务实例标识</dd>
  <dt>--instance-name</dt>
  <dd>服务实例名称</dd>
  <dt>--alias-id</dt>
  <dd>服务别名标识</dd>
  <dt>--alias-name</dt>
  <dd>服务别名</dd>
</dl>

<strong>示例</strong>：
列出服务实例 `my-service-instance` 的服务密钥：

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

显示服务密钥的详细信息

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>键的名称</dd>
  <dt>--id</dt>
  <dd>显示服务密钥的标识</dd>
</dl>

<strong>示例</strong>：
显示服务密钥 `my-service-key` 的详细信息：

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

创建服务密钥

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME</dt>
  <dd>键的名称</dd>
  <dt>ROLE_NAME</dt>
  <dd>用户角色的名称</dd>
  <dt>--instance-id</dt>
  <dd>服务实例标识</dd>
  <dt>--instance-name</dt>
  <dd>服务实例名称</dd>
  <dt>--alias-id</dt>
  <dd>服务别名标识</dd>
  <dt>--alias-name</dt>
  <dd>服务别名</dd>
  <dt>--service-id</dt>
  <dd>角色所属的服务标识的名称或 UUID</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：
使用角色 `Administrator` 为服务实例 `my-service-instance` 创建名为 `my-service-key` 的服务密钥：

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

删除服务密钥

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>键的名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：
删除服务密钥 `my-service-key`：

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服务实例的别名

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>所属服务实例的标识。</dd>
  <dt>--instance-name</dt>
  <dd>所属服务实例的名称。</dd>
</dl>

<strong>示例</strong>：
列出服务实例 `my-service-instance` 的服务别名：
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

显示服务别名的详细信息

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>--id</dt>
  <dd>仅显示给定服务别名的标识。将禁止别名的所有其他输出。</dd>
</dl>

<strong>示例</strong>：
显示服务别名 `my-service-alias` 的详细信息：
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

创建服务实例的别名

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>--instance-id</dt>
  <dd>所属服务实例的标识。</dd>
  <dt>--instance-name</dt>
  <dd>所属服务实例的名称。</dd>
  <dt>-s</dt>
  <dd>在其中创建别名的空间的名称。缺省值为当前空间。</dd>
  <dt>-t, --tags</dt>
  <dd>标记列表。</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串。</dd>
</dl>

<strong>示例</strong>：
创建服务实例 `my-service-instance` 的服务别名 `my-service-alias`：
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服务别名

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>-n, --name</dt>
  <dd>服务别名的新名称。</dd>
  <dt>-t, --tags</dt>
  <dd>标记列表。</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串。</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而无需用户确认。</dd>
</dl>

<strong>示例</strong>：
更新服务别名 `my-service-alias`，将其名称更改为 `new-service-alias`：

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

删除服务别名

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：
删除服务别名 `my-service-alias`：

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
使用 Lucene 查询语法搜索资源

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-offset, --o</dt>
  <dd>起始资源位置编号</dd>
  <dt>-limit, --l</dt>
  <dd>要返回的资源数（最多 10000 个）</dd>
</dl>

<strong>示例</strong>：
搜索其名称以指定文本开头的 Cloud Foundry 应用程序：

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

搜索指定服务名称的 Cloud Foundry 服务实例：

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

在具有指定标识的组织中搜索 Cloud Foundry 服务绑定：

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

搜索具有指定名称且位于两个指定区域之一内的 Cloud Foundry 空间：

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

在具有指定标识的 Cloud Foundry 空间中搜索其名称中包含文字 dev 的资源：

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

在指定位置中（即，在 us-south 区域中）搜索资源控制器资源：

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

在具有指定标识的资源组中搜索资源或别名：

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

搜索名称为 default 的资源组：

```
ibmcloud resource search 'name:default AND type:resource-group'
```

搜索指定服务名称的资源绑定：

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

搜索具有指定云资源名称 (CRN) 的资源：

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

搜索具有指定标记的资源：

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

列出所有标记

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-type</dt>
  <dd>标记类型（支持的值：user、restricted）</dd>
  <dt>-o, --offset</dt>
  <dd>起始资源位置编号（缺省值：0）</dd>
  <dt>-l, --limit</dt>
  <dd>要返回的资源数（最多 10000 个）（缺省值：10000）</dd>
</dl>

<strong>示例</strong>：

列出所有标记

```
ibmcloud resource tags 
```

列出所有 restricted 标记

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

显示标记详细信息

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
</dl>

<strong>示例</strong>：

显示标记“Ray Brown”的详细信息

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

创建标记

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称</dd>
  <dt>--tag-type</dt>
  <dd>标记类型（支持的值：user、restricted；缺省值为 user）</dd>
</dl>

<strong>示例</strong>：

创建名称为 think:2018 的 user 标记

```
ibmcloud resource tag-create --tag-name think:2018
```

创建名称为 department:marketing 的 restricted 标记

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

创建名称为“Ray Brown”的 user 标记

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

创建名称为“environment:My Development”的 restricted 标记

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

删除标记

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
</dl>

<strong>示例</strong>：

删除标记“Ray Brown”

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

向资源添加标记

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--resource-crn（必填）</dt>
  <dd>资源 CRN</dd>
</dl>

<strong>示例</strong>：

向 crn 为 resource_example_crn 的资源添加标记“Ray Brown”。

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

从资源除去标记

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--resource-crn（必填）</dt>
  <dd>资源 CRN</dd>
</dl>

<strong>示例</strong>：

除去 crn 为 resource_example_crn 的资源的标记“Ray Brown”。

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

从 user 标记切换到 restricted 标记，反之亦然

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--tag-type（必填）</dt>
  <dd>标记类型</dd>
</dl>

<strong>示例</strong>：

从标记“Ray Brown”切换到 restricted 标记

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```


## ibmcloud catalog search
{: #ibmcloud_catalog_search}

搜索目录条目

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-r, --region</dt>
  <dd>指定要在其中进行搜索的地理区域。目前仅支持“us-south”和“united-kingdom”</dd>
  <dt>-k, --kind</dt>
  <dd>按资源种类过滤。目前仅支持“service-cf”、“iaas”、“runtime”、“template”和“dashboard”</dd>
  <dt>-p, --price</dt>
  <dd>按价格过滤。目前仅支持“free”、“paygo”和“bluemix-subscription”</dd>
  <dt>-t, --tag</dt>
  <dd>按标记过滤。</dd>
  <dt>--sort-by</dt>
  <dd>要作为排序依据的属性</dd>
  <dt>--col</dt>
  <dd>指定表的其他列。目前有“group”、“provider”和“tags”</dd>
  <dt>--reverse</dt>
  <dd>是否反转排序顺序</dd>
  <dt>--json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>--csv</dt>
  <dd>输出 CSV 文件</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

搜索服务 `Automation test`：

```
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

获取目录条目

```
ibmcloud catalog entry ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--children</dt>
  <dd>获取目录条目的所有子代</dd>
  <dt>--json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

获取标识为 `a0ef1-d3b4j0` 的条目：

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
创建新的目录条目（仅限帐户的目录管理员）

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-p, --parent</dt>
  <dd>对象的父标识</dd>
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件创建父标识为 `a0ef1-d3b4j0` 资源：

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
更新现有目录条目（仅限帐户的目录管理员或编辑者）

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件更新资源 `j402-dnf1i`：

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
删除目录条目（仅限帐户的目录管理员）
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

删除资源 `j402 - dnf1i`：

```
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
获取目录条目的可视性（仅限帐户的目录管理员）

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>-global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

获取资源 `j402-dnf1i` 在全球范围的可视性：

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
更新现有目录条目的可视性（仅限帐户的目录管理员）

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>

  <dt>--includes-add</dt>
  <dd>将帐户（或逗号分隔帐户列表）添加到“包含”列表，授予该条目可视性。可接受电子邮件或帐户 GUID</dd>
  <dt>--includes-remove</dt>
  <dd>从“包含”列表中除去帐户（或逗号分隔帐户列表），撤销该条目的可视性。可接受电子邮件或帐户 GUID</dd>  
  <dt>--excludes-add</dt>
  <dd>将帐户（或逗号分隔帐户列表）添加到“排除”列表。可接受电子邮件或帐户 GUID</dd>
  <dt>--excludes-remove</dt>
  <dd>从“排除”列表中除去帐户（或逗号分隔帐户列表），撤销该条目的可视性。如果帐户是由全局管理员设置的，那么帐户管理员无法除去该帐户。可接受电子邮件或帐户 GUID</dd>
  <dt>--owner</dt>
  <dd>更改对象的所有者。可接受电子邮件或帐户 GUID。</dd>
  <dt>--restrict</dt>
  <dd>将可视性对象的限制更改为“专用”</dd>
  <dt>--unrestrict</dt>
  <dd>将可视性对象的限制更改为“公共”</dd>  
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件设置资源 `j402-dnf1i` 的可视性：

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
列出市场中的服务产品

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--cf</dt>
  <dd>仅显示 Cloud Foundry 服务</dd>
  <dt>--rc</dt>
  <dd>仅显示 RC 兼容服务</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

显示全球范围的服务产品：

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

查看 {{site.data.keyword.Bluemix_notm}} 上的样板模板。

```
ibmcloud catalog templates [-d]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>-d（可选）</dt>
   <dd>如果指定了 <i>-d</i> 选项，那么还会显示每个模板的描述。否则，只显示每个模板的标识和名称。</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

查看指定样板模板的详细信息。

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>TEMPLATE_ID（必需）</dt>
   <dd>样板模板的标识。使用 <i>ibmcloud templates</i> 可查看所有模板的标识。</dd>
   </dl>


<strong>示例</strong>：

查看模板 `mobileBackendStarter` 的详细信息：

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

使用指定 URL 和描述基于指定模板创建 cf 应用程序。缺省情况下，新应用程序将自动启动。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
   <dl>
   <dt>TEMPLATE_ID（必需）</dt>
   <dd>创建应用程序时将基于的模板。使用 <i>ibmcloud templates</i> 可查看所有模板的标识。</dd>
   <dt>CF_APP_NAME（必需）</dt>
   <dd>要创建的 cf 应用程序的名称。</dd>
   <dt>-u <i>URL</i>（可选）</dt>
   <dd>应用程序的路径。如果未指定，路径将由 {{site.data.keyword.Bluemix_notm}} 根据您的应用程序名称和缺省域自动设置。</dd>
   <dt>-d <i>DESCRIPTION</i>（可选）</dt>
   <dd>应用程序的描述。</dd>
   <dt>--no-start（可选）</dt>
   <dd>应用程序创建后不自动启动。如果未指定，应用程序创建后将自动启动。</dd>
   </dl>


<strong>示例</strong>：

基于 `javaHelloWorld` 模板创建 cf 应用程序 `my-app`：

```
ibmcloud catalog template-run javaHelloWorld my-app
```

基于 `rubyHelloWorld` 模板创建应用程序 `my-ruby-app`，路径为 `myrubyapp.chinabluemix.net`，描述为 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`：

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

基于 `pythonHelloWorld` 模板创建应用程序 `my-python-app`，不带自动启动：

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

以您选择的格式获取区域选项子集。

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>命令选项</strong>：

<dl>
  <dt>-i, --id</dt>
  <dd>按标识指定地理位置。</dd>
  <dt>-k, --kind</dt>
  <dd>获取指定种类的条目列表。</dd>
  <dt>--col</dt>
  <dd>指定表的其他列。目前有“group”、“provider”和“tags”。</dd>
  <dt>--json</dt>
  <dd>原始 JSON 响应的输出。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行。</dd>
  <dt>--csv</dt>
  <dd>输出 CSV 文件</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

查看运行时的详细信息。此命令仅可用于公共云。

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>示例</strong>：

显示运行时“nodejsHelloWorld”的详细信息：

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

列出所有运行时。此命令仅可用于公共云。

```
ibmcloud catalog runtimes [-d]
```

<strong>命令选项</strong>：

<dl>
  <dt>-d</dt>
  <dd>显示每个运行时的描述</dd>
</dl>

<strong>示例</strong>：

列出所有运行时及其描述：

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

显示当前帐户的每月使用情况（仅限帐户管理员）

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--json（可选）</dt>
  <dd>以 JSON 格式显示使用情况结果。</dd>
</dl>

<strong>示例</strong>：

显示当前帐户 2016 年 6 月的使用情况和成本报告：

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

显示组织的每月使用情况（仅限帐户管理员或组织记帐管理员）

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>ORG_NAME（必需）</dt>
  <dd>组织的名称。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--json（可选）</dt>
  <dd>以 JSON 格式显示使用情况结果。</dd>
</dl>


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

显示资源组的每月使用情况（仅限帐户管理员或资源组管理员）

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>GROUP_NAME（必需）</dt>
  <dd>资源组的名称。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--json（可选）</dt>
  <dd>以 JSON 格式显示使用情况结果。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

显示当前帐户的每月资源实例使用情况。

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>-o ORG_NAME（可选）</dt>
  <dd>按组织过滤实例。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>按资源组过滤实例。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--json（可选）</dt>
  <dd>以 JSON 格式显示使用情况结果。</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中注册的所有插件存储库。

```
ibmcloud plugin repos
```

<strong>先决条件</strong>：无


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

将新的插件存储库添加到 {{site.data.keyword.Bluemix_notm}} CLI 中。

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>REPO_NAME（必需）</dt>
   <dd>要添加的存储库的名称。可以为每个存储库定义您自己的名称。</dd>
   <dt>REPO_URL（必需）</dt>
   <dd>要添加的存储库的 URL。存储库 URL 必须包含协议（例如，http://plugins.ng.bluemix.net，而不是 plugins.ng.bluemix.net）。http://plugins.ng.bluemix.net 是 {{site.data.keyword.Bluemix_notm}} CLI 的官方插件存储库。</dd>
    </dl>


<strong>示例</strong>：

将 {{site.data.keyword.Bluemix_notm}} CLI 的官方插件存储库添加为 `bluemix-repo`：

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

从 {{site.data.keyword.Bluemix_notm}} CLI 中除去插件存储库。

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
   <dl>
   <dt>REPO_NAME（必需）</dt>
   <dd>要除去的存储库的名称。</dd>
   </dl>

<strong>示例</strong>：

从 {{site.data.keyword.Bluemix_notm}} CLI 中除去 `bluemix-repo` 存储库：

```
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

列出所有添加的存储库或特定存储库中的所有可用插件。

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（可选）</dt>
   <dd>仅列出指定存储库中的插件。</dd>
   </dl>

<strong>示例</strong>：

列出所有添加的存储库中的所有插件：

```
ibmcloud plugin repo-plugins
```

列出 `bluemix-repo` 存储库中的所有插件：

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

显示存储库中插件的详细信息。

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（可选）</dt>
   <dd>存储库的名称。如果未指定存储库，此命令将使用缺省插件存储库。</dd>
   </dl>

<strong>示例</strong>：

列出存储库“sample-repo”中插件“IBM-Containers”的详细信息：

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

列出缺省存储库中插件“IBM-Containers”的详细信息

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中的所有已安装插件。

```
ibmcloud plugin list
```

<strong>先决条件</strong>：无

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

显示已安装插件的详细信息。

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>先决条件</strong>：无


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

从指定的路径或存储库将特定版本的插件安装到 {{site.data.keyword.Bluemix_notm}} CLI 中。

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

如果未指定存储库，此命令将使用缺省插件存储库“Bluemix”。如果未指定版本，此命令将选择可用的最新版本进行安装。

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME（必需）</dt>
   <dd>如果未指定 -r <i>REPO_NAME</i>，那么将从指定的本地路径或远程 URL 安装插件。</dd>
   <dt>-r <i>REPO_NAME</i>（可选）</dt>
   <dd>插件二进制文件所在的存储库的名称。如果未指定存储库，此命令将使用缺省插件存储库“Bluemix”。</dd>
   <dt>-v <i>VERSION</i>（可选）</dt>
   <dd>要安装的插件的版本。如果未提供，将安装插件的最新版本。此选项仅对从存储库安装插件有效。</dd>
   <dt>-f</dt>
   <dd>强制安装插件而不确认。</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI 具有官方存储库名称 `Bluemix`。

<strong>示例</strong>：

从本地文件安装插件：

```
ibmcloud plugin install /downloads/new_plugin
```

从远程 URL 安装插件：

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

从“Bluemix”存储库安装最新版本的“container-service”插件：

```
ibmcloud plugin install container-service -r Bluemix
```

或者简单地指定为：

```
ibmcloud plugin install container-service
```

从官方插件存储库安装版本“0.1.425”的“container-service”插件：

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

从存储库升级插件。

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

如果未指定存储库，此命令将使用缺省插件存储库“Bluemix”。如果未指定版本，此命令将选择可用的最新版本进行安装。

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>要更新的插件的名称。如果未指定，此命令将检查安装的所有插件的升级。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>插件二进制文件所在的存储库的名称。如果未指定，此命令将使用缺省插件存储库“Bluemix”。</dd>
 <dt>-v <i>VERSION</i>（可选）</dt>
 <dd>要更新到的插件版本。如果未提供，那么将插件更新到最新可用版本。</dd>
 <dt>--all</dt>
 <dd>更新所有可用的插件</dd>
</dl>

<strong>示例</strong>：

检查官方插件存储库“Bluemix”中所有可用的升级：

```
ibmcloud plugin update -r Bluemix
```

或者简单地指定为：

```
ibmcloud plugin update
```

将官方插件存储库中的插件“container-service”升级到最新版本：

```
ibmcloud plugin update container-service
```

将官方插件存储库中的插件“container-service”更新到版本“0.1.440”：

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

从 {{site.data.keyword.Bluemix_notm}} CLI 中卸载指定的插件。

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>PLUGIN_NAME（必需）</dt>
   <dd>要卸载的插件的名称。</dd>
    </dl>

<strong>示例</strong>：

卸载先前安装的“container-service”插件：

```
ibmcloud plugin uninstall container-service
```

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

列出 CFEE 环境。

```
bx cfee environments
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

显示 CFEE 环境的详细信息。

```
bx cfee environment NAME [--id]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>--id</dt>
   <dd>仅显示标识。</dd>
  </dl>

<strong>示例</strong>：

显示 CFEE 环境 env_example 的详细信息：

```
bx cfee environment env_example
```

显示 CFEE 环境 env_example 的标识：

```
bx cfee environment env_example --id
```
