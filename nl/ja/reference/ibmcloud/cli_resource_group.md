---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# リソース・グループとリソース
{: #ibmcloud_commands_resource}

リソース・グループは、アカウント・リソースをカスタマイズ可能なグループに編成するための方法です。 以下のコマンドを使用して、{{site.data.keyword.Bluemix}} リソース・グループとリソース・グループ内のリソースを管理します。
{: shortdesc}

<table summary="リソース・グループとリソースを管理するために使用できる ibmcloud コマンド。">
  <thead>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

リソース・グループをリストします。

```
ibmcloud resource groups [--default]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--default</dt>
  <dd>現行アカウントのデフォルト・グループを取得します。</dd>
</dl>

<strong>例</strong>:

現在のターゲット・アカウントのすべてのリソース・グループをリストします

```
ibmcloud resource groups
```

現在のターゲット・アカウントのデフォルト・グループをリストします

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

リソース・グループの詳細を表示します

```
ibmcloud resource group NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>リソース・グループの名前</dd>
  <dt>--id</dt>
  <dd>ID のみを表示します</dd>
</dl>

<strong>例</strong>:

リソース・グループ `example-group` を表示します

```
ibmcloud resource group example-group
```

リソース・グループ `example-group` の ID のみを表示します

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

リソース・グループを作成します

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

<strong>例</strong>:

割り当て量 `free` のリソース・グループ `example-group` を作成します。

```
ibmcloud resource group-create example-group free
```

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

既存のリソース・グループを更新します

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>ターゲット・リソース・グループの名前</dd>
  <dt>-n, --name</dt>
  <dd>リソース・グループの新しい名前</dd>
  <dt>-q, --quota</dt>
  <dd>新規割り当て量定義の名前</dd>
  <dt>-f</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

リソース・グループ `example-group` を `trial-group` に名前変更します

```
ibmcloud resource group-update example-group -n trial-group
```

リソース・グループ `example-group` の割り当て量を `free` に変更します

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

すべての割り当て量定義をリストします

```
ibmcloud resource quotas
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

すべての割り当て量定義をリストします

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

割り当て量定義の詳細を表示します

```
ibmcloud resource quota NAME
```

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

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloudfoundry サービス・インスタンスをリソース・グループにマイグレーションします

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

サービス・インスタンスをリストします

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>従属サービスの名前</dd>
  <dt>--location</dt>
  <dd>場所を基準にフィルター操作します</dd>
  <dt>--long</dt>
  <dd>出力に追加フィールドを表示します</dd>
</dl>

<strong>例</strong>:

サービス `test-service` のサービス・インスタンスをリストします。

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

サービス・インスタンスの詳細を表示します

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

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

サービス・インスタンスの作成

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス・インスタンスの名前</dd>
  <dt>SERVICE_NAME または SERVICE_ID (必須)</dt>
  <dd>サービスの名前または ID</dd>
  <dt>SERVICE_PLAN_NAME または SERVICE_PLAN_ID (必須)</dt>
  <dd>サービス・プランの名前または ID</dd>
  <dt>LOCATION</dt>
  <dd>サービス・インスタンスを作成するターゲットの場所または環境</dd>
  <dt>-t, --tags</dt>
  <dd>タグ</dd>
  <dt>-p, --parameters</dt>
  <dd>サービス・インスタンスを作成するパラメーターの JSON ファイルまたは JSON 文字列</dd>
  <dt>-d, --deployment</dt>
  <dd>デプロイメントの名前</dd>
</dl>

<strong>例</strong>:
場所 `eu-gb` にサービス `test-service` のサービス・プラン `test-service-plan` を使用してサービス・インスタンス `my-service-instance` を作成します。

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

サービス・インスタンスを更新します

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME (必須)</dt>
  <dd>サービス・インスタンスの名前。ID と同時に指定することはできません。</dd>
  <dt>ID (必須)</dt>
  <dd>サービス・インスタンスの ID。NAME と同時に指定することはできません。</dd>
  <dt>-n, --name</dt>
  <dd>新規サービス・インスタンス名</dd>
  <dt>-t, --tags</dt>
  <dd>新規タグ</dd>
  <dt>--service-plan-id</dt>
  <dd>新規サービス・プラン ID</dd>
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

サービス・インスタンスを削除します

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

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

サービス別名へのバインディングを表示します

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ALIAS (必須)</dt>
  <dd>サービス別名</dd>
</dl>

<strong>例</strong>:
サービス別名 `my-service-alias` へのリソース・バインディングを表示します

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

サービス・バインディングの詳細を表示します

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry アプリケーション名</dd>
  <dt>--id</dt>
  <dd>ID のみを表示します。 このサービス・バインディングの他の出力はすべて抑制されます。</dd>
</dl>

<strong>例</strong>:
サービス別名 `my-service-alias` とアプリ `my-app` の間のサービス・バインディングの詳細を表示します

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

サービス・バインディングの作成

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (必須)</dt>
  <dd>サービス別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry アプリケーション名</dd>
  <dt>ROLE_NAME</dt>
  <dd>ユーザー役割の名前</dd>
  <dt>--service-id</dt>
  <dd>役割が属しているサービス ID の名前または UUID</dd>
  <dt>-p, --parameter</dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに作成を強制します</dd>
</dl>

<strong>例</strong>:
`Administrator` の役割によってサービス別名 `my-service-alias` とアプリ `my-app` の間のサービス・バインディングを作成します

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

サービス・バインディングの削除

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

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

サービス・インスタンスまたはサービス別名のサービス・キーをリストします

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
</dl>

<strong>例</strong>:
サービス・インスタンス `my-service-instance` のサービス・キーをリストします

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

サービス・キーの詳細を表示します

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>キーの名前</dd>
  <dt>--id</dt>
  <dd>サービス・キーの ID を表示します</dd>
</dl>

<strong>例</strong>:
サービス・キー `my-service-key` の詳細を表示します

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

サービス・キーを作成します

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>NAME</dt>
  <dd>キーの名前</dd>
  <dt>ROLE_NAME</dt>
  <dd>ユーザー役割の名前</dd>
  <dt>--instance-id</dt>
  <dd>サービス・インスタンス ID</dd>
  <dt>--instance-name</dt>
  <dd>サービス・インスタンス名</dd>
  <dt>--alias-id</dt>
  <dd>サービス別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>サービス別名</dd>
  <dt>--service-id</dt>
  <dd>役割が属しているサービス ID の名前または UUID</dd>
  <dt>-p, --parameters</dt>
  <dd>パラメーター JSON ファイルまたは JSON 文字列</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに作成を強制します</dd>
</dl>

<strong>例</strong>:
役割 `Administrator` を使用して、サービス・インスタンス `my-service-instance` に対して `my-service-key` という名前のサービス・キーを作成します。

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

サービス・キーを削除します

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>キーの名前</dd>
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

サービス・インスタンスの別名をリストします

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>従属サービス・インスタンスの ID</dd>
  <dt>--instance-name</dt>
  <dd>従属サービス・インスタンスの名前</dd>
</dl>

<strong>例</strong>:
サービス・インスタンス `my-service-instance` のサービス別名をリストします
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

サービス別名の詳細を表示します

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>ALIAS_NAME (必須)</dt>
  <dd>サービス別名の名前</dd>
  <dt>--id</dt>
  <dd>指定されたサービス別名の ID のみを表示してください。 この別名の他の出力はすべて抑制されます。</dd>
</dl>

<strong>例</strong>:
サービス別名 `my-service-alias` の詳細を表示します
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

サービス・インスタンスの別名を作成します

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

サービス別名を更新します

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

サービス別名を削除します

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
Lucene 照会構文を使用してリソースを検索します

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)]
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
</dl>

<strong>例</strong>:
指定したテキストで始まる名前の Cloud Foundry アプリケーションを検索します。

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

指定したサービス名の Cloud Foundry サービス・インスタンスを検索します。

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

指定した ID を持つ組織内の Cloud Foundry サービス・バインディングを検索します。

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

指定した 2 つの地域のどちらかにある、指定した名前の Cloud Foundry スペースを検索します。

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

指定した ID の Cloud Foundry スペースの中で、名前に dev が入ったリソースを検索します。

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

指定した場所 (つまり us-south 地域) で、リソース・コントローラーのリソースを検索します。

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

指定した ID を持つリソース・グループ内のリソースまたは別名を検索します。

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

デフォルトの名前を持つリソース・グループを検索します。

```
ibmcloud resource search 'name:default AND type:resource-group'
```

指定したサービス名のリソース・バインディングを検索します。

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

指定したクラウド・リソース名 (CRN) を持つリソースを検索します。

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

指定したタグを持つリソースを検索します。

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

すべてのタグをリストします

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>タグ・タイプ (サポートされる値: user、restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>開始リソース位置番号 (デフォルト: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>返されるリソースの数 (最大 10000) (デフォルト: 10000)</dd>
</dl>

<strong>例</strong>:

すべてのタグをリストします

```
ibmcloud resource tags
```

すべての制限付きタグをリストします

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

タグの詳細を表示します

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名。--tag-crn と同時に指定することはできません。</dd>
  <dt>--tag-crn (必須)</dt>
  <dd>タグ CRN。--tag-name と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

タグ "Ray Brown" の詳細を表示します

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

タグを作成します

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名</dd>
  <dt>--tag-type</dt>
  <dd>タグ・タイプ (サポートされる値: user、restricted。デフォルト: user)</dd>
</dl>

<strong>例</strong>:

think:2018 という名前のユーザー・タグを作成します

```
ibmcloud resource tag-create --tag-name think:2018
```

department:marketing という名前の制限付きタグを作成します

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

"Ray Brown" という名前のユーザー・タグを作成します

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

"environment:My Development" という名前の制限付きタグを作成します

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

タグを削除します

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名。--tag-crn と同時に指定することはできません。</dd>
  <dt>--tag-crn (必須)</dt>
  <dd>タグ CRN。--tag-name と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

タグ "Ray Brown" を削除します

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

タグをリソースに追加します

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名。--tag-crn と同時に指定することはできません。</dd>
  <dt>--tag-crn (必須)</dt>
  <dd>タグ CRN。--tag-name と同時に指定することはできません。</dd>
  <dt>--resource-crn (必須)</dt>
  <dd>リソース CRN</dd>
</dl>

<strong>例</strong>:

CRN が resource_example_crn であるリソースにタグ "Ray Brown" を追加します。

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

リソースからタグを削除します

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名。--tag-crn と同時に指定することはできません。</dd>
  <dt>--tag-crn (必須)</dt>
  <dd>タグ CRN。--tag-name と同時に指定することはできません。</dd>
  <dt>--resource-crn (必須)</dt>
  <dd>リソース CRN</dd>
</dl>

<strong>例</strong>:

CRN が resource_example_crn であるリソースからタグ "Ray Brown" を削除します。

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

ユーザー・タグと制限付きタグを切り替えます

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--tag-name (必須)</dt>
  <dd>タグ名。--tag-crn と同時に指定することはできません。</dd>
  <dt>--tag-crn (必須)</dt>
  <dd>タグ CRN。--tag-name と同時に指定することはできません。</dd>
  <dt>--tag-type (必須)</dt>
  <dd>タグ・タイプ</dd>
</dl>

<strong>例</strong>:

タグ "Ray Brown" を制限付きタグに切り替えます

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
