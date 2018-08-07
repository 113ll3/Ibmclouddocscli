---

copyright:

  years: 2018


lastupdated: "2018-07-26"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 리소스 그룹 및 리소스 관리를 위한 명령
{: #ibmcloud_commands_resource}

<table summary="리소스 그룹 및 리소스를 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
  <caption>표 1. 리소스 그룹 및 리소스 관리를 위한 명령</caption>
  <thead>
    <th colspan="5">리소스 그룹 및 리소스 관리를 위한 명령</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags 
](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

### ibmcloud resource groups
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

### ibmcloud resource group
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

### ibmcloud resource group-create
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

### ibmcloud resource group-update
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

### ibmcloud resource quotas
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

### ibmcloud resource quota
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

### ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloudfoundry 서비스 인스턴스를 리소스 그룹으로 마이그레이션

```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
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

### ibmcloud resource service-instances
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

### ibmcloud resource service-instance
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

### ibmcloud resource service-instance-create
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

### ibmcloud resource service-instance-delete
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

### ibmcloud resource service-bindings
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

### ibmcloud resource service-binding
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

### ibmcloud resource service-binding-create
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

### ibmcloud resource service-binding-delete
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

### ibmcloud resource service-keys
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

### ibmcloud resource service-key
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

### ibmcloud resource service-key-create
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

### ibmcloud resource service-aliases
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

### ibmcloud resource service-alias
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

### ibmcloud resource service-alias-create
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

### ibmcloud resource service-alias-update
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

### ibmcloud resource service-alias-delete
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

### ibmcloud resource search
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

### ibmcloud resource tags
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

### ibmcloud resource tag
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

### ibmcloud resource tag-create
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

### ibmcloud resource tag-delete
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

### ibmcloud resource tag-attach
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

### ibmcloud resource tag-detach
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

### ibmcloud resource tag-update
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
