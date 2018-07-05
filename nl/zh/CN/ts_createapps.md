---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

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

# 有关 {{site.data.keyword.Bluemix_notm}} Developer Tools 的故障诊断
{: #troubleshoot}

使用 {{site.data.keyword.dev_cli_short}} CLI 创建应用程序的常见问题可能包括部署失败，或者在创建应用程序时无法检索代码。在许多情况下，只需执行几个简单的步骤即可解决这些问题。
{:shortdesc}

## 使用非移动模式创建应用程序时发生主机名错误
{: #hostname-error}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 将应用程序部署到 Cloud Foundry，那么可能会看到以下错误。即使您确信输入的主机名是唯一的，也仍然可能会看到此消息。

```
主机名 <myHostname> 已占用。
```
{: codeblock}
{: tsSymptoms}

导致此错误的原因是登录令牌已到期。
{: tsCauses}

请重新登录。

```
bx login
```
{: codeblock}
{: tsResolve}

## 有关 {{site.data.keyword.dev_cli_short}} CLI 的常见故障
{: #general}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 的 `create`、`delete`、`list` 或 `code` 命令，那么可能会看到以下错误：

```
对应用程序执行 <command> 失败。
```
{: codeblock}
{: tsSymptoms}

导致此错误的原因是登录令牌已到期。
{: tsCauses}

请重新登录。

```
bx login
```
{: codeblock}
{: tsResolve}

## 运行新应用程序时遇到“错误：没有此类映像”
{: #nosuchimage}

如果没有先构建应用程序就运行应用程序，那么可能会看到以下错误。

```
$ bx dev run
未指定 run-cmd 选项
正在停止“testProject”容器...
找不到“testProject”容器
正在基于 Dockerfile 创建映像 bx-dev-testProject...
正常
正在基于该映像创建名为“testProject”的容器...
失败
无法创建容器“testProject”：
错误：没有此类映像：bx-dev-testProject
```
{: tsSymptoms}

必须先构建应用程序，然后才能运行应用程序。
{: tsCauses}

在当前应用程序目录中运行以下命令来构建应用程序：

```
bx dev build
```
{: codeblock}

在当前应用程序目录中运行以下命令来启动应用程序：

```
bx dev run
```
{: tsResolve}

## 添加 {{site.data.keyword.objectstorageshort}} 功能时发生服务代理程序错误
{: #os}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 来创建具有 {{site.data.keyword.objectstorageshort}} 功能的两个应用程序，那么可能会看到以下错误：

```
失败
代理程序错误：{"description"=>"无法创建此 Object Storage 实例。每个使用 Object Storage 服务的组织在免费套餐中只能使用一个实例。"}
```
{: codeblock}
{: tsSymptoms}

导致此错误的原因是 {{site.data.keyword.objectstorageshort}} 服务仅在免费套餐中提供一个 {{site.data.keyword.objectstorageshort}} 实例。
{: tsCauses}

系统会提示您选择其他套餐以避免此错误。
{: tsResolve}

## 创建应用程序时获取代码失败
{: #code}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 来创建应用程序，那么可能会看到以下错误：

```
失败
应用程序已创建，但无法获取代码
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

导致此错误的原因是内部超时。
{: tsCauses}

可以通过以下任一方式来获取代码：

* 使用 CLI 运行以下命令：

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   将 `<your-app-name>` 替换为您在应用程序创建期间指定的应用程序名称。

* 使用 {{site.data.keyword.dev_console}}。

	1. 在 {{site.data.keyword.dev_console}} 中选择您的[应用程序 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://console.bluemix.net/developer/appservice/apps)。

	2. 单击**下载代码**。

{: tsResolve}

## 对 Node.js 应用程序运行 `bx dev run` 时出错
{: #node}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 对 Node.js Web 或 BFF 应用程序运行 `bx dev run`，那么可能会看到以下错误：

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
{: codeblock}
{: tsSymptoms}

`appmetrics` 模块安装在其他体系结构上时，会发生此错误。安装在一个体系结构上的本机 npm 模块不能在另一个体系结构上运行。包含的 Docker 映像基于 Linux 内核。
{: tsCauses}

删除 `node_modules` 文件夹，然后再次运行 `bx dev run` 命令。
{: tsResolve}

## 未能部署到 {{site.data.keyword.Bluemix_notm}}

尝试使用 {{site.data.keyword.dev_cli_short}} CLI 部署到 {{site.data.keyword.Bluemix_notm}} 时失败，但未显示任何错误。
{: tsSymptoms}

您可能未登录到帐户。
{: tsCauses}

请登录并重试。

```
bx login
```
{: tsResolve}

## 未能部署到 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes

在提示您输入集群名称后，可能会显示以下故障：

```
失败
未能执行操作：退出状态 1：

失败
未能配置对集群“<cluster-name>”的部署，原因是：退出状态 1
```
{: tsSymptoms}

最有可能导致此错误的原因是集群名称无效。可以通过运行带 `--trace` 的相同命令来确认原因，并且错误输出中可能包含以下详细信息：

```
失败，错误为：{"incidentID":"<id-number>","code":"E0008","description":"找不到指定的集群。","recoveryCLI":"请运行“bx cs clusters”以列出您有权访问的所有集群。","type":"正在供应"}
```
{: tsCauses}

确保使用的是正确集群，并且已通过运行以下命令将集群配置为用于部署：

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## 未能部署映像目标

在系统提示您提供部署映像目标后，可能会显示以下故障：

```
失败
无法执行操作：退出状态 1：已拒绝：请求对资源的访问被拒绝


失败
将标记为“registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1”的 Run 映像推送到 Docker 注册表时失败，原因：退出状态 1
```
{: tsSymptoms}

最有可能导致此错误的原因是部署映像目标无效。更具体地说，名称空间（即部署映像目标中的中间值）可能无效。

确保部署映像目标中的名称空间与通过运行以下命令而找到的名称空间之一相匹配：

```
bx cr namespaces
```
{: tsResolve}

## 重新安装工具
{: #appendix}

对于大多数用户，所有必备软件都是使用平台安装程序安装的。如果需要手动安装任何组件，请按以下指示信息进行操作：

要安装 dev 插件，必须先安装 [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started)。

要使用 dev 插件本身，必须运行以下命令来安装该插件：`bx plugin install dev -r Bluemix`

要在本地运行和调试应用程序，还必须安装 [Docker](https://www.docker.com/get-docker)。

要将应用程序部署为容器，还必须安装 Kubernetes、Helm 和以下 IBM Cloud CLI 插件：

安装 Kubernetes：
* Mac 用户：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux 用户：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows 用户：
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

安装 Helm：
* Mac 和 Linux 用户：
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows 用户：
下载并安装二进制文件：https://github.com/kubernetes/helm/releases/tag/v2.6.0

安装 container-registry 插件：
`bx plugin install container-registry`

安装 container-service 插件：
`bx plugin install container-service`
