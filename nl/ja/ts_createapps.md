---

copyright:
  years: 2015, 2018
lastupdated: "2018-04-26"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# {{site.data.keyword.Bluemix_notm}} 開発者ツールに関するトラブルシューティング
{: #troubleshoot}

{{site.data.keyword.dev_cli_short}} CLI を使用してアプリを作成する際の一般的な問題には、デプロイメントの失敗や、アプリを作成する際にコードを取得できないなどが含まれます。 多くの場合、いくつかの簡単なステップを実行することで、これらの問題から復旧することが可能です。
{:shortdesc}

## 非モバイル・パターンのアプリを作成するとホスト名エラーになる
{: #hostname-error}

{{site.data.keyword.dev_cli_short}} CLI を使用して Cloud Foundry にアプリをデプロイすると、以下のエラーが表示される場合があります。 固有であると思っているホスト名を入力してもこのメッセージが表示されることがあります。

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。
{: tsCauses}

再ログインしてください。

```
bx login
```
{: codeblock}
{: tsResolve}

## {{site.data.keyword.dev_cli_short}} CLI の一般障害
{: #general}

{{site.data.keyword.dev_cli_short}} CLI の `create`、`delete`、 `list`、または `code` のコマンドを使用すると、以下のエラーが表示される場合があります。

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。
{: tsCauses}

再ログインしてください。

```
bx login
```
{: codeblock}
{: tsResolve}

## エラー: 新規アプリを実行すると、「No such image」と表示される
{: #nosuchimage}

ビルドをせずにアプリを実行すると、以下のエラーが表示される場合があります。

```
$ bx dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```
{: tsSymptoms}

アプリは、実行する前にビルドする必要があります。
{: tsCauses}

現行アプリ・ディレクトリー内で以下のコマンドを実行して、アプリをビルドします。

```
bx dev build
```
{: codeblock}

現行アプリ・ディレクトリー内で以下のコマンドを実行して、アプリを開始します。

```
bx dev run
```
{: tsResolve}

## {{site.data.keyword.objectstorageshort}} 機能を追加すると、サービス・ブローカー・エラーが発生する
{: #os}

{{site.data.keyword.dev_cli_short}} CLI を使用して、{{site.data.keyword.objectstorageshort}} 機能を持つ 2 つのアプリを作成すると、以下のエラーが表示される場合があります。

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、{{site.data.keyword.objectstorageshort}} サービスが、フリー {{site.data.keyword.objectstorageshort}} プランの 1 つのインスタンスのみ提供していることです。
{: tsCauses}

このエラーを回避するために、別のプランを選択するようプロンプトが出されます。
{: tsResolve}

## アプリの作成時にコードの取得に失敗する
{: #code}

{{site.data.keyword.dev_cli_short}} CLI を使用してアプリを作成すると、以下のエラーが表示される場合があります。

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、内部タイムアウトです。
{: tsCauses}

以下のいずれかの方法でコードを取得できます。

* CLI を使用して以下のコマンドを実行します。

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   `<your-app-name>` を、アプリ作成時に指定したアプリ名で置き換えます。

* {{site.data.keyword.dev_console}}を使用します。

	1. {{site.data.keyword.dev_console}}で、[アプリ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.bluemix.net/developer/appservice/apps)を選択します。

	2. **「コードのダウンロード」**をクリックします。

{: tsResolve}

## Node.js アプリで `bx dev run` を実行するとエラーになる
{: #node}

Node.js Web プロジェクトまたは BFF アプリ用の {{site.data.keyword.dev_cli_short}} CLI で `bx dev run` を実行すると、以下のエラーが表示される場合があります。

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}
{: tsSymptoms}

このエラーは、`appmetrics` モジュールが別のアーキテクチャーにインストールされている場合に発生します。 1 つのアーキテクチャーにインストールされているネイティブ NPM モジュールは、別のアーキテクチャーでは機能しません。 付属の Docker イメージは、Linux カーネルに基づいています。
{: tsCauses}

`node_modules` フォルダーを削除してから、`bx dev run` コマンドを再度実行します。
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}} へのデプロイに失敗する

{{site.data.keyword.dev_cli_short}} CLI を使用して {{site.data.keyword.Bluemix_notm}} へデプロイしようとすると、失敗しますが、エラーは表示されません。
{: tsSymptoms}

アカウントにログインしていない可能性があります。
{: tsCauses}

ログインして、やり直してください。

```
bx login
```
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}} 上の Kubernetes へのデプロイに失敗する

クラスター名のプロンプトが出された後、以下の失敗が表示される場合があります。

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

これは、ほとんどの場合、無効のクラスター名が原因です。 同じコマンドに `--trace` を付けて実行することによって、原因を確認することができます。エラー出力には、以下の詳細が含まれる場合があります。

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

正しいクラスターを使用していて、かつクラスターがデプロイメント用に構成済みであることを確認するために、以下を実行します。

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## イメージ・ターゲットのデプロイに失敗する

デプロイ用イメージ・ターゲットのプロンプトが出された後、以下の失敗が表示される場合があります。

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

これは、ほとんどの場合、無効のデプロイ用イメージ・ターゲットが原因です。 具体的には、デプロイ用イメージ・ターゲットの中間値である名前空間が無効である可能性があります。

デプロイ用イメージ・ターゲット内の名前空間が、以下を実行して表示される名前空間のいずれかと一致していることを確認します。

```
bx cr namespaces
```
{: tsResolve}

## ツールの再インストール
{: #appendix}

ほとんどのユーザー向けにすべての前提条件がプラットフォーム・インストーラーを使用してインストールされます。 いずれかのコンポーネントを手動でインストールする必要がある場合の手順を以下に示します。

開発プラグインをインストールするには、最初に [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started) をインストールする必要があります。

開発プラグイン自体を使用するには、`bx plugin install dev -r Bluemix` コマンドを実行してそれをインストールする必要があります。

アプリをローカルに実行およびデバッグするには、[Docker](https://www.docker.com/get-docker) もインストールする必要があります。

アプリをコンテナーとしてデプロイするには、Kubernetes、Helm、および以下の IBM Cloud CLI プラグインもインストールする必要があります。

Kubernetes をインストールするには、次のようにします。
* Mac ユーザー:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux ユーザー:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows ユーザー:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Helm をインストールするには、次のようにします。
* Mac ユーザーおよび Linux ユーザー:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows ユーザー:
Download and install the binary at https://github.com/kubernetes/helm/releases/tag/v2.6.0

container-registry プラグインをインストールするには、次のようにします。
`bx plugin install container-registry`

container-service プラグインをインストールするには、次のようにします。
`bx plugin install container-service`

