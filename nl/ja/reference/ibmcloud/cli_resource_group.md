---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# リソースおよびリソース・グループの処理
{: #ibmcloud_commands_resource}

リソース・グループは、アカウント・リソースをカスタマイズ可能なグループに編成するための方法です。 以下のコマンドを使用して、リソース・グループ内の {{site.data.keyword.cloud}} リソースを管理します。
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

リソース・グループをリストします。
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--default</dt>
  <dd>現行アカウントのデフォルト・グループを取得します。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

現在のターゲット・アカウントのすべてのリソース・グループをリストします
```
ibmcloud resource groups
```
{: codeblock}

現在のターゲット・アカウントのデフォルト・グループをリストします
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

リソース・グループの詳細を表示します
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>リソース・グループの名前</dd>
  <dt>--id</dt>
  <dd>ID のみを表示します</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

リソース・グループ `example-group` を表示します
```
ibmcloud resource group example-group
```
{: codeblock}

リソース・グループ `example-group` の ID のみを表示します
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

リソース・グループを作成します。
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>リソース・グループの名前</dd>
</dl>

<strong>例</strong>:

リソース・グループ `example-group` を作成します
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

既存のリソース・グループを更新します
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] 
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>ターゲット・リソース・グループの名前</dd>
  <dt>-n, --name</dt>
  <dd>リソース・グループの新しい名前</dd>
  <dt>-f</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

リソース・グループ `example-group` を `trial-group` に名前変更します
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

すべての割り当て量定義をリストします。
```
ibmcloud resource quotas
```
{: codeblock}

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

すべての割り当て量定義をリストします
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

割り当て量定義の詳細を表示します。
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>割り当て量の名前</dd>
</dl>

<strong>例</strong>:

割り当て量 `free` の詳細を表示します
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloud Foundry サービス・インスタンスをリソース・グループにマイグレーションします
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>前提条件</strong>: ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME または SERVICE_INSTANCE_ID (必須)</dt>
  <dd>サービス・インスタンスの名前または ID</dd>
  <dt>--resource-group-name</dt>
  <dd>リソース・グループの名前。 このオプションは、「--resource-group-id」と同時に指定することはできません。 これらのどれも指定されない場合のデフォルトは、現在ターゲットになっているリソース・グループです。</dd>
  <dt>--resource-group-id</dt>
  <dd>リソース・グループの ID。 このオプションは、「--resource-group-name」と同時に指定することはできません。 これらのどれも指定されない場合のデフォルトは、現在ターゲットになっているリソース・グループです。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにマイグレーションします</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

サービス・インスタンスをリストします。
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>従属サービスの名前</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>場所を基準にフィルター操作します</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>インスタンスのタイプ。 指定されない場合は、`service_instance` タイプが使用されます。すべてのタイプのインスタンスをリストするには、all を使用します。</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>リソース・グループ名</dd>
  <dt>--long</dt>
  <dd>出力に追加フィールドを表示します</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。 </dd>
</dl>

<strong>例</strong>:

サービス `test-service` のサービス・インスタンスをリストします。
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

サービス・インスタンスの詳細を表示します。

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)。ID と同時に指定することはできません。</dt>
  <dd>サービス・インスタンスの名前</dd>
  <dt>ID (必須)。NAME と同時に指定することはできません。</dt>
  <dd>サービス・インスタンスの ID</dd>
  <dt>--location</dt>
  <dd>場所を基準にフィルター操作します</dd>
  <dt>--id</dt>
  <dd>サービス・インスタンスの ID を表示します</dd>
  <dt>--output</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

サービス・インスタンス `my-service-instance` の詳細を表示します
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

