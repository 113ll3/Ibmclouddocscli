---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# 安裝獨立式 {{site.data.keyword.cloud_notm}} CLI
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI 提供指令行介面，以便在 {{site.data.keyword.cloud_notm}} 中管理資源。您仍可以使用 `cf` CLI 登入 {{site.data.keyword.cloud_notm}}，但它適用於 {{site.data.keyword.cloud_notm}} 中的 Cloud Foundry 服務。 

如果您想要同時安裝最新的 {{site.data.keyword.cloud}} CLI 及其他建議外掛程式和工具，來開發 {{site.data.keyword.cloud_notm}} 的應用程式，請參閱[開始使用 {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started)。
{: tip}

## 開始之前
{: #before-download-cli}

如果您需要使用 32 位元版本或舊版（而非 {{site.data.keyword.cloud_notm}} Dedicated 環境的最新版本），請參閱 [{{site.data.keyword.cloud_notm}} CLI 版本](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")。

## 使用安裝程式來安裝
{: #ibmcloud-cli-installer}

請使用下列步驟，以安裝最新的獨立式 {{site.data.keyword.cloud_notm}} CLI：

1. 使用瀏覽器來存取正式 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub 儲存庫，並**選取**您 OS 的安裝程式以開始下載。支援下列作業系統：macOS X 64 位元、Windows&trade; 64 位元、Linux&trade; x86 64 位元及 Linux&trade; LE 64 位元 (ppc64le)。

2. 執行安裝程式：
  * 若為 Mac 及 Windows&trade;，請執行安裝程式。
  * 若為 Linux&trade;，請解壓縮套件並執行 `install` Script。

3. 登入 {{site.data.keyword.cloud_notm}}：
  ```
   ibmcloud login
   ```
  {: codeblock}
   
  現在，您已準備好管理 {{site.data.keyword.cloud_notm}} 資源。輸入 `ibmcloud help` 以檢視指令說明。

  如果您是使用聯合 ID，請[使用一次性密碼或 API 金鑰進行登入](/docs/iam?topic=iam-federated_id)。
  {: tip}

## 從 Shell 安裝
{: #shell_install}

若要從 Shell 為您的 OS 手動安裝最新 CLI，請針對您的 OS 使用下列指令：

* 若為 **Mac**，請複製下列指令、將其貼至終端機，然後執行它：
  ```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
  {: codeblock}

* 若為 **Linux&trade;**，請複製下列指令、將其貼至終端機，然後執行它：
  ```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
  {: codeblock}

* 若為 **Windows&trade;**，請複製下列指令、將其貼至 [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示") 終端機主控台，然後執行它：
  ```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
  {: codeblock}

## 安裝至自訂目錄
{: #install-custom-dir}

當您使用安裝程式或 Shell Script 來安裝 {{site.data.keyword.cloud_notm}} CLI 時，它會安裝在您的系統目錄中。如果您想要指定不同目錄，請使用下列步驟。

1. 使用瀏覽器來存取正式 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub 儲存庫，並**選取**您平台的符合二進位檔以開始下載。支援下列平台：macOS、linux32、linux64、ppc64le、win32 及 win64。

2. 將套件解壓縮到您指定的目錄。

   您可以看到下列解壓縮的內容：

   若為 Linux&trade; 及 Mac：
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   若為 Windows&trade;：
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. 新增至 `PATH` 環境變數並啟用 Shell 自動完成。
  * 將 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 新增至 `PATH` 環境變數。
  * 如需 Shell 自動完成支援（僅限 Mac 及 Linux&trade;），請參閱[啟用 IBM Cloud CLI 的 Shell 自動完成](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。

## 更新 {{site.data.keyword.cloud_notm}} CLI
{: #update-ibmcloud-cli}

您必須使用最新版本的 CLI。如果不是使用最新版本，請執行下列指令來更新您的 CLI：

```
ibmcloud update
```
{: codeblock}

若要判定您的 {{site.data.keyword.cloud_notm}} CLI 版本，請執行下列指令：
```
ibmcloud -v
```
{: codeblock}

如果您是執行現行版本，則會顯示下列輸出：
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

若要收到關於 {{site.data.keyword.cloud_notm}} CLI 版本的通知，請訂閱 [{{site.data.keyword.cloud_notm}} CLI 版本儲存庫](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")。
