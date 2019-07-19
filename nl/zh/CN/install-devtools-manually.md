---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# 手动安装 {{site.data.keyword.cloud_notm}} Developer Tools CLI 插件组件
{: #install-devtools-manually}

如果您希望对 Developer Tools 组件的安装进行更精细地控制，那么可以使用以下步骤来进行手动安装。对于大多数用户，都将通过[平台安装程序](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)自动安装所有必备软件。
{: shortdesc}

## 开始之前
{: cli-before-you-begin}

* 安装独立 [{{site.data.keyword.cloud}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)，以便支持为 `ibmcloud` 安装命令行插件。
* 安装 [curl](https://curl.haxx.se/download.html){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 命令，以便通过命令行下载软件包。

## 步骤 1. 安装 {{site.data.keyword.cloud_notm}} Developer Tools CLI 插件
{: #install-devtools-idt}

您可以使用 {{site.data.keyword.cloud_notm}} Developer Tools CLI (ibmcloud dev) 命令来创建、管理、部署、调试和测试应用程序。

运行以下命令来安装 `dev` 插件： 
```
ibmcloud plugin install dev
```
{: codeblock}

## 步骤 2. 安装 Docker
{: #install-devtools-docker}

要在本地运行和调试应用程序，请安装 [Docker](https://www.docker.com/get-docker){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

## 步骤 3. 安装 Kubernetes：
{: #idt-install-kube}

Kubernetes 是一个开放式源代码容器编排引擎，用于自动化容器化应用程序的部署、扩展和管理。

要支持容器化部署，请针对您的平台安装 Kubernetes：

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

## 步骤 4. 安装 Kubernetes CLI 插件
{: #idt-install-kubernetes-cli-plugins}

要从命令行管理 Kubernetes 部署，请安装以下容器插件：

* 安装 `container-registry` 插件：
  ```
ibmcloud plugin install container-registry
```
  {: codeblock}

* 安装 `container-service` 插件：
  ```
ibmcloud plugin install container-service
```
  {: codeblock}

有关更多信息，请参阅[设置 CLI 和 API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install)。

## 步骤 5. 安装 Helm：
{: #idt-install-helm}

安装 [Helm](https://helm.sh/docs/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")，Helm 是一个基于 Kubernetes 的软件包管理器。

* 对于 MacOS 和 Linux&trade; 用户，运行以下命令：
  ```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
  {: codeblock}

* Windows&trade; 用户可以下载和安装 Helm [二进制文件](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

## 步骤 6. 安装 {{site.data.keyword.openwhisk_short}} CLI 插件
{: #idt-install-functions}

您可以使用 {{site.data.keyword.openwhisk}} CLI 插件来管理操作中的代码片段，创建触发器和规则以使操作能够响应事件，以及将操作捆绑到包中。

要安装 {{site.data.keyword.openwhisk_short}} CLI 插件，请运行以下命令：
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

有关更多信息，请参阅[设置 {{site.data.keyword.openwhisk_short}} CLI 插件](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)。

## 步骤 7. 安装 SDK Generator CLI 插件
{: #idt-install-sdk-gen}

作为 {{site.data.keyword.cloud_notm}} 上的开发者，您可以使用此插件通过符合 [Open API 规范 ](https://www.openapis.org/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 的 REST API 定义来生成 SDK。对 REST API 定义进行更改后，可以使用此插件来仅重新生成 SDK，而不重新生成整个项目。

安装 SDK Generator CLI 插件：
```
ibmcloud plugin install sdk-gen
	```
{: codeblock}

有关更多信息，请参阅 [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)。
