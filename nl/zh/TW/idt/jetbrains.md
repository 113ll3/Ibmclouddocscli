---

copyright:

  years: 2018

lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools for Jetbrains IDEs
{: #ibm-dev-tools-for-jetbrains}

IBM Developer Extension for Jetbrains IDEs（包括 IntelliJ、WebStorm、Android Studio 等等）提供了新的功能表項目，可從 IDE 內直接存取 IDT CLI 指令。它可讓您快速存取 Docker 及 CloudFoundry 工作流程的部分 `ibmcloud dev` 指令，包括應用程式部署、在 {{site.data.keyword.Bluemix_notm}} 上啟動/停止/重新啟動應用程式、檢視遠端應用程式日誌等，而這些都不需要離開編輯器的環境定義。
{:shortdesc}

![在 WebStorm IDE 內執行之 IBM Developer Tools 的畫面擷取。](jetbrains.png "在 WebStorm IDE 內執行的 IDT 功能表範例")

## 相依關係
{: #dependencies}

若要使用 Jetbrains IDE 的 IBM Developer Tools 延伸規格，您需要在系統上安裝 [IBM Cloud Developer Tools CLI](index.html)。

## 安裝
{: #installation}

針對 Jetbrains IDE 安裝 IBM Developers Tools 延伸規格的最簡單方法，是移至 [IDT GitHub 儲存庫的 Jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) 頁面，然後遵循指示。

## 用法
{: #usage}

您可以從現有的伺服器端應用程式開始，並為 IBM Cloud 啟用它，或使用 IDT CLI 從 StarterKit 建立新的應用程式 (ibmcloud dev create)。具有應用程式專案時，請在 JetBrins IDE 中開啟它。

如果您有通用伺服器端應用程式，請選取「工具」> IBM Cloud Developer Tools > Enable app for IBM Cloud。這會檢查所有必要檔案，並新增遺漏的任何檔案，以讓您在本端建置應用程式，並使用 Cloud Foundry 應用程式將它部署至 IBM Cloud，或是部署在 Kubernetes 叢集內。

請使用 IDT 功能表裡的基本建置/執行/部署動作來開發雲端原生應用程式。如果您需要採取不在功能表中的動作，請開啟「終端機」標籤，並手動輸入想要的指令。
