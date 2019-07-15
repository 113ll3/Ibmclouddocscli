---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 用于 JetBrains IDE 的 IBM Cloud Developer Tools
{: #ibm-dev-tools-for-jetbrains}

用于 JetBrains IDE（包括 `IntelliJ`、`WebStorm` 和 `Android Studio` 等）的 {{site.data.keyword.cloud}} Developer Tools 扩展提供了用于从 IDE 中直接访问 {{site.data.keyword.dev_cli_notm}} CLI 命令的新菜单项。您可以快速访问适用于 Docker 和 Cloud Foundry 工作流程的 `ibmcloud dev` 命令子集，包括应用程序部署、在 {{site.data.keyword.cloud_notm}} 上启动/停止/重新启动应用程序、查看远程应用程序日志等等。这一切操作都无需离开编辑器的上下文环境。
{: shortdesc}

![在 WebStorm IDE 中运行的 IBM Cloud Developer Tools 的截屏。](../images/jetbrains.png "在 WebStorm IDE 中运行的 {{site.data.keyword.cloud_notm}} Developer Tools 菜单示例")

## 依赖项
{: #jetbrains-dependencies}

要使用适用于基于 JetBrains 的 IDE 的 {{site.data.keyword.cloud_notm}} Developer Tools 扩展，还需要在系统上安装 [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started)。

## 安装
{: #jetbrains-installation}

安装适用于 JetBrains IDE 的 {{site.data.keyword.cloud_notm}} Developer Tools 扩展的最佳方法是转至 [{{site.data.keyword.cloud_notm}} Developer Tools GitHub 存储库的 JetBrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 页面，然后按照相关指示信息进行操作。

## 用法
{: #jetbrains-usage}

您可以从现有服务器端应用程序开始，针对云来启用该应用程序，或使用 {{site.data.keyword.dev_cli_notm}} CLI 通过入门模板工具包 (`ibmcloud dev create`) 创建新应用程序。有了应用程序的项目后，请在 JetBrains IDE 中将其打开。

要对通用服务器端应用程序进行云启用，请选择**工具** > **IBM Cloud Developer Tools** > **针对 {{site.data.keyword.cloud_notm}} 启用应用程序**。这将检查所有必需的文件，然后添加这些文件（如果需要）以通过 Cloud Foundry 应用程序部署到 {{site.data.keyword.cloud_notm}}，或者部署到 Kubernetes 集群中。

使用 {{site.data.keyword.cloud_notm}} Developer Tools 菜单中的基本构建、运行和部署操作来开发云本机应用程序。如果需要执行的操作不在菜单中，只需打开“终端”选项卡并手动输入命令即可。
