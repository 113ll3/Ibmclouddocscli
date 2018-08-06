---



copyright:

  years: 2015，2017

lastupdated: "2018-05-24"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:prereq: .prereq}
{:download: .download}
{:pre: .pre}
{:app_name: data-hd-keyref="app_name"}
{:app_key: data-hd-keyref="app_key"}
{:app_secret: data-hd-keyref="app_secret"}
{:app_url: data-hd-keyref="app_url"}
{:host: data-hd-keyref="host"}
{:org_name: data-hd-keyref="org_name"}
{:route: data-hd-keyref="route"}
{:space_name: data-hd-keyref="space_name"}
{:service_name: data-hd-keyref="service_name"}
{:service_instance_name: data-hd-keyref="service_instance_name"}
{:user_ID: data-hd-keyref="user_ID"}
{:tip: .tip}

# 使用指令行介面下載、修改及重新部署 Cloud Foundry 應用程式

使用 {{site.data.keyword.Bluemix_notm}} 指令行介面，以下載、修改及重新部署 Cloud Foundry 應用程式和服務實例。
{:shortdesc}

開始之前，請下載並安裝 {{site.data.keyword.Bluemix_notm}} [CLI](/docs/cli/index.html#overview){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg)


**限制：**Cygwin 不支援指令行工具。在指令行視窗（而非 Cygwin 指令行視窗）中，使用此工具。
{:prereq}

安裝指令行介面之後，即可開始：

  1. {: download}將您應用程式的程式碼下載至新的目錄，以設定開發環境。

    <a class="xref" href="http://bluemix.net" target="_blank" title="（在新分頁或視窗中開啟）"><img class="image" src="images/btn_starter-code.svg" alt="下載應用程式碼" /> </a>

      **附註**：繼續之前，請先將 node 版本升級至 `8.9.x` 或 `package.json` 檔中的最新版本。

  2. 切換至您程式碼所在的目錄。

  <pre class="pre"><code class="hljs">cd <var class="keyword varname">your_new_directory</var></code></pre>

  3.  適當地變更應用程式碼。例如，如果您是使用 {{site.data.keyword.Bluemix}} 範例應用程式，而且您的應用程式包含 `src/main/webapp/index.html` 檔案，則可以修改它，並編輯 "Thanks for creating ..." 傳達新的訊息。請先確定應用程式在本端執行，再將它部署回 {{site.data.keyword.Bluemix_notm}}。

    記下 `manifest.yml` 檔案。將應用程式部署回 {{site.data.keyword.Bluemix_notm}} 時，此檔案用來決定您應用程式的 URL、記憶體配置、實例數以及其他決定性參數。您可以在 Cloud Foundry 文件中[深入閱讀資訊清單檔](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html){: new_window}。

    也請注意 `README.md` 檔案，它包含建置指示這類詳細資料（適用時）。

    附註：如果您的應用程式是 Liberty 應用程式，則必須先建置它，再重新部署。

  4. 連接並登入 {{site.data.keyword.Bluemix_notm}}。

  <pre class="pre"><code class="hljs">bluemix api https://api.<span class="keyword" data-hd-keyref="DomainName">DomainName</span></code></pre>

  <pre class="pre"><code class="hljs">bluemix login -u <var class="keyword varname" data-hd-keyref="user_ID">username</var> -o <var class="keyword varname" data-hd-keyref="org_name">org_name</var> -s <var class="keyword varname" data-hd-keyref="space_name">space_name</var></code></pre>

  如果您要使用聯合 ID，請使用 `-sso` 選項。

  <pre class="pre"><code class="hljs">bluemix login  -o <var class="keyword varname" data-hd-keyref="org_name">org_name</var> -s <var class="keyword varname" data-hd-keyref="space_name">space_name</var> -sso</code></pre>

  **附註**：如果值包含空格，您必須在 `username`、`org_name` 和 `space_name` 週圍加上單引號或雙引號，例如 `-o "my org"`。

  5. 從 <var class="keyword varname">your_new_directory</var> 中，使用 `bluemix app push` 指令以將應用程式重新部署至 {{site.data.keyword.Bluemix_notm}}。如需 `bx app push` 指令的相關資訊，請參閱[上傳應用程式](/docs/starters/upload_app.html)。

  <pre class="pre"><code class="hljs">bluemix app push <var class="keyword varname" data-hd-keyref="app_name">app_name</var></code></pre>

  6. 瀏覽至 https://<var class="keyword varname" data-hd-keyref="app_url">app_url</var>.<span class="keyword" data-hd-keyref="APPDomain">AppDomainName</span>，以存取應用程式。
