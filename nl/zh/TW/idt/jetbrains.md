---

copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Jetbrains IDE 的 IBM Cloud Developer Tools
{: #ibm-dev-tools-for-jetbrains}

Jetbrains IDE（包括 `IntelliJ`、`WebStorm`、`Android Studio` 等等）的 {{site.data.keyword.Bluemix_notm}} Developer Tools 延伸規格提供了新的功能表項目，可從 IDE 內直接存取 {{site.data.keyword.dev_cli_notm}} CLI 指令。它讓您能快速存取 Docker 及 CloudFoundry 工作流程的部分 `ibmcloud dev` 指令，包括應用程式部署、在 {{site.data.keyword.Bluemix_notm}} 上啟動/停止/重新啟動應用程式、檢視遠端應用程式日誌等，而這些都不需要離開編輯器的環境定義。
{:shortdesc}

![在 WebStorm IDE 內執行之 IBM Cloud Developer Tools 的畫面擷取。](jetbrains.png "在 WebStorm IDE 內執行的 {{site.data.keyword.Bluemix_notm}} Developer Tools 功能表範例")

## 相依關係
{: #dependencies}

若要針對 Jetbrains IDE 使用 {{site.data.keyword.Bluemix_notm}} Developer Tools 延伸規格，您也需要在系統上安裝 [{{site.data.keyword.dev_cli_notm}} CLI](index.html)。

## 安裝
{: #installation}

針對 Jetbrains IDE 安裝 {{site.data.keyword.Bluemix_notm}} Developer Tools 延伸規格的最簡單方法，是移至 [{{site.data.keyword.Bluemix_notm}} 開發人員工具 GitHub 儲存庫的 Jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) 頁面，然後遵循指示。

## 用法
{: #usage}

您可以從現有的伺服器端應用程式開始，並為 {{site.data.keyword.Bluemix_notm}} 啟用它，或使用 {{site.data.keyword.dev_cli_notm}} CLI 從 StarterKit 建立新的應用程式 (ibmcloud dev create)。一旦您具有應用程式的專案，請在 JetBrins IDE 中開啟它。

如果您有通用伺服器端應用程式，請選取「工具」> IBM Cloud Developer Tools >「針對 IBM Cloud 啟用應用程式」。這會檢查所有必要檔案，並新增遺漏的任何檔案，以讓您在本端建置應用程式，並使用 Cloud Foundry 應用程式將它部署至 {{site.data.keyword.Bluemix_notm}}，或是部署在 Kubernetes 叢集內。

請使用 {{site.data.keyword.Bluemix_notm}} Developer Tools 功能表裡的基本建置/執行/部署動作來開發雲端原生應用程式。如果您需要執行不在功能表中的動作，請直接開啟「終端機」標籤，並手動輸入想要的指令。
