---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# API 키, ID 및 액세스 관리
{: #ibmcloud_commands_iam}

<table summary="API 키 및 정책을 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
 <caption>표 1. API 키 및 정책 관리를 위한 명령</caption>
  <thead>
  <th colspan="5">API 키 및 정책 관리를 위한 명령</th>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-ids](cli_api_policy.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam service-id](cli_api_policy.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](cli_api_policy.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](cli_api_policy.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](cli_api_policy.html#ibmcloud_iam_service_id_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-id-lock](cli_api_policy.html#ibmcloud_iam_service_id_lock)</td>
   <td>[ibmcloud iam service-id-unlock](cli_api_policy.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam api-keys
](cli_api_policy.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](cli_api_policy.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](cli_api_policy.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](cli_api_policy.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](cli_api_policy.html#ibmcloud_iam_api_key_lock)</td>
   <td>[ibmcloud iam api-key-unlock](cli_api_policy.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](cli_api_policy.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](cli_api_policy.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](cli_api_policy.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](cli_api_policy.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](cli_api_policy.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-api-key-lock](cli_api_policy.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[ibmcloud iam service-api-key-unlock](cli_api_policy.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-policies](cli_api_policy.html#ibmcloud_iam_service_policies)</td>
   <td>[ibmcloud iam service-policy](cli_api_policy.html#ibmcloud_iam_service_policy)</td>
   <td>[ibmcloud iam service-policy-create](cli_api_policy.html#ibmcloud_iam_service_policy_create)</td>
   <td>[ibmcloud iam service-policy-update](cli_api_policy.html#ibmcloud_iam_service_policy_update)</td>
   <td>[ibmcloud iam service-policy-delete](cli_api_policy.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](cli_api_policy.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](cli_api_policy.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](cli_api_policy.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](cli_api_policy.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](cli_api_policy.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam oauth-tokens
](cli_api_policy.html#ibmcloud_iam_oauth_tokens)</td>
   <td>[ibmcloud iam dedicated-id-disconnect](cli_api_policy.html#ibmcloud_iam_dedicated_id_disconnect)</td>
   <td>[ibmcloud iam authorization-policy-create](cli_api_policy.html#ibmcloud_iam_authorization_policy_create)</td>
   <td>[ibmcloud iam authorization-policy-delete](cli_api_policy.html#ibmcloud_iam_authorization_policy_delete)</td>
   <td>[ibmcloud iam authorization-policy](cli_api_policy.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam authorization-policies
](cli_api_policy.html#ibmcloud_iam_authorization_policies)</td>
   <td>[ibmcloud iam access-groups](cli_api_policy.html#ibmcloud_iam_access-groups)</td>
   <td>[ibmcloud iam access-group](cli_api_policy.html#ibmcloud_iam_access-group)</td>
   <td>[ibmcloud iam access-group-create](cli_api_policy.html#ibmcloud_iam_access-group-create)</td>
   <td>[ibmcloud iam access-group-update](cli_api_policy.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-delete](cli_api_policy.html#ibmcloud_iam_access-group-delete)</td>
   <td>[ibmcloud iam access-group-users](cli_api_policy.html#ibmcloud_iam_access-group-users)</td>
   <td>[ibmcloud iam access-group-user-add](cli_api_policy.html#ibmcloud_iam_access-group-user-add)</td>
   <td>[ibmcloud iam access-group-user-remove](cli_api_policy.html#ibmcloud_iam_access-group-user-remove)</td>
   <td>[ibmcloud iam access-group-user-purge](cli_api_policy.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-service-ids](cli_api_policy.html#ibmcloud_iam_access-group-service-ids)</td>
   <td>[ibmcloud iam access-group-service-id-add](cli_api_policy.html#ibmcloud_iam_access-group-service-id-add)</td>
   <td>[ibmcloud iam access-group-service-id-remove](cli_api_policy.html#ibmcloud_iam_access-group-service-id-remove)</td>
   <td>[ibmcloud iam access-group-service-id-purge](cli_api_policy.html#ibmcloud_iam_access-group-service-id-purge)</td>
   <td>[ibmcloud iam access-group-policies](cli_api_policy.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-policy](cli_api_policy.html#ibmcloud_iam_access-group-policy)</td>
   <td>[ibmcloud iam access-group-policy-create](cli_api_policy.html#ibmcloud_iam_access_group_policy_create)</td>
   <td>[ibmcloud iam access-group-policy-update](cli_api_policy.html#ibmcloud_iam_access_group_policy_update)</td>
   <td>[ibmcloud iam access-group-policy-delete](cli_api_policy.html#ibmcloud_iam_access_group_policy_delete)</td>
  </tr>
  </tbody>
  </table>

  ## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

모든 서비스 ID 나열

```
ibmcloud iam service-ids [--uuid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>서비스 ID의 UUID만 표시</dd>
</dl>

<strong>예제</strong>:
현재 계정 아래에 모든 서비스 ID의 UUID 나열

```
ibmcloud iam service-ids --uuid
```

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

서비스 ID의 세부사항 표시

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>--uuid</dt>
  <dd>서비스 ID의 UUID 표시</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-test`의 세부사항 표시

```
ibmcloud iam service-id sample-test
```
서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 세부사항 표시

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

서비스 ID 작성

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스 ID의 설명</dd>
  <dt>--lock</dt>
  <dd>작성 시 서비스 ID 잠금</dd>
</dl>

<strong>예제</strong>:

서비스 이름이 `sample-test`이고 해당 설명이 `hello, world!`인 서비스 ID 작성

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

서비스 이름이 `sample-test`이고 설명이 `hello, world!`인 잠긴 서비스 ID 작성

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```

## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
서비스 ID 업데이트

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-n, --name</dt>
  <dd>서비스의 새 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스의 새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 ID 이름 `sample-test`를 확인 없이 `sample-test-2`로 바꾸기

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

서비스 `sample-test`의 설명 업데이트

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 이름을 설명이 새로 포함된 `sample-test-3`으로 바꾸기

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

서비스 ID 삭제

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 삭제

```
ibmcloud iam service-id-delete sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 삭제

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

서비스 ID 잠금

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 잠금

```
ibmcloud iam service-id-lock sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

서비스 ID 잠금 해제

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금 해제</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-teset` 잠금 해제

```
ibmcloud iam service-id-unlock sample-teset -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금 해제

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 나열

```
ibmcloud iam api-keys
```

<strong>전제조건</strong>: 엔드포인트, 로그인

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

새 {{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 작성

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>작성할 API 키의 이름입니다.</dd>
<dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
<dd>API 키의 설명</dd>
<dt>--file <i>FILE</i></dt>
<dd>지정된 파일에 API 키 정보를 저장합니다. 설정하지 않으면 JSON 컨텐츠가 표시됩니다.</dd>
<dt>--lock</dt>
<dd>작성 시 API 키 잠금</dd>
</dl>

<strong>예제</strong>:

API 키 작성 및 파일에 저장

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

이름이 "test-key"인 잠긴 API 키 작성

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 업데이트

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>업데이트할 API 키의 이전 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>업데이트할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-n <i>NAME</i>(선택사항)</dt>
<dd>API 키의 새 이름</dd>
<dt>-d <i>DESCRIPTION</i>(선택사항)</dt>
<dd>API 키의 새 설명</dd>
</dl>

<strong>예제</strong>:

API 키의 설명 업데이트:

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

{{site.data.keyword.Bluemix_notm}} 플랫폼 API 키 삭제

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>삭제할 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>삭제할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제 삭제합니다.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

플랫폼 API 키 잠금

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠글 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠글 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠급니다.</dd>
</dl>

<strong>예제</strong>:

API 키 test-api-key 잠금

```
ibmcloud iam api-key-lock test-api-key
```

확인 없이 UUID가 지정된 API 키 잠금

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

플랫폼 API 키 잠금 해제

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠금 해제할 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠금 해제할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠금 해제합니다.</dd>
</dl>

<strong>예제</strong>:

API 키 test-api-key 잠금 해제

```
ibmcloud iam api-key-unlock test-api-key
```

확인 없이 UUID가 지정된 API 키 잠금 해제

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

서비스의 모든 API 키 나열

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 API 키 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `sample-service`의 모든 API 키 나열:

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

서비스 API 키의 세부사항 나열

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>--uuid</dt>
  <dd>서비스 API 키의 UUID 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 API 키 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `sample-service`의 서비스 API 키 `sample-key`의 세부사항 표시:

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

서비스 API 키 작성

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스 ID 또는 새로 작성된 서비스 API 키 이름</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-d, --description</dt>
  <dd>API 키의 설명</dd>
  <dt>--file</dt>
  <dd>지정된 파일에 API 키 정보를 저장합니다. 설정하지 않으면 JSON 컨텐츠가 표시됩니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 작성</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 `sample-service`의 서비스 API 키 `sample-key` 작성:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

서비스 API 키 업데이트

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-n, --name</dt>
  <dd>서비스 API 키의 새 이름</dd>
  <dt>-d, --description</dt>
  <dd>서비스 API 키의 새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 API 키 이름 `sample-key`를 `new-sample-key`로 바꾸기:

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

서비스 API 키 삭제

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 삭제:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

서비스 API 키 잠금

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 잠금:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

서비스 API 키 잠금 해제

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금 해제</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 잠금 해제:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

사용자 `name@example.com`의 정책 나열:

```
ibmcloud iam user-policies name@example.com
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
</dl>

<strong>예제</strong>:

사용자 `name@example.com`의 정책 나열:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

사용자 정책의 세부사항 표시

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>POLICY_ID(필수)</dt>
<dd>정책 ID</dd>
</dl>

<strong>예제</strong>:

사용자 `name@example.com`의 정책 `0bb730daa` 나열:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

사용자 정책 작성

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>--file <i>FILE</i>(선택사항)</dt>
<dd>정책 정의의 JSON 파일</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (선택사항)</dt>
<dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
<dt>--service-name <i>SERVICE_NAME</i>(선택사항)</dt>
<dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>(선택사항)</dt>
<dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--region <i>REGION</i>(선택사항)</dt>
<dd>정책 정의의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>(선택사항)</dt>
<dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource <i>RESOURCE</i>(선택사항)</dt>
<dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>(선택사항)</dt>
<dd>리소스 그룹의 이름. 이는 '--file', '--resource' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>(선택사항)</dt>
<dd>리소스 그룹의 ID. 이는 '--file', '--resource' 및 '--resource-group-name' 플래그와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

정책 JSON 파일 `policy.json`에서 사용자 `name@example.com`의 사용자 정책 작성:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

모든 `sample-service` 리소스에 `name@example.com` `Administrator` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 샘플 서비스 인스턴스의 리소스 `key123`에 `name@example.com` `Editor` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 `name@example.com` `Operator` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 `name@example.com` `Viewer` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 `name@example.com` `Viewer` 역할 제공:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

사용자 정책 업데이트

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dt>USER_NAME(필수)</dt>
<dd>정책이 속한 사용자 이름</dd>
<dt>POLICY_ID(필수)</dt>
<dd>업데이트할 정책의 ID</dd>
<dt>--file <i>FILE</i>(선택사항)</dt>
<dd>정책 정의의 JSON 파일</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (선택사항)</dt>
<dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
<dt>--service-name <i>SERVICE_NAME</i>(선택사항)</dt>
<dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>(선택사항)</dt>
<dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--region <i>REGION</i>(선택사항)</dt>
<dd>정책 정의의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>(선택사항)</dt>
<dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource <i>RESOURCE</i>(선택사항)</dt>
<dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>(선택사항)</dt>
<dd>리소스 그룹의 이름. 이는 '--file', '--resource' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>(선택사항)</dt>
<dd>리소스 그룹의 ID. 이는 '--file', '--resource' 및 '--resource-group-name' 플래그와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

사용자 정책을 JSON 파일로 된 정책으로 업데이트:

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

모든 `sample-service` 리소스에 `name@example.com` `Administrator` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 `us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 샘플 서비스 인스턴스의 리소스 `key123`에 `name@example.com` `Editor` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 `name@example.com` `Operator` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 `name@example.com` `Viewer` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

ID `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 `name@example.com` `Viewer` 역할을 제공하도록 사용자 정책 업데이트:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

사용자 정책 삭제

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 계정을 대상으로 지정

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 사용자 정책 삭제</dd>
</dl>

<strong>예제</strong>:
사용자 `name@example.com`의 정책 `user-policy-id` 삭제:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

확인 없이 사용자 `name@example.com`의 정책 `user-policy-id` 삭제:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

지정된 서비스의 모든 서비스 정책 나열

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>-json</dt>
  <dd>JSON 형식으로 정책 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 나열:

```
ibmcloud iam service-policies test
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 나열:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

서비스 정책의 세부사항 표시

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>-json</dt>
  <dd>JSON 형식으로 정책 표시</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 표시</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 `140798e2-8ea7db3` 표시:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 `140798e2-8ea7db3` 표시:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

서비스 정책 작성

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일. 이는 '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' 및 '--resource-group-id' 플래그와 배타적입니다.</dd>
  <dt>-r, --roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>--service-name</dt>
  <dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource</dt>
  <dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>--resource-group-id </dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 작성</dd>
</dl>

<strong>예제</strong>:

서비스 `test`에 대해 JSON 파일에서 서비스 정책 작성:

```
ibmcloud iam service-policy-create test --file @policy.json
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`에 대해 JSON 파일에서 서비스 정책 작성:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

서비스 정책 업데이트

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일. 이는 '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' 및 'resource-group-id' 플래그와 배타적입니다.</dd>
  <dt>-r, --roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이는 '--file' 플래그와 배타적입니다.</dd>
  <dt>--resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>--resource-group-id </dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 서비스 정책 업데이트</dd>
</dl>

<strong>예제</strong>:

서비스 `test`에 대해 JSON 파일에서 서비스 정책 `140798e2-8ea7db3` 업데이트:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`에 대해 JSON 파일에서 서비스 정책 `140798e2-8ea7db3` 업데이트:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

서비스 정책 삭제

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SERVICE_ID(필수)</dt>
  <dd>서비스 ID의 UUID 또는 이름</dd>
  <dt>POLICY_ID(필수)</dt>
  <dd>서비스 정책의 ID<dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

서비스 `test`의 정책 `140798e2-8ea7db3` 삭제

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
서비스 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`의 정책 `140798e2-8ea7db3` 삭제

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

현재 세션에 대한 OAuth 토큰 검색 및 표시

```
ibmcloud iam oauth-tokens
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

OAuth 토큰 새로 고치기 및 표시

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

전용 비IBM ID와 공용 IBM ID의 연결 끊기

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 연결 끊기</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

다른 서비스 인스턴스에 대한 서비스 인스턴스 액세스를 허용하기 위한 권한 부여 정책을 작성합니다.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>액세스 권한이 부여될 수 있는 소스 서비스입니다.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>소스 서비스의 액세스 권한이 부여될 수 있는 대상 서비스입니다.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>소스 서비스에 대한 액세스 권한을 제공하는 역할입니다.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>소스 서비스의 모든 인스턴스의 액세스 권한이 부여될 소스 서비스 인스턴스 이름(지정되지 않은 경우)입니다.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>대상 서비스의 모든 인스턴스의 액세스 권한이 부여될 대상 서비스 인스턴스 이름(지정되지 않은 경우)입니다.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

권한 부여 정책을 삭제합니다.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>삭제할 권한 정책의 ID입니다.</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제를 강제 실행합니다.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

권한 정책의 세부사항을 표시합니다.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>전제조건</strong>: 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>표시할 권한 정책의 ID입니다.</dd>
</dl>

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

현재 계정의 권한 부여 정책을 나열합니다.

```
ibmcloud iam authorization-policies
```

<strong>전제조건</strong>: 로그인, 대상

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

현재 계정에서 액세스 그룹 나열

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-u</dt>
  <dd>사용자가 속한 액세스 그룹을 나열합니다. 이 플래그는 '-s'와 배타적입니다.</dd>
  <dt>-s</dt>
  <dd>서비스 ID가 속한 액세스 그룹을 나열합니다. 이 플래그는 '-u'와 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹 나열:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

액세스 그룹의 세부사항 표시

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-id</dt>
  <dd>ID만 표시</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 세부사항 표시:

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

액세스 그룹 작성

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>액세스 그룹에 대한 설명</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group` 작성:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

액세스 그룹 업데이트

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>새 액세스 그룹 이름</dd>
  <dt>-d, --description</dt>
  <dd>새 설명</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 업데이트</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 이름을 `hello_world_group`으로 바꾸기:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

액세스 그룹 삭제

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
  <dt>-r, --recursive</dt>
  <dd>액세스 그룹 및 해당 구성원 삭제</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group` 삭제:

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

액세스 그룹의 사용자 나열

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 모든 사용자 나열:

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

액세스 그룹에 사용자 추가

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 사용자 `name@example.com` 추가:

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

액세스 그룹에서 사용자 제거

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에서 사용자 `name@example.com` 제거:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

모든 액세스 그룹에서 사용자 제거

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹에서 사용자 `name@example.com` 제거:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

액세스 그룹에 서비스 ID 나열

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 모든 서비스 ID 나열:

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

액세스 그룹에 서비스 ID 추가

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에 서비스 ID `example-service` 추가:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

액세스 그룹에서 서비스 ID 제거

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`에서 서비스 ID `example-service` 제거:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

모든 액세스 그룹에서 서비스 ID 제거

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 삭제</dd>
</dl>

<strong>예제</strong>:

모든 액세스 그룹에서 서비스 ID `example-service` 제거:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

액세스 그룹의 정책 나열

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 모든 정책 나열:

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

액세스 그룹 정책의 세부사항 표시

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 정책 `51b9717e-76b0-4f6a-bda7-b8132431f926`에 대한 세부사항 표시:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

액세스 그룹 정책 작성

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일</dd>
  <dt>-roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>-resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

JSON 파일에서 액세스 그룹 정책 작성:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

모든 `sample-service` 리소스에 `example_group` `Administrator` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 `sample-service` 인스턴스의 리소스 `key123`에 `example_group` `Editor` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 대한 `example_group` `Operator` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 대한 `example_group` `Viewer` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 대한 `example_group` `Viewer` 역할 제공:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

액세스 그룹 정책 업데이트

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>--file</dt>
  <dd>정책 정의의 JSON 파일</dd>
  <dt>--roles</dt>
  <dd>정책 정의의 역할 이름. 특정 서비스의 지원되는 역할의 경우 'ibmcloud iam roles --service SERVICE_NAME'을 실행하십시오. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-name</dt>
  <dd>정책 정의의 서비스 이름. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>정책 정의의 서비스 인스턴스의 GUID. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-region</dt>
  <dd>정책 정의 지역. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-type</dt>
  <dd>정책 정의의 리소스 유형. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource</dt>
  <dd>정책 정의의 리소스. 이 옵션은 '--file'과 배타적입니다.</dd>
  <dt>-resource-group-name</dt>
  <dd>리소스 그룹의 이름. 이 옵션은 '--file' 및 '--resource-group-id'와 배타적입니다.</dd>
  <dt>-resource-group-id</dt>
  <dd>리소스 그룹의 ID. 이 옵션은 '--file' 및 '--resource-group-name'과 배타적입니다.</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 정책을 정책 JSON 파일의 정책으로 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

모든 `sample-service` 리소스에 대한 `example_group` `Administrator` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

`us-south` 지역에 있는 GUID가 `d161aeea-fd02-40f8-a487-df1998bd69a9`인 `sample-service` 인스턴스의 리소스 `key123`에 대한 `example_group` `Editor` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹에 대한 `example_group` `Operator` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

리소스 그룹 `sample-resource-group`의 멤버에 대한 `example_group` `Viewer` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

ID가 `dda27e49d2a1efca58083a01dfde18f6`인 리소스 그룹의 멤버에 대한 `example_group` `Viewer` 역할을 제공하도록 액세스 그룹 정책 업데이트:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

액세스 그룹 정책 삭제

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>확인 없이 강제 삭제</dd>
</dl>

<strong>예제</strong>:

액세스 그룹 `example_group`의 정책 `51b9717e-76b0-4f6a-bda7-b8132431f926` 삭제:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
