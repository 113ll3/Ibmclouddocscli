---

copyright:
  years: 2019
lastupdated: "2019-06-19"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# 手動安裝 {{site.data.keyword.cloud_notm}} Developer Tools CLI 外掛程式
{: #install-devtools-manually}

如果您希望以更精細控制的方式來安裝元件，則可以手動安裝 {{site.data.keyword.cloud}} Developer Tools 指令行介面 (CLI) 外掛程式。否則，會使用[平台安裝程式](/docs/cli?topic=cloud-cli-getting-started#step1-install-idt)為大部分使用者自動安裝所有必要條件。
{: shortdesc}

## 開始之前
{: cli-before-you-begin}

* 安裝獨立式 [{{site.data.keyword.cloud_notm}}CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)，以支援安裝 {{site.data.keyword.cloud_notm}} 的指令行外掛程式。
* 安裝 [curl](https://curl.haxx.se/download.html){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 指令，以透過指令行來下載套件。

## 安裝 {{site.data.keyword.cloud_notm}} Developer Tools CLI 外掛程式
{: #install-devtools-idt}

您可以使用 {{site.data.keyword.cloud_notm}} Developer Tools CLI 指令來建立、管理、部署、除錯及測試應用程式。

若要安裝 {{site.data.keyword.cloud_notm}} Developer Tools 外掛程式，請執行下列指令： 
```
ibmcloud plugin install dev
```
{: codeblock}

## 安裝 Docker
{: #install-devtools-docker}

若要在本端執行及除錯應用程式，請安裝 [Docker](https://www.docker.com/get-started){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

## 安裝 Kubernetes 指令行工具
{: #idt-install-kube}

若要檢視本端版本的 Kubernetes 儀表板，以及將應用程式部署至叢集，請針對您的平台安裝 [Kubernetes 指令行工具](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")：

* Mac：
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

使用 Kubernetes 指令行工具來執行指令的字首是 `kubectl`。如需相關資訊，請參閱[設定 CLI 及 API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install)。

## 安裝 {{site.data.keyword.cos_full_notm}} CLI 外掛程式

{{site.data.keyword.cos_full_notm}} 外掛程式會以 API 封套延伸 {{site.data.keyword.cloud_notm}} 指令行 (CLI)，以便使用 Object Storage 資源。

* 若要安裝 {{site.data.keyword.cos_full_notm}} 外掛程式，請執行下列指令：
  ```
  ibmcloud plugin install cloud-object-storage
  ```
  {: codeblock}

如需相關資訊，請參閱 [{{site.data.keyword.cos_full_notm}} 指令參考手冊](/docs/cloud-object-storage-cli-plugin?topic=cloud-object-storage-cli-ic-cos-cli)。

## 安裝 {{site.data.keyword.registrylong_notm}} CLI 外掛程式
{: #idt-install-container-registry-cli-plugin}

您可以使用 `container-registry` CLI 外掛程式，在 IBM 代管及管理的專用登錄中設定您自己的映像檔名稱空間，您可以在此登錄中儲存 Docker 映像檔，並與 {{site.data.keyword.cloud_notm}} 帳戶中的所有使用者共用這些映像檔。

* 若要安裝 {{site.data.keyword.registrylong}} 外掛程式，請執行下列指令：
  ```
ibmcloud plugin install container-registry
```
  {: codeblock}

如需相關資訊，請參閱 [{{site.data.keyword.registrylong}} 指令參考手冊](/docs/services/Registry?topic=container-registry-cli-plugin-containerregcli)。

## 安裝 {{site.data.keyword.containerlong_notm}} CLI 外掛程式
{: #idt-install-kubernetes-cli-plugin}

若要在 {{site.data.keyword.containerlong}} 中建立及管理 Kubernetes 叢集：

* 若要安裝 {{site.data.keyword.registryshort_notm}} 外掛程式，請執行下列指令：
  ```
ibmcloud plugin install container-service
```
  {: codeblock}

如需相關資訊，請參閱 [{{site.data.keyword.registryshort_notm}} 指令參考手冊](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference)。

## 安裝 Helm
{: #idt-install-helm}

安裝 [Helm](https://helm.sh/docs/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")，這是 Kubernetes 型套件管理程式。

* Mac 及 Linux&trade; 使用者，請執行下列指令：
  ```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
  {: codeblock}

* Windows&trade; 使用者可下載及安裝 Helm [二進位檔](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

## 安裝 {{site.data.keyword.openwhisk_short}} CLI 外掛程式
{: #idt-install-functions}

您可以使用 {{site.data.keyword.openwhisk}} CLI 外掛程式來管理作用中的程式碼 Snippet、將動作組合為套件，以及建立觸發程式和規則來啟用回應事件的動作。

若要安裝 {{site.data.keyword.openwhisk_short}} CLI 外掛程式，請執行下列指令：
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

如需相關資訊，請參閱[安裝 {{site.data.keyword.openwhisk_short}} CLI 外掛程式](/docs/openwhisk?topic=cloud-functions-cli_install)。

