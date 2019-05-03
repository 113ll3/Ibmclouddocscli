---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# {{site.data.keyword.cloud_notm}} Developer Tools CLI プラグインのトラブルシューティング
{: #troubleshoot}

{{site.data.keyword.dev_cli_short}} コマンド・ライン・インターフェース (CLI) を使用してアプリを作成する際の一般的な問題には、デプロイメントの失敗や、コードを取得できないなどが含まれます。 多くの場合、いくつかの簡単なステップを実行することで、これらの問題から復旧することが可能です。
{: shortdesc}

## 非モバイル・パターンでアプリを作成するとホスト名エラーになるのはなぜですか?
{: #ts-cli-hostname-error}
{: troubleshoot}

{{site.data.keyword.dev_cli_short}} CLI を使用して Cloud Foundry にアプリをデプロイする場合、以下のエラーが表示されることがあります。 固有のホスト名を入力してもこのメッセージが表示されることがあります。
```
The hostname <myHostname> is taken.
```
{: screen}
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
{: #ts-cli-general-failures}
{: troubleshoot}

`create`、`delete`、 `list`、または `code` のコマンドを使用すると、以下のエラーが表示される場合があります。
```
Failed to <command> app.
```
{: screen}
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
{: #ts-cli-nosuchimage}
{: troubleshoot}

最初にビルドせずにアプリに対して `ibmcloud dev run` を実行しようとすると、以下のエラーが表示されることがあります。
```
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
{: screen}
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
{: #ts-cli-object-storage}
{: troubleshoot}

CLI を使用して、{{site.data.keyword.objectstorageshort}} 機能を持つ 2 つのアプリを作成すると、以下のエラーが表示される場合があります。

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

このエラーの原因は、{{site.data.keyword.objectstorageshort}} サービスが、フリー {{site.data.keyword.objectstorageshort}} プランの 1 つのインスタンスのみ提供していることです。
{: tsCauses}

別のプランを選択してください。
{: tsResolve}

## アプリの作成時にコードが取得されないのはなぜですか?
{: #retrieve-code-error}
{: troubleshoot}

CLI を使用してアプリを作成するときに、以下のエラーが表示されることがあります。
```
FAILED                            
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
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

	1. {{site.data.keyword.dev_console}}で、[アプリ](https://cloud.ibm.com/resources){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")を選択します。

	2. **「コードのダウンロード」**をクリックします。
{: tsResolve}

## Node.js アプリに対して `ibmcloud dev run` コマンドを実行できないのはなぜですか?
{: #ts-cli-node}
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
{: screen}
{: tsSymptoms}

このエラーは、`appmetrics` モジュールが別のアーキテクチャーにインストールされている場合に発生します。 1 つのアーキテクチャーにインストールされているネイティブ NPM モジュールは、別のアーキテクチャーでは機能しません。 付属の Docker イメージは、Linux カーネルに基づいています。
{: tsCauses}

`node_modules` フォルダーを削除してから、`ibmcloud dev run` コマンドを再度実行します。
{: tsResolve}

## {{site.data.keyword.cloud_notm}} にデプロイできないのはなぜですか?
{: #ts-cli-deploy-issues}
{: troubleshoot}

{{site.data.keyword.cloud_notm}} へデプロイしようとすると、失敗しますが、表示されるエラーはありません。
{: tsSymptoms}

アカウントにログインしていない可能性があります。
{: tsCauses}

以下のコマンドを実行してログインし、再試行してください。
```
ibmcloud login
```
{: tsResolve}

## {{site.data.keyword.cloud_notm}} 上の Kubernetes にデプロイできないのはなぜですか?
{: #ts-cli-kube-deploy}
{: troubleshoot}

クラスター名のプロンプトが出された後、以下の失敗が表示される場合があります。
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

これは、ほとんどの場合、無効のクラスター名が原因です。 同じコマンドに `--trace` を付けて実行することによって、原因を確認することができます。エラー出力には、以下の詳細が含まれる場合があります。
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

正しいクラスターを使用していて、かつクラスターがデプロイメント用に構成されていることを確認するために、以下を実行します。
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## イメージ・ターゲットをデプロイできないのはなぜですか?
{: #ts-deploy-image-target}
{: troubleshoot}

デプロイ用イメージ・ターゲットのプロンプトが出された後、以下の失敗が表示される場合があります。
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

これは、ほとんどの場合、無効のデプロイ用イメージ・ターゲットが原因です。 具体的には、デプロイ用イメージ・ターゲットの中間値である名前空間が無効である可能性があります。
{: tsCauses}

デプロイ用イメージ・ターゲット内の名前空間が、次のコマンドを実行して表示される名前空間のいずれかと一致していることを確認してください。
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## アプリの言語を判別できないのはなぜですか?
{: #ts-cli-determine-language}
{: troubleshoot}

アプリを開始しようとしたときに、以下の失敗が表示されることがあります。
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

このエラーの原因は、以下のいずれかである可能性があります。
- アプリケーションのソース・ディレクトリーではないディレクトリーから [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) コマンドを実行する。
- 認識されていない言語のアプリに対して [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) コマンドを実行する。
{: tsCauses}

必ず、アプリのソース・コードを含んでいるアプリ・ディレクトリーからコマンドを実行してください。 これで問題が解決されず、言語が[サポートされる言語](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options)のいずれかである場合は、`--language` パラメーターを使用して言語を指定してください。
{: tsResolve}

## クラウド・デプロイメントが有効になっているアプリをビルドまたは実行できないのはなぜですか?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

有効になっているアプリを[ビルド](/docs/cli/idt?topic=cloud-cli-idt-cli#build)または[実行](/docs/cli/idt?topic=cloud-cli-idt-cli#run)しようとしたときに、さまざまな失敗が発生することがあります。
{: tsSymptoms}

多くの考えられる原因が以下の各リンクに記載されています。
{: tsCauses}

- Spring アプリでのそのような問題の解決について詳しくは、『[既存 Spring Boot アプリケーションでのクラウド・デプロイメントの有効化 (Enabling existing Spring Boot applications for cloud deployment)](/docs/java-spring?topic=java-spring-enable_existing#enable_existing)』を参照してください。
- `Node.js` アプリでのそのような問題の解決について詳しくは、『[既存の Node.js アプリケーションでのクラウド・デプロイメントの有効化 (Enabling existing Node.js applications for cloud deployment)](/docs/node?topic=nodejs-enable_existing#enable_existing)』を参照してください。
{: tsResolve}

## {{site.data.keyword.dev_cli_notm}} CLI コンポーネントを別個にインストールする方法
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

{{site.data.keyword.dev_cli_notm}} CLI コンポーネントを別個にインストールするには、これらの[ステップ](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually)に従ってください。

## Docker イメージをビルドできないのはなぜですか?
{: $ts-cli-docker}
{: troubleshoot}

以下のエラーが表示されることがあります。 
```
失敗
Docker イメージのビルド中に、エラー exit status 1 が
検出されました。
```
{: screen}

このエラーの原因は、以下のいずれかである可能性があります。
- Docker がインストールされていない。
- Docker デーモンが稼働していない。
{: tsCauses}

以下のようにして、Docker がインストール済みで、かつ稼動していることを確認します。
- [Docker for Mac](https://docs.docker.com/docker-for-mac/install/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールまたは開始する場合
- [Docker for Windows](https://docs.docker.com/docker-for-windows/install/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールまたは開始する場合
- [Docker for Linux](https://docs.docker.com/v17.12/install/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールまたは開始する場合
{: tsResolve}

## Helm バージョンの非互換性を解決するには、どうすればよいですか?
{: ts-cli-helm}
{: troubleshoot}

クライアントとサーバーで Helm のバージョンが同期していない場合、以下のエラーが表示されることがあります。
```
失敗
アクションを実行できませんでした:  exit status 1: エラー: アップグレードが失敗しました:
configmaps は禁止されています (configmaps is forbidden): ユーザー "system:serviceaccount:kube-system:default"
はリソース "configmaps" (API グループ "" 内、名前空間
"kube-system" 内) をリストできません (User "system:serviceaccount:kube-system:default"
cannot list resource "configmaps" in API group "" in the namespace
"kube-system")
```
{: screen}

```
失敗
「helm upgrade」コマンドを exit status 1 が原因で完了できませんでした
```
{: screen}

この問題を解決するには、クライアントのバージョンをクラスターと同じバージョンに設定します。例えば、Helm バージョン 2.8.1 をインストールするには、以下のコマンドを実行します。
{: tsResolve}

* Mac および Linux の場合、次のコマンドを実行します。
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* Windows の場合、管理者として次の操作を実行します。[https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") で `helm` バイナリーをダウンロードしてインストールします。
  
  PowerShell 端末から、次のコマンドを使用します。
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```

## 「@」が含まれるユーザー名の使用時に ibmcloud dev build が失敗するのはなぜですか?
{: ts-cli-username}
{: troubleshoot}
イメージをビルドするプロセス中に、Docker ツールのイメージ内でユーザーとしてご使用のユーザー名が使用されます。このユーザー名に「@」や「-」などの特殊文字が含まれている場合、Docker イメージをビルドするプロセスが失敗し、以下のエラーが発生することがあります。
```
イメージにユーザー johnsmith@acme.com (ID 501) が追加されます

Docker イメージのビルドの実行中 (Executing docker image build)  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

失敗
Docker イメージのビルド中に、エラー exit status 1 が検出されました。

コマンドによる出力をダンプしています:
```
{: screen}

この問題を解決するには、ご使用のユーザー名を変更して特殊文字が含まれないようにするか、以下のフラグを指定して代わりに root ユーザーを使用します。
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
