---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 使用资源和资源组
{: #ibmcloud_commands_resource}

资源组是一种使用可定制的分组来组织帐户资源的方法。使用以下命令可管理 {{site.data.keyword.cloud}} 资源及资源组中的资源。
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

列出资源组。
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--default</dt>
  <dd>获取当前帐户的缺省组。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

列出当前目标帐户下的所有资源组：
```
ibmcloud resource groups
```
{: codeblock}

列出当前目标帐户的缺省组：
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

显示资源组的详细信息
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>资源组的名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

显示资源组 `example-group`：
```
ibmcloud resource group example-group
```
{: codeblock}

仅显示资源组 `example-group` 的标识：
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

创建资源组：
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>资源组的名称</dd>
</dl>

<strong>示例</strong>：

创建资源组 `example-group`：
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

更新现有资源组
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>目标资源组的名称</dd>
  <dt>-n, --name</dt>
  <dd>资源组的新名称</dd>
  <dt>-q, --quota</dt>
  <dd>新配额定义的名称</dd>
  <dt>-f</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

将资源组 `example-group` 重命名为 `trial-group`：
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

将资源组 `example-group` 的配额更改为 `free`：
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配额定义。
```
ibmcloud resource quotas
```
{: codeblock}

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出所有配额定义：
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

显示配额定义的详细信息。
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>配额的名称</dd>
</dl>

<strong>示例</strong>：

显示配额 `free` 的详细信息：
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

将 Cloud Foundry 服务实例迁移到资源组
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_INSTANCE_NAME or SERVICE_INSTANCE_ID（必需）</dt>
  <dd>服务实例的名称或标识</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。此选项与“--resource-group-id”互斥。如果未指定其中任何选项，缺省情况下为当前的目标资源组。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。此选项与“--resource-group-name”互斥。如果未指定其中任何选项，缺省情况下为当前的目标资源组。</dd>
  <dt>-f, --force</dt>
  <dd>迁移而不确认</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服务实例。
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--service-name</dt>
  <dd>所属服务的名称</dd>
  <dt>--location</dt>
  <dd>按位置过滤</dd>
  <dt>--long</dt>
  <dd>在输出中显示更多字段</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

列出服务 `test-service` 的服务实例：
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance

{: #ibmcloud_resource_service_instance}

显示服务实例的详细信息。

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需），与 ID 互斥</dt>
  <dd>服务实例的名称</dd>
  <dt>ID（必需），与 NAME 互斥</dt>
  <dd>服务实例的标识</dd>
  <dt>--location</dt>
  <dd>按位置过滤</dd>
  <dt>--id</dt>
  <dd>显示服务实例的标识</dd>
  <dt>--output</dt>
  <dd>指定输出格式，目前仅支持 JSON。此选项与“--id”互斥。</dd>
</dl>

<strong>示例</strong>：

显示服务实例 `my-service-instance` 的详细信息：
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

创建服务实例。
```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务实例的名称</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必需）</dt>
  <dd>服务的名称或标识。要列出服务产品，请使用 `ibmcloud catalog service-marketplace` [命令](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace)。</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必需）</dt>
  <dd>服务套餐的名称或标识</dd>
  <dt>LOCATION</dt>
  <dd>用于创建服务实例的目标位置或环境</dd>
  <dt>-p, --parameters</dt>
  <dd>用于创建服务实例的参数的 JSON 文件或 JSON 字符串</dd>
  <dt>-d, --deployment</dt>
  <dd>部署的名称</dd>
</dl>

<strong>示例</strong>：

使用服务 `test-service` 的服务套餐 `test-service-plan` 在位置 `eu-gb` 中创建名为 `my-service-instance` 的服务实例：
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服务实例。
```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [--parameters @JSON_FILE | JSON_STRING] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必需）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必需）</dt>
  <dd>服务实例的 ID，与 NAME 互斥 </dd>
  <dt>-n, --name</dt>
  <dd>新服务实例名称</dd>
  <dt>--service-plan-id</dt>
  <dd>新服务套餐标识</dd>
  <dt>--parameters @JSON_FILE | JSON_STRING</dt>
  <dd>用于创建服务实例的参数的 JSON 文件或 JSON 字符串</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

更新服务实例 `my-service-instance`，将其名称更改为 `new-service-instance`：
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

删除服务实例。
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必需）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必需）</dt>
  <dd>服务实例的 ID，与 NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
  <dt>--recursive</dt>
  <dd>删除全部所属资源</dd>
</dl>

<strong>示例</strong>：

删除资源服务实例 `my-service-instance`：
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

显示与服务别名的绑定。
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS（必需）</dt>
  <dd>服务别名</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

显示与服务别名 `my-service-alias` 的资源绑定：
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

显示服务绑定的详细信息。
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识。将禁止服务绑定的所有其他输出。此选项与“--output”互斥。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。此选项与“--id”互斥。</dd>
</dl>

<strong>示例</strong>：

显示服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定的详细信息：
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

创建服务绑定。
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>ROLE_NAME</dt>
  <dd>用户角色的名称</dd>
  <dt>--service-id</dt>
  <dd>角色所属的服务标识的名称或 UUID</dd>
  <dt>-p, --parameter</dt>
  <dd>参数 JSON 文件或 JSON 字符串</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：

使用角色 `Administrator` 创建服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定：
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

删除服务绑定。
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：
删除服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定：
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服务实例或服务别名的服务密钥。
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>服务实例标识</dd>
  <dt>--instance-name</dt>
  <dd>服务实例名称</dd>
  <dt>--alias-id</dt>
  <dd>服务别名标识</dd>
  <dt>--alias-name</dt>
  <dd>服务别名</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

列出服务实例 `my-service-instance` 的服务密钥：
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

显示任意数量的服务密钥的详细信息，其中服务密钥名称的前 *n* 个字符与所提供的 KEY_NAME 相匹配。
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME</dt>
  <dd>密钥的名称</dd>
  <dt>ID</dt>
  <dd>密钥的标识</dd>
  <dt>-g</dt>
  <dd>资源组名称</dd>
  <dt>--id</dt>
  <dd>显示服务密钥的标识。此选项与“--output”互斥。</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>资源组名称</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。此选项与“--id”互斥。</dd>
</dl>

<strong>示例</strong>：

显示服务密钥 `my-service-key` 的详细信息：
```
ibmcloud resource service-key my-service-key
```
<strong>示例</strong>：
显示标识为 `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79` 的服务密钥的详细信息：

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

创建服务密钥。
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME</dt>
  <dd>密钥的名称</dd>
  <dt>ROLE_NAME</dt>
  <dd>用户角色的名称</dd>
  <dt>--instance-id</dt>
  <dd>服务实例标识</dd>
  <dt>--instance-name</dt>
  <dd>服务实例名称</dd>
  <dt>--alias-id</dt>
  <dd>服务别名标识</dd>
  <dt>--alias-name</dt>
  <dd>服务别名</dd>
  <dt>--service-id</dt>
  <dd>角色所属的服务标识的名称或 UUID</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：

使用角色 `Administrator` 为服务实例 `my-service-instance` 创建名为 `my-service-key` 的服务密钥：
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

更新服务密钥。
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME | ID</dt>
  <dd>密钥的名称或标识</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>密钥的新名称</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>密钥所属的资源组的标识</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

更新名为 `my-service-key` 的服务密钥，为其指定新名称 `my-service-key-2`：
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

删除服务密钥。
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>密钥的名称或密钥的标识</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务密钥 `my-service-key`：
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服务实例的别名。
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>所属服务实例的标识。</dd>
  <dt>--instance-name</dt>
  <dd>所属服务实例的名称。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

列出服务实例 `my-service-instance` 的服务别名：
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

显示服务别名的详细信息。
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>--id</dt>
  <dd>仅显示给定服务别名的标识。将禁止别名的所有其他输出。此选项与“--output”互斥。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>--output value  指定输出格式，目前仅支持 JSON。此选项与“--id”互斥。</dd>
</dl>

<strong>示例</strong>：

显示服务别名 `my-service-alias` 的详细信息：
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

创建服务实例的别名。
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>--instance-id</dt>
  <dd>所属服务实例的标识。</dd>
  <dt>--instance-name</dt>
  <dd>所属服务实例的名称。</dd>
  <dt>-s</dt>
  <dd>在其中创建别名的空间的名称。缺省值为当前空间。</dd>
  <dt>-t, --tags</dt>
  <dd>标记列表。</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串。</dd>
</dl>

<strong>示例</strong>：

创建服务实例 `my-service-instance` 的服务别名 `my-service-alias`：
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服务别名。
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>-n, --name</dt>
  <dd>服务别名的新名称。</dd>
  <dt>-t, --tags</dt>
  <dd>标记列表。</dd>
  <dt>-p, --parameters</dt>
  <dd>参数 JSON 文件或 JSON 字符串。</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而无需用户确认。</dd>
</dl>

<strong>示例</strong>：

更新服务别名 `my-service-alias`，将其名称更改为 `new-service-alias`：
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

删除服务别名。
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务别名 `my-service-alias`：
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

使用 Lucene 查询语法搜索资源。
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-o, -offset</dt>
  <dd>起始资源位置编号</dd>
  <dt>-l, -limit</dt>
  <dd>要返回的资源数（最多 10000 个）</dd>
  <dt>-s, --sort-by</dt>
  <dd>要作为排序依据的属性。接受的输入为 `name`、`family`、`region`、`type` 或 `crn`。</dd>
  <dt>-p, --provider</dt>
  <dd>显示经典基础架构资源，唯一允许的值为：classic-infrastructure</dd>
</dl>

<strong>可搜索的属性</strong>：
您可以搜索以下属性：

<dl>
  <dt>name</dt>
  <dd>用户定义的资源名称。</dd>
  <dt>区域 (region)</dt>
  <dd>供应资源的地理位置。例如：us-south、us-east、au-syd、eu-gb、eu-de 和 jp-tok。</dd>
  <dt>service_name</dt>
  <dd>在“ibmcloud catalog service-marketplace”的输出的 Name 列中显示的服务名称。</dd>
  <dt>family</dt>
  <dd>资源所属的云组件。允许的值为 cloud_foundry、containers、resource_controller、vmware 或 ims。</dd>
  <dt>organization_id</dt>
  <dd>Cloud Foundry 组织 GUID。</dd>
  <dt>doc.space_id</dt>
  <dd>Cloud Foundry 空间 GUID。</dd>
  <dt>doc.resource_group_id</dt>
  <dd>资源组的标识。</dd>
  <dt>type</dt>
  <dd>资源类型。允许的值为 k8-cluster、cf-service-instance、cf-user-provided-service-instance、cf-organization、cf-service-binding、cf-space、cf-application、resource-instance、resource-alias、resource-binding、resource-group、vmware-solutions、cloud-objects-storage-infrastructure、block-storage、file-storage 和 cloud-backup。</dd>
  <dt>creation_date</dt>
  <dd>创建资源的日期。</dd>
  <dt>modification_date</dt>
  <dd>上次修改资源的日期。格式为 yyyy-mm-ddThh:mm:ssZ</dd>
  <dt>_objectType</dt>
  <dd>经典基础架构资源的类型。允许的值为 SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 和 SoftLayer_Virtual_Guest。</dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>附加到资源的标记。搜索附加到经典基础架构资源的标记时，请使用 tagReferences.tag.name。</dd> 
</dl>

<strong>示例</strong>：

搜索名称以指定文本开头的 Cloud Foundry 应用程序：
```
ibmcloud resource search 'name:my* AND type:cf-application'
```

搜索指定服务名称的 Cloud Foundry 服务实例：
```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

在具有指定标识的组织中搜索 Cloud Foundry 服务绑定：
```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

搜索具有指定名称且位于两个指定区域之一内的 Cloud Foundry 空间：
```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

在具有指定标识的 Cloud Foundry 空间中搜索其名称中包含文字 dev 的资源：
```
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

在指定位置中（即，在 us-south 区域中）搜索资源控制器资源：
```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

在具有指定标识的资源组中搜索资源或别名：
```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

搜索名称为 default 的资源组：
```
ibmcloud resource search 'name:default AND type:resource-group'
```

搜索指定服务名称的资源绑定：
```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

搜索具有指定云资源名称 (CRN) 的资源：
```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

搜索具有指定标记的资源：
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

搜索具有指定标识的经典基础架构虚拟访客资源（仅使用 -p classic-infrastructure）：
```
ibmcloud resource search 'id:12345678 _objectType:SoftLayer_Virtual_Guest'
```
{: codeblock}

搜索具有指定标记名称的经典基础架构硬件资源（仅使用 -p classic-infrastructure）：
```
ibmcloud resource search 'tagReferences.tag.name:name _objectType:SoftLayer_Hardware'
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

列出计费帐户中的所有标记

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-o, -offset</dt>
  <dd>起始标记位置编号</dd>
  <dt>-l, -limit</dt>
  <dd>要返回的标记数（最多 10000 个）</dd>
  <dt>-p; --provider</dt> 
  <dd>搜索经典基础架构标记时，请指定 classic-infrastructure</dd>
  <dt>-d, --details</dt>
  <dd>显示已标记资源的数量。</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

将一个或多个标记附加到资源：
```
ibmcloud resource tag-attach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```
<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-names（必需）</dt>
  <dd>以逗号分隔的标记名称的列表</dd>
  <dt>--resource-id</dt>
  <dd>要对其附加标记的资源的 CRN；对于经典基础架构资源而言，它是资源的标识</dd>
  <dt>--resource-type</dt>
  <dd>要对其附加标记的经典基础架构资源的资源类型；要将标记附加到经典基础架构资源时，此参数是必需的。--resource-type 的可能值为：SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 和 SoftLayer_Virtual_Guest。</dd>
</dl>

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

从资源中分离一个或多个标记：
```
ibmcloud resource tag-detach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-names（必需）</dt>
  <dd>以逗号分隔的标记名称的列表</dd>
  <dt>--resource-id</dt>
  <dd>要从中分离标记的资源的 CRN；对于经典基础架构资源而言，它是资源的标识</dd>
  <dt>--resource-type</dt>
  <dd>要从中分离标记的经典基础架构资源的资源类型；要从经典基础架构资源中分离标记，此参数是必需的。--resource-type 的可能值为：SoftLayer_Virtual_DedicatedHost、SoftLayer_Hardware、SoftLayer_Network_Application_Delivery_Controller、SoftLayer_Network_Subnet_IpAddress、SoftLayer_Network_Vlan、SoftLayer_Network_Vlan_Firewall 和 SoftLayer_Virtual_Guest。</dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

删除标记：
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必需）</dt>
  <dd>要删除的标记的名称。</dd>
  <dt>-p; --provider</dt> 
  <dd>删除经典基础架构标记时，请指定 classic-infrastructure</dd>
</dl>

只能删除未附加到任何资源的标记。
