---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 外掛程式
{: #ibmcloud_commands_settings}

使用下列指令來管理 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式。
{: shortdesc}

<table summary="您可以用來管理 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式的 ibmcloud 指令。">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud plugin repo-add](cli_plugin.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_plugin.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_plugin.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_plugin.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_plugin.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_plugin.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_plugin.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_plugin.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_plugin.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud plugin repos](cli_plugin.html#ibmcloud_plugin_repos)</td>
</tr>
 </tbody>
 </table>


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
