---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# カタログ、プラグイン、および請求処理の設定の管理
{: #ibmcloud_commands_settings}

<table summary="{{site.data.keyword.Bluemix_notm}} カタログ、プラグイン、請求、およびセキュリティー設定を管理するために使用できる ibmcloud コマンド">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} カタログ、プラグイン、請求、およびセキュリティー設定を管理するためのコマンド</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} カタログ、プラグイン、請求、およびセキュリティー設定を管理するためのコマンド</th>
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
  <td>[ibmcloud plugin list](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
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

カタログ項目を検索します

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>検索範囲の地理的地域を指定します。 現在は、「us-south」と「united-kingdom」のみがサポートされています。</dd>
  <dt>-k, --kind</dt>
  <dd>リソースの種類を基準にしてフィルター操作します。 現在は、「service-cf」、「iaas」、「runtime」、「template」、および「dashboard」のみがサポートされています。</dd>
  <dt>-p, --price</dt>
  <dd>価格を基準にしてフィルター操作します。 現在は、「free」、「paygo」、「bluemix-subscription」のみがサポートされています。</dd>
  <dt>-t, --tag</dt>
  <dd>タグを基準にしてフィルター操作します。</dd>
  <dt>--sort-by</dt>
  <dd>ソート基準のプロパティー</dd>
  <dt>--col</dt>
  <dd>表の追加列を指定します。 現在は、「group」、「provider」、および「 tags」です。</dd>
  <dt>--reverse</dt>
  <dd>ソート順序を反転するかどうか</dd>
  <dt>--json</dt>
  <dd>元の JSON 応答を出力します</dd>
  <dt>--csv</dt>
  <dd>CSV ファイルを出力します</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

サービス `Automation test` を検索します

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

カタログ項目を取得します

```
ibmcloud catalog entry ID [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--children</dt>
  <dd>カタログ項目のすべての子を取得します</dd>
  <dt>--json</dt>
  <dd>元の JSON 応答を出力します</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

ID `a0ef1-d3b4j0` の項目を取得します

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
新しいカタログ項目を作成します (アカウントのカタログ管理者のみ)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>オブジェクトの親 ID</dd>
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供される、カタログ固有の構成パラメーターを含む有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

親 ID `a0ef1-d3b4j0` を持つ JSON ファイルからリソースを作成します

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
既存のカタログ項目を更新します (アカウントのカタログ管理者またはエディターのみ)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供される、カタログ固有の構成パラメーターを含む有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

JSON ファイルからリソース `j402-dnf1i` を更新します

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
カタログ項目を削除します (アカウントのカタログ管理者のみ)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

リソース `j402-dnf1i` を削除します

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
カタログ項目の可視性を取得します (アカウントのカタログ管理者のみ)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-json</dt>
  <dd>元の JSON 応答を出力します</dd>
  <dt>-global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

グローバル・スコープでリソース `j402-dnf1i` の可視性を取得します

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
既存のカタログ項目の可視性を更新します (アカウントのカタログ管理者のみ)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>アカウント (またはコンマ区切りの一連のアカウント) を組み込みリストに追加し、項目の可視性を付与します。 E メールまたはアカウント GUID を指定可能です</dd>
  <dt>--includes-remove</dt>
  <dd>アカウント (またはコンマ区切りの一連のアカウント) を組み込みリストから削除し、項目の可視性を取り消します。 E メールまたはアカウント GUID を指定可能です</dd>  
  <dt>--excludes-add</dt>
  <dd>アカウント (またはコンマ区切りの一連のアカウント) を除外リストに追加します。 E メールまたはアカウント GUID を指定可能です</dd>
  <dt>--excludes-remove</dt>
  <dd>アカウント (またはコンマ区切りの一連のアカウント) を除外リストから削除し、項目の可視性を取り消します。 アカウントがグローバル管理者によって設定されていた場合は、アカウント管理者がそのアカウントを削除することはできません。E メールまたはアカウント GUID を指定可能です</dd>
  <dt>--owner</dt>
  <dd>オブジェクトの所有者を変更します。 E メールまたはアカウント GUID を指定可能です。</dd>
  <dt>--restrict</dt>
  <dd>表示可能オブジェクトの制限を「プライベート」に変更します</dd>
  <dt>--unrestrict</dt>
  <dd>表示可能オブジェクトの制限を「パブリック」に変更します</dd>  
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供される、カタログ固有の構成パラメーターを含む有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

JSON ファイルからリソース `j402-dnf1i` の可視性を設定します

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
マーケットプレイス内のサービス・オファリングをリストします

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Cloud Foundry サービスのみを表示します</dd>
  <dt>--rc</dt>
  <dd>RC と互換性のあるサービスのみを表示します</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します</dd>
</dl>

<strong>例</strong>:

グローバル・スコープでのサービス・オファリングを表示します

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

{{site.data.keyword.Bluemix_notm}} のボイラープレート・テンプレートを表示します。

```
ibmcloud catalog templates [-d]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-d (オプション)</dt>
   <dd><i>-d</i> オプションが指定されている場合、各テンプレートの説明
も表示されます。 それ以外の場合、各テンプレートの ID および名前のみが表示されます。</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

指定されたボイラープレート・テンプレートの詳細情報を表示します。

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>TEMPLATE_ID (必須)</dt>
   <dd>ボイラープレート・テンプレートの ID。 すべてのテンプレートの ID を表示するには、
<i>ibmcloud templates</i> を使用します。</dd>
   </dl>


<strong>例</strong>:

テンプレート `mobileBackendStarter` の詳細を表示します。

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

指定されたテンプレートをベースにした、指定された URL と説明を持つ cf アプリケーションを作成します。 デフォルトでは、この新規アプリケーションは自動的に開始されます。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>TEMPLATE_ID (必須)</dt>
   <dd>アプリケーションの作成時にそのアプリケーションの基盤とするテンプレート。 すべてのテンプレートの ID を表示するには、<i>ibmcloud templates</i> を使用します。</dd>
   <dt>CF_APP_NAME (必須)</dt>
   <dd>作成される cf アプリケーションの名前。</dd>
   <dt>-u <i>URL</i> (オプション)</dt>
   <dd>アプリケーションの経路。 指定されない場合、経路は、アプリケーション名およびデフォルト・ドメインに基づいて {{site.data.keyword.Bluemix_notm}} によって自動的に設定されます。</dd>
   <dt>-d <i>DESCRIPTION</i> (オプション)</dt>
   <dd>アプリケーションの説明。</dd>
   <dt>--no-start (オプション)</dt>
   <dd>作成後のアプリケーションを自動的に開始しません。 指定されない場合、アプリケーションは作成された後で自動的に開始されます。</dd>
   </dl>


<strong>例</strong>:

`javaHelloWorld` テンプレートをベースにして cf アプリケーション `my-app` を作成します。

```
ibmcloud catalog template-run javaHelloWorld my-app
```

`rubyHelloWorld` テンプレートに基づき、経路 `myrubyapp.chinabluemix.net` と説明 `My first ruby app on {{site.data.keyword.Bluemix_notm}}.` を使用してアプリケーション `my-ruby-app` を作成するには、以下のように指定します。

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

`pythonHelloWorld` テンプレートをベースにして、自動開始なしでアプリケーション `my-python-app` を作成します。

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

選択されたフォーマットで地域の選択サブセットを取得します。

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>ID でジオグラフィーを指定します。</dd>
  <dt>-k, --kind</dt>
  <dd>指定した種類の項目のリストを取得します。</dd>
  <dt>--col</dt>
  <dd>表の追加列を指定します。 現在は、「group」、「provider」、および「tags」です。</dd>
  <dt>--json</dt>
  <dd>元の JSON 応答の出力。</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します。</dd>
  <dt>--csv</dt>
  <dd>CSV ファイルを出力します</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

ランタイムの詳細を表示します。 このコマンドは、パブリック・クラウドにのみ使用可能です。

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>例</strong>:

ランタイム "nodejsHelloWorld" の詳細を表示します。

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

すべてのランタイムをリストします。 このコマンドは、パブリック・クラウドにのみ使用可能です。

```
ibmcloud catalog runtimes [-d]
```

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-d</dt>
  <dd>各ランタイムの説明を表示します</dd>
</dl>

<strong>例</strong>:

すべてのランタイムを説明と共にリストします。

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

現行アカウントの月々の使用量を表示します (アカウント管理者のみ)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--json (オプション)</dt>
  <dd>使用量の結果を JSON 形式で表示します。</dd>
</dl>

<strong>例</strong>:

2016 年 6 月の現行アカウントの使用量とコストのレポートを表示します。

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

組織の月々の使用量を表示します (アカウント管理者または組織の請求管理者のみ)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>ORG_NAME (必須)</dt>
  <dd>組織の名前。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--json (オプション)</dt>
  <dd>使用量の結果を JSON 形式で表示します。</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

リソース・グループの月々の使用量を表示します (アカウント管理者またはリソース・グループ管理者のみ)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>GROUP_NAME (必須)</dt>
  <dd>リソース・グループの名前。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--json (オプション)</dt>
  <dd>使用量の結果を JSON 形式で表示します。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

現行アカウントの月次リソース・インスタンス使用量を表示します。

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-o ORG_NAME (オプション)</dt>
  <dd>組織を基準にしてインスタンスをフィルターに掛けます。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>リソース・グループを基準にしてインスタンスをフィルターに掛けます。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--json (オプション)</dt>
  <dd>使用量の結果を JSON 形式で表示します。</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.Bluemix_notm}} CLI に登録されているすべてのプラグイン・リポジトリーをリストします。

