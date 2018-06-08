---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} 概述
{: #overview}

{{site.data.keyword.dev_cli_notm}} 是一种命令行方法，用于为那些想要使用命令行来开发端到端 Web、移动和微服务应用程序的开发者创建、开发和部署应用程序。通过运行以下其中一个脚本来快速开始使用建议的工具集。
{: shortdesc}

## {{site.data.keyword.dev_cli_notm}} 的先决条件
{: #prereq}

注册 [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration)。

* 如果使用的是 Microsoft Windows&trade;，那么必须使用 Windows 10 或更高版本。

* 您必须使用 Docker 的稳定通道，最低版本为 1.13.1。

## 如何安装 {{site.data.keyword.dev_cli_notm}}
{: #installation}

要安装工具集，可以运行相关命令来启动安装程序。这将安装用于 {{site.data.keyword.Bluemix_notm}} 开发的以下建议工具（如果尚未安装）：`Homebrew`（仅限 Mac）、`Git`、`Docker`、`Helm`、`kubectl`、`curl`、{{site.data.keyword.Bluemix_notm}} CLI、{{site.data.keyword.dev_cli_notm}} 插件、Cloud Functions 插件、Container Registry 插件、Container Service 插件和 `sdk-gen` 插件。

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

## 验证安装
要验证安装，请运行 `help` 命令：

```
ibmcloud dev help
```
{: codeblock}

如果安装成功，那么输出应该列出用法指示信息、当前版本和支持的命令。


## 用于进一步探索 {{site.data.keyword.dev_cli_notm}} 的其他链接

- [详细设置](/docs/cli/idt/setting_up_idt.html)
- [用法](/docs/cli/idt/index.html)
- [命令](/docs/cli/idt/commands.html)
- [CLI 插件](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE 扩展](/docs/cli/idt/vscode.html)
- [手动安装 IBM Cloud CLI](/docs/cli/reference/bluemix_cli/get_started.html)
- [在 GitHub 上报告问题](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech 的 Slack - #developer-tools 频道](https://ibm-cloud-tech.slack.com) - 请求团队访问[此处](https://slack-invite-ibm-cloud-tech.mybluemix.net/)
