---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理 IAM 存取、API 金鑰、服務 ID 及存取群組
{: #ibmcloud_commands_iam}

請使用下列指令管理使用者、服務及存取群組的 API 金鑰、服務 ID、存取群組及授權原則。
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

列出所有服務 ID。

```
ibmcloud iam service-ids [--uuid]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--uuid</dt>
  <dd>僅顯示服務 ID 的 UUID</dd>
</dl>

<strong>範例</strong>：列出現行帳戶下所有服務 ID 的 UUID：

```
ibmcloud iam service-ids --uuid
```

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

顯示服務 ID 的詳細資料。

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱，與 UUID 不能同時使用</dd>
  <dt>UUID（必要）</dt>
  <dd>服務的 UUID，與 NAME 不能同時使用</dd>
  <dt>--uuid</dt>
  <dd>顯示服務 ID 的 UUID</dd>
</dl>

<strong>範例</strong>：

顯示服務 ID `sample-test` 的詳細資料。

```
ibmcloud iam service-id sample-test
```
顯示服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的詳細資料。

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

建立服務 ID。

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務 ID 的說明</dd>
  <dt>--lock</dt>
  <dd>建立時鎖定服務 ID</dd>
</dl>

<strong>範例</strong>：

建立服務名稱為 `sample-test` 且說明為 `hello, world!` 的服務 ID。

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

建立服務名稱為 `sample-test` 且說明為 `hello, world!` 的鎖定服務 ID。

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
--lock
```

## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
更新服務 ID。

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱，與 UUID 不能同時使用</dd>
  <dt>UUID（必要）</dt>
  <dd>服務的 UUID，與 NAME 不能同時使用</dd>
  <dt>-n, --name</dt>
  <dd>服務的新名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務的新說明</dd>
  <dt>-f, --force</dt>
  <dd>更新而不進行確認</dd>
</dl>

<strong>範例</strong>：

將服務 ID `sample-test` 重新命名為 `sample-test-2`，而不進行確認。

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

更新服務 `sample-test` 的說明。

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

將服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 重新命名為 `sample-test-3`，並具有新的說明。

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

刪除服務 ID。

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱，與 UUID 不能同時使用</dd>
  <dt>UUID（必要）</dt>
  <dd>服務的 UUID，與 NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務 ID `sample-teset`，而不進行確認。

```
ibmcloud iam service-id-delete sample-teset -f
```

刪除服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`。

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

鎖定服務 ID。

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱，與 UUID 不能同時使用</dd>
  <dt>UUID（必要）</dt>
  <dd>服務的 UUID，與 NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>鎖定而不進行確認</dd>
</dl>

<strong>範例</strong>：

鎖定服務 ID `sample-teset`，而不進行確認。

```
ibmcloud iam service-id-lock sample-teset -f
```

鎖定服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`。

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

解除鎖定服務 ID。

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務的名稱，與 UUID 不能同時使用</dd>
  <dt>UUID（必要）</dt>
  <dd>服務的 UUID，與 NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>解除鎖定，而不進行確認</dd>
</dl>

<strong>範例</strong>：

解除鎖定服務 ID `sample-teset`，而不進行確認。

```
ibmcloud iam service-id-unlock sample-teset -f
```

解除鎖定服務 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`。

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

列出所有 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰。

```
ibmcloud iam api-keys
```

<strong>必要條件</strong>：端點、登入

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

建立新的 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰。

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要建立之 API 金鑰的名稱。</dd>
<dt>-d <i>DESCRIPTION</i>（選用）</dt>
<dd>API 金鑰的說明</dd>
<dt>--file <i>FILE</i></dt>
<dd>將 API 金鑰資訊儲存至指定的檔案。</dd>
<dt>--lock</dt>
<dd>建立時鎖定 API 金鑰</dd>
</dl>

<strong>範例</strong>：

建立 API 金鑰，並儲存至檔案。

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

建立名稱為 "test-key" 的鎖定 API 金鑰。

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

更新 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰。

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要更新之 API 金鑰的舊名稱，與 UUID 不能同時使用</dd>
<dt>UUID（必要）</dt>
<dd>要更新之 API 金鑰的 UUID，與 NAME 不能同時使用</dd>
<dt>-n <i>NAME</i>（選用）</dt>
<dd>API 金鑰的新名稱</dd>
<dt>-d <i>DESCRIPTION</i>（選用）</dt>
<dd>API 金鑰的新說明</dd>
</dl>

<strong>範例</strong>：

更新 API 金鑰的說明：

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

刪除 {{site.data.keyword.Bluemix_notm}} 平台 API 金鑰。

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要刪除之 API 金鑰的名稱，與 UUID 不能同時使用。</dd>
<dt>UUID（必要）</dt>
<dd>要刪除之 API 金鑰的 UUID，與 NAME 不能同時使用。</dd>
<dt>-f, --force</dt>
<dd>強制刪除，而不進行確認。</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

鎖定平台 API 金鑰。

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要鎖定之 API 金鑰的名稱，與 UUID 不能同時使用</dd>
<dt>UUID（必要）</dt>
<dd>要鎖定之 API 金鑰的 UUID，與 NAME 不能同時使用</dd>
<dt>-f, --force</dt>
<dd>強制鎖定，而不進行確認。</dd>
</dl>

<strong>範例</strong>：

鎖定 API 金鑰 test-api-key。

```
ibmcloud iam api-key-lock test-api-key
```

鎖定具有給定 UUID 的 API 金鑰，而不進行確認。

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

解除鎖定平台 API 金鑰。

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要解除鎖定之 API 金鑰的名稱，與 UUID 不能同時使用</dd>
<dt>UUID（必要）</dt>
<dd>要解除鎖定之 API 金鑰的 UUID，與 NAME 不能同時使用</dd>
<dt>-f, --force</dt>
<dd>強制解除鎖定，而不進行確認。</dd>
</dl>

<strong>範例</strong>：

解除鎖定 API 金鑰 test-api-key。

```
ibmcloud iam api-key-unlock test-api-key
```

解除鎖定具有給定 UUID 的 API 金鑰，而不進行確認。

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

列出服務的所有 API 金鑰。

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務 API 金鑰，而不進行確認</dd>
</dl>

<strong>範例</strong>：

列出服務 `sample-service` 的所有 API 金鑰：

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

列出服務 API 金鑰的詳細資料。

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>--uuid</dt>
  <dd>顯示服務 API 金鑰的 UUID</dd>
  <dt>-f, --force</dt>
  <dd>顯示服務 API 金鑰，而不進行確認</dd>
</dl>

<strong>範例</strong>：

顯示服務 `sample-service` 的服務 API 金鑰 `sample-key` 的詳細資料：

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

建立服務 API 金鑰。

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務 ID 的名稱，或新建立的服務 API 金鑰</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-d, --description</dt>
  <dd>API 金鑰的說明</dd>
  <dt>--file</dt>
  <dd>將 API 金鑰資訊儲存至指定的檔案。</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：

建立服務 `sample-service` 的服務 API 金鑰 `sample-key`，而不進行確認：

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

更新服務 API 金鑰。

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-n, --name</dt>
  <dd>服務 API 金鑰的新名稱</dd>
  <dt>-d, --description</dt>
  <dd>服務 API 金鑰的新說明</dd>
  <dt>-f, --force</dt>
  <dd>更新而不進行確認</dd>
</dl>

<strong>範例</strong>：

將服務 API 金鑰 `sample-key` 重新命名為 `new-sample-key`：

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

刪除服務 API 金鑰。

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務 ID `sample-service` 的服務 API 金鑰 `sample-key`：

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

鎖定服務 API 金鑰。

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>鎖定而不進行確認</dd>
</dl>

<strong>範例</strong>：

服務 ID `sample-service` 的鎖定服務 API 金鑰 `sample-key`：

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

解除鎖定服務 API 金鑰。

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>解除鎖定，而不進行確認</dd>
</dl>

<strong>範例</strong>：

解除鎖定服務 ID `sample-service` 的服務 API 金鑰 `sample-key`：

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

列出使用者 `name@example.com` 的原則：

```
ibmcloud iam user-policies name@example.com
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
</dl>

<strong>範例</strong>：

列出使用者 `name@example.com` 的原則：

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

顯示使用者原則的詳細資料

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>POLICY_ID（必要）</dt>
<dd>原則的 ID</dd>
</dl>

<strong>範例</strong>：

列出使用者 `name@example.com` 的原則 `0bb730daa`：

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

建立使用者原則。

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>--file <i>FILE</i>（選用）</dt>
<dd>原則定義的 JSON 檔案</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（選用）</dt>
<dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（選用）</dt>
<dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>原則定義之服務實例的 UUID。這與 '--file' 旗標不能同時使用。</dd>
<dt>--region <i>REGION</i>（選用）</dt>
<dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（選用）</dt>
<dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource <i>RESOURCE</i>（選用）</dt>
<dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（選用）</dt>
<dd>資源群組的名稱。這與 '--file'、'--resource' 及 '--resource-group-id' 旗標不能同時使用。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（選用）</dt>
<dd>資源群組的 ID。這與 '--file'、'--resource' 及 '--resource-group-name' 旗標不能同時使用。</dd>
</dl>

<strong>範例</strong>：

從原則 JSON 檔案 `policy.json`，建立使用者 `name@example.com` 的使用者原則：

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Give `name@example.com` `Editor` role for resource `key123` of sample service instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

更新使用者原則。

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dt>USER_NAME（必要）</dt>
<dd>原則所屬的使用者名稱</dd>
<dt>POLICY_ID（必要）</dt>
<dd>要更新之原則的 ID</dd>
<dt>--file <i>FILE</i>（選用）</dt>
<dd>原則定義的 JSON 檔案</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（選用）</dt>
<dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（選用）</dt>
<dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>原則定義之服務實例的 UUID。這與 '--file' 旗標不能同時使用。</dd>
<dt>--region <i>REGION</i>（選用）</dt>
<dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（選用）</dt>
<dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource <i>RESOURCE</i>（選用）</dt>
<dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（選用）</dt>
<dd>資源群組的名稱。這與 '--file'、'--resource' 及 '--resource-group-id' 旗標不能同時使用。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（選用）</dt>
<dd>資源群組的 ID。這與 '--file'、'--resource' 及 '--resource-group-name' 旗標不能同時使用。</dd>
</dl>

<strong>範例</strong>：

將使用者原則更新為 JSON 檔案中的使用者原則：

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

更新使用者原則，以針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 更新使用者原則，以針對 `us-south` 地區中 GUID 為 `d161aeea-fd02-40f8-a487-df1998bd69a9` 之範例服務實例的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

更新使用者原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新使用者原則，以針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

更新使用者原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `name@example.com`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

刪除使用者原則。

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入、設為目標的帳戶

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除使用者原則，而不進行確認</dd>
</dl>

<strong>範例</strong>：刪除使用者 `name@example.com` 的原則 `user-policy-id`：

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

刪除使用者 `name@example.com` 的原則 `user-policy-id`，而不進行確認：

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

列出指定服務的所有服務原則。

```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定服務原則輸出格式，目前只支援 JSON。</dd>
  <dt>-f, --force（選用）</dt>
  <dd>顯示服務原則，而不進行確認</dd>
</dl>

<strong>範例</strong>：

列出服務 `test` 的原則：

```
ibmcloud iam service-policies test
```
列出服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

顯示服務原則的詳細資料

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定服務原則輸出格式，目前只支援 JSON。</dd>
  <dt>-f, --force（選用）</dt>
  <dd>顯示服務原則，而不進行確認</dd>
</dl>

<strong>範例</strong>：

顯示服務 `test` 的原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
顯示服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

建立服務原則。

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [-f, --force]",
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案。這與 '-r, --roles'、'--service-name'、'--service-instance'、'--region'、'--resource-type'、'--resource'、'--resource-group-name' 及 '--resource-group-id' 旗標不能同時使用。</dd>
  <dt>-r, --roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>--service-name</dt>
  <dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-type</dt>
  <dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource</dt>
  <dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
  <dt>--account-management（選用）</dt>
  <dd>提供對所有帳戶管理服務的存取權</dd>
  <dt>-f, --force</dt>
  <dd>建立服務原則，而不進行確認</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，建立服務 `test` 的服務原則：

```
ibmcloud iam service-policy-create test --file @policy.json
```
從 JSON 檔案，建立服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的服務原則：

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

將所有帳戶管理服務的 `Administrator` 角色授與服務 `test`：

```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

將帳戶中所有資源的 `Viewer` 角色授與服務 `test`：

```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

更新服務原則。

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [-f, --force]",
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案。這與 '-r, --roles'、'--service-name'、'--service-instance'、'--region'、'--resource-type'、'--resource'、'resource-group-name' 及 'resource-group-id' 旗標不能同時使用。</dd>
  <dt>-r, --roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。這與 '--file' 旗標不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。這與 '--file' 旗標不能同時使用。</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
  <dt>--account-management（選用）</dt>
  <dd>提供對所有帳戶管理服務的存取權</dd>
  <dt>-f, --force</dt>
  <dd>更新服務原則，而不進行確認</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，更新服務 `test` 的服務原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

從 JSON 檔案，更新服務 `test` 的服務原則 `140798e2-8ea7db3`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

更新服務原則 `140798e2-8ea7db3`，以將所有帳戶管理服務的 `Administrator` 角色授與服務 `test`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

更新服務原則 `140798e2-8ea7db3`，以將帳戶中所有資源的 `Viewer` 角色授與服務 `test`：

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

刪除服務原則。

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ID（必要）</dt>
  <dd>服務 ID 的名稱或 UUID</dd>
  <dt>POLICY_ID（必要）</dt>
  <dd>服務原則的 ID<dd>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除測試 `test` 的原則 `140798e2-8ea7db3`。

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
刪除服務 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的原則 `140798e2-8ea7db3`。

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

擷取並顯示現行階段作業的 OAuth 記號。

```
ibmcloud iam oauth-tokens
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

重新整理並顯示 OAuth 記號。

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

中斷公用 IBM ID 與專用非 IBM ID 的連線。

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制中斷連線，而不進行確認</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

建立授權原則以容許某個服務實例存取另一個服務實例。

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-type RESOURCE_TYPE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME] [--target-resource-type RESOURCE_TYPE | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--output FORMAT]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>可獲得授與存取權的來源服務。</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>可授與來源服務存取權的目標服務。</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>提供來源服務存取權的角色。</dd>  
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>來源服務實例名稱，與 `--source-service-instance-id` 互斥。如果未指定，則會授與所有來源服務實例的存取權。</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>來源服務實例 ID，與 `--source-service-instance-name` 互斥。如果未指定，則會授與所有來源服務實例的存取權。</dd>
  <dt>--source-resource-type</dt>
  <dd>來源服務的資源類型</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>目標服務實例名稱，與 `--target-service-instance-id` 互斥。如果未指定，則會授與所有目標服務實例的存取權。</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>目標服務實例 ID，與 `--target-service-instance-name` 互斥。如果未指定，則會授與所有目標服務實例的存取權。</dd>
  <dt>--target-resource-type</dt>
  <dd>目標服務的資源類型</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

