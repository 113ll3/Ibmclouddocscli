---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# 手動安裝 {{site.data.keyword.cloud_notm}} Developer Tools CLI 外掛程式元件
{: #install-devtools-manually}

如果您偏好更精細的控制來安裝 Developer Tools 元件，則可以使用下列步驟手動進行安裝。否則，會使用[平台安裝程式](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)為大部分使用者自動安裝所有必要條件。
{: shortdesc}

## 開始之前
{: cli-before-you-begin}

* 安裝獨立式 [{{site.data.keyword.cloud}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)，以支援安裝 `ibmcloud` 的指令行外掛程式。
* 安裝 [curl](https://curl.haxx.se/download.html){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 指令，以透過指令行來下載套件。

## 步驟 1. 安裝 {{site.data.keyword.cloud_notm}} Developer Tools CLI 外掛程式
{: #install-devtools-idt}

您可以使用 {{site.data.keyword.cloud_notm}} Developer Tools CLI (ibmcloud dev) 指令來建立、管理、部署、除錯及測試應用程式。

執行下列指令，以安裝 `dev` 外掛程式： 
```
ibmcloud plugin install dev
```
{: codeblock}

## 步驟 2. 安裝 Docker
{: #install-devtools-docker}

若要在本端執行及除錯應用程式，請安裝 [Docker](https://www.docker.com/get-docker){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

## 步驟 3. 安裝 Kubernetes：
{: #idt-install-kube}

Kubernetes 是一種開放程式碼容器編排引擎，可自動化部署、調整及管理容器化應用程式。

若要支援容器化部署，請安裝您平台適用的 Kubernetes：

* MacOS：
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
  {: codeblock}

* Linux&trade;：
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
  {: codeblock}

* Windows&trade;：
  ```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
  {: codeblock}

## 步驟 4. 安裝 Kubernetes CLI 外掛程式
{: #idt-install-kubernetes-cli-plugins}

若要從指令行管理 Kubernetes 部署，請安裝下列容器外掛程式：

* 安裝 `container-registry` 外掛程式：
  ```
ibmcloud plugin install container-registry
```
  {: codeblock}

* 安裝 `container-service` 外掛程式：
  ```
ibmcloud plugin install container-service
```
  {: codeblock}

如需相關資訊，請參閱[設定 CLI 及 API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install)。

## 步驟 5. 安裝 Helm：
{: #idt-install-helm}

安裝 [Helm](https://helm.sh/docs/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")，這是 Kubernetes 型套件管理程式。

* MacOS 及 Linux&trade; 使用者，請執行下列指令：
  ```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
  {: codeblock}

* Windows&trade; 使用者可下載及安裝 Helm [二進位檔](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

## 步驟 6. 安裝 {{site.data.keyword.openwhisk_short}} CLI 外掛程式
{: #idt-install-functions}

您可以使用 {{site.data.keyword.openwhisk}} CLI 外掛程式來管理作用中的程式碼 Snippet、建立觸發程式和規則來啟用回應事件的動作，以及將動作組合為套件。

若要安裝 {{site.data.keyword.openwhisk_short}} CLI 外掛程式，請執行下列指令：
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

如需相關資訊，請參閱[設定 {{site.data.keyword.openwhisk_short}} CLI 外掛程式](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)。

## 步驟 7. 安裝 SDK 產生器 CLI 外掛程式
{: #idt-install-sdk-gen}

作為 {{site.data.keyword.cloud_notm}} 的開發人員，您可以使用此外掛程式，從遵循 [開放式 API 規格 ](https://www.openapis.org/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 的 REST API 定義產生 SDK。當您變更 REST API 定義時，可以使用此外掛程式只重新產生 SDK，而不必重新產生整個專案。

安裝 SDK 產生器 CLI 外掛程式：
```
ibmcloud plugin install sdk-gen
	```
{: codeblock}

如需相關資訊，請參閱 [SDK 產生器](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)。
