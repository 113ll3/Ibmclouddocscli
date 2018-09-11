---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 型錄、帳單及 CLI 外掛程式
{: #ibmcloud_commands_settings}

請使用下列指令管理 {{site.data.keyword.Bluemix_notm}} 型錄、用量/計費及 CLI 外掛程式。
{: shortdesc}

<table summary="您可以用來管理 {{site.data.keyword.Bluemix_notm}} 型錄、外掛程式、帳單及安全設定的 ibmcloud 指令。">
<thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list
](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update
](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

搜尋型錄項目

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-r, --region</dt>
  <dd>指定要在其中搜尋的地理區域。目前僅支援 "us-south" 及 "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>依資源類型過濾。目前僅支援 "service-cf"、"iaas"、"runtime"、"template" 及 "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>依價格過濾。目前僅支援 "free"、"paygo" 及 "bluemix-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>依標籤過濾。</dd>
  <dt>--sort-by</dt>
  <dd>內容排序方式</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"</dd>
  <dt>--reverse</dt>
  <dd>是否反轉排序順序</dd>
  <dt>--json</dt>
  <dd>輸出原始 JSON 回應</dd>
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
ibmcloud catalog entry ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>--children</dt>
  <dd>取得型錄項目的所有子項</dd>
  <dt>--json</dt>
  <dd>輸出原始 JSON 回應</dd>
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
ibmcloud catalog entry-visibility ID [--global]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>-json</dt>
  <dd>輸出原始 JSON 回應</dd>
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
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>指令選項</strong>：

<dl>
  <dt>-i, --id</dt>
  <dd>依 ID 指定地理位置。</dd>
  <dt>-k, --kind</dt>
  <dd>取得指定類型的項目清單。</dd>
  <dt>--col</dt>
  <dd>指定表格的其他直欄。目前為 "group"、"provider" 及 "tags"。</dd>
  <dt>--json</dt>
  <dd>原始 JSON 回應的輸出。</dd>
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

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

顯示現行帳戶的每月用量（僅限帳戶管理者）

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

顯示現行帳戶在 2016-06 的用量和費用報告：

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

顯示組織的每月用量（僅限帳戶管理者或組織帳單管理員）

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>ORG_NAME（必要）</dt>
  <dd>組織的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

顯示資源群組的每月用量（僅帳戶管理者或資源群組管理者）

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>GROUP_NAME（必要）</dt>
  <dd>資源群組的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

顯示現行帳戶下的每月資源實例用量。

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-o ORG_NAME（選用）</dt>
  <dd>依組織過濾實例。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>依資源群組過濾實例。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示以 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中登錄的所有外掛程式儲存庫。

```
ibmcloud plugin repos
```

<strong>必要條件</strong>：無

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

將新的外掛程式儲存庫新增至 {{site.data.keyword.Bluemix_notm}} CLI。

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>REPO_NAME（必要）</dt>
   <dd>要新增之儲存庫的名稱。您可以自行為每一個儲存庫定義名稱。</dd>
   <dt>REPO_URL（必要）</dt>
   <dd>要新增之儲存庫的 URL。儲存庫 URL 必須包含通訊協定（例如，http://plugins.ng.bluemix.net 而非 plugins.ng.bluemix.net）。http://plugins.ng.bluemix.net 是 {{site.data.keyword.Bluemix_notm}} CLI 的正式外掛程式儲存庫。</dd>
    </dl>


<strong>範例</strong>：

將 {{site.data.keyword.Bluemix_notm}} CLI 的正式外掛程式儲存庫新增為 `bluemix-repo`：

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

從 {{site.data.keyword.Bluemix_notm}} CLI 移除外掛程式儲存庫。

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>REPO_NAME（必要）</dt>
   <dd>要移除之儲存庫的名稱。</dd>
   </dl>

<strong>範例</strong>：

從 {{site.data.keyword.Bluemix_notm}} CLI 移除 `bluemix-repo` 儲存庫：

```
ibmcloud plugin repo-remove bluemix-repo
```

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

列出所有已新增之儲存庫或特定儲存庫中的所有可用外掛程式。

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>只列出指定儲存庫中的外掛程式。</dd>
   </dl>

<strong>範例</strong>：

列出所有已新增之儲存庫中的所有外掛程式：

```
ibmcloud plugin repo-plugins
```

列出 `bluemix-repo` 儲存庫中的所有外掛程式：

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

顯示儲存庫中外掛程式的詳細資料。

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>儲存庫的名稱。如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫。</dd>
   </dl>

<strong>範例</strong>：

列出儲存庫 "sample-repo" 中外掛程式 "IBM-Containers" 的詳細資料：

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

列出預設儲存庫中外掛程式 "IBM-Containers" 的詳細資料

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

列出 {{site.data.keyword.Bluemix_notm}} CLI 中的所有已安裝外掛程式。

```
ibmcloud plugin list
```

<strong>必要條件</strong>：無

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

顯示已安裝外掛程式的詳細資料。

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>必要條件</strong>：無

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

從指定的路徑或儲存庫，將特定版本的外掛程式安裝到 {{site.data.keyword.Bluemix_notm}} CLI 中。

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。如果未指定版本，則指令會選取最新可用的版本來進行安裝。

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME（必要）</dt>
   <dd>如果未指定 -r <i>REPO_NAME</i>，則會從指定的本端路徑或遠端 URL 來安裝外掛程式。</dd>
   <dt>-r <i>REPO_NAME</i>（選用）</dt>
   <dd>外掛程式二進位檔所在儲存庫的名稱。如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。
</dd>
   <dt>-v <i>VERSION</i>（選用）</dt>
   <dd>要安裝之外掛程式的版本。如果未提供，將安裝最新版本的外掛程式。只有從儲存庫安裝外掛程式時，此選項才有效。</dd>
   <dt>-f</dt>
   <dd>強制安裝外掛程式，而不進行確認。</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI 具有的正式儲存庫名稱為 `Bluemix`。

<strong>範例</strong>：

從本端檔案安裝外掛程式：

```
ibmcloud plugin install /downloads/new_plugin
```

從遠端 URL 安裝外掛程式：

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

從 'Bluemix' 儲存庫安裝最新版本的 'container-service' 外掛程式：

```
ibmcloud plugin install container-service -r Bluemix
```

還是只用：

```
ibmcloud plugin install container-service
```

從正式外掛程式儲存庫中安裝 '0.1.425' 版的 'container-service' 外掛程式：

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

從儲存庫升級外掛程式。

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

如果未指定儲存庫，則指令會使用預設的外掛程式儲存庫 'Bluemix'。如果未指定版本，則指令會選取最新可用的版本來進行安裝。

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>要更新之外掛程式的名稱。如果未指定，則這個指令會檢查所有已安裝外掛程式的升級。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>外掛程式二進位檔所在儲存庫的名稱。如果未指定，則指令會使用預設的外掛程式儲存庫 'Bluemix'。</dd>
 <dt>-v <i>VERSION</i>（選用）</dt>
 <dd>外掛程式要更新到的目標版本。如果未提供，便將外掛程式更新至最新的可用版本。</dd>
 <dt>--all</dt>
 <dd>更新所有可用的外掛程式</dd>
</dl>

<strong>範例</strong>：

檢查正式外掛程式儲存庫 'Bluemix' 中的所有可用升級：

```
ibmcloud plugin update -r Bluemix
```

還是只用：

```
ibmcloud plugin update
```

將正式外掛程式儲存庫中的外掛程式 'container-service' 升級至最新：

```
ibmcloud plugin update container-service
```

將正式外掛程式儲存庫中的外掛程式 'container-service' 更新至 '0.1.440' 版：

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

從 {{site.data.keyword.Bluemix_notm}} CLI 解除安裝指定的外掛程式。

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>PLUGIN_NAME（必要）</dt>
   <dd>要解除安裝之外掛程式的名稱。</dd>
    </dl>

<strong>範例</strong>：

解除安裝先前安裝的 'container-service' 外掛程式：

```
ibmcloud plugin uninstall container-service
```
