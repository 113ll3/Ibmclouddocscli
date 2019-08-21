---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}

# IAM アクセス、 API キー、サービス ID、およびアクセス・グループの管理
{: #ibmcloud_commands_iam}

以下のコマンドを使用して、API キー、サービス ID、アクセス・グループ、ならびにユーザー、サービス、およびアクセス・グループの許可ポリシーを管理します。
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

すべてのサービス ID をリストします。
```
ibmcloud iam service-ids [--uuid] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>サービス ID の UUID のみを表示します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

現行アカウントに含まれているすべてのサービス ID の UUID をリストします。
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

サービス ID の詳細を表示します。
```
ibmcloud iam service-id (NAME|UUID) [--uuid] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>--uuid</dt>
  <dd>サービス ID の UUID を表示します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

サービス ID `sample-test` の詳細を表示します。
```
ibmcloud iam service-id sample-test
```
{: codeblock}

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` の詳細を表示します。
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

サービス ID を作成します。
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前</dd>
  <dt>-d, --description</dt>
  <dd>サービス ID の説明</dd>
  <dt>--lock</dt>
  <dd>作成時にサービス ID をロックします</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

サービス名 `sample-test` と説明 `hello, world!` でサービス ID を作成します。
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

サービス名 `sample-test` と説明 `hello, world!` で、ロックされたサービス ID を作成します。
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

サービス ID を更新します。
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-n, --name</dt>
  <dd>サービスの新しい名前</dd>
  <dt>-d, --description</dt>
  <dd>サービスの新しい説明</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新します</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID `sample-test` を `sample-test-2` に名前変更します。
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

サービス `sample-test` の説明を更新します。
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` を `sample-test-3` に名前変更し、説明も新しくします。。
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

サービス ID を削除します。
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID `sample-teset` を削除します。
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` を削除します。
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

サービス ID をロックします。
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにロックします</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID `sample-teset` をロックします。
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` をロックします。
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

サービス ID をアンロックします。
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにアンロックします</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID `sample-teset` をアンロックします。
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` をアンロックします。
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

すべての {{site.data.keyword.cloud_notm}} プラットフォーム API キーをリストします。
```
ibmcloud iam api-keys [--output FORMAT]
```
{: codeblock}

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

{{site.data.keyword.cloud_notm}} プラットフォーム API キーを作成します。
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock] [--output FORMAT]
```

API キーを使用した {{site.data.keyword.cloud_notm}} CLI ログインの使用時には、`control.softlayer.com` 上にある従来の SL API キーを処理しません。 API キーを使用した {{site.data.keyword.cloud_notm}} CLI ログインには、[cloud.ibm.com](https://cloud.ibm.com/registration){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") でインフラストラクチャーが管理されている、アップグレード済みの {{site.data.keyword.cloud_notm}} アカウントが必要です。
{: note}

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>作成する API キーの名前。</dd>
<dt>-d <i>DESCRIPTION</i> (オプション)</dt>
<dd>API キーの説明</dd>
<dt>--file <i>FILE</i></dt>
<dd>指定されたファイルに API キー情報を保存します。</dd>
<dt>--lock</dt>
<dd>作成時に API キーをロックします。</dd>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

API キーを作成し、ファイルに保存します。
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

"test-key" という名前のロックされた API キーを作成します。
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

{{site.data.keyword.cloud_notm}} プラットフォーム API キーを更新します。
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>更新する API キーの古い名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>更新する API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-n <i>NAME</i> (オプション)</dt>
<dd>API キーの新しい名前</dd>
<dt>-d <i>DESCRIPTION</i> (オプション)</dt>
<dd>API キーの新しい説明</dd>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

API キーの説明を更新します。
```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

{{site.data.keyword.cloud_notm}} プラットフォーム API キーを削除します。
```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>削除する API キーの名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>削除する API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-f, --force</dt>
<dd>確認なしで削除を強制します。</dd>
</dl>

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

プラットフォーム API キーをロックします。
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>ロックする API キーの名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>ロックする API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-f, --force</dt>
<dd>確認なしでロックを強制します。</dd>
</dl>

<strong>例</strong>:

API キー test-api-key をロックします。
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

確認を求めずに、指定された UUID の API キーをロックします。
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}s

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

プラットフォーム API キーをアンロックします。
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>アンロックする API キーの名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>アンロックする API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-f, --force</dt>
<dd>確認なしでアンロックを強制します。</dd>
</dl>

<strong>例</strong>:

API キー test-api-key をアンロックします。
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

確認を求めずに、指定された UUID の API キーをアンロックします。
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

サービスのすべての API キーをリストします。
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにサービス API キーを表示します</dd>
</dl>

<strong>例</strong>:

サービス `sample-service` のすべての API キーをリストします
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

サービス API キーの詳細をリストします。
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>--uuid</dt>
  <dd>サービス API キーの UUID を表示します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにサービス API キーを表示します</dd>
</dl>

<strong>例</strong>:

サービス `sample-service` のサービス API キー `sample-key` の詳細を表示します
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

サービス API キーを作成します。
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [--output FORMAT] [-f, --force] [--lock]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス ID または新しく作成されるサービス API キーの名前</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-d, --description</dt>
  <dd>API キーの説明</dd>
  <dt>--file</dt>
  <dd>指定されたファイルに API キー情報を保存します。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに作成を強制します</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス `sample-service` のサービス API キー `sample-key` を作成します。
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

サービス API キーを更新します。
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-n, --name</dt>
  <dd>サービスAPI キーの新しい名前</dd>
  <dt>-d, --description</dt>
  <dd>サービス API キーの新しい説明</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新します</dd>
</dl>

<strong>例</strong>:

サービス API キー `sample-key` を `new-sample-key` に名前変更します
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

サービス API キーを削除します。
```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

サービス ID `sample-service` のサービス API キー `sample-key` を削除します
```
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

サービス API キーをロックします。
```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにロックします</dd>
</dl>

<strong>例</strong>:

サービス ID `sample-service` のサービス API キー `sample-key` をロックします
```
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

サービス API キーをアンロックします。
```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにアンロックします</dd>
</dl>

<strong>例</strong>:

サービス ID `sample-service` のサービス API キー `sample-key` をアンロックします
```
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

ユーザーのポリシーをリストします
```
ibmcloud iam user-policies USER_NAME [--output FORMAT]
```

<strong>前提条件</strong>:  エンドポイント、ログイン、ターゲットのアカウント

<strong>コマンド・オプション</strong>:
<dl>
<dt>USER_NAME (必須)</dt>
<dd>ポリシーが属するユーザー名</dd>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:
 
ユーザー `name@example.com` のポリシーをリストします
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

ユーザー・ポリシーの詳細を表示します。
```
ibmcloud iam user-policy USER_NAME POLICY_ID [--output FORMAT]
```

<strong>前提条件</strong>:  エンドポイント、ログイン、ターゲットのアカウント

<strong>コマンド・オプション</strong>:
<dl>
<dt>USER_NAME (必須)</dt>
<dd>ポリシーが属するユーザー名</dd>
<dt>POLICY_ID (必須)</dt>
<dd>ポリシーの ID</dd>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` のポリシー `0bb730daa` をリストします
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

ユーザー・ポリシーを作成します。
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
```

<strong>前提条件</strong>:  エンドポイント、ログイン、ターゲットのアカウント

<strong>コマンド・オプション</strong>:
<dl>
<dt>USER_NAME (必須)</dt>
<dd>ポリシーが属するユーザー名</dd>
<dt>--file <i>FILE</i> (オプション)</dt>
<dd>ポリシー定義の JSON ファイル</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (オプション)</dt>
<dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
<dt>--service-name <i>SERVICE_NAME</i> (オプション)</dt>
<dd>ポリシー定義のサービス名。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (オプション)</dt>
<dd>ポリシー定義のサービス・インスタンスの GUID。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--region <i>REGION</i> (オプション)</dt>
<dd>ポリシー定義の地域。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (オプション)</dt>
<dd>ポリシー定義のリソース・タイプ。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource <i>RESOURCE</i> (オプション)</dt>
<dd>ポリシー定義のリソース。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (オプション)</dt>
<dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file`、`--resource` および `--resource-group-id` フラグと同時に指定することはできません。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (オプション)</dt>
<dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file`、`--resource` および `--resource-group-name` フラグと同時に指定することはできません。</dd>
<dt>--account-management (オプション)</dt>
<dd>すべてのアカウント管理サービスにアクセス権限を付与します。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

ポリシー JSON ファイル `policy.json` から、ユーザー `name@example.com` のユーザー・ポリシーを作成します。
```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

`name@example.com` に、すべての `sample-service` リソースの `Administrator` 役割を与えます。
```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`name@example.com` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` のサンプル・サービス・インスタンスのリソース `key123` の `Editor` 役割を与えます。
```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`name@example.com` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えます。
```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`name@example.com` に、 リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

`name@example.com` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

ユーザー・ポリシーを更新します。
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
```

<strong>前提条件</strong>:  エンドポイント、ログイン、ターゲットのアカウント

<strong>コマンド・オプション</strong>:
<dt>USER_NAME (必須)</dt>
<dd>ポリシーが属するユーザー名</dd>
<dt>POLICY_ID (必須)</dt>
<dd>更新するポリシーの ID</dd>
<dt>--file <i>FILE</i> (オプション)</dt>
<dd>ポリシー定義の JSON ファイル</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (オプション)</dt>
<dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
<dt>--service-name <i>SERVICE_NAME</i> (オプション)</dt>
<dd>ポリシー定義のサービス名。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (オプション)</dt>
<dd>ポリシー定義のサービス・インスタンスの GUID。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--region <i>REGION</i> (オプション)</dt>
<dd>ポリシー定義の地域。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (オプション)</dt>
<dd>ポリシー定義のリソース・タイプ。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource <i>RESOURCE</i> (オプション)</dt>
<dd>ポリシー定義のリソース。これは、`--file` フラグと同時に指定することはできません。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (オプション)</dt>
<dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file`、`--resource` および `--resource-group-id` フラグと同時に指定することはできません。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (オプション)</dt>
<dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file`、`--resource` および `--resource-group-name` フラグと同時に指定することはできません。</dd>
<dt>--account-management (オプション)</dt>
<dd>すべてのアカウント管理サービスにアクセス権限を付与します。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

JSON ファイル内のポリシーによってユーザー・ポリシーを更新します
```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

`name@example.com` に、すべての `sample-service` リソースの `Administrator` 役割を与えるようにユーザー・ポリシーを更新します
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

`name@example.com` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` のサンプル・サービス・インスタンスのリソース `key123` の `Editor` 役割を与えるように、ユーザー・ポリシーを更新します。
```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`name@example.com` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えるようにユーザー・ポリシーを更新します
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`name@example.com` に、 リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えるようにユーザー・ポリシーを更新します
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

`name@example.com` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えるようにユーザー・ポリシーを更新します
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

ユーザー・ポリシーを削除します
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>前提条件</strong>:  エンドポイント、ログイン、ターゲットのアカウント

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認を求めずにユーザー・ポリシーを削除します</dd>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` のポリシー `user-policy-id` を削除します。
```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

確認を求めずに、ユーザー `name@example.com` のポリシー `user-policy-id` を削除します。
```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

指定したサービスのすべてのサービス・ポリシーをリストします。
```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID (必須)</dt>
  <dd>サービス ID の名前または UUID</dd>
  <dt>--output FORMAT</dt>
  <dd>サービス・ポリシーの出力形式を指定します。現在、JSON のみがサポートされています。</dd>
  <dt>-f, --force (オプション)</dt>
  <dd>確認を求めずにサービス・ポリシーを表示します</dd>
</dl>

<strong>例</strong>:

サービス `test` のポリシーをリストします
```
ibmcloud iam service-policies test
```

サービス `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` のポリシーをリストします
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

サービス・ポリシーの詳細を表示します。
```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID (必須)</dt>
  <dd>サービス ID の名前または UUID</dd>
  <dt>POLICY_ID (必須)</dt>
  <dd>サービス・ポリシーの ID<dd>
  <dt>--output FORMAT</dt>
  <dd>サービス・ポリシーの出力形式を指定します。現在、JSON のみがサポートされています。</dd>
  <dt>-f, --force (オプション)</dt>
  <dd>確認を求めずにサービス・ポリシーを表示します</dd>
</dl>

<strong>例</strong>:

サービス `test` のポリシー `140798e2-8ea7db3` を表示します
```
ibmcloud iam service-policies test 140798e2-8ea7db3
```

サービス `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` のポリシー `140798e2-8ea7db3` を表示します
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

サービス・ポリシーを作成します。
```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID (必須)</dt>
  <dd>サービス ID の名前または UUID</dd>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル。 このオプションは、`-r, --roles`、`--service-name`、`--service-instance`、`--region`、`--resource-type`、`--resource`、`--resource-group-name`、`--resource-group-id` フラグと同時に指定することはできません。</dd>
  <dt>-r, --roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>--service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>--resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>--resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>--resource-group-name</dt>
  <dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file` および `--resource-group-id` と同時に指定することはできません。</dd>
  <dt>--resource-group-id </dt>
  <dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、`--file` および `--resource-group-name` と同時に指定することはできません。</dd>
  <dt>--account-management (オプション)</dt>
  <dd>すべてのアカウント管理サービスにアクセス権限を付与します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにサービス・ポリシーを作成します</dd>
</dl>

<strong>例</strong>:

サービス `test` のサービス・ポリシーを JSON ファイルから作成します
```
ibmcloud iam service-policy-create test --file @policy.json
```

サービス `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` のサービス・ポリシーを JSON ファイルから作成します
```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

サービス `test` に、すべてのアカウント管理サービスに対する `Administrator` 役割を付与します。
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

サービス `test` に、アカウント内のすべてのリソースに対する `Viewer` 役割を付与します。
```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

サービス・ポリシーを更新します。
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID (必須)</dt>
  <dd>サービス ID の名前または UUID</dd>
  <dt>POLICY_ID (必須)</dt>
  <dd>サービス・ポリシーの ID<dd>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル。 このオプションは、`-r, --roles`、`--service-name`、`--service-instance`、`--region`、`--resource-type`、`--resource`、`--resource-group-name`、`resource-group-id` フラグと同時に指定することはできません。</dd>
  <dt>-r, --roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>-resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>-resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、`--file` フラグと同時に指定することはできません。</dd>
  <dt>--resource-group-name</dt>
  <dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file` および `--resource-group-id` と同時に指定することはできません。</dd>
  <dt>--resource-group-id </dt>
  <dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、`--file` および `--resource-group-name` と同時に指定することはできません。</dd>
  <dt>--account-management (オプション)</dt>
  <dd>すべてのアカウント管理サービスにアクセス権限を付与します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにサービス・ポリシーを更新します</dd>
</dl>

<strong>例</strong>:

サービス `test` のサービス・ポリシー `140798e2-8ea7db3` を JSON ファイルから更新します
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

サービス `test` のサービス・ポリシー `140798e2-8ea7db3` を JSON ファイルから更新します
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

サービス `test` に、すべてのアカウント管理サービスに対する `Administrator` 役割を付与するように、サービス・ポリシー `140798e2-8ea7db3` を更新します。
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

サービス `test` に、アカウント内のすべてのリソースに対する `Viewer` 役割を付与するように、サービス・ポリシー `140798e2-8ea7db3` を更新します。
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

サービス・ポリシーを削除します。
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ID (必須)</dt>
  <dd>サービス ID の名前または UUID</dd>
  <dt>POLICY_ID (必須)</dt>
  <dd>サービス・ポリシーの ID<dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

サービス `test` のポリシー `140798e2-8ea7db3` を削除します。
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```

サービス `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` のポリシー `140798e2-8ea7db3` を削除します。
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

現行セッションの OAuth トークンを取得して表示します。
```
ibmcloud iam oauth-tokens [--output FORMAT]
```
{: codeblock}

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

OAuth トークンを更新して表示します。
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

プラットフォームおよびサービスの定義済み役割をリストします。
```
ibmcloud iam roles [--service SERVICE_NAME] [--output FORMAT]
```
{: codeblock}

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--service SERVICE_NAME</dt>
  <dd>サービスの名前、指定されていない場合はプラットフォームの定義済み役割のみをリストします。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

プラットフォーム役割をリストします
```
ibmcloud iam roles
```

JSON 形式でサービス `cloudantnosql` の役割をリストします。
```
ibmcloud iam roles --service cloudantnosql --output JSON
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

パブリック IBMid を専用の非 IBMid から切断します。
```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認なしで切断を強制します</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

特定のサービス・インスタンスが別のサービス・インスタンスへアクセスできるようにするための許可ポリシーを作成します。

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-type RESOURCE_TYPE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME] [--target-resource-type RESOURCE_TYPE | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--output FORMAT]
```

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>アクセスを許可されるソース・サービス。</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>ソース・サービスがアクセスを許可されるターゲット・サービス。</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>ソース・サービスのアクセス権限を提供する役割。</dd>  
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>ソース・サービス・インスタンス名。`--source-service-instance-id` と同時に指定することはできません。 指定されない場合、ソース・サービスのすべてのインスタンスがアクセスを許可されます。</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>ソース・サービス・インスタンス ID。`--source-service-instance-name` と同時に指定することはできません。 指定されない場合、ソース・サービスのすべてのインスタンスがアクセスを許可されます。</dd>
  <dt>--source-resource-type</dt>
  <dd>ソース・サービスのリソース・タイプ</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>ターゲット・サービス・インスタンス名。`--target-service-instance-id` と同時に指定することはできません。 指定されない場合、ターゲット・サービスのすべてのインスタンスがアクセスを許可されます。</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>ターゲット・サービス・インスタンス ID。`--target-service-instance-name` と同時に指定することはできません。 指定されない場合、ターゲット・サービスのすべてのインスタンスがアクセスを許可されます。</dd>
  <dt>--target-resource-type</dt>
  <dd>ターゲット・サービスのリソース・タイプ</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

許可ポリシーを削除します。
```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>削除する許可ポリシーの ID。</dd>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します。</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

