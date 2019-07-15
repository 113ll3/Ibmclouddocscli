---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-06"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 使用資源和資源群組
{: #ibmcloud_commands_resource}

資源群組可讓您用可自訂的分組來組織帳戶資源。請使用下列指令來管理資源群組中的 {{site.data.keyword.cloud}} 資源。
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

列出資源群組。
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--default</dt>
  <dd>取得現行帳戶的預設群組。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

列出目前設為目標的帳戶下的所有資源群組：
```
ibmcloud resource groups
```
{: codeblock}

列出目前設為目標的帳戶的預設群組：
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

顯示資源群組的詳細資料。
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>資源群組的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

顯示資源群組 `example-group`：
```
ibmcloud resource group example-group
```
{: codeblock}

僅顯示資源群組 `example-group` 的 ID：
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

建立資源群組：
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>資源群組的名稱</dd>
</dl>

<strong>範例</strong>：

建立資源群組 `example-group`：
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

更新現有資源群組。
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] 
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>目標資源群組的名稱</dd>
  <dt>-n, --name</dt>
  <dd>資源群組的新名稱</dd>
  <dt>-f</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將資源群組 `example-group` 重新命名為 `trial-group`：
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配額定義。
```
ibmcloud resource quotas
```
{: codeblock}

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出所有配額定義：
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

顯示配額定義的詳細資料。
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>配額名稱</dd>
</dl>

<strong>範例</strong>：

顯示配額 `free` 的詳細資料：
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

將 Cloud Foundry 服務實例移轉至資源群組。
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_INSTANCE_NAME 或 SERVICE_INSTANCE_ID（必要）</dt>
  <dd>服務實例的名稱或 ID</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--resource-group-id' 不能同時使用。如果未指定，則預設為現行目標資源群組。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--resource-group-name' 不能同時使用。如果未指定，則預設為現行目標資源群組。</dd>
  <dt>-f, --force</dt>
  <dd>移轉而不進行確認</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服務實例。
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>隸屬服務的名稱</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>依位置進行過濾</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>實例的類型。若未指定，則會使用 `service_instance` 類型，使用 all 可列出實例的所有類型。</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>資源群組名稱</dd>
  <dt>--long</dt>
  <dd>在輸出中顯示其他欄位</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

列出服務 `test-service` 的服務實例：
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

顯示服務實例的詳細資料。

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要），與 ID 不能同時使用</dt>
  <dd>服務實例的名稱</dd>
  <dt>ID（必要），與 NAME 不能同時使用</dt>
  <dd>服務實例的 ID</dd>
  <dt>--location</dt>
  <dd>依位置進行過濾</dd>
  <dt>--id</dt>
  <dd>顯示服務實例的 ID</dd>
  <dt>--output</dt>
  <dd>指定輸出格式，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

顯示服務實例 `my-service-instance` 的詳細資料：
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

