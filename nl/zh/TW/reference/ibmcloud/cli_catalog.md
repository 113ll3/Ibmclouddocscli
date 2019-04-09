---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 搜尋及管理型錄供應項目
{: #ibmcloud_catalog}

請使用下列指令管理 {{site.data.keyword.Bluemix}} 型錄項目、查詢範本、運行環境及資料中心的地理位置。
{: shortdesc}

<table summary="您可以用來管理 {{site.data.keyword.Bluemix_notm}} 型錄的 ibmcloud 指令。">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_catalog.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_catalog.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_catalog.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_catalog.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_catalog.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_catalog.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_catalog.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_catalog.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_catalog.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_catalog.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_catalog.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_catalog.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_catalog.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_catalog.html#ibmcloud_catalog_runtimes)</td>
</tr>
 </tbody>
 </table>
  
  ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

搜尋型錄項目

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-r, --region</dt>
  <dd>指定要在其中搜尋的地理區域。目前僅支援 "us-south" 及 "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>依資源類型過濾。目前僅支援 "service-cf"、"iaas"、"runtime"、"template" 及 "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>依價格過濾。目前僅支援 "free"、"paygo"、"ibmcloud-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>依標籤過濾。</dd>
  <dt>--sort-by</dt>
  <dd>內容排序方式</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"</dd>
  <dt>--reverse</dt>
  <dd>是否反轉排序順序</dd>
  <dt>--output TYPE（選用）</dt>
  <dd>--output value  指定輸出 TYPE，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
  <dt>--csv</dt>
  <dd>輸出 CSV 檔案</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

搜尋服務 `Automation test`：

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

取得型錄項目

```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--children</dt>
  <dd>取得型錄項目的所有子項</dd>
  <dt>--output TYPE（選用）</dt>
  <dd>--output value  指定輸出 TYPE，目前只支援 JSON。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

取得 ID 為 `a0ef1-d3b4j0` 的項目：

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
建立新型錄項目（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-p, --parent</dt>
  <dd>物件的母項 ID</dd>
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，建立母項 ID 為 `a0ef1-d3b4j0` 的資源：

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
更新現有型錄項目（僅限帳戶的型錄管理者或編輯者）

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，更新資源 `j402-dnf1i`：

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
刪除型錄項目（僅限帳戶的型錄管理者）
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

刪除資源 `j402-dnf1i`：

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
取得型錄項目的可見性（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-json</dt>
  <dd>輸出原始 JSON 回應</dd>
  <dt>--output TYPE（選用）</dt>
  <dd>--output value  指定輸出 TYPE，目前只支援 JSON。</dd>
  <dt>-global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

取得廣域範圍中資源 `j402-dnf1i` 的可見性：

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
更新現有型錄項目的可見性（僅限帳戶的型錄管理者）

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>

  <dt>--includes-add</dt>
  <dd>將帳戶（或逗點區隔的帳戶清單）新增至 includes 清單，並授與項目的可見性。可接受電子郵件或帳戶 GUID</dd>
  <dt>--includes-remove</dt>
  <dd>從 includes 清單中移除帳戶（或逗點區隔的帳戶清單），並撤銷項目的可見性。可接受電子郵件或帳戶 GUID</dd>  
  <dt>--excludes-add</dt>
  <dd>將帳戶（或逗點區隔的帳戶清單）新增至 excludes 清單。可接受電子郵件或帳戶 GUID</dd>
  <dt>--excludes-remove</dt>
  <dd>從 excludes 清單中移除帳戶（或逗點區隔的帳戶清單），並撤銷項目的可見性。如果帳戶是由廣域管理者所設定，則帳戶管理者無法移除該帳戶。可接受電子郵件或帳戶 GUID</dd>
  <dt>--owner</dt>
  <dd>變更物件的擁有者。可接受電子郵件或帳戶 GUID。</dd>
  <dt>--restrict</dt>
  <dd>將可見性物件的限制變更為「專用」</dd>
  <dt>--unrestrict</dt>
  <dd>將可見性物件的限制變更為「公用」</dd>  
  <dt>-c</dt>
  <dd>包含型錄特定配置參數的有效 JSON 物件（透過行內或檔案所提供）。如需所支援配置參數的清單，請參閱特定型錄項目的文件。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔案，設定資源 `j402-dnf1i` 的可見性：

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
列出 Marketplace 中的服務供應項目

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--cf</dt>
  <dd>僅顯示 Cloud Foundry 服務</dd>
  <dt>--rc</dt>
  <dd>僅顯示 RC 相容服務</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作</dd>
</dl>

<strong>範例</strong>：

顯示廣域範圍中的服務供應項目：

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

檢視 {{site.data.keyword.Bluemix_notm}} 上的樣板範本。

```
ibmcloud catalog templates [-d]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>-d（選用）</dt>
   <dd>如果指定 <i>-d</i> 選項，也會顯示每個範本的說明。否則，只會顯示每一個範本的 ID 及名稱。</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

檢視所指定樣板範本的詳細資訊。

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>TEMPLATE_ID（必要）</dt>
   <dd>樣板範本的 ID。請使用 <i>ibmcloud templates</i> 來檢視所有範本的 ID。</dd>
   </dl>


<strong>範例</strong>：

檢視範本 `mobileBackendStarter` 的詳細資料：

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

以指定的 URL 及說明，建立根據所指定範本的 cf 應用程式。依預設，新的應用程式會自動啟動。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
   <dl>
   <dt>TEMPLATE_ID（必要）</dt>
   <dd>應用程式在建立時將根據的範本。請使用 <i>ibmcloud templates</i> 來查看所有範本 ID。</dd>
   <dt>CF_APP_NAME（必要）</dt>
   <dd>要建立之 cf 應用程式的名稱。</dd>
   <dt>-u <i>URL</i>（選用）</dt>
   <dd>應用程式的路徑。如果未指定，{{site.data.keyword.Bluemix_notm}} 會自動根據應用程式名稱及預設網域來設定路徑。</dd>
   <dt>-d <i>DESCRIPTION</i>（選用）</dt>
   <dd>應用程式的說明。</dd>
   <dt>--no-start（選用）</dt>
   <dd>建立應用程式之後，不要自動將它啟動。如果未指定，應用程式會在建立之後自動啟動。</dd>
   </dl>


<strong>範例</strong>：

根據 `javaHelloWorld` 範本建立 cf 應用程式 `my-app`：

```
ibmcloud catalog template-run javaHelloWorld my-app
```

根據 `rubyHelloWorld` 範本建立應用程式 `my-ruby-app`，路徑為 `myrubyapp.chinabluemix.net`，說明為 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`：

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

根據 `pythonHelloWorld` 範本建立應用程式 `my-python-app`，不自動啟動：

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

以您選擇的格式取得地區的選擇子集。

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>指令選項</strong>：

<dl>
  <dt>-i, --id</dt>
  <dd>依 ID 指定地理位置。</dd>
  <dt>-k, --kind</dt>
  <dd>取得指定類型的項目清單。</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"。</dd>
  <dt>--output TYPE（選用）</dt>
  <dd>--output value  指定輸出 TYPE，目前只支援 JSON。此選項與 '--id' 不能同時使用。</dd>
  <dt>--global</dt>
  <dd>在廣域範圍中操作。</dd>
  <dt>--csv</dt>
  <dd>輸出 CSV 檔案</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

檢視運行環境的詳細資料。這個指令僅適用於公用雲端。

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>範例</strong>：

顯示運行環境 "nodejsHelloWorld" 的詳細資料：

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

列出所有運行環境。這個指令僅適用於公用雲端。

```
ibmcloud catalog runtimes [-d]
```

<strong>指令選項</strong>：

<dl>
  <dt>-d</dt>
  <dd>顯示每個運行環境的說明</dd>
</dl>

<strong>範例</strong>：

列出所有運行環境及其說明：

```
ibmcloud catalog runtimes -d
```
