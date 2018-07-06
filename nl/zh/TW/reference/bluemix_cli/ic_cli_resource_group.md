---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用來管理資源群組及資源的 CLI 指令
{: #ibmcloud_commands_resource}

<table summary="您可以用來管理資源群組及資源的 ibmcloud 指令。">
  <caption>表 1. 用來管理資源群組及資源的指令</caption>
  <thead>
    <th colspan="5">用來管理資源群組及資源的指令</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](ic_cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](ic_cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](ic_cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](ic_cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](ic_cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](ic_cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](ic_cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](ic_cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](ic_cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](ic_cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](ic_cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](ic_cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](ic_cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](ic_cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](ic_cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](ic_cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](ic_cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](ic_cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](ic_cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](ic_cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](ic_cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](ic_cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](ic_cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](ic_cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](ic_cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](ic_cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](ic_cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](ic_cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](ic_cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](ic_cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](ic_cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](ic_cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](ic_cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](ic_cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

### ibmcloud resource groups
{: #ibmcloud_resource_groups}

列出資源群組。

```
ibmcloud resource groups [--default]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--default</dt>
  <dd>取得現行帳戶的預設群組。</dd>
</dl>

<strong>範例</strong>：

列出目前設為目標的帳戶下的所有資源群組：

```
ibmcloud resource groups
```

列出目前設為目標的帳戶的預設群組：

```
ibmcloud resource groups --default
```

### ibmcloud resource group
{: #ibmcloud_resource_group}

顯示資源群組的詳細資料

```
ibmcloud resource group NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>資源群組的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID</dd>
</dl>

<strong>範例</strong>：

顯示資源群組 `example-group`：

```
ibmcloud resource group example-group
```

僅顯示資源群組 `example-group` 的 ID：

```
ibmcloud resource group example-group --id
```

### ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

建立資源群組

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

<strong>範例</strong>：

建立配額為 `free` 的資源群組 `example-group`：

```
ibmcloud resource group-create example-group free
```

### ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

更新現有資源群組

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>目標資源群組的名稱</dd>
  <dt>-n, --name</dt>
  <dd>資源群組的新名稱</dd>
  <dt>-q, --quota</dt>
  <dd>新配額定義的名稱</dd>
  <dt>-f</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將資源群組 `example-group` 重新命名為 `trial-group`：

```
ibmcloud resource group-update example-group -n trial-group
```

將資源群組 `example-group` 的配額變更為 `free`：

```
ibmcloud resource group-update example-group -q free
```

### ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配額定義

```
ibmcloud resource quotas
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出所有配額定義：

```
ibmcloud resource quotas
```

### ibmcloud resource quota
{: #ibmcloud_resource_quota}

顯示配額定義的詳細資料

```
ibmcloud resource quota NAME
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>配額名稱</dd>
</dl>

<strong>範例</strong>：顯示配額 `free` 的詳細資料：

```
ibmcloud resource quota free
```

### ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

將 Cloudfoundry 服務實例移轉至資源群組

```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>必要條件</strong>：登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_INSTANCE_NAME 或 SERVICE_INSTANCE_ID（必要）</dt>
  <dd>服務實例的名稱或 ID</dd>
  <dt>--resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--resource-group-id' 不能同時使用。如果未指定其中個，則會預設為設成目標的資源群組。</dd>
  <dt>--resource-group-id </dt>
  <dd>資源群組的 ID。此選項與 '--resource-group-name' 不能同時使用。如果未指定其中個，則會預設為設成目標的資源群組。</dd>
  <dt>-f, --force</dt>
  <dd>移轉而不進行確認</dd>
</dl>

### ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服務實例

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--service-name</dt>
  <dd>隸屬服務的名稱</dd>
  <dt>--location</dt>
  <dd>依位置過濾</dd>
  <dt>--long</dt>
  <dd>顯示輸出中的其他欄位</dd>
</dl>

<strong>範例</strong>：

列出服務 `test-service` 的服務實例：

```
ibmcloud resource service-instances --service-name test-service
```

### ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

顯示服務實例的詳細資料

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要），與 ID 不能同時使用</dt>
  <dd>服務實例的名稱</dd>
  <dt>ID（必要），與 NAME 不能同時使用</dt>
  <dd>服務實例的 ID</dd>
  <dt>--location</dt>
  <dd>依位置過濾</dd>
  <dt>--id</dt>
  <dd>顯示服務實例的 ID</dd>
</dl>

<strong>範例</strong>：

顯示服務實例 `my-service-instance` 的詳細資料：

```
ibmcloud resource service-instance my-service-instance
``` 

### ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

建立服務實例

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME（必要）</dt>
  <dd>服務實例的名稱</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必要）</dt>
  <dd>服務的名稱或 ID</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必要）</dt>
  <dd>服務方案的名稱或 ID</dd>
  <dt>LOCATION</dt>
  <dd>用於建立服務實例的目標位置或環境</dd>
  <dt>-t, --tags</dt>
  <dd>標籤</dd>
  <dt>-p, --parameters</dt>
  <dd>要建立服務實例之參數的 JSON 檔案或 JSON 字串</dd>
  <dt>-d, --deployment</dt>
  <dd>部署的名稱</dd>
</dl>

<strong>範例</strong>：在位置 `eu-gb` 上使用服務 `test-service` 的服務方案 `test-service-plan`，建立名為 `my-service-instance` 的服務實例：

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服務實例

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>Name（必要）</dt>
  <dd>服務實例的名稱，與 ID 不能同時使用</dd>
  <dt>ID（必要）</dt>
  <dd>服務實例的 ID，與 NAME 不能同時使用</dd>
  <dt>-n, --name</dt>
  <dd>新的服務實例名稱</dd>
  <dt>-t, --tags</dt>
  <dd>新標籤</dd>
  <dt>--service-plan-id</dt>
  <dd>新的服務方案 ID</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：更新服務實例 `my-service-instance`，並將其名稱變更為 `new-service-instance`：

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

### ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

刪除服務實例

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

<strong>範例</strong>：刪除資源服務實例 `my-service-instance`：

```
ibmcloud resource service-instance-delete my-service-instance
```

### ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

顯示與服務別名的連結

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS（必要）</dt>
  <dd>服務別名</dd>
</dl>

<strong>範例</strong>：顯示與服務別名 `my-service-alias` 的資源連結：

```
ibmcloud resource bindings my-service-alias
```

### ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

顯示服務連結的詳細資料

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示 ID。會抑制服務連結的所有其他輸出。</dd>
</dl>

<strong>範例</strong>：顯示服務別名 `my-service-alias` 與應用程式 `my-app` 之間服務連結的詳細資料：

```
ibmcloud resource bindings my-service-alias my-app
```

### ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

建立服務連結

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必要）</dt>
  <dd>服務別名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 應用程式名稱</dd>
  <dt>ROLE_NAME</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--service-id</dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameter</dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：以 `Administrator` 角色，建立服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

### ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

刪除服務連結

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

<strong>範例</strong>：刪除服務別名 `my-service-alias` 與應用程式 `my-app` 之間的服務連結：

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

### ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服務實例或服務別名的服務金鑰

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
</dl>

<strong>範例</strong>：列出服務實例 `my-service-instance` 的服務金鑰：

```
ibmcloud resource service-keys --instance-name my-service-instance
```

### ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

顯示服務金鑰的詳細資料

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>--id</dt>
  <dd>顯示服務金鑰的 ID</dd>
</dl>

<strong>範例</strong>：顯示服務金鑰 `my-service-key` 的詳細資料：

```
ibmcloud resource service-key my-service-key
```

### ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

建立服務金鑰

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>ROLE_NAME</dt>
  <dd>使用者角色的名稱</dd>
  <dt>--instance-id</dt>
  <dd>服務實例 ID</dd>
  <dt>--instance-name</dt>
  <dd>服務實例名稱</dd>
  <dt>--alias-id</dt>
  <dd>服務別名 ID</dd>
  <dt>--alias-name</dt>
  <dd>服務別名</dd>
  <dt>--service-id</dt>
  <dd>角色所屬服務 ID 的名稱或 UUID</dd>
  <dt>-p, --parameters</dt>
  <dd>參數 JSON 檔案或 JSON 字串</dd>
  <dt>-f, --force</dt>
  <dd>強制建立，而不進行確認</dd>
</dl>

<strong>範例</strong>：以 `Administrator` 角色，為服務實例 `my-service-instance` 建立名為 `my-service-key` 的服務金鑰：

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

刪除服務金鑰

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>索引鍵的名稱</dd>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：刪除服務金鑰 `my-service-key`：

```
ibmcloud resource service-key-delete my-service-key
```

### ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服務實例的別名

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>隸屬服務實例的 ID。</dd>
  <dt>--instance-name</dt>
  <dd>隸屬服務實例的名稱。</dd>
</dl>

<strong>範例</strong>：列出服務實例 `my-service-instance` 的服務別名：
```
ibmcloud resource service-aliases my-service-instance
```

### ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

顯示服務別名的詳細資料

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>ALIAS_NAME（必要）</dt>
  <dd>服務別名的名稱</dd>
  <dt>--id</dt>
  <dd>僅顯示給定服務別名的 ID。會抑制別名的所有其他輸出。</dd>
</dl>

<strong>範例</strong>：顯示服務別名 `my-service-alias` 的詳細資料：
```
ibmcloud resource service-alias  my-service-alias
```

### ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

建立服務實例的別名

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

<strong>範例</strong>：為服務實例 `my-service-instance`，建立名為 `my-service-alias` 的服務別名：
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

### ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服務別名

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

<strong>範例</strong>：更新服務別名 `my-service-alias`，並將其名稱變更為 `new-service-alias`：

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

### ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

刪除服務別名

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

<strong>範例</strong>：刪除服務別名 `my-service-alias`：

```
ibmcloud resource service-alias-delete my-service-alias
```

### ibmcloud resource search
{: #ibmcloud_resource_search}
使用 Lucene 查詢語法來搜尋資源

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-offset, --o</dt>
  <dd>開始的資源位置號碼</dd>
  <dt>-limit, --l</dt>
  <dd>要傳回的資源數（上限為 10000）</dd>
</dl>

<strong>範例</strong>：搜尋名稱開頭為指定文字的 Cloud Foundry 應用程式：

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

搜尋指定服務名稱的 Cloud Foundry 服務實例：

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

在組織中搜尋具有指定 ID 的 Cloud Foundry 服務連結：

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

搜尋具有指定名稱且位於兩個指定地區之一的 Cloud Foundry 空間：

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

在具有指定 ID 的 Cloud Foundry 空間中，搜尋名稱包含 dev 一字的資源：

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

搜尋指定位置（亦即 us-south 地區）中的資源控制器資源：

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

在具有指定 ID 的資源群組中搜尋資源或別名：

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

搜尋名稱為 default 的資源群組：

```
ibmcloud resource search 'name:default AND type:resource-group'
```

搜尋指定服務名稱的資源連結：

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

搜尋具有指定「雲端資源名稱 (CRN)」的資源：

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

搜尋具有指定標籤的資源：

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

### ibmcloud resource tags
{: #ibmcloud_resource_tags}

列出所有標籤

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-type</dt>
  <dd>標籤類型（支援的值：user、restricted）</dd>
  <dt>-o, --offset</dt>
  <dd>開始的資源位置號碼（預設值：0）</dd>
  <dt>-l, --limit</dt>
  <dd>要傳回的資源數（上限為 10000）（預設值：10000）</dd>
</dl>

<strong>範例</strong>：

列出所有標籤

```
ibmcloud resource tags 
```

列出所有受限標籤

```
ibmcloud resource tags --tag-type restricted
```

### ibmcloud resource tag
{: #ibmcloud_resource_tag}

顯示標籤的詳細資料

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱，與 --tag-crn 不能同時使用</dd>
  <dt>--tag-crn（必要）</dt>
  <dd>標籤 CRN，與 --tag-name 不能同時使用</dd>
</dl>

<strong>範例</strong>：

顯示標籤 "Ray Brown" 的詳細資料

```
ibmcloud resource tag --tag-name "Ray Brown"
```

### ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

建立標籤

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱</dd>
  <dt>--tag-type</dt>
  <dd>標籤類型（支援的值：user、restricted；預設值：user）</dd>
</dl>

<strong>範例</strong>：

建立名稱為 think:2018 的使用者標籤

```
ibmcloud resource tag-create --tag-name think:2018
```

建立名稱為 department:marketing:2018 的受限標籤

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

建立名稱為 "Ray Brown" 的使用者標籤

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

建立名稱為 "environment:My Development" 的受限標籤

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

### ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

刪除標籤

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱，與 --tag-crn 不能同時使用</dd>
  <dt>--tag-crn（必要）</dt>
  <dd>標籤 CRN，與 --tag-name 不能同時使用</dd>
</dl>

<strong>範例</strong>：

刪除標籤 "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

### ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

將標籤新增至資源

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱，與 --tag-crn 不能同時使用</dd>
  <dt>--tag-crn（必要）</dt>
  <dd>標籤 CRN，與 --tag-name 不能同時使用</dd>
  <dt>--resource-crn（必要）</dt>
  <dd>資源 CRN</dd>
</dl>

<strong>範例</strong>：

將標籤 "Ray Brown" 新增至其 crn 為 resource_example_crn 的資源。

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

從資源中移除標籤

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱，與 --tag-crn 不能同時使用</dd>
  <dt>--tag-crn（必要）</dt>
  <dd>標籤 CRN，與 --tag-name 不能同時使用</dd>
  <dt>--resource-crn（必要）</dt>
  <dd>資源 CRN</dd>
</dl>

<strong>範例</strong>：

從其 crn 為 resource_example_crn 的資源中移除標籤 "Ray Brown"。

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

將使用者標籤切換至受限標籤，反之亦然

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--tag-name（必要）</dt>
  <dd>標籤名稱，與 --tag-crn 不能同時使用</dd>
  <dt>--tag-crn（必要）</dt>
  <dd>標籤 CRN，與 --tag-name 不能同時使用</dd>
  <dt>--tag-type（必要）</dt>
  <dd>標籤類型</dd>
</dl>

<strong>範例</strong>：

將標籤 "Ray Brown" 切換至受限標籤

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
