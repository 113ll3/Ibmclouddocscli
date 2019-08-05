---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# 계정, 사용자 및 Cloud Foundry 조직 관리
{: #ibmcloud_commands_account}

다음 명령을 사용하여 계정, 계정의 사용자 및 퍼블릭 Cloud Foundry 환경의 조직, 영역 및 역할을 관리하십시오.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

모든 조직을 나열합니다.
```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>지역 이름입니다. 지정된 지역의 조직을 나열합니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다. 'all'로 설정되면 모든 지역의 모든 조직이 나열됩니다.</dd>
   <dt>--guid</dt>
   <dd>조직의 guid를 표시합니다. 이 옵션은 `--output`과 배타적입니다. </dd>
   <dt>--output FORMAT</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 `--guid`와 배타적입니다. </dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>계정 ID. 계정의 조직을 나열합니다. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다. `all`로 설정되면 모든 계정의 조직을 나열합니다. 이 옵션은 `-u`와 배타적입니다. </dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>계정 소유자 이름입니다. 해당 사용자가 소유한 계정 아래의 조직을 나열합니다. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다. 'all'로 설정되면 모든 계정 아래 조직이 나열됩니다. 이 옵션은 `-c`와 배타적입니다. </dd>
   </dl>

<strong>예제</strong>:

GUID를 표시하여 `us-south` 지역의 모든 조직 나열: 
```
ibmcloud account orgs -r us-south --guid
```

JSON 형식으로 모든 조직 나열: 
```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

지정된 조직의 정보를 표시합니다.
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>-r REGION</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 기본값은 현재 지역입니다. `all`로 설정되면 모든 지역에서 지정된 이름을 가지는 조직이 나열됩니다. </dd>
   <dt>--guid</dt>
   <dd>조직의 GUID를 검색하고 표시합니다. 조직의 기타 모든 출력은 억제됩니다. 이 옵션은 `--output`과 배타적입니다. </dd>
   <dt>--output REGION</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 `--guid`와 배타적입니다. </dd>
   </dl>

<strong>예제</strong>:

조직 `IBM`의 정보를 GUID를 표시하여 보여줍니다.
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

조직을 작성합니다. 이 조작은 계정 소유자만 실행할 수 있습니다.
```
ibmcloud account org-create ORG_NAME [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>작성될 조직의 이름입니다. </dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
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
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>복제할 기존 조직의 이름입니다.</dd>
   <dt>REGION_NAME(필수)</dt>
   <dd>복제된 조직을 호스팅하는 지역의 이름입니다.</dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
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
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>OLD_ORG_NAME(필수)</dt>
   <dd>이름이 변경될 조직의 이전 이름입니다.</dd>
   <dt>NEW_ORG_NAME(필수)</dt>
   <dd>이름이 변경될 조직의 새 이름입니다.</dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

모든 계정 영역을 나열합니다.
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-o ORG_NAME(선택사항)</dt>
   <dd>조직 이름입니다. 지정된 조직 아래의 영역을 나열합니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>-r REGION-NAME(선택사항)</dt>
   <dd>지역 이름입니다. 지정된 지역의 영역을 나열합니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   <dt>--output FORMAT(선택사항)</dt>
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

특정 영역의 정보를 표시합니다.
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
   <dd>영역의 GUID를 검색하고 표시합니다. 영역의 기타 모든 출력은 억제됩니다. 이 옵션은 `--output`과 배타적입니다. </dd>
   <dt>--output FORMAT</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 영역의 기타 모든 출력은 억제됩니다. 이 옵션은 `--guid`와 배타적입니다. </dd>
   <dt>--security-group-rules</dt>
   <dd>영역과 연관된 모든 보안 그룹의 규칙을 검색합니다.</dd>
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

이 명령은 [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘") 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

이 명령은 [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘") 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

이 명령은 [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘") 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

역할별로 지정된 조직의 사용자를 표시합니다.

```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>ORG_NAME(필수)</dt>
<dd>조직의 이름입니다.</dd>
<dt>-a, -all(선택사항)</dt>
<dd>지정된 조직의 모든 사용자를 나열하지만, 역할별로 그룹화하지는 않습니다.</dd>
<dt>-r, --region REGION(선택사항)</dt>
<dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

조직에 사용자를 추가합니다(조직 관리자 필요).
```
 ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>사용자의 이름입니다.</dd>
<dt>ORG(필수)</dt>
<dd>조직의 이름입니다.</dd>
<dt>-r, --region REGION(선택사항)</dt>
<dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

조직에서 사용자를 제거합니다(조직 관리자 또는 사용자만).
```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--force, -f</dt>
<dd>확인 없이 삭제 강제 실행합니다.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

현재 사용자의 모든 조직 역할을 가져옵니다.
```
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>-u</dt>
   <dd>사용자 ID입니다. 지정되지 않은 경우 현재 사용자로 기본값이 지정됩니다.</dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

사용자에게 조직 역할을 지정합니다. 이 조작은 조직 관리자만 실행할 수 있습니다.
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>지정할 사용자의 이름입니다.</dd>
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
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직에 `OrgManager` 역할로 지정합니다.
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
CLI를 사용하여 조직 및 영역 역할을 설정할 수 있지만, 기타 권한을 설정하려면 UI를 사용해야 합니다. 자세한 정보는 [리소스에 대한 액세스 관리](/docs/iam?topic=iam-iammanidaccser)를 참조하십시오.
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

사용자로부터 조직 역할을 제거합니다. 이 조작은 조직 관리자만 수행할 수 있습니다.
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>제거할 사용자의 이름입니다.</dd>
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
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
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
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG_NAME(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>영역의 이름입니다.</dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

특정 조직 아래에 있는 현재 사용자의 모든 영역 역할 가져오기

```
ibmcloud account space-roles ORG [-r, --region REGION] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>ORG(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>-r(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

사용자에게 영역 역할을 지정합니다. 이 조작은 영역 관리자만 실행할 수 있습니다.
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>지정할 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 지정되는 조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>이 사용자가 지정되는 영역의 이름입니다.</dd>
   <dt>SPACE_ROLE(필수)</dt>
   <dd>이 사용자가 지정되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul>
   </dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
   </dl>

<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직 및 `Cloud` 영역에 `SpaceManager` 역할로 지정합니다.
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

사용자로부터 영역 역할을 제거합니다. 이 조작은 영역 관리자만 실행할 수 있습니다.
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

   <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>제거할 사용자의 이름입니다.</dd>
   <dt>ORG_NAME(필수)</dt>
   <dd>이 사용자가 제거되는 조직의 이름입니다.</dd>
   <dt>SPACE_NAME(필수)</dt>
   <dd>이 사용자가 제거되는 영역의 이름입니다.</dd>
   <dt>SPACE_ROLE(필수)</dt>
   <dd>이 사용자가 제거되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul></dd>
   <dt>-r, --region REGION(선택사항)</dt>
   <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
    </dl>


<strong>예제</strong>:

사용자 `Mary`를 `IBM` 조직 및 `Cloud` 영역에서 `SpaceManager` 역할로 제거합니다.
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

현재 사용자의 모든 계정 나열:
```
ibmcloud account list [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

지정된 조직의 계정을 표시합니다(조직 사용자 필요).
```
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid | --output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-r(선택사항)</dt>
  <dd>지역 이름입니다. 지정되지 않은 경우 현재 지역으로 기본값이 지정됩니다.</dd>
  <dt>--guid(선택사항)</dt>
  <dd>계정 ID만 표시</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

계정 세부사항을 표시합니다.
```
ibmcloud account show
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

현재 대상으로 지정된 계정의 세부사항 표시:
```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

특정 계정 업데이트:
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>SoftLayer 계정의 서비스 엔드포인트 연결을 사용 또는 사용 안함으로 설정합니다.</dd>
</dl>

<strong>예제</strong>:

현재 계정에 대한 서비스 엔드포인트 연결성을 사용으로 설정:
```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

SoftLayer 계정 감사 로그 나열:
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>조치. 조치와 함께 감사 로그를 나열합니다.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>종료 날짜. 종료 날짜 이전의 감사 로그를 나열합니다. 지원되는 형식은 yyyy-MM-ddTHH:mm:ss입니다.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>오브젝트. 오브젝트와 함께 감사 로그를 나열합니다.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>오브젝트 유형. 오브젝트 유형과 함께 감사 로그를 나열합니다.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>시작 날짜. 시작 날자 이후의 감사 로그를 나열합니다. 지원되는 형식은 yyyy-MM-ddTHH:mm:ss입니다.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>사용자 이름. 사용자 이름과 함께 감사 로그를 나열합니다.</dd>
</dl>

<strong>예제</strong>:

감사 로그 나열:
```
ibmcloud account audit-logs
```

## ibmcloud account users
{: #ibmcloud_account_users}

계정과 연관된 사용자를 표시합니다. 이 조작은 계정 소유자만 실행할 수 있습니다.
```
ibmcloud account users [-c, --account-id ACCOUNT_ID] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>-c(선택사항)</dt>
<dd>계정 ID. 지정되지 않은 경우 현재 계정으로 기본값이 지정됩니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

계정에서 사용자를 제거합니다(계정 소유자 전용).
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

계정에 사용자 초대:
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>초대될 사용자의 이메일입니다.</dd>
   <dt>-o ORG</dt>
   <dd>사용자를 초대할 조직</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>조직 역할. 올바른 입력은 OrgManager, BillingManager, OrgAuditor 및 OrgUser입니다. 이를 생략하면 OrgUser 역할이 설정됩니다.</dd>
   <dt>-s SPACE</dt>
   <dd>사용자를 초대할 영역</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>영역 역할. 올바른 입력은 SpaceManager, SpaceDeveloper 및 SpaceAuditor입니다.</dd>
</dl>

액세스 권한을 지정할 준비가 되지 않았거나 Cloud Foundry 액세스 권한 대신 IAM 정책을 지정하려는 경우, 액세스 권한이 없는 사용자를 초대하고 나중에 이를 지정할 수 있습니다. 사용자에게 액세스 권한을 지정하는 데 대한 자세한 정보는 [리소스에 대한 액세스 관리](/docs/iam?topic=iam-iammanidaccser#assign_new_access)를 참조하십시오.
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

사용자(계정 admin)에게 초대를 재발송합니다.
```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>다시 초대될 사용자의 이메일입니다.</dd>
</dl>

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

계정 감사 로그 나열

```
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE] [--output FORMAT]
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--user-name <i>USER_NAME</i>(선택사항)</dt>
   <dd>사용자 이름과 함께 감사 로그를 나열합니다.</dd>
   <dt>--object-type <i>OBJECT_TYPE</i>(선택사항)</dt>
   <dd>오브젝트 유형과 함께 감사 로그를 나열합니다.</dd>
   <dt>--object <i>OBJECT</i>(선택사항)</dt>
   <dd>오브젝트와 함께 감사 로그를 나열합니다.</dd>
   <dt>--action <i>ACTION</i>(선택사항)</dt>
   <dd>조치와 함께 감사 로그를 나열합니다.</dd>
   <dt>--start-date <i>START_DATE</i>(선택사항)</dt>
   <dd>시작 날자 이후의 감사 로그를 나열합니다. 지원되는 형식은 yyyy-MM-ddTHH:mm:ss입니다.</dd>
   <dt>--end-date <i>END_DATE</i>(선택사항)</dt>
   <dd>종료 날짜 이전의 감사 로그를 나열합니다. 지원되는 형식은 yyyy-MM-ddTHH:mm:ss입니다.</dd>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

사용자 환경 설정의 세부사항을 표시합니다.

```
ibmcloud account user-preference [--output FORMAT]
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

사용자 환경 설정 업데이트

```
ibmcloud account user-preference-update (--position NEW_POSITION) [--output FORMAT]
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--position <i>NEW_POSITION</i>(선택사항)</dt>
   <dd>사용자의 지위(예: 'manager' 또는 'student')를 설정합니다. </dd>
   <dt>--output FORMAT(선택사항)</dt>
   <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

플랫폼 알림 구독:
```
ibmcloud account platform-notification-subscribe (--type TYPE)
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--type <i>TYPE</i>(선택사항)</dt>
   <dd>알림 유형('unplanned_events', 'planned_maintenance' 중 하나)입니다. </dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

플랫폼 알림 구독 해제:
```
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
   <dt>--type <i>TYPE</i>(선택사항)</dt>
   <dd>알림 유형('unplanned_events', 'planned_maintenance' 중 하나)입니다. </dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

도메인의 인증서 정보 나열: 
```
ibmcloud account domain-cert DOMAIN_NAME
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
ibmcloud account domain-cert ibmcxo-eventconnect.com
```

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

현재 조직의 지정된 도메인에 인증서를 추가합니다.
```
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

현재 조직의 지정된 도메인에서 인증서를 제거합니다.
```
ibmcloud account domain-cert-remove DOMAIN [-f]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>DOMAIN(필수)</dt>
   <dd>인증서가 제거되는 도메인입니다.</dd>
   <dt>-f(선택사항)</dt>
   <dd>확인 없이 삭제 강제 실행합니다.</dd>
   </dl>
