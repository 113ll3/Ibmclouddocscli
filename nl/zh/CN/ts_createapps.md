---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# 有关 {{site.data.keyword.cloud_notm}} Developer Tools CLI 插件的故障诊断
{: #troubleshoot}

使用 {{site.data.keyword.dev_cli_short}} 命令行界面 (CLI) 创建应用程序的常见问题可能包括部署失败或者无法检索的代码。在许多情况下，只需执行几个简单的步骤即可解决这些问题。
{: shortdesc}

## 我使用非移动模式创建应用程序时，为什么会收到主机名错误？
{: #ts-cli-hostname-error}
{: troubleshoot}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 将应用程序部署到 Cloud Foundry，那么可能会显示以下错误。即使您输入的主机名是唯一的，也仍然可能会看到此消息。
```
主机名 <myHostname> 已采用。
```
{: screen}
{: tsSymptoms}

导致此错误的原因是登录令牌已到期。
{: tsCauses}

运行以下命令重新登录：
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 为什么我会收到一般命令故障？
{: #ts-cli-general-failures}
{: troubleshoot}

如果使用 `create`、`delete`、`list` 或 `code` 命令，那么可能会显示以下错误：
```
对应用程序执行 <command> 失败。
```
{: screen}
{: tsSymptoms}

导致此错误的原因是登录令牌已到期。
{: tsCauses}

运行以下命令重新登录：
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 为什么无法识别新应用程序的映像？
{: #ts-cli-nosuchimage}
{: troubleshoot}

如果没有先构建应用程序就尝试对其运行 `ibmcloud dev run`，那么可能会显示以下错误。
```
未指定 run-cmd 选项
正在停止“testProject”容器...
找不到“testProject”容器
正在基于 Dockerfile 创建映像 ibmcloud-dev-testProject...
正常
正在基于该映像创建名为“testProject”的容器...
失败
无法创建“testProject”容器：
错误：没有此类映像：ibmcloud-dev-testProject
```
{: screen}
{: tsSymptoms}

必须先构建应用程序，然后才能运行应用程序。
在当前应用程序目录中运行以下命令：
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

在当前应用程序目录中运行以下命令来启动应用程序：
```
ibmcloud dev run
```
{: tsResolve}

## 为什么我在添加 {{site.data.keyword.objectstorageshort}} 功能时收到了服务代理程序错误？
{: #ts-cli-object-storage}
{: troubleshoot}

如果使用 CLI 来创建具有 {{site.data.keyword.objectstorageshort}} 功能的两个应用程序，那么可能会显示以下错误：

```
失败
代理程序错误：{"description"=>"无法创建此 Object Storage 实例。每个使用 Object Storage 服务的组织在免费套餐中只能使用一个实例。"}
```
{: screen}
{: tsSymptoms}

导致此错误的原因是 {{site.data.keyword.objectstorageshort}} 服务仅在免费套餐中提供一个 {{site.data.keyword.objectstorageshort}} 实例。
{: tsCauses}

请选择其他套餐。
{: tsResolve}

## 为什么在我创建应用程序时未检索我的代码？
{: #retrieve-code-error}
{: troubleshoot}

如果使用 CLI 来创建应用程序，那么可能会显示以下错误：
```
FAILED                            
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

导致此错误的原因是内部超时。
{: tsCauses}

使用以下某种方法来获取代码：

* 运行以下命令：

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   将 `<your-app-name>` 替换为您在应用程序创建期间指定的应用程序名称。

* 使用 {{site.data.keyword.dev_console}}。

	1. 在 {{site.data.keyword.dev_console}} 中选择您的[应用程序 ](https://cloud.ibm.com/resources){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

	2. 单击**下载代码**。
{: tsResolve}

## 为什么不能对 Node.js 应用程序运行 `ibmcloud dev run` 命令？
{: #ts-cli-node}
{: troubleshoot}

如果对 Node.js Web 或 BFF 应用程序运行 `ibmcloud dev run` 命令，那么可能会显示以下错误：

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

错误：/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: ELF 头无效
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: screen}
{: tsSymptoms}

`appmetrics` 模块安装在其他体系结构上时，会发生此错误。安装在一个体系结构上的本机 npm 模块不能在另一个体系结构上运行。包含的 Docker 映像基于 Linux 内核。
{: tsCauses}

删除 `node_modules` 文件夹，然后再次运行 `ibmcloud dev run` 命令。
{: tsResolve}

## 为什么无法部署到 {{site.data.keyword.cloud_notm}}？
{: #ts-cli-deploy-issues}
{: troubleshoot}

尝试部署到 {{site.data.keyword.cloud_notm}} 时失败，但未显示任何错误。
{: tsSymptoms}

您可能未登录到帐户。
{: tsCauses}

运行以下命令来登录并重试。
```
ibmcloud login
```
{: tsResolve}

## 为什么无法在 {{site.data.keyword.cloud_notm}} 上部署 Kubernetes？
{: #ts-cli-kube-deploy}
{: troubleshoot}

在提示您输入集群名称后，可能会显示以下故障：
```
失败
未能执行操作：退出状态 1：

失败
未能配置对集群“<cluster-name>”的部署，原因是：退出状态 1
```
{: screen}
{: tsSymptoms}

最有可能导致此错误的原因是集群名称无效。可以通过运行带 `--trace` 的相同命令来确认原因，并且错误输出中可能包含以下详细信息：
```
失败，错误为：{"incidentID":"<id-number>","code":"E0008","description":"找不到指定的集群。","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"正在供应"}
```
{: screen}
{: tsCauses}

确保使用的是正确集群，并且已通过运行以下命令将该集群配置用于部署：
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## 为什么我无法部署映像目标？
{: #ts-deploy-image-target}
{: troubleshoot}

在系统提示您提供部署映像目标后，可能会显示以下故障：
```
失败
无法执行操作：退出状态 1：已拒绝：请求对资源的访问被拒绝


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

最有可能导致此错误的原因是部署映像目标无效。更具体地说，名称空间（即部署映像目标中的中间值）可能无效。
{: tsCauses}

确保部署映像目标中的名称空间与在运行以下命令时显示的其中一个名称空间相匹配：
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## 为什么无法确定我的应用程序的语言？
{: #ts-cli-determine-language}
{: troubleshoot}

在尝试启动应用程序时，可能会显示以下故障：
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

此错误可能是以下某个原因导致的：
- 从不是应用程序源目录的目录中运行 [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 命令。
- 对无法识别其语言的应用程序运行 [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 命令。
{: tsCauses}

请确保从包含应用程序源代码的应用程序目录中运行该命令。如果仍未解决此问题，而该语言是[受支持的语言](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options)，请使用 `--language` 参数指定语言。
{: tsResolve}

## 为什么我无法构建或运行已针对云部署启用的应用程序？
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

尝试[构建](/docs/cli/idt?topic=cloud-cli-idt-cli#build)或[运行](/docs/cli/idt?topic=cloud-cli-idt-cli#run)已启用的应用程序时，可能会遇到各种故障。
{: tsSymptoms}

在以下每个链接中，可以找到多种不同的可能原因。
{: tsCauses}

- 有关如何使用 Spring 应用程序解决此类问题的更多信息，请参阅[针对云部署启用现有 Spring Boot 应用程序](/docs/java-spring?topic=java-spring-enable_existing#enable_existing)。
- 有关如何使用 `Node.js` 应用程序解决此类问题的更多信息，请参阅[针对云部署启用现有 Node.js 应用程序](/docs/node?topic=nodejs-enable_existing#enable_existing)。
{: tsResolve}

## 如何单独手动安装 {{site.data.keyword.dev_cli_notm}} CLI 组件
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

要单独手动安装 {{site.data.keyword.dev_cli_notm}} CLI 组件，可以执行以下[步骤](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually)。

## 为什么我无法构建 Docker 映像？
{: $ts-cli-docker}
{: troubleshoot}

如果看到以下错误： 
```
FAILED
An error exit status 1 was encountered while building the Docker 
image.
```
{: screen}

此错误可能是以下某个原因导致的：
- Docker 未安装。
- Docker 守护程序未在运行。
{: tsCauses}

确保 Docker 已安装并正在运行：
- 要安装或启动 [Docker for Mac](https://docs.docker.com/docker-for-mac/install/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
- 要安装或启动 [Docker for Windows](https://docs.docker.com/docker-for-windows/install/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
- 要安装或启动 [Docker for Linux](https://docs.docker.com/v17.12/install/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
{: tsResolve}

## 如何解决 helm 版本不兼容的问题？
{: ts-cli-helm}
{: troubleshoot}

如果客户机和服务器的 helm 版本不同步，那么可能会看到以下错误：
```
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED: 
configmaps is forbidden: User "system:serviceaccount:kube-system:default" 
cannot list resource "configmaps" in API group "" in the namespace 
"kube-system"
```
{: screen}

```
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

要解决此问题，请将客户机版本设置为与集群版本相同。例如，要安装 2.8.1 helm 版本，请运行以下命令：
{: tsResolve}

* 对于 Mac 和 Linux，请运行以下命令：
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* 对于 Windows，以管理员身份执行以下操作：
  下载并安装 `helm` 二进制文件：[https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。
  
  在 PowerShell 终端中，使用以下命令：
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```

## 为什么使用包含“@”的用户名时 ibmcloud dev 构建会失败？
{: ts-cli-username}
{: troubleshoot}
在映像构建过程中，您的用户名用于 Docker 工具映像中的用户。如果用户名包含诸如“@”或“-”的任何特殊字符，那么 Docker 映像构建过程会失败，并且可能会发生以下错误：
```
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Dumping output from the command:
```
{: screen}

要解决此问题，请将您的用户名更改为不包含任何特殊字符，或者指定以下标志以改为使用 root 用户：
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
