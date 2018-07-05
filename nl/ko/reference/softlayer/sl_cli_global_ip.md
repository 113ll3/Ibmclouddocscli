---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 글로벌 IP CLI 명령

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 {{site.data.keyword.BluSoftlayer_notm}} 인프라 명령">
<caption>표 1. {{site.data.keyword.BluSoftlayer_notm}} 인프라 글로벌 IP 명령</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 인프라 글로벌 IP 명령</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl globalip assign
{: #sl_globalip_assign}

대상 라우터 또는 디바이스에 글로벌 IP를 지정합니다.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**예제**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
이 명령은 ID가 12345678인 IP 주소를 IP 주소가 9.111.123.456인 대상 디바이스에 지정합니다.

### ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

글로벌 IP를 취소합니다.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl globalip cancel 12345678
```
이 명령은 ID가 12345678인 IP 주소를 취소합니다.
 
 ### ibmcloud sl globalip create
{: #sl_globalip_create}

글로벌 IP를 작성합니다.
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--v6</dt>
<dd>IPv6 IP 주소 주문.</dd>
<dt>--test</dt>
<dd>테스트 주문.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl globalip create --v6
```
이 명령은 IP V6 주소를 작성합니다.

### ibmcloud sl globalip list
{: #sl_globalip_list}

계정의 모든 글로벌 IP를 나열합니다.
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--v4</dt>
<dd>IPv4만 표시.</dd>
<dt>--v6</dt>
<dd>IPv6만 표시.</dd>
<dt>--order</dt>
<dd>이 IP 주소를 구매한 주문의 ID별 필터링.</dd>
</dl>

**예제**:
```
ibmcloud sl globalip list --v4
```
이 명령은 현재 계정의 모든 IP V4 주소를 나열합니다.

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

대상 라우터 또는 디바이스에서 글로벌 IP를 지정 해제합니다.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**예제**:
```
ibmcloud sl globalip unassign 12345678
```
이 명령은 대상 디바이스에서 ID가 12345678인 IP 주소의 지정을 해제합니다.
