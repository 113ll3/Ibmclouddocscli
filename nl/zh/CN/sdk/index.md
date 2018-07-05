---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK Generator
{: #sdk-cli}

可以在 [{{site.data.keyword.Bluemix_notm}} CLI ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](/docs/cli/reference/bluemix_cli/all_versions.html) 中安装 {{site.data.keyword.IBM}} SDK Generator 插件。

作为 {{site.data.keyword.Bluemix_notm}} 上的开发者，您可以使用此插件通过符合 [Open API 规范 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.openapis.org/) 的 REST API 定义来生成 SDK。对 REST API 定义进行更改后，可以使用此插件来仅重新生成 SDK，而不重新生成整个项目。

您还可以查看特定空间中的 Cloud Foundry 应用程序是否具有对于生成 SDK 有效的 REST API 定义。最后，您可以使用 {{site.data.keyword.IBM_notm}} SDK Generator 插件来验证任何 REST API 定义，以确保这些定义符合 SDK Generator 的需求。

通过此 {{site.data.keyword.IBM_notm}} SDK Generator 插件，您可以轻松将应用程序的后端服务与生成的 SDK 集成在一起。对 REST API 进行更改后，可以重新生成 SDK，并替换旧的 SDK，以实现 SDK 升级。还可以将 CLI 集成到 DevOps 管道中，并确保每次构建应用程序时，SDK 始终与 API 规范一致。

REST API 定义必须有效，并且在实时服务器端点上或在系统上的本地文件中托管。如果托管了 REST API 定义，那么必须在 `OPENAPI_SPEC` 环境变量中定义相对 URL。


## 需求
{: #prereqs}

确保满足以下需求。

* 您具有 [{{site.data.keyword.Bluemix_notm}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://bluemix.net) 帐户
* 符合 [Open API ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.openapis.org/) 规范的有效 API 定义


## 安装
{: #installation}

1. [安装 {{site.data.keyword.Bluemix}} CLI ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://clis.ng.bluemix.net/ui/home.html)。

2. [安装插件 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](/docs/cli/reference/bluemix_cli/all_versions.html#install_plug-in)。

	```
	ibmcloud plugin install sdk-gen
	```
	{: codeblock}


## 命令
{: #commands}

使用以下命令来生成 SDK，验证 Open API 定义文件或列出 Cloud Foundry 应用程序。


### 生成 SDK
{: #gen}

使用 `ibmcloud sdk generate [arguments...] [command options]`。


#### 自变量
{: #gen-args}

* `APP_NAME` - 当前空间中 Cloud Foundry 应用程序的名称
* `OPENAPI_DOC_LOCATION` - 原始 REST API 定义 JSON 或 YAML 的 URL 或相对文件路径
* `GENERATED_SDK_NAME`（可选）- 生成的 SDK 的名称


#### 选项
{: #gen-options}

* `PLATFORM`（必需）
   * `--android` - 生成 Android SDK
   * `--ios` - 生成 iOS Swift SDK
   * `--swift` - 生成 Swift 服务器 SDK
   * `--js` - 生成 JavaScript SDK
* `LOCATION`（必需）- 为 `OPENAPI_DOC_LOCATION` 指定类型
   * `-r` - 远程 URL
   * `-f` - 文件
   * `-a` - 在 {{site.data.keyword.Bluemix_notm}} 上运行的应用程序
   * `-l` - 本地主机 URL
* `--output "YOUR_RELATIVE_PATH"`（可选）- 将生成的 SDK 放入 `YOUR_RELATIVE_PATH` 所指定的目录中（如果存在现有 SDK，将进行覆盖）
* `--unzip`（可选）- 解压缩生成的 SDK（如果存在现有 SDK 工件，将进行覆盖）


#### 用法
{: #gen-usage}

要从在 {{site.data.keyword.Bluemix_notm}} 中运行的 Cloud Foundry 应用程序生成 SDK，可以将应用程序的名称用作 CLI 的参数。以下命令使用应用程序名称作为 `SDK_Name`。

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

要通过指向 Open API 定义文件或者本地 JSON 或 YAML 文件的 URL 生成 SDK，请使用以下命令。

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### 验证开放式 API 定义
{: #validating}

使用 `ibmcloud sdk validate [argument]`。


#### 自变量
{: #val-args}

* `APP_NAME` - 当前空间中 Cloud Foundry 应用程序的名称
* `OPENAPI_DOC_LOCATION` - 原始 REST API 定义 JSON 或 YAML 的 URL 或相对文件路径


#### 用法
{: #val-usage}

要验证在 {{site.data.keyword.Bluemix_notm}} 中运行的 Cloud Foundry 应用程序的 API 规范，可以将应用程序的名称用作 CLI 的参数。

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

要通过指向 API 规范文档或者本地 JSON 或 YAML 文件的 URL 验证 SDK，请使用以下命令。

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### 列出应用程序 (Cloud Foundry)
{: #list-apps}

使用 `ibmcloud sdk list [argument] [option]` 可列出应用程序并验证 API 规范。必须将 `OPENAPI_SPEC` 环境变量设置为托管规范的路径的相对 URL。


#### 自变量
{: #list-args}

* `SPACE_NAME`（可选）- 当前组织内要在其中搜索应用程序的 Cloud Foundry 空间的名称。如果未提供，那么将搜索当前空间。


#### 选项
{: #list-options}

* `--url`（可选）- 为列表中的每个应用程序显示 Open API 定义的完整格式 URL


#### 用法
{: #list-usage}

要列出当前空间中的应用程序，请使用以下命令。

```
ibmcloud sdk list
```
{: codeblock}

要列出当前空间中的应用程序并显示 API 规范 URL，请使用以下命令。

```
ibmcloud sdk list --url
```
{: codeblock}

要列出特定空间中的应用程序，请使用以下命令。

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

要列出特定空间中的应用程序并显示 API 规范 URL，请使用以下命令。

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
