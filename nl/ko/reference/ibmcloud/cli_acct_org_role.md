---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 계정, 사용자 및 조직
 {: #ibmcloud_commands_account}

 다음 명령을 사용하여 계정, 계정의 사용자 및 조직, 영역과 역할을 관리하십시오.
  {: shortdesc}

  <table summary="계정, 조직, 영역 및 역할을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
   <thead>
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
   </tr>
   </tbody>
   </table>

 ## ibmcloud account orgs
{: #ibmcloud_account_orgs}

모든 조직 나열

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>지역 이름입니다. 지정된 지역의 조직을 나열합니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다. 'all'로 설정되면 모든 지역의 모든 조직이 나열됩니다.</dd>
   <dt>--guid</dt>
   <dd>조직의 guid를 표시합니다. 이 옵션은 '--output'과 배타적입니다.</dd>
   <dt>--output FORMAT</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--guid'와 배타적입니다.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>계정 ID. 지정된 계정의 조직을 나열합니다. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다. 'all'로 설정되면 모든 계정 아래 조직이 나열됩니다. 이 옵션은 '-u'와 배타적입니다.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>계정 소유자 이름입니다. 지정된 사용자가 소유한 계정 아래 조직을 나열합니다. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다. 'all'로 설정되면 모든 계정 아래 조직이 나열됩니다. 이 옵션은 '-c'와 배타적입니다.</dd>
   </dl>

<strong>예제</strong>:

지역: `us-south`의 모든 조직을 GUID를 표시하여 나열합니다.

```
ibmcloud account orgs -r us-south --guid
```

JSON 형식으로 모든 조직 나열

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

지정된 조직의 정보 표시.

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>-r REGION</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 기본값은 현재 지역입니다. 'all'로 설정된 경우 모든 지역 중 지정된 이름이 있는 조직이 나열됩니다.</dd>
   <dt>--guid</dt>
   <dd>지정된 조직의 GUID를 검색하고 표시합니다. 조직의 다른 모든 출력은 억제됩니다. 이 옵션은 '--output'과 배타적입니다.</dd>
   <dt>--output REGION</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--guid'와 배타적입니다.</dd>
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
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>조직 이름입니다. 지정된 조직 아래의 영역을 나열합니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>-r REGION-NAM</dt>
   <dd>지역 이름입니다. 지정된 지역 아래의 영역을 나열합니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   <dt>--output FORMAT</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
   </dl>

<strong>예제</strong>:

모든 영역 나열:

```
ibmcloud account spaces
```

JSON 형식으로 `org_example` 조직의 모든 영역 나열:

```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

지정된 영역의 정보 표시

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>SPACE_NAME(필수)</dt>
   <dd>표시할 영역의 이름입니다.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>--guid</dt>
   <dd>지정된 영역의 GUID를 검색하고 표시합니다. 영역의 다른 모든 출력은 억제됩니다. 이 옵션은 '--output'과 배타적입니다.</dd>
   <dt>--output FORMAT</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 영역의 다른 모든 출력은 억제됩니다. 이 옵션은 '--guid'와 배타적입니다.</dd>
   <dt>--security-group-rules</dt>
   <dd>영역과 연관된 모든 보안 그룹에 대한 규칙을 검색합니다.</dd>
   </dl>

<strong>예제</strong>:

`space_example` 영역의 정보 표시:

```
ibmcloud account space space_example
```

`space_example` 영역의 GUID 표시:

```
ibmcloud account space space_example --guid
```

JSON 형식으로 `space_example` 영역의 정보 표시:

```
ibmcloud account space space_example --output JSON
```

`space_example` 영역의 보안 그룹 규칙 표시:

```
ibmcloud account space space_example --security-group-rules
```

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
