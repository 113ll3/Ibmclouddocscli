---
copyright:

  years: 2018

lastupdated: "2018-06-27"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# 開發及部署應用程式
{: #developing}

使用 {{site.data.keyword.dev_cli_notm}} CLI 開發「雲端原生」應用程式時遵循相當簡單的流程：

1. [建立或啟用應用程式](#create)
2. 使用容器在本端[編寫程式碼、建置及執行](#build)應用程式
3. 將應用程式[部署](#deploy)至 {{site.data.keyword.Bluemix_notm}}

## 建立或啟用應用程式
{: #create}

您有數種方式可以建立「雲端」應用程式。
- 適用於通用 Web 應用程式及微服務的[應用程式服務 Web 主控台](https://console.bluemix.net/developer/appservice)
- 用於建立啟用 Watson 型功能之入門範本應用程式的 [Watson 儀表板](https://console.bluemix.net/dashboard/watson)。
    - 其他產業及技術型儀表板可以從 {{site.data.keyword.Bluemix_notm}} 首頁上的「漢堡式」功能表取得。全部都採用使用「入門範本套件」建立新應用程式的類似方法。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev create`](./commands.html#create) 指令以建立新的應用程式。
- {{site.data.keyword.dev_cli_notm}} CLI 的 [`ibmcloud dev enable`](./commands.html#enable) 指令以快速在現有伺服器端應用程式上啟用雲端。

針對上述任何建立方法，流程類似。您可以選擇要使用的專案類型、實作語言及應用程式模式。您也可以選擇將加值型服務新增至應用程式（例如鑑別或持續性）。最後，您可以選擇啟用應用程式的 DevOps 功能，以提供來源控制及團隊通訊的完整工具鏈，以及每次確定時觸發的管線，以驗證、建置及部署您的應用程式至 IBM Cloud。

![使用 IDT CLI 的範例建立流程](create_flow.png "使用 IDT CLI 的範例建立流程") <br> 圖 2. 使用 IDT CLI 的範例建立流程

{{site.data.keyword.dev_cli_notm}} CLI 緊密合作，以在開發期間提供無縫經驗。在任何 Web 主控台內建立的專案都會提供「下載程式碼」按鈕，以將產生的原始碼下載至工作站，以進行更多開發。

### 有用的 CLI 指令
{: #helpful}

下列 CLI 指令可協助您處理專案及 Web 主控台：
- [`code`](./commands.html#code) 將應用程式的已產生原始碼直接取回到工作站
- [`console`](./commands.html#console) 將瀏覽器開啟到 {{site.data.keyword.Bluemix_notm}} 中現行應用程式的專案頁面
- [`create`](./commands.html#create) 指令以建立新的應用程式。
- [`delete`](./commands.html#delete) 以從 {{site.data.keyword.Bluemix_notm}} 專案區域中刪除現行應用程式。
- [`enable`](./commands.html#enable) 指令以對現有的伺服器端應用程式啟用雲端功能。
- [`get-credentials`](./commands.html#get-credentials) 以取得專案所需的認證，以啟用連結服務的使用。
- [`list`](./commands.html#list) 以從 CLI 或主控台，列出您已在目前選取的組織/空間中所建立的所有應用程式。


### 探索應用程式的專案結構
{: #exploring-project}

已建立或啟用以與工具搭配使用的專案，會在 `cli-config.yml` 檔案中具有封裝的預先配置設定。`cli-config.yml` 包含工具指令所使用的預設項目，其可置換為透過指令行所傳遞的值。

您可以在這裡找到專案結構的其他詳細資料：
- [Java 專案](/docs/apps/projects/java_project_contents.html)
- [NodeJS 專案](/docs/apps/projects/node_project_contents.html)
- [Python 專案](/docs/apps/projects/python_project_contents.html)
- [Swift 專案](/docs/apps/projects/swift_project_contents.html)


### 參照部落格及視訊
{: #ref1}

- 視訊：[Installing IDT on Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- 部落格：[Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## 編寫程式碼、建置及執行
{: #build}


建立專案之後，您現在可以將它精心製作成有用的項目。一般流程包含編輯原始碼，然後執行 [`ibmcloud dev build`](commands.html#build) 以在應用程式語言及配置特有的本端容器內編譯應用程式。根據使用的應用程式語言及產生器，有一個以上的容器預設為支援在本端進行建置及執行。一般而言，將會有 "tools" 容器以進行建置及本端除錯。此容器通常會有額外的工具及功能可協助您進行開發。還有一個 "run" 容器，可在部署至雲端（在 Cloud Foundry 或 IBM 的 Kubernetes 型容器環境中）之後，緊密模擬您應用程式的實際運行環境環境。


您可以免費使用偏好用來編寫應用程式的 IDE 或編輯器。我們提供 Microsoft VisualStudio Code (VSCode) 編輯器的延伸規格，讓您能夠直接在編輯器內存取所有 IDE 指令。

根據應用程式的產生器配置，在建置專案之後，您接著想要使用 [`ibmcloud dev run`](commands.html#run) 或 [`ibmcloud dev debug`](commands.html#debug) 來執行應用程式。這會在適當的容器內執行應用程式。部分應用程式模式支援應用程式外部的多個容器（例如持續性或其他功能）。這些會在執行或除錯期間自動啟動及配置。還有 [`ibmcloud dev test`](commands.html#test) 指令可執行與應用程式相關聯的任何測試案例。


### 本端容器的使用方式
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI 使用兩個容器來協助建置及測試應用程式。第一個是 tools 容器，其中包含用來建置及測試應用程式的必要公用程式。此容器的 Dockerfile 是透過 [`dockerfile-tools`](commands.html#command-parameters) 參數所定義。您可能會將它視為開發容器，因為它包含一般用於開發特定運行環境的工具。

第二個容器是 run 容器。此容器是適合部署以供使用的表單，例如，在 {{site.data.keyword.Bluemix}} 中。因此，定義的進入點可啟動您的應用程式。當您選擇透過 {{site.data.keyword.dev_cli_short}} CLI 執行應用程式時，它會使用此容器。此容器的 Dockerfile 是透過 [`dockerfile-run`](commands.html#run-parameters) 參數所定義。


### 有用的 CLI 指令
{: #helpful2}

下列 CLI 指令可協助您在編寫程式碼、建置及執行週期期間處理專案：
- [`build`](./commands.html#build)：在本端容器中建置專案
- [`debug`](./commands.html#debug)：在本端容器中針對您的應用程式進行除錯
- [`run`](./commands.html#run)：在本端容器中執行應用程式
- [`shell`](./commands.html#shell)：將 Shell 開啟到本端容器
- [`status`](./commands.html#status)：檢查 CLI 所使用容器的狀態
- [`stop`](./commands.html#stop)：停止容器
- [`test`](./commands.html#test)：在本端容器中測試應用程式

### 參照部落格及視訊
{: #ref2}

- [對本端應用程式進行除錯](local_debug.html)





## 部署
{: #deploy}

在適當的雲端原生環境下，您想要利用完整運作的 DevOps 管線來管理所有部署，以及其他許多功能。在建立流程期間，您可以設定應用程式以使用 IBM Cloud 的 DevOps。如果您還沒有準備好使用內建 DevOps，則可以手動對應用程式執行 [`ibmcloud dev deploy`](./commands.html#deploy)，或在自己的 DevOps 管線內使用 deploy 指令。  



### 有用的 CLI 指令
{: #helpful3}

下列 CLI 指令可協助您在部署處理程序期間處理專案：
- [`console`](./commands.html#console)：開啟專案的 IBM Cloud 主控台
- [`deploy`](./commands.html#deploy)：將應用程式部署至 IBM Cloud
- [`view`](./commands.html#view)：檢視專案的 URL


### 參照部落格及視訊
{: #ref3}

- 部落格：[Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- 部落格：[Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
