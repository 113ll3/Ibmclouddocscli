---
copyright:

  years: 2018

lastupdated: "2018-05-23"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# {{site.data.keyword.dev_cli_notm}} CLI の使用
{: #developing}

{{site.data.keyword.dev_cli_notm}} CLI を使用したクラウド・ネイティブ・アプリの開発は、以下のとおり、かなり単純なフローです。

1. [アプリの作成または有効化](#create)
2. コンテナーを使用した、ローカルでのアプリの[コーディング、ビルド、および実行](#build)
3. {{site.data.keyword.Bluemix_notm}} へのアプリの[デプロイ](#deploy)

## アプリの作成または有効化
{: #create}

クラウド・アプリを作成する方法はいくつかあります。
- [アプリ・サービス Web コンソール](https://console.bluemix.net/developer/appservice): 汎用の Web アプリおよびマイクロサービス用
- [Watson ダッシュボード](https://console.bluemix.net/dashboard/watson): Watson ベースの機能に対応したスターター・アプリの作成用
    - 業界およびテクノロジーをベースにしたその他のダッシュボードも、{{site.data.keyword.Bluemix_notm}} ホーム・ページのハンバーガー・メニューから使用できます。 いずれを使用する場合も、スターター・キットを使用して新規アプリを作成するアプローチは似ています。
- {{site.data.keyword.dev_cli_notm}} CLI の [`ibmcloud dev create`](./commands.html#create) コマンドでは、新規アプリを作成できます。
- {{site.data.keyword.dev_cli_notm}} CLI の [`ibmcloud dev enable`](./commands.html#enable) コマンドでは、既存のサーバー・サイド・アプリ上でクラウドを素早く使用可能にすることができます。

上記のいずれの作成方法でも、フローはよく似ています。 使用するプロジェクト・タイプ、実装言語、およびアプリ・パターンを選択できます。 また、認証やパーシスタンスなど、付加価値があるサービスをアプリに追加することを選択できます。 最後に、アプリに対して DevOps 機能を有効にするかどうかを選択できます。この機能は、ソース制御からチームのコミュニケーション、さらにアプリの検証、ビルド、および IBM Cloud へのデプロイがコミットされるたびにトリガーされるパイプラインに至るまでの完全なツールチェーンを提供します。

![IDT CLI を使用した作成フローのサンプル](create_flow.png "IDT CLI を使用した作成フローのサンプル") <br> 図 2. IDT CLI を使用した作成フローのサンプル

{{site.data.keyword.dev_cli_notm}} CLI は、密接に連携することで、シームレスな開発体験を提供します。 いずれの Web コンソールでも、そこで作成されたプロジェクトには、生成済みのソース・コードをワークステーションにダウンロードしてさらに開発を追加するための「コードのダウンロード」ボタンが表示されます。

### 便利な CLI コマンド
{: #helpful}

以下の CLI コマンドは、プロジェクトおよび Web コンソールを使用した作業に役立ちます。
- [`code`](./commands.html#code) アプリの生成済みソース・コードをワークステーションに直接プルします。
- [`console`](./commands.html#console) {{site.data.keyword.Bluemix_notm}} 内の現行アプリのプロジェクト・ページがブラウザーに開かれます。
- [`create`](./commands.html#create) 新規アプリを作成するためのコマンドです。
- [`delete`](./commands.html#delete) {{site.data.keyword.Bluemix_notm}} プロジェクト・エリアから現行アプリを削除します。
- [`enable`](./commands.html#enable) 既存のサーバー・サイド・アプリをクラウド対応にするためのコマンドです。
- [`get-credentials`](./commands.html#get-credentials) バインドされたサービスを使用可能にするためにプロジェクトによって必要とされる資格情報を取得します。
- [`list`](./commands.html#list) 現在選択されている組織/スペース内に、CLI またはコンソールからユーザーが作成したすべてのアプリをリストします。


### アプリのプロジェクト構造の探索
{: #exploring-project}

ツールを使用して作成または使用可能化されたプロジェクトには、`cli-config.yml` ファイル内にカプセル化されている事前構成された設定が付属しています。 `cli-config.yml` には、ツールのコマンドによって使用されるデフォルト項目が含まれています。それらは、コマンド・ラインを介して渡す値によってオーバーライドできます。

プロジェクトの構造の詳細については、以下を参照してください。
- [Java プロジェクト](/docs/apps/projects/java_project_contents.html)
- [NodeJS プロジェクト](/docs/apps/projects/node_project_contents.html)
- [Python プロジェクト](/docs/apps/projects/python_project_contents.html)
- [Swift プロジェクト](/docs/apps/projects/swift_project_contents.html)


### 関連するブログやビデオ
{: #ref1}

- ビデオ: [Ubuntu Linux 上での IDT のインストール](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- ブログ: [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## コーディング、ビルド、および実行
{: #build}


プロジェクトが作成された後、そのプロジェクトをどう活用するかはユーザー次第です。 フローの一般的な構成は、ソース・コードを編集し、次に [`ibmcloud dev build`](commands.html#build) を実行して、そのアプリの言語と構成に固有のローカル・コンテナー内でアプリをコンパイルすることです。 アプリの言語および使用される生成プログラムに応じて、アプリのビルドとローカルでの実行をデフォルトでサポートする 1 つ以上のコンテナーが存在します。  標準では、ビルドおよびローカル・デバッグのための「ツール」コンテナーがあります。  このコンテナーには、通常、開発を支援する追加のツールや機能が含まれます。  また、「実行」コンテナーも存在します。これは、Cloud Foundry または IBM の Kubernetes ベースのコンテナー環境のいずれかにおいて、アプリがクラウドにデプロイされた後の実際のランタイム環境に近い環境を再現します。


アプリケーションをコーディングするときは、好みの IDE またはエディターを任意に使用できます。 IBM は、Microsoft VisualStudio Code (VSCode) エディターの拡張を提供しており、これを使用すると、エディター内から直接すべての IDE のコマンドを利用できます。

プロジェクトのビルドが完了したら、次は、アプリの生成プログラムの構成に応じて、[`ibmcloud dev run`](commands.html#run) または [`ibmcloud dev debug`](commands.html#debug) を使用してアプリを実行する必要があります。  これにより、適切なコンテナー内でアプリが実行されます。  一部のアプリ・パターンでは、パーシスタンスやその他の機能など、アプリ外部の複数のコンテナーがサポートされます。  これらは、実行時またはデバッグ時に自動的に開始され、構成されます。  アプリに関連付けられた任意のテスト・ケースを実行する、[`ibmcloud dev test`](commands.html#test) コマンドも存在します。


### ローカル・コンテナーが使用される方法
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI は、アプリケーションのビルドとテストを容易にする 2 つのコンテナーを使用します。 1 つはツール・コンテナーであり、ここには、アプリケーションをビルドおよびテストするために必要なユーティリティーが含まれています。 このコンテナーの Dockerfile は、[`dockerfile-tools`](commands.html#command-parameters) パラメーターで定義されます。 このコンテナーには特定のランタイムの開発に通常使用されるツールが含まれるため、開発コンテナーと見なすことができます。

2 つ目は、実行コンテナーです。 このコンテナーは、例えば、{{site.data.keyword.Bluemix}} で使用するためなど、デプロイするのに適した形式になっています。 このため、アプリケーションを開始するエントリー・ポイントが定義されています。 {{site.data.keyword.dev_cli_short}} CLI からアプリケーションを実行することを選択すると、このコンテナーが使用されます。 このコンテナーの Dockerfile は、[`dockerfile-run`](commands.html#run-parameters) パラメーターで定義されます。


### 便利な CLI コマンド
{: #helpful2}

以下の CLI コマンドは、コーディング、ビルド、および実行サイクルにおいて、プロジェクトで作業するときに役立ちます。
- [`build`](./commands.html#build) ローカル・コンテナー内にプロジェクトをビルドします。
- [`debug`](./commands.html#debug) ローカル・コンテナー内でアプリケーションをデバッグします。
- [`run`](./commands.html#run) ローカル・コンテナー内でアプリケーションを実行します。
- [`shell`](./commands.html#shell) ローカル・コンテナーにシェルを開きます。
- [`status`](./commands.html#status) CLI で使用されるコンテナーの状況をチェックします。
- [`stop`](./commands.html#stop) コンテナーを停止します。
- [`test`](./commands.html#test) ローカル・コンテナー内でアプリケーションをテストします。

### 関連するブログやビデオ
{: #ref2}

- [ローカル・アプリのデバッグ](local_debug.html)





## デプロイします。
{: #deploy}

適切なクラウド・ネイティブ環境の下で、すべてのデプロイメントを管理する完全に機能する DevOps パイプラインを使用できるほか、その他の豊富な機能を活用できます。  作成フローの中で、IBM Cloud の DevOps を使用するようにアプリをセットアップできます。  組み込みの DevOps を使用する準備ができていない場合は、アプリを手動で [`ibmcloud dev deploy`](./commands.html#deploy) するか、独自の DevOps パイプライン内でデプロイ・コマンドを使用できます。  



### 便利な CLI コマンド
{: #helpful3}

以下の CLI コマンドは、デプロイ・プロセスでのプロジェクトを使用した作業に役立ちます。
- [`console`](./commands.html#console) プロジェクトの IBM Cloud コンソールを開きます。
- [`deploy`](./commands.html#deploy) アプリケーションを IBM Cloud にデプロイします。
- [`view`](./commands.html#view) プロジェクトの URL を表示します。


### 関連するブログやビデオ
{: #ref3}

- ブログ: [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- ブログ: [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
