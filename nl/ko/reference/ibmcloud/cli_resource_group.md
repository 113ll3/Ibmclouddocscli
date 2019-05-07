---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-22"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 리소스 및 리소스 그룹에 대한 작업
{: #ibmcloud_commands_resource}

리소스 그룹은 사용자 정의할 수 있는 그룹화에서 계정 리소스를 구성하기 위한 방법입니다. 다음 명령을 사용하여 리소스 그룹의 {{site.data.keyword.cloud}} 리소스를 관리하십시오.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

리소스 그룹을 나열합니다.
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--default</dt>
  <dd>현재 계정의 기본 그룹을 가져옵니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

현재 대상 계정의 모든 리소스 그룹을 나열합니다.
```
ibmcloud resource groups
```
{: codeblock}

현재 대상으로 지정된 계정의 기본 그룹 나열:
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

리소스 그룹의 세부사항을 표시합니다.
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>리소스 그룹의 이름</dd>
  <dt>--id</dt>
  <dd>ID만 표시</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

리소스 그룹 `example-group` 표시:
```
ibmcloud resource group example-group
```
{: codeblock}

리소스 그룹 `example-group`의 ID만 표시:
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

리소스 그룹을 작성합니다.
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>리소스 그룹의 이름</dd>
</dl>

<strong>예제</strong>:

리소스 그룹 `example-group` 작성:
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

기존 리소스 그룹을 업데이트합니다.
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
  <dd>확인 없이 업데이트 강제 실행</dd>
</dl>

<strong>예제</strong>:

리소스 그룹 이름 `example-group`을 `trial-group`으로 바꾸기:
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

리소스 그룹 `example-group`의 할당량을 `free`로 변경:
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

모든 할당량 정의를 나열합니다.
```
ibmcloud resource quotas
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

모든 할당량 정의 나열:
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

할당량 정의의 세부사항을 표시합니다.
```
ibmcloud resource quota NAME
```
{: codeblock}

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
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloud foundry 서비스 인스턴스를 리소스 그룹으로 마이그레이션합니다.
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME 또는 SERVICE_INSTANCE_ID(필수)</dt>
  <dd>서비스 인스턴스의 이름 또는 ID</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--resource-group-id'와 배타적입니다. 이들이 지정되지 않은 경우에는 현재 대상 지정된 리소스 그룹으로 기본 설정됩니다.</dd>
  <dt>--resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--resource-group-name'과 배타적입니다. 이들이 지정되지 않은 경우에는 현재 대상 지정된 리소스 그룹으로 기본 설정됩니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 마이그레이션</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

서비스 인스턴스를 나열합니다.
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>소속된 서비스의 이름</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>위치별 필터링</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>인스턴스 유형. 지정하지 않으면 `service_instance` 유형이 사용됩니다. 모든 인스턴스 유형을 나열하려면 all을 사용하십시오.</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--long</dt>
  <dd>출력에 추가 필드 표시</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. </dd>
</dl>

<strong>예제</strong>:

서비스 `test-service`의 서비스 인스턴스 나열:
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

서비스 인스턴스의 세부사항을 표시합니다.

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
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
  <dt>--output</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`의 세부사항 표시:
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

서비스 인스턴스를 작성합니다.
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 인스턴스의 이름</dd>
  <dt>SERVICE_NAME 또는 SERVICE_ID(필수)</dt>
  <dd>서비스의 이름 또는 ID입니다. 서비스 오퍼링을 나열하려면 `ibmcloud catalog service-marketplace` [명령](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace)을 사용하십시오.</dd>
  <dt>SERVICE_PLAN_NAME 또는 SERVICE_PLAN_ID(필수)</dt>
  <dd>서비스 플랜의 이름 또는 ID</dd>
  <dt>LOCATION(필수)</dt>
  <dd>서비스 인스턴스를 작성하는 대상 위치 또는 환경</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>배치의 이름</dd>
  <dt>-p, --parameters <i>@JSONFILE or JSON_STRING</i></dt>
  <dd>서비스 인스턴스를 작성하기 위한 매개변수의 JOSN 문자열 또는 JSON 파일</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>서비스 엔드포인트의 유형</dd>
</dl>

<strong>예제</strong>:

위치 `eu-gb`에 있는 서비스 `test-service`의 서비스 플랜 `test-service-plan`을 사용하여 서비스 인스턴스 `my-service-instance` 작성:
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

서비스 인스턴스를 업데이트합니다.
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>이름(필수)</dt>
  <dd>서비스 인스턴스의 이름(ID와 배타적)</dd>
  <dt>ID(필수)</dt>
  <dd>서비스 인스턴스의 ID(NAME과 배타적)</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>새 서비스 인스턴스 이름</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>새 서비스 플랜 ID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>서비스 인스턴스를 작성하기 위한 매개변수의 JOSN 문자열 또는 JSON 파일</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>서비스 엔드포인트의 유형</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트 강제 실행</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance` 업데이트, 해당 이름을 `new-service-instance`로 변경:
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

서비스 인스턴스를 삭제합니다.
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
  <dd>확인 없이 삭제 강제 실행</dd>
  <dt>--recursive</dt>
  <dd>소속된 모든 리소스 삭제</dd>
</dl>

<strong>예제</strong>:

리소스 서비스 인스턴스 `my-service-instance` 삭제:
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

서비스 별명에 대한 바인딩을 표시합니다.
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ALIAS(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

서비스 별명 `my-service-alias`에 대한 리소스 바인딩 표시:
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

서비스 바인딩의 세부사항을 표시합니다.
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 애플리케이션 이름</dd>
  <dt>--id</dt>
  <dd>ID만 표시합니다. 서비스 바인딩의 기타 모든 출력은 표시되지 않습니다. 이 옵션은 '--output'과 배타적입니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩의 세부사항 표시:
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

서비스 바인딩을 작성합니다.
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME(필수)</dt>
  <dd>서비스 별명 이름</dd>
  <dt>APP_NAME(필수)</dt>
  <dd>CloudFoundry 애플리케이션 이름</dd>
  <dt>ROLE_NAME(필수)</dt>
  <dd>사용자 역할의 이름</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>역할이 속한 서비스 ID의 UUID 또는 이름</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>서비스 엔드포인트의 유형</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 작성 강제 실행</dd>
</dl>

<strong>예제</strong>:

`Administrator` 역할로 서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩 작성:
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

서비스 바인딩을 삭제합니다.
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
  <dd>확인 없이 삭제 강제 실행</dd>
</dl>

<strong>예제</strong>:
서비스 별명 `my-service-alias` 및 앱 `my-app` 간의 서비스 바인딩 삭제:
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

서비스 별명 또는 서비스 인스턴스의 서비스 키를 나열합니다.
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
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
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`의 서비스 키 나열:
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

임의 수의 서비스 키에 관한 세부사항을 표시합니다. 여기서 서비스 키 이름의 처음 *n*개의 문자는 제공된 KEY_NAME과 일치합니다.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME</dt>
  <dd>키의 이름</dd>
  <dt>ID</dt>
  <dd>키의 ID</dd>
  <dt>-g</dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--id</dt>
  <dd>서비스 키의 ID를 표시합니다. 이 옵션은 '--output'과 배타적입니다.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

서비스 키 `my-service-key`의 세부사항 표시:
```
ibmcloud resource service-key my-service-key
```
<strong>예</strong>:
ID가 `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79`인 서비스 키의 세부사항 표시:

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

서비스 키를 작성합니다.
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>키의 이름</dd>
  <dt>ROLE_NAME(필수)</dt>
  <dd>사용자 역할의 이름</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>서비스 인스턴스 ID</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>서비스 인스턴스 이름</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>서비스 별명 ID</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>서비스 별명 이름</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>역할이 속한 서비스 ID의 UUID 또는 이름</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>리소스 그룹 이름</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>서비스 엔드포인트의 유형</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 작성 강제 실행</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`에 대해 `Administrator` 역할로 `my-service-key`로 이름 지정된 서비스 키 작성:
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

서비스 키를 업데이트합니다.
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>키의 이름 또는 ID</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>키의 새 이름</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>키가 속한 리소스 그룹의 ID</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트 강제 실행</dd>
</dl>

<strong>예제</strong>:

`my-service-key`라는 서비스 키를 업데이트하고 새로운 이름 `my-service-key-2`를 지정합니다.
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

서비스 키를 삭제합니다.
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>키의 이름 또는 키의 ID</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제 강제 실행</dd>
</dl>

<strong>예제</strong>:

서비스 키 `my-service-key` 삭제:
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

서비스 인스턴스의 별명을 나열합니다.
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>소속된 서비스 인스턴스의 ID.</dd>
  <dt>--instance-name</dt>
  <dd>소속된 서비스 인스턴스의 이름.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`의 서비스 별명 나열:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

서비스 별명의 세부사항을 표시합니다.
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>--id</dt>
  <dd>제공된 서비스 별명의 ID만 표시합니다. 별명에 대한 다른 모든 출력은 표시되지 않습니다. 이 옵션은 '--output'과 배타적입니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>--output value  출력 형식을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

서비스 별명 `my-service-alias`의 세부사항 표시:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

서비스 인스턴스의 별명을 작성합니다.
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>--instance-id</dt>
  <dd>소속된 서비스 인스턴스의 ID.</dd>
  <dt>--instance-name</dt>
  <dd>소속된 서비스 인스턴스의 이름.</dd>
  <dt>-s</dt>
  <dd>별명이 작성되는 영역의 이름. 기본값은 현재 영역입니다.</dd>
  <dt>-t, --tags</dt>
  <dd>태그 목록</dd>
  <dt>-p, --parameters</dt>
  <dd>매개변수 JSON 파일 또는 JSON 문자열</dd>
</dl>

<strong>예제</strong>:

서비스 인스턴스 `my-service-instance`의 `my-service-alias`로 이름 지정된 서비스 별명 작성:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

서비스 별명을 업데이트합니다.
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
  <dd>사용자 확인 없이 업데이트 강제 실행</dd>
</dl>

<strong>예제</strong>:

서비스 별명 `my-service-alias` 업데이트, 해당 이름을 `new-service-alias`로 변경:
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

서비스 별명을 삭제합니다.
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>ALIAS_NAME(필수)</dt>
  <dd>서비스 별명의 이름</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제 강제 실행</dd>
</dl>

<strong>예제</strong>:

서비스 별명 `my-service-alias` 삭제:
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

Lucene 조회 구문을 사용하여 리소스를 검색합니다.
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>시작 리소스 위치 번호</dd>
  <dt>-l, -limit</dt>
  <dd>리턴할 리소스의 수(최대 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>정렬 기준 특성. 허용되는 입력은 `name`, `family`, `region`, `type`, `crn`입니다.</dd>
  <dt>-p, --provider</dt>
  <dd>클래식 인프라 리소스 표시, 유일하게 허용된 값: classic-infrastructure</dd>
</dl>

<strong>검색 가능한 속성</strong>:
다음 속성을 검색할 수 있습니다.

<dl>
  <dt>이름</dt>
  <dd>리소스의 사용자 정의 이름입니다.</dd>
  <dt>지역(region)</dt>
  <dd>리소스가 프로비저닝된 지리적 위치입니다. 예: us-south, us-east, au-syd, eu-gb, eu-de 및 jp-tok.</dd>
  <dt>service_name</dt>
  <dd>'ibmcloud catalog service-marketplace' 출력의 이름 열에 표시되는 서비스의 이름입니다.</dd>
  <dt>family</dt>
  <dd>리소스가 속한 클라우드 컴포넌트입니다. 허용되는 값은 cloud_foundry, containers, resource_controller, vmware 또는 ims입니다.</dd>
  <dt>organization_id</dt>
  <dd>Cloud Foundry 조직 GUID입니다.</dd>
  <dt>doc.space_id</dt>
  <dd>Cloud Foundry 영역 GUID입니다.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>리소스 그룹의 ID입니다.</dd>
  <dt>type</dt>
  <dd>리소스 유형입니다. 허용되는 값은 k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup입니다.</dd>
  <dt>creation_date</dt>
  <dd>리소스가 작성된 날짜입니다.</dd>
  <dt>modification_date</dt>
  <dd>마지막으로 리소스가 수정된 날짜입니다. yyyy-mm-ddThh:mm:ssZ 형식입니다. </dd>
  <dt>_objectType</dt>
  <dd>클래식 인프라 리소스의 유형입니다. 허용되는 값은 SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall 및 SoftLayer_Virtual_Guest입니다. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>리소스에 연결되는 태그입니다. 클래식 인프라 리소스에 연결되는 태그를 검색하는 경우에는 tagReferences.tag.name을 사용하십시오. </dd> 
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
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

지정된 태그가 있는 리소스 검색:
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

지정된 ID를 사용하여 클래식 인프라 가상 게스트 리소스 검색(-p classic-infrastructure만 해당됨):
```
ibmcloud resource search 'id:12345678 _objectType:SoftLayer_Virtual_Guest'
```
{: codeblock}

지정된 태그 이름을 사용하여 클래식 인프라 하드웨어 리소스 검색(-p classic-infrastructure만 해당됨):
```
ibmcloud resource search 'tagReferences.tag.name:name _objectType:SoftLayer_Hardware'
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

청구 계정의 모든 태그를 나열합니다.

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>시작 태그 위치 번호</dd>
  <dt>-l, -limit</dt>
  <dd>리턴할 태그 수(최대 1000, 기본 100)</dd>
  <dt>-p; --provider</dt> 
  <dd>클래식 인프라 태그를 검색할 때 classic-infrastructure를 지정합니다.</dd>
  <dt>-d, --details</dt>
  <dd>태그가 지정된 리소스의 수를 표시합니다.</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

하나 이상의 태그를 리소스에 연결합니다.
```
ibmcloud resource tag-attach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```
<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-names(필수)</dt>
  <dd>쉼표로 구분된 태그 이름 목록</dd>
  <dt>--resource-id</dt>
  <dd>태그를 연결해야 하는 리소스의 CRN이며 클래식 인프라 리소스의 경우 리소스의 ID입니다. 'ibmcloud resource search' 명령을 사용하여 리소스 ID 또는 CRN을 얻을 수 있습니다.</dd>
  <dt>--resource-type</dt>
  <dd>태그를 연결해야 하는 클래식 인프라 리소스의 리소스 유형이며 클래식 인프라 리소스에 태그를 연결하는 경우, 이 매개변수는 필수입니다. --resource-type에 대해 가능한 값은 SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall 및 SoftLayer_Virtual_Guest입니다. </dd>
</dl>

<strong>예제</strong>:

* `MyTag` 태그를 `MyCluster`라는 Kubernetes 클러스터에 연결하려면 먼저 태그 지정하려는 클러스터의 CRN을 찾으십시오.
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  다음 예제와 유사한 문자열인 CRN을 적어 두십시오. 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  태그를 연결하려면 다음 명령을 실행하십시오.
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* `MyTag` 태그를 `MyVM`이라는 클래식 인프라 가상 게스트에 연결하려면 먼저 태그 지정하려는 가상 게스트의 ID를 찾으십시오.
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  `48373549`와 유사한 문자열인 ID을 적어 두십시오.

  태그를 연결하려면 다음 명령을 실행하십시오.
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

하나 이상의 태그를 리소스에서 분리합니다.
```
ibmcloud resource tag-detach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-names(필수)</dt>
  <dd>쉼표로 구분된 태그 이름 목록</dd>
  <dt>--resource-id</dt>
  <dd>태그를 분리해야 하는 리소스의 CRN이며 클래식 인프라 리소스의 경우 리소스의 ID입니다. 'ibmcloud resource search' 명령을 사용하여 리소스 ID 또는 CRN을 얻을 수 있습니다.</dd>
  <dt>--resource-type</dt>
  <dd>태그를 분리해야 하는 클래식 인프라 리소스의 리소스 유형이며 클래식 인프라 리소스에 태그를 연결하는 경우, 이 매개변수는 필수입니다. --resource-type에 대해 가능한 값은 SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall 및 SoftLayer_Virtual_Guest입니다. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

태그를 삭제합니다.
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--tag-name(필수)</dt>
  <dd>삭제할 태그의 이름입니다.</dd>
  <dt>-p; --provider</dt> 
  <dd>클래식 인프라 태그를 삭제할 때 classic-infrastructure를 지정합니다.</dd>
</dl>

태그는 어떠한 리소스에도 연결되지 않은 경우에만 삭제할 수 있습니다.
