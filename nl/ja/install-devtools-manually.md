---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# {{site.data.keyword.cloud_notm}} Developer Tools CLI プラグイン・コンポーネントの手動インストール
{: #install-devtools-manually}

Developer Tools コンポーネントのインストールでより細かい制御が必要な場合には、以下の手順を使用して、それらを手動でインストールすることができます。 それ以外の場合は、ほとんどのユーザー向けにすべての前提条件が[プラットフォーム・インストーラー](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)を使用して自動的にインストールされます。
{: shortdesc}

## 始める前に
{: cli-before-you-begin}

* `ibmcloud` のコマンド・ライン・プラグインのインストールをサポートできるように、スタンドアロンの [{{site.data.keyword.cloud}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) をインストールします。
* コマンド・ラインからパッケージをダウンロードするために、[curl](https://curl.haxx.se/download.html){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") コマンドをインストールします。

## ステップ 1. {{site.data.keyword.cloud_notm}} Developer Tools CLI プラグインのインストール
{: #install-devtools-idt}

{{site.data.keyword.cloud_notm}} Developer Tools CLI (ibmcloud dev) コマンドを使用すると、アプリケーションの作成、管理、デプロイ、デバッグ、およびテストを行うことができます。

以下のコマンドを実行して、`dev` プラグインをインストールします。 
```
ibmcloud plugin install dev
```
{: codeblock}

## ステップ 2. Docker のインストール
{: #install-devtools-docker}

アプリをローカルに実行およびデバッグするには、[Docker](https://www.docker.com/get-docker){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールします。

## ステップ 3. Kubernetes のインストール
{: #idt-install-kube}

Kubernetes は、コンテナー化されたアプリケーションの自動デプロイ、自動スケーリング、および自動管理を行うためのオープン・ソースのコンテナー・オーケストレーション・エンジンです。

コンテナー化されたデプロイメントをサポートするには、プラットフォーム用の Kubernetes をインストールします。

* MacOS:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux&trade;:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows&trade;:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

## ステップ 4. Kubernetes CLI プラグインのインストール
{: #idt-install-kubernetes-cli-plugins}

コマンド・ラインから Kubernetes のデプロイメントを管理するには、以下のコンテナー・プラグインをインストールします。

* `container-registry` プラグインをインストールします。
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* `container-service` プラグインをインストールします。
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

詳しくは、[CLI および API のセットアップ (Setting up the CLI and API)](/docs/containers?topic=containers-cs_cli_install#cs_cli_install) を参照してください。

## ステップ 5. Helm のインストール
{: #idt-install-helm}

Kubernetes ベースのパッケージ・マネージャーである [Helm](https://helm.sh/docs/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールします。

* MacOS および Linux&trade; ユーザーは、以下のコマンドを実行します。
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade; ユーザーは、Helm [バイナリー](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をダウンロードしてインストールできます。

## ステップ 6. {{site.data.keyword.openwhisk_short}} CLI プラグインのインストール
{: #idt-install-functions}

{{site.data.keyword.openwhisk}} CLI プラグインを使用すると、アクションでのコード・スニペットの管理、アクションがイベントに応答できるようにするトリガーおよびルールの作成、パッケージへのアクションのバンドルを行うことができます。

{{site.data.keyword.openwhisk_short}} CLI プラグインをインストールするため、以下のコマンドを実行します。
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

詳しくは、[ {{site.data.keyword.openwhisk_short}} CLI プラグインのセットアップ (Setting up the OpenWhisk CLI plug-in) ](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)を参照してください。

## ステップ 7. SDK Generator CLI プラグインのインストール
{: #idt-install-sdk-gen}

{{site.data.keyword.cloud_notm}} の開発者は、このプラグインを使用して [Open API 仕様 ](https://www.openapis.org/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") 準拠の REST API 定義から SDK を生成することができます。 REST API 定義を変更する際、このプラグインを使用することで、プロジェクト全体を再生成する代わりに SDK のみを再生成することができます。

SDK Generator CLI プラグインをインストールします。
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

詳しくは、[SDK ジェネレーター](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)を参照してください。
