---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} 관리 CLI
{: #bluemixadmincli}

{{site.data.keyword.cloud_notm}} 관리 CLI 플러그인에 Cloud Foundry 명령행 인터페이스(CLI)를 사용하여 {{site.data.keyword.cloud_notm}} 로컬 또는 {{site.data.keyword.cloud_notm}} 데디케이티드 환경을 관리할 수 있습니다. 예를 들어, LDAP 레지스트리에서 사용자를 추가할 수 있습니다.

시작하기 전에 Cloud Foundry CLI를 설치하십시오. {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인에는
`cf` 버전 6.11.2 이상이 필요합니다. [Cloud Foundry 명령행 인터페이스 다운로드](https://github.com/cloudfoundry/cli/releases){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")

Cloud Foundry CLI는 Cygwin에 의해 지원되지 않습니다. Cygwin 명령행 창 이외의 명령행 창에서 Cloud Foundry CLI를 사용하십시오.

{{site.data.keyword.cloud_notm}} 관리 CLI는 {{site.data.keyword.cloud_notm}} 로컬 및 {{site.data.keyword.cloud_notm}} 데디케이티드 환경에만 사용됩니다. {{site.data.keyword.cloud_notm}} 퍼블릭에서 지원되지 않습니다.
{: note}

## {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인 추가
{: #add-admin-cli}

Cloud Foundry CLI가 설치된 후에 {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인을 추가할 수 있습니다.

이전에 {{site.data.keyword.cloud_notm}} 관리 플러그인을 설치한 경우, 최신 업데이트를 가져오려면 이 플러그인을 설치 제거하고 저장소를 삭제한 후 설치해야 합니다.
{: tip}

저장소를 추가하고 플러그인을 설치하려면 다음 단계를 완료하십시오.

1. {{site.data.keyword.cloud_notm}} 관리 플러그인 저장소를 추가하려면 다음 명령을 실행하십시오.
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  관리 콘솔 CLI 페이지(`https://<customer_console_endpoint>.bluemix.net/cli`)에서 실제 엔드포인트가 있는 동일한 명령을 찾을 수 있습니다.
  {: note}

2. {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인을 설치하려면 다음 명령을 실행하십시오.
  ```
cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
```
  {: codeblock}

## {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인 설치 제거
{: #remove-admin-cli}

플러그인을 설치 제거하려면 다음 단계를 사용하십시오. 

1. 플러그인 설치 제거:
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. 플러그인 저장소 제거:
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

그런 다음, 업데이트된 저장소를 추가하고 최신 플러그인을 설치할 수 있습니다.

## {{site.data.keyword.cloud_notm}} 관리 CLI 플러그인 사용
{: #using-admin-cli}

{{site.data.keyword.cloud_notm}} 관리 CLI 플러그인을 사용하여 사용자 추가 및 제거, 조직에서 사용자 지정 및 지정 취소, 기타 관리 태스크를 수행할 수 있습니다.

명령 목록을 보려면 다음 명령을
실행하십시오.
```
cf plugins
```
{: codeblock}

명령에 대한 도움말을 보려면 `-help` 옵션을 사용하십시오.

### {{site.data.keyword.cloud_notm}}에 연결 및 로그인
{: #connecting-ibm-cloud}

1. {{site.data.keyword.cloud_notm}} API 엔드포인트에 연결하려면 다음 명령을 실행하십시오.
  ```
  cf api api.us-south.cf.cloud.ibm.com
  ```
  {: codeblock}
  
  기존 `api.*.bluemix.net` Cloud Foundry API 엔드포인트를 여전히 사용할 수 있지만, 스크립트와 인프라 자동화를 업데이트하여 해당 지역에 대해 다음과 같은 업데이트된 Cloud Foundry API 엔드포인트를 사용할 수 있습니다.

  * api.us-south.cf.cloud.ibm.com(이전의 api.ng.bluemix.net)
  * api.eu-gb.cf.cloud.ibm.com(이전의 api.eu-gb.bluemix.net)
  * api.us-east.cf.cloud.ibm.com(이전의 api.us-east.bluemix.net)
  * api.eu-de.cf.cloud.ibm.com(이전의 api.eu-de.bluemix.net)
  * api.au-syd.cf.cloud.ibm.com(이전의 api.au-syd.bluemix.net)

  관리 콘솔의 리소스 및 정보 페이지에서 올바른 URL을 확인할 수 있습니다. URL은 **API URL** 필드의 API 정보 섹션에
표시됩니다.

2. 다음 명령을 실행하여 {{site.data.keyword.cloud_notm}}에 로그인하십시오.
  ```
cf login
  ```
  {: codeblock}

## 사용자 관리
{: #admin_users}

### 사용자 추가
{: #admin_add_user}

사용자 환경의 사용자 레지스트리에서 {{site.data.keyword.cloud_notm}} 환경에 사용자를 추가하려면
다음 명령을 사용하십시오.
```
cf ba add-user <user_name> <organization> <first_name> <last_name>
```
{: codeblock}

특정 조직에 사용자를 추가하려면 users.write 권한이 있는 관리자(또는 수퍼유저)여야 합니다. 조직 관리자인 경우 **`enable-managers-add-users`** 명령을 실행하는 수퍼유저가 조직에 사용자를 추가하는 기능을 제공할 수 있습니다. 자세한 정보는 [관리자가 사용자를 추가하도록 설정](#clius_emau)을 참조하십시오.

|옵션 |설명 | 
| -------| ------------|
| _userName_ |LDAP 레지스트리 내의 사용자 이름입니다. |
| _organization_ |사용자를 추가할 {{site.data.keyword.cloud_notm}} 조직의 이름 또는 GUID입니다. |
| _firstName_ |조직에 추가할 사용자의 이름입니다. | 
| _lastName_ |조직에 추가할 사용자의 성입니다. | 
{: caption="표 1. cf ba add-user 명령 옵션" caption-side="top"}

긴 **`ba add-user`** 명령어에 대한 별명으로 **`ba au`**를 사용할 수도 있습니다.
{: tip}

### {{site.data.keyword.Bluemix_dedicated_notm}}에서 사용자 초대
{: #admin_dedicated_invite_public}

각 {{site.data.keyword.Bluemix_dedicated_notm}} 환경에 {{site.data.keyword.cloud_notm}}의 클라이언트 소유의 공용 회사 계정이 있습니다. 데디케이티드 환경의 사용자가 {{site.data.keyword.containershort}}에서 클러스터를 작성하려면 관리자가 이 공용 회사 계정에 사용자를 추가해야 합니다. 사용자가 공용 회사 계정에 추가되면 해당 데디케이티드 계정과 공용 계정이 함께 연결됩니다. 그러면 사용자는 IBM ID를 사용하여 데디케이티드와 공용 모두에 동시에 로그인할 수 있으며 데디케이티드 인터페이스를 통해 공용 계정에서 리소스를 작성할 수 있습니다. 자세한 정보는 [IBM Cloud Container Service on Dedicated 설정](/docs/containers?topic=containers-dedicated#dedicated_setup)을 참조하십시오. 데디케이티드 사용자를 공용 계정으로 초대하려면 다음을 수행하십시오.
```
cf ba invite-users-to-public -userid=<user_email> -organization=<dedicated_org_id> -apikey=<public_api_key> -public_org_id=<public_org_id>
```
{: pre}

{{site.data.keyword.cloud_notm}} 공용 계정에 데디케이티드 환경 사용자를 추가하려면 데디케이티드 계정의 관리자여야 합니다.

|옵션 |설명 | 
| -------| ------------|
| -userid |단일 사용자를 초대하는 경우 사용자의 이메일입니다. |
| -organization |현재 데디케이티드 계정 조직의 모든 사용자를 초대하는 경우 데디케이티드 계정 조직 ID입니다. |
| -apikey |공용 계정에 사용자를 초대하는 데 필요한 API 키입니다. 이는 공용 계정의 관리자가 생성해야 합니다. | 
| -public_org_id |사용자를 초대하는 공용 계정 조직의 ID입니다. | 
{: caption="표 2. cf ba invite-users-to-public 명령 옵션" caption-side="top"}

### {{site.data.keyword.Bluemix_dedicated_notm}}에서 초대된 사용자 나열
{: #admin_dedicated_list}

[**`invite-users-to-public`** 명령](#admin_dedicated_invite_public)으로 {{site.data.keyword.Bluemix_notm}} 계정에 데디케이티드 환경 사용자를 초대한 경우, 계정의 사용자를 나열하여 초대 상태를 볼 수 있습니다. 기존 IBM ID가 있는 초대된 사용자의 상태는 ACTIVE입니다. 기존 IBM ID가 없는 초대된 사용자의 상태는 계정에 대한 초대 수락 여부에 따라 PENDING 또는 ACTIVE입니다. {{site.data.keyword.Bluemix_notm}} 계정에 사용자를 나열하려면 다음을 수행하십시오.

```
cf ba invite-users-status -apikey=<public_api_key>
```
{: pre}

{{site.data.keyword.Bluemix_notm}} 공용 계정에 데디케이티드 환경 사용자를 추가하려면 데디케이티드 계정의 관리자여야 합니다.

<dl class="parml">
<dt class="pt dlterm">&lt;public_api_key&gt;</dt>
<dd class="pd">계정에 사용자를 초대하는 데 사용된 API 키입니다. 이는 공용 계정의 관리자가 생성해야 합니다.</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### 사용자 검색
{: #admin_search_user}

사용자를 검색하려면, 선택적 검색 필터 매개변수(이름, 권한, 조직 및 역할)와 함께
다음 명령을 사용하십시오.

```
cf ba search-users -name=<user_name_value> -permission=<permission_value> -organization=<organization_value> -role=<role_value>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| -name |사용자의 이름입니다. |
| -permission |사용자에게 지정된 권한입니다. 사용 가능한 권한은 admin(또는 superuser), login(또는 basic), catalog.read, catalog.write, reports.read, reports.write, users.read 또는 users.write입니다. 동일한 조회에 조직 매개변수가 있으면 이 매개변수를 사용할 수 없습니다. |
| -organization |사용자가 속한 조직 이름입니다. 동일한 조회에 권한 매개변수가 있으면 이 매개변수를 사용할 수 없습니다. | 
| -role |사용자에게 지정된 조직 역할입니다. 사용 가능한 역할은 auditors, managers 및 billing_managers입니다. 이 매개변수와 함께 조직을 지정해야 합니다. | 
{: caption="표 3. cf ba search-users 명령 옵션" caption-side="top"}

긴 **`ba search-users`** 명령어에 대한 별명으로 **`ba su`**를 사용할 수도 있습니다.
{: tip}

### 사용자의 권한 설정
{: #admin_setperm_user}

지정된 사용자의 권한을 설정하려면 다음 명령을 사용하십시오.
```
cf ba set-permissions <user_name> <permission> <access>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _userName_ |사용자의 이름입니다. |
| _permission_ |사용자에게 지정된 권한을 설정합니다. 사용 가능한 권한은 admin(또는 superuser), login(또는 basic), catalog.read, catalog.write, reports.read, reports.write, users.read 또는 users.write입니다. 동일한 조회에 조직 매개변수가 있으면 이 매개변수를 사용할 수 없습니다. |
| _access_ |카탈로그, 보고서 또는 사용자 권한의 경우 `read` 또는 `write`로 액세스 레벨을 설정해야 합니다.|  
{: caption="표 4. cf ba set-permissions 명령 옵션" caption-side="top"}

한 번에 하나의 권한만 설정할 수 있습니다.

긴 **`ba set-permissions`** 명령어에 대한 별명으로 **`ba sp`**를 사용할 수도 있습니다.
{: tip}

<!-- staging-only commands end -->

### 사용자 제거
{: #admin_remov_user}

{{site.data.keyword.Bluemix_notm}} 환경에서 사용자를 제거하려면 다음 명령을 사용하십시오.

```
cf ba remove-user <user_name>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 내의 사용자 이름입니다.</dd>

</dl>

긴 **`ba remove-user`** 명령어에 대한 별명으로 **`ba ru`**를 사용할 수도 있습니다.
{: tip}

### 관리자가 사용자를 추가할 수 있도록 설정
{: #clius_emau}

{{site.data.keyword.Bluemix_notm}} 환경에 수퍼유저 권한이 있는 경우 조직 관리자가 자신이 관리하는 조직에 사용자를 추가할 수 있도록 설정할 수 있습니다. 관리자가 사용자를 추가할 수 있도록 하려면 다음 명령을 사용하십시오.

```
cf ba enable-managers-add-users
```
{: codeblock}

긴 **`ba enable-managers-add-users`** 명령어에 대한 별명으로 **`ba emau`**를 사용할 수도 있습니다.
{: tip}

### 관리자가 사용자를 추가할 수 없도록 설정
{: #clius_dmau}

조직 관리자가 **`enable-managers-add-users`** 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 환경에서 자신이 관리하는 조직에 사용자를 추가할 수 있도록 설정된 경우 및 수퍼유저 권한이 있는 경우 이 설정을 제거할 수 있습니다. 관리자가 사용자를 추가할 수 없도록 하려면 다음 명령을 사용하십시오.

```
cf ba disable-managers-add-users
```
{: codeblock}

긴 **`ba disable-managers-add-users`** 명령어에 대한 별명으로 **`ba dmau`**를 사용할 수도 있습니다.
{: tip}

## 조직 관리
{: #admin_orgs}

### 조직 추가
{: #admin_add_org}

조직을 추가하려면 다음 명령을 사용하십시오.

```
cf ba create-org <organization> <manager>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |추가할 {{site.data.keyword.Bluemix_notm}} 조직의 이름 또는 GUID입니다.|
| _manager_ |조직 관리자의 사용자 이름입니다. |
{: caption="표 5. cf ba create-org 명령 옵션" caption-side="top"}

긴 **`ba create-org`** 명령어에 대한 별명으로 **`ba co`**를 사용할 수도 있습니다.
{: tip}

### 조직 삭제
{: #admin_delete_org}

조직을 삭제하려면 다음 명령을 사용하십시오.

```
cf ba delete-org <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">삭제할 {{site.data.keyword.cloud_notm}} 조직의 이름 또는 GUID입니다.</dd>
</dl>

긴 **`ba delete-org`** 명령어에 대한 별명으로 **`ba do`**를 사용할 수도 있습니다.
{: tip}

### 조직에 사용자 지정
{: #admin_ass_user_org}

{{site.data.keyword.cloud_notm}} 환경에 있는 사용자를 특정 조직에 지정하려면
다음 명령을 사용하십시오.

```
cf ba set-org <user_name> <organization> [<role>]
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _userName_ |사용자의 이름입니다. |
| _organization_ |사용자를 지정할 {{site.data.keyword.cloud_notm}} 조직의 이름 또는 GUID입니다. |
| _role_ |사용자의 역할입니다. 올바른 값은 `OrgManager`, `BillingManager`, `OrgAuditor`입니다. 역할 설명에 대해서는 [역할](/docs/iam?topic=iam-userroles#userroles)을 참조하십시오. |  
{: caption="표 6. cf ba set-org 명령 옵션" caption-side="top"}

긴 **`ba set-org`** 명령어에 대한 별명으로 **`ba so`**를 사용할 수도 있습니다.
{: tip}

### 조직에서 사용자 지정 취소
{: #admin_unass_user_org}

{{site.data.keyword.cloud_notm}} 환경에 있는 사용자를 특정 조직에서 지정 취소하려면
다음 명령을 사용하십시오.

```
cf ba unset-org <user_name> <organization> [<role>]
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _userName_ |사용자의 이름입니다. |
| _organization_ |{{site.data.keyword.cloud_notm}} 조직의 이름 또는 GUID입니다.|
| _role_ |사용자의 역할입니다. 올바른 값은 `OrgManager`, `BillingManager`, `OrgAuditor`입니다. 역할 설명에 대해서는 [역할](/docs/iam?topic=iam-userroles#userroles)을 참조하십시오. |  
{: caption="표 7. cf ba unset-org 명령 옵션" caption-side="top"}

긴 **`ba unset-org`** 명령어에 대한 별명으로 **`ba uo`**를 사용할 수도 있습니다.
{: tip}

### 조직에 할당량 설정
{: #admin_set_org_quota}

특정 조직에 사용 할당량을 설정하려면 다음 명령을 사용하십시오.

```
cf ba set-quota <organization> <plan>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |할당량을 설정할 {{site.data.keyword.cloud_notm}} 조직의 이름 또는 GUID입니다. |
| _plan_ |조직에 대한 할당량 플랜입니다. |  
{: caption="표 8. cf ba set-quota 명령 옵션" caption-side="top"}

긴 **`ba set-quota`** 명령어에 대한 별명으로 **`ba sq`**를 사용할 수도 있습니다.
{: tip}


### 조직의 컨테이너 할당량 찾기
{: #admin_find_containquotas}

조직의 컨테이너 할당량을 찾으려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin containers-quota <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">IBM Cloud의 조직 이름 또는 ID. 이 매개변수는 필수입니다.</dd>
</dl>

긴 **`ibmcloud-admin containers-quota`** 명령어에 대한 별명으로 **`ba cq`**를 사용할 수도 있습니다.
{: tip}

### 조직의 컨테이너 할당량 설정
{: #admin_set_containquotas}

조직의 컨테이너 할당량을 설정하려면 하나 이상의 옵션을 포함하여 다음 명령을 사용하십시오.

```
cf ibmcloud-admin set-containers-quota <organization> <options>
```
{: codeblock}

여러 옵션을 포함할 수 있지만 적어도 하나는 포함해야 합니다.
{: note}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |할당량을 설정할 {{site.data.keyword.cloud_notm}} 조직의 이름 또는 ID입니다.|
| _options_ |선택사항은 **`floating-ips-max value`**(단축 이름 **`fim`**), **`floating-ips-space-default value`**(단축 이름 **`fisd`**), **`memory-max value`**(단축 이름 **`mm`**), **`memory-space-default value`**(단축 이름 **`msd`**) 또는 **`image-limit value`**(단축 이름**`il`**)입니다. 값은 정수여야 합니다.  |  
{: caption="표 9. cf ibmcloud-admin set-containers-quota 명령 옵션" caption-side="top"}

선택적으로 올바른 JSON 오브젝트에 특정 구성 매개변수를 포함하는 파일을 제공할 수 있습니다. **`-file`** 옵션을 사용하면 이 옵션이 우선 적용되고 다른 옵션은 무시됩니다. 옵션을 설정하는 대신에 파일을 제공하려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin set-containers-quota <organization> <-file path_to_JSON_file>
```
{: codeblock}

JSON 파일의 형식은 다음 예제와 같습니다.

```
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: codeblock}

긴 **`ibmcloud-admin set-containers-quota`** 명령어에 대한 별명으로 **`ba scq`**를 사용할 수도 있습니다.
{: tip}

## 영역 관리
{: #admin_spaces}

### 조직에 영역 추가

조직에 영역을 추가하려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin create-space <organization> <space_name>
```

{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |영역을 추가할 조직의 이름 또는 GUID입니다.|
| _spaceName_ |조직에 추가하는 영역의 이름입니다.|  
{: caption="표 10. cf ibmcloud-admin create-space 명령 옵션" caption-side="top"}

긴 **`ba create-space`** 명령어에 대한 별명으로 **`ba cs`**를 사용할 수도 있습니다.
{: tip}

### 조직에서 영역 삭제

조직에서 영역을 삭제하려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin delete-space <organization> <space_name>
```

{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |영역을 제거할 조직의 이름 또는 GUID입니다.|
| _spaceName_ |조직에서 제거하는 영역의 이름입니다.|  
{: caption="표 11. cf ibmcloud-admin delete-space 명령 옵션" caption-side="top"}

긴 **`ba delete-space`** 명령어에 대한 별명으로 **`ba cs`**를 사용할 수도 있습니다.
{: tip}

### 역할과 함께 영역에 사용자 추가

지정된 역할과 함께 영역에 사용자를 작성하려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin set-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |사용자를 추가하는 조직의 이름 또는 GUID입니다.|
| _spaceName_ |사용자를 추가하는 조직의 이름입니다.|
| _userName_ |사용자의 이름입니다. |
| _role_ |사용자의 역할입니다. 올바른 값은 `Manager`, `Developer` 또는 `Auditor`입니다. |  
{: caption="표 12. cf ibmcloud-admin set-space 명령 옵션" caption-side="top"}

긴 **`ba set-space`** 명령어에 대한 별명으로 **`ba ss`**를 사용할 수도 있습니다.
{: tip}


### 영역에서 사용자의 역할 제거

영역에서 사용자 역할을 제거하려면 다음 명령을 사용하십시오.

```
cf ibmcloud-admin unset-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _organization_ |사용자가 속한 조직의 이름 또는 GUID입니다.|
| _spaceName_ |사용자가 속한 영역의 이름입니다.|
| _userName_ |사용자의 이름입니다. |
| _role_ |사용자의 역할입니다. 올바른 값은 `Manager`, `Developer` 또는 `Auditor`입니다. |  
{: caption="표 13. cf ibmcloud-admin unset-space 명령 옵션" caption-side="top"}

긴 **`ba unset-space`** 명령어에 대한 별명으로 **`ba us`**를 사용할 수도 있습니다.
{: tip}

## 카탈로그 관리
{: #admin_catalog}

### 모든 조직에 대해 서비스 사용
{: #admin_ena_service_org}

모든 조직에 대해
{{site.data.keyword.cloud_notm}} 카탈로그에
서비스를 표시하도록 설정하려면 다음 명령을 사용하십시오.

```
cf ba enable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">사용할 서비스 플랜의 이름 또는 GUID입니다. 고유하지 않은 서비스 플랜 이름(예: "표준" 또는 "기본")을 입력하면 선택할 수 있는 서비스 플랜이 프롬프트됩니다. 서비스 플랜 이름을 식별하려면, 홈 페이지에서 서비스 카테고리를 선택한 후에 **추가**를 선택하여 해당 카테고리의 서비스를 보십시오. 서비스 이름을 클릭하여 세부사항 보기를 여십시오. 그러면 해당 서비스에 사용 가능한 서비스 플랜의 이름을 볼 수 있습니다. </dd>
</dl>

긴 **`ba enable-service-plan`** 명령어에 대한 별명으로 **`ba esp`**를 사용할 수도 있습니다.
{: tip}

### 모든 조직에 대해 서비스 사용 안함
{: #admin_dis_service_org}

모든 조직에 대해 {{site.data.keyword.Bluemix_notm}} 카탈로그에
서비스를 표시하지 않도록 설정하려면 다음 명령을 사용하십시오.

```
cf ba disable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">사용할 서비스 플랜의 이름 또는 GUID입니다. 고유하지 않은 서비스 플랜 이름(예: "표준" 또는 "기본")을 입력하면 선택할 수 있는 서비스 플랜이 프롬프트됩니다. 서비스 플랜 이름을 식별하려면, 홈 페이지에서 서비스 카테고리를 선택한 후에 **추가**를 선택하여 해당 카테고리의 서비스를 보십시오. 서비스 이름을 클릭하여 세부사항 보기를 여십시오. 그러면 해당 서비스에 사용 가능한 서비스 플랜의 이름을 볼 수 있습니다.</dd>
</dl>

긴 **`ba disable-service-plan`** 명령어에 대한 별명으로 **`ba dsp`**를 사용할 수도 있습니다.
{: tip}

### 조직에 대한 서비스 가시성 추가
{: #admin_addvis_service_org}

{{site.data.keyword.Bluemix_notm}} 카탈로그에서 특정 서비스를 볼 수 있는 조직을 조직 목록에서 추가할 수 있습니다. 조직이 카탈로그에서 특정 서비스를 볼 수 있도록 허용하려면 다음 명령을 사용하십시오.

```
cf ba add-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _planIdentifier_ |사용할 서비스 플랜의 이름 또는 GUID입니다. 고유하지 않은 서비스 플랜 이름(예: "표준" 또는 "기본")을 입력하면 선택할 수 있는 서비스 플랜이 프롬프트됩니다. 서비스 플랜 이름을 식별하려면, 홈 페이지에서 서비스 카테고리를 선택한 후에 **추가**를 선택하여 해당 카테고리의 서비스를 보십시오. 서비스 이름을 클릭하여 세부사항 보기를 여십시오. 그러면 해당 서비스에 사용 가능한 서비스 플랜의 이름을 볼 수 있습니다. |
| _organization_ |서비스의 가시성 목록에 추가할 조직의 이름 또는 GUID입니다.|  
{: caption="표 14. cf ba add-service-plan-visibility 명령 옵션" caption-side="top"}

긴 **`ba add-service-plan-visibility`** 명령어에 대한 별명으로 **`ba aspv`**를 사용할 수도 있습니다.
{: tip}

### 조직에 대한 서비스 가시성 제거
{: #admin_remvis_service_org}

{{site.data.keyword.Bluemix_notm}} 카탈로그에서
특정 서비스를 볼 수 있는 조직을 조직 목록에서 제거할 수 있습니다. 카탈로그에서 조직에 대한 서비스의 가시성을 제거하려면 다음 명령을 사용하십시오.

```
cf ba remove-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _planIdentifier_ |사용할 서비스 플랜의 이름 또는 GUID입니다. 고유하지 않은 서비스 플랜 이름(예: "표준" 또는 "기본")을 입력하면 선택할 수 있는 서비스 플랜이 프롬프트됩니다. 서비스 플랜 이름을 식별하려면, 홈 페이지에서 서비스 카테고리를 선택한 후에 **추가**를 선택하여 해당 카테고리의 서비스를 보십시오. 서비스 이름을 클릭하여 세부사항 보기를 여십시오. 그러면 해당 서비스에 사용 가능한 서비스 플랜의 이름을 볼 수 있습니다. |
| _organization_ |서비스의 가시성 목록에서 제거할 조직의 이름 또는 GUID입니다.|  
{: caption="표 15. cf ba remove-service-plan-visibility 명령 옵션" caption-side="top"}

긴 **`ba remove-service-plan-visibility`** 명령어에 대한 별명으로 **`ba rspv`**를 사용할 수도 있습니다.
{: tip}

### 조직에 대한 서비스 가시성 편집
{: #admin_editvis_service_org}

{{site.data.keyword.Bluemix_notm}} 카탈로그에서
특정 조직이 볼 수 있는 서비스의 목록을 편집하고 대체할 수도 있습니다. 단일 조직 또는 여러 조직에 대해 표시되는 기존 서비스를 모두 대체하려면
다음 명령을 사용하십시오.

```
cf ba edit-service-plan-visibilities <plan_identifier> <organization_1> <optional_organization_2>
```
{: codeblock}

이 명령은 지정된 조직에 대해 표시되는 기존 서비스를 명령에서 지정하는 서비스로 대체합니다.

|옵션 |설명 | 
| -------| ------------|
| _planIdentifier_ |사용할 서비스 플랜의 이름 또는 GUID입니다. 고유하지 않은 서비스 플랜 이름(예: "표준" 또는 "기본")을 입력하면 선택할 수 있는 서비스 플랜이 프롬프트됩니다. 서비스 플랜 이름을 식별하려면, 홈 페이지에서 서비스 카테고리를 선택한 후에 **추가**를 선택하여 해당 카테고리의 서비스를 보십시오. 서비스 이름을 클릭하여 세부사항 보기를 여십시오. 그러면 해당 서비스에 사용 가능한 서비스 플랜의 이름을 볼 수 있습니다. |
| _organization_ |가시성을 추가할 조직의 이름 또는 GUID입니다. 명령에 추가로 조직 이름 또는 GUID를 입력하여 둘 이상의 조직에 대해
서비스의 가시성을 사용으로 설정할 수 있습니다. |  
{: caption="표 16. cf ba edit-service-plan-visibilities 명령 옵션" caption-side="top"}

긴 **`ba edit-service-plan-visibility`** 명령어에 대한 별명으로 **`ba espv`**를 사용할 수도 있습니다.
{: tip}

## 보고서 관리
{: #admin_add_report}

### 보고서 추가
{: #admin_adding_report}

보안 보고서를 추가하려면 다음 명령을 사용하십시오.

```
cf ba add-report <category> <date> <PDF|TXT|LOG> <RTF>
```
{: codeblock}

보고서 권한에 대해 쓰기 액세스 권한이 있는 경우, 새 카테고리를 작성하고 사용자에 대한 허용된 형식으로 보고서를 추가할 수 있습니다. **`category`** 매개변수에 대해 새 카테고리 이름을 입력하거나 새 보고서를 기존 카테고리에 추가하십시오.

|옵션 |설명 | 
| -------| ------------|
| _category_ |보고서의 카테고리입니다. 이름에 공백이 있는 경우 따옴표를 사용하십시오.|
| _date_ |YYYYMMDD 형식의 보고서 날짜입니다.|  
| _filePath_ |업로드할 보고서 PDF, 텍스트 파일 또는 로그 파일의 경로입니다. |
| _RTF_ |PDF의 RTF(Rich Text Format) 버전을 포함시키는 옵션입니다. 이 옵션은 보고서 PDF의 경로를 포함하는 경우에만 적용됩니다. RTF 버전은 색인 작성 및 검색에 사용됩니다. |
{: caption="표 17. cf ba add-report 명령 옵션" caption-side="top"}

긴 **`ba add-report`** 명령어에 대한 별명으로 **`ba ar`**를 사용할 수도 있습니다.
{: tip}

### 보고서 삭제
{: #admin_del_report}

보안 보고서를 삭제하려면 다음 명령을 사용하십시오.

```
cf ba delete-report <category> <date> <name>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _category_ |보고서의 카테고리입니다. 이름에 공백이 있는 경우 따옴표를 사용하십시오.|
| _date_ |YYYYMMDD 형식의 보고서 날짜입니다.|  
| _name_ |보고서의 이름입니다. |
{: caption="표 18. cf ba delete-report 명령 옵션" caption-side="top"}

긴 **`ba delete-report`** 명령어에 대한 별명으로 **`ba d`r**를 사용할 수도 있습니다.
{: tip}

### 보고서 검색
{: #admin_retr_report}

보안 보고서를 검색하려면 다음 명령을 사용하십시오.

```
cf ba retrieve-report <search>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;search&gt;</dt>
<dd class="pd">보고서의 파일 이름입니다. 이름에 공백이 있는 경우 이름을 따옴표 안에
넣으십시오.</dd>
</dl>

긴 **`ba retrieve-report`** 명령어에 대한 별명으로 **`ba rr`**을 사용할 수도 있습니다.
{: tip}

## 리소스 메트릭 정보 보기
{: #cliresourceusage}

메모리, 디스크 및 CPU 사용량을 포함하여 리소스 메트릭 정보를 확인할 수 있습니다. 실제 및 예약 리소스의 사용량을 포함하여 사용 가능한 실제 및 예약 리소스의 요약을 볼 수 있습니다. 또한 DEA(Droplet Execution Agent) 및 셀(Diego 아키텍처) 사용량 데이터도 볼 수 있습니다. 리소스 메트릭 정보를 보려면 다음 명령을 사용하십시오.

```
cf ba resource-metrics
```

긴 **`ba resource-metrics`** 명령어에 대한 별명으로 **`ba rsm`**을 사용할 수도 있습니다.
{: tip}

## 리소스 메트릭 히스토리 보기
{: #cliresourceusagehistory}

메모리 및 디스크 사용량의 리소스 메트릭 히스토리를 검색할 수 있습니다. 리턴된 메트릭에는 실제 및 예약된 리소스에 사용할 수 있는 총계 중에서 사용된 리소스의 양이 포함되어 있습니다. 메모리 및 디스크 사용량의 히스토리 데이터는 시간별, 일별 또는 월별로 표시할 수 있습니다. 시작 및 종료 날짜를 지정하여 특정 데이터 범위에서 데이터를 검색할 수 있습니다. 날짜가 지정되지 않은 경우 기본 히스토리 데이터는 최근 48시간 동안의 시간별 메모리 데이터입니다. 데이터는 내림차순으로 가장 최근 날짜가 먼저 표시됩니다. 리소스 메트릭 히스토리 정보를 보려면 다음 명령을 사용하십시오.

```
cf ba resource-metrics-history <hourly|daily|monthly>  <memory|disk >  <start|end>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| --hourly | View the historical data for the last 48 hours. This is the default value. |
| --daily | View the historical data daily average for the last 30 days. |  
| --monthly | View the historical data monthly average for the last 6 months. |
| --memory | View the used and total reserved and physical memory. |
| --disk | View the used and total reserved and physical disk. | 
| --start | Specify a start date for daily or monthly in the format of mm-dd-yyyy, or start date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
| --end | Specify an end date for daily or monthly in the format of mm-dd-yyyy, or end date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
{: caption="표 19. cf ba resource-metrics-history 명령 옵션" caption-side="top"}

**예제**

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

다음 명령을 사용하여 이전 명령 매개변수 및 예제의 목록을 볼 수 있습니다.

```
cf ba resource-metrics-history -help
```

긴 **`ba resource-metrics-history`** 명령어에 대한 별명으로 **`ba rsmh`**를 사용할 수도 있습니다.
{: tip}

## 서비스 브로커 관리
{: #admin_servbro}

### 서비스 브로커 나열
{: #clilistservbro}

서비스 브로커를 나열하려면 다음 명령을 사용하십시오.

```
cf ba service-brokers <broker_name>
```
{: codeblock}

모든 서비스 브로커를 나열하려면 **`broker_name`** 매개변수 없이 명령을 입력하십시오.

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">사용자 정의 서비스 브로커의 이름입니다. 특정 서비스 브로커에 대한 정보를 가져오려면 이 매개변수를 사용하십시오. 선택사항.</dd>
</dl>

긴 **`ba service-brokers`** 명령어에 대한 별명으로 **`ba sb`**를 사용할 수도 있습니다.
{: tip}

### 서비스 브로커 추가
{: #cliaddservbro}

서비스 브로커를 추가하여 {{site.data.keyword.Bluemix_notm}} 카탈로그에 사용자 정의 서비스를 추가하려면 다음 명령을 사용하십시오.

```
cf ba add-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _brokerName_ |사용자 정의 서비스 브로커의 이름입니다. |
| _userName_ |서비스 브로커에 액세스할 수 있는 계정의 사용자 이름입니다. |  
| _password_ |서비스 브로커에 액세스할 수 있는 계정의 비밀번호입니다. |
| _brokerURL_ |서비스 브로커의 URL입니다. |
{: caption="표 20. cf ba add-service-broker 명령 옵션" caption-side="top"}

긴 **`ba add-service-broker`** 명령어에 대한 별명으로 **`ba asb`**를 사용할 수도 있습니다.
{: tip}

### 서비스 브로커 삭제
{: #clidelservbro}

{{site.data.keyword.Bluemix_notm}} 카탈로그에서
사용자 정의 서비스를 제거하는 서비스 브로커를 삭제하려면 다음 명령을 사용하십시오.

```
cf ba delete-service-broker <service_broker>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;service_broker&gt;</dt>
<dd class="pd">사용자 정의 서비스 브로커의 이름 또는 GUID입니다.</dd>
</dl>

긴 **`ba delete-service-broker`** 명령어에 대한 별명으로 **`ba dsb`**를 사용할 수도 있습니다.
{: tip}

### 서비스 브로커 업데이트
{: #cliupdservbro}

서비스 브로커를 업데이트하려면 다음 명령을 사용하십시오.

```
cf ba update-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _brokerName_ |사용자 정의 서비스 브로커의 이름입니다. |
| _userName_ |서비스 브로커에 액세스할 수 있는 계정의 사용자 이름입니다. |  
| _password_ |서비스 브로커에 액세스할 수 있는 계정의 비밀번호입니다. |
| _brokerURL_ |서비스 브로커의 URL입니다. |
{: caption="표 21. cf ba update-service-broker 명령 옵션" caption-side="top"}

긴 **`ba update-service-broker`** 명령어에 대한 별명으로 **`ba usb`**를 사용할 수도 있습니다.
{: tip}

## 애플리케이션 보안 그룹 관리
{: #admin_secgro}

애플리케이션 보안 그룹(ASG)에 대해 작업하려면 로컬 또는 데디케이티드 환경의 전체 액세스 관리자여야 합니다. 환경의 모든 사용자는 명령으로 대상이 되는 조직의 사용 가능한 ASG를 나열할 수 있습니다. 그러나 ASG의 작성, 업데이트 또는 바인드를 수행하려면 {{site.data.keyword.Bluemix_notm}} 환경의 관리자여야 합니다.

ASG는 {{site.data.keyword.cloud_notm}} 환경에서 앱의 아웃바운드 트래픽을 제어하는 가상 방화벽 역할을 합니다. 각 ASG는 네트워크 안팎으로 특정 트래픽과 통신을 허용하는 규칙의 목록으로 구성됩니다. 하나 이상의 ASG를 특정 보안 그룹 세트(예: 글로벌 액세스를 적용하는 데 사용되는 그룹 세트)에 바인딩하거나 {{site.data.keyword.Bluemix_notm}} 환경에서 조직 내의 영역에 바인딩할 수 있습니다.

{{site.data.keyword.Bluemix_notm}}는 처음에 외부 네트워크에 대한 모든 액세스가 제한된 상태로 설정됩니다. IBM에서 작성한 두 보안 그룹(`public_networks`, `dns`)을 사용하면 이들 그룹을 기본 Cloud Foundry 보안 그룹 세트에 바인딩할 때 외부 네트워크에 대한 글로벌 액세스가 가능합니다. 글로벌 액세스를 적용하는 데 사용되는 Cloud Foundry의 두 보안 그룹 세트는 **기본 스테이징** 그룹 세트와 **기본 실행** 그룹 세트입니다. 이 그룹 세트는 모든 실행 중인 앱 또는 모든 스테이징 앱에 대한 트래픽을 허용하는 규칙을 적용합니다. 이 두 개의 보안 그룹 세트에 바인딩하지 않으려면 Cloud Foundry 그룹 세트에서 바인드를 해제한 후 특정 영역에 보안 그룹을 바인딩할 수 있습니다. 자세한 정보는 [애플리케이션 보안 그룹 바인딩](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")을 참조하십시오.

IBM에서 작성한 두 개의 보안 그룹에서 **기본 스테이징** 또는 **기본 실행** 그룹 세트의 바인드를 해제하면, `public_networks` 및 `dns`에서 외부 네트워크에 대한 글로벌 액세스를 사용 안함으로 설정합니다. 바인드 해제를 사용할 때는 환경에 있는 실행 및 스테이징 앱에 대한 잠재적 영향을 이해하고 주의를 기울이십시오.
{: important}

보안 그룹 관련 작업을 수행할 수 있는 다음 명령은 Cloud Foundry 1.6 버전을 기반으로 합니다. 필수 필드 및 선택 필드를 포함하여 자세한 정보는 [애플리케이션 보안 그룹 작성 ](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")에 대한 Cloud Foundry 정보를 참조하십시오.

### 보안 그룹 나열
{: #clilissecgro}

보안 그룹을 모두 나열하려면 다음 명령을 사용하십시오.

```
cf ba security-groups
```
{: codeblock}

특정 보안 그룹에 대한 세부사항을 표시하려면 다음 명령을 사용하십시오.

```
cf ba security-groups <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba security-groups`** 명령어에 대한 별명으로 **`ba sg`**를 사용할 수도 있습니다.
{: tip}

### 보안 그룹 작성
{: #clicreasecgro}

보안 그룹을 작성하려면 다음 명령을 사용하십시오.
```
cf ba create-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

작성하는 각 보안 그룹의 이름에 접두부 `adminconsole_`이 추가되어 IBM에서 작성한 보안 그룹과 구별됩니다.

|옵션 |설명 | 
| -------| ------------|
| _groupName_ |보안 그룹의 이름입니다. |
| _filePath_ |규칙 파일의 절대 또는 상대 경로입니다.|  
{: caption="표 22. cf ba create-security-group 명령 옵션" caption-side="top"}

긴 **`ba create-security-group`** 명령어에 대한 별명으로 **`ba csg`**를 사용할 수도 있습니다.
{: tip}

보안 그룹 및 출력 트래픽을 정의하는 규칙 작성에 대한 자세한 정보는 [애플리케이션 보안 그룹 작성](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")을 참조하십시오.

### 보안 그룹 업데이트
{: #cliupdsecgro}

보안 그룹을 업데이트하려면 다음 명령을 사용하십시오.

```
cf ba update-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _groupName_ |보안 그룹의 이름입니다. |
| _filePath_ |규칙 파일의 절대 또는 상대 경로입니다.|  
{: caption="표 23. cf ba update-security-group 명령 옵션" caption-side="top"}

긴 **`ba update-security-group`** 명령어에 대한 별명으로 **`ba usg`**를 사용할 수도 있습니다.
{: tip}

### 보안 그룹 삭제
{: #clidelsecgro}

보안 그룹을 삭제하려면 다음 명령을 사용하십시오.
```
cf ba delete-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba delete-security-group`** 명령어에 대한 별명으로 **`ba dsg`**를 사용할 수도 있습니다.
{: tip}

### 보안 그룹 바인딩
{: #clibindsecgro}

기본 스테이징 보안 그룹 세트를 바인드하려면 다음 명령을 사용하십시오.

```
cf ba bind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba bind-staging-security-group`** 명령어에 대한 별명으로 **`ba bssg`**를 사용할 수도 있습니다.
{: tip}

기본 실행 보안 그룹 세트를 바인드하려면 다음 명령을 사용하십시오.

```
cf ba bind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba bind-running-security-group`** 명령어에 대한 별명으로 **`ba brsg`**를 사용할 수도 있습니다.
{: tip}

보안 그룹을 영역에 바인드하려면 다음 명령을 사용하십시오.

```
cf ba bind-security-group <security-group> <org> <space>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _groupName_ |보안 그룹의 이름입니다. |
| _org_ |보안 그룹을 바인딩할 조직의 이름입니다.|
| _space_ |보안 그룹을 바인딩할 조직 내의 영역 이름입니다.|
{: caption="표 24. cf ba bind-security-group 명령 옵션" caption-side="top"}

긴 **`ba bind-security-group`** 명령어에 대한 별명으로 **`ba bsg`**를 사용할 수도 있습니다.
{: tip}

보안 그룹 바인딩에 대한 자세한 정보는 [애플리케이션 보안 그룹 바인딩](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")을 참조하십시오.

### 보안 그룹 바인드 해제
{: #cliunbindsecgro}

IBM에서 작성한 두 개의 보안 그룹에서 기본 스테이징 그룹 세트의 바인딩을 해제하면, `public_networks` 및 `dns`에서 네트워크 외부에 대한 글로벌 액세스를 사용 안함으로 설정하므로, 환경에 있는 모든 스테이징 앱에 미치는 영향을 이해하고 주의하여 사용해야 합니다.기본 스테이징 보안 그룹 세트에서 바인드 해제하려면 다음 명령을 사용하십시오.

```
cf ba unbind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba unbind-staging-security-group`** 명령어에 대한 별명으로 **`ba ussg`**를 사용할 수도 있습니다.
{: tip}

IBM에서 작성한 두 개의 보안 그룹에서 기본 실행 그룹 세트의 바인딩을 해제하면, `public_networks` 및 `dns`에서 네트워크 외부에 대한 글로벌 액세스를 사용 안함으로 설정하므로, 환경에 있는 모든 실행 앱에 미치는 영향을 이해하고 주의하여 사용해야 합니다.기본 실행 보안 그룹 세트에서 바인드 해제하려면 다음 명령을 사용하십시오.

```
cf ba unbind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">보안 그룹의 이름</dd>
</dl>

긴 **`ba unbind-running-security-group`** 명령어에 대한 별명으로 **`ba brsg`**를 사용할 수도 있습니다.
{: tip}

보안 그룹을 영역에서 바인드 해제하려면 다음 명령을 사용하십시오.

```
cf ba unbind-security-group <security-group> <org> <space>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _groupName_ |보안 그룹의 이름입니다. |
| _org_ |보안 그룹을 바인드 해제할 조직의 이름입니다.|
| _space_ |보안 그룹을 바인드 해제할 조직 내의 영역 이름입니다.|
{: caption="표 25. cf ba unbind-security-group 명령 옵션" caption-side="top"}

긴 **`ba unbind-security-group`** 명령어에 대한 별명으로 **`ba usg`**를 사용할 수도 있습니다.
{: tip}

보안 그룹 바인딩 해제에 대한 자세한 정보는 [애플리케이션 보안 그룹 바인딩 해제](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")을 참조하십시오.

## 빌드팩 관리
{: #admin_buildpack}

### 빌드팩 나열
{: #clilistbuildpack}

앱 카탈로그 쓰기 권한이 있는 경우, 빌드팩을 나열할 수 있습니다. 모든 빌드팩을 나열하거나 특정 빌드팩을 보려면 다음 명령을 사용하십시오.

```
cf ba buildpacks <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">보기 위한 특정 빌드팩을 지정하는 선택적 매개변수입니다.</dd>
</dl>

긴 **`ba buildpacks`** 명령어에 대한 별명으로 **`ba lb`**를 사용할 수도 있습니다.
{: tip}

### 빌드팩 작성 및 업로드
{: #clicreupbuildpack}

앱 카탈로그 쓰기 권한이 있는 경우, 빌드팩을 작성 및 업로드할 수 있습니다. `.zip` 파일 유형이 있는 압축된 파일을 업로드할 수 있습니다. 빌드팩을 업로드하려면 다음 명령을 사용하십시오.

```
cf ba create-buildpack <buildpack_name> <file_path> <position>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _name_ |업로드할 빌드팩의 이름입니다. |
| _filePath_ |빌드팩 압축 파일의 경로입니다. |
| _position_ |빌드팩 자동 삭제 중에 빌드팩이 선택되는 순서입니다. |
{: caption="표 26. cf ba create-buildpack 명령 옵션" caption-side="top"}

긴 **`ba create-buildpack`** 명령어에 대한 별명으로 **`ba cb`**를 사용할 수도 있습니다.
{: tip}

### 빌드팩 업데이트
{: #cliupdabuildpack}

앱 카탈로그 쓰기 권한이 있는 경우, 기존 빌드팩을 업데이트할 수 있습니다. 빌드팩을 업데이트하려면 다음 명령을 사용하십시오.
```
cf ba update-buildpack <buildpack_name> <position> <enabled> <locked>
```
{: codeblock}

|옵션 |설명 | 
| -------| ------------|
| _name_ |업데이트할 빌드팩의 이름입니다. |
| _position_ |빌드팩 자동 삭제 중에 빌드팩이 선택되는 순서입니다. |
| _enabled_ |빌드팩이 스테이징에 사용되는지를 표시합니다. |
| _locked_ |업데이트를 방지하기 위해 빌드팩이 잠기는지를 표시합니다. | 
{: caption="표 27. cf ba update-buildpack 명령 옵션" caption-side="top"}

긴 **`ba update-buildpack`** 명령어에 대한 별명으로 **`ba ub`**를 사용할 수도 있습니다.
{: tip}

### 빌드팩 삭제
{: #clidelbuildpack}

앱 카탈로그 쓰기 권한이 있는 경우, 기존 빌드팩을 삭제할 수 있습니다. 빌드팩을 삭제하려면 다음 명령을 사용하십시오.
```
cf ba delete-buildpack <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">삭제할 빌드팩의 이름입니다.</dd>
</dl>

긴 **`ba delete-buildpack`** 명령어에 대한 별명으로 **`ba db`**를 사용할 수도 있습니다.
{: tip}
