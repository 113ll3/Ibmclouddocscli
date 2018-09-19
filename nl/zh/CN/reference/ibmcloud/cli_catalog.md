---

copyright:

  years: 2018


lastupdated: "2018-09-04"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 目录
{: #ibmcloud_catalog}

使用以下命令可管理 {{site.data.keyword.Bluemix_notm}}“目录”。
{: shortdesc}

<table summary="可用于管理 {{site.data.keyword.Bluemix_notm}}“目录”的 ibmcloud 命令。">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_catalog.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_catalog.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_catalog.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_catalog.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_catalog.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_catalog.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_catalog.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_catalog.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_catalog.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_catalog.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_catalog.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_catalog.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_catalog.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_catalog.html#ibmcloud_catalog_runtimes)</td>
</tr>
 </tbody>
 </table>
  
  ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

搜索目录条目

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-r, --region</dt>
  <dd>指定要在其中进行搜索的地理区域。目前仅支持“us-south”和“united-kingdom”</dd>
  <dt>-k, --kind</dt>
  <dd>按资源种类过滤。目前仅支持“service-cf”、“iaas”、“runtime”、“template”和“dashboard”</dd>
  <dt>-p, --price</dt>
  <dd>按价格过滤。目前仅支持“free”、“paygo”和“bluemix-subscription”</dd>
  <dt>-t, --tag</dt>
  <dd>按标记过滤。</dd>
  <dt>--sort-by</dt>
  <dd>要作为排序依据的属性</dd>
  <dt>--col</dt>
  <dd>指定表的其他列。目前有“group”、“provider”和“tags”</dd>
  <dt>--reverse</dt>
  <dd>是否反转排序顺序</dd>
  <dt>--json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>--csv</dt>
  <dd>输出 CSV 文件</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

搜索服务 `Automation test`：

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

获取目录条目

```
ibmcloud catalog entry ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--children</dt>
  <dd>获取目录条目的所有子代</dd>
  <dt>--json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

获取标识为 `a0ef1-d3b4j0` 的条目：

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
创建新的目录条目（仅限帐户的目录管理员）

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-p, --parent</dt>
  <dd>对象的父标识</dd>
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件创建父标识为 `a0ef1-d3b4j0` 资源：

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
更新现有目录条目（仅限帐户的目录管理员或编辑者）

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件更新资源 `j402-dnf1i`：

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
删除目录条目（仅限帐户的目录管理员）
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

删除资源 `j402 - dnf1i`：

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
获取目录条目的可视性（仅限帐户的目录管理员）

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-json</dt>
  <dd>输出原始 JSON 响应</dd>
  <dt>-global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

获取资源 `j402-dnf1i` 在全球范围的可视性：

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
更新现有目录条目的可视性（仅限帐户的目录管理员）

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>

  <dt>--includes-add</dt>
  <dd>将帐户（或逗号分隔帐户列表）添加到“包含”列表，授予该条目可视性。可接受电子邮件或帐户 GUID</dd>
  <dt>--includes-remove</dt>
  <dd>从“包含”列表中除去帐户（或逗号分隔帐户列表），撤销该条目的可视性。可接受电子邮件或帐户 GUID</dd>  
  <dt>--excludes-add</dt>
  <dd>将帐户（或逗号分隔帐户列表）添加到“排除”列表。可接受电子邮件或帐户 GUID</dd>
  <dt>--excludes-remove</dt>
  <dd>从“排除”列表中除去帐户（或逗号分隔帐户列表），撤销该条目的可视性。如果帐户是由全局管理员设置的，那么帐户管理员无法除去该帐户。可接受电子邮件或帐户 GUID</dd>
  <dt>--owner</dt>
  <dd>更改对象的所有者。可接受电子邮件或帐户 GUID。</dd>
  <dt>--restrict</dt>
  <dd>将可视性对象的限制更改为“专用”</dd>
  <dt>--unrestrict</dt>
  <dd>将可视性对象的限制更改为“公共”</dd>  
  <dt>-c</dt>
  <dd>包含特定于目录的配置参数的有效 JSON 对象，以内联方式或文件形式提供。要获取受支持的配置参数的列表，请参阅特定目录条目的文档。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件设置资源 `j402-dnf1i` 的可视性：

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
列出市场中的服务产品

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--cf</dt>
  <dd>仅显示 Cloud Foundry 服务</dd>
  <dt>--rc</dt>
  <dd>仅显示 RC 兼容服务</dd>
  <dt>--global</dt>
  <dd>在全球范围运行</dd>
</dl>

<strong>示例</strong>：

显示全球范围的服务产品：

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

查看 {{site.data.keyword.Bluemix_notm}} 上的样板模板。

```
ibmcloud catalog templates [-d]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>-d（可选）</dt>
   <dd>如果指定了 <i>-d</i> 选项，那么还会显示每个模板的描述。否则，只显示每个模板的标识和名称。</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

查看指定样板模板的详细信息。

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>TEMPLATE_ID（必需）</dt>
   <dd>样板模板的标识。使用 <i>ibmcloud templates</i> 可查看所有模板的标识。</dd>
   </dl>


<strong>示例</strong>：

查看模板 `mobileBackendStarter` 的详细信息：

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

使用指定 URL 和描述基于指定模板创建 cf 应用程序。缺省情况下，新应用程序将自动启动。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
   <dl>
   <dt>TEMPLATE_ID（必需）</dt>
   <dd>创建应用程序时将基于的模板。使用 <i>ibmcloud templates</i> 可查看所有模板的标识。</dd>
   <dt>CF_APP_NAME（必需）</dt>
   <dd>要创建的 cf 应用程序的名称。</dd>
   <dt>-u <i>URL</i>（可选）</dt>
   <dd>应用程序的路径。如果未指定，路径将由 {{site.data.keyword.Bluemix_notm}} 根据您的应用程序名称和缺省域自动设置。</dd>
   <dt>-d <i>DESCRIPTION</i>（可选）</dt>
   <dd>应用程序的描述。</dd>
   <dt>--no-start（可选）</dt>
   <dd>应用程序创建后不自动启动。如果未指定，应用程序创建后将自动启动。</dd>
   </dl>


<strong>示例</strong>：

基于 `javaHelloWorld` 模板创建 cf 应用程序 `my-app`：

```
ibmcloud catalog template-run javaHelloWorld my-app
```

基于 `rubyHelloWorld` 模板创建应用程序 `my-ruby-app`，路径为 `myrubyapp.chinabluemix.net`，描述为 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`：

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

基于 `pythonHelloWorld` 模板创建应用程序 `my-python-app`，不带自动启动：

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

以您选择的格式获取区域选项子集。

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>命令选项</strong>：

<dl>
  <dt>-i, --id</dt>
  <dd>按标识指定地理位置。</dd>
  <dt>-k, --kind</dt>
  <dd>获取指定种类的条目列表。</dd>
  <dt>--col</dt>
  <dd>指定表的其他列。目前有“group”、“provider”和“tags”。</dd>
  <dt>--json</dt>
  <dd>原始 JSON 响应的输出。</dd>
  <dt>--global</dt>
  <dd>在全球范围运行。</dd>
  <dt>--csv</dt>
  <dd>输出 CSV 文件</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

查看运行时的详细信息。此命令仅可用于公共云。

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>示例</strong>：

显示运行时“nodejsHelloWorld”的详细信息：

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

列出所有运行时。此命令仅可用于公共云。

```
ibmcloud catalog runtimes [-d]
```

<strong>命令选项</strong>：

<dl>
  <dt>-d</dt>
  <dd>显示每个运行时的描述</dd>
</dl>

<strong>示例</strong>：

列出所有运行时及其描述：

```
ibmcloud catalog runtimes -d
```
