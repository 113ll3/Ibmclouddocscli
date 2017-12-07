---



copyright:

  years: 2015，2017

lastupdated: "2011-01-12"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Auto-Scaling CLI
{: #autoscalingcli}


您可以利用 {{site.data.keyword.autoscaling}} CLI for {{site.data.keyword.Bluemix_notm}} 來配置 {{site.data.keyword.autoscaling}} 服務。{{site.data.keyword.autoscaling}} CLI 支援 Linux64、Win64 及 OSX，並提供類似於 Auto-Scaling RESTful API 所提供的功能。
{: shortdesc}

開始之前，請先安裝 {{site.data.keyword.Bluemix_notm}} CLI。如需指示，請參閱[下載 {{site.data.keyword.Bluemix_notm}} CLI ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/home.html){: new_window}。

## 新增 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式

在安裝 {{site.data.keyword.Bluemix_notm}} CLI 之後，您可以新增 {{site.data.keyword.autoscaling}} CLI 外掛程式。

完成下列步驟以新增儲存庫並安裝外掛程式：
1. 若要新增 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式儲存庫，請執行下列指令：

```
bluemix plugin repo-add bluemix-plugin-repo https://plugins.ng.bluemix.net
```
2. 若要安裝 {{site.data.keyword.autoscaling}} CLI 外掛程式，請執行下列指令：

```
bluemix plugin install auto-scaling -r Bluemix
```

## 附加自動擴充原則

您可以將自動擴充原則附加至特定應用程式。請執行下列指令：

```
bx as policy-attach <APP_NAME> -p <policy_file>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">您要將自動擴充原則附加至其中的應用程式名稱。</dd>
<dt class="pt dlterm">&lt;policy_file&gt;</dt>
<dd class="pd">說明自動擴充原則之 JSON 檔案的名稱。如需其他詳細資料，請參閱 <a href="https://new-console.{DomainName}/apidocs/48" target="_blank">{{site.data.keyword.autoscaling}} RESTful API 文件</a>。</dd>
</dl>


## 產生自動擴充原則

您可以透過在指令行介面上回答問題來產生自動擴充原則。視您的輸入而定，會以您輸入的名稱儲存一個包含自動擴充原則定義的 JSON 檔案。如果您未輸入檔名，原則內容會直接列印至指令行，而不會將它儲存至檔案。請執行下列指令：

```
bx as policy-create
```
{: codeblock}


## 顯示自動擴充原則

您可以顯示應用程式的自動擴充原則。原則的內容會直接列印至指令行。請執行下列指令：

```

bx as policy-show <APP_NAME> [--json]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">您要顯示其自動擴充原則的應用程式名稱。依預設，JSON 結構會轉換為一系列人類可閱讀的輸出。</dd>
</dl>

**提示：**您也可以使用 **--json** 選項，來進行原始 JSON 回應的細緻列印。


## 分離自動擴充原則

您可以從應用程式移除自動擴充原則。請執行下列指令：

```
bx as policy-detach <APP_NAME>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">您要分離其自動擴充原則的應用程式名稱。</dd>
</dl>


## 啟用或停用自動擴充原則

您可以啟用或停用特定應用程式的自動擴充原則。請執行下列指令：

```
bx as policy-enable|policy-disable <APP_NAME>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">您要啟用或停用其自動擴充原則的應用程式名稱。</dd>
</dl>


## 顯示應用程式的自動擴充歷程

您可以顯示特定應用程式之自動擴充活動的歷程。自動擴充歷程記錄的表格會顯示在指令行介面中。

```

bx as history-show <APP_NAME>  [--start-date=<start_timestamp>]  [--end-date=<end_timestamp>]  [--json]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">您要顯示其自動擴充原則歷程的應用程式名稱。
<dt class="pt dlterm">&lt;start_timestamp&gt;</dt>
<dd class="pd">歷程範圍開始的時間戳記。支援的格式為 `yyyy-MM-ddTHH:mm:ss+/-hhmm、yyyy-MM-ddTHH:mm:ssZ`。依預設，時間戳記會設為現行時間前的 50 小時。如需有關時間戳記格式的詳細資料，請參閱 <a href="https://www.w3.org/TR/NOTE-datetime" target="_blank">W3C 日期和時間格式標準</a>。
<dt class="pt dlterm">&lt;end_timestamp&gt;</dt>
<dd class="pd">歷程範圍結束的時間戳記。支援的格式為 `yyyy-MM-ddTHH:mm:ss+/-hhmm、yyyy-MM-ddTHH:mm:ssZ`。依預設，時間戳記會設為現行時間。如需有關時間戳記格式的詳細資料，請參閱 <a href="https://www.w3.org/TR/NOTE-datetime" target="_blank">W3C 日期和時間格式標準</a>。
</dl>



**提示：**您也可以使用 **--json** 選項，來進行原始 JSON 回應的細緻列印。

# rellinks
{: rellinks}
## general
{: general}
* [{{site.data.keyword.autoscaling}} 服務](/docs/services/Auto-Scaling/index.html)
* [{{site.data.keyword.Bluemix_notm}} CLI ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/home.html){: new_window}
* [W3C Date and Time Formats standard ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://www.w3.org/TR/NOTE-datetime){: new_window}
