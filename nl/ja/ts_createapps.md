---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-30"

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
{:troubleshoot: data-hd-content-type='troubleshoot'}

# {{site.data.keyword.Bluemix_notm}} Developer Tools CLI プラグインのトラブルシューティング
{: #troubleshoot}

{{site.data.keyword.dev_cli_short}} コマンド・ライン・インターフェース (CLI) を使用してアプリを作成する際の一般的な問題には、デプロイメントの失敗や、コードを取得できないなどが含まれます。 多くの場合、いくつかの簡単なステップを実行することで、これらの問題から復旧することが可能です。
{:shortdesc}

## 非モバイル・パターンでアプリを作成するとホスト名エラーになるのはなぜですか?
{: #hostname-error}
{: troubleshoot}

{{site.data.keyword.dev_cli_short}} CLI を使用して Cloud Foundry にアプリをデプロイする場合、以下のエラーが表示されることがあります。 固有のホスト名を入力してもこのメッセージが表示されることがあります。

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。
{: tsCauses}

以下のコマンドを実行してもう一度ログインしてください。
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 汎用コマンドが失敗するのはなぜですか?
{: #general}
{: troubleshoot}

`create`、`delete`、 `list`、または `code` のコマンドを使用すると、以下のエラーが表示される場合があります。

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、ログイン・トークンが有効期限切れになったことです。
{: tsCauses}

以下のコマンドを実行してもう一度ログインしてください。
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 新しいアプリのイメージが認識されないのはなぜですか?
{: #nosuchimage}
{: troubleshoot}

最初にビルドせずにアプリを実行しようとすると、以下のエラーが表示されることがあります。

```
$ ibmcloud dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: tsSymptoms}

アプリは、実行する前にビルドする必要があります。 現行アプリ・ディレクトリー内で以下のコマンドを実行します。
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

現行アプリ・ディレクトリー内で以下のコマンドを実行して、アプリを開始します。
```
ibmcloud dev run
```
{: tsResolve}

## {{site.data.keyword.objectstorageshort}} 機能を追加するとサービス・ブローカー・エラーになるのはなぜですか?
{: #os}
{: troubleshoot}

CLI を使用して、{{site.data.keyword.objectstorageshort}} 機能を持つ 2 つのアプリを作成すると、以下のエラーが表示される場合があります。

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、{{site.data.keyword.objectstorageshort}} サービスが、フリー {{site.data.keyword.objectstorageshort}} プランの 1 つのインスタンスのみ提供していることです。
{: tsCauses}

別のプランを選択してください。
{: tsResolve}

## アプリの作成時にコードが取得されないのはなぜですか?
{: #code}
{: troubleshoot}

CLI を使用してアプリを作成するときに、以下のエラーが表示されることがあります。

```
FAILED                            
Application created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

このエラーの原因は、内部タイムアウトです。
{: tsCauses}

以下のいずれかの方法を使用して、コードを取得してください。

* 次のコマンドを実行します。

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   `<your-app-name>` を、アプリ作成時に指定したアプリ名で置き換えます。

* {{site.data.keyword.dev_console}}を使用します。

	1. {{site.data.keyword.dev_console}}で、[アプリ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.bluemix.net/developer/appservice/apps)を選択します。

	2. **「コードのダウンロード」**をクリックします。
{: tsResolve}

## Node.js アプリに対して `ibmcloud dev run` コマンドを実行できないのはなぜですか?
{: #node}
{: troubleshoot}

Node.js Web アプリまたは BFF アプリに対して `ibmcloud dev run` コマンドを実行する場合、以下のエラーが表示されることがあります。

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

`node_modules` フォルダーを削除してから、`ibmcloud dev run` コマンドを再度実行します。
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}} にデプロイできないのはなぜですか?
{: troubleshoot}

{{site.data.keyword.Bluemix_notm}} へデプロイしようとすると、失敗しますが、エラーは表示されません。
{: tsSymptoms}

アカウントにログインしていない可能性があります。
{: tsCauses}

以下のコマンドを実行してログインし、再試行してください。
```
ibmcloud login
```
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}} 上の Kubernetes にデプロイできないのはなぜですか?
{: troubleshoot}

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
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

正しいクラスターを使用していて、かつクラスターがデプロイメント用に構成済みであることを確認するために、以下を実行します。
```
ibmcloud cs cluster-config <cluster-name>
```
{: tsResolve}

## イメージ・ターゲットをデプロイできないのはなぜですか?
{: troubleshoot}

デプロイ用イメージ・ターゲットのプロンプトが出された後、以下の失敗が表示される場合があります。
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

これは、ほとんどの場合、無効のデプロイ用イメージ・ターゲットが原因です。 具体的には、デプロイ用イメージ・ターゲットの中間値である名前空間が無効である可能性があります。
{: tsCauses}

デプロイ用イメージ・ターゲット内の名前空間が、以下のコマンドを実行して表示される名前空間のいずれかと一致していることを確認してください。
```
ibmcloud cr namespaces
```
{: tsResolve}

## アプリの言語を判別できないのはなぜですか?
{: troubleshoot}

アプリを開始しようとしたときに、以下の失敗が表示されることがあります。
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: tsSymptoms}

