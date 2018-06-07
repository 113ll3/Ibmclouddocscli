---
copyright:

  years: 2018

lastupdated: "2018-05-17"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# 設定 {{site.data.keyword.dev_cli_notm}} CLI
{: #add-cli}

{{site.data.keyword.dev_cli_short}} CLI 是一種指令行方法，可針對想要使用指令行開發端對端 Web、行動及微服務應用程式的開發人員建立、開發及部署應用程式。執行下列其中一個 Script，以快速開始使用建議的工具集。
{: shortdesc}

## {{site.data.keyword.dev_cli_notm}} 的必要條件
{: #prereq}

註冊 [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration)。

*  如果您是使用 Microsoft Windows&trade;，則必須使用 Windows 10 或更新版本。

* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 如何安裝 {{site.data.keyword.dev_cli_notm}}
{: #installation}

若要安裝工具集，您可以執行相關的指令來啟動安裝程式。這會安裝 {{site.data.keyword.Bluemix_notm}} 開發的下列建議工具（如果尚未安裝的話）：`Homebrew`（僅限 Mac）、`Git`、`Docker`、`Helm`、`kubectl`、`curl`、{{site.data.keyword.Bluemix_notm}} CLI、{{site.data.keyword.dev_cli_notm}} 外掛程式、Cloud Functions 外掛程式、Container Registry 外掛程式、Container Service 外掛程式，及 `sdk-gen` 外掛程式。若要進行安裝，請使用下列安裝步驟：

**Mac 及 Linux：**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10：**

* 附註：請在 PowerShell 圖示按一下滑鼠右鍵並選取「以系統管理員身分執行」，以開啟 Windows PowerShell。

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

## 驗證安裝
若要驗證安裝，請執行 `help` 指令：

```
ibmcloud dev help
```
{: codeblock}

如果安裝成功，輸出應該列出用法指令、現行版本，及支援的指令。

[重新安裝工具](/docs/troubleshoot/ts_createapps.html#appendix)一節包含個別安裝所有相依關係的資訊。

## 配置環境
{: #configure-environment}

1. 連接至 {{site.data.keyword.Bluemix_notm}} 地區中的 API 端點。例如，輸入下列指令以連接至 {{site.data.keyword.Bluemix_notm}} 美國南部地區：

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. 使用 IBM ID 登入 {{site.data.keyword.Bluemix_notm}}。

	```
	ibmcloud login
	```
	{: codeblock}

	**附註：**如果您的認證遭到拒絕，您可能會使用「聯合 ID」。請遵循下列步驟，以使用「聯合 ID」進行鑑別。

	1. 登入 [{{site.data.keyword.iamshort}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.bluemix.net/iam/#/apikeys){: new_window}。
	2. 選取**建立 API 金鑰**。
		* 輸入 apiKey 名稱及說明
	3. 下載 apiKey。
	4. 開啟檔案，並複製 `apiKey` 欄位中的值。
	5. 使用下列指令來登入：

		```
		ibmcloud login --apikey <value>
		```
		{: codeblock}

3. 使用下列指令，設定 ORG 及 SPACE：

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 進一步瞭解
{: #learn}

現在，您已安裝 {{site.data.keyword.dev_cli_short}} CLI，因此可以瞭解如何有效地使用此功能強大的工具：
- [開始使用 IDT CLI](index.html)
- [IDT (ibmcloud dev) 指令](commands.html)
- [Developer Tools for VS Code](vscode.html)
- [Developer Tools for Jetbrains IDE](jetbrains.html)

查看[指導教學](/docs/apps/tutorials/tutorial_bff.html)，以顯示如何使用 {{site.data.keyword.dev_cli_short}} CLI 建立雲端原生應用程式。

## 進一步閱讀
{: #learn-more}

使用 IBM Developer Tools CLI 開發「雲端原生」應用程式時，下列資源十分有用：

- [IBM Cloud Developer Tools 主要登陸頁面](https://www.ibm.com/cloud/cli) - IDT CLI 的主要產品頁面
- [IBM Developer Tools 安裝程式](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - 具有詳細安裝指示的公用 GitHub 儲存庫
- [IBM Cloud 應用程式服務](https://console.bluemix.net/developer/appservice) - IDT 工具隨附的 IBM Cloud 主控台頁面以建立及管理雲端原生應用程式
- [在 GitHub 上報告問題](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech 的 Slack - #developer-tools 頻道](https://ibm-cloud-tech.slack.com) - 在[這裡](https://slack-invite-ibm-cloud-tech.mybluemix.net/)要求團隊存取

**著重的語言**

- [IBM Cloud 上的 Node.js](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**部落格及指導教學**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
