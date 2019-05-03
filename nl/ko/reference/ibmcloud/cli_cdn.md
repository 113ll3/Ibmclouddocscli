---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN 서비스에 대한 작업
{: #sl-cdn-service}

Content Delivery Network(CDN) 서비스는 필요한 위치에 컨텐츠를 분배합니다. 처음으로 컨텐츠가 요청되면 호스트 서버에서 네트워크로 가져온 후 다른 사용자가 액세스할 수 있도록 네트워크에서 유지됩니다.

다음 명령을 사용하여 {{site.data.keyword.cloud_notm}} 클래식 인프라 CDN 서비스를 관리하십시오.
{: shortdesc}

## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

CDN 계정을 취소합니다.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

CDN 계정의 세부사항을 표시합니다.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

모든 CDN 계정을 나열합니다.
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id, name, type, created.</dd>
<dt>--order</dt>
<dd>주문 ID별 필터링.</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

모든 에지 노드에서 하나 이상의 파일을 캐시합니다.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

CDN 계정을 주문합니다.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN 대역폭. 지정되지 않은 경우 '종량과금제' 가격이 사용됩니다.</dd>
<dt>-s, --storage</dt>
<dd>CDN 스토리지. 지정되지 않은 경우 '종량과금제' 가격이 사용됩니다.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

CDN 계정 주문을 위한 대역폭 및 스토리지 옵션입니다.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

원본 가져오기(pull) 맵핑을 작성합니다.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-t, --type</dt>
<dd>이 맵핑의 매체 유형(http, flash, wm, ...). 기본값: http.</dd>
<dt>-c, --cname</dt>
<dd>맵핑에 첨부할 선택적 CNAME.</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

원본 가져오기(pull) 맵핑을 나열합니다.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

원본 가져오기(pull) 맵핑을 제거합니다.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

모든 에지 노드에서 캐시된 파일을 영구 제거합니다.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>
