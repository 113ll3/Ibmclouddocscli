---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 이미지

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 인프라 이미지를 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 인프라 이미지 명령">
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl image delete
{: #sl_image_delete}

이미지를 삭제합니다.
```
ibmcloud sl image delete IDENTIFIER
```
**예제**:
```
   ibmcloud sl image delete 12345678
```
이 명령은 ID가 `12345678`인 이미지를 삭제합니다.

## ibmcloud sl image detail
{: #sl_image_detail}

이미지에 대한 세부사항을 가져옵니다.
```
ibmcloud sl image detail IDENTIFIER
```
**예제**:
```
 ibmcloud sl image detail 12345678
```
이 명령은 ID가 12345678인 이미지의 세부사항을 가져옵니다.

## ibmcloud sl image edit
{: #sl_image_edit}

이미지의 세부사항을 편집합니다.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--name</dt>
<dd>이미지의 이름입니다.</dd>
<dt>--note</dt>
<dd>이미지에 대한 추가 참고입니다.</dd>
<dt>--tag</dt>
<dd>이미지에 대한 태그입니다.</dd>
</dl>

*예제**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
이 명령은 ID가 `12345678`인 이미지를 편집하고 해당 이름을 `ubuntu16`, 참고를 `testing`, 태그를 `staging`으로 설정합니다.

## ibmcloud sl image list
{: #sl_image_list}

계정의 모든 이미지를 나열합니다.
```
ibmcloud sl image list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--name</dt>
<dd>이미지 이름 필터링.</dd>
<dt>--public</dt>
<dd>공용 이미지만 표시.</dd>
<dt>--private</dt>
<dd>개인용 이미지만 표시.</dd>
</dl>