このエラーの原因は、以下のいずれかである可能性があります。
- アプリケーションのソース・ディレクトリーではないディレクトリーから [enable](/docs/cli/idt/commands.html#enable) コマンドを実行する。
- 現時点で認識されていない言語のアプリに対して [enable](/docs/cli/idt/commands.html#enable) コマンドを実行する。
{: tsCauses}

アプリのソース・コードを含んでいるアプリ・ディレクトリーからコマンドを実行してください。 これで問題が解決されず、言語が[サポートされる言語](/docs/cli/idt/commands.html#enable-language-options)のいずれかである場合は、`--language` パラメーターを使用して言語を指定してください。
{: tsResolve}

## クラウド・デプロイメントが有効になっているアプリをビルドまたは実行できないのはなぜですか?
{: troubleshoot}

有効になっているアプリを[ビルド](/docs/cli/idt/commands.html#build)または[実行](/docs/cli/idt/commands.html#run)しようとしたときに、さまざまな失敗が発生することがあります。
{: tsSymptoms}


多くの考えられる原因が以下の各リンクに記載されています。
{: tsCauses}

- Spring アプリでのそのような問題の解決について詳しくは、『[既存 Spring Boot アプリケーションでのクラウド・デプロイメントの有効化 (Enabling existing Spring Boot applications for cloud deployment)](/docs/java-spring/enable_existing.html#enable_existing)』を参照してください。
- `Node.js` アプリでのそのような問題の解決について詳しくは、『[既存の Node.js アプリケーションでのクラウド・デプロイメントの有効化 (Enabling existing Node.js applications for cloud deployment)](/docs/node/enable_existing.html#enable_existing)』を参照してください。
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}} 開発者ツールを手動でインストールするにはどのようにすればよいでしょうか?
{: #appendix}
ほとんどのユーザー向けにすべての前提条件がプラットフォーム・インストーラーを使用してインストールされます。 いずれかのコンポーネントを手動でインストールする必要がある場合のそれぞれの手順を以下に示します。
開発プラグインをインストールするには、最初に [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use) をインストールする必要があります。
開発プラグイン自体を使用するには、以下のコマンドを実行してそれをインストールする必要があります。 
```
ibmcloud plugin install dev
```
{: codeblock}
 
アプリをローカルに実行およびデバッグするには、[Docker](https://www.docker.com/get-docker) もインストールする必要があります。
 
アプリをコンテナーとしてデプロイするには、Kubernetes、Helm、および以下の IBM Cloud CLI プラグインもインストールする必要があります。
 
### Kubernetes をインストールするには、次のようにします。
Mac ユーザー:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Linux ユーザー:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Windows ユーザー:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### Helm をインストールするには、次のようにします。
Mac および Linux ユーザー:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Windows ユーザー:
[バイナリー](https://github.com/kubernetes/helm/releases/tag/v2.7.2)をダウンロードしてインストールします。

### container-registry プラグインをインストールするには、次のようにします。
```
ibmcloud plugin install container-registry
```
{: codeblock}

### container-service プラグインをインストールするには、次のようにします。
```
ibmcloud plugin install container-service
```
{: codeblock}
