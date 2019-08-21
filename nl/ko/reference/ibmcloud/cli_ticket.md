---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 클래식 인프라 티켓 관리
{: #manage-sl-tickets}

다음 명령을 사용하여 {{site.data.keyword.cloud}} 클래식 인프라 티켓을 관리할 수 있습니다.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

티켓에 디바이스를 첨부하려면 다음을 수행하십시오.
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--hardware</dt>
<dd>첨부할 하드웨어에 대한 식별자입니다.</dd>
<dt>--virtual</dt>
<dd>첨부할 가상 서버의 ID입니다.</dd>
</dl>

**예제**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

지원 티켓을 작성하려면 다음을 수행하십시오.
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--attachment</dt>
<dd>티켓에 첨부할 초기 오브젝트 ID 번호입니다.</dd>
<dt>--rootpwd</dt>
<dd>첨부된 디바이스 ID와 연관된 루트 비밀번호입니다.</dd>
<dt>--subject-id</dt>
<dd>필수. 티켓에 사용할 주제 ID입니다. 목록을 가져오려면 `ibmcloudsl ticket subjects`를 실행하십시오.</dd>
<dt>--title</dt>
<dd>필수. 티켓의 제목입니다.</dd>
<dt>--body</dt>
<dd>티켓 본문입니다.</dd>
<dt>--priority</dt>
<dd>티켓 우선순위[1|2|3|4]입니다. 1 (위험)부터 4(최소 영향)까지 있습니다. 고급 및 프리미엄 지원에서만 설정할 수 있습니다. https://www.ibm.com/cloud/support를 참조하십시오.</dd>
<dt>--attachment-type</dt>
<dd>첨부 유형 즉 hardware 또는 virtual을 지정합니다. 기본값은 hardware입니다.</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

티켓에서 디바이스를 분리하려면 다음을 수행하십시오.
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--hardware</dt>
<dd>분리할 하드웨어에 대한 식별자입니다.</dd>
<dt>--virtual</dt>
<dd>분리할 가상 서버의 ID입니다.</dd>
</dl>

**예제**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

티켓 세부사항을 보려면 다음을 수행하십시오.
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--count</dt>
<dd>업데이트 수입니다.</dd>
</dl>

**예제**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

티켓을 나열하려면 다음을 수행하십시오.
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--open</dt>
<dd>열려 있는 티켓만 표시합니다.</dd>
<dt>--closed</dt>
<dd>닫힌 티켓만 표시합니다.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

티켓 작성을 위한 주제 ID를 나열하려면 다음을 수행하십시오.
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

티켓에 대한 요약 정보를 보려면 다음을 수행하십시오.
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

기존 티켓에 업데이트를 추가하려면 다음을 수행하십시오.
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**예제**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

기존 티켓에 첨부를 추가하려면 다음을 수행하십시오.
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>명령 옵션</strong>:
<dl>
<dt>--name</dt>
<dd>티켓에 표시된 첨부의 이름입니다.</dd>
</dl>

**예제**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

