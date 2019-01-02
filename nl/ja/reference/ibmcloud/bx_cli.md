---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 汎用 CLI (ibmcloud) コマンド
{: #ibmcloud_cli}


{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) では、ユーザーが {{site.data.keyword.Bluemix_notm}} と対話できるように、名前空間別にグループ化したコマンドのセットが提供されています。

{{site.data.keyword.Bluemix_notm}} コマンド・ライン・クライアントは、Cloud Foundry コマンド・ライン・クライアントをインストール済み環境にバンドルしています。 独自の cf cli がインストールされている場合は、{{site.data.keyword.Bluemix_notm}} CLI コマンド `ibmcloud [command]` と、独自のインストール済み環境の Cloud Foundry CLI コマンド `cf [command]` の両方を同じコンテキストで使用しないでください。 cf cli を使用して {{site.data.keyword.Bluemix_notm}} CLI コンテキストで Cloud Foundry リソースを管理したい場合は、代わりに `ibmcloud cf [command]` を使用してください。  `ibmcloud cf api/login/logout/target` は使用できないので注意してください。代わりに、`ibmcloud api/login/logout/target` を使用してください。

2018 年 5 月、{{site.data.keyword.Bluemix_notm}} CLI コマンドは `bluemix` および `bx` から `ibmcloud` に変更されました。 ただし、後日削除されるまで、`bluemix` および `bx` CLI CLI コマンドを引き続き使用できます。
{: tip}

名前、引数、オプション、前提条件、説明、および例を含め、{{site.data.keyword.Bluemix_notm}} CLI でサポートされている詳細なコマンドを以下にリストします。
{:shortdesc}

*前提条件*には、コマンドを使用する前に必要なアクションがリストされています。 前提条件となるアクションのないコマンドでは、**なし**とリストされています。 それ以外の場合、前提条件には以下のアクションのうちの 1 つ以上が含まれます。

<dl>
<dt>エンドポイント</dt>
<dd>このコマンドを使用する前に、<code>ibmcloud api</code> を介して API エンドポイントを設定する必要があります。</dd>
<dt>ログイン</dt>
<dd>このコマンドを使用する前に、<code>ibmcloud login</code> コマンドを使用してログインする必要があります。
フェデレーテッド ID でログインする場合は、「--sso」オプションを使用してワンタイム・パスコードで認証するか、「--apikey」を使用して API キーで認証します。
</dd>
<dt>ターゲット</dt>
<dd>このコマンドを使用する前に、<code>ibmcloud target</code> コマンドを使用して組織およびスペースを設定する必要があります。</dd>
<dt>Docker</dt>
<dd>このコマンドを実行するためには、Docker CLI (docker) がインストールされている必要があります。</dd>
</dl>


以下の表の索引を使用して、使用頻度の高い ibmcloud コマンドを参照してください。

## 汎用 ibmcloud コマンド
{: #ibmcloud_commands_index}

<table summary="汎用 ibmcloud コマンド。">
<caption>表 1. 汎用 ibmcloud コマンド</caption>
 <thead>
 <th colspan="5">汎用 ibmcloud コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](bx_cli.html#ibmcloud_help)</td>
 <td>[ibmcloud api](bx_cli.html#ibmcloud_api)</td>
 <td>[ibmcloud config](bx_cli.html#ibmcloud_config)</td>
 <td>[ibmcloud info
](bx_cli.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](bx_cli.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](bx_cli.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](bx_cli.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](bx_cli.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](bx_cli.html#ibmcloud_target)</td>
 <td>[ibmcloud update](bx_cli.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud help
{: #ibmcloud_help}
{{site.data.keyword.Bluemix_notm}} CLI の第 1 レベルの組み込みコマンドおよびサポートされる名前空間に関する一般ヘルプを表示するか、または、特定の組み込みコマンドまたは名前空間に関するヘルプを表示します。

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (オプション)</dt>
   <dd>ヘルプを表示する対象のコマンドまたは名前空間。 指定されない場合、{{site.data.keyword.Bluemix_notm}} CLI の一般ヘルプが表示されます。</dd>
   </dl>



<strong>例</strong>:

{{site.data.keyword.Bluemix_notm}} CLI の一般ヘルプを表示します。

```
ibmcloud help
```

`info` コマンドのヘルプを表示します。

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
{{site.data.keyword.Bluemix_notm}} API エンドポイントを設定または表示します。

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>API_ENDPOINT (オプション)</dt>
   <dd>ターゲットの API エンドポイント (例えば `https://api.chinabluemix.net`)。 *API_ENDPOINT* オプションと `--unset` オプションのどちらも指定されない場合、現行 API エンドポイントが表示されます。</dd>
   <dt>--unset (オプション)</dt>
   <dd>API エンドポイント設定を削除します。</dd>
   <dt>--skip-ssl-validation (オプション)</dt>
   <dd>HTTP 要求の SSL 検証をバイパスします。</dd>
   </dl>
<strong>例</strong>:

API エンドポイントを api.chinabluemix.net に設定します。

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

現行 API エンドポイントを表示します。

```
ibmcloud api
```

API エンドポイントを設定解除します。

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


構成ファイルにデフォルト値を書き込みます。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>HTTP 要求のタイムアウト値。 デフォルト値は 60 秒です。</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>端末または指定されたファイルへの HTTP 要求をトレースします。</dd>
   <dt>--color true|false</dt>
   <dd>カラー出力を使用可能または使用不可にします。 カラー出力はデフォルトで使用可能に設定されています。</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>デフォルト・ロケールを設定します。 LOCALE  が <i>CLEAR</i> の場合は、前のロケールが削除されます。</dd>
   <dt>--check-version true|false</dt>
   <dd>CLI バージョン・チェックを使用可能または使用不可にします。</dd>
   </dl>

一度に指定できるのは、これらのオプションの 1 つだけです。

<strong>例</strong>:

次のように、HTTP 要求タイムアウトを 30 秒に設定します。

```
ibmcloud config --http-timeout 30
```

次のように、HTTP 要求のトレース出力を使用可能にします。

```
ibmcloud config --trace true
```

次のように、指定されたファイル */home/usera/my_trace* への HTTP 要求をトレースします。

```
ibmcloud config --trace /home/usera/my_trace
```

次のように、カラー出力を使用不可にします。

```
ibmcloud config --color false
```

次のように、ロケールを zh_Hans に設定します。

```
ibmcloud config --locale zh_Hans
```

次のように、ロケール設定をクリアします。

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

基本的な {{site.data.keyword.Bluemix_notm}} 情報を表示します。これには、現行領域、クラウド・コントローラーのバージョン、および、いくつかの有用なエンドポイント (例えば、ログイン用のエンドポイントや、アクセス・トークン交換用のエンドポイントなど) が含まれます。

```
ibmcloud info
```

<strong>前提条件</strong>: エンドポイント

## ibmcloud cf
{: #ibmcloud_cf}

組み込み CF CLI を呼び出します

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>「cf コマンドの呼び出し中...」というメッセージをオフにします</dd>
</dl>

<strong>例</strong>:

cf アプリをリストします

```
ibmcloud cf apps
```

「cf コマンドの呼び出し中...」というメッセージを表示せずに cf サービスをリストします

```
ibmcloud -q cf services
```

## ibmcloud login
{: #ibmcloud_login}

ユーザーをログインします。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>前提条件</strong>: なし

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>コマンド・オプション</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (オプション)</dt>
  <dd> API エンドポイント (例: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY または @API_KEY_FILE_PATH</i>
  <dd> API キーの内容、または @ で示された API キー・ファイルのパス</dd>
  <dt> --sso (オプション) </dt>
  <dd> ワンタイム・パスコードを使用してログインします </dd>
  <dt> -u <i>USERNAME</i> (オプション)</dt>
  <dd> ユーザー名</dd>
  <dt> -p <i>PASSWORD</i> (オプション)</dt>
  <dd> パスワード</dd>
  <dt> -c <i>ACCOUNT_ID</i> (オプション) </dt>
  <dd> ターゲット・アカウントの ID。 このオプションは、「--no-account」と同時に指定することはできません。</dd>
  <dt> --no-account (オプション) </dt>
  <dd> アカウント無しでログインを強制します。 このオプションは推奨されません。 このオプションは、「-c」と同時に指定することはできません。</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (オプション) </dt>
  <dd> ターゲット・リソース・グループの名前</dd>
  <dt> -o <i>ORG</i> (オプション)</dt>
  <dd> ターゲット組織の名前 (非推奨。'ibmcloud target -o ORG' を使用のこと)</dd>
  <dt> -s <i>SPACE</i> (オプション) </dt>
  <dd> ターゲット・スペースの名前 (非推奨。'ibmcloud target -s SPACE' を使用のこと)</dd>
  <dt> --no-iam </dt>
  <dd> パブリック IAM の代わりにログイン・サーバーでの認証を強制します</dd>
  <dt> --skip-ssl-validation (オプション) </dt>
  <dd> HTTP 要求の SSL 検証をバイパスします。 このオプションは推奨されません。</dd>
</dl>

<strong>例</strong>:

### 対話式ログイン

```
ibmcloud login
```

以下のように、ユーザー名とパスワードを使用してログインし、ターゲットのアカウント、組織、およびスペースを設定します。

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

ワンタイム・パスコードを使用してログインし、ターゲット・アカウント、組織、およびスペースを設定します

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

API キーを使用してログインし、ターゲットを設定します。

### API キーにアカウントが関連付けられている

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### API キーにアカウントが関連付けられていない

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>注:</strong> API キーに、関連付けられたアカウントがある場合、別のアカウントへの切り替えは許可されません。

### ワンタイム・パスコードを使用する

```
ibmcloud login -u UserID --sso
```

すると、CLI は以下のように URL リンクを提供し、パスコードの入力を要求します。
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

ブラウザーでこのリンクを開くと、パスコードを取得するための案内が表示されます。 提供されたパスコードをコンソールに入力するとログインできます。

## ibmcloud logout
{: #ibmcloud_logout}

ユーザーをログアウトします。

```
ibmcloud logout
```

<strong>前提条件</strong>: なし

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.Bluemix_notm}} のすべての地域の情報を表示します。

```
ibmcloud regions
```

<strong>前提条件</strong>: エンドポイント

## ibmcloud target
{: #ibmcloud_target}


ターゲット・アカウント、地域、組織、またはスペースを設定するか表示します。

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (オプション)</dt>
   <dd>切り替え先の地域の名前。例えば、「us-south」または「eu-gb」など。</dd>
   <dt>-c <i>ACCOUNT_ID</i> (オプション)</dt>
   <dd>ターゲットとなるアカウントの ID。</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (オプション)</dt>
   <dd>リソース・グループの名前。</dd>
   <dt>--cf</dt>
   <dd>ターゲットの組織およびスペースを対話式に選択します</dd>
   <dt>-o <i>ORG_NAME</i> (オプション)</dt>
   <dd>ターゲットとなる組織の名前。</dd>
   <dt>-s <i>SPACE_NAME</i> (オプション)</dt>
   <dd>ターゲットとなるスペースの名前。</dd>
   </dl>
どのオプションも指定されていない場合、現行のアカウント、地域、組織、およびスペースが表示されます。

<strong>例</strong>:

現行のアカウント、組織、およびスペースを設定します。

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

新しい地域に切り替えます。

```
ibmcloud target -r eu-gb
```

現行のアカウント、地域、組織、およびスペースを表示します。

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

CLI を最新バージョンに更新します。

```
ibmcloud update [-f]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f</dt>
  <dd>確認を求めずに更新を強制します。 root 権限が必要です。</dd>
</dl>


## 汎用クラシック・インフラストラクチャーのサービス・コマンド
{: #softlayer_cli}


{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) でクラシック・インフラストラクチャー・コマンドを使用して、インフラストラクチャー・サービスを構成および管理します。


以下のコマンドがサポートされます。 使用可能なコマンドのリストを表示するには、`ibmcloud sl` コマンドを使用します。

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用コマンド">
<caption>表 1. 汎用クラシック・インフラストラクチャー・コマンド</caption>
 <thead>
 <th colspan="6">汎用クラシック・インフラストラクチャー・コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/ibmcloud/bx_cli.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/ibmcloud/bx_cli.html#sl_help)</td>
   </tbody>
 </table>

 コマンドのヘルプ情報を表示するには、`ibmcloud sl [command] -h` を実行します。

 ## ibmcloud sl init
{: #sl_init}

クラシック・インフラストラクチャー環境への接続に使用される構成設定を初期化します。 この構成には、ユーザー名、API キーまたはパスワード、アカウント、およびエンドポイントが含まれます。
```
ibmcloud sl init [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>クラシック・インフラストラクチャーの API エンドポイント URL。デフォルトは、API キー認証の場合は https://api.softlayer.com/rest/v3.1、IBMid 認証の場合は https://api.softlayer.com/mobile/v3.1。</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1 インフラストラクチャー・ユーザー名。</dd>
<dt>-p, --sl-password</dt>
<dd>パスワードまたは API キー。</dd>
<dt>-c, --account-id</dt>
<dd>アカウント ID。</dd>
<dt>-q, --security-question-id</dt>
<dd>認証に使用されるセキュリティー質問 ID。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-w, --security-question-answer</dt>
<dd>認証に使用されるセキュリティー質問の回答。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-s, --security-code</dt>
<dd>二要素認証が有効になっている場合にセキュリティー・ベンダーによって生成されるセキュリティー・コード。</dd>
<dt>-v, --security-vendor</dt>
<dd>認証用のセキュリティー・コードを提供するセキュリティー・ベンダー。オプション: VERISIGN、TOTP、PHONE_FACTOR。</dd>
<dt>-t, --auth-token</dt>
<dd>電話認証が有効な場合の認証トークン。</dd>
</dl>

例えば、クラシック・インフラストラクチャーのユーザー名とパスワード/API キーを使用してログインします
```
$ ibmcloud sl init
Choose how to configure classic infrastructure authentication:
1. Login with your classic infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
classic infrastructure API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> user@example.com
API key or password: []> abcd

API endpoint:    https://api.softlayer.com/rest/v3.1   
User name:       user@example.com   
API Key:         xxxxxxxxxx
```
例えば、{{site.data.keyword.Bluemix_notm}} の Single-Sign-On を使用してクラシック・インフラストラクチャーにログインします
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           user@example.com   
Account:        example user's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Choose how to configure classic infrastructure authentication:

1. Login with your classic infrastructure user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
classic infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

classic infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1   

Account ID:                123456   
User ID:                   user@example.com  
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

クラシック・インフラストラクチャー環境で作動するすべてのコマンドのヘルプ情報を表示します。
```
ibmcloud sl help
```
