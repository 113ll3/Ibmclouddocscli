---

copyright:

  years: 2017, 2018

lastupdated: "2018-06-21"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

IBM Developer Extension for Visual Studio Code 是一種延伸規格，可讓編輯器直接存取 Visual Studio Code 編輯器之指令選用區內的 IBM Developer CLI 功能。它可讓您快速存取 Docker 及 CloudFoundry 工作流程的部分 `ibmcloud dev` 指令，包括應用程式部署、在 {{site.data.keyword.Bluemix_notm}} 上啟動/停止/重新啟動應用程式、檢視遠端應用程式日誌等，而這些都不需要離開編輯器的環境定義。
{:shortdesc}

![IBM Developer Tools 延伸規格下載畫面的畫面擷取。](vscode.png "Visual Studio Code 內的延伸規格下載畫面")

## 相依關係
{: #dependencies}

若要使用 Visual Studio Code 的 IBM Developer Tools 延伸規格，您需要在系統上安裝 [{{site.data.keyword.Bluemix_notm}} CLI](https://plugins.ng.bluemix.net/ui/home.html) 及 [IBM Developer CLI](index.html) 外掛程式。

## 安裝
{: #installation}

IBM Developers Tools 延伸規格的最簡單安裝方式是使用 Visual Studio Code 的 'quick open' 指令：

1. 從編輯器內使用下列組合鍵，以開啟 'quick open' 指令選用區：

  * **Mac：**`cmd + p`
  * **Windows/Linux：**`ctrl + p`

2. 輸入 `ext install ibm-developer` 指令，然後按 Enter 鍵以在 Visual Studio Code 編輯器內安裝 IBM Developer Tools 延伸規格。

或者，您可以透過「延伸規格」管理視窗來安裝 IBM Developer Tools 延伸規格：

1. 開啟 Visual Studio Code 編輯器內的**延伸規格**資訊看板，然後使用字串 `publisher:IBM Developer` 進行搜尋。IBM Developer Tools 延伸規格會顯示在搜尋結果中。  
2. 按一下**安裝**按鈕以開始安裝。

您也可以直接存取 [Visual Studio Code Marketplace 內的 IBM Developer Tools 延伸規格](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer)。

## 用法
{: #usage}

您可以使用 Visual Studio Code 的指令選用區來啟動延伸規格指令。

首先，使用下列組合鍵來開啟指令選用區：

* **Mac：**`cmd + shift + p`
* **Windows/Linux：**`ctrl + shift + p`

接下來，輸入或選取您要啟動的指令。您可以在指令選用區內鍵入 'ibmcloud'，以查看所有可用指令的清單。

### 使用 IBM Developer Extension for Docker 工作流程（Docker 容器）
{: #usage-docker}

只要幾個步驟，您就可以開始使用 ibmcloud dev 工作流程：
* 使用下列兩種方法之一，來建立專案：
  * 使用 [{{site.data.keyword.Bluemix_notm}} Web 主控台](https://console.ng.bluemix.net/developer/getting-started/)，並下載產生的程式碼
  * 使用 [{{site.data.keyword.Bluemix_notm}} Developer CLI](index.html)，並使用 `ibmcloud dev create` 指令產生專案
* 在 Visual Studio Code 編輯器中本端開啟專案的資料夾
* 使用 `ibmcloud dev build` 指令，將應用程式建置至 Docker 映像檔
* 使用 `ibmcloud dev debug` 指令，在本端 Docker 中執行應用程式以進行開發
> 附註：若要對本端 Docker 容器內執行的 Node.js 應用程式進行除錯，您需要[新增本端容器的除錯配置](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container)。
* 使用 `ibmcloud dev run` 指令，以發行模式在本端 Docker 中執行應用程式
* 使用 `ibmcloud dev deploy` 指令，以在 {{site.data.keyword.Bluemix_notm}} 上將應用程式部署至 Cloud Foundry 運行環境

### 使用 IBM Developer Extension for Cloud Foundry 工作流程
{: #usage-cloud-foundry}

如果使用者目前正在 IBM {{site.data.keyword.Bluemix_notm}} 上將應用程式部署至 Cloud Foundry 運行環境，則我們也支援 `cf` 作業集。

只要幾個步驟，您就可以開始使用 CloudFoundry 工作流程：
* 建立新的 CloudFoundry 應用程式
  * 使用 [Web 主控台](https://console.ng.bluemix.net/dashboard/cf-apps)，並下載入門範本程式碼
  * 手動建立新的 CloudFoundry 應用程式
* 在 Visual Studio Code 編輯器中本端開啟專案資料夾
* 使用 `ibmcloud cf apps`，以列出您的所有應用程式
* 使用 `ibmcloud cf push`，以將您應用程式的建置推送至 Cloud Foundry 運行環境
* 使用 `ibmcloud cf <start/stop/restage/restart>`，以變更您應用程式的狀態
* 使用 `ibmcloud cf logs`，以檢視您應用程式的即時日誌串流
  * 使用 `ibmcloud cf logs`，以停止日誌串流
