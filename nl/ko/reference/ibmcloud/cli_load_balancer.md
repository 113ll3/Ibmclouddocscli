---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 로드 밸런서

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 인프라 로드 밸런서 서비스로 로드 밸런서를 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 로드 밸런서 명령">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

 ## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

기존 로드 밸런서를 취소합니다.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

작성-옵션에서 리턴된 ID가 제공된 로드 밸런서를 추가합니다.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

로드 밸런서를 작성하기 위한 가격 옵션을 가져옵니다.
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

로드 밸런서 세부사항을 가져옵니다.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

새 load_balancer 서비스를 추가합니다.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>필수. 연결의 할당된 백분율.</dd>
<dt>-p, --port</dt>
<dd>필수. 포트 번호.</dd>
<dt>-t, --routing-type</dt>
<dd>필수. 라우팅 유형의 ID. ID를 찾으려면 'ibmcloud sl loadbal routing-types'를 실행하십시오.</dd>
<dt>-m, --routing-method</dt>
<dd>필수. 라우팅 메소드의 ID. ID를 찾으려면 'ibmcloud sl loadbal routing-methods'를 실행하십시오.</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

기존 로드 밸런서 서비스 그룹을 삭제합니다.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

기존 로드 밸런서 서비스 그룹을 편집합니다.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>연결의 할당된 백분율을 변경합니다.</dd>
<dt>-p, --port</dt>
<dd>포트 번호를 변경합니다.</dd>
<dt>-t, --routing-type</dt>
<dd>라우팅 유형의 ID를 변경합니다. ID를 찾으려면 'ibmcloud sl loadbal routing-types'를 실행하십시오.</dd>
<dt>-m, --routing-method</dt>
<dd>라우팅 메소드의 ID를 변경합니다. ID를 찾으려면 'ibmcloud sl loadbal routing-methods'를 실행하십시오.</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

특정 서비스 그룹의 연결을 재설정합니다.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

상태 확인 유형을 나열합니다.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

활성 로드 밸런서를 나열합니다.
```
ibmcloud sl loadbal list
```

<strong>명령 옵션</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
<dt>-o, --order</dt>
<dd>로드 밸런서를 구매한 주문 ID별 필터링.</dd>
<dt>-p, --ip-address</dt>
<dd>IP 주소별 필터링.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

라우팅 방법을 나열합니다.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

라우팅 유형을 나열합니다.
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

새 로드 밸런서 서비스를 추가합니다.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--disabled</dt>
<dd>선택사항. 서비스를 사용 안함으로 작성합니다. 지정되지 않은 경우 기본값이 사용됩니다.</dd>
<dt>-p, --port</dt>
<dd>필수. 서비스의 포트 번호.</dd>
<dt>-w, --weight</dt>
<dd>필수. 서비스의 가중치.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>필수. 상태 검사 유형.</dd>
<dt>-i, --ip-address</dt>
<dd>필수. 서비스의 IP 주소.</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

기존 로드 밸런서 서비스를 삭제합니다.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

서비스 그룹의 특성을 편집합니다.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--disabled</dt>
<dd>서비스를 사용 안함으로 설정합니다.</dd>
<dt>--enabled</dt>
<dd>서비스를 사용으로 설정합니다.</dd>
<dt>-p, --port</dt>
<dd>서비스의 포트 번호를 변경합니다.</dd>
<dt>-w, --weight</dt>
<dd>서비스의 가중치를 변경합니다.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>상태 검사 유형을 변경합니다.</dd>
<dt>-i, --ip-address</dt>
<dd>서비스의 IP 주소를 변경합니다.</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

기존 로드 밸런서 서비스의 상태를 토글합니다.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>
