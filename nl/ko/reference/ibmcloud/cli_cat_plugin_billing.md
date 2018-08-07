---

copyright:

  years: 2018


lastupdated: "2018-07-26"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 카탈로그, 플러그인 및 청구 설정 관리를 위한 명령
{: #ibmcloud_commands_settings}

<table summary="{{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 비용 청구 및 보안 설정을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 1. {{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 청구 및 보안 설정 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 카탈로그, 플러그인, 청구 및 보안 설정의 관리를 위한 명령</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list
](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update
](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ### ibmcloud catalog search
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

### ibmcloud catalog entry
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

### ibmcloud catalog entry-create
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

### ibmcloud catalog entry-update
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

### ibmcloud catalog entry-delete
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

### ibmcloud catalog entry-visibility
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

### ibmcloud catalog entry-visibility-set
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

### ibmcloud catalog service-marketplace
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

### ibmcloud catalog templates
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

### ibmcloud catalog template
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

### ibmcloud catalog template-run
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

### ibmcloud catalog locations
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

### ibmcloud catalog runtime
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

### ibmcloud catalog runtimes
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

### ibmcloud billing account-usage
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

### ibmcloud billing org-usage
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

### ibmcloud billing resource-group-usage
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

### ibmcloud billing resource-instances-usage
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

### ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.Bluemix_notm}} CLI에 등록된 모든 플러그인 저장소를 나열합니다.

```
ibmcloud plugin repos
```

<strong>전제조건</strong>: 없음

### ibmcloud plugin repo-add
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

### ibmcloud plugin repo-remove
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

### ibmcloud plugin repo-plugins
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

### ibmcloud plugin repo-plugin
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

### ibmcloud plugin list
{: #ibmcloud_plugin_list}

{{site.data.keyword.Bluemix_notm}} CLI의 설치된 모든 플러그인을 나열합니다.

```
ibmcloud plugin list
```

<strong>전제조건</strong>: 없음

### ibmcloud plugin show
{: #ibmcloud_plugin_show}

설치된 플러그인의 세부사항을 표시합니다.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>전제조건</strong>: 없음

### ibmcloud plugin install
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

### ibmcloud plugin update
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

### ibmcloud plugin uninstall
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
