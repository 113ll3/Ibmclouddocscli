---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} 概觀
{: #overview}

{{site.data.keyword.dev_cli_notm}} 是一種指令行方法，可針對想要使用指令行開發端對端 Web、行動及微服務應用程式的開發人員建立、開發及部署應用程式。執行下列其中一個 Script，以快速開始使用建議的工具集。
{: shortdesc} 

## {{site.data.keyword.dev_cli_notm}} 的必要條件
{: #prereq}

註冊 [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration)。

* 如果您是使用 Microsoft Windows&trade;，則必須使用 Windows 10 或更新版本。

* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 如何安裝 {{site.data.keyword.dev_cli_notm}}
{: #installation}

若要安裝工具集，您可以執行相關的指令來啟動安裝程式。這會安裝 {{site.data.keyword.Bluemix_notm}} 開發的下列建議工具（如果尚未安裝的話）：`Homebrew`（僅限 Mac）、`Git`、`Docker`、`Helm`、`kubectl`、`curl`、{{site.data.keyword.Bluemix_notm}} CLI、{{site.data.keyword.dev_cli_notm}} 外掛程式、Cloud Functions 外掛程式、Container Registry 外掛程式、Container Service 外掛程式，及 `sdk-gen` 外掛程式。

**Mac 及 Linux：**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10：**

* 附註：請按一下滑鼠右鍵並選取「以系統管理員身分執行」，以開啟 Windows PowerShell。

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## 可進一步探索 {{site.data.keyword.dev_cli_notm}} 的其他鏈結

- [詳細設定](/docs/cli/idt/setting_up_idt.html)
- [用法](/docs/cli/idt/index.html)
- [指令](/docs/cli/idt/commands.html)
- [CLI 外掛程式](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE Extension](/docs/cli/idt/vscode.html)
- [手動安裝 IBM Cloud CLI](/docs/cli/reference/bluemix_cli/get_started.html)
