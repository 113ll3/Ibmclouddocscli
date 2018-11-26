---

copyright:

  years: 2018
lastupdated: "2018-11-13"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 從 Docker 容器使用 {{site.data.keyword.dev_cli_notm}}

使用 {{site.data.keyword.dev_cli_notm}} Docker 容器，您會得到 {{site.data.keyword.Bluemix}} CLI，以及下列工具：

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 外掛程式
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 外掛程式
* {{site.data.keyword.registrylong_notm}} 外掛程式
* {{site.data.keyword.containerlong_notm}} 外掛程式
* `sdk-gen` 外掛程式

## 開始之前
{: #prereq}

您需要 [{{site.data.keyword.Bluemix_notm}} 帳戶](https://console.bluemix.net/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")，且必須在採取下列步驟之前安裝最新的穩定 Docker 版本。

## 步驟 1. 從 Docker Hub 取回 Docker 映像檔。
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步驟 2. 啟動 Docker 容器。
{: #step2}

使用下列指令來啟動 {{site.data.keyword.dev_cli_notm}} Docker 容器。

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步驟 3. 使用 IBM ID 登入 {{site.data.keyword.Bluemix_notm}}。
{: #step3}

```
ibmcloud login
```
{: codeblock}


如果您的認證遭到拒絕，您可能是使用聯合 ID。如需詳細資料，請參閱[使用聯合 ID 進行登入](/docs/iam/login_fedid.html#federated_id)。
{: tip}

{{site.data.keyword.dev_cli_notm}} CLI 外掛程式使用兩個容器來協助建置及測試應用程式。第一個是 tools 容器，其中包含用來建置及測試應用程式的必要公用程式。此容器的 `Dockerfile` 是透過 [`dockerfile-tools`](/docs/cli/idt/commands.html#command-parameters) 參數所定義。您可能會將它視為一個開發容器，因為它包含一般用於開發特定運行環境的工具。

第二個容器是 run 容器，可在應用程式部署至雲端之後，密切模擬您應用程式的實際運行環境。此容器為適合部署以供在例如 {{site.data.keyword.Bluemix_notm}} 中使用的形式。因此，定義的進入點可啟動您的應用程式。當您選擇透過 {{site.data.keyword.dev_cli_notm}} 執行應用程式時，它會使用此容器。此容器的 `Dockerfile` 是透過 [`dockerfile-run`](/docs/cli/idt/commands.html#run-parameters) 參數所定義。

現在您可以使用 {{site.data.keyword.dev_cli_notm}} 來管理 {{site.data.keyword.Bluemix_notm}} 資源，以及開發和部署應用程式。
