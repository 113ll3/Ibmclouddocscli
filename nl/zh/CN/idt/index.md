---
copyright:

  years: 2018

lastupdated: "2018-06-27"

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

1. [创建或启用应用程序](#create)
2. 使用容器在本地对应用程序进行[编码、构建和运行](#build)
3. 将应用程序[部署](#deploy)到 {{site.data.keyword.Bluemix_notm}}

## 创建或启用应用程序
{: #create}

可以通过多种方式来创建云应用程序。
- [应用程序服务 Web 控制台](https://console.bluemix.net/developer/appservice)，用于通用 Web 应用程序和微服务。
- [Watson 仪表板](https://console.bluemix.net/dashboard/watson)，用于创建支持基于 Watson 的功能的入门模板应用程序。
    - {{site.data.keyword.Bluemix_notm}} 主页上的“汉堡包”菜单中提供了其他基于行业和技术的仪表板。所有这些仪表板都采用类似的方法使用初学者工具包来创建新的应用程序。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev create`](./commands.html#create) 命令，用于创建新应用程序。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev enable`](./commands.html#enable) 命令，用于快速在现有服务器端应用程序上启用云。

对于上面的任何创建方法，流程都是类似的。您可以选择要使用的项目类型、实现语言和应用程序模式。还可以选择向应用程序添加增值服务，例如认证或持久性。最后，您可以选择对该应用程序启用 DevOps 功能，以提供源代码控制和团队通信的完整工具链，以及每次落实时触发的管道，用于验证和构建应用程序并将其部署到 IBM Cloud。

![使用 IDT CLI 的样本创建流](create_flow.png "使用 IDT CLI 的样本创建流") <br> 图 2. 使用 IDT CLI 的样本创建流

{{site.data.keyword.dev_cli_notm}} CLI 将紧密协作，以在开发过程中提供无缝的体验。在任一 Web 控制台中创建的项目都会提供“下载代码”按钮，用于将生成的源代码下载到工作站以进行更多开发。

### 有帮助的 CLI 命令
{: #helpful}

以下 CLI 命令可帮助使用项目和 Web 控制台：
- [`code`](./commands.html#code)，用于直接将应用程序的已生成源代码拉取到工作站
- [`console`](./commands.html#console)，用于打开浏览器，转至 {{site.data.keyword.Bluemix_notm}} 中当前应用程序的项目页面。
- [`create`](./commands.html#create) 命令，用于创建新应用程序。
- [`delete`](./commands.html#delete)，用于从 {{site.data.keyword.Bluemix_notm}} 项目区域中删除当前应用程序。
- [`enable`](./commands.html#enable) 命令，用于通过云启用现有服务器端应用程序。
- [`get-credentials`](./commands.html#get-credentials)，用于获取项目支持使用绑定服务时所需的凭证。
- [`list`](./commands.html#list)，通过 CLI 或控制台列出您在当前所选的组织/空间中创建的所有应用程序。


### 浏览应用程序的项目结构
{: #exploring-project}

为了与工具配合使用而创建或启用的项目随附了 `cli-config.yml` 文件中封装的预配置设置。`cli-config.yml` 包含工具命令使用的缺省条目，可由通过命令行传递的值覆盖。

可在以下位置找到有关项目结构的更多详细信息：
- [Java 项目](/docs/apps/projects/java_project_contents.html)
- [NodeJS 项目](/docs/apps/projects/node_project_contents.html)
- [Python 项目](/docs/apps/projects/python_project_contents.html)
- [Swift 项目](/docs/apps/projects/swift_project_contents.html)


### 参考博客和视频
{: #ref1}

- 视频：[在 Ubuntu Linux 上安装 IDT](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- 博客：[Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## 编码、构建和运行
{: #build}


一旦创建项目后，现在由您负责将其制作成有用的内容。一般流程包括编辑源代码，然后运行 [`ibmcloud dev build`](commands.html#build)，以在特定于应用程序语言和配置的本地容器中编译应用程序。根据使用的应用程序语言和生成器，有一个或多个容器缺省设置为支持在本地构建和运行。通常，会有一个“工具”容器用于构建和本地调试。此容器通常有额外的工具和功能，可帮助您进行开发。另外还有一个“运行”容器，密切模拟在 Cloud Foundry 或 IBM 基于 Kubernetes 的容器环境中已部署到云的应用程序的实际运行时环境。


您可以自由地使用偏爱的任何 IDE 或编辑器来对应用程序进行编码。我们提供了针对 Microsoft VisualStudio Code (VSCode) 编辑器的扩展，支持您直接在编辑器中访问所有 IDE 命令。

一旦构建项目后，接下来您需要使用 [`ibmcloud dev run`](commands.html#run) 或 [`ibmcloud dev debug`](commands.html#debug)（取决于应用程序生成器配置）来运行应用程序。这将在正确的容器内运行应用程序。某些应用程序模式支持应用程序外部的多个容器（例如，持久性或其他功能）。这些容器将在运行或调试期间自动启动并配置。还有一个 [`ibmcloud dev test`](commands.html#test) 命令，用于执行与应用程序关联的任何测试用例。


### 如何使用本地容器
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI 使用两个容器来帮助构建和测试应用程序。第一个是“工具”容器，包含用于构建和测试应用程序的必要实用程序。此容器的 Dockerfile 由 [`dockerfile-tools`](commands.html#command-parameters) 参数定义。您可将其视为开发容器，因为它包含正常用于开发特定运行时的工具。

第二个容器是“运行”容器。此容器的形式适合部署以供在 {{site.data.keyword.Bluemix}} 等中使用。因此，将定义用于启动应用程序的入口点。选择通过 {{site.data.keyword.dev_cli_short}} CLI 来运行应用程序时，它将使用此容器。此容器的 Dockerfile 由 [`dockerfile-run`](commands.html#run-parameters) 参数定义。


### 有帮助的 CLI 命令
{: #helpful2}

以下 CLI 命令可帮助在编码、构建和运行周期中使用项目：
- [`build`](./commands.html#build)，在本地容器中构建项目
- [`debug`](./commands.html#debug)，在本地容器中调试应用程序
- [`run`](./commands.html#run)，在本地容器中运行应用程序
- [`shell`](./commands.html#shell)，将 shell 打开到本地容器中
- [`status`](./commands.html#status)，检查 CLI 使用的容器的状态
- [`stop`](./commands.html#stop)，停止容器
- [`test`](./commands.html#test)，在本地容器中测试应用程序

### 参考博客和视频
{: #ref2}

- [调试本地应用程序](local_debug.html)





## 部署
{: #deploy}

在相应的云本机环境下，您将希望利用完整功能的 DevOps 管道来管理所有部署以及丰富的其他功能。在创建流的过程中，可以将应用程序设置为使用 IBM Cloud 的 DevOps。如果尚未准备好使用内置 DevOps，那么可以手动对应用程序运行 [`ibmcloud dev deploy`](./commands.html#deploy)，也可以在自己的 DevOps 管道中使用部署命令。  



### 有帮助的 CLI 命令
{: #helpful3}

以下 CLI 命令可帮助您在部署过程中使用项目：
- [`console`](./commands.html#console)，打开 IBM Cloud 控制台以使用项目
- [`deploy`](./commands.html#deploy)，将应用程序部署到 IBM Cloud
- [`view`](./commands.html#view)，查看项目的 URL


### 参考博客和视频
{: #ref3}

- 博客：[Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- 博客：[Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
