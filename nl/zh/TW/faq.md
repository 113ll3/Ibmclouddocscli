---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# 常見問題
{: #ibm-cli-faq}

## 需要使用 {{site.data.keyword.cloud_notm}} CLI 的最新版本嗎？
{: #cli-latest-version}

是，您必須使用最新版本。您可以執行下列指令來檢查正在使用的版本：

```
ibmcloud -v
```
{: codeblock}

## 如何更新我的 CLI？
{: #cli-update-version}

請執行下列指令來更新為 CLI 的最新版本：

```
ibmcloud update
```
{: codeblock}

## 是否可以收到新版 CLI 的通知？
{: #cli-get-notified}

是，當提供新版 CLI 時，您便會收到第一手資料。請訂閱 [{{site.data.keyword.cloud_notm}} CLI 版本儲存庫](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")。

## {{site.data.keyword.cloud_notm}} 應用程式的檔案結構為何？
{: #cli-file-structure}

從 CLI 建立或啟用的應用程式，會隨附 `cli-config.yml` 檔中所封裝的預先配置設定。`cli-config.yml` 包含 CLI 的指令所使用的預設項目，其可置換為透過指令行所傳遞的值。

已部署至 DevOps 工具鏈的應用程式也可能包含 `toolchain.yml` 及 `pipeline.yml` 之類的檔案。手動部署的應用程式可以包含 `manifest.yml` 及 Helm 圖表檔案（比方說，用於部署至 Cloud Foundry 或 Kubernetes）。

## 如何使用本端容器？
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 外掛程式使用兩個容器來協助建置及測試應用程式。第一個是 tools 容器，其中包含用來建置及測試應用程式的必要公用程式。此容器的 `Dockerfile` 是透過 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 參數所定義。您可能會將它視為一個開發容器，因為它包含一般用於開發特定運行環境的工具。

第二個容器是 run 容器，一旦您的應用程式部署至雲端，該容器便會緊密模擬您應用程式的實際運行環境。此容器為適合部署以供在例如 {{site.data.keyword.cloud_notm}} 中使用的形式。因此，定義了一個進入點以便啟動您的應用程式。當您選擇透過 {{site.data.keyword.dev_cli_long}} CLI 外掛程式執行應用程式時，它會使用此容器。此容器的 `Dockerfile` 是透過 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 參數所定義。

## 如何部署現有的程式碼？

若要部署現有程式碼庫，請參閱[產生部署及雲端啟用資產](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)。

