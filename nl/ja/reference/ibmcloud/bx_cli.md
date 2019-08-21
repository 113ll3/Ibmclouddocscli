---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# 汎用 CLI (ibmcloud) コマンド
{: #ibmcloud_cli}

{{site.data.keyword.cloud_notm}} コマンド・ライン・インターフェース (CLI) では、ユーザーが {{site.data.keyword.cloud_notm}} と対話できるように、名前空間別にグループ化したコマンドのセットが提供されています。
{: shortdesc}

{{site.data.keyword.cloud_notm}} コマンド・ライン・クライアントは、Cloud Foundry コマンド・ライン・クライアントをインストール済み環境にバンドルしています。 独自の Cloud Foundry CLI がインストールされている場合は、{{site.data.keyword.cloud_notm}} CLI コマンド と、独自のインストール済み環境の Cloud Foundry CLI コマンドの両方を同じコンテキストで使用しないでください。 Cloud Foundry CLI を使用して {{site.data.keyword.cloud_notm}} CLI コンテキストで Cloud Foundry リソースを管理したい場合は、代わりに **`ibmcloud cf [command]`** を使用してください。 **`ibmcloud cf api/login/logout/target`** は使用できないので、代わりに、**`ibmcloud api/login/logout/target`** を使用してください。

2018 年 5 月、{{site.data.keyword.cloud_notm}} CLI コマンドは **`bluemix`** および **`bx`** から **`ibmcloud`** に変更されました。ただし、後に削除されるまで、**`bluemix`** および **`bx`** の CLI コマンドを引き続き使用できます。
{: tip}

名前、引数、オプション、前提条件、説明、および例を含め、{{site.data.keyword.cloud_notm}} CLI でサポートされている詳細なコマンドを以下にリストします。

前提条件には、コマンドを使用する前に必要なアクションがリストされています。以下のアクションが 1 つ以上含まれる場合があります。

<dl>
<dt>Docker</dt>
<dd>Docker CLI をインストールします。</dd>
<dt>エンドポイント</dt>
<dd>**`ibmcloud api`** コマンドを使用して、 API エンドポイントを設定します。</dd>
<dt>ログイン</dt>
<dd>**`ibmcloud login`** コマンドを使用して、ログインします。 フェデレーテッド ID でログインする場合は、**`--sso`** オプションを使用してワンタイム・パスコードで認証するか、**`--apikey`** オプションを使用して API キーで認証します。</dd>
<dt>ターゲット</dt>
<dd>**`ibmcloud target`** コマンドを使用して、組織とスペースを設定します。</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

{{site.data.keyword.cloud_notm}} CLI の第 1 レベルの組み込みコマンドおよびサポートされる名前空間に関する一般ヘルプを表示するか、または、特定の組み込みコマンドまたは名前空間に関するヘルプを表示します。

```
ibmcloud help [COMMAND|NAMESPACE]
```

### 前提条件
{: #help-prereqs}

なし。

### コマンド・オプション
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>ヘルプを表示する対象のコマンドまたは名前空間。 指定されない場合、{{site.data.keyword.cloud_notm}} CLI の一般ヘルプが表示されます。 オプション。</dd>
</dl>

### 例
{: #help-examples}

{{site.data.keyword.cloud_notm}} CLI の一般ヘルプを表示します。
```
ibmcloud help
```
{: codeblock}

**`dev`** コマンドのヘルプを次のように表示します。
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

{{site.data.keyword.cloud_notm}} API エンドポイントを設定または表示します。
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### 前提条件
{: #api-prereqs}

なし。

### コマンド・オプション
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>ターゲットの API エンドポイント (例えば `https://cloud.ibm.com`)。 **`API_ENDPOINT`** オプションと **`--unset`** オプションのどちらも指定されない場合、現行 API エンドポイントが表示されます。 オプション。</dd>
<dt>--skip-ssl-validation</dt>
<dd>HTTP 要求の SSL 検証をバイパスします。 オプション。</dd>
<dt>--unset</dt>
<dd>API エンドポイント設定を削除します。</dd>
</dl>

### 例
{: #api-examples}

API エンドポイントを cloud.ibm.com に設定します。
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

現行 API エンドポイントを表示します。
```
ibmcloud api
```
{: codeblock}

API エンドポイントを削除します。
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

構成ファイルにデフォルト値を書き込みます。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### 前提条件
{: #config-prereqs}

なし。

### コマンド・オプション
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>CLI バージョン・チェックを使用可能または使用不可にします。 有効値は `true` または `false` です。</dd>
<dt>--color</dt>
<dd>カラー出力を使用可能または使用不可にします。 このオプションはデフォルトで使用不可になっています。 有効値は `true` または `false` です。</dd>
<dt>--http-timeout</dt>
<dd>HTTP 要求のタイムアウト値 (秒)。 デフォルト値は 60 秒です。</dd>
<dt>--locale</dt>
<dd>デフォルト・ロケールを設定します。 値を指定しない場合は、前のロケールが削除されます。 </dd>
<dt>--trace</dt>
<dd>端末または指定されたファイルへの HTTP 要求をトレースします。 有効値は `true` または `false` です。</dd>
</dl>

一度に 1 つのオプションしか指定できません。
{: tip}

### 例
{: #config-examples}

次のように、HTTP 要求タイムアウトを 30 秒に設定します。
```
ibmcloud config --http-timeout 30
```
{: codeblock}

次のように、HTTP 要求のトレース出力を使用可能にします。
```
ibmcloud config --trace true
```
{: codeblock}

`/home/usera/my_trace` ファイルへの HTTP 要求をトレースします。
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

次のように、カラー出力を使用不可にします。
```
ibmcloud config --color false
```
{: codeblock}

次のように、ロケールを zh_Hans に設定します。
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

次のように、ロケール設定をクリアします。
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

**`ibmcloud info`** コマンドは、CLI バージョン 0.14 から使用できなくなりました。 最新の CLI バージョンをインストールするには、[スタンドアロン {{site.data.keyword.cloud_notm}} CLI のインストール](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)を参照してください。

## ibmcloud cf
{: #ibmcloud_cf}

組み込み Cloud Foundry CLI を呼び出します。
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### 前提条件
{: #info-prereqs}

なし。

### コマンド・オプション
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>呼び出しのメッセージを表示しません。</dd>
</dl>

### 例
{: #info-examples}

Cloud Foundry アプリをリストします。

```
ibmcloud cf apps
```

`Invoking cf command...` メッセージを表示せずに Cloud Foundry サービスをリストします。
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

IBM Cloud CLI 用の Cloud Foundry CLI をインストールします
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### 前提条件
{: #cfinstall-prereqs}

なし。

### コマンド・オプション
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>インストールする Cloud Foundry CLI のバージョンを指定します</dd>
  <dt>--restore</dt>
  <dd>バンドル前のバージョンの Cloud Foundry CLI に復元します</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにインストールを強制します</dd>
</dl>

### 例
{: #cfinstall-examples}

Cloud Foundry CLI `6.44.1` をインストールします。

```
ibmcloud cf install -v 6.44.1
```

確認なしで最新バージョンの Cloud Foundry CLI をインストールします。

```
ibmcloud cf install -f
```

デフォルトのバンドル済み Cloud Foundry CLI にリカバリーします。

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

{{site.data.keyword.cloud_notm}} CLI にログインします。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### 前提条件
{: #login-prereqs}

なし。

### コマンド・オプション
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>API エンドポイント (例えば、`cloud.ibm.com`)。 </dd>
<dt>--apikey API_KEY または @API_KEY_FILE_PATH</dt>
<dd>API キーの内容、または @ 記号で示された API キー・ファイルのパス。</dd>
<dt>-u USER_NAME</dt>
<dd>ユーザー名。 オプション。</dd>
<dt>-p PASS_WORD</dt>
<dd>ユーザー・パスワード。 オプション。</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ターゲット・アカウントの ID。 このオプションは、**`--no account`** オプションと同時に指定することはできません。</dd>
<dt>--no-account</dt>
<dd>アカウントなしでログインを強制します。 このオプションは非推奨です。**`-c`** オプションと同時に指定することはできません。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>ターゲット・リソース・グループの名前。 オプション。</dd>
<dt>-r REGION</dt>
<dd>ターゲット地域の名前。例えば、us-south や eu-gb などです。</dd>
<dt>--no-region</dt>
<dd>地域をターゲットにせずにログインを強制します。</dd>
<dt>-o ORG</dt>
<dd>ターゲット組織の名前。 このオプションは非推奨です。 代わりに **`ibmcloud target -o org_name`** を使用してください。 オプション。</dd>
<dt>-s SPACE</dt>
<dd>ターゲット・スペースの名前。 このオプションは非推奨です。 代わりに **`ibmcloud target -s space_name`** を使用してください。 オプション。</dd>
<dt>--no-iam</dt>
<dd>パブリック IAM の代わりにログイン・サーバーでの認証を強制します。</dd>
<dt>--skip-ssl-validation</dt>
<dd>HTTP 要求の SSL 検証をバイパスします。 このオプションは推奨されません。</dd>
</dl>

### 例
{: #login-examples}

対話式にログインします。

```
ibmcloud login
```
{: codeblock}

以下のように、ユーザー名とパスワードを使用してログインし、ターゲットのアカウント、組織、およびスペースを設定します。
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

ワンタイム・パスコードを使用してログインし、ターゲットのアカウント、組織、スペースを設定します。
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Cloud Found の組織とスペースを設定します。 以下のコマンドを実行して、対話式に組織とスペースを特定できます。

```
ibmcloud target --cf
```
{: codeblock}

あるいは、サービスが所属する組織とスペースが分かる場合は、以下のコマンドを使用できます。

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

アカウントが関連付けられている API キーを使用します。

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

アカウントが関連付けられていない API キーを使用します。

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

API キーにアカウントが関連付けられている場合は、別のアカウントへの切り替えはできません。
{: note}

ワンタイム・パスコードを使用します。

```
ibmcloud login -u UserID --sso
```
{: codeblock}

すると、CLI が URL リンクを提供し、パスコードの入力を要求します。

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

ブラウザーでこのリンクを開いて、パスコードを取得します。 コンソールにパスコードを入力して、ログインします。

## ibmcloud logout
{: #ibmcloud_logout}

CLI からログアウトします。

```
ibmcloud logout
```
{: codeblock}

### 前提条件
{: #logout-prereqs}

なし。

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.cloud_notm}} のすべての地域の情報を表示します。

```
ibmcloud regions
```
{: codeblock}

### 前提条件
{: #regions-prereqs}

**`ibmcloud api`** コマンドを使用して、 API エンドポイントを設定します。

## ibmcloud target
{: #ibmcloud_target}

ターゲット・アカウント、地域、組織、またはスペースを設定するか表示します。

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### 前提条件
{: #target-prereqs}

* **`ibmcloud api`** コマンドを使用して、 API エンドポイントを設定します。
* **`ibmcloud login`** コマンドを使用して、ログインします。 フェデレーテッド ID でログインする場合は、**`--sso`** オプションを使用してワンタイム・パスコードで認証するか、**`--apikey`** オプションを使用して API キーで認証します。

### コマンド・オプション
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>ターゲット・アカウントの ID。 オプション。</dd>
<dt>-r REGION</dt>
<dd>ターゲット地域の名前。例えば、us-south や eu-gb などです。 オプション。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>ターゲット・リソース・グループの名前。 オプション。</dd>
<dt>--cf</dt>
<dd>ターゲットの組織とスペースを対話式に指定します。</dd>
<dt>--cf-api</dt>
<dd>Cloud Foundry API エンドポイント。</dd>
<dt>-o ORG</dt>
<dd>ターゲット組織の名前。 オプション。</dd>
<dt>-s SPACE</dt>
<dd>ターゲット・スペースの名前。 オプション。</dd>
<dt>--unset-region</dt>
<dd>ターゲット領域をクリアします。</dd>
<dt>--unset-resource-group</dt>
<dd>ターゲット・リソース・グループをクリアします。</dd>
<dt>--output FORMAT</dt>
<dd>指定の出力形式。 JSON 形式だけがサポートされています。</dd>
</dl>

どのオプションも指定されていない場合、現行のアカウント、地域、組織、およびスペースが表示されます。
{: note}

### 例
{: #target-examples}

現行のアカウント、組織、およびスペースを設定します。
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

新しい地域に切り替えます。
```
ibmcloud target -r eu-gb
```
{: codeblock}

現行のアカウント、地域、組織、およびスペースを表示します。
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

CLI を最新バージョンに更新します。

```
ibmcloud update [-f]
```
### 前提条件
{: #update-prereqs}

### コマンド・オプション
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>確認を求めずに更新を強制します。 root 権限が必要です。</dd>
</dl>

## 汎用クラシック・インフラストラクチャーのサービス・コマンド
{: #classic-service-commands}

{{site.data.keyword.cloud_notm}} CLI でクラシック・インフラストラクチャー・コマンドを使用して、インフラストラクチャー・サービスを構成したり管理したりします。

使用可能なコマンドのリストを表示するには、**`ibmcloud sl`** コマンドを実行します。
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Classic infrastructure Block Storage
   file            Classic infrastructure File Storage
   dns             Classic infrastructure Domain Name System
   globalip        Classic infrastructure Global IP addresses
   hardware        Classic infrastructure hardware servers
   image           Classic infrastructure Compute images
   ipsec           Classic infrastructure IPSEC VPN
   loadbal         Classic infrastructure Load balancers
   security        Classic infrastructure SSH Keys and SSL Certificates
   securitygroup   Classic infrastructure network security groups
   subnet          Classic infrastructure Network subnets
   ticket          Classic infrastructure Manage Tickets
   vlan            Classic infrastructure Network VLANs
   vs              Classic infrastructure Virtual Servers
   order           Classic infrastructure Orders
   user            Classic infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

コマンドのヘルプ情報を表示するには、以下のコマンドを実行します。
```
ibmcloud sl [command] -h
```

**`ibmcloud sl init`** コマンドは、CLI バージョン `0.14` から使用できなくなりました。 最新の CLI バージョンをインストールするには、[スタンドアロン {{site.data.keyword.cloud_notm}} CLI のインストール](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)を参照してください。
{: note}

## ibmcloud sl help
{: #sl_help}

クラシック・インフラストラクチャー環境で作動するすべてのコマンドのヘルプ情報を表示します。
```
ibmcloud sl help
```
{: codeblock}