サービス・インスタンスを作成します。
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス・インスタンスの名前</dd>
  <dt>SERVICE_NAME または SERVICE_ID (必須)</dt>
  <dd>サービスの名前または ID。 サービス・オファリングをリストするには、`ibmcloud catalog service-marketplace`[コマンド](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_catalog#ibmcloud_catalog_service_marketplace)を使用します。</dd>
  <dt>SERVICE_PLAN_NAME または SERVICE_PLAN_ID (必須)</dt>
  <dd>サービス・プランの名前または ID</dd>
  <dt>LOCATION (必須)</dt>
  <dd>サービス・インスタンスを作成するターゲットの場所または環境</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>デプロイメントの名前</dd>
  <dt>-p, --parameters <i>@JSONFILE または JSON_STRING</i></dt>
  <dd>サービス・インスタンスを作成するパラメーターの JSON ファイルまたは JSON 文字列</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>リソース・グループ名</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>サービス・エンドポイントのタイプ。 指定可能な値は「public」、「private」、「public-and-private」です。</dd>
</dl>

<strong>例</strong>:

場所 `eu-gb` にサービス `test-service` のサービス・プラン `test-service-plan` を使用してサービス・インスタンス `my-service-instance` を作成します。
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

サービス・インスタンスを更新します。
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス・インスタンスの名前。ID と同時に指定することはできません。</dd>
  <dt>ID (必須)</dt>
  <dd>サービス・インスタンスの ID。NAME と同時に指定することはできません。</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>新規サービス・インスタンス名</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>新規サービス・プラン ID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>サービス・インスタンスを作成するパラメーターの JSON ファイルまたは JSON 文字列</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>リソース・グループ名</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>サービス・エンドポイントのタイプ。 指定可能な値は「public」、「private」、「public-and-private」です。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

サービス・インスタンス `my-service-instance` を更新し、その名前を `new-service-instance` に変更します
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

サービス・インスタンスを削除します。
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス・インスタンスの名前。ID と同時に指定することはできません。</dd>
  <dt>ID (必須)</dt>
  <dd>サービス・インスタンスの ID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
  <dt>--recursive</dt>
  <dd>従属リソースをすべて削除します</dd>
</dl>

<strong>例</strong>:

リソース・サービス・インスタンス `my-service-instance` を削除します
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

サービス別名へのバインディングを表示します。
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ALIAS (必須)</dt>
  <dd>サービス別名</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

サービス別名 `my-service-alias` へのリソース・バインディングを表示します
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

サービス・バインディングの詳細を表示します。
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry アプリケーション名</dd>
  <dt>--id</dt>
  <dd>ID のみを表示します。 このサービス・バインディングの他の出力はすべて抑制されます。 このオプションは、「--output」と同時に指定することはできません。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

サービス別名 `my-service-alias` とアプリ `my-app` の間のサービス・バインディングの詳細を表示します
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

サービス・バインディングを作成します。
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (必須)</dt>
  <dd>サービス別名</dd>
  <dt>APP_NAME (必須)</dt>
  <dd>CloudFoundry アプリケーション名</dd>
  <dt>ROLE_NAME (必須)</dt>
  <dd>ユーザー役割の名前</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>役割が属しているサービス ID の名前または UUID</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>サービス・エンドポイントのタイプ。 指定可能な値は、「public」および「private」です。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに作成を強制します</dd>
</dl>

<strong>例</strong>:

`Administrator` の役割によってサービス別名 `my-service-alias` とアプリ `my-app` の間のサービス・バインディングを作成します
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

サービス・バインディングを削除します。
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (必須)</dt>
  <dd>サービス別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry アプリケーション名</dd>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
</dl>

<strong>例</strong>:
サービス別名 `my-service-alias` とアプリ `my-app` の間のサービス・バインディングを削除します
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

サービス・インスタンスまたはサービス別名のサービス・キーをリストします。
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>サービス・インスタンス ID</dd>
  <dt>--instance-name</dt>
  <dd>サービス・インスタンス名</dd>
  <dt>--alias-id</dt>
  <dd>サービス別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>サービス別名</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

サービス・インスタンス `my-service-instance` のサービス・キーをリストします
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

サービス・キー名の最初の *n* 文字が、指定された KEY_NAME と一致する、任意の数のサービス・キーの詳細を表示します。
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME</dt>
  <dd>キーの名前</dd>
  <dt>ID</dt>
  <dd>キーの ID</dd>
  <dt>-g</dt>
  <dd>リソース・グループ名</dd>
  <dt>--id</dt>
  <dd>サービス・キーの ID を表示します。 このオプションは、「--output」と同時に指定することはできません。</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>リソース・グループ名</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

サービス・キー `my-service-key` の詳細を表示します
```
ibmcloud resource service-key my-service-key
```
<strong>例</strong>:
ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79` のサービス・キーの詳細を表示します。

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

サービス・キーを作成します。
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>キーの名前</dd>
  <dt>ROLE_NAME (必須)</dt>
  <dd>ユーザー役割の名前</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>サービス・インスタンス ID</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>サービス・インスタンス名</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>サービス別名 ID</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>サービス別名</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>役割が属しているサービス ID の名前または UUID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>リソース・グループ名</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>サービス・エンドポイントのタイプ。 指定可能な値は、「public」および「private」です。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに作成を強制します</dd>
</dl>

<strong>例</strong>:

役割 `Administrator` を使用して、サービス・インスタンス `my-service-instance` に対して `my-service-key` という名前のサービス・キーを作成します。
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

サービス・キーを更新します。
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>キーの名前または ID</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>キーの新しい名前</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>キーが属するリソース・グループの ID</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

`my-service-key` という名前のサービス・キーを更新し、新しい名前 `my-service-key-2` を付けます
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

サービス・キーを削除します。
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>キーの名前または ID</dd>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
</dl>

<strong>例</strong>:

サービス・キー `my-service-key` を削除します
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

サービス・インスタンスの別名をリストします。
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>従属サービス・インスタンスの ID</dd>
  <dt>--instance-name</dt>
  <dd>従属サービス・インスタンスの名前</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

サービス・インスタンス `my-service-instance` のサービス別名をリストします
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

サービス別名の詳細を表示します。
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名の名前</dd>
  <dt>--id</dt>
  <dd>指定されたサービス別名の ID のみを表示してください。 この別名の他の出力はすべて抑制されます。 このオプションは、「--output」と同時に指定することはできません。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>--output value  出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

サービス別名 `my-service-alias` の詳細を表示します
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

サービス・インスタンスの別名を作成します。
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名の名前</dd>
  <dt>--instance-id</dt>
  <dd>従属サービス・インスタンスの ID</dd>
  <dt>--instance-name</dt>
  <dd>従属サービス・インスタンスの名前</dd>
  <dt>-s</dt>
  <dd>別名が作成されるスペースの名前。 デフォルトは現行のスペースです。</dd>
  <dt>-t, --tags</dt>
  <dd>タグのリスト。</dd>
  <dt>-p, --parameters</dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列。</dd>
</dl>

<strong>例</strong>:

サービス・インスタンス `my-service-instance` のサービス別名 `my-service-alias` を作成します。
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

サービス別名を更新します。
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名の名前</dd>
  <dt>-n, --name</dt>
  <dd>サービス別名の新しい名前。</dd>
  <dt>-t, --tags</dt>
  <dd>タグのリスト。</dd>
  <dt>-p, --parameters</dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列。</dd>
  <dt>-f, --force</dt>
  <dd>ユーザーの確認を求めずに更新を強制します。</dd>
</dl>

<strong>例</strong>:

サービス別名 `my-service-alias` を更新し、その名前を `new-service-alias` に変更します
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

サービス別名を削除します。
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名の名前</dd>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
</dl>

<strong>例</strong>:

サービス別名 `my-service-alias` を削除します
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

Lucene 照会構文を使用してリソースを検索します。
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>開始リソース位置番号</dd>
  <dt>-l, -limit</dt>
  <dd>返されるリソースの数 (最大 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>ソート基準のプロパティー。 受け入れられる入力は、`name`、`family`、`region`、`type`、`crn` です。</dd>
  <dt>-p, --provider</dt>
  <dd>クラシック・インフラストラクチャー・リソースを表示します (許可される値は classic-infrastructure のみです)</dd>
</dl>

<strong>検索できる属性</strong>:
以下の属性を検索できます。

<dl>
  <dt>name</dt>
  <dd>リソースのユーザー定義名。</dd>
  <dt>地域 (region)</dt>
  <dd>リソースがプロビジョンされている地理的位置。 例: us-south、us-east、au-syd、eu-gb、eu-de、jp-tok。</dd>
  <dt>service_name</dt>
  <dd>「ibmcloud catalog service-marketplace」の出力の名前列に表示されるサービスの名前。</dd>
  <dt>family</dt>
  <dd>リソースが属するクラウド・コンポーネント。 許可される値は、cloud_foundry、containers、resource_controller、vmware、ims です。</dd>
  <dt>organization_id</dt>
  <dd>Cloud Foundry 組織 GUID。</dd>
  <dt>doc.space_id</dt>
  <dd>Cloud Foundry スペース GUID。</dd>
  <dt>doc.resource_group_id</dt>
  <dd>リソース・グループの ID。</dd>
  <dt>type</dt>
  <dd>リソース・タイプ。 許可される値は、k8-cluster、cf-service-instance、cf-user-provided-service-instance、cf-organization、cf-service-binding、cf-space、cf-application、resource-instance、resource-alias、resource-binding、resource-group、vmware-solutions、cloud-objects-storage-infrastructure、block-storage、file-storage、cloud-backup です。</dd>
  <dt>creation_date</dt>
  <dd>リソースが作成された日付。</dd>
  <dt>modification_date</dt>
  <dd>リソースの最終変更日。 形式は、yyyy-mm-ddThh:mm:ssZ です。 </dd>
  <dt>_objectType</dt>
  <dd>クラシック・インフラストラクチャー・リソースのタイプ。 許可される値は、SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall、SoftLayer_Virtual_Guest です。 </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>リソースにアタッチされているタグ。 クラシック・インフラストラクチャー・リソースにアタッチされているタグを検索する場合は、tagReferences.tag.name を使用します。 </dd> 
</dl>

<strong>例</strong>:

指定したテキストで始まる名前の Cloud Foundry アプリを検索します。
```
ibmcloud resource search "name:my* AND type:cf-application"
```

指定したサービス名の Cloud Foundry サービス・インスタンスを検索します。
```
ibmcloud resource search "service_name:messagehub AND type:cf-service-instance"
```

指定した ID を持つ組織内の Cloud Foundry サービス・バインディングを検索します。
```
ibmcloud resource search "organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding"
```

指定した 2 つの地域のどちらかにある、指定した名前の Cloud Foundry スペースを検索します。
```
ibmcloud resource search "name:dev AND type:cf-space AND region:(us-south OR eu-gb)"
```

指定した ID の Cloud Foundry スペースの中で、名前に dev が入ったリソースを検索します。
```
ibmcloud resource search "name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7"
```

指定した場所 (つまり us-south 地域) で、リソース・コントローラーのリソースを検索します。
```
ibmcloud resource search "region:us-south AND family:resource_controller"
```

指定した ID を持つリソース・グループ内のリソースまたは別名を検索します。
```
ibmcloud resource search "(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)"
```

デフォルトの名前を持つリソース・グループを検索します。
```
ibmcloud resource search "name:default AND type:resource-group"
```

指定したサービス名のリソース・バインディングを検索します。
```
ibmcloud resource search "service_name:cloud-object-storage AND type:resource-binding"
```

指定したクラウド・リソース名 (CRN) を持つリソースを検索します。
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

指定したタグを持つリソースを検索します。
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

指定した ID を持つクラシック・インフラストラクチャー仮想ゲスト・リソースを検索します (-p classic-infrastructure が指定されている場合のみ)。
```
ibmcloud resource search "id:12345678 _objectType:SoftLayer_Virtual_Guest"
```
{: codeblock}

指定したタグ名を持つクラシック・インフラストラクチャー・ハードウェア・リソースを検索します (-p classic-infrastructure が指定されている場合のみ)。
```
ibmcloud resource search "tagReferences.tag.name:name _objectType:SoftLayer_Hardware"
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

ご使用の請求処理アカウントのすべてのタグをリストします

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>開始タグ位置番号</dd>
  <dt>-l, -limit</dt>
  <dd>返されるタグの数 (最大 1000、デフォルト 100 )</dd>
  <dt>-p; --provider</dt> 
  <dd>クラシック・インフラストラクチャーのタグを検索する場合は、classic-infrastructure を指定します</dd>
  <dt>-d, --details</dt>
  <dd>タグ付きリソースの数を表示します。</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

1 つ以上のタグをリソースにアタッチします。
```
ibmcloud resource tag-attach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-names(必須)</dt>
  <dd>タグ名のコンマ区切りリスト</dd>
  <dt>--resource-name</dt>
  <dd>タグをアタッチするリソースの名前。 クラシック・インフラストラクチャー・リソースでは、このオプションを使用できません。</dd>
  <dt>--resource-id</dt>
  <dd>タグをアタッチするリソースの CRN。クラシック・インフラストラクチャー・リソースの場合は、リソースの ID です。 `ibmcloud resource search` コマンドを使用して、リソースの CRN または ID を入手できます。</dd>
  <dt>--resource-type</dt>
  <dd>タグをアタッチするクラシック・インフラストラクチャー・リソースのリソース・タイプ。クラシック・インフラストラクチャー・リソースにタグをアタッチする場合、このパラメーターは必須です。 --resource-type に指定できる値は、SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall、SoftLayer_Virtual_Guest です。 </dd>
</dl>

<strong>例</strong>:

* タグ `MyTag` を `MyCluster` という名前の Kubernetes クラスターにアタッチするには、最初に以下のようにして、タグをアタッチしようとしているクラスターの CRN を検索します。
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  CRN をメモします。CRN は以下の例のようなストリングです。 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  タグをアタッチするには、以下のコマンドを実行します。
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* タグ `MyTag` をリソース名 `MyResource` にアタッチするには、以下のようにします。
  ```
  ibmcloud resource tag-attach --tag-name MyTag --resource-name  'MyResource'
  ```
  {: codeblock}
  
  
* タグ `MyTag` を `MyVM` という名前のクラシック・インフラストラクチャー仮想ゲストにアタッチするには、最初に以下のようにして、タグをアタッチしようとしている仮想ゲストの ID を検索します。
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  ID をメモします。ID は `48373549` のようなストリングです。

  タグをアタッチするには、以下のコマンドを実行します。
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

1 つ以上のタグをリソースから切り離します。
```
ibmcloud resource tag-detach  --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-names(必須)</dt>
  <dd>タグ名のコンマ区切りリスト</dd>
  <dt>--resource-name</dt>
  <dd>タグをデタッチするリソースの名前。 クラシック・インフラストラクチャー・リソースでは、このオプションを使用できません。</dd>
  <dt>--resource-id</dt>
  <dd>タグを切り離すリソースの CRN。クラシック・インフラストラクチャー・リソースの場合は、リソースの ID です。 `ibmcloud resource search` コマンドを使用して、リソースの CRN または ID を入手できます。</dd>
  <dt>--resource-type</dt>
  <dd>タグを切り離すクラシック・インフラストラクチャー・リソースのリソース・タイプ。クラシック・インフラストラクチャー・リソースからタグを切り離す場合、このパラメーターは必須です。 --resource-type に指定できる値は、SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall、SoftLayer_Virtual_Guest です。 </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

タグを削除します。
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>削除するタグの名前。</dd>
  <dt>-p; --provider</dt> 
  <dd>クラシック・インフラストラクチャーのタグを削除する場合は、classic-infrastructure を指定します</dd>
</dl>

タグは、リソースにアタッチされていない場合にのみ削除できます。
