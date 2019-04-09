---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-01"

keywords: IBM Cloud Developer Tools CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 開始使用 {{site.data.keyword.cloud_notm}} CLI
{: #ibmcloud-cli}

在本指導教學中，您將安裝一組 {{site.data.keyword.cloud}} Developer Tools、驗證安裝，並配置環境。{{site.data.keyword.cloud_notm}} Developer Tools 提供指令行方法，以建立、開發及部署 Web、行動及微服務應用程式。
{: shortdesc}

安裝之後，您會得到獨立式 {{site.data.keyword.cloud_notm}} CLI，以及下列工具：

* `Homebrew`（僅限 Mac）
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 外掛程式
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 外掛程式
* {{site.data.keyword.registrylong_notm}} 外掛程式
* {{site.data.keyword.containerlong_notm}} 外掛程式
* `sdk-gen` 外掛程式

## 開始之前
{: #idt-prereq}

您需要 [{{site.data.keyword.cloud_notm}} 帳戶](https://cloud.ibm.com/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 及下列系統需求：

* 如果您執行 Windows，則除非您執行 Windows 10 Pro，否則不支援部分功能。
* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 步驟 1. 執行安裝指令
{: #step1-install-idt}

* 若為 Mac 和 Linux，請執行下列指令：
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* 若為 Windows 10 Pro，請以管理者身分執行下列指令：
  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

    在 Windows PowerShell 圖示上按一下滑鼠右鍵，然後選取**以系統管理員身分執行**。
  {: tip}

  您也可以從這個 [GitHub 儲存庫](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 下載安裝程式 Script。

<!--Uncomment when this linked topic goes to prod.
  For the steps to install these tools manually, see [Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->

## 步驟 2. 驗證安裝
{: #step2-verify-idt}

若要驗證是否已順利安裝 CLI 及 Developer Tools，請執行 `help` 指令：
```
ibmcloud dev help
```
{: codeblock}

輸出會列出用法指示、現行版本及支援的指令。

## 步驟 3. 配置環境
{: #step3-configure-idt-env}

1. 使用 IBM ID 登入 {{site.data.keyword.cloud_notm}}。如果您有多個帳戶，則系統會提示您選取要使用的帳戶。如果您未使用 `-r` 旗標來指定地區，則必須同時選擇地區。
  ```
   ibmcloud login
   ```
  {: codeblock}
  
  如果您的認證遭到拒絕，您可能是使用聯合 ID。若要使用聯合 ID 來登入，請使用 `--sso` 旗標。如需詳細資料，請參閱[使用聯合 ID 進行登入](/docs/iam/federated_id?topic=iam-federated_id#federated_id)。
  {: tip}

2. 若要使用 Cloud Foundry 服務，請將組織及空間設為目標。
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  您可以選擇使用前一個指令的輸出，以下列指令手動設定您的組織及空間：
  ```
ibmcloud target -o <value> -s <value>
	```
  {: codeblock}

## 後續步驟
{: #next-steps}

您現在已準備好開始開發及部署您的第一個應用程式！如需相關資訊，請參閱[使用 CLI 建立及部署應用程式](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)。
