---

copyright:

  years: 2018


lastupdated: "2018-09-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# VLAN

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 인프라 VLAN을 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 인프라 VLAN 명령">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options
](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl vlan create
{: #sl_vlan_create}

새 VLAN을 작성합니다.
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>VLAN의 유형(공용 또는 사설).</dd>
<dt>-r, --router</dt>
<dd>라우터의 호스트 이름.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터의 짧은 이름.</dd>
<dt>-n, --name</dt>
<dd>VLAN의 이름.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
이 명령은 16개의 IP 주소와 함께 데이터 센터 dal09에 위치하고 이름이 myvlan인 공용 VLAN을 작성합니다.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

VLAN을 취소합니다.
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vlan cancel 12345678 -f
```
이 명령은 확인 요청 없이 ID가 12345678인 VLAN을 취소합니다.

## ibmcloud sl vlan detail
{: #sl_vlan_detail}

VLAN에 대한 세부사항을 가져옵니다.
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--no-vs</dt>
<dd>가상 서버 목록 숨기기.</dd>
<dt>--no-hardware</dt>
<dd>하드웨어 목록 숨기기.</dd>
</dl>

**예제**:
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
이 명령은 ID가 12345678인 VLAN의 세부사항을 표시하며 가상 서버 또는 하드웨어 서버는 나열하지 않습니다.

## ibmcloud sl vlan edit
{: #sl_vlan_edit}

VLAN에 대한 세부사항을 편집합니다.
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-n, --name</dt>
<dd>VLAN의 이름.</dd>
</dl>

**예제**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
이 명령은 ID가 12345678인 VLAN을 업데이트하고 새 이름으로 "myvlan-rename"을 지정합니다.

## ibmcloud sl vlan list
{: #sl_vlan_list}

계정의 모든 VLAN을 나열합니다.
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
<dt>-n, --number</dt>
<dd>VLAN 번호별 필터링.</dd>
<dt>--name</dt>
<dd>VLAN 이름별 필터링.</dd>
<dt>--order</dt>
<dd>VLAN을 구매한 주문 ID별 필터링.</dd>
</dl>

**예제**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
이 명령은 현재 계정의 모든 VLAN을 나열합니다. 데이터 센터 기준 필터링은 dal09와 동일하고 VLAN 번호별로 정렬합니다.

## ibmcloud sl vlan options
{: #sl_vlan_options}

VLAN 작성을 위한 모든 옵션을 나열합니다.
```
ibmcloud sl vlan options
```


**예제**:
```
ibmcloud sl vlan options
```
이 명령은 VLAN 작성을 위한 모든 옵션(예: VLAN 유형, 데이터 센터, 서브넷 크기, 라우터 등)을 나열합니다.
