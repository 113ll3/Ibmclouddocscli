---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# JetBrains IDE 的 IBM Cloud Developer Tools
{: #ibm-dev-tools-for-jetbrains}

JetBrains IDE（包括 `IntelliJ`、`WebStorm`、`Android Studio` 等等）的 {{site.data.keyword.cloud}} Developer Tools 延伸規格提供了新的功能表項目，可從 IDE 內直接存取 {{site.data.keyword.dev_cli_notm}} CLI 指令。您可以快速存取 Docker 及 Cloud Foundry 工作流程的部分 `ibmcloud dev` 指令，包括應用程式部署、在 {{site.data.keyword.cloud_notm}} 上啟動/停止/重新啟動應用程式、檢視遠端應用程式日誌等。這些都不需要離開編輯器的環境定義。
{: shortdesc}

![在 WebStorm IDE 內執行之 IBM Cloud Developer Tools 的畫面擷取。](jetbrains.png "在 WebStorm IDE 內執行的 {{site.data.keyword.cloud_notm}} Developer Tools 功能表範例")


## 相依關係
{: #jetbrains-dependencies}

若要針對以 JetBrains 為基礎的 IDE 使用 {{site.data.keyword.cloud_notm}} Developer Tools 延伸規格，您需要在系統上安裝 [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

## 安裝
{: #jetbrains-installation}

若要為 JetBrains IDE 安裝 {{site.data.keyword.cloud_notm}} Developer Tools 延伸規格，最佳方法就是移至 [{{site.data.keyword.cloud_notm}} Developer Tools GitHub 儲存庫的 JetBrains 頁面](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")，然後遵循指示進行。

## 用法
{: #jetbrains-usage}

您可以從現有的伺服器端應用程式開始，並啟用它的雲端功能，或使用 {{site.data.keyword.dev_cli_notm}} CLI 從入門範本套件建立新的應用程式 (`ibmcloud dev create`)。若您具有應用程式的專案，請在 JetBrains IDE 中開啟它。

若要對通用伺服器端應用程式啟用雲端功能，請選取**工具** > **IBM Cloud Developer Tools** > **針對 {{site.data.keyword.cloud_notm}} 啟用應用程式**。這時會檢查所有必要檔案，並在必要時新增它們，以使用 Cloud Foundry 應用程式或在 Kubernetes 叢集內部署至 {{site.data.keyword.cloud_notm}}。

請使用 {{site.data.keyword.cloud_notm}} Developer Tools 功能表中的基本建置、執行及部署動作來開發雲端原生應用程式。如果您需要執行不在功能表中的動作，請直接開啟終端機標籤，然後手動輸入指令。
