---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# 開始使用 {{site.data.keyword.cloud_notm}} CLI
{: #ibmcloud-cli}

在本指導教學中，您將安裝一組 {{site.data.keyword.cloud}} Developer Tools、驗證安裝，並配置環境。{{site.data.keyword.dev_cli_notm}} 提供指令行方法，以建立、開發及部署雲端應用程式。
{: shortdesc}

本指導教學中的安裝指令會安裝最新版的獨立式 {{site.data.keyword.cloud_notm}} CLI 版本，外加下列工具：

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

* 如果您是執行 Windows&trade;，則除非執行的是 Windows&trade; 10 Pro，否則不支援部分功能。
* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 步驟 1. 執行安裝指令
{: #step1-install-idt}

執行指令時會安裝最新版本的 {{site.data.keyword.cloud_notm}} CLI。

* 若為 Mac 和 Linux&trade;，請執行下列指令：
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* 若為 Windows&trade; 10 Pro，請以管理者身分執行下列指令：
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  在 Windows&trade; PowerShell 圖示上按一下滑鼠右鍵，然後選取**以系統管理員身分執行**。
  {: tip}

您也可以從這個 [GitHub 儲存庫](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 下載安裝程式 Script。

如果您需要使用 32 位元版本的 CLI 或舊版（而非 {{site.data.keyword.cloud_notm}} Dedicated 環境的最新版本），請參閱 [{{site.data.keyword.cloud_notm}} CLI 版本](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。
{: note}

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

2. 若要存取 Cloud Foundry 服務，您必須指定 Cloud Foundry 組織及空間。您可以執行下列指令，以互動方式識別組織及空間：
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  或者，如果您知道服務所屬的組織及空間，則可以使用下列指令：
  ```
ibmcloud target -o <value> -s <value>
	```
  {: codeblock}

## 後續步驟
{: #next-steps}

* 您現在已準備好開始開發及部署您的第一個應用程式。如需相關資訊，請參閱[使用 CLI 建立及部署應用程式](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)。

* 您可以收到關於新 {{site.data.keyword.cloud_notm}} CLI 版本的通知。請訂閱 [{{site.data.keyword.cloud_notm}} CLI 版本儲存庫](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。
