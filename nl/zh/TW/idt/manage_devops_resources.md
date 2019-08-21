---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# 使用 CLI 管理 DevOps 資源
{: #managing-devops-resources-cli}

您可以使用 [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started) 直接從指令行管理 DevOps 資源。瞭解如何使用 CLI 來檢視 DevOps 工具鏈、管線和管線日誌。
{: shortdesc}

## 開始之前
{: #set-toolchain-view}

工具鏈視圖取決於現行目標資源群組。使用下列指令來識別現行目標資源群組，並在需要時對其進行變更。

* 若要檢視現行目標資源群組，請執行下列指令：
  ```
ibmcloud target
``` 
  {: codeblock}

* 如果未設定資源群組，或您要變更資源群組，請執行下列指令： 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## 檢視工具鏈
{: #viewing-toolchains}

您可以從指令行檢視工具鏈資訊，或在瀏覽器中檢視工具鏈資訊。

* 若要檢視目標資源群組中的工具鏈，請執行下列指令：
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* 若要檢視該工具鏈的詳細資料，請執行下列指令：
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* 若要在瀏覽器中檢視工具鏈詳細資料，請執行下列指令：
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## 檢視管線
{: #viewing-pipeline}

若要取得呼叫管線所需的詳細資料，請執行 `ibmcloud dev toolchains` 以取得工具鏈的名稱。如果已經知道名稱，請執行 `ibmcloud dev toolchain-get [toolchain-name]` 來取得該工具鏈的詳細資料。 

* 若要取得管線及其階段的詳細資料，請識別管線及其 ID 以執行下列指令：
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* 使用前一個指令中的管線 ID，您可以執行管線：
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  此指令會呼叫階段及其工作的執行。成功執行會為所選取階段中的每個工作產生工作執行。

## 檢視管線日誌
{: #viewing-pipeline-logs}

* 若要檢視來自管線執行的日誌，請執行下列指令：
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* 若要依階段過濾日誌，請套用前一個指令，並新增階段 ID：
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## 有用的 DevOps 指令
{: #helpful-devops-commands}

使用下列 `ibmcloud dev` 指令來管理 DevOps 資源。

### 工具鏈指令
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains)：檢視目標資源群組中工具鏈的清單。
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get)：檢視目標資源群組中所選取工具鏈的詳細資料。
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open)：在瀏覽器中開啟選取的工具鏈。
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete)：刪除工具鏈。

### 管線指令
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get)：檢視工具鏈管線的詳細資料。
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run)：執行管線。
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open)：在瀏覽器中開啟管線。
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log)：檢視管線執行的日誌。

如需相關資訊，請參閱完整的 `ibmcloud dev` [指令參考手冊](/docs/cli/idt?topic=idt-cli)。
