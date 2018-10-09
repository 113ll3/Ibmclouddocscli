---

copyright:

  years: 2015, 2018

lastupdated: "2018-08-31"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} CLI 入门
{: #overview}

在本教程中，您将安装一组 {{site.data.keyword.Bluemix}} Developer Tools，验证安装，并配置环境。{{site.data.keyword.Bluemix}} Developer Tools 提供一种命令行方法，用于创建、开发和部署端到端 Web、移动和微服务应用程序。
{:shortdesc}

通过此安装，您将获得独立 {{site.data.keyword.Bluemix_notm}} CLI 以及以下工具：

* `Homebrew`（仅限 Mac）
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 插件
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 插件
* {{site.data.keyword.registrylong_notm}} 插件
* {{site.data.keyword.containerlong_notm}} 插件
* `sdk-gen` 插件

## 开始之前
{: #prereq}

您需要 [{{site.data.keyword.Bluemix_notm}} 帐户 ](https://console.bluemix.net/){: new_window}![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 并满足以下系统需求：

* 如果您运行的是 Windows，但并不是 Windows 10 专业版，可能不支持某些功能。
* 您必须使用 Docker 的稳定通道，最低版本为 1.13.1。

## 步骤 1. 运行安装命令
{: #step1}

* 对于 Mac 和 Linux，请运行以下命令：

  ```
curl -sL https://ibm.biz/idt-installer | bash
```
  {: codeblock}

* 对于 Windows 10 专业版，请以管理员身份运行以下命令：

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

    右键单击 Windows PowerShell 图标，并选择**以管理员身份运行**。
  {: tip}

  您还可以从 [GitHub 存储库](https://github.com/IBM-Cloud/ibm-cloud-developer-tools)下载安装程序脚本。

  有关手动安装这些工具的步骤，请参阅[重新安装工具](/docs/cli/ts_createapps.html#appendix)。

## 步骤 2. 验证安装
{: #step2}

要验证是否已成功安装 CLI 和开发者工具，请运行 `help` 命令：

```
ibmcloud dev help
```
{: codeblock}
<br>
输出会列出用法指示信息、当前版本和支持的命令。

## 步骤 3. 配置环境
{: #step3}

1. 连接到您的 {{site.data.keyword.Bluemix_notm}} 区域中的 API 端点。例如，输入以下命令来连接到 {{site.data.keyword.Bluemix_notm}} 美国南部区域：

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. 使用 IBM 标识登录到 {{site.data.keyword.Bluemix_notm}}。

	```
	ibmcloud login
	```
	{: codeblock}
    <br>

	如果凭证被拒绝，说明您可能使用的是联合标识。有关更多详细信息，请参阅[使用联合标识进行登录](/docs/iam/login_fedid.html#federated_id)。
	{: tip}

3. 设置组织和空间。

	```
	  ibmcloud target --cf
  ```
	{: codeblock}

	（可选）可以使用上面命令的输出，通过以下命令来手动设置组织和空间：

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 后续步骤
{: #next-steps}

现在，您已准备好开发和部署第一个应用程序！
