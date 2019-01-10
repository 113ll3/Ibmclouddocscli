---

copyright:

  years: 2017, 2018

lastupdated: "2018-11-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

针对 Visual Studio Code 的 IBM Cloud Developer Tools 扩展是一个编辑器扩展，可用于直接在 Visual Studio Code 编辑器的命令选用板内访问 IBM 开发者 CLI 中的功能。它支持快速访问适用于 Docker 和 CloudFoundry 工作流的 `ibmcloud dev` 命令子集，包括应用程序部署、在 {{site.data.keyword.Bluemix}} 上启动/停止/重新启动应用程序、查看远程应用程序日志等等，这一切操作都无需离开编辑器的上下文。
{:shortdesc}

![IBM Developer Tools 扩展下载屏幕的截屏。](vscode.png "Visual Studio Code 中的扩展下载屏幕")

## 依赖项
{: #dependencies}

要使用针对 Visual Studio Code 的 IBM Cloud Developer Tools 扩展，您需要 [{{site.data.keyword.Bluemix_notm}} CLI](/docs/cli/index.html#overview) 以及系统上安装的 {{site.data.keyword.Bluemix_notm}} CLI 插件。

## 安装
{: #installation}

最简单的 IBM Cloud Developers Tools 扩展安装方法是使用 Visual Studio Code 的“快速打开”命令：

1. 在编辑器中使用以下组合键打开“快速打开”命令选用板：

  * **Mac：**`cmd + p`
  * **Windows / Linux：**`ctrl + p`

2. 输入 `ext install ibm-developer` 命令，然后按 Enter 键以在 Visual Studio Code 编辑器中安装 IBM Cloud Developer Tools 扩展。

或者，可以通过“扩展”管理窗口来安装 IBM Cloud Developer Tools 扩展：

1. 打开 Visual Studio Code 编辑器内部的**扩展**侧边栏，然后使用字符串 `publisher:IBM Developer` 进行搜索。IBM Cloud Developer Tools 扩展将显示在搜索结果中。  
2. 单击**安装**按钮以开始安装。

您还可以[直接在 Visual Studio Code 的 Marketplace 中访问 IBM Cloud Developer Tools 扩展](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

## 用法
{: #usage}

可以使用 Visual Studio Code 的命令选用板来启动扩展命令。

首先，使用以下组合键打开命令选用板：

* **Mac：**`cmd + shift + p`
* **Windows / Linux：**`ctrl + shift + p`

接下来，输入或选择要启动的命令。可以在命令选用板中输入“ibmcloud”来查看所有可用命令的列表。

### 使用 IBM Developer Extension for Docker 工作流（Docker 容器）
{: #usage-docker}

只需几个步骤即可开始使用 `ibmcloud dev` 工作流：
* 使用以下两种方法之一来创建项目：
  * 使用 [{{site.data.keyword.Bluemix_notm}} Web 控制台](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 并下载生成的代码
  * 使用 {{site.data.keyword.Bluemix_notm}} Developer Tools CLI 插件，并使用 [ibmcloud dev create](/docs/cli/idt/commands.html#create) 命令生成项目。
* 在 Visual Studio Code 编辑器本地打开项目的文件夹
* 使用 `ibmcloud dev build` 命令将应用程序构建到 Docker 映像中
* 使用 `ibmcloud dev debug` 命令在本地 Docker 中运行应用程序以进行开发
> 注：要调试在本地 Docker 容器内运行的 Node.js 应用程序，需要[为本地容器添加调试配置](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。
* 使用 `ibmcloud dev run` 命令在本地 Docker 中以发布方式运行应用程序
* 使用 `ibmcloud dev deploy` 命令将应用程序部署到 {{site.data.keyword.Bluemix_notm}} 上的 Cloud Foundry 运行时

### 使用 IBM Developer Extension for Cloud Foundry 工作流
{: #usage-cloud-foundry}

对于当前正在将应用程序部署到 IBM {{site.data.keyword.Bluemix_notm}} 上的 Cloud Foundry 运行时的用户，还提供了对 `cf` 操作集的支持。

只需几个步骤即可开始使用 CloudFoundry 工作流：
* 创建新的 CloudFoundry 应用程序
  * 使用 [{{site.data.keyword.Bluemix_notm}} Web 控制台](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 并下载入门模板代码
  * 手动创建新的 CloudFoundry 应用程序
* 在 Visual Studio Code 编辑器本地打开项目文件夹
* 使用 `ibmcloud cf apps` 列出所有应用程序
* 使用 `ibmcloud cf push` 将应用程序的构建推送到 Cloud Foundry 运行时
* 使用 `ibmcloud cf <start/stop/restage/restart>` 更改应用程序的状态
* 使用 `ibmcloud cf logs` 查看应用程序的实时日志流
  * 使用 `ibmcloud cf logs` 停止日志流
