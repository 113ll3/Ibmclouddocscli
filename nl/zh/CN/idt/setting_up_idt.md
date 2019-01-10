---
copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# 设置 {{site.data.keyword.dev_cli_notm}} CLI
{: #add-cli}

{{site.data.keyword.dev_cli_short}} CLI 是一种命令行方法，用于为那些想要使用命令行来开发端到端 Web、移动和微服务应用程序的开发者创建、开发和部署应用程序。通过运行以下其中一个脚本来快速开始使用建议的工具集。
{: shortdesc}

## 开始安装 {{site.data.keyword.dev_cli_notm}} 之前 
{: #prereq}

注册 [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration)。

*  如果使用的是 Microsoft Windows&trade;，那么必须使用 Windows 10 或更高版本。

* 您必须使用 Docker 的稳定通道，最低版本为 1.13.1。

## 如何安装 {{site.data.keyword.dev_cli_notm}}
{: #installation}

要安装工具集，可以运行相关命令来启动安装程序。这将安装用于 {{site.data.keyword.Bluemix_notm}} 开发的以下建议工具（如果尚未安装）：`Homebrew`（仅限 Mac）、`Git`、`Docker`、`Helm`、`kubectl`、`curl`、{{site.data.keyword.Bluemix_notm}} CLI、{{site.data.keyword.dev_cli_notm}} 插件、Cloud Functions 插件、Container Registry 插件、Container Service 插件和 `sdk-gen` 插件。要进行安装，请使用以下安装步骤：

**Mac 和 Linux：**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10：**

* 注：通过右键单击 PowerShell 图标并选择“以管理员身份运行”来打开 Windows PowerShell。

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

您还可以从 [GitHub 存储库](https://github.com/IBM-Cloud/ibm-cloud-developer-tools)下载安装程序脚本。

## 验证安装
要验证安装，请运行 `help` 命令：

```
ibmcloud dev help
```
{: codeblock}

如果安装成功，那么输出信息将列出用法指示信息、当前版本和支持的命令。

[重新安装工具](/docs/troubleshoot/ts_createapps.html#appendix)部分包含有关单独安装所有依赖项的信息。

## 配置环境
{: #configure-environment}

1. 连接到您的 {{site.data.keyword.Bluemix_notm}} 位置的 API 端点。例如，输入以下命令来连接到 {{site.data.keyword.Bluemix_notm}} 达拉斯位置：

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. 使用 IBM 标识登录到 {{site.data.keyword.Bluemix_notm}}。

	```
	ibmcloud login
	```
	{: codeblock}

	如果凭证被拒绝，说明您可能使用的是联合标识。请执行以下步骤来使用联合标识进行认证。
	{: note}

	1. 登录到 [{{site.data.keyword.iamshort}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.bluemix.net/iam/#/apikeys){: new_window}。
	2. 选择**创建 API 密钥**。
		* 输入 API 密钥的名称和描述。
	3. 下载 API 密钥。
	4. 打开相应文件，然后从 `apiKey` 字段中复制相应值。
	5. 使用以下命令进行登录：

		```
		ibmcloud login --apikey <value>
		```
		{: codeblock}

3. 使用以下内容设置 ORG 和 SPACE：

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 了解更多
{: #learn}

现在，您已安装了 {{site.data.keyword.dev_cli_short}} CLI，接下来可以了解如何有效利用此功能强大的工具：
- [IDT CLI 入门](index.html)
- [IDT (ibmcloud dev) 命令](commands.html)
- [用于 VS Code 的 Developer Tools](vscode.html)
- [用于 Jetbrains IDE 的 Developer Tools](jetbrains.html)

查看显示如何创建使用 {{site.data.keyword.dev_cli_short}} CLI 的云本机应用程序的[教程](/docs/apps/tutorials/tutorial_bff.html)。

## 进一步阅读
{: #learn-more}

使用 IBM Developer Tools CLI 开发云本机应用程序时，以下资源可能非常有用：

- [IBM Cloud Developer Tools 主登录页面](https://www.ibm.com/cloud/cli) - IDT CLI 的主产品页面
- [IBM Developer Tools 安装程序](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - 包含详细安装指示信息的公共 GitHub 存储库
- [IBM Cloud App Service](https://{DomainName}/developer/appservice) - IBM Cloud 控制台页面，是 IDT 工具用于创建和管理云本机应用程序的指南
- [在 GitHub 上报告问题](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech 的 Slack - #developer-tools 频道](https://ibm-cloud-tech.slack.com) - 请求团队访问[此处](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**专注于语言**

- [Node.js on IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**博客和教程**

- [Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
