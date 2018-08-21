---

copyright:

  years: 2018


lastupdated: "2018-08-15"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 계정, 조직 및 역할 관리를 위한 명령
 {: #ibmcloud_commands_account}

<table summary="계정, 조직, 영역 및 역할을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 1. 계정, 조직, 영역 및 역할 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">계정, 조직, 영역 및 역할 관리를 위한 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list
](cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users
](cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
  <td>[ibmcloud app domain-cert](cli_acct_org_role.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](cli_acct_org_role.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](cli_acct_org_role.html#ibmcloud_app_domain_cert_remove)</td>
 </tr>
 </tbody>
 </table>

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

### ibmcloud account org
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

### ibmcloud account org-create
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

### ibmcloud account org-replicate
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

### ibmcloud account org-rename
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

### ibmcloud account spaces
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

### ibmcloud account space
{: #ibmcloud_account_space}

이 명령은 [cf space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

이 명령은 [cf create-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


이 명령은 [cf rename-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


이 명령은 [cf delete-space ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

### ibmcloud account org-users
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

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

조직에 사용자를 추가합니다(조직 관리자 필요).

```
 ibmcloud account org-user-add USER_NAME ORG
```

### ibmcloud account org-user-remove
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

### ibmcloud account org-roles
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

### ibmcloud account org-role-set
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

### ibmcloud account org-role-unset
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

### ibmcloud account space-users
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

### ibmcloud account space-role-set
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

### ibmcloud account space-role-unset
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

### ibmcloud account list
{: #ibmcloud_account_list}

현재 사용자의 모든 계정 나열

```
ibmcloud account list
```

<strong>전제조건</strong>: 엔드포인트, 로그인

### ibmcloud account org-account
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

### ibmcloud account users
{: #ibmcloud_account_users}

계정과 연관된 사용자를 표시합니다. 이 조작은 계정 소유자만 수행할 수 있습니다.

```
ibmcloud account users
```

### ibmcloud account user-remove
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

### ibmcloud account user-invite
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

### ibmcloud account user-reinvite
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

### ibmcloud iam access-groups
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

### ibmcloud iam access-group
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

### ibmcloud iam access-group-create
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

### ibmcloud iam access-group-update
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

### ibmcloud iam access-group-delete
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

### ibmcloud iam access-group-users
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

### ibmcloud iam access-group-user-add
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

### ibmcloud iam access-group-user-remove
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

### ibmcloud iam access-group-user-purge
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

### ibmcloud iam access-group-service-ids
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

### ibmcloud iam access-group-service-id-add
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

### ibmcloud iam access-group-service-id-remove
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

### ibmcloud iam access-group-service-id-purge
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

### ibmcloud iam access-group-policies
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

### ibmcloud iam access-group-policy
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

### ibmcloud iam access-group-policy-create
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

### ibmcloud iam access-group-policy-update
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

### ibmcloud iam access-group-policy-delete
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

### ibmcloud app domain-cert
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

### ibmcloud app domain-cert-add
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

### ibmcloud app domain-cert-remove
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
