---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK 產生器
{: #sdk-cli}

{{site.data.keyword.IBM}} SDK 產生器外掛程式可以安裝在 [{{site.data.keyword.Bluemix_notm}} CLI ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/cli/reference/bluemix_cli/all_versions.html)。

作為 {{site.data.keyword.Bluemix_notm}} 的開發人員，您可以使用此外掛程式，從遵循 [開放式 API 規格 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.openapis.org/) 的 REST API 定義產生 SDK。當您變更 REST API 定義時，可以使用此外掛程式只重新產生 SDK，而不必重新產生整個專案。

您也可以查看特定空間中的 Cloud Foundry 應用程式是否具有可用於 SDK 產生的 REST API 定義。最後，您可以使用 {{site.data.keyword.IBM_notm}} SDK 產生器外掛程式來驗證任何 REST API 定義，以確保它們遵守 SDK 產生器的要求。

這個 {{site.data.keyword.IBM_notm}} SDK 產生器外掛程式，容許您使用產生的 SDK 輕鬆地將後端服務整合到您的應用程式。當 REST API 發生變更時，您可以重新產生 SDK 並取代舊的，以進行 SDK 升級。您也可以將 CLI 整合至 DevOps 管線，並確保每次建置應用程式時，SDK 永遠與 API 規格一致。

REST API 定義必須有效，且在即時伺服器端點上或您系統的本端檔案上管理。如果 REST API 定義已管理，相對 URL 必須定義在 `OPENAPI_SPEC` 環境變數中。


## 需求
{: #prereqs}

請確定您滿足下列需求。

* 您有 [{{site.data.keyword.Bluemix_notm}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://bluemix.net) 帳戶
* 符合[開放式 API ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.openapis.org/) 規格的有效 API 定義


## 安裝
{: #installation}

1. [安裝 {{site.data.keyword.Bluemix}} CLI ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://clis.ng.bluemix.net/ui/home.html)。

2. [安裝外掛程式 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/cli/reference/bluemix_cli/all_versions.html#install_plug-in)。

	```
	bx plugin install sdk-gen
	```
	{: codeblock}


## 指令
{: #commands}

使用下列指令來產生 SDK、驗證開放式 API 定義檔，或列出 Cloud Foundry 應用程式。


### 產生 SDK
{: #gen}

使用 `bx sdk generate [arguments...] [command options]`。


#### 引數
{: #gen-args}

* `APP_NAME` - 您現行空間中 Cloud Foundry 應用程式的名稱
* `OPENAPI_DOC_LOCATION` - 原始 REST API 定義 JSON 或 Yaml 的 URL 或相對檔案路徑
* `GENERATED_SDK_NAME`（選用）- 所產生 SDK 的名稱


#### 選項
{: #gen-options}

* `PLATFORM`（必要）
   * `--android` - 產生 Android SDK
   * `--ios` - 產生 iOS Swift SDK
   * `--swift` - 產生 Swift 伺服器 SDK
   * `--js` - 產生 JavaScript SDK
* `LOCATION`（必要）- 指定 `OPENAPI_DOC_LOCATION` 的類型
   * `-r` - 遠端 URL
   * `-f` - 檔案
   * `-a` - 在 {{site.data.keyword.Bluemix_notm}} 上執行的應用程式
   * `-l` - 本端主機 URL
* `--output "YOUR_RELATIVE_PATH"`（選用）- 將產生的 SDK 放置在 `YOUR_RELATIVE_PATH` 所指定的目錄（在現有 SDK 存在時改寫）
* `--unzip`（選用）- 擷取所產生的 SDK（在現有 SDK 構件存在時改寫）


#### 用法
{: #gen-usage}

若要從 {{site.data.keyword.Bluemix_notm}} 中所執行的 Cloud Foundry 應用程式產生 SDK，您可以使用應用程式的名稱作為 CLI 的參數。下列指令使用應用程式的名稱作為 `SDK_Name`。

```
bx sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

若要從開放式 API 定義檔或是本端 JSON 或 Yaml 檔案的 URL 產生 SDK，請使用下列指令。

```
bx sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### 驗證開放式 API 定義
{: #validating}

使用 `bx sdk validate [argument]`。


#### 引數
{: #val-args}

* `APP_NAME` - 您現行空間中 Cloud Foundry 應用程式的名稱
* `OPENAPI_DOC_LOCATION` - 原始 REST API 定義 JSON 或 Yaml 的 URL 或相對檔案路徑


#### 用法
{: #val-usage}

若要驗證在 {{site.data.keyword.Bluemix_notm}} 中執行之 Cloud Foundry 應用程式的 API 規格，您可以使用應用程式的名稱作為 CLI 的參數。

```
bx sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

若要從 API 規格文件或是本端 JSON 或 Yaml 檔案的 URL 驗證 SDK，請使用下列指令。

```
bx sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### 列出應用程式 (Cloud Foundry)
{: #list-apps}

使用 `bx sdk list [argument] [option]` 來列出應用程式，以及驗證 API 規格。您必須將 `OPENAPI_SPEC` 環境變數設為管理規格的相對 URL 路徑。


#### 引數
{: #list-args}

* `SPACE_NAME`（選用）- 現行組織內您要搜尋應用程式的 Cloud Foundry 空間名稱。如果未提供，則會搜尋現行空間。


#### 選項
{: #list-options}

* `--url`（選用）- 顯示清單中每一個應用程式之開放式 API 定義的完整格式 URL


#### 用法
{: #list-usage}

若要列出現行空間中的應用程式，請使用下列指令。

```
bx sdk list
```
{: codeblock}

若要列出現行空間中的應用程式，並顯示 API 規格 URL，請使用下列指令。

```
bx sdk list --url
```
{: codeblock}

若要列出特定空間中的應用程式，請使用下列指令。

```
bx sdk list [SPACE_NAME]
```
{: codeblock}

若要列出特定空間中的應用程式，並顯示 API 規格 URL，請使用下列指令。

```
bx sdk list [SPACE_NAME] --url
```
{: codeblock}
