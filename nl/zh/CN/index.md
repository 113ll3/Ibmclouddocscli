---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-19"

keywords: cli, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# 入门教程
{: #getting-started}

在本教程中，您将安装一组 {{site.data.keyword.cloud}} Developer Tools，验证安装，并配置环境。{{site.data.keyword.dev_cli_notm}} 提供了一种命令行方法，用于创建、开发和部署云应用程序。
{: shortdesc}

本教程中的安装命令会安装最新可用的独立 {{site.data.keyword.cloud_notm}} CLI 版本以及以下工具：

* `Homebrew`（仅限 Mac）
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 插件
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 插件
* {{site.data.keyword.cos_full_notm}} 插件
* {{site.data.keyword.registrylong_notm}} 插件
* {{site.data.keyword.containerlong_notm}} 插件

## 开始之前
{: #idt-prereq}

您需要 [{{site.data.keyword.cloud_notm}} 帐户 ](https://cloud.ibm.com/){: new_window}![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 并满足以下系统需求：

* 如果您运行的是 Windows&trade;，但并不是 Windows&trade; 10 专业版，那么某些功能将不受支持。
* 您必须使用 Docker 的稳定通道，最低版本为 1.13.1。

## 步骤 1. 运行安装命令
{: #step1-install-idt}

运行命令时，将安装 {{site.data.keyword.cloud_notm}} CLI 的最新版本。

* 对于 Mac 和 Linux&trade;，请运行以下命令：
  ```
curl -sL https://ibm.biz/idt-installer | bash
```
  {: codeblock}

* 对于 Windows&trade; 10 专业版，请以管理员身份运行以下命令：
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  右键单击 Windows&trade; PowerShell 图标，并选择**以管理员身份运行**。
  {: tip}

您还可以从此 [GitHub 存储库](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 中下载安装程序脚本。

如果需要使用 32 位版本的 CLI 或 {{site.data.keyword.cloud_notm}} Dedicated 环境的最新版本之外的先前版本，请参阅 [{{site.data.keyword.cloud_notm}} CLI 发行版](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。
{: note}

## 步骤 2. 验证安装
{: #step2-verify-idt}

要验证是否已成功安装 CLI 和 Developer Tools，请运行 `help` 命令：
```
ibmcloud dev help
```
{: codeblock}

输出会列出用法指示信息、当前版本和支持的命令。

## 步骤 3. 配置环境
{: #step3-configure-idt-env}

1. 使用 IBM 标识登录到 {{site.data.keyword.cloud_notm}}。如果您有多个帐户，系统会提示您选择要使用的帐户。如果未使用 `-r` 标志指定区域，那么还必须选择区域。

  ```
ibmcloud login
```
  {: codeblock}
  
  如果凭证被拒绝，说明您可能使用的是联合标识。要使用联合标识登录，请使用 `--sso` 标志。有关更多详细信息，请参阅[使用联合标识进行登录](/docs/iam/federated_id?topic=iam-federated_id#federated_id)。
  {: tip}

2. 要访问 Cloud Foundry 服务，必须指定 Cloud Foundry 组织和空间。您可以运行以下命令，通过交互方式确定组织和空间：
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  或者，如果您知道服务所属的组织和空间，可以使用以下命令：
  ```
ibmcloud target -o <value> -s <value>
	```
  {: codeblock}

## 后续步骤
{: #next-steps}

* 现在，您已准备好开发和部署您的首个应用程序。有关更多信息，请参阅[使用 CLI 创建和部署应用程序](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)。

* 您可以接收有关新 {{site.data.keyword.cloud_notm}} CLI 发行版的通知。请预订 [{{site.data.keyword.cloud_notm}} CLI 发行版存储库](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。