許可ポリシーの詳細を表示します。
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID [--output FORMAT]
```

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>表示する許可ポリシーの ID。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl> 

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

現行アカウントの許可ポリシーをリストします。
```
ibmcloud iam authorization-policies [--output FORMAT]
```
{: codeblock}

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
   </dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

現行アカウントのアクセス・グループをリストします。
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-u</dt>
  <dd>ユーザーが所属するアクセス・グループをリストします。 このフラグと '-s' を同時に指定することはできません。</dd>
  <dt>-s</dt>
  <dd>サービス ID が所属するアクセス・グループをリストします。 このフラグと '-u' を同時に指定することはできません。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

すべてのアクセス・グループをリストします
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

アクセス・グループの詳細を表示します。
```
ibmcloud iam access-group GROUP_NAME [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-id</dt>
  <dd>ID のみを表示します</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` の詳細を表示します。
```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

アクセス・グループを作成します。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>アクセス・グループの説明</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を作成します。
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

アクセス・グループを更新します。
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>新規アクセス・グループ名</dd>
  <dt>-d, --description</dt>
  <dd>新規説明</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を `hello_world_group` に名前変更します。
```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

アクセス・グループを削除します

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
  <dt>-r, --recursive</dt>
  <dd>アクセス・グループとそのメンバーを削除します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を削除します。
```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

アクセス・グループ内のユーザーをリストします。
```
ibmcloud iam access-group-users GROUP_NAME [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` 内のすべてのユーザーをリストします。
```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

ユーザーをアクセス・グループに追加します。
```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をアクセス・グループ `example_group` に追加します。
```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

アクセス・グループからユーザーを削除します。
```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をアクセス・グループ `example_group` から削除します。
```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

すべてのアクセス・グループからユーザーを削除します。
```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をすべてのアクセス・グループから削除します。
```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

アクセス・グループ内のサービス ID をリストします。
```
ibmcloud iam access-group-service-ids GROUP_NAME [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` 内のすべてのサービス ID をリストします。
```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

サービス ID をアクセス・グループに追加します。
```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

サービス ID `example-service` をアクセス・グループ `example_group` に追加します。
```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

アクセス・グループからサービス ID を削除します。
```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

サービス ID `example-service` をアクセス・グループ `example_group` から削除します。
```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

サービス ID をすべてのアクセス・グループから削除します。
```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

サービス ID `example-service` をすべてのアクセス・グループからから削除します。

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

アクセス・グループのポリシーをリストします。
```
ibmcloud iam access-group-policies GROUP_NAME [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のすべてのポリシーをリストします。
```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

アクセス・グループ・ポリシーの詳細を表示します。
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のポリシー `51b9717e-76b0-4f6a-bda7-b8132431f926` の詳細を表示します
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

アクセス・グループ・ポリシーを作成します。
```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル</dd>
  <dt>-roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource-group-name</dt>
  <dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file` および `--resource-group-id` と同時に指定することはできません。</dd>
  <dt>-resource-group-id</dt>
  <dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、`--file` および `--resource-group-name` と同時に指定することはできません。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

JSON ファイルからアクセス・グループ・ポリシーを作成します。
```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

`example_group` に、すべての `sample-service` リソースの `Administrator` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`example_group` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` の `sample-service` インスタンスのリソース `key123` の `Editor` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`example_group` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` に、 リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

`example_group` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

アクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル</dd>
  <dt>--roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、`ibmcloud iam roles --service SERVICE_NAME` を実行してください。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、`--file` と同時に指定することはできません。</dd>
  <dt>-resource-group-name</dt>
  <dd>リソース・グループの名前。 `*` はすべてのリソース・グループを表します。 このオプションは、 `--file` および `--resource-group-id` と同時に指定することはできません。</dd>
  <dt>-resource-group-id</dt>
  <dd>リソース・グループの ID。 `*` はすべてのリソース・グループを表します。 このオプションは、`--file` および `--resource-group-name` と同時に指定することはできません。</dd>
  <dt>--output FORMAT</dt>
  <dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

ポリシー JSON ファイル内のもので、アクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

`example_group` に、すべての `sample-service` リソースの `Administrator` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

`example_group` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` の `sample-service` インスタンスのリソース `key123` の `Editor` 役割を与えるように、アクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

`example_group` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` に、リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

`example_group` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

アクセス・グループ・ポリシーを削除します。
```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のポリシー `51b9717e-76b0-4f6a-bda7-b8132431f926` を削除します。
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