刪除授權原則。

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要刪除的授權原則 ID。</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認。</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

顯示授權原則的詳細資料。

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要顯示的授權原則 ID。</dd>
</dl>

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

列出現行帳戶下的授權原則。

```
ibmcloud iam authorization-policies
```

<strong>必要條件</strong>：登入、目標

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

列出現行帳戶下的存取群組。

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-u</dt>
  <dd>列出使用者所屬的存取群組。此旗標與 '-s' 互斥。</dd>
  <dt>-s</dt>
  <dd>列出服務 ID 所屬的存取群組。此旗標與 '-u' 互斥。</dd>
</dl>

<strong>範例</strong>：

列出所有存取群組：

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

顯示存取群組的詳細資料。

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-id</dt>
  <dd>僅顯示 ID</dd>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 的詳細資料：

```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

建立存取群組。

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-d, --description</dt>
  <dd>存取群組的說明</dd>
</dl>

<strong>範例</strong>：

建立存取群組 `example_group`：

```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

更新存取群組。

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-n, --name</dt>
  <dd>新的存取群組名稱</dd>
  <dt>-d, --description</dt>
  <dd>新的說明</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將存取群組 `example_group` 重新命名為 `hello_world_group`：

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

刪除存取群組。

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
  <dt>-r, --recursive</dt>
  <dd>刪除存取群組及其成員</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group`：

```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

