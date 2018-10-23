---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# カタログ
{: #ibmcloud_catalog}

以下のコマンドを使用して、データ・センターの {{site.data.keyword.Bluemix}} カタログ・エントリー、照会テンプレート、ランタイム、および地理位置情報を管理します。
{: shortdesc}

<table summary="{{site.data.keyword.Bluemix_notm}} カタログを管理するために使用できる ibmcloud コマンド。">
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
