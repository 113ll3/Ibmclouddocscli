---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# 手动安装 {{site.data.keyword.cloud_notm}} Developer Tools CLI 插件
{: #install-devtools-manually}

如果您希望对组件安装进行粒度更细的控制，那么可以手动安装 {{site.data.keyword.cloud}} Developer Tools 命令行界面 (CLI) 插件。对于大多数用户，都将通过[平台安装程序](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)自动安装所有必备软件。
{: shortdesc}

## 开始之前
{: cli-before-you-begin}

* 安装独立 [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) 以获取有关安装 {{site.data.keyword.cloud_notm}} 的命令行插件的支持。
* 安装 [curl](https://curl.haxx.se/download.html){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 命令，以便通过命令行下载软件包。

## 安装 {{site.data.keyword.cloud_notm}} Developer Tools CLI 插件
{: #install-devtools-idt}

您可以使用 {{site.data.keyword.cloud_notm}} Developer Tools CLI 命令来创建、管理、部署、调试和测试应用程序。

要安装 {{site.data.keyword.cloud_notm}} Developer Tools 插件，请运行以下命令： 
```
ibmcloud plugin install dev
```
{: codeblock}

## 安装 Docker
{: #install-devtools-docker}

要在本地运行和调试应用程序，请安装 [Docker](https://www.docker.com/get-started){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

## 安装 Kubernetes 命令行工具
{: #idt-install-kube}

要查看 Kubernetes 仪表板的本地版本并将应用程序部署到集群，请安装适用于您平台的 [Kubernetes 命令行工具 ](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")：

* MacOS：
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
  {: codeblock}

* Linux&trade;：
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
  {: codeblock}

* Windows&trade;：
  ```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
  {: codeblock}

使用 Kubernetes 命令行工具运行命令的前缀是 `kubectl`。 有关更多信息，请参阅[设置 CLI 和 API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install)。

## 安装 {{site.data.keyword.registrylong_notm}} CLI 插件
{: #idt-install-container-registry-cli-plugin}

您可以使用 `container-registry` CLI 插件，在 IBM 托管和管理的专用注册表中设置您自己的映像名称空间，在此注册表中，可存储 Docker 映像并与 {{site.data.keyword.cloud_notm}} 帐户中所有用户共享。

* 要安装 {{site.data.keyword.registrylong}} 插件，请运行以下命令：
  ```
ibmcloud plugin install container-registry
```
  {: codeblock}

有关更多信息，请参阅 [{{site.data.keyword.registrylong}} 命令参考](/docs/services/Registry?topic=registry-registry_cli_reference)。

## 安装 {{site.data.keyword.containerlong_notm}} CLI 插件
{: #idt-install-kubernetes-cli-plugin}

要在 {{site.data.keyword.containerlong}} 中创建和管理 Kubernetes 集群，请执行以下操作：

* 要安装 {{site.data.keyword.registryshort_notm}} 插件，请运行以下命令：
  ```
ibmcloud plugin install container-service
```
  {: codeblock}

有关更多信息，请参阅 [{{site.data.keyword.registryshort_notm}} 命令参考](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference)。

## 安装 Helm
{: #idt-install-helm}

安装 [Helm](https://helm.sh/docs/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")，Helm 是一个基于 Kubernetes 的软件包管理器。

* 对于 MacOS 和 Linux&trade; 用户，运行以下命令：
  ```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
  {: codeblock}

* Windows&trade; 用户可以下载和安装 Helm [二进制文件](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

## 安装 {{site.data.keyword.openwhisk_short}} CLI 插件
{: #idt-install-functions}

您可以使用 {{site.data.keyword.openwhisk}} CLI 插件来管理操作中的代码片段，将操作捆绑到包中，创建触发器和规则以使操作能够响应事件。

要安装 {{site.data.keyword.openwhisk_short}} CLI 插件，请运行以下命令：
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

有关更多信息，请参阅[设置 {{site.data.keyword.openwhisk_short}} CLI 插件](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)。

## 安装 SDK Generator CLI 插件
{: #idt-install-sdk-gen}

作为 {{site.data.keyword.cloud_notm}} 上的开发者，您可以使用此插件通过符合 [Open API 规范](https://www.openapis.org/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 的 REST API 定义来生成 SDK。对 REST API 定义进行更改后，可以使用此插件来仅重新生成 SDK，而不重新生成整个项目。

要安装 SDK Generator CLI 插件，请运行以下命令：
```
ibmcloud plugin install sdk-gen
	```
{: codeblock}

有关更多信息，请参阅 [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)。
