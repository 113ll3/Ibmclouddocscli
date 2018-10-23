---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# DNS

{{site.data.keyword.Bluemix}} Domain Name Service(DNS)는 고객에게 기본 DNS 관리 인터페이스를 통해 고객의 도메인을 보고 관리할 수 있는 중심 위치를 제공하며, 동일한 위치에서 무료로 역방향 및 보조 DNS를 관리할 수 있는 옵션도 사용자에게 제공합니다. 

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 인프라 DNS 서비스를 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 인프라 DNS 명령">
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

## ibmcloud sl dns import
{: #sl_dns_import}

BIND 구역 파일 기반이 아닌 구역을 가져옵니다.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--dry-run</dt>
<dd>레코드를 실제로 작성하지 않음.</dd>
</dl>

**예제**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
이 명령은 ~/ibm.com.txt 파일에서 구역 및 해당 리소스 레코드를 가져옵니다.

## ibmcloud sl dns record-add
{: #sl_dns_record_add}

구역의 리소스 레코드를 추가합니다.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL(Time-To-Live)(초). 예: 86400. 기본값: 7200.</dd>
</dl>

**예제**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
이 명령은 A 레코드를 ibm.com 구역에 추가합니다. 해당 호스트는 "ftp"이고, 데이터는 "127.0.0.1"이며 ttl은 86400초입니다.

## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

구역의 리소스 레코드를 업데이트합니다.
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--by-record</dt>
<dd>호스트 레코드로 편집(예: www).</dd>
<dt>--by-id</dt>
<dd>해당 ID별로 단일 레코드 편집.</dd>
<dt>--data</dt>
<dd>레코드 데이터(예: IP 주소).</dd>
<dt>--ttl</dt>
<dd>TTL 값(초)(예: 86400).</dd>
</dl>

**예제**:
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
이 명령은 ID가 12345678인 ibm.com 구역 아래의 레코드를 편집하고, 해당 데이터는 "127.0.0.2"로 설정하고 ttl은 3600으로 설정합니다.

## ibmcloud sl dns record-list
{: #sl_dns_record_list}

구역의 모든 리소스 레코드를 나열합니다.
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--data</dt>
<dd>레코드 데이터별 필터링(예: IP 주소).</dd>
<dt>--record</dt>
<dd>호스트 레코드로 필터링(예: www).</dd>
<dt>--ttl</dt>
<dd>TTL 값별 필터링(초)(예: 86400).</dd>
<dt>--type</dt>
<dd>레코드 유형별 필터링(예: A 또는 CNAME).</dd>
</dl>

**예제**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
이 명령은 ibm.com 구역 아래의 모든 A 레코드를 나열합니다. 호스트 기준 필터링은 elasticsearch이고 ttl은 900초입니다.

## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

구역에서 리소스 레코드를 제거합니다.
```
ibmcloud sl dns record-remove RECORD_ID
```


**예제**:
```
ibmcloud sl dns record-remove 12345678
```
이 명령은 ID가 12345678인 리소스 레코드를 제거합니다.

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

구역을 작성합니다.
```
ibmcloud sl dns zone-create ZONE
```


**예제**:
```
ibmcloud sl dns zone-create ibm.com
```
이 명령은 이름이 ibm.com인 구역을 작성합니다.

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

구역을 삭제합니다.
```
ibmcloud sl dns zone-delete ZONE
```


**예제**:
```
ibmcloud sl dns zone-delete ibm.com
```
이 명령은 이름이 ibm.com인 구역을 삭제합니다.

## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

계정의 모든 구역을 나열합니다.
```
ibmcloud sl dns zone-list
```


**예제**:
```
ibmcloud sl dns zone-list
```
이 명령은 현재 계정 아래의 모든 구역을 나열합니다.

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

BIND 형식으로 구역 및 리소스 레코드를 인쇄합니다.
```
ibmcloud sl dns zone-print ZONE
```


**예제**:
```
ibmcloud sl dns zone-print ibm.com
```
이 명령은 BIND 형식으로 이름이 ibm.com인 구역을 인쇄합니다.
