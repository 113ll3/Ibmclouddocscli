---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl image, manage compute images, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 컴퓨팅 이미지 작성, 편집 및 삭제
{: #sl-manage-compute-images}

다음 명령을 사용하여 {{site.data.keyword.cloud}} 컴퓨팅 이미지를 관리하십시오.
{: shortdesc}

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

이 명령은 ID가 `12345678`인 이미지의 세부사항을 가져옵니다.

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