列出存取群組中的使用者。

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有使用者：

```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

將使用者新增至存取群組。

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 新增至存取群組 `example_group`：

```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

從存取群組移除使用者。

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

從所有存取群組移除使用者。

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除使用者 `name@example.com`：

```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

列出存取群組中的服務 ID。

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有服務 ID：

```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

將服務 ID 新增至存取群組。

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 新增至存取群組 `example_group`：

```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

從存取群組移除服務 ID。

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

從所有存取群組移除服務 ID。

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除服務 ID `example-service`：

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

列出存取群組的原則。

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 的所有原則：

```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

顯示存取群組原則的詳細資料。

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 之原則 `51b9717e-76b0-4f6a-bda7-b8132431f926` 的詳細資料：

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

建立存取群組原則。

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>-roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。此選項與 '--file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔建立存取群組原則：

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

針對 `us-south` 地區中 GUID 為 `d161aeea-fd02-40f8-a487-df1998bd69a9` 之 `sample-service` 實例的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

更新存取群組原則。

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>--roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。此選項與 '--file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

以原則 JSON 檔案中的原則來更新存取群組原則：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

更新存取群組原則，以針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

更新存取群組原則，以針對 `us-south` 地區中 GUID 為 `d161aeea-fd02-40f8-a487-df1998bd69a9` 之 `sample-service` 實例的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

更新存取群組原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新存取群組原則，以針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

更新存取群組原則，以針對具有 ID `dda27e49d2a1efca58083a01dfde18f6` 的資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

刪除存取群組原則。

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group` 的原則 `51b9717e-76b0-4f6a-bda7-b8132431f926`：
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
