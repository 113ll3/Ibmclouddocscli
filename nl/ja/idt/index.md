---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# アプリの開発とデプロイ
{: #developing}

{{site.data.keyword.dev_cli_notm}} CLI によるクラウド・ネイティブ・アプリの開発は、以下のとおり、かなり単純なフローです。

1. [デプロイメント用アプリの作成または有効化](#idt-create)。
2. コンテナーを使用した、ローカルでのアプリの[コーディング、ビルド、および実行](#code-build-run)。
3. {{site.data.keyword.cloud_notm}}へのアプリの[デプロイ](#cli-deploy)。

## クラウド・デプロイメント用アプリの作成または有効化
{: #idt-create}

アプリを作成する方法はいくつかあります。
- [アプリ・サービス Web コンソール](https://cloud.ibm.com/developer/appservice/dashboard): 汎用の Web アプリおよびマイクロサービス用
- [Watson ダッシュボード](https://cloud.ibm.com/developer/watson/dashboard): Watson ベースの機能に対応したスターター・アプリの作成用
    - 業界およびテクノロジーをベースにしたその他のダッシュボードも、{{site.data.keyword.cloud_notm}} ホーム・ページのハンバーガー・メニューから使用できます。 いずれも、スターター・キットを使用して新規アプリを作成するアプローチは似ています。
- {{site.data.keyword.dev_cli_notm}} CLI の [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) コマンドでは、新規アプリを作成できます。
- {{site.data.keyword.dev_cli_notm}} CLI の [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) コマンドでは、既存のサーバー・サイド・アプリ上でクラウドを素早く使用可能にすることができます。

上記のいずれの作成方法でも、フローはよく似ています。 使用するプロジェクト・タイプ、実装言語、およびアプリ・パターンを選択します。 また、認証やパーシスタンスなど、サービスをアプリに追加することを選択できます。 最後に、アプリに対して DevOps 機能を追加できます。この機能は、ソース制御とチームのコミュニケーションのための完全なツールチェーンを提供します。 さらにアプリの検証、ビルド、および {{site.data.keyword.cloud_notm}} へのデプロイがコミットされるたびにトリガーされるパイプラインも含まれます。

![{{site.data.keyword.dev_cli_notm}} CLI を使用する作成フローのサンプル](create_flow.png "{{site.data.keyword.dev_cli_notm}} CLI を使用する作成フローのサンプル")

{{site.data.keyword.dev_cli_notm}} CLI は、密接に連携することで、円滑な開発体験を提供します。 Web コンソールで作成されるプロジェクトには、生成済みのソース・コードをワークステーションにダウンロードしてさらに開発を追加するための**「コードのダウンロード」**ボタンが表示されます。

### 便利な CLI コマンド
{: #helpful}

以下の `ibmcloud dev` CLI コマンドは、プロジェクトおよび Web コンソールを使用した作業に役立ちます。
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code): アプリのソース・コードをワークステーションにダウンロードします。
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console): {{site.data.keyword.cloud_notm}} 内の現行アプリのプロジェクト・ページがブラウザーに開かれます。
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create): 新しいアプリを作成するためのコマンドです。
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete): {{site.data.keyword.cloud_notm}} プロジェクト・エリアから現行アプリを削除します。
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable): 既存のサーバー・サイド・アプリをクラウド対応にするためのコマンドです。
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials): バインドされたサービスを使用可能にするためにプロジェクトによって必要とされる資格情報を取得します。
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list): 現在選択されている組織およびスペース内に、CLI またはコンソールから作成したすべてのアプリをリストします。

### アプリのプロジェクト構造の探索
{: #exploring-project}

開発者用ツールを使用して作成または使用可能化されたプロジェクトには、`cli-config.yml` ファイル内にカプセル化されている事前構成された設定が付属しています。 `cli-config.yml` には、`ibmcloud dev` コマンドによって使用されるデフォルト項目があります。それらは、コマンド・ラインから渡す値によってオーバーライドできます。

### 関連するブログやビデオ
{: #ref1}

- ビデオ: [Ubuntu Linux 上での {{site.data.keyword.cloud_notm}} 開発者ツールのインストール&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
- ブログ: [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")

## コーディング、ビルド、および実行
{: #code-build-run}

プロジェクトを作成した後、そのプロジェクトをどう活用するかはユーザー次第です。 フローの一般的な構成は、ソース・コードを編集し、次に [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) を実行して、そのアプリの言語と構成に固有のローカル・コンテナー内でアプリをコンパイルすることです。 アプリの言語および使用される生成プログラムに応じて、アプリのビルドとローカルでの実行をデフォルトでサポートする 1 つ以上のコンテナーが存在します。 標準では、ビルドおよびローカル・デバッグのための「ツール」コンテナーがあります。 このコンテナーには、開発を支援する追加のツールや機能が含まれます。 また、「実行」コンテナーもあります。これは、Cloud Foundry または IBM の Kubernetes ベースのコンテナー環境のいずれかにおいて、アプリがクラウドにデプロイされた際のランタイム環境を再現します。

アプリをコーディングするときは、好みの IDE またはエディターを任意に使用できます。 {{site.data.keyword.IBM_notm}} は、Microsoft&trade; Visual Studio Code (VSCode) エディターの拡張を提供しており、これを使用すると、エディター内から直接すべての IDE のコマンドを利用できます。

プロジェクトがビルドされたら、[`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) または [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) を使用して、アプリを実行します。 アプリは、適切なコンテナー内で実行されます。 一部のアプリ・パターンでは、アプリの外部にある複数のコンテナーがサポートされます。 アプリは、実行時またはデバッグ時に自動的に開始され、構成されます。 アプリに関連付けられた任意のテスト・ケースを実行する、[`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) コマンドも存在します。

### ローカル・コンテナーが使用される方法
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI は、アプリのビルドとテストに 2 つのコンテナーを使用します。 1 つはツール・コンテナーであり、ここには、アプリをビルドおよびテストするために必要なユーティリティーが含まれています。 このコンテナーの Dockerfile は、[`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) パラメーターで定義されます。 このコンテナーには特定のランタイムの開発に通常使用されるツールが含まれるため、開発コンテナーと見なすことができます。

2 つ目は、実行コンテナーです。 このコンテナーは、例えば、{{site.data.keyword.cloud}} で使用するためなど、デプロイするのに適した形式になっています。 このため、アプリを開始するエントリー・ポイントが定義されています。 {{site.data.keyword.dev_cli_short}} CLI からアプリを実行することを選択すると、このコンテナーが使用されます。 このコンテナーの Dockerfile は、[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) パラメーターで定義されます。

### 便利な CLI コマンド
{: #helpful2}

以下の CLI コマンドはプロジェクトのデバッグに役立ちます。
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) ローカル・コンテナー内にプロジェクトをビルドします。
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) ローカル・コンテナー内でアプリケーションをデバッグします。
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) ローカル・コンテナー内でアプリケーションを実行します。
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) ローカル・コンテナーにシェルを開きます。
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) {{site.data.keyword.dev_cli_notm}} CLI で使用されるコンテナーの状況をチェックします。
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) コンテナーを停止します。
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) ローカル・コンテナー内でアプリケーションをテストします。

### ローカル・アプリのデバッグ
{: #ref2}

- [ローカル・アプリのデバッグ](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## デプロイします。
{: #cli-deploy}

適切なクラウドのネイティブ環境下で、すべてのデプロイメントを管理するための完全に機能する DevOps パイプラインと、その他の豊富な機能を使用します。 作成フローの中で、IBM Cloud の DevOps を使用するようにアプリをセットアップできます。 組み込みの DevOps を使用する準備ができていない場合は、手動で [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) を実行してアプリをデプロイするか、独自の DevOps パイプライン内で `deploy` コマンドを使用できます。

### 便利な CLI コマンド
{: #helpful3}

以下の CLI コマンドは、デプロイメント・プロセスでのプロジェクトを使用した作業に役立ちます。
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console): プロジェクトの {{site.data.keyword.cloud_notm}} コンソールを開きます。
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy): アプリケーションを {{site.data.keyword.cloud_notm}} にデプロイします。
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view): プロジェクトの URL を表示します。

### 関連するブログやビデオ
{: #ref3}

- ブログ: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
- ブログ: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
