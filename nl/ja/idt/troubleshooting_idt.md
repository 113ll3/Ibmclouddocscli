---
copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# IBM Cloud 開発者ツールのトラブルシューティング
{: #ts}

{{site.data.keyword.dev_cli_notm}} に関するいくつかの既知の問題と、その回避策を説明します。
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## 既知の問題
{: #knownissues}

以下のセクションでは、既知の問題および可能な解決策について説明します。


### 非モバイル・パターンのプロジェクトを作成すると hostname is taken エラーになる
{: #hostname}

{{site.data.keyword.dev_cli_short}} を使用して、Web アプリ・パターン、BFF パターン、またはマイクロサービス・パターンからプロジェクトを作成すると、以下のエラーが表示される場合があります。

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### 原因
{: #hostname-cause}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。


#### 解決策
{: #hostname-resolution}

再ログインしてください。

```
ibmcloud login
```
{: codeblock}


### {{site.data.keyword.dev_cli_short}} の一般障害
{: #general}

{{site.data.keyword.dev_cli_short}} の create、delete、list、または code のコマンドを使用すると、以下のエラーが表示される場合があります。

```
Failed to <command> project.
```
{: codeblock}


#### 原因
{: #general-cause}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。


#### 解決策
{: #general-resolution}

再ログインしてください。

```
ibmcloud login
```
{: codeblock}


### エラー: 新規プロジェクトを実行すると、「No such image」と表示される
{: #nosuchimage}

ビルドをせずにプロジェクトを実行すると、以下のエラーが表示される場合があります。

```
$ ibmcloud dev run testProject
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


#### 原因
{: #nosuchimage-cause}

プロジェクトは、実行する前にビルドする必要があります。


#### 解決策
{: #nosuchimage-resolution}

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションをビルドします。

```
ibmcloud dev build
```
{: codeblock}

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションを開始します。

```
ibmcloud dev run
```


### {{site.data.keyword.objectstorageshort}} 機能を追加すると、サービス・ブローカー・エラーが発生する
{: #os}

{{site.data.keyword.dev_cli_short}} を使用して、{{site.data.keyword.objectstorageshort}} 機能を持つ 2 つのプロジェクトを作成すると、以下のエラーが表示される場合があります。

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### 原因
{: #os-cause}

このエラーの原因は、{{site.data.keyword.objectstorageshort}} サービスが、フリー {{site.data.keyword.objectstorageshort}} プランの 1 つのインスタンスのみ提供していることです。


#### 解決策
{: #os-resolution}

このエラーを回避するために、別のプランを選択するようプロンプトが出されます。


### プロジェクト作成中にコードの取得に失敗する
{: #code}

{{site.data.keyword.dev_cli_short}} を使用してプロジェクトを作成すると、以下のエラーが表示される場合があります。

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### 原因
{: #code-cause}

このエラーの原因は、内部タイムアウトです。


#### 解決策
{: #code-resolution}

以下のいずれかの方法でコードを取得できます。

* CLI を使用して以下のコマンドを実行します。

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   `<your-project-name>` を、プロジェクト作成時に指定したプロジェクト名で置き換えます。

* {{site.data.keyword.dev_console}}を使用します。

	1. {{site.data.keyword.dev_console}}で、[プロジェクト![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.{DomainName}/developer/projects)を選択し、**「コードの取得 (Get the Code)」**をクリックします。

	2. **「コードの生成 (Generate Code)」**をクリックします。

	3. コードの生成が終了したら、**「コードのダウンロード」**をクリックします。


### Node.js プロジェクトで `ibmcloud dev run` を実行するとエラーになる
{: #node}

Node.js Web プロジェクトまたは BFF プロジェクト用の {{site.data.keyword.dev_cli_short}} で `ibmcloud dev run` を実行すると、以下のエラーが表示される場合があります。

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


#### 原因
{: #node-cause}

このエラーは、`appmetrics` モジュールが別のアーキテクチャーにインストールされている場合に発生します。 1 つのアーキテクチャーにインストールされているネイティブ NPM モジュールは、別のアーキテクチャーでは機能しません。 付属の Docker イメージは、Linux カーネルに基づいています。


#### 解決策
{: #node-resolution}

`node_modules` フォルダーを削除してから、`ibmcloud dev run` を再度実行します。


### {{site.data.keyword.Bluemix_notm}} へのデプロイに失敗する
{: #failuretodeploy}

{{site.data.keyword.dev_cli_short}}を使用して {{site.data.keyword.Bluemix_notm}} へのデプロイを行おうとしたときに、{{site.data.keyword.Bluemix_notm}} へのデプロイは行われないが、エラーがないことがあります。


#### 原因
{: #cause1}

アカウントにログインしていない可能性があります。

#### 解決策
{: #resolution1}

ログインして、やり直してください。

```
ibmcloud login
```


### {{site.data.keyword.Bluemix_notm}} 上の Kubernetes へのデプロイに失敗する
{: #failuretodeploytokube}

クラスター名を求める最初のプロンプトの後、次のような失敗が表示されることがあります。

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### 原因
{: #cause2}

最も可能性の高い原因は無効なクラスター名です。これは、同じコマンドを `--trace` を指定して実行することで確認でき、エラー出力に次のように表示される可能性があります。

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### 解決策
{: #resolution2}

正しいクラスターを使用していて、かつクラスターがデプロイメント用に構成済みであることを確認するために、以下を実行します。

```
ibmcloud cs cluster-config <cluster-name>
```


### {{site.data.keyword.Bluemix_notm}} 上の Kubernetes へのデプロイに失敗する

デプロイ用イメージ・ターゲットを指定するよう求めるプロンプトの後、次のような失敗が表示されることがあります。

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### 原因
{: #cause3}

最も可能性の高い原因は、無効なデプロイ用イメージ・ターゲットです。 具体的には、デプロイ用イメージ・ターゲットの中間値である名前空間が無効である可能性があります。


#### 解決策
{: #resolution3}

デプロイ用イメージ・ターゲット内の名前空間が、以下を実行して表示される名前空間のいずれかと一致していることを確認します。

```
ibmcloud cr namespaces
```



## 付録
{: #appendix}

プラットフォーム・インストーラーを使用するほとんどのユーザー用に、すべての前提条件がインストールされます。いずれかのコンポーネントを手動でインストールする必要がある場合の手順を以下に示します。

開発プラグインをインストールするには、まず [IBM Cloud CLI](../reference/bluemix_cli/get_started.md#getting-started) をインストールする必要があります。

開発プラグイン自体を使用するには、`ibmcloud plugin install dev -r Bluemix` コマンドを実行してそれをインストールする必要があります。

アプリケーションをローカルに実行およびデバッグするには、[Docker ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.docker.com/get-docker) もインストールする必要があります。

アプリケーションをコンテナーとしてデプロイするには、`Kubernetes`、`Helm`、および以下の IBM Cloud CLI プラグインもインストールする必要があります。

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
`ibmcloud plugin install container-registry`

container-service プラグインをインストールするには、次のようにします。
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## ヘルプおよびサポートの利用
{: #gettinghelp}

{{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}}または {{site.data.keyword.dev_cli_notm}} に関して問題または質問がある場合、情報を検索するか、フォーラムを通して質問することによって、ヘルプを利用できます。 サポート・チケットをオープンすることもできます。

フォーラムに投稿するときには、{{site.data.keyword.Bluemix_notm}} 開発チームに通知するために、質問にタグを付けることができます。

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

{{site.data.keyword.dev_console}}または {{site.data.keyword.dev_cli_notm}}を使用したアプリの開発やデプロイに関して技術上の質問がある場合は、次のようにします。

* [スタック・オーバーフロー ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) に質問を投稿し、質問に `bluemix-dev-services` および `ibm-bluemix` というタグを付けます。
* [Slack ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](http://ibm-cloud-tech.slack.com/) の `bluemix-dev-services` チャネルで質問を投稿します。 すぐに [登録 ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](http://ibm.biz/IBMCloudNativeSlack) してください。


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

これらのフォーラムの使用について詳しくは、『[ヘルプの取得![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/support/index.html#getting-help)』を参照してください。

{{site.data.keyword.IBM}} サポート・チケットのオープン、またはサポート・レベルおよびチケットの重大度については、『[サポートへのお問い合わせ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/support/index.html#contacting-support)』を参照してください。

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