建立服務實例。
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務實例的名稱</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必要）</dt>
  <dd>服務的名稱或 ID。若要列出服務供應項目，請使用 `ibmcloud catalog service-marketplace` [指令](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_catalog#ibmcloud_catalog_service_marketplace)。</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必要）</dt>
  <dd>服務方案的名稱或 ID</dd>
  <dt>LOCATION（必要）</dt>
  <dd>用於建立服務實例的目標位置或環境</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>部署的名稱</dd>
  <dt>-p, --parameters <i>@JSONFILE 或 JSON_STRING</i></dt>
  <dd>要建立服務實例之參數的 JSON 檔案或 JSON 字串</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>資源群組名稱</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>服務端點的類型。可能的值為 'public'、'private'、'public-and-private'。</dd>
</dl>

<strong>範例</strong>：

在位置 `eu-gb` 上使用服務 `test-service` 的服務方案 `test-service-plan`，建立名為 `my-service-instance` 的服務實例：
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服務實例。
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>Name（必要）</dt>
  <dd>服務實例的名稱，與 ID 不能同時使用</dd>
  <dt>ID（必要）</dt>
  <dd>服務實例的 ID，與 NAME 不能同時使用</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>新的服務實例名稱</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>新的服務方案 ID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>要建立服務實例之參數的 JSON 檔案或 JSON 字串</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>資源群組名稱</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>服務端點的類型。可能的值為 'public'、'private'、'public-and-private'。</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

更新服務實例 `my-service-instance`，並將其名稱變更為 `new-service-instance`：
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

刪除服務實例。
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>Name（必要）</dt>
  <dd>服務實例的名稱，與 ID 不能同時使用</dd>
  <dt>ID（必要）</dt>
  <dd>服務實例的 ID，與 NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
  <dt>--recursive</dt>
  <dd>刪除所有隸屬資源</dd>
</dl>

<strong>範例</strong>：

刪除資源服務實例 `my-service-instance`：
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

顯示與服務別名的連結。
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS（必要）</dt>
  <dd>服務別名</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

顯示與服務別名 `my-service-alias` 的資源連結：
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

顯示服務連結的詳細資料。
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID。會抑制服務連結的所有其他輸出。此選項與 '--output' 不能同時使用。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

顯示服務別名 `my-service-alias` 與應用程式 `my-app` 之間服務連結的詳細資料：
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

建立服務連結。
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME（必要）</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>ROLE_NAME（必要）</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>服務端點的類型。可能的值為 'public'、'private'。</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：

以 `Administrator` 角色，建立服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

刪除服務連結。
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：
刪除服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服務實例或服務別名的服務金鑰。
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>服務實例 ID</dd>
  <dt>--instance-name</dt>
  <dd>服務實例名稱</dd>
  <dt>--alias-id</dt>
  <dd>服務別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>服務別名</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

列出服務實例 `my-service-instance` 的服務金鑰：
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

顯示任何數目服務金鑰的詳細資料，其中服務金鑰名稱的前 *n* 個字元符合所提供的 KEY_NAME。
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME</dt>
  <dd>金鑰的名稱</dd>
  <dt>ID</dt>
  <dd>金鑰的 ID</dd>
  <dt>-g</dt>
  <dd>資源群組名稱</dd>
  <dt>--id</dt>
  <dd>顯示服務金鑰的 ID。此選項與 '--output' 不能同時使用。</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>資源群組名稱</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

顯示服務金鑰 `my-service-key` 的詳細資料：
```
ibmcloud resource service-key my-service-key
```
<strong>範例</strong>：
顯示 ID 為 `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79` 之服務金鑰的詳細資料：

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

建立服務金鑰。
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>金鑰的名稱</dd>
  <dt>ROLE_NAME（必要）</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>服務實例 ID</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>服務實例名稱</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>服務別名 ID</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>服務別名</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>資源群組名稱</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>服務端點的類型。可能的值為 'public'、'private'。</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：

以 `Administrator` 角色，為服務實例 `my-service-instance` 建立名為 `my-service-key` 的服務金鑰：
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

更新服務金鑰。
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME | ID</dt>
  <dd>金鑰的名稱或 ID</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>金鑰的新名稱</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>金鑰所屬資源群組的 ID</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

更新名為 `my-service-key` 的服務金鑰，提供它新名稱 `my-service-key-2`：
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

刪除服務金鑰。
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>金鑰的名稱或金鑰的 ID</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務金鑰 `my-service-key`：
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服務實例的別名。
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>隸屬服務實例的 ID。</dd>
  <dt>--instance-name</dt>
  <dd>隸屬服務實例的名稱。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

列出服務實例 `my-service-instance` 的服務別名：
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

顯示服務別名的詳細資料。
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示給定服務別名的 ID。會抑制別名的所有其他輸出。此選項與 '--output' 不能同時使用。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>--output value  指定輸出格式，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

顯示服務別名 `my-service-alias` 的詳細資料：
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

建立服務實例的別名。
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>--instance-id</dt>
  <dd>隸屬服務實例的 ID。</dd>
  <dt>--instance-name</dt>
  <dd>隸屬服務實例的名稱。</dd>
  <dt>-s</dt>
  <dd>在其中建立別名的空間名稱。預設為現行空間。</dd>
  <dt>-t, --tags</dt>
  <dd>標籤清單。</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串。</dd>
</dl>

<strong>範例</strong>：

為服務實例 `my-service-instance`，建立名為 `my-service-alias` 的服務別名：
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服務別名。
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>-n, --name</dt>
  <dd>服務別名的新名稱。</dd>
  <dt>-t, --tags</dt>
  <dd>標籤清單。</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串。</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行使用者確認。</dd>
</dl>

<strong>範例</strong>：

更新服務別名 `my-service-alias`，並將其名稱變更為 `new-service-alias`：
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

刪除服務別名。
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除服務別名 `my-service-alias`：
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

使用 Lucene 查詢語法來搜尋資源。
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-o, -offset</dt>
  <dd>開始的資源位置號碼</dd>
  <dt>-l, -limit</dt>
  <dd>要傳回的資源數（上限為 10000）</dd>
  <dt>-s, --sort-by</dt>
  <dd>排序依據的內容。接受的輸入為 `name`、`family`、`region`、`type`、`crn`。</dd>
  <dt>-p, --provider</dt>
  <dd>顯示「標準基礎架構」資源，唯一容許的值為：classic-infrastructure</dd>
</dl>

<strong>可搜尋的屬性</strong>：您可以搜尋下列屬性：

<dl>
  <dt>name</dt>
  <dd>資源的使用者定義名稱。</dd>
  <dt>地區 (region)</dt>
  <dd>佈建資源的地理位置。例如：us-south、us-east、au-syd、eu-gb、eu-de 及 jp-tok。</dd>
  <dt>service_name</dt>
  <dd>服務出現在 'ibmcloud catalog service-marketplace' 輸出 Name 直欄中時，所顯示的名稱。</dd>
  <dt>family</dt>
  <dd>資源所屬的雲端元件。容許的值為 cloud_foundry、containers、resource_controller、vmware 或 ims。</dd>
  <dt>organization_id</dt>
  <dd>Cloud Foundry 組織 GUID。</dd>
  <dt>doc.space_id</dt>
  <dd>Cloud Foundry 空間 GUID。</dd>
  <dt>doc.resource_group_id</dt>
  <dd>資源群組的 ID。</dd>
  <dt>type</dt>
  <dd>資源類型。容許的值為 k8-cluster、cf-service-instance、cf-user-provided-service-instance、cf-organization、cf-service-binding、cf-space、cf-application、resource-instance、resource-alias、resource-binding、resource-group、vmware-solutions、cloud-objects-storage-infrastructure、block-storage、file-storage、cloud-backup。</dd>
  <dt>creation_date</dt>
  <dd>資源的建立日期。</dd>
  <dt>modification_date</dt>
  <dd>資源的前次修改日期。它的格式為 yyyy-mm-ddThh:mm:ssZ。</dd>
  <dt>_objectType</dt>
  <dd>標準基礎架構資源的類型。容許的值為 SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 及 SoftLayer_Virtual_Guest。</dd>
  <dt>tags、tagReferences.tag.name</dt>
  <dd>連接至資源的標籤。搜尋連接至標準基礎架構資源的標籤時，請使用 tagReferences.tag.name。</dd> 
</dl>

<strong>範例</strong>：

搜尋名稱開頭為指定文字的 Cloud Foundry 應用程式：
```
ibmcloud resource search "name:my* AND type:cf-application"
```

搜尋指定服務名稱的 Cloud Foundry 服務實例：
```
ibmcloud resource search "service_name:messagehub AND type:cf-service-instance"
```

在組織中搜尋具有指定 ID 的 Cloud Foundry 服務連結：
```
ibmcloud resource search "organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding"
```

搜尋具有指定名稱且位於兩個指定地區之一的 Cloud Foundry 空間：
```
ibmcloud resource search "name:dev AND type:cf-space AND region:(us-south OR eu-gb)"
```

在具有指定 ID 的 Cloud Foundry 空間中，搜尋名稱包含 dev 一字的資源：
```
ibmcloud resource search "name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7"
```

搜尋指定位置（亦即 us-south 地區）中的資源控制器資源：
```
ibmcloud resource search "region:us-south AND family:resource_controller"
```

在具有指定 ID 的資源群組中搜尋資源或別名：
```
ibmcloud resource search "(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)"
```

搜尋名稱為 default 的資源群組：
```
ibmcloud resource search "name:default AND type:resource-group"
```

搜尋指定服務名稱的資源連結：
```
ibmcloud resource search "service_name:cloud-object-storage AND type:resource-binding"
```

搜尋具有指定「雲端資源名稱 (CRN)」的資源：
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

搜尋具有指定標籤的資源：
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

搜尋具有所指定 ID 的「標準基礎架構虛擬訪客」資源（僅具有 -p classic-infrastructure）：
```
ibmcloud resource search "id:12345678 _objectType:SoftLayer_Virtual_Guest"
```
{: codeblock}

搜尋具有所指定標籤名稱的「標準基礎架構硬體」資源（僅具有 -p classic-infrastructure）：
```
ibmcloud resource search "tagReferences.tag.name:name _objectType:SoftLayer_Hardware"
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

列出計費帳戶中的所有標籤

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-o, -offset</dt>
  <dd>開始的標籤位置號碼</dd>
  <dt>-l, -limit</dt>
  <dd>要傳回的標籤數（上限為 1000，預設為 100）</dd>
  <dt>-p; --provider</dt> 
  <dd>搜尋標準基礎架構標籤時，請指定 classic-infrastructure</dd>
  <dt>-d, --details</dt>
  <dd>顯示已標記資源的數目。</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

將一個以上的標籤連接至資源：
```
ibmcloud resource tag-attach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```
<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-names（必要）</dt>
  <dd>以逗點區隔的標籤名稱清單</dd>
  <dt>--resource-name</dt>
  <dd>應連接標籤之資源的名稱。此選項無法與標準基礎架構資源搭配使用。</dd>
  <dt>--resource-id</dt>
  <dd>將連接標籤之資源的 CRN；對於標準基礎架構資源，它是資源的 ID。您可以使用 'ibmcloud resource search' 指令，來取得資源的 CRN 或 ID。</dd>
  <dt>--resource-type</dt>
  <dd>將連接標籤之標準基礎架構資源的資源類型；如果將標籤連接至標準基礎架構資源，則此為必要參數。--resource-type 的可能值為：SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 及 SoftLayer_Virtual_Guest。</dd>
</dl>

<strong>範例</strong>：

* 若要將標籤 `MyTag` 連接至名稱為 `MyCluster` 的 Kubernetes 叢集，請先尋找您要標示之叢集的 CRN：
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  請記下 CRN，這是類似於下列範例的字串： 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  若要連接標籤，請執行下列指令：
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* 若要將標籤 `MyTag` 連接至資源名稱 `MyResource`，請執行下列指令：
  ```
  ibmcloud resource tag-attach --tag-name MyTag --resource-name  'MyResource'
  ```
  {: codeblock}
  
  
* 若要將標籤 `MyTag` 連接至名稱為 `MyVM` 的標準基礎架構虛擬來賓，請先尋找您要標示之虛擬來賓的 ID：
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  請記下 ID，這是類似於 `48373549` 的字串。

  若要連接標籤，請執行下列指令：
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

分離一個以上的標籤與資源：
```
ibmcloud resource tag-detach  --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-names（必要）</dt>
  <dd>以逗點區隔的標籤名稱清單</dd>
  <dt>--resource-name</dt>
  <dd>應從中分離標籤之資源的名稱。此選項無法與標準基礎架構資源搭配使用。</dd>
  <dt>--resource-id</dt>
  <dd>將從中分離標籤之資源的 CRN；若為標準基礎架構資源，其為資源的 ID。您可以使用 'ibmcloud resource search' 指令，來取得資源的 CRN 或 ID。</dd>
  <dt>--resource-type</dt>
  <dd>將分離標籤之標準基礎架構資源的資源類型；如果將標籤連接至標準基礎架構資源，則此為必要參數。--resource-type 的可能值為：SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 及 SoftLayer_Virtual_Guest。</dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

刪除標籤：
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>要刪除之標籤的名稱。</dd>
  <dt>-p; --provider</dt> 
  <dd>刪除標準基礎架構標籤時，請指定 classic-infrastructure</dd>
</dl>

只有在標籤未連接至任何資源時，才能刪除標籤。
