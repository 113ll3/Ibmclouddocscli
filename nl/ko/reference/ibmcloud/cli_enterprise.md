---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 엔터프라이즈, 계정 그룹 및 계정 관리
{: #ibmcloud_enterprise}

다음 명령을 사용하여 엔터프라이즈, 계정 그룹 및 계정을 관리할 수 있습니다.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

엔터프라이즈를 작성합니다.
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>NAME(필수)</dt>
<dd>엔터프라이즈 이름입니다.</dd>
<dt>-d, --domain DOMAIN_NAME(선택사항)</dt>
<dd>도메인 이름입니다.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID(선택사항)</dt>
<dd>엔터프라이즈의 기본 연락처 사용자 ID입니다.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

엔터프라이즈 정보를 업데이트합니다.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>-f, --force(선택사항)</dt>
<dd>확인 없이 업데이트합니다.</dd>
<dt>-n, --name NEW_NAME(필수)</dt>
<dd>엔터프라이즈의 새 이름입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

엔터프라이즈의 세부사항을 표시합니다.
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

계정 그룹을 작성합니다.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>NAME(필수)</dt>
<dd>계정 그룹 이름입니다.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME(선택사항)</dt>
<dd>상위 계정 그룹의 이름입니다. 이를 생략하면 상위는 현재 엔터프라이즈입니다.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID(선택사항)</dt>
<dd>계정 그룹의 기본 연락처 사용자 ID입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

계정 그룹을 업데이트합니다.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--id ID(필수)</dt>
<dd>대상 계정 그룹의 ID입니다. 이 옵션은 `-n, --name`과 배타적입니다.</dd>
<dt>-n, --name NAME(필수)</dt>
<dd>대상 계정 그룹의 이름입니다. 이 옵션은 `--id`와 배타적입니다.</dd>
<dt>--new-name NEW_NAME(필수)</dt>
<dd>대상 계정 그룹의 새 이름입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

계정 그룹의 세부사항을 표시합니다.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--id ID(필수)</dt>
<dd>계정 그룹의 ID입니다. 이 옵션은 `-n, --name`과 배타적입니다.</dd>
<dt>-n, --name NAME(필수)</dt>
<dd>계정 그룹의 이름입니다. 이 옵션은 `--id`와 배타적입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

계정 그룹을 나열합니다.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME(선택사항)</dt>
<dd>상위 계정 그룹의 이름입니다. 이 옵션은 `--parent-account-group-id`와 배타적입니다.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID(선택사항)</dt>
<dd>상위 계정 그룹의 ID입니다. 이 옵션은 `--parent-account-group`과 배타적입니다.</dd>
<dt>--recursive(선택사항)</dt>
<dd>하위 계정 그룹을 표시합니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

계정을 작성합니다.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>NAME(필수)</dt>
<dd>계정 그룹 이름입니다.</dd>
<dt>--owner USER_ID(선택사항)</dt>
<dd>계정 그룹의 사용자 ID입니다.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME(선택사항)</dt>
<dd>상위 계정 그룹의 이름입니다. 이를 생략하면 상위는 현재 엔터프라이즈입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

다른 상위 아래로 계정을 이동합니다.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--id ID(필수)</dt>
<dd>대상 계정의 ID입니다. 이 옵션은 `-n, --name`과 배타적입니다.</dd>
<dt>-n, --name NAME(필수)</dt>
<dd>대상 계정의 이름입니다. 이 옵션은 `--id`와 배타적입니다.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME(필수)</dt>
<dd>상위 계정 그룹의 이름입니다. 이 옵션은 `--parent-account-group-id` 및 `--parent-enterprise`와 배타적입니다.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID(필수)</dt>
<dd>상위 계정 그룹의 ID입니다. 이 옵션은 `--parent-account-group` 및 `--parent-enterprise`와 배타적입니다.</dd>
<dt>--parent-enterprise(필수)</dt>
<dd>엔터프라이즈를 상위로 설정합니다. 이 옵션은 `--parent-account-group` 및 `--parent-account-group-id`와 배타적입니다.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

계정의 세부사항을 표시합니다.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--id ID(필수)</dt>
<dd>계정의 ID입니다. 이 옵션은 `-n, --name`과 배타적입니다.</dd>
<dt>-n, --name NAME(필수)</dt>
<dd>계정의 이름입니다. 이 옵션은 `--id`와 배타적입니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

계정을 나열합니다.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME(선택사항)</dt>
<dd>상위 계정 그룹의 이름입니다. 이 옵션은 `--parent-account-group-id`와 배타적입니다.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID(선택사항)</dt>
<dd>상위 계정 그룹의 ID입니다. 이 옵션은 `--parent-account-group`과 배타적입니다.</dd>
<dt>--recursive(선택사항)</dt>
<dd>하위 계정을 표시합니다.</dd>
<dt>--output FORMAT(선택사항)</dt>
<dd>출력 형식을 지정합니다. 'JSON'만 지원됩니다.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

독립형 계정을 가져옵니다.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
<dt>--account-id</dt>
<dd>소스 계정의 ID입니다.</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP(선택사항)</dt>
<dd>상위 계정 그룹의 이름입니다. 이 옵션은 `--parent-account-group-id`와 배타적입니다.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID(선택사항)</dt>
<dd>상위 계정 그룹의 ID입니다. 이 옵션은 `--parent-account-group`과 배타적입니다.</dd>
</dl>
