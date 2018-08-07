---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} 인프라 서브넷 관리를 위한 명령

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 {{site.data.keyword.Bluemix_notm}} 인프라 명령">
<caption>표 1. {{site.data.keyword.Bluemix_notm}} 인프라 서브넷 명령</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 인프라 서브넷 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ### ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

서브넷을 취소합니다.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl subnet cancel 12345678 -f
```
이 명령은 확인 요청 없이 ID가 12345678인 서브넷을 취소합니다.

### ibmcloud sl subnet create
{: #sl_subnet_create}

계정에 새 서브넷을 추가합니다.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>IPv6 주소 주문.</dd>
<dt>--test</dt>
<dd>서브넷을 주문하지 않음. 견적서만 가져오기.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl subnet create public 16 567
```
이 명령은 16개의 IP v4 주소를 사용하여 공인 서브넷을 작성하고 ID 567인 VLAN에 배치합니다.

### ibmcloud sl subnet detail
{: #sl_subnet_detail}

서브넷의 세부사항을 가져옵니다.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
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
ibmcloud sl subnet detail 12345678
```
이 명령은 가상 서버 및 하드웨어 서버 정보를 포함하여 ID가 12345678인 서브넷에 대한 자세한 정보를 표시합니다.

### ibmcloud sl subnet list
{: #sl_subnet_list}

계정의 모든 서브넷을 나열합니다.
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열. 옵션: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
<dt>--identifier</dt>
<dd>네트워크 ID별 필터링.</dd>
<dt>-t, --subnet-type</dt>
<dd>서브넷 유형별 필터링.</dd>
<dt>--network-space</dt>
<dd>네트워크 영역별 필터링.</dd>
<dt>--v4, --ipv4</dt>
<dd>IPv4 서브넷만 표시.</dd>
<dt>--v6, --ipv6</dt>
<dd>IPv6 서브넷만 표시.</dd>
<dt>--order</dt>
<dd>서브넷을 구매한 주문 ID별 필터링.</dd>
</dl>

**예제**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
이 명령은 현재 계정의 IP V4 서브넷을 나열합니다. 데이터 센터 기준 필터링은 dal09이고, 서브넷 유형은 PRIMARY이며 네트워크 영역은 PUBLIC입니다.

### ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

IP 주소를 찾고 해당 서브넷 및 디바이스 정보를 표시합니다.
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**예제**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
이 명령은 주소가 9.125.235.255인 IP 주소 레코드를 찾고 해당 서브넷과 디바이스 정보를 표시합니다.
