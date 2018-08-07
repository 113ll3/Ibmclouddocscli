---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-18"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}}(ibmcloud) 명령
{: #bluemix_cli}

버전: 0.7.1

{{site.data.keyword.Bluemix_notm}} 명령행 인터페이스(CLI)는 사용자가 {{site.data.keyword.Bluemix_notm}}와 상호작용할 수 있도록 네임스페이스별로 그룹화된 명령 세트를 제공합니다.

버전 0.5.0부터 {{site.data.keyword.Bluemix_notm}} 명령행 클라이언트는 Cloud Foundry 명령행 클라이언트를 해당 설치에서 번들화합니다. 자신에게 직접 설치한 cf cli가 있는 경우에는 {{site.data.keyword.Bluemix_notm}} CLI 명령 `ibmcloud [command]`와 해당 설치의 Cloud Foundry CLI 명령 `cf [command]`를 동일한 컨텍스트에서 함께 사용하지 마십시오. cf cli를 사용하여 {{site.data.keyword.Bluemix_notm}} CLI 컨텍스트에서 Cloud Foundry 리소스를 관리하려면 `ibmcloud cf [command]`를 대신 사용하십시오.  `ibmcloud cf api/login/logout/target`은 허용되지 않으며 대신 `ibmcloud api/login/logout/target`을 사용해야 한다는 점을 참고하십시오.

2018년 5월부터 {{site.data.keyword.Bluemix_notm}} CLI 명령은 `bluemix` 및 `bx`에서 `ibmcloud`로 변경되었습니다. 하지만 `bluemix` 및 `bx` CLI 명령은 나중에 제거할 때까지 사용할 수 있습니다.
{: tip}

다음에는 해당 이름, 인수, 옵션, 필수 소프트웨어, 설명 및 예제를 포함하여 {{site.data.keyword.Bluemix_notm}} CLI에서 지원하는 자세한 명령이 나열되어 있습니다.
{:shortdesc}

**참고:** *전제조건*에는 명령을 사용하기 전에 필요한 조치가 설명되어 있습니다. 전제조건 조치가 없는 명령은 **없음**으로 표시됩니다. 그 밖의 경우에는 전제조건으로 다음과 같은 조치 중 하나 이상을 수행해야 할 수 있습니다.

<dl>
<dt>엔드포인트</dt>
<dd>명령을 사용하기 전에 <code>bluemix api</code>를 통해 API 엔드포인트를 설정해야 합니다.</dd>
<dt>로그인</dt>
<dd>이 명령을 사용하기 전에 <code>bluemix login</code> 명령을 사용하여 로그인해야 합니다.
 연합 ID로 로그인한 경우에는 '--sso' 옵션을 사용하여 일회성 패스코드로 인증하거나 '--apikey'를 사용하여 API 키로 인증하십시오. API 키를 작성하려면 {{site.data.keyword.Bluemix_notm}} 콘솔 **관리** &gt; **보안** &gt; **플랫폼 API 키**로 이동하십시오.
</dd>
<dt>대상</dt>
<dd>이 명령을 사용하기 전에 <code>bluemix target</code> 명령을 사용하여 조직과 영역을 설정해야 합니다.</dd>
<dt>Docker</dt>
<dd>이 명령을 실행하려면 Docker CLI(docker)가 설치되어 있어야 합니다.</dd>
</dl>


자주 사용되는 ibmcloud 명령을 참조하려면 다음 표의 색인을 사용하십시오.

## 일반 ibmcloud 명령
{: #bx_commands_index}

<table summary="일반 ibmcloud 명령입니다. ">
<caption>표 1. 일반 ibmcloud 명령</caption>
 <thead>
 <th colspan="5">일반 ibmcloud 명령</th>
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

 ## {{site.data.keyword.BluSoftlayer_notm}} 인프라 서비스의 관리 및 구성을 위한 명령(ibmcloud sl)
  {: #bx_commands_softlayer}

{{site.data.keyword.BluSoftlayer_notm}} 인프라 관리를 위한 명령은 {{site.data.keyword.Bluemix_notm}} CLI에 병합되었습니다. {{site.data.keyword.Bluemix_notm}} CLI를 사용한 {{site.data.keyword.BluSoftlayer_notm}} 인프라 서비스의 구성 및 관리에 대한 자세한 정보는 [{{site.data.keyword.Bluemix_notm}} CLI {{site.data.keyword.BluSoftlayer_notm}} 인프라(ibmcloud sl) 명령](/docs/cli/reference/softlayer/index.html#softlayer_cli)을 참조하십시오.

 ## 계정, 조직 및 역할 관리를 위한 명령
 {: #bx_commands_account}

<table summary="계정, 조직, 영역 및 역할을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 2. 계정, 조직, 영역 및 역할 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">계정, 조직, 영역 및 역할 관리를 위한 명령</th>
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


 ## 리소스 그룹 및 리소스 관리를 위한 명령
{: #bx_commands_resource}

<table summary="리소스 그룹 및 리소스를 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
  <caption>표 3. 리소스 그룹 및 리소스 관리를 위한 명령</caption>
  <thead>
    <th colspan="5">리소스 그룹 및 리소스 관리를 위한 명령</th>
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


 ## API 키 및 정책 관리를 위한 명령
 {: #bx_commands_iam}
 <table summary="API 키 및 정책을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
 <caption>표 4. API 키 및 정책 관리를 위한 명령</caption>
  <thead>
  <th colspan="5">API 키 및 정책 관리를 위한 명령</th>
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

 ## cf 앱 및 앱 관련 도메인, 라우트 및 인증서 관리를 위한 명령
 {: #bx_commands_apps}

<table summary="cf 앱 및 앱 관련 도메인, 라우트, 인증서를 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 5. 앱 및 앱 관련 도메인, 라우트 및 인증서 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">cf 앱 및 앱 관련 도메인, 라우트 및 인증서 관리를 위한 명령</th>
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

 ## {{site.data.keyword.Bluemix_notm}} 서비스 관리를 위한 명령
 {: #bx_commands_services}

<table summary="{{site.data.keyword.Bluemix_notm}} 서비스를 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 6. {{site.data.keyword.Bluemix_notm}} 서비스 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 서비스 관리를 위한 명령</th>
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


 ## 카탈로그, 플러그인 및 청구 설정 관리를 위한 명령
 {: #bx_commands_settings}

<table summary="{{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 비용 청구 및 보안 설정을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 7. {{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 청구 및 보안 설정 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 청구 및 보안 설정의 관리를 위한 명령</th>
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

 ## Cloud Foundry Enterprise Environments 관리(시범)
{: #bx_commands_cfee}

<table summary="Cloud Foundry Enterprise Environments 관리(시범)">
<caption>표 8. Cloud Foundry Enterprise Environments 관리(시범)</caption>
 <thead>
 <th colspan="5">Cloud Foundry Enterprise Environments 관리(시범)</th>
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
첫 번째 레벨 기본 제공 명령 및 지원되는 {{site.data.keyword.Bluemix_notm}} CLI 네임스페이스에 대한 일반 도움말 또는 특정 기본 제공 명령 또는 네임스페이스의 도움말을 표시합니다.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE(선택사항)</dt>
   <dd>해당 도움말이 표시되는 명령 또는 네임스페이스입니다. 값을 지정하지 않으면 {{site.data.keyword.Bluemix_notm}} CLI의 일반 도움말이 표시됩니다.</dd>
   </dl>



<strong>예제</strong>:

{{site.data.keyword.Bluemix_notm}} CLI의 일반 도움말을 표시합니다.

```
ibmcloud help
```

`info` 명령의 도움말을 표시합니다.

```
ibmcloud help info
```



## ibmcloud api
{: #ibmcloud_api}
{{site.data.keyword.Bluemix_notm}} API 엔드포인트를 설정하거나 확인합니다.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>API_ENDPOINT(선택사항)</dt>
   <dd>대상으로 지정된 API 엔드포인트입니다(예: `https://api.chinabluemix.net`). *API_ENDPOINT* 및 `--unset` 옵션 중 하나를 지정하지 않으면 현재 API 엔드포인트가 표시됩니다.</dd>
   <dt>--unset(선택사항)</dt>
   <dd>API 엔드포인트 설정을 제거합니다.</dd>
   <dt>--skip-ssl-validation(선택사항)</dt>
   <dd>HTTP 요청의 SSL 유효성 검증을 무시합니다.</dd>
   </dl>
<strong>예제</strong>:

API 엔드포인트를 api.chinabluemix.net으로 설정합니다.

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

현재 API 엔드포인트를 확인합니다.

```
ibmcloud api
```

API 엔드포인트를 설정 해제합니다.

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


구성 파일에 기본값을 작성합니다.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>HTTP 요청의 제한시간 값입니다. 기본값은 60초입니다.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>터미널 또는 지정된 파일에 대한 HTTP 요청을 추적합니다.</dd>
   <dt>--color true|false</dt>
   <dd>색상 출력을 사용하거나 사용하지 않습니다. 색상 출력은 기본적으로 사용됩니다.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>기본 로케일을 설정합니다. LOCALE이 <i>CLEAR</i>인 경우 이전 로케일이 삭제됩니다.</dd>
   <dt>--check-version true|false</dt>
   <dd>CLI 버전 확인을 사용하거나 사용하지 않습니다.</dd>
   </dl>

이들 옵션 중에서 한 번에 하나만 지정할 수 있습니다.

<strong>예제</strong>:

HTTP 요청 제한시간을 30초로 설정합니다.

```
ibmcloud config --http-timeout 30
```

HTTP 요청에 대한 추적 출력을 사용하도록 설정합니다.

```
ibmcloud config --trace true
```

지정된 파일 */home/usera/my_trace*에 대한 HTTP 요청 추적:

```
ibmcloud config --trace /home/usera/my_trace
```

색상 출력을 사용하지 않도록 설정합니다.

```
ibmcloud config --color false
```

로케일을 zh_Hans로 설정합니다.

```
ibmcloud config --locale zh_Hans
```

로케일 설정을 지웁니다.

```
ibmcloud config --locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

현재 지역, 클라우드 제어기 버전, 로그인과 교환 액세스 토큰의 엔드포인트 같은 유용한 엔드포인트 등 기본 {{site.data.keyword.Bluemix_notm}} 정보를 확인합니다.

```
ibmcloud info
```

<strong>전제조건</strong>: 엔드포인트


## ibmcloud cf
{: #ibmcloud_cf}

임베디드 CF CLI 호출

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>메시지 "cf 명령 호출 중..." 끄기</dd>
</dl>

<strong>예제</strong>:

cf 앱 나열:

```
ibmcloud cf apps
```

메시지 "cf 명령 호출 중..." 없이 cf 서비스 나열:

```
ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

사용자가 로그인됩니다.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 없음

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>명령 옵션</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i>(선택사항)</dt>
  <dd> API 엔드포인트(예: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY 또는 @API_KEY_FILE_PATH</i>
  <dd> API 키 컨텐츠 또는 @로 표시되는 API 키 파일의 경로</dd>
  <dt> --sso(선택사항) </dt>
  <dd> 일회성 패스코드를 사용하여 로그인 </dd>
  <dt> -u <i>USERNAME</i>(선택사항)</dt>
  <dd> 사용자 이름</dd>
  <dt> -p <i>PASSWORD</i>(선택사항)</dt>
  <dd> 비밀번호</dd>
  <dt> -c <i>ACCOUNT_ID</i>(선택사항) </dt>
  <dd> 대상 계정의 ID입니다. 이 옵션은 --no-account와 배타적입니다.</dd>
  <dt> --no-account(선택사항) </dt>
  <dd> 계정을 사용하지 않은 로그인을 강제합니다. 이 옵션은 권장되지 않습니다. 이 옵션은 -c와 배타적입니다.</dd>
  <dt> -g <i>RESOURCE_GROUP</i>(선택사항) </dt>
  <dd> 대상 리소스 그룹의 이름</dd>
  <dt> -o <i>ORG</i>(선택사항)</dt>
  <dd> 대상 조직의 이름(더 이상 사용되지 않음, 'ibmcloud target -o ORG' 사용)</dd>
  <dt> -s <i>SPACE</i>(선택사항) </dt>
  <dd> 대상 영역의 이름(더 이상 사용되지 않음, 'ibmcloud target -s SPACE' 사용)</dd>
  <dt> --no-iam </dt>
  <dd> 공용 IAM 대신 로그인 서버를 통한 인증 강제 실행</dd>
  <dt> --skip-ssl-validation(선택사항) </dt>
  <dd> HTTP 요청의 SSL 유효성 검증을 무시합니다. 이 옵션은 권장되지 않습니다.</dd>
</dl>

<strong>예제</strong>:

#### 대화식 로그인

```
ibmcloud login
```

사용자 이름과 비밀번호로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

일회성 패스코드로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

API 키로 로그인하고 대상을 설정하십시오.

#### API 키에 계정이 연관되어 있음

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API에 계정이 연관되어 있지 않음

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>참고:</strong> API 키에 연관된 계정이 있는 경우, 다른 계정으로 전환이 허용되지 않습니다.

#### 일회성 패스코드 사용

```
ibmcloud login -u UserID --sso
```

그러면 CLI에서 URL 링크를 제공하고 패스코드를 요청합니다.
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

브라우저에서 링크를 열면 패스코드를 가져오도록 안내를 받게 됩니다. 콘솔에서 제공된 패스코드를 입력하면 로그인할 수 있어야 합니다.

## ibmcloud logout
{: #ibmcloud_logout}

사용자가 로그아웃됩니다.

```
ibmcloud logout
```

<strong>전제조건</strong>: 없음

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.Bluemix_notm}}의 모든 지역에 대한 정보를 확인합니다.

```
ibmcloud regions
```

<strong>전제조건</strong>: 엔드포인트


## ibmcloud target
{: #ibmcloud_target}


대상 계정, 지역, 조직 또는 영역을 설정하거나 보십시오.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i>(선택사항)</dt>
   <dd>전환할 지역의 이름입니다(예: 'us-south' 또는 'eu-gb').</dd>
   <dt>-c <i>ACCOUNT_ID</i>(선택사항)</dt>
   <dd>대상으로 지정된 계정의 ID입니다.</dd>
   <dt>-g <i>RESOURCE_GROUP</i>(선택사항)</dt>
   <dd>리소스 그룹의 이름</dd>
   <dt>--cf</dt>
   <dd>대상 조직 및 영역을 대화식으로 선택합니다.</dd>
   <dt>-o <i>ORG_NAME</i>(선택사항)</dt>
   <dd>대상으로 지정된 조직의 이름입니다.</dd>
   <dt>-s <i>SPACE_NAME</i>(선택사항)</dt>
   <dd>대상으로 지정된 영역의 이름입니다.</dd>
   </dl>
옵션이 지정되지 않은 경우, 현재 계정, 영역, 조직 및 영역이 표시됩니다.

<strong>예제</strong>:

현재 계정, 조직 및 영역 설정하기:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

새 지역으로 전환하기:

```
ibmcloud target -r eu-gb
```

현재 계정, 지역, 조직 및 영역 보기:

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

최신 버전으로 CLI를 업데이트합니다.

```
ibmcloud update [-f]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>-f</dt>
  <dd>확인 없이 업데이트를 강제 실행합니다. 루트 권한이 필요합니다.</dd>
</dl>

### ibmcloud account orgs
{: #ibmcloud_account_orgs}

모든 조직 나열

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r <i>REGION</i>(선택사항)</dt>
   <dd>조직 정보가 표시되는 대상 지역입니다. 'all'로 설정되면 모든 지역의 모든 조직이 나열됩니다.</dd>
   <dt>--guid(선택사항)</dt>
   <dd>조직의 GUID를 표시합니다.</dd>
   </dl>

<strong>예제</strong>:

지역: `us-south`의 모든 조직을 GUID를 표시하여 나열합니다.

```
ibmcloud account orgs -r us-south --guid
```

## ibmcloud account org
{: #ibmcloud_account_org}

지정된 조직의 정보를 표시합니다.

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>--guid(선택사항)</dt>
   <dd>조직의 GUID를 표시합니다.</dd>
   </dl>

<strong>예제</strong>:

조직 `IBM`의 정보를 GUID를 표시하여 보여줍니다.

```
ibmcloud account org IBM --guid
```


## ibmcloud account org-create
{: #ibmcloud_account_org_create}

새 조직을 작성합니다. 이 조작은 계정 소유자만 수행할 수 있습니다.

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>작성 중인 조직의 이름입니다.</dd>
   <dt>-f</dt>
   <dd>확인 없이 작성을 강제 실행합니다.</dd>
   </dl>

<strong>예제</strong>:

이름이 `IBM`인 조직을 작성합니다.

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

현재 지역의 조직을 다른 지역으로 복제합니다.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>복제할 기존 조직의 이름입니다.</dd>
   <dt>REGION_NAME(필수)</dt>
   <dd>복제된 조직을 호스팅하는 지역의 이름입니다.</dd>
   </dl>

<strong>예제</strong>:

`myorg` 조직을 `eu-gb` 지역에 복제합니다.

```
ibmcloud account org-replicate myorg eu-gb
```


## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

조직의 이름을 변경합니다. 이 조작은 조직 관리자만 수행할 수 있습니다.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>OLD_ORG_NAME(필수)</dt>
   <dd>이름이 변경될 조직의 이전 이름입니다.</dd>
   <dt>NEW_ORG_NAME(필수)</dt>
   <dd>이름이 변경될 대상 조직의 새 이름입니다.</dd>
   </dl>


## ibmcloud account spaces
{: #ibmcloud_account_spaces}

모든 영역 나열

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-o</dt>
   <dd>조직 이름입니다. 지정된 조직 아래의 영역을 나열합니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>-r</dt>
   <dd>지역 이름입니다. 지정된 지역 아래의 영역을 나열합니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   </dl>



## ibmcloud account space
{: #ibmcloud_account_space}

이 명령은 [cf space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud account space-create
{: #ibmcloud_account_space_create}

이 명령은 [cf create-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


이 명령은 [cf rename-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


이 명령은 [cf delete-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

역할별로 지정된 조직의 사용자를 표시합니다.

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>ORG_NAME(필수)</dt>
<dd>조직의 이름입니다.</dd>
<dt>-a(선택사항)</dt>
<dd>지정된 조직의 모든 사용자를 나열하지만, 역할별로 그룹화하지는 않습니다.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

조직에 사용자를 추가합니다(조직 관리자 필요).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

조직에서 사용자 제거(조직 관리자 또는 사용자 자신만)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--force, -f</dt>
<dd>확인 없이 강제 삭제합니다.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

현재 사용자의 모든 조직 역할 가져오기

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>-u</dt>
   <dd>사용자 ID입니다. 지정되지 않은 경우 현재 사용자로 기본값이 지정됩니다.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

사용자에게 조직 역할을 지정합니다. 이 조작은 조직 관리자만 수행할 수 있습니다.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>지정되는 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 지정되는 조직의 이름입니다.</dd>
   <dt>ORG_ROLE(필수)</dt>
   <dd>이 사용자가 지정되는 조직 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>OrgManager: 이 역할은 사용자를 초대 및 관리하고, 플랜을 선택 및 변경하며, 지출 한계를 설정할 수 있습니다.</li>
   <li>BillingManager: 이 역할은 청구 계정 및 결제 정보를 작성하고 관리할 수 있습니다.</li>
   <li>OrgAuditor: 이 역할은 조직 정보 및 보고서에 대한 읽기 전용 액세스 권한을 보유합니다.</li>
   </ul>
   </dd>
  </dl>

<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직에 `OrgManager` 역할로 지정합니다.

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**참고**: CLI를 사용하여 조직/영역 역할을 설정할 수 있으나, 그 외의 권한을 설정하려는 경우에는 UI를 사용해야 합니다. 세부사항은 [사용자 액세스 지정](/docs/iam/assignaccess.html#assignaccess)을 참조하십시오.
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

사용자로부터 조직 역할을 제거합니다. 이 조작은 조직 관리자만 수행할 수 있습니다.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>제거되는 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 제거되는 조직의 이름입니다.</dd>
   <dt>ORG_ROLE(필수)</dt>
   <dd>이 사용자가 제거되는 조직 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>OrgManager: 이 역할은 사용자를 초대 및 관리하고, 플랜을 선택 및 변경하며, 지출 한계를 설정할 수 있습니다.</li>
   <li>BillingManager: 이 역할은 청구 계정 및 결제 정보를 작성하고 관리할 수 있습니다.</li>
   <li>OrgAuditor: 이 역할은 조직 정보 및 보고서에 대한 읽기 전용 액세스 권한을 보유합니다.</li>
   </ul>
   </dd>
    </dl>

<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직에서 `OrgManager` 역할로 제거합니다.

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

역할별로 지정된 영역의 사용자를 표시합니다.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>영역의 이름입니다.</dd>
   </dl>


## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

사용자에게 영역 역할을 지정합니다. 이 조작은 영역 관리자만 수행할 수 있습니다.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>지정되는 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 지정되는 조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>이 사용자가 지정되는 영역의 이름입니다.</dd>
   <dt>SPACE_ROLE(필수)</dt>
   <dd>이 사용자가 지정되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 제공된 영역에 대한 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul></dd>
    </dl>

<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직 및 `Cloud` 영역에 `SpaceManager` 역할로 지정합니다.

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

사용자로부터 영역 역할을 제거합니다. 이 조작은 영역 관리자만 수행할 수 있습니다.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>제거되는 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 제거되는 조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>이 사용자가 제거되는 영역의 이름입니다.</dd>
   <dt>SPACE_ROLE(필수)</dt>
   <dd>이 사용자가 제거되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 제공된 영역에 대한 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul></dd>
    </dl>


<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직 및 `Cloud` 영역에서 `SpaceManager` 역할로 제거합니다.

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

현재 사용자의 모든 계정 나열

```
ibmcloud account list
```

<strong>전제조건</strong>: 엔드포인트, 로그인


## ibmcloud account org-account
{: #ibmcloud_account_org_account}

지정된 조직의 계정 표시(조직 사용자 필요)

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--guid(선택사항)</dt>
  <dd>계정 ID만 표시</dd>
</dl>


## ibmcloud account users
{: #ibmcloud_account_users}

계정과 연관된 사용자를 표시합니다. 이 조작은 계정 소유자만 수행할 수 있습니다.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

계정에서 사용자 제거(계정 소유자만)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>USER_ID(필수)</dt>
<dd>사용자 ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>계정 ID. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제 제거합니다.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

계정에 사용자 초대

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>초대받는 사용자의 이메일입니다.</dd>
   <dt>-o ORG</dt>
   <dd>사용자를 초대할 조직</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>조직 역할. 올바른 입력은 OrgManager, BillingManager, OrgAuditor 및 OrgUser입니다. 생략하면 OrgUser 역할이 설정됩니다.</dd>
   <dt>-s SPACE</dt>
   <dd>사용자를 초대할 영역</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>영역 역할. 올바른 입력은 SpaceManager, SpaceDeveloper 및 SpaceAuditor입니다.</dd>
</dl>


## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

사용자에게 초대 재발송(계정 관리자)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>다시 초대되는 사용자의 이메일입니다.</dd>
</dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

현재 계정에서 액세스 그룹 나열

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-u</dt>
  <dd>사용자가 속한 액세스 그룹을 나열합니다. 이 플래그는 '-s'와 배타적입니다.</dd>
  <dt>-s</dt>
  <dd>서비스 ID가 속한 액세스 그룹을 나열합니다. 이 플래그는 '-u'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹 나열:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

액세스 그룹의 세부사항 표시

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-id</dt>
  <dd>ID만 표시</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 세부사항 표시:

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

액세스 그룹 작성

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>액세스 그룹에 대한 설명</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group` 작성:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

액세스 그룹 업데이트

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>새 액세스 그룹 이름</dd>
  <dt>-d, --description</dt>
  <dd>새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 업데이트</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 이름을 `hello_world_group`으로 바꾸기:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

액세스 그룹 삭제

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
  <dt>-r, --recursive</dt>
  <dd>액세스 그룹 및 해당 구성원 삭제</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group` 삭제:

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

액세스 그룹의 사용자 나열

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 모든 사용자 나열:

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

액세스 그룹에 사용자 추가

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 사용자 `name@example.com` 추가:

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

액세스 그룹에서 사용자 제거

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에서 사용자 `name@example.com` 제거:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

모든 액세스 그룹에서 사용자 제거

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹에서 사용자 `name@example.com` 제거:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

액세스 그룹에 서비스 ID 나열

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 모든 서비스 ID 나열:

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

액세스 그룹에 서비스 ID 추가

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 서비스 ID `example-service` 추가:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

액세스 그룹에서 서비스 ID 제거

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에서 서비스 ID `example-service` 제거:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

모든 액세스 그룹에서 서비스 ID 제거

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹에서 서비스 ID `example-service` 제거:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

액세스 그룹의 정책 나열

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 모든 정책 나열:

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

액세스 그룹 정책의 세부사항 표시

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 정책 `51b9717e-76b0-4f6a-bda7-b8132431f926`에 대한 세부사항 표시:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

액세스 그룹 정책 작성

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일</dd>
  <dt>-roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>-resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

JSON 파일에서 액세스 그룹 정책 작성:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

모든 `sample-service` 리소스에 `example_group` `Administrator` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 `sample-service` 인스턴스의 리소스 `key123`에 `example_group` `Editor` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 대한 `example_group` `Operator` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 대한 `example_group` `Viewer` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 대한 `example_group` `Viewer` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

액세스 그룹 정책 업데이트

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일</dd>
  <dt>--roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>-resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 정책을 정책 JSON 파일의 정책으로 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

모든 `sample-service` 리소스에 대한 `example_group` `Administrator` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 `sample-service` 인스턴스의 리소스 `key123`에 대한 `example_group` `Editor` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 대한 `example_group` `Operator` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 대한 `example_group` `Viewer` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 대한 `example_group` `Viewer` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

액세스 그룹 정책 삭제

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 정책 `51b9717e-76b0-4f6a-bda7-b8132431f926` 삭제:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

모든 서비스 ID 나열

```
ibmcloud iam service-ids [--uuid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>서비스 ID의 UUID만 표시</dd>
</dl>

<strong>예제</strong>:
현재 계정 아래에 모든 서비스 ID의 UUID 나열

```
ibmcloud iam service-ids --uuid
```


## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

서비스 ID의 세부사항 표시

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>--uuid</dt>
  <dd>서비스 ID의 UUID 표시</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-test`의 세부사항 표시

```
ibmcloud iam service-id sample-test
```
서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 세부사항 표시

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

서비스 ID 작성

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스 ID의 설명</dd>
  <dt>--lock</dt>
  <dd>작성 시 서비스 ID 잠금</dd>
</dl>

<strong>예제</strong>:

서비스 이름이 `sample-test`이고 해당 설명이 `hello, world!`인 서비스 ID 작성

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

서비스 이름이 `sample-test`이고 설명이 `hello, world!`인 잠긴 서비스 ID 작성

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```


## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
서비스 ID 업데이트

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-n, --name</dt>
  <dd>서비스의 새 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스의 새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 ID 이름 `sample-test`를 확인 없이 `sample-test-2`로 바꾸기

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

서비스 `sample-test`의 설명 업데이트

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 이름을 설명이 새로 포함된 `sample-test-3`으로 바꾸기

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

서비스 ID 삭제

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 삭제

```
ibmcloud iam service-id-delete sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 삭제

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

서비스 ID 잠금

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 잠금

```
ibmcloud iam service-id-lock sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

서비스 ID 잠금 해제

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금 해제</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 잠금 해제

```
ibmcloud iam service-id-unlock sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금 해제

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 나열

```
ibmcloud iam api-keys
```

<strong>전제조건</strong>: 엔드포인트, 로그인

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

새 {{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 작성

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>작성할 API 키의 이름입니다.</dd>
<dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
<dd>API 키의 설명</dd>
<dt>--file <i>FILE</i></dt>
<dd>지정된 파일에 API 키 정보를 저장합니다. 설정하지 않으면 JSON 컨텐츠가 표시됩니다.</dd>
<dt>--lock</dt>
<dd>작성 시 API 키 잠금</dd>
</dl>

<strong>예제</strong>:

API 키 작성 및 파일에 저장

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

이름이 "test-key"인 잠긴 API 키 작성

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 업데이트

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>업데이트할 API 키의 이전 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>업데이트할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-n <i>NAME</i>(선택사항)</dt>
<dd>API 키의 새 이름</dd>
<dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
<dd>API 키의 새 설명</dd>
</dl>

<strong>예제</strong>:

API 키의 설명 업데이트:

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 삭제

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>삭제할 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>삭제할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제 삭제합니다.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

플랫폼 API 키 잠금

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠글 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠글 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠급니다.</dd>
</dl>

<strong>예제</strong>:

API 키 test-api-key 잠금

```
ibmcloud iam api-key-lock test-api-key
```

확인 없이 UUID가 지정된 API 키 잠금

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

플랫폼 API 키 잠금 해제

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠금 해제할 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠금 해제할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠금 해제합니다.</dd>
</dl>

<strong>예제</strong>:

API 키 test-api-key 잠금 해제

```
ibmcloud iam api-key-unlock test-api-key
```

확인 없이 UUID가 지정된 API 키 잠금 해제

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

서비스의 모든 API 키 나열

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 API 키 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `sample-service`의 모든 API 키 나열:

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

서비스 API 키의 세부사항 나열

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>--uuid</dt>
  <dd>서비스 API 키의 UUID 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 API 키 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `sample-service`의 서비스 API 키 `sample-key`의 세부사항 표시:

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

서비스 API 키 작성

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 ID 또는 새로 작성된 서비스 API 키 이름</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-d, --description</dt>
  <dd>API 키의 설명</dd>
  <dt>--file</dt>
  <dd>지정된 파일에 API 키 정보를 저장합니다. 설정하지 않으면 JSON 컨텐츠가 표시됩니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 작성</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 `sample-service`의 서비스 API 키 `sample-key` 작성:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

서비스 API 키 업데이트

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-n, --name</dt>
  <dd>서비스 API 키의 새 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스 API 키의 새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 API 키 이름 `sample-key`를 `new-sample-key`로 바꾸기:

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

서비스 API 키 삭제

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 삭제:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

서비스 API 키 잠금

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 잠금:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

서비스 API 키 잠금 해제

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금 해제</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 잠금 해제:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

사용자 `name@example.com`의 정책 나열:

```
ibmcloud iam user-policies name@example.com
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
</dl>

<strong>예제</strong>:

사용자 `name@example.com`의 정책 나열:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

사용자 정책의 세부사항 표시

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>POLICY_ID(필수)</dt>
<dd>정책 ID</dd>
</dl>

<strong>예제</strong>:

사용자 `name@example.com`의 정책 `0bb730daa` 나열:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

사용자 정책 작성

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>--file <i>FILE</i>(선택사항)</dt>
<dd>정책 정의의 JSON 파일</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (선택사항)</dt>
<dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
<dt>--service-name <i>SERVICE_NAME</i>(선택사항)</dt>
<dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>(선택사항)</dt>
<dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--region <i>REGION</i>(선택사항)</dt>
<dd>정책 정의의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>(선택사항)</dt>
<dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource <i>RESOURCE</i>(선택사항)</dt>
<dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>(선택사항)</dt>
<dd>리소스 그룹의 이름. 이는 '--file', '--resource' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>(선택사항)</dt>
<dd>리소스 그룹의 ID. 이는 '--file', '--resource' 및 '--resource-group-name' 플래그와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

정책 JSON 파일 `policy.json`에서 사용자 `name@example.com`의 사용자 정책 작성:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

모든 `sample-service` 리소스에 `name@example.com` `Administrator` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 샘플 서비스 인스턴스의 리소스 `key123`에 `name@example.com` `Editor` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 `name@example.com` `Operator` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 `name@example.com` `Viewer` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 `name@example.com` `Viewer` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

사용자 정책 업데이트

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>POLICY_ID(필수)</dt>
<dd>업데이트할 정책의 ID</dd>
<dt>--file <i>FILE</i>(선택사항)</dt>
<dd>정책 정의의 JSON 파일</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (선택사항)</dt>
<dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
<dt>--service-name <i>SERVICE_NAME</i>(선택사항)</dt>
<dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>(선택사항)</dt>
<dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--region <i>REGION</i>(선택사항)</dt>
<dd>정책 정의의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>(선택사항)</dt>
<dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource <i>RESOURCE</i>(선택사항)</dt>
<dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>(선택사항)</dt>
<dd>리소스 그룹의 이름. 이는 '--file', '--resource' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>(선택사항)</dt>
<dd>리소스 그룹의 ID. 이는 '--file', '--resource' 및 '--resource-group-name' 플래그와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

사용자 정책을 JSON 파일로 된 정책으로 업데이트:

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

모든 `sample-service` 리소스에 `name@example.com` `Administrator` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 `us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 샘플 서비스 인스턴스의 리소스 `key123`에 `name@example.com` `Editor` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 `name@example.com` `Operator` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 `name@example.com` `Viewer` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 `name@example.com` `Viewer` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

사용자 정책 삭제

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 사용자 정책 삭제</dd>
</dl>

<strong>예제</strong>:
사용자 `name@example.com`의 정책 `user-policy-id` 삭제:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

확인 없이 사용자 `name@example.com`의 정책 `user-policy-id` 삭제:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

지정된 서비스의 모든 서비스 정책 나열

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>-json</dt>
  <dd>JSON 형식으로 정책 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 나열:

```
ibmcloud iam service-policies test
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 나열:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

서비스 정책의 세부사항 표시

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>-json</dt>
  <dd>JSON 형식으로 정책 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 `140798e2-8ea7db3` 표시:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 `140798e2-8ea7db3` 표시:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

서비스 정책 작성

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일. 이는 '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
  <dt>-r, --roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>--service-name</dt>
  <dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource</dt>
  <dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>--resource-group-id </dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 작성</dd>
</dl>

<strong>예제</strong>:

서비스 `test`에 대해 JSON 파일에서 서비스 정책 작성:

```
ibmcloud iam service-policy-create test --file @policy.json
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`에 대해 JSON 파일에서 서비스 정책 작성:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```


## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

서비스 정책 업데이트

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일. 이는 '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' 및 'resource-group-id' 플래그와 배타적입니다.</dd>
  <dt>-r, --roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>--resource-group-id </dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 `test`에 대해 JSON 파일에서 서비스 정책 `140798e2-8ea7db3` 업데이트:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`에 대해 JSON 파일에서 서비스 정책 `140798e2-8ea7db3` 업데이트:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

서비스 정책 삭제

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 `140798e2-8ea7db3` 삭제

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 `140798e2-8ea7db3` 삭제

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

현재 세션에 대한 OAuth 토큰 검색 및 표시

```
ibmcloud iam oauth-tokens
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

OAuth 토큰 새로 고치기 및 표시

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

전용 비IBM ID와 공용 IBM ID의 연결 끊기

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 연결 끊기</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

다른 서비스 인스턴스에 대한 서비스 인스턴스 액세스를 허용하기 위한 권한 부여 정책을 작성합니다.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>액세스 권한이 부여될 수 있는 소스 서비스입니다.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>소스 서비스의 액세스 권한이 부여될 수 있는 대상 서비스입니다.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>소스 서비스에 대한 액세스 권한을 제공하는 역할입니다.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>소스 서비스의 모든 인스턴스의 액세스 권한이 부여될 소스 서비스 인스턴스 이름(지정되지 않은 경우)입니다.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>대상 서비스의 모든 인스턴스의 액세스 권한이 부여될 대상 서비스 인스턴스 이름(지정되지 않은 경우)입니다.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

권한 부여 정책을 삭제합니다.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>삭제할 권한 정책의 ID입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제를 강제 실행합니다.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

권한 정책의 세부사항을 표시합니다.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>표시할 권한 정책의 ID입니다.</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

현재 계정의 권한 부여 정책을 나열합니다.

```
ibmcloud iam authorization-policies
```

<strong>전제조건</strong>: 로그인, 대상


## ibmcloud resource groups
{: #ibmcloud_resource_groups}

리소스 그룹을 나열합니다.

```
ibmcloud resource groups [--default]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--default</dt>
  <dd>현재 계정의 기본 그룹을 가져옵니다.</dd>
</dl>

<strong>예제</strong>:

현재 대상 계정의 모든 리소스 그룹을 나열합니다.

```
ibmcloud resource groups
```

현재 대상으로 지정된 계정의 기본 그룹 나열:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

리소스 그룹의 세부사항 표시

```
ibmcloud resource group NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>리소스 그룹의 이름</dd>
  <dt>--id</dt>
  <dd>ID만 표시</dd>
</dl>

<strong>예제</strong>:

리소스 그룹 `example-group` 표시:

```
ibmcloud resource group example-group
```

리소스 그룹 `example-group`의 ID만 표시:

```
ibmcloud resource group example-group --id
```


## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

리소스 그룹 작성

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

<strong>예제</strong>:

할당량이 `free`인 리소스 그룹 `example-group` 작성:

```
ibmcloud resource group-create example-group free
```


## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

기존 리소스 그룹 업데이트

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>대상 리소스 그룹의 이름</dd>
  <dt>-n, --name</dt>
  <dd>리소스 그룹의 새 이름</dd>
  <dt>-q, --quota</dt>
  <dd>새 할당량 정의의 이름</dd>
  <dt>-f</dt>
  <dd>확인 없이 강제 업데이트</dd>
</dl>

<strong>예제</strong>:

리소스 그룹 이름 `example-group`을 `trial-group`으로 바꾸기:

```
ibmcloud resource group-update example-group -n trial-group
```

리소스 그룹 `example-group`의 할당량을 `free`로 변경:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

모든 할당량 정의 나열

```
ibmcloud resource quotas
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

모든 할당량 정의 나열:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

할당량 정의의 세부사항 표시

```
ibmcloud resource quota NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>할당량의 이름</dd>
</dl>

<strong>예제</strong>:
할당량 `free`의 세부사항 표시:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloudfoundry 서비스 인스턴스를 리소스 그룹으로 마이그레이션

```
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME 또는 SERVICE_INSTANCE_ID(필수)</dt>
  <dd>서비스 인스턴스의 이름 또는 ID</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--resource-group-id'와 배타적입니다. 지정되지 않은 경우 현재 대상 지정된 리소스 그룹으로 기본값이 설정됩니다.</dd>
  <dt>--resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--resource-group-name'과 배타적입니다. 지정되지 않은 경우 현재 대상 지정된 리소스 그룹으로 기본값이 설정됩니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 마이그레이션</dd>
</dl>


## ibmcloud app push
{: #ibmcloud_app_push}

이 명령은 [cf push ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app list
{: #ibmcloud_app_list}

이 명령은 [cf apps ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app show
{: #ibmcloud_app_show}

이 명령은 [cf app ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app delete
{: #ibmcloud_app_delete}

이 명령은 [cf delete ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app rename
{: #ibmcloud_app_rename}

이 명령은 [cf rename ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app start
{: #ibmcloud_app_start}

이 명령은 [cf start ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app stop
{: #ibmcloud_app_stop}

이 명령은 [cf stop ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app restart
{: #ibmcloud_app_restart}

이 명령은 [cf restart ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app restage
{: #ibmcloud_app_restage}


이 명령은 [cf restage ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


이 명령은 [cf restart-app-instance ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app events
{: #ibmcloud_app_events}

이 명령은 [cf events ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app files
{: #ibmcloud_app_files}

이 명령은 [cf files ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app logs
{: #ibmcloud_app_logs}

이 명령은 [cf logs ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app env
{: #ibmcloud_app_env}

이 명령은 [cf env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app env-set
{: #ibmcloud_app_env_set}

이 명령은 [cf set-env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

이 명령은 [cf unset-env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app stacks
{: #ibmcloud_app_stacks}

이 명령은 [cf stacks ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

이 명령은 [cf stack ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

이 명령은 [cf create-app-manifest ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

도메인의 인증서 정보를 나열합니다.

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>DOMAIN_NAME(필수)</dt>
<dd>인증서를 호스팅하는 도메인입니다.</dd>
</dl>


<strong>예제</strong>:

`ibmcxo-eventconnect.com` 도메인의 인증서 정보를 봅니다.

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

현재 조직의 지정된 도메인에 인증서를 추가합니다.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
   <dl>
   <dt>DOMAIN(필수)</dt>
   <dd>인증서가 추가되는 도메인입니다.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>(필수)</dt>
   <dd>개인 키 파일 경로입니다.</dd>
   <dt>-c <i>CERT_FILE</i>(필수)</dt>
   <dd>인증서 파일 경로입니다.</dd>
   <dt>-p <i>PASSWORD</i>(선택사항)</dt>
   <dd>인증서의 비밀번호입니다.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>(선택사항)</dt>
   <dd>중간 인증서 파일 경로입니다.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>(선택사항)</dt>
   <dd>신뢰 저장소 파일입니다.</dd>
   </dl>


<strong>예제</strong>:

인증서를 도메인 `ibmcxo-eventconnect.com`에 추가합니다.

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

현재 조직의 지정된 도메인에서 인증서를 제거합니다.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>DOMAIN(필수)</dt>
   <dd>인증서가 제거되는 도메인입니다.</dd>
   <dt>-f(선택사항)</dt>
   <dd>확인 없이 강제 삭제합니다.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

이 명령은 [cf routes ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app route-check
{: #ibmcloud_app_route_check}

이 명령은 [cf check-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app route-map
{: #ibmcloud_app_route_map}

지정된 도메인과 호스트 이름이 있는 기존의 cf 애플리케이션 또는 컨테이너 그룹에 라우트를 맵핑합니다.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME(필수)</dt>
   <dd>라우트로 맵핑되는 cf 애플리케이션 또는 컨테이너 그룹의 이름입니다.</dd>
   <dt>DOMAIN(필수)</dt>
   <dd>라우트의 도메인입니다. 예: mychinabluemix.net 또는 chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i>(선택사항)</dt>
   <dd>라우트의 호스트 이름입니다. 값을 제공하지 않으면 호스트 이름이 기본적으로 앱 이름 또는 컨테이너 그룹 이름으로 설정됩니다.</dd>
   </dl>

<strong>예제</strong>:

라우트를 지정된 도메인이 있는 `my-app`으로 맵핑합니다.

```
ibmcloud app route-map my-app mychinabluemix.net
```

라우트를 지정된 도메인과 호스트 이름이 있는 'my-container-group'으로 맵핑합니다.

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

기존의 cf 애플리케이션이나 컨테이너 그룹과 지정된 라우트의 맵핑을 해제합니다.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME(필수)</dt>
   <dd>cf 애플리케이션 또는 컨테이너 그룹의 이름입니다.</dd>
   <dt>DOMAIN(필수)</dt>
   <dd>라우트의 도메인입니다(예: mychinabluemix.net 또는 chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i>(선택사항)</dt>
   <dd>라우트의 호스트 이름입니다. 값을 제공하지 않으면 호스트 이름이 기본적으로 앱 이름 또는 컨테이너 그룹 이름으로 설정됩니다.</dd>
   </dl>

<strong>예제</strong>:

`my-app`에서 `my-app.mychinabluemix.net`을 맵핑 해제합니다.

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

`my-container-group`에서 `abc.chinabluexmix.net`을 맵핑 해제합니다.

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## ibmcloud app route-create
{: #ibmcloud_app_route_create}

이 명령은 [cf create-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

이 명령은 [cf delete-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

이 명령은 [cf delete-orphaned-routes ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app domains
{: #ibmcloud_app_domains}

이 명령은 [cf domains ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

이 명령은 [cf create-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

이 명령은 [cf delete-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

이 명령은 [cf create-shared-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

이 명령은 [cf delete-shared-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service offerings
{: #ibmcloud_service_offerings}


이 명령은 [cf marketplace ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service list
{: #ibmcloud_service_list}

이 명령은 [cf services ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service show
{: #ibmcloud_service_show}

이 명령은 [cf service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service create
{: #ibmcloud_service_create}

이 명령은 [cf create-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service update
{: #ibmcloud_service_update}

이 명령은 [cf update-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service delete
{: #ibmcloud_service_delete}

이 명령은 [cf delete-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service rename
{: #ibmcloud_service_rename}

이 명령은 [cf rename-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service bind
{: #ibmcloud_service_bind}

이 명령은 [cf bind-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service unbind
{: #ibmcloud_service_unbind}

이 명령은 [cf unbind-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service key-create
{: #ibmcloud_service_key_create}

이 명령은 [cf create-service-key ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service key-delete
{: #ibmcloud_service_key_delete}

이 명령은 [cf delete-service-key ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service keys
{: #ibmcloud_service_keys}

이 명령은 [cf service-keys ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service key-show
{: #ibmcloud_service_key_show}

이 명령은 [cf service-key ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service user-provided-create
{: #ibmcloud_service_user_provided_create}

이 명령은 [cf create-user-provided-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud service user-provided-update
{: #ibmcloud_service_user_provided_update}

이 명령은 [cf update-user-provided-service ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.


## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

서비스 인스턴스 나열

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>속해 있는 서비스의 이름</dd>
  <dt>--location</dt>
  <dd>위치별 필터링</dd>
  <dt>--long</dt>
  <dd>출력에 추가 필드 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `test-service`의 서비스 인스턴스 나열:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

서비스 인스턴스의 세부사항 표시

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수), ID와 배타적</dt>
  <dd>서비스 인스턴스의 이름</dd>
  <dt>ID(필수), NAME과 배타적</dt>
  <dd>서비스 인스턴스의 ID</dd>
  <dt>--location</dt>
  <dd>위치별 필터링</dd>
  <dt>--id</dt>
  <dd>서비스 인스턴스의 ID 표시</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`의 세부사항 표시:

```
ibmcloud resource service-instance my-service-instance
``` 

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

서비스 인스턴스 작성

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 인스턴스의 이름</dd>
  <dt>SERVICE_NAME 또는 SERVICE_ID(필수)</dt>
  <dd>서비스의 이름 또는 ID</dd>
  <dt>SERVICE_PLAN_NAME 또는 SERVICE_PLAN_ID(필수)</dt>
  <dd>서비스 플랜의 이름 또는 ID</dd>
  <dt>LOCATION</dt>
  <dd>서비스 인스턴스를 작성하는 대상 위치 또는 환경</dd>
  <dt>-t, --tags</dt>
  <dd>태그</dd>
  <dt>-p, --parameters</dt>
  <dd>서비스 인스턴스를 작성하기 위한 매개변수의 JOSN 문자열 또는 JSON 파일</dd>
  <dt>-d, --deployment</dt>
  <dd>배치의 이름</dd>
</dl>

<strong>예</strong>:
위치 `eu-gb`에 있는 서비스 `test-service`의 서비스 플랜 `test-service-plan`을 사용하여 서비스 인스턴스 `my-service-instance` 작성:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

서비스 인스턴스 업데이트

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>이름(필수)</dt>
  <dd>서비스 인스턴스의 이름(ID와 배타적)</dd>
  <dt>ID(필수)</dt>
  <dd>서비스 인스턴스의 ID(NAME과 배타적)</dd>
  <dt>-n, --name</dt>
  <dd>새 서비스 인스턴스 이름</dd>
  <dt>-t, --tags</dt>
  <dd>새 태그</dd>
  <dt>--service-plan-id</dt>
  <dd>새 서비스 플랜 ID</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 업데이트</dd>
</dl>

<strong>예</strong>:
서비스 인스턴스 `my-service-instance` 업데이트, 해당 이름을 `new-service-instance`로 변경:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

서비스 인스턴스 삭제

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>이름(필수)</dt>
  <dd>서비스 인스턴스의 이름(ID와 배타적)</dd>
  <dt>ID(필수)</dt>
  <dd>서비스 인스턴스의 ID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
  <dt>--recursive</dt>
  <dd>속해 있는 모든 리소스 삭제</dd>
</dl>

<strong>예</strong>:
리소스 서비스 인스턴스 `my-service-instance` 삭제:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

서비스 별명에 대한 바인딩 표시

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ALIAS(필수)</dt>
  <dd>서비스 별명 이름</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias`에 대한 리소스 바인딩 표시:

```
ibmcloud resource bindings my-service-alias
```
## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

서비스 바인딩의 세부사항 표시

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 애플리케이션 이름</dd>
  <dt>--id</dt>
  <dd>ID만 표시합니다. 서비스 바인딩의 기타 모든 출력은 표시되지 않습니다.</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩의 세부사항 표시:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

서비스 바인딩 작성

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 애플리케이션 이름</dd>
  <dt>ROLE_NAME</dt>
  <dd>사용자 역할의 이름</dd>
  <dt>--service-id</dt>
  <dd>역할이 속한 서비스 ID의 UUID 또는 이름</dd>
  <dt>-p, --parameter</dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 작성</dd>
</dl>

<strong>예</strong>:
`Administrator` 역할로 서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩 작성:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

서비스 바인딩 삭제

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 애플리케이션 이름</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩 삭제:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

서비스 별명 또는 서비스 인스턴스의 서비스 키 나열

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>서비스 인스턴스 ID</dd>
  <dt>--instance-name</dt>
  <dd>서비스 인스턴스 이름</dd>
  <dt>--alias-id</dt>
  <dd>서비스 별명 ID</dd>
  <dt>--alias-name</dt>
  <dd>서비스 별명 이름</dd>
</dl>

<strong>예</strong>:
서비스 인스턴스 `my-service-instance`의 서비스 키 나열:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

서비스 키의 세부사항 표시

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>키의 이름</dd>
  <dt>--id</dt>
  <dd>서비스 키의 ID 표시</dd>
</dl>

<strong>예</strong>:
서비스 키 `my-service-key`의 세부사항 표시:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

서비스 키 작성

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME</dt>
  <dd>키의 이름</dd>
  <dt>ROLE_NAME</dt>
  <dd>사용자 역할의 이름</dd>
  <dt>--instance-id</dt>
  <dd>서비스 인스턴스 ID</dd>
  <dt>--instance-name</dt>
  <dd>서비스 인스턴스 이름</dd>
  <dt>--alias-id</dt>
  <dd>서비스 별명 ID</dd>
  <dt>--alias-name</dt>
  <dd>서비스 별명 이름</dd>
  <dt>--service-id</dt>
  <dd>역할이 속한 서비스 ID의 UUID 또는 이름</dd>
  <dt>-p, --parameters</dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 작성</dd>
</dl>

<strong>예</strong>:
서비스 인스턴스 `my-service-instance`에 대해 `Administrator` 역할로 `my-service-key`로 이름 지정된 서비스 키 작성:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

서비스 키 삭제

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>키의 이름</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
</dl>

<strong>예</strong>:
서비스 키 `my-service-key` 삭제:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

서비스 인스턴스의 별명 나열

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>속해 있는 서비스 인스턴스의 ID.</dd>
  <dt>--instance-name</dt>
  <dd>속해 있는 서비스 인스턴스의 이름.</dd>
</dl>

<strong>예</strong>:
서비스 인스턴스 `my-service-instance`의 서비스 별명 나열:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

서비스 별명의 세부사항 표시

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>--id</dt>
  <dd>제공된 서비스 별명의 ID만 표시합니다. 별명에 대한 다른 모든 출력은 표시되지 않습니다.</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias`의 세부사항 표시:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

서비스 인스턴스의 별명 작성

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>--instance-id</dt>
  <dd>속해 있는 서비스 인스턴스의 ID.</dd>
  <dt>--instance-name</dt>
  <dd>속해 있는 서비스 인스턴스의 이름.</dd>
  <dt>-s</dt>
  <dd>별명이 작성되는 영역의 이름. 기본값은 현재 영역입니다.</dd>
  <dt>-t, --tags</dt>
  <dd>태그 목록</dd>
  <dt>-p, --parameters</dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
</dl>

<strong>예</strong>:
서비스 인스턴스 `my-service-instance`의 `my-service-alias`로 이름 지정된 서비스 별명 작성:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

서비스 별명 업데이트

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>-n, --name</dt>
  <dd>서비스 별명의 새 이름</dd>
  <dt>-t, --tags</dt>
  <dd>태그 목록</dd>
  <dt>-p, --parameters</dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
  <dt>-f, --force</dt>
  <dd>사용자 확인 없이 강제 업데이트</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias` 업데이트, 해당 이름을 `new-service-alias`로 변경:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

서비스 별명 삭제

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
</dl>

<strong>예</strong>:
서비스 별명 `my-service-alias` 삭제:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Lucene 조회 구문을 사용하여 리소스 검색

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-offset, --o</dt>
  <dd>시작 리소스 위치 번호</dd>
  <dt>-limit, --l</dt>
  <dd>리턴할 리소스의 수(최대 10000)</dd>
</dl>

<strong>예제</strong>:
이름이 지정된 텍스트로 시작하는 Cloud Foundry 애플리케이션 검색:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

지정된 서비스 이름의 Cloud Foundry 서비스 인스턴스 검색:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

지정된 ID의 조직에서 Cloud Foundry 서비스 바인딩 검색:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

지정된 두 지역 중 하나에 있으며 지정된 이름을 가진 Cloud Foundry 영역 검색:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

지정된 ID를 가진 Cloud Foundry 영역에서 이름에 단어 dev가 포함된 리소스 검색:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

지정된 위치(즉, 미국 남부 지역)에서 리소스 제어기의 리소스 검색:

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

지정된 ID를 가진 리소스 그룹에서 리소스 또는 별명 검색:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

이름이 기본값인 리소스 그룹 검색:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

지정된 서비스 이름에 대한 리소스 바인딩 검색:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

지정된 클라우드 리소스 이름(CRN)의 리소스 검색:

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

지정된 태그가 있는 리소스 검색:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

모든 태그 나열

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>태그 유형(지원되는 값: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>시작 리소스 위치 번호(기본값: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>리턴할 리소스의 수(최대 10000)(기본값: 10000)</dd>
</dl>

<strong>예제</strong>:

모든 태그 나열

```
ibmcloud resource tags 
```

제한된 모든 태그 나열

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

태그의 세부사항 표시

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름, --tag-crn과 배타적</dd>
  <dt>--tag-crn(필수)</dt>
  <dd>태그 CRN, --tag-name과 배타적</dd>
</dl>

<strong>예제</strong>:

태그 "Ray Brown"의 세부사항 표시

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

태그 작성

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름</dd>
  <dt>--tag-type</dt>
  <dd>태그 유형(지원되는 값: user, restricted, 기본값: user)</dd>
</dl>

<strong>예제</strong>:

이름이 think:2018인 사용자 태그 작성

```
ibmcloud resource tag-create --tag-name think:2018
```

이름이 department:marketing인 제한된 태그 작성

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

이름이 "Ray Brown"인 사용자 태그 작성

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

이름이 "environment:My Development"인 제한된 태그 작성

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

태그 삭제

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름, --tag-crn과 배타적</dd>
  <dt>--tag-crn(필수)</dt>
  <dd>태그 CRN, --tag-name과 배타적</dd>
</dl>

<strong>예제</strong>:

태그 "Ray Brown" 삭제

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

리소스에 태그 추가

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름, --tag-crn과 배타적</dd>
  <dt>--tag-crn(필수)</dt>
  <dd>태그 CRN, --tag-name과 배타적</dd>
  <dt>--resource-crn(필수)</dt>
  <dd>리소스 CRN</dd>
</dl>

<strong>예제</strong>:

crn이 resource_example_crn인 리소스에 태그 "Ray Brown"을 추가합니다.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

리소스에서 태그 제거

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름, --tag-crn과 배타적</dd>
  <dt>--tag-crn(필수)</dt>
  <dd>태그 CRN, --tag-name과 배타적</dd>
  <dt>--resource-crn(필수)</dt>
  <dd>리소스 CRN</dd>
</dl>

<strong>예제</strong>:

crn이 resource_example_crn인 리소스에서 태그 "Ray Brown"을 제거합니다.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

사용자 태그를 제한된 태그로 전환 또는 그 반대로 전환

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>태그 이름, --tag-crn과 배타적</dd>
  <dt>--tag-crn(필수)</dt>
  <dd>태그 CRN, --tag-name과 배타적</dd>
  <dt>--tag-type(필수)</dt>
  <dd>태그 유형</dd>
</dl>

<strong>예제</strong>:

태그 "Ray Brown"을 제한된 태그로 전환

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```


## ibmcloud catalog search
{: #ibmcloud_catalog_search}

카탈로그 항목 검색

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>검색할 범위의 지리적 지역 지정. 현재 "us-south" 및 "united-kingdom"만 지원됨</dd>
  <dt>-k, --kind</dt>
  <dd>리소스 종류별 필터링. 현재 "service-cf", "iaas", "runtime", "template" 및 "dashboard"만 지원됨</dd>
  <dt>-p, --price</dt>
  <dd>가격별 필터링. 현재 "free", "paygo", "bluemix-subscription"만 지원됨</dd>
  <dt>-t, --tag</dt>
  <dd>태그별 필터링.</dd>
  <dt>--sort-by</dt>
  <dd>정렬 기준 특성</dd>
  <dt>--col</dt>
  <dd>테이블의 추가 컬럼을 지정합니다. 현재 "group", "provider" 및 "tags"</dd>
  <dt>--reverse</dt>
  <dd>정렬 순서를 반대로 할지 여부</dd>
  <dt>--json</dt>
  <dd>원래 JSON 응답 출력</dd>
  <dt>--csv</dt>
  <dd>출력 CSV 파일</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

서비스 `Automation test` 검색:

```
ibmcloud catalog search -k service -q 'Automation test'
```


## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

카탈로그 항목 가져오기

```
ibmcloud catalog entry ID [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--children</dt>
  <dd>카탈로그 항목의 모든 하위 가져오기</dd>
  <dt>--json</dt>
  <dd>원래 JSON 응답 출력</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

ID가 `a0ef1-d3b4j0`인 항목 가져오기:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
새 카탈로그 항목 작성(계정의 카탈로그 관리자만)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>오브젝트의 상위 ID</dd>
  <dt>-c</dt>
  <dd>카탈로그 특정 구성 매개변수가 포함된 유효한 JSON 오브젝트(인라인 또는 파일로 제공됨). 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

상위 ID가 `a0ef1-d3b4j0`인 JSON 파일에서 리소스 작성:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```


## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
기존 카탈로그 항목 업데이트(계정의 카탈로그 관리자 또는 편집자만)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-c</dt>
  <dd>카탈로그 특정 구성 매개변수가 포함된 유효한 JSON 오브젝트(인라인 또는 파일로 제공됨). 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

JSON 파일에서 리소스 `j402-dnf1i` 업데이트:

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
카탈로그 항목 삭제(계정의 카탈로그 관리자만)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

리소스 `j402-dnf1i` 삭제:

```
ibmcloud catalog delete 'j402-dnf1i'
```


## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
카탈로그 항목의 가시성 가져오기(계정의 카탈로그 관리자만)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-json</dt>
  <dd>원래 JSON 응답 출력</dd>
  <dt>-global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

글로벌 범위에서 리소스 `j402-dnf1i`의 가시성 가져오기:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```


## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
기존 카탈로그 항목의 가시성 업데이트(계정의 카탈로그 관리자만)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 포함 목록에 추가하고 항목에 대한 가시성을 부여합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--includes-remove</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 포함 목록에서 제거하고 항목에 대한 가시성을 취소합니다. 이메일 또는 계정 GUID 허용</dd>  
  <dt>--excludes-add</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 제외 목록에 추가합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--excludes-remove</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 제외 목록에서 제거하고 항목에 대한 가시성을 취소합니다. 글로벌 관리자가 계정을 설정한 경우, 계정 관리자는 계정을 제거할 수 없습니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--owner</dt>
  <dd>오브젝트의 소유자를 변경합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--restrict</dt>
  <dd>가시성 오브젝트의 제한을 '개인용'으로 변경</dd>
  <dt>--unrestrict</dt>
  <dd>가시성 오브젝트의 제한을 '공용'으로 변경</dd>  
  <dt>-c</dt>
  <dd>카탈로그 특정 구성 매개변수가 포함된 유효한 JSON 오브젝트(인라인 또는 파일로 제공됨). 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

JSON 파일에서 리소스 `j402-dnf1i`의 가시성 설정:

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```


## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
마켓플레이스의 서비스 오퍼링 나열

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Cloud Foundry 서비스만 표시</dd>
  <dt>--rc</dt>
  <dd>RC 호환 가능 서비스만 표시</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동</dd>
</dl>

<strong>예제</strong>:

글로벌 범위의 서비스 오퍼링 표시:

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

{{site.data.keyword.Bluemix_notm}}에서 표준 유형 템플리트를 확인합니다.

```
ibmcloud catalog templates [-d]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

   <dl>
   <dt>-d(선택사항)</dt>
   <dd><i>-d</i> 옵션을 지정하면 각 템플리트의 설명도 표시됩니다. 그렇지 않으면 각 템플리트의 ID와 이름만 표시됩니다.</dd>
   </dl>


## ibmcloud catalog template
{: #ibmcloud_catalog_template}

지정된 표준 유형 템플리트의 자세한 정보를 봅니다.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>TEMPLATE_ID(필수)</dt>
   <dd>표준 유형 템플리트의 ID입니다. 모든 템플리트의 ID를 보려면 <i>ibmcloud templates</i>를 사용하십시오.</dd>
   </dl>


<strong>예제</strong>:

`mobileBackendStarter` 템플리트의 세부사항을 봅니다.

```
ibmcloud catalog template mobileBackendStarter
```


## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

특정 URL 및 설명이 있는 지정된 템플리트를 기반으로 하는 cf 애플리케이션을 작성합니다. 기본적으로 새 앱이 자동으로 시작됩니다.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
   <dl>
   <dt>TEMPLATE_ID(필수)</dt>
   <dd>애플리케이션을 작성할 때 이의 기반이 되는 템플리트입니다. 모든 템플리트의 ID를 보려면 <i>ibmcloud templates</i>를 사용하십시오.</dd>
   <dt>CF_APP_NAME(필수)</dt>
   <dd>작성되는 cf 애플리케이션의 이름입니다.</dd>
   <dt>-u <i>URL</i>(선택사항)</dt>
   <dd>애플리케이션의 라우트입니다. 지정되지 않은 경우, 앱 이름과 기본 도메인을 기반으로 {{site.data.keyword.Bluemix_notm}}에 의해 자동으로 라우트가 설정됩니다.</dd>
   <dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
   <dd>애플리케이션에 대한 설명입니다.</dd>
   <dt>--no-start(선택사항)</dt>
   <dd>애플리케이션을 작성한 후에 이를 자동으로 시작하지 않습니다. 값을 지정하지 않으면 애플리케이션이 작성 후 자동으로 시작됩니다.</dd>
   </dl>


<strong>예제</strong>:

`javaHelloWorld` 템플리트를 기반으로 cf 애플리케이션 `my-app`을 작성합니다.

```
ibmcloud catalog template-run javaHelloWorld my-app
```

라우트가 `myrubyapp.chinabluemix.net`이고 설명이 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`인 `rubyHelloWorld` 템플리트를 기반으로 `my-ruby-app` 애플리케이션을 작성합니다.

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

자동 시작 없이 `pythonHelloWorld` 템플리트를 기반으로 `my-python-app` 애플리케이션을 작성합니다.

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

선택한 형식으로 지역의 선택 서브세트를 가져옵니다.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>명령 옵션</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>id에 의해 지역을 지정합니다.</dd>
  <dt>-k, --kind</dt>
  <dd>지정된 유형에 대한 항목의 목록을 가져옵니다.</dd>
  <dt>--col</dt>
  <dd>테이블의 추가 컬럼을 지정합니다. 현재는 "group", "provider" 및 "tags"입니다.</dd>
  <dt>--json</dt>
  <dd>원래 JSON 응답의 출력입니다.</dd>
  <dt>--global</dt>
  <dd>글로벌 범위에서 작동됩니다.</dd>
  <dt>--csv</dt>
  <dd>출력 CSV 파일</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

런타임의 세부사항을 봅니다. 이 명령은 퍼블릭 클라우에서만 사용할 수 있습니다.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>예제</strong>:

"nodejsHelloWorld" 런타임의 세부사항 표시:

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

모든 런타임을 나열합니다. 이 명령은 퍼블릭 클라우에서만 사용할 수 있습니다.

```
ibmcloud catalog runtimes [-d]
```

<strong>명령 옵션</strong>:

<dl>
  <dt>-d</dt>
  <dd>각 런타임의 설명 표시</dd>
</dl>

<strong>예제</strong>:

모든 런타임을 설명과 함께 나열:

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

현재 계정의 월별 사용량 표시(계정 관리자만)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--json(선택사항)</dt>
  <dd>JSON 형식으로 사용량 결과를 표시하십시오.</dd>
</dl>

<strong>예제</strong>:

2016년 6월에 현재 계정의 사용량 및 비용 보고서 표시:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

조직의 월별 사용량 표시(계정 관리자 또는 조직 청구 관리자만)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>ORG_NAME(필수)</dt>
  <dd>조직의 이름입니다.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--json(선택사항)</dt>
  <dd>JSON 형식으로 사용량 결과를 표시하십시오.</dd>
</dl>


## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

리소스 그룹의 월별 사용량 표시(계정 관리자 또는 리소스 그룹 관리자만)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>GROUP_NAME(필수)</dt>
  <dd>리소스 그룹의 이름.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--json(선택사항)</dt>
  <dd>JSON 형식으로 사용량 결과를 표시하십시오.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

현재 계정의 월별 리소스 인스턴스 사용량을 표시합니다.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>-o ORG_NAME(선택사항)</dt>
  <dd>조직으로 인스턴스를 필터링합니다.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>리소스 그룹으로 인스턴스를 필터링합니다.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시하십시오. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--json(선택사항)</dt>
  <dd>JSON 형식으로 사용량 결과를 표시하십시오.</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.Bluemix_notm}} CLI에 등록된 모든 플러그인 저장소를 나열합니다.

```
ibmcloud plugin repos
```

<strong>전제조건</strong>: 없음


## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

{{site.data.keyword.Bluemix_notm}} CLI에 새 플러그인 저장소를 추가합니다.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>REPO_NAME(필수)</dt>
   <dd>추가되는 저장소의 이름입니다. 각 저장소의 고유 이름을 정의할 수 있습니다.</dd>
   <dt>REPO_URL(필수)</dt>
   <dd>추가되는 저장소의 URL입니다. 저장소 URL에는 프로토콜이 포함되어 있어야 합니다(예: plugins.ng.bluemix.net이 아닌 http://plugins.ng.bluemix.net). 다음이 {{site.data.keyword.Bluemix_notm}} CLI의 공식 플러그인 저장소입니다. http://plugins.ng.bluemix.net</dd>
    </dl>


<strong>예제</strong>:

`bluemix-repo`로서 {{site.data.keyword.Bluemix_notm}} CLI의 공식 플러그인 저장소 추가:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```


## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

{{site.data.keyword.Bluemix_notm}} CLI에서 플러그인 저장소를 제거합니다.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>REPO_NAME(필수)</dt>
   <dd>제거되는 저장소의 이름입니다.</dd>
   </dl>

<strong>예제</strong>:

{{site.data.keyword.Bluemix_notm}} CLI에서 `bluemix-repo` 저장소를 제거합니다.

```
ibmcloud plugin repo-remove bluemix-repo
```


## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

추가된 모든 저장소 또는 특정 저장소에서 사용 가능한 모든 플러그인을 나열합니다.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>지정된 저장소의 플러그인만 나열합니다.</dd>
   </dl>

<strong>예제</strong>:

모든 추가된 저장소의 플러그인을 나열합니다.

```
ibmcloud plugin repo-plugins
```

`bluemix-repo` 저장소의 모든 플러그인 나열:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

저장소의 플러그인 세부사항을 표시합니다.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>저장소 이름. 저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소를 사용합니다.</dd>
   </dl>

<strong>예제</strong>:

"sample-repo" 저장소의 "IBM-Containers" 플러그인 세부사항 나열:

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

기본 저장소의 "IBM-Containers" 플러그인 세부사항 나열

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

{{site.data.keyword.Bluemix_notm}} CLI의 설치된 모든 플러그인을 나열합니다.

```
ibmcloud plugin list
```

<strong>전제조건</strong>: 없음

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

설치된 플러그인의 세부사항을 표시합니다.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>전제조건</strong>: 없음


## ibmcloud plugin install
{: #ibmcloud_plugin_install}

지정된 경로 또는 저장소의 {{site.data.keyword.Bluemix_notm}} CLI에 특정 버전의 플러그인을 설치합니다.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'Bluemix'를 사용합니다.
버전이 지정되지 않은 경우 명령은 설치할 최신의 사용 가능한 버전을 선택합니다.

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME(필수)</dt>
   <dd>-r <i>REPO_NAME</i>이 지정되지 않은 경우 플러그인은 지정된 로컬 경로 또는 원격 URL에서 설치됩니다.</dd>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>플러그인 2진이 있는 저장소의 이름입니다. 저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'Bluemix'를 사용합니다.</dd>
   <dt>-v <i>VERSION</i>(선택사항)</dt>
   <dd>설치될 플러그인의 버전입니다. 제공되지 않은 경우 최신 버전의 플러그인이 설치됩니다. 이 옵션은 저장소에서 플러그인을 설치하는 경우에만 유효합니다.</dd>
   <dt>-f </dt>
   <dd>확인 없이 플러그인 설치를 강제 실행합니다.</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI에 `Bluemix`의 공식 저장소 이름이 있습니다.

<strong>예제</strong>:

로컬 파일에서 플러그인 설치:

```
ibmcloud plugin install /downloads/new_plugin
```

원격 URL에서 플러그인 설치:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

'Bluemix' 저장소에서 최신 버전의 'container-service' 플러그인을 설치합니다.

```
ibmcloud plugin install container-service -r Bluemix
```

또는 단순히

```
ibmcloud plugin install container-service
```

공식 플러그인 저장소에서 버전 '0.1.425'의 'container-service' 플러그인 설치:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

저장소에서 플러그인을 업그레이드합니다.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'Bluemix'를 사용합니다.
버전이 지정되지 않은 경우 명령은 설치할 최신의 사용 가능한 버전을 선택합니다.

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>업데이트할 플러그인의 이름입니다. 지정되지 않은 경우, 이 명령은 설치된 모든 플러그인의 업그레이드를 확인합니다.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>플러그인 2진이 있는 저장소의 이름입니다. 지정되지 않은 경우 명령은 기본 플러그인 저장소 'Bluemix'를 사용합니다.</dd>
 <dt>-v <i>VERSION</i>(선택사항)</dt>
 <dd>업데이트되는 플러그인의 버전입니다. 제공되지 않은 경우 최신 사용 가능 버전으로 플러그인을 업데이트합니다.</dd>
 <dt>--all</dt>
 <dd>사용 가능한 플러그인 모두 업데이트</dd>
</dl>

<strong>예제</strong>:

공식 플러그인 저장소 'Bluemix'에서 사용 가능한 모든 업그레이드 확인:

```
ibmcloud plugin update -r Bluemix
```

또는 단순히

```
ibmcloud plugin update
```

공식 플러그인 저장소의 플러그인 'container-service'를 최신으로 업그레이드:

```
ibmcloud plugin update container-service
```

공식 플러그인 저장소의 플러그인 'container-service'를 버전 '0.1.440'으로 업데이트:

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

{{site.data.keyword.Bluemix_notm}} CLI에서 지정된 플러그인을 설치 제거합니다.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>PLUGIN_NAME(필수)</dt>
   <dd>설치 제거될 플러그인의 이름입니다.</dd>
    </dl>

<strong>예제</strong>:

이전에 설치된 'container-service' 플러그인 설치 제거:

```
ibmcloud plugin uninstall container-service
```

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE 환경을 나열합니다.

```
bx cfee environments
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:


## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

CFEE 환경의 세부사항을 표시합니다.

```
bx cfee environment NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>--id</dt>
   <dd>ID만 표시합니다.</dd>
  </dl>

<strong>예제</strong>:

CFEE 환경 env_example의 세부사항 표시:

```
bx cfee environment env_example
```

CFEE 환경 env_example의 ID 표시:

```
bx cfee environment env_example --id
```
