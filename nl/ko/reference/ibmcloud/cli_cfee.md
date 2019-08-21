---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-31"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Cloud Foundry Enterprise Environment 서비스에 대한 작업
{: #ibmcloud_commands_cfee}

{{site.data.keyword.cfee_full}}(CFEE)를 사용하여 격리된 여러 엔터프라이즈급 Cloud Foundry 플랫폼을 요청 시 인스턴스화할 수 있습니다. IBM Cloud Foundry Enterprise 서비스의 인스턴스는 {{site.data.keyword.cloud_notm}}의 고유 계정 내에서 실행됩니다. 환경은 격리된 하드웨어(Kubernetes 클러스터)에 배치됩니다. 액세스 제어, 용량, 버전 업데이트, 리소스 사용 및 모니터링을 포함하여 환경을 완벽히 제어할 수 있습니다.

다음 명령을 사용하여 CFEE 환경, 조직, 영역, 사용자 및 역할을 관리하십시오.
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE 환경 나열:
```
ibmcloud cfee environments
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

CFEE 환경의 세부사항 표시:
```
ibmcloud cfee environment NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>NAME(필수)</dt>
   <dd>표시할 환경의 이름입니다.</dd>
   <dt>--id</dt>
   <dd>ID만 표시</dd>
  </dl>

<strong>예제</strong>:

CFEE 환경 `env_example`의 세부사항 표시:
```
ibmcloud cfee environment env_example
```
{: codeblock}

CFEE 환경 `env_example`의 ID 표시:
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

모든 조직 나열:
```
ibmcloud cfee orgs [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

모든 조직 나열:
```
ibmcloud cfee orgs
```
{: codeblock}

CFEE 환경 `env_example`의 모든 조직 나열:
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

조직의 세부사항 표시:
```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>--guid</dt>
   <dd>조직 GUID만 표시합니다. 조직의 다른 모든 출력은 억제됩니다.</dd>
  </dl>

<strong>예제</strong>:

CFEE 조직 `org_example`의 세부사항 표시:
```
ibmcloud cfee org org_example
```
{: codeblock}

CFEE 환경 `env_example`의 CFEE 조직 `org_example` 세부사항 표시:
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

CFEE 조직 `org_example`의 GUID 표시:
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

조직 작성:
```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>작성될 조직의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>새로 작성된 조직에 지정할 할당량입니다(지정되지 않은 경우 기본 할당량 사용).</dd>
  </dl>

<strong>예제</strong>:

CFEE 조직 `org_example` 작성:
```
ibmcloud cfee org-create org_example
```
{: codeblock}

CFEE 환경 `env_example`의 CFEE 조직 `org_example` 작성:
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

할당량이 `quote_example`인 CFEE 조직 `org_example` 작성:
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

조직 삭제:
```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>삭제할 조직의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 삭제 강제 실행</dd>
  </dl>

<strong>예제</strong>:

CFEE 조직 `org_example` 삭제:
```
ibmcloud cfee org-delete org_example
```
{: codeblock}

CFEE 환경 `env_example`의 CFEE 조직 `org_example` 삭제:
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

확인 없이 CFEE 조직 `org_example` 삭제:
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

지정된 조직의 사용자를 역할순으로 표시:
```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>-a, --all</dt>
   <dd>지정된 조직의 모든 사용자 나열</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

CFEE 조직 `org_example`의 사용자 표시:
```
ibmcloud cfee org-users org_example
```
{: codeblock}

CFEE 환경 `env_example`의 CFEE 조직 `org_example`에 있는 사용자 표시:
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

CFEE 조직 `org_example`의 모든 사용자 나열:
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

사용자에게 조직 역할 지정(조직 관리자 필요)
```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>지정될 사용자의 이메일입니다.</dd>
   <dt>ORG(필수)</dt>
   <dd>이 사용자가 지정되는 조직의 이름입니다.</dd>
   <dt>ROLE(필수)</dt>
   <dd>이 사용자가 지정되는 조직 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>OrgManager: 이 역할은 사용자를 초대 및 관리하고, 플랜을 선택 및 변경하며, 지출 한계를 설정할 수 있습니다.</li>
   <li>BillingManager: 이 역할은 청구 계정 및 결제 정보를 작성하고 관리할 수 있습니다.</li>
   <li>OrgAuditor: 이 역할은 조직 정보 및 보고서에 대한 읽기 전용 액세스 권한을 보유합니다.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

`org_example` 조직에 있는 `test@exmaple.com` 사용자에게 `BillingManager` 역할 지정:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```
{: codeblock}

CFEE 환경 `env_example`의 `org_example` 조직에 있는 `test@exmaple.com` 사용자에게 `BillingManager` 역할 지정:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

사용자에서 조직 역할 제거(조직 관리자 또는 사용자 전용):
```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>제거할 사용자의 이메일입니다.</dd>
   <dt>ORG(필수)</dt>
   <dd>이 사용자가 제거되는 조직의 이름입니다.</dd>
   <dt>ROLE(필수)</dt>
   <dd>이 사용자가 제거되는 조직 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>OrgManager: 이 역할은 사용자를 초대 및 관리하고, 플랜을 선택 및 변경하며, 지출 한계를 설정할 수 있습니다.</li>
   <li>BillingManager: 이 역할은 청구 계정 및 결제 정보를 작성하고 관리할 수 있습니다.</li>
   <li>OrgAuditor: 이 역할은 조직 정보 및 보고서에 대한 읽기 전용 액세스 권한을 보유합니다.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

`org_example` 조직에서 `test@exmaple.com` 사용자의 `BillingManager` 역할 제거:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```
{: codeblock}

CFEE 환경 `env_example`의 `org_example` 조직에서 `test@exmaple.com` 사용자의 `BillingManager` 역할 제거:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

모든 영역 나열:
```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

모든 영역 나열:
```
ibmcloud cfee spaces
```
{: codeblock}

조직 `org_example` 및 CFEE 환경 `env_example`의 모든 영역 나열
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

지정된 영역의 정보 표시
```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>SPACE(필수)</dt>
   <dd>표시할 영역의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>--guid</dt>
   <dd>영역의 GUID를 검색하고 표시합니다. 영역의 기타 모든 출력은 억제됩니다.</dd>
   <dt>-o, --org ORG</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
   <dt>--security-group-rules</dt>
   <dd>영역과 연관된 모든 보안 그룹의 규칙을 검색합니다.</dd>
  </dl>

<strong>예제</strong>:

이름이 `space_example`인 영역의 세부사항 표시:
```
ibmcloud cfee space space_example
```
{: codeblock}

`space_example` 영역의 GUID 검색 및 표시:
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

`space_example` 영역과 연관된 모든 보안 그룹에 대한 규칙 표시:
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

영역 `space_example`, 조직 `org_example` 및 CFEE 환경 `env_example`의 세부사항 표시:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

영역 작성:
```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>SPACE(필수)</dt>
   <dd>작성할 영역의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>-o, --org ORG</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

이름이 `space_example`인 영역 작성:
```
ibmcloud cfee space-create space_example
```
{: codeblock}

CFEE 환경 `env_example`의 조직 `org_example` 아래에 이름이 `space_example`인 영역 작성:
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

영역 이름 바꾸기:
```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>OLD_NAME(필수)</dt>
   <dd>이름을 바꿀 영역의 이전 이름입니다.</dd>
   <dt>NEW_NAME(필수)</dt>
   <dd>이름을 바꿀 영역의 새 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>-o, --org ORG</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

영역 이름 `space_example`을 `new_pace_example`로 바꾸기:
```
ibmcloud cfee space-rename space_example new_pace_example
```
{: codeblock}

조직 `org_example` 및 CFEE 환경 `env_example`에서 영역 이름 `space_example`을 `new_pace_example`로 바꾸기:
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

영역 삭제:
```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>SPACE(필수)</dt>
   <dd>삭제할 영역의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 삭제 강제 실행합니다.</dd>
   <dt>-o, --org ORG</dt>
   <dd>조직 이름입니다. 지정되지 않은 경우 현재 조직으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

영역 `space_example` 삭제:
```
ibmcloud cfee space-delete space_example
```
{: codeblock}

확인 없이 조직 `org_example` 및 CFEE 환경 `env_example`에 영역 `space_example` 삭제:
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

사용자에게 영역 역할 지정
```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>지정될 사용자의 이메일입니다.</dd>
   <dt>ORG(필수)</dt>
   <dd>이 사용자가 지정되는 조직의 이름입니다.</dd>
   <dt>SPACE(필수)</dt>
   <dd>이 사용자가 지정되는 영역의 이름입니다.</dd>
   <dt>ROLE(필수)</dt>
   <dd>이 사용자가 지정되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 영역에 대한 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

조직 `org_example` 및 영역 `space_example`에 대한 사용자 `test@exmaple.com`을 `SpaceManager` 역할로 지정:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```
{: codeblock}

환경 `env_example`에서 조직 `org_example` 및 영역 `space_example`에 대한 사용자 `test@exmaple.com`을 `SpaceManager` 역할로 지정:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

사용자에게서 영역 역할 제거
```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_EMAIL(필수)</dt>
   <dd>제거할 사용자의 이메일입니다.</dd>
   <dt>ORG(필수)</dt>
   <dd>이 사용자가 제거되는 조직의 이름입니다.</dd>
   <dt>SPACE(필수)</dt>
   <dd>이 사용자가 제거되는 영역의 이름입니다.</dd>
   <dt>ROLE(필수)</dt>
   <dd>이 사용자가 제거되는 영역 역할의 이름입니다. 예를 들어, 다음과 같습니다.
   <ul>
   <li>SpaceManager: 이 역할은 사용자를 초대 및 관리하고 영역에 대한 기능을 사용할 수 있습니다.</li>
   <li>SpaceDeveloper: 이 역할은 앱 및 서비스를 작성 및 관리하며 로그 및 보고서를 볼 수 있습니다.</li>
   <li>SpaceAuditor: 이 역할은 영역에 대한 설정 및 로그, 보고서를 볼 수 있습니다.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

조직 `org_example` 및 영역 `space_example`에 대한 `SpaceManager` 역할의 사용자 `test@exmaple.com` 제거:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```
{: codeblock}

환경 `env_example`에서 조직 `org_example` 및 영역 `space_example`에 대한 `SpaceManager` 역할의 사용자 `test@exmaple.com` 제거:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

특정 조직 아래에 있는 현재 사용자의 모든 영역 역할 가져오기

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

조직 `org_example` 아래에 있는 현재 사용자의 모든 영역 역할 가져오기:
```
ibmcloud cfee space-roles org_example
```
{: codeblock}

조직 `org_example` 및 환경 `env_example` 아래에 있는 현재 사용자의 모든 영역 역할 가져오기:
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

지정된 영역의 사용자를 역할순으로 표시
```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>ORG(필수)</dt>
   <dd>조직의 이름입니다.</dd>
   <dt>SPACE(필수)</dt>
   <dd>영역의 이름입니다.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 환경 이름입니다. 지정되지 않은 경우 현재 CFEE 환경으로 기본값이 지정됩니다.</dd>
  </dl>

<strong>예제</strong>:

영역 `space_example` 및 조직 `org_example`의 모든 사용자 표시:
```
ibmcloud cfee space-users org_example space_example
```
{: codeblock}

영역 `space_example` 및 조직 `org_example` 및 환경 `env_example`의 모든 사용자 표시:
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Cloud Foundry Enterprise Environment의 인스턴스를 작성하도록 요청:
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-n, --name NAME(필수)</dt>
  <dd>CFEE의 이름을 지정합니다. 이름은 24자 이하여야 하고 문자로 시작해야 하며 영숫자 문자, '-', '_' 및 '.'만 포함해야 합니다.</dd>
  <dt>--location LOCATION(필수)</dt>
  <dd>이 CFEE를 프로비저닝할 데이터 센터(예: dal10)를 지정합니다. 사용 가능한 데이터 센터를 찾으려면 ibmcloud cfee create-locations를 실행하십시오.</dd>
  <dt>--cells CELLS</dt>
  <dd>이 CFEE의 셀 수를 지정합니다. 기본값은 2이고 최소값은 1입니다. 셀이 하나인 CFEE에서는 고가용성을 사용할 수 없습니다.</dd>
  <dt>--private-access</dt>
  <dd>CFEE의 일부로 프로비저닝되는 PostgreSQL 데이터베이스의 네트워크 액세스 유형을 지정합니다. 계정이 VRF이고 서비스 엔드포인트가 사용 가능한 경우에만 플래그를 설정하십시오. 이 플래그가 설정되면 사설 액세스 엔드포인트가 사용됩니다.</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>전용 하드웨어를 사용하면 작업자 노드가 사용자 계정 전용 인프라에서 호스팅됩니다. 공유 하드웨어를 사용하면 하이퍼바이저 및 물리적 하드웨어와 같은 인프라 리소스는 다른 IBM 고객과 공유되지만 각 작업자 노드는 사용자에 대해 단일 테넌트입니다. 플래그가 설정되지 않은 경우 "Shared"가 기본값입니다. "dedicated" 작업자를 사용하면 추가 비용이 발생합니다.</dd>
  <dt>--private-vlan ID</dt>
  <dd>사설 VLAN의 ID를 지정합니다. 기본적으로 사용 가능한 VLAN 세트가 사용되거나 한 쌍이 작성됩니다.</dd>
  <dt>--public-vlan ID</dt>
  <dd>공용 VLAN의 ID를 지정합니다. 기본적으로 사용 가능한 VLAN 세트가 사용되거나 한 쌍이 작성됩니다.</dd>
  <dt>--plan ID</dt>
  <dd>플랜의 ID를 지정합니다. 기본적으로 표준 플랜이 사용됩니다.</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>인라인 또는 파일로 제공된 API 특정 구성 매개변수가 포함된 유효한 JSON 오브젝트입니다. 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 https://cloud.ibm.com/apidocs/cfaas#provision-new-cfee-environment를 참조하십시오. 다중 구역 CFEE를 프로비저닝하는 데 필요합니다. 참고: 기타 모든 플래그가 무시되고 resource_group_id, access_token 및 refresh_token 필드가 CLI 명령에 의해 처리됩니다.</dd>
</dl>

<strong>예제</strong>:

`dal10`에 `test-cfee`라는 인스턴스 작성:
```
ibmcloud cfee create test-cfee dal10
```

`4`개의 셀이 있는 `dal10`에 `test-cfee`라는 `dedicated` 인스턴스 작성:
```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

대상으로 지정된 지역에 사용 가능한 데이터 센터 목록을 가져오도록 요청
```
ibmcloud cfee create-locations [--output FORMAT]
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

사용자가 CFEE 인스턴스를 작성하는 데 필요한 모든 권한을 가지고 있는지 확인하십시오. 이 명령은 대상 사용자에 대해 다음 액세스 정책을 확인합니다. CFEE 서비스에 대한 편집자, Kubernetes Service에 대한 관리자 역할, Cloud Object Storage 서비스에 대한 플랫폼 역할의 편집자 및 서비스 액세스 역할의 관리자 및 Compose for PostgreSQL 프로비저닝을 위한 현재 조직의 현재 영역에 대한 개발자 역할

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>사용자의 이름입니다.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>권한을 검사할 액세스 그룹의 이름입니다. 기본 액세스 그룹은 "cfee-provision-access-group"입니다.</dd>
   <dt>--output FORMAT</dt>
   <dd>권한 출력 형식을 지정합니다. 현재 JSON만 지원됩니다.</dd>
  </dl>
  
<strong>예제</strong>:

사용자 `name@example.com`에 대한 CFEE 작성 권한 검사:
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

사용자 `name@example.com` 및 액세스 그룹 `test-access-group`에 대한 CFEE 작성 권한 검사:
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

CFEE 인스턴스를 작성하는 데 필요한 모든 권한을 사용자에게 부여합니다. 이 명령은 대상 사용자에 대해 다음 액세스 정책을 작성합니다. CFEE 서비스에 대한 편집자 역할, Kubernetes service에 대한 관리자 역할, Cloud Object Storage 서비스에 대한 플랫폼 역할의 편집자 및 서비스 액세스 역할의 관리자 및 Compose for PostgreSQL 프로비저닝을 위한 현재 조직의 현재 영역에 대한 개발자 역할

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
  <dl>
   <dt>USER_NAME(필수)</dt>
   <dd>사용자의 이름입니다.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>권한을 부여할 액세스 그룹의 이름입니다. 기본 액세스 그룹은 "cfee-provision-access-group"입니다.</dd>
  </dl>
  
<strong>예제</strong>:

기본 액세스 그룹을 사용하여 사용자 `name@example.com`에 CFEE 작성 권한 부여:
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

액세스 그룹 `test-access-group`을 사용하여 사용자 `name@example.com`에 CFEE 작성 권한 부여:
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

CFEE 인스턴스의 프로비저닝 상태 확인:
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>NAME 또는 ID(필수)</dt>
   <dd>CFEE 인스턴스의 이름 또는 ID입니다.</dd>
   <dt>--poll</dt>
   <dd>이 호출을 반복해서 안정된 상태가 될 때까지 폴링할지 여부를 지정합니다.</dd>
   <dt>--output FORMAT</dt>
   <dd>상태 출력 형식을 지정합니다. 현재 JSON만 지원됩니다.</dd>
  </dl>

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

대상으로 지정된 CFEE 환경에서 모니터링 사용:
```
ibmcloud cfee monitoring-enable
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

대상으로 지정된 CFEE 환경에서 모니터링 사용 안함:
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

대상으로 지정된 CFEE 환경에서 최신 모니터링 사용/사용 안함 조작의 상태를 확인합니다.
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>--poll</dt>
   <dd>이 호출을 반복하고 안정된 상태가 될 때까지 폴링할지 여부를 지정합니다.</dd>
  </dl>
