---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-21"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 开发和部署应用程序
{: #developing}

使用 {{site.data.keyword.dev_cli_notm}} CLI 开发云本机应用程序遵循相当简单的流程：

1. [创建或启用应用程序以进行部署](#idt-create)。
2. 使用容器在本地对应用程序进行[编码、构建和运行](#code-build-run)。
3. 将应用程序[部署](#cli-deploy)到 {{site.data.keyword.cloud_notm}}。

## 创建或启用应用程序以进行云部署
{: #idt-create}

您可以通过多种方式创建应用程序。
- [应用程序服务 Web 控制台](https://cloud.ibm.com/developer/appservice/dashboard)，用于通用 Web 应用程序和微服务。
- [Watson 仪表板](https://cloud.ibm.com/developer/watson/dashboard)，用于创建支持基于 Watson 的功能的入门模板应用程序。
    - {{site.data.keyword.cloud_notm}} 主页上的“汉堡包”菜单中提供了其他基于行业和技术的仪表板。所有这些仪表板都采用类似的方法使用入门模板工具包来创建新的应用程序。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) 命令，用于创建新应用程序。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 命令，用于快速在现有服务器端应用程序上启用云。

对于上面的任何创建方法，流程都是类似的。选择要使用的项目类型、实现语言和应用程序模式。还可以选择向应用程序添加服务，例如认证或持久性。最后，您可以为应用程序配置持续交付，用于提供源代码控制和团队通信的完整工具链，包括在每次落实时触发的管道，以验证和构建应用程序并将其部署到 {{site.data.keyword.cloud_notm}}。

![使用 {{site.data.keyword.dev_cli_notm}} CLI 的样本创建流](../images/create_flow.png "使用 {{site.data.keyword.dev_cli_notm}} CLI 的样本创建流") {{site.data.keyword.dev_cli_notm}} CLI 将紧密协作，以在开发过程中提供顺利的体验。在 Web 控制台中创建的项目会提供**下载代码**按钮，用于将生成的源代码下载到工作站以执行进一步开发。

### 有帮助的 CLI 命令
{: #helpful}

以下 `ibmcloud dev` CLI 命令可帮助使用项目和 Web 控制台：
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code)：用于将应用程序源代码下载到工作站。
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console)：在浏览器中打开 {{site.data.keyword.cloud_notm}} 中当前应用程序的项目页面。
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create)：此命令用于创建新应用程序。
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete)：用于从 {{site.data.keyword.cloud_notm}} 项目区域中删除当前应用程序。
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable)：此命令用于对现有服务器端应用程序进行云启用。
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials)：获取使项目支持使用绑定服务所需的凭证。
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list)：列出通过 CLI 或控制台在当前所选的组织和空间中创建的所有应用程序。

### 浏览应用程序的项目结构
{: #exploring-project}

为了与 Developer Tools 配合使用而创建或启用的项目随附了 `cli-config.yml` 文件中封装的预配置设置。`cli-config.yml` 具有 `ibmcloud dev` 命令使用的缺省条目，可由通过命令行传递的值覆盖。

### 参考博客和视频
{: #ref1}

- 视频：[在 Ubuntu Linux 上安装 {{site.data.keyword.cloud_notm}} Developer Tools&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
- 博客：[Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/cloud-archive/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli//){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

## 编码、构建和运行
{: #code-build-run}

创建项目后，您需要负责将其制作成有用的内容。一般流程包括编辑源代码，然后运行 [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build)，以在特定于应用程序语言和配置的本地容器中编译应用程序。根据使用的应用程序语言和生成器，有一个或多个容器缺省设置为支持在本地构建和运行。通常，会有一个“tools”容器用于构建和本地调试。此容器具有额外的工具和功能，可帮助您进行开发。另外还有一个“run”容器，它模拟应用程序在部署到云之后的运行时环境：Cloud Foundry 或 IBM 基于 Kubernetes 的容器环境。

您可以自由地使用自己偏好的任何 IDE 或编辑器来对应用程序进行编码。{{site.data.keyword.IBM_notm}} 提供了针对 Microsoft&trade; Visual Studio Code (VSCode) 编辑器的扩展，支持直接在编辑器中访问所有 IDE 命令。

构建项目后，使用 [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 或 [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) 来运行应用程序。应用程序将在相应的容器内运行。某些应用程序的模式支持使用应用程序外部的多个容器。这些应用程序将在运行或调试期间自动启动和配置。还有一个 [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) 命令，用于运行与应用程序相关联的任何测试用例。

### 如何使用本地容器
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI 使用两个容器来构建和测试应用程序。第一个是 tools 容器，包含用于构建和测试应用程序的必要实用程序。此容器的 Dockerfile 由 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 参数定义。您可将其视为开发容器，因为它包含通常用于开发特定运行时的工具。

第二个容器是 run 容器。此容器的形式适合部署以供在 {{site.data.keyword.cloud}} 等中使用。因此，将定义用于启动应用程序的入口点。选择通过 {{site.data.keyword.dev_cli_short}} CLI 来运行应用程序时，它将使用此容器。此容器的 Dockerfile 由 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) 参数定义。

### 有帮助的 CLI 命令
{: #helpful2}

以下 CLI 命令可帮助调试项目：
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build)：在本地容器中构建项目。
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug)：在本地容器中调试应用程序。
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run)：在本地容器中运行应用程序。
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell)：将 shell 打开到本地容器中。
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status)：检查 {{site.data.keyword.dev_cli_notm}} CLI 使用的容器的状态。
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop)：停止容器
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test)：在本地容器中测试应用程序。

### 调试本地应用程序
{: #ref2}

- [调试本地应用程序](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## 部署
{: #cli-deploy}

在适当的云本机环境下，您可使用完整功能的 DevOps 管道来管理所有部署以及丰富的其他功能。在创建流的过程中，可以将应用程序设置为使用 IBM Cloud 的 DevOps。如果尚未准备好使用内置 DevOps，那么可以手动运行 [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) 来部署应用程序，也可以在您自己的 DevOps 管道中使用 `deploy` 命令。

### 有帮助的 CLI 命令
{: #helpful3}

以下 CLI 命令可帮助您在部署过程中使用项目：
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console)：打开 {{site.data.keyword.cloud_notm}} 控制台以处理项目。
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy)：将应用程序部署到 {{site.data.keyword.cloud_notm}}。
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view)：查看项目的 URL。

### 参考博客和视频
{: #ref3}

- 博客：[Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/cloud/blog/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
- 博客：[Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/cloud-archive/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
