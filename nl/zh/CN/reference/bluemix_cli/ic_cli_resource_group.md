---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用于管理资源组和资源的 CLI 命令
{: #ibmcloud_commands_resource}

<table summary="可用于管理资源组和资源的 ibmcloud 命令。">
  <caption>表 1. 用于管理资源组和资源的命令</caption>
  <thead>
    <th colspan="5">用于管理资源组和资源的命令</th>
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

列出资源组。

```
ibmcloud resource groups [--default]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--default</dt>
  <dd>获取当前帐户的缺省组。</dd>
</dl>

<strong>示例</strong>：

列出当前目标帐户下的所有资源组：

```
ibmcloud resource groups
```

列出当前目标帐户的缺省组：

```
ibmcloud resource groups --default
```

### ibmcloud resource group
{: #ibmcloud_resource_group}

显示资源组的详细信息

```
ibmcloud resource group NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>资源组的名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识</dd>
</dl>

<strong>示例</strong>：

显示资源组 `example-group`：

```
ibmcloud resource group example-group
```

仅显示资源组 `example-group` 的标识：

```
ibmcloud resource group example-group --id
```

### ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

创建资源组

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：

<strong>示例</strong>：

创建配额为 `free` 的资源组 `example-group`：

```
ibmcloud resource group-create example-group free
```

### ibmcloud resource group-update
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

将资源组 `example-group` 的配额更改为 `free`：

```
ibmcloud resource group-update example-group -q free
```

### ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

列出所有配额定义

```
ibmcloud resource quotas
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出所有配额定义：

```
ibmcloud resource quotas
```

### ibmcloud resource quota
{: #ibmcloud_resource_quota}

显示配额定义的详细信息

```
ibmcloud resource quota NAME
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>配额的名称</dd>
</dl>

<strong>示例</strong>：显示配额 `free` 的详细信息：

```
ibmcloud resource quota free
```

### ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

将 Cloudfoundry 服务实例迁移到资源组

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

### ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

列出服务实例

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
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
</dl>

<strong>示例</strong>：

列出服务 `test-service` 的服务实例：

```
ibmcloud resource service-instances --service-name test-service
```

### ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

显示服务实例的详细信息

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
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
</dl>

<strong>示例</strong>：

显示服务实例 `my-service-instance` 的详细信息：

```
ibmcloud resource service-instance my-service-instance
``` 

### ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

创建服务实例

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务实例的名称</dd>
  <dt>SERVICE_NAME 或 SERVICE_ID（必需）</dt>
  <dd>服务的名称或标识</dd>
  <dt>SERVICE_PLAN_NAME 或 SERVICE_PLAN_ID（必需）</dt>
  <dd>服务套餐的名称或标识</dd>
  <dt>LOCATION</dt>
  <dd>用于创建服务实例的目标位置或环境</dd>
  <dt>-t, --tags</dt>
  <dd>标记</dd>
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

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

更新服务实例

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必填）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必填）</dt>
  <dd>服务实例的 ID，与 NAME 互斥 </dd>
  <dt>-n, --name</dt>
  <dd>新服务实例名称</dd>
  <dt>-t, --tags</dt>
  <dd>新标记</dd>
  <dt>--service-plan-id</dt>
  <dd>新服务套餐标识</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：
更新服务实例 `my-service-instance`，将其名称更改为 `new-service-instance`：

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

### ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

删除服务实例

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>Name（必填）</dt>
  <dd>服务实例的名称，与 ID 互斥 </dd>
  <dt>ID（必填）</dt>
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

### ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

显示与服务别名的绑定

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ALIAS（必需）</dt>
  <dd>服务别名</dd>
</dl>

<strong>示例</strong>：
显示与服务别名 `my-service-alias` 的资源绑定：

```
ibmcloud resource bindings my-service-alias
```

### ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

显示服务绑定的详细信息

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry 应用程序名称</dd>
  <dt>--id</dt>
  <dd>仅显示标识。将禁止服务绑定的所有其他输出。</dd>
</dl>

<strong>示例</strong>：
显示服务别名 `my-service-alias` 和应用程序 `my-app` 之间的服务绑定的详细信息：

```
ibmcloud resource bindings my-service-alias my-app
```

### ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

创建服务绑定

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

### ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

删除服务绑定

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

### ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

列出服务实例或服务别名的服务密钥

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
</dl>

<strong>示例</strong>：
列出服务实例 `my-service-instance` 的服务密钥：

```
ibmcloud resource service-keys --instance-name my-service-instance
```

### ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

显示服务密钥的详细信息

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>键的名称</dd>
  <dt>--id</dt>
  <dd>显示服务密钥的标识</dd>
</dl>

<strong>示例</strong>：
显示服务密钥 `my-service-key` 的详细信息：

```
ibmcloud resource service-key my-service-key
```

### ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

创建服务密钥

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME</dt>
  <dd>键的名称</dd>
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

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

删除服务密钥

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>KEY_NAME</dt>
  <dd>键的名称</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：
删除服务密钥 `my-service-key`：

```
ibmcloud resource service-key-delete my-service-key
```

### ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

列出服务实例的别名

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--instance-id</dt>
  <dd>所属服务实例的标识。</dd>
  <dt>--instance-name</dt>
  <dd>所属服务实例的名称。</dd>
</dl>

<strong>示例</strong>：
列出服务实例 `my-service-instance` 的服务别名：
```
ibmcloud resource service-aliases my-service-instance
```

### ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

显示服务别名的详细信息

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>ALIAS_NAME（必需）</dt>
  <dd>服务别名的名称</dd>
  <dt>--id</dt>
  <dd>仅显示给定服务别名的标识。将禁止别名的所有其他输出。</dd>
</dl>

<strong>示例</strong>：
显示服务别名 `my-service-alias` 的详细信息：
```
ibmcloud resource service-alias  my-service-alias
```

### ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

创建服务实例的别名

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

### ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

更新服务别名

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

### ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

删除服务别名

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

### ibmcloud resource search
{: #ibmcloud_resource_search}
使用 Lucene 查询语法搜索资源

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-offset, --o</dt>
  <dd>起始资源位置编号</dd>
  <dt>-limit, --l</dt>
  <dd>要返回的资源数（最多 10000 个）</dd>
</dl>

<strong>示例</strong>：
搜索其名称以指定文本开头的 Cloud Foundry 应用程序：

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

### ibmcloud resource tags
{: #ibmcloud_resource_tags}

列出所有标记

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-type</dt>
  <dd>标记类型（支持的值：user、restricted）</dd>
  <dt>-o, --offset</dt>
  <dd>起始资源位置编号（缺省值：0）</dd>
  <dt>-l, --limit</dt>
  <dd>要返回的资源数（最多 10000 个）（缺省值：10000）</dd>
</dl>

<strong>示例</strong>：

列出所有标记

```
ibmcloud resource tags 
```

列出所有 restricted 标记

```
ibmcloud resource tags --tag-type restricted
```

### ibmcloud resource tag
{: #ibmcloud_resource_tag}

显示标记详细信息

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
</dl>

<strong>示例</strong>：

显示标记“Ray Brown”的详细信息

```
ibmcloud resource tag --tag-name "Ray Brown"
```

### ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

创建标记

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称</dd>
  <dt>--tag-type</dt>
  <dd>标记类型（支持的值：user、restricted；缺省值为 user）</dd>
</dl>

<strong>示例</strong>：

创建名称为 think:2018 的 user 标记

```
ibmcloud resource tag-create --tag-name think:2018
```

创建名称为 department:marketing 的 restricted 标记

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

创建名称为“Ray Brown”的 user 标记

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

创建名称为“environment:My Development”的 restricted 标记

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

### ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

删除标记

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
</dl>

<strong>示例</strong>：

删除标记“Ray Brown”

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

### ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

向资源添加标记

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--resource-crn（必填）</dt>
  <dd>资源 CRN</dd>
</dl>

<strong>示例</strong>：

向 crn 为 resource_example_crn 的资源添加标记“Ray Brown”。

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

从资源除去标记

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--resource-crn（必填）</dt>
  <dd>资源 CRN</dd>
</dl>

<strong>示例</strong>：

除去 crn 为 resource_example_crn 的资源的标记“Ray Brown”。

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

从 user 标记切换到 restricted 标记，反之亦然

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--tag-name（必填）</dt>
  <dd>标记名称，与 --tag-crn 互斥 </dd>
  <dt>--tag-crn（必填）</dt>
  <dd>标记 CRN，与 --tag-name 互斥 </dd>
  <dt>--tag-type（必填）</dt>
  <dd>标记类型</dd>
</dl>

<strong>示例</strong>：

从标记“Ray Brown”切换到 restricted 标记

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