```
ibmcloud plugin repos
```

<strong>前提条件</strong>: なし

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

新規プラグイン・リポジトリーを {{site.data.keyword.Bluemix_notm}} CLI に追加します。

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>追加するリポジトリーの名前。 各リポジトリーに対して任意の名前を定義できます。</dd>
   <dt>REPO_URL (必須)</dt>
   <dd>追加するリポジトリーの URL。 リポジトリー URL にはプロトコルが含まれている必要があります (例えば、plugins.ng.bluemix.net ではなく、http://plugins.ng.bluemix.net)。 {{site.data.keyword.Bluemix_notm}} CLI の公式プラグイン・リポジトリーは http://plugins.ng.bluemix.net です。</dd>
    </dl>


<strong>例</strong>:

{{site.data.keyword.Bluemix_notm}} CLI の公式プラグイン・リポジトリーを `bluemix-repo` として追加します。

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

{{site.data.keyword.Bluemix_notm}} CLI からプラグイン・リポジトリーを削除します。

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>削除するリポジトリーの名前。</dd>
   </dl>

<strong>例</strong>:

{{site.data.keyword.Bluemix_notm}} CLI から `bluemix-repo` リポジトリーを削除します。

```
ibmcloud plugin repo-remove bluemix-repo
```

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

追加されたすべてのリポジトリーまたは特定のリポジトリー内にある使用可能なプラグインをすべてリストします。

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>指定されたリポジトリー内のプラグインのみをリストします。</dd>
   </dl>

<strong>例</strong>:

追加されたすべてのリポジトリー内のすべてのプラグインをリストします。

```
ibmcloud plugin repo-plugins
```

`bluemix-repo` リポジトリー内のすべてのプラグインをリストします。

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

リポジトリー内のプラグインの詳細を表示します。

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>リポジトリーの名前。 リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリーを使用します</dd>
   </dl>

<strong>例</strong>:

リポジトリー「sample-repo」内のプラグイン「IBM-Containers」の詳細をリストします

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

デフォルト・リポジトリー内のプラグイン「IBM-Containers」の詳細をリストします

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

{{site.data.keyword.Bluemix_notm}} CLI 内のインストールされたプラグインをすべてリストします。

```
ibmcloud plugin list
```

<strong>前提条件</strong>: なし

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

インストールされたプラグインの詳細を表示します。

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>前提条件</strong>: なし

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

指定したパスまたはリポジトリーから、特定のバージョンのプラグインを {{site.data.keyword.Bluemix_notm}} CLI にインストールします。

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。
バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (必須)</dt>
   <dd>「-r <i>REPO_NAME</i>」が指定されない場合、指定されたローカル・パスまたはリモート URL からプラグインがインストールされます。</dd>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。</dd>
   <dt>-v <i>VERSION</i> (オプション)</dt>
   <dd>インストールするプラグインのバージョン。 指定されていない場合は、最新バージョンのプラグインがインストールされます。 このオプションは、リポジトリーからプラグインをインストールする場合にのみ有効です。</dd>
   <dt>-f </dt>
   <dd>確認なしでプラグインのインストールを強制します。</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI の公式リポジトリー名は、`Bluemix` です。

<strong>例</strong>:

ローカル・ファイルからプラグインをインストールします。

```
ibmcloud plugin install /downloads/new_plugin
```

リモート URL からプラグインをインストールします。

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

最新バージョンの「container-service」プラグインを「Bluemix」リポジトリーからインストールするには、以下のように指定します。

```
ibmcloud plugin install container-service -r Bluemix
```

あるいは、簡単に以下のように指定します。

```
ibmcloud plugin install container-service
```

公式プラグイン・リポジトリーから、バージョン「0.1.425」の「container-service」プラグインをインストールするには、以下のように指定します。

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

リポジトリーからプラグインをアップグレードします。

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。
バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>更新するプラグインの名前。 指定されない場合、コマンドは、インストールされているすべてのプラグインのアップグレードを確認します。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。</dd>
 <dt>-v <i>VERSION</i> (オプション)</dt>
 <dd>更新するプラグインのバージョン。 表示されない場合、プラグインを入手可能な最新バージョンに更新してください。</dd>
 <dt>--all</dt>
 <dd>利用可能なすべてのプラグインを更新します</dd>
</dl>

<strong>例</strong>:

公式プラグイン・リポジトリー「Bluemix」内のすべての使用可能アップグレードを確認するには、以下のように指定します。

```
ibmcloud plugin update -r Bluemix
```

あるいは、簡単に以下のように指定します。

```
ibmcloud plugin update
```

公式プラグイン・リポジトリー内のプラグイン「container-service」を最新にアップグレードするには、以下のように指定します。

```
ibmcloud plugin update container-service
```

公式プラグイン・リポジトリー内のプラグイン「container-service」をバージョン「0.1.440」に更新するには、以下のように指定します。

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

指定されたプラグインを {{site.data.keyword.Bluemix_notm}} CLI からアンインストールします。

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>PLUGIN_NAME (必須)</dt>
   <dd>アンインストールされるプラグインの名前。</dd>
    </dl>

<strong>例</strong>:

前にインストールされた「container-service」プラグインをアンインストールします。

```
ibmcloud plugin uninstall container-service
```
