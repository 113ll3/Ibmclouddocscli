---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 카탈로그 오퍼링 검색 및 관리
{: #ibmcloud_catalog}

다음 명령을 사용하여 {{site.data.keyword.cloud}} 카탈로그 항목, 조회 템플리트, 데이터 센터의 지리적 위치 및 런타임을 관리하십시오.
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

카탈로그 항목 검색:
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>검색할 범위의 지리적 지역 지정. 현재 "us-south" 및 "united-kingdom"만 지원됨</dd>
  <dt>-k, --kind</dt>
  <dd>리소스 종류별 필터링. 현재 "service-cf", "iaas", "runtime", "template" 및 "dashboard"만 지원됨</dd>
  <dt>-p, --price</dt>
  <dd>가격별 필터링. 현재 "free", "paygo", "ibmcloud-subscription"만 지원됨</dd>
  <dt>-t, --tag</dt>
  <dd>태그별 필터링.</dd>
  <dt>--sort-by</dt>
  <dd>정렬 기준 특성</dd>
  <dt>--col</dt>
  <dd>테이블의 추가 컬럼을 지정합니다. 현재는 "group", "provider" 및 "tags"입니다.</dd>
  <dt>--reverse</dt>
  <dd>정렬 순서를 반대로 할지 여부</dd>
  <dt>--output TYPE(선택사항)</dt>
  <dd>--output value  출력 유형을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
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
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--children</dt>
  <dd>카탈로그 항목의 모든 하위 가져오기</dd>
  <dt>--output TYPE(선택사항)</dt>
  <dd>--output value  출력 유형을 지정합니다. 이제 JSON만 지원됩니다.</dd>
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

새 카탈로그 항목 작성(계정의 카탈로그 관리자만):
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>오브젝트의 상위 ID</dd>
  <dt>-c</dt>
  <dd>인라인 또는 파일로 제공되는 카탈로그 특정 구성 매개변수를 포함하는 올바른 JSON 오브젝트입니다. 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
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

기존 카탈로그 항목 업데이트(카탈로그 관리자 또는 계정의 편집자 전용):
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-c</dt>
  <dd>인라인 또는 파일로 제공되는 카탈로그 특정 구성 매개변수를 포함하는 올바른 JSON 오브젝트입니다. 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
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
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-json</dt>
  <dd>원래 JSON 응답 출력</dd>
  <dt>--output TYPE(선택사항)</dt>
  <dd>--output value  출력 유형을 지정합니다. 이제 JSON만 지원됩니다.</dd>
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

기존 카탈로그 항목의 가시성 업데이트(계정의 카탈로그 관리자만):
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 포함 목록에 추가하고 항목에 대한 가시성을 부여합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--includes-remove</dt>
  <dd>포함 목록에서 계정(또는 쉼표로 구분된 계정)을 제거하여 항목에 대한 가시성을 제거합니다. 이메일 또는 계정 GUID 허용</dd>  
  <dt>--excludes-add</dt>
  <dd>계정(또는 쉼표로 구분된 계정의 목록)을 제외 목록에 추가합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--excludes-remove</dt>
  <dd>제외 목록에서 계정(또는 쉼표로 구분된 계정)을 제거하여 항목에 대한 가시성을 제거합니다. 글로벌 관리자가 계정을 설정한 경우, 계정 관리자는 계정을 제거할 수 없습니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--owner</dt>
  <dd>오브젝트의 소유자를 변경합니다. 이메일 또는 계정 GUID 허용</dd>
  <dt>--restrict</dt>
  <dd>가시성 오브젝트의 제한을 '개인용'으로 변경</dd>
  <dt>--unrestrict</dt>
  <dd>가시성 오브젝트의 제한을 '공용'으로 변경</dd>  
  <dt>-c</dt>
  <dd>인라인 또는 파일로 제공되는 카탈로그 특정 구성 매개변수를 포함하는 올바른 JSON 오브젝트입니다. 지원되는 구성 매개변수의 목록은 특정 카탈로그 항목에 대한 문서를 참조하십시오.</dd>
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

마켓플레이스의 서비스 오퍼링 나열:
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

{{site.data.keyword.cloud_notm}}에서 표준 유형 템플리트를 확인합니다.
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
   <dd>애플리케이션이 작성될 때 기반으로 하는 템플리트입니다. 모든 템플리트의 ID를 보려면 <i>ibmcloud templates</i>를 사용하십시오.</dd>
   <dt>CF_APP_NAME(필수)</dt>
   <dd>작성되는 cf 애플리케이션의 이름입니다.</dd>
   <dt>-u <i>URL</i>(선택사항)</dt>
   <dd>애플리케이션의 라우트입니다. 지정되지 않은 경우, 앱 이름과 기본 도메인을 기반으로 {{site.data.keyword.Bluemix_notm}}에 의해 자동으로 라우트가 설정됩니다.</dd>
   <dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
   <dd>애플리케이션에 대한 설명입니다.</dd>
   <dt>--no-start(선택사항)</dt>
   <dd>애플리케이션이 작성된 후에 자동으로 시작되지 않습니다. 지정하지 않으면 애플리케이션이 작성된 후 자동으로 시작됩니다.</dd>
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
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>명령 옵션</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>id에 의해 지역을 지정합니다.</dd>
  <dt>-k, --kind</dt>
  <dd>지정된 유형에 대한 항목의 목록을 가져옵니다.</dd>
  <dt>--col</dt>
  <dd>테이블의 추가 컬럼을 지정합니다. 현재는 "group", "provider" 및 "tags"입니다.</dd>
  <dt>--output TYPE(선택사항)</dt>
  <dd>--output value  출력 유형을 지정합니다. 이제 JSON만 지원됩니다. 이 옵션은 '--id'와 배타적입니다.</dd>
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
