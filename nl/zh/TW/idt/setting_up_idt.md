---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# 設定 {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

{{site.data.keyword.dev_cli_short}} 是一種指令行方法，可針對想要使用指令行開發端對端 Web、行動及微服務應用程式的開發人員建立、開發及部署應用程式。
{: shortdesc}

## 必要條件
{: #prereq}

註冊 [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net)。

*  如果您是使用 Microsoft Windows&trade;，則必須使用 Windows 10 或更新版本。

* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 安裝
{: #installation}

若要安裝此工具，您可以執行相關的指令來呼叫我們的安裝程式。這也會安裝相依關係，例如 IBM Cloud CLI、Kubernetes、Helm 及 Docker。若要安裝這些項目，請使用下列安裝步驟：

**Mac 及 Linux：**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10：**

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

執行下列指令，以驗證成功的外掛程式安裝：  

```
bx dev
```
{: codeblock}

## 配置環境
{: #configure-environment}

1. 連接至 [{{site.data.keyword.Bluemix_notm}} 地區](/docs/overview/cf.html#ov_intro_reg)中的 API 端點。例如，輸入下列指令以連接至 {{site.data.keyword.Bluemix_notm}} 美國南部地區：

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. 登入 IBM ID 登入 {{site.data.keyword.Bluemix_notm}}。

	```
	bx login
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
		bx login --apikey <value>
		```
		{: codeblock}

3. 使用下列指令，設定 ORG 及 SPACE：

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## 進一步瞭解
{: #learn}

現在，您已安裝 {{site.data.keyword.dev_cli_short}}，因此可以瞭解如何有效地使用此功能強大的工具。
- [開始使用 IDT CLI](index.html)
- [IDT (bx dev) 指令](commands.html)
- [Developer Tools for VS Code](vscode.html)
- [Developer Tools for Jetbrains IDE](jetbrains.html)

查看[指導教學](/docs/apps/tutorials/tutorial_bff.html)，以顯示如何使用 {{site.data.keyword.dev_cli_short}} 建立雲端原生應用程式。

## 進一步閱讀
{: #learn-more}

使用 IBM Developer Tools CLI 開發「雲端原生」應用程式時，下列資源十分有用：

- [IBM Cloud Developer Tools 主要登陸頁面](https://www.ibm.com/cloud/cli) - IDT CLI 的主要產品頁面
- [IBM Developer Tools 安裝程式](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - 具有詳細安裝指示的公用 GitHub 儲存庫
- [IBM Cloud 應用程式服務](https://console.bluemix.net/developer/appservice) - IDT 工具隨附的 IBM Cloud 主控台頁面以建立及管理雲端原生應用程式
- [IBM Cloud Tech 的 Slack - #developer-tools 通道](https://ibm-cloud-tech.slack.com) - 討論 IDT 工具、取得答案、建議構想等
	- [要求團隊存取](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**聚焦語言**

- [IBM Cloud 上的 Node.js](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**部落格及指導教學**

- [使用 IBM Cloud Developer Tools CLI 部署至 IBM Cloud 專用](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [使用 IBM Cloud Developer Tools CLI 啟用 IBM Cloud 的現有專案](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [使用 IBM Cloud Developer Tools CLI 部署至 IBM Cloud 上的 Kubernetes](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
