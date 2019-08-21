---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-19"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# カタログ・オファリングの検索と管理
{: #ibmcloud_catalog}

以下のコマンドを使用して、データ・センターの {{site.data.keyword.cloud}} カタログ・エントリー、照会テンプレート、ランタイム、および地理位置情報を管理します。
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

カタログ・エントリーを検索します。
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>検索範囲の地理的地域を指定します。 現在は、「us-south」と「united-kingdom」のみがサポートされています。</dd>
  <dt>-k, --kind</dt>
  <dd>リソースの種類を基準にしてフィルター操作します。 現在は、「service-cf」、「iaas」、「runtime」、「template」、および「dashboard」のみがサポートされています。</dd>
  <dt>-p, --price</dt>
  <dd>価格を基準にしてフィルター操作します。 現在は、「free」、「paygo」、「ibmcloud-subscription」のみがサポートされています。</dd>
  <dt>-t, --tag</dt>
  <dd>タグを基準にしてフィルター操作します。</dd>
  <dt>--sort-by</dt>
  <dd>ソート基準のプロパティー</dd>
  <dt>--col</dt>
  <dd>表の追加列を指定します。 現在は、「group」、「provider」、および「 tags」です。</dd>
  <dt>--reverse</dt>
  <dd>ソート順序を反転するかどうか</dd>
  <dt>--output TYPE (オプション)</dt>
  <dd>--output value  出力タイプを指定します。現在は JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
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

カタログ・エントリーを取得します
```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--children</dt>
  <dd>カタログ項目のすべての子を取得します</dd>
  <dt>--output TYPE (オプション)</dt>
  <dd>--output value  出力タイプを指定します。現在は JSON のみがサポートされています。</dd>
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

カタログ・エントリーを作成します (アカウントのカタログ管理者のみ)。
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>オブジェクトの親 ID</dd>
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供されるカタログ固有の構成パラメーターを含む、有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
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

既存のカタログ・エントリーを更新します (アカウントのカタログ管理者またはエディターのみ)。
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供されるカタログ固有の構成パラメーターを含む有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
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
ibmcloud catalog delete `j402-dnf1i`
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

カタログ項目の可視性を取得します (アカウントのカタログ管理者のみ)
```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-json</dt>
  <dd>元の JSON 応答を出力します</dd>
  <dt>--output TYPE (オプション)</dt>
  <dd>--output value  出力タイプを指定します。現在は JSON のみがサポートされています。</dd>
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

既存のカタログ・エントリーの可視性を更新します (アカウントのカタログ管理者のみ)。
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>組み込みリストにアカウント (またはアカウントのコンマ区切りリスト) を追加して、エントリーに可視性を付与しています。 E メールまたはアカウント GUID を指定可能です。</dd>
  <dt>--includes-remove</dt>
  <dd>組み込みリストからアカウント (またはアカウントのコンマ区切りリスト) を削除して、エントリーへの可視性を取り消しています。 E メールまたはアカウント GUID を指定可能です。</dd>  
  <dt>--excludes-add</dt>
  <dd>除外リストにアカウント (またはアカウントのコンマ区切りリスト) を追加しています。 E メールまたはアカウント GUID を指定可能です。</dd>
  <dt>--excludes-remove</dt>
  <dd>除外リストからアカウント (またはアカウントのコンマ区切りリスト) を削除して、エントリーへの可視性を取り消しています。 アカウントがグローバル管理者によって設定されていた場合は、アカウント管理者がそのアカウントを削除することはできません。 E メールまたはアカウント GUID を指定可能です。</dd>
  <dt>--owner</dt>
  <dd>オブジェクトの所有者を変更します。 E メールまたはアカウント GUID を指定可能です。</dd>
  <dt>--restrict</dt>
  <dd>可視性オブジェクトの制限を「プライベート」に変更しています。</dd>
  <dt>--unrestrict</dt>
  <dd>可視性オブジェクトの制限を「パブリック」に変更しています。</dd>  
  <dt>-c</dt>
  <dd>インラインまたはファイルのいずれかで提供されるカタログ固有の構成パラメーターを含む有効な JSON オブジェクト。 サポートされている構成パラメーターのリストについては、特定のカタログ項目用の資料を参照してください。</dd>
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

このマーケットプレイス内のサービス・オファリングをリストします。
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
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

{{site.data.keyword.cloud_notm}} のボイラープレート・テンプレートを表示します。
```
ibmcloud catalog templates [-d] [--output json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-d (オプション)</dt>
   <dd><i>-d</i> オプションが指定されている場合、各テンプレートの説明
も表示されます。 それ以外の場合、各テンプレートの ID および名前のみが表示されます。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

指定されたボイラープレート・テンプレートの詳細情報を表示します。
```
ibmcloud catalog template TEMPLATE_ID [--output json]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>TEMPLATE_ID (必須)</dt>
   <dd>ボイラープレート・テンプレートの ID。 すべてのテンプレートの ID を表示するには、
<i>ibmcloud templates</i> を使用します。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
   </dl>


<strong>例</strong>:

テンプレート `mobileBackendStarter` の詳細を表示します。
```
ibmcloud catalog template mobileBackendStarter
```
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

指定されたテンプレートをベースにした、指定された URL と説明を持つ cf アプリケーションを作成します。 デフォルトでは、この新規アプリケーションは自動的に開始されます。

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>TEMPLATE_ID (必須)</dt>
   <dd>作成時にアプリケーションの基となるテンプレート。 すべてのテンプレートの ID を表示するには、<i>ibmcloud templates</i> を使用します。</dd>
   <dt>CF_APP_NAME (必須)</dt>
   <dd>作成される cf アプリケーションの名前。</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>CF アプリケーションのホスト名。 指定されない場合、経路は、アプリケーション名およびデフォルト・ドメインに基づいて {{site.data.keyword.cloud_notm}} によって自動的に設定されます。</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>CF アプリケーションのドメイン。 指定されない場合、経路は、アプリケーション名およびデフォルト・ドメインに基づいて {{site.data.keyword.cloud_notm}} によって自動的に設定されます。</dd>
   <dt>--desc <i>DESCRIPTION</i> (オプション)</dt>
   <dd>アプリケーションの説明。</dd>
   <dt>--no-start (オプション)</dt>
   <dd>アプリケーションが作成された後、アプリケーションを自動的に開始しません。 指定されない場合、アプリケーションは作成された後で自動的に開始されます。</dd>
   </dl>


<strong>例</strong>:

`javaHelloWorld` テンプレートに基づいて、`my-app` という名前の `cf` アプリを作成します。
```
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

`rubyHelloWorld` テンプレートに基づいて、説明付きのアプリ `my-ruby-app` を作成します。
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

`pythonHelloWorld` テンプレートをベースにして、自動開始なしでアプリ `my-python-app` を作成します。
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

選択されたフォーマットで地域の選択サブセットを取得します。
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>ID でジオグラフィーを指定します。</dd>
  <dt>-k, --kind</dt>
  <dd>指定した種類の項目のリストを取得します。</dd>
  <dt>--col</dt>
  <dd>表の追加列を指定します。 現在は、「group」、「provider」、および「tags」です。</dd>
  <dt>--output TYPE (オプション)</dt>
  <dd>--output value  出力タイプを指定します。現在は JSON のみがサポートされています。 このオプションは、「--id」と同時に指定することはできません。</dd>
  <dt>--global</dt>
  <dd>グローバル・スコープで操作します。</dd>
  <dt>--csv</dt>
  <dd>CSV ファイルを出力します</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

ランタイムの詳細を表示します。 このコマンドは、パブリック・クラウドにのみ使用可能です。
```
ibmcloud catalog runtime RUNTIME_ID [--output json]
```

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

ランタイム "nodejsHelloWorld" の詳細を表示します。
```
catalog runtime nodejsHelloWorld
```
{: codeblock}

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

すべてのランタイムをリストします。 このコマンドは、パブリック・クラウドにのみ使用可能です。
```
ibmcloud catalog runtimes [-d] [--output json]
```

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-d</dt>
  <dd>各ランタイムの説明を表示します</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

すべてのランタイムを説明と共にリストします。
```
ibmcloud catalog runtimes -d
```
{: codeblock}
