---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# {{site.data.keyword.cloud_notm}} Developer Tools CLI プラグインの手動インストール
{: #install-devtools-manually}

コンポーネントのインストールを細かく制御したい場合は、{{site.data.keyword.cloud}} 開発者用ツールのコマンド・ライン・インターフェース (CLI) プラグインを手動でインストールできます。それ以外の場合は、ほとんどのユーザー向けにすべての前提条件が[プラットフォーム・インストーラー](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)を使用して自動的にインストールされます。
{: shortdesc}

## 始める前に
{: cli-before-you-begin}

* {{site.data.keyword.cloud_notm}} 用コマンド・ライン・プラグインのインストールをサポートするために、スタンドアロン [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) をインストールします。
* コマンド・ラインからパッケージをダウンロードするために、[curl](https://curl.haxx.se/download.html){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") コマンドをインストールします。

## {{site.data.keyword.cloud_notm}} Developer Tools CLI プラグインのインストール
{: #install-devtools-idt}

{{site.data.keyword.cloud_notm}} Developer Tools CLI コマンドを使用すると、アプリケーションの作成、管理、デプロイ、デバッグ、およびテストを行うことができます。

{{site.data.keyword.cloud_notm}} 開発者用ツール・プラグインをインストールするには、以下のコマンドを実行します。 
```
ibmcloud plugin install dev
```
{: codeblock}

## Docker のインストール
{: #install-devtools-docker}

アプリをローカルに実行およびデバッグするには、[Docker](https://www.docker.com/get-started){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールします。

## Kubernetes コマンド・ライン・ツールのインストール
{: #idt-install-kube}

Kubernetes ダッシュボードのローカル・バージョンを表示したり、アプリをクラスター内にデプロイしたりするには、ご使用のプラットフォーム用の [Kubernetes コマンド・ライン・ツール](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールします。

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

Kubernetes コマンド・ライン・ツールを使用してコマンドを実行するための接頭部は、`kubectl` です。
詳しくは、[CLI および API のセットアップ (Setting up the CLI and API)](/docs/containers?topic=containers-cs_cli_install#cs_cli_install) を参照してください。

## {{site.data.keyword.registrylong_notm}} CLI プラグインのインストール
{: #idt-install-container-registry-cli-plugin}

`container-registry` CLI プラグインを使用すると、IBM によってホストおよび管理されている専用レジストリー内に、Docker イメージを保管したり、{{site.data.keyword.cloud_notm}} アカウント内のすべてのユーザーと Docker イメージを共有したりできる、独自のイメージ名前空間をセットアップすることができます。


* {{site.data.keyword.registrylong}} プラグインをインストールするため、以下のコマンドを実行します。
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

詳しくは、[{{site.data.keyword.registrylong}} コマンド・リファレンス](/docs/services/Registry?topic=registry-registry_cli_reference)を参照してください。

## {{site.data.keyword.containerlong_notm}} CLI プラグインのインストール
{: #idt-install-kubernetes-cli-plugin}

{{site.data.keyword.containerlong}} で Kubernetes クラスターを作成および管理するには、以下のようにします。

* {{site.data.keyword.registryshort_notm}} プラグインをインストールするため、以下のコマンドを実行します。
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

詳しくは、[{{site.data.keyword.registryshort_notm}} コマンド・リファレンス](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference)を参照してください。

## Helm のインストール

{: #idt-install-helm}

Kubernetes ベースのパッケージ・マネージャーである [Helm](https://helm.sh/docs/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をインストールします。

* MacOS および Linux&trade; ユーザーは、以下のコマンドを実行します。
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade; ユーザーは、Helm [バイナリー](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") をダウンロードしてインストールできます。

## {{site.data.keyword.openwhisk_short}} CLI プラグインのインストール
{: #idt-install-functions}

{{site.data.keyword.openwhisk}} CLI プラグインを使用して、アクション内のコード・スニペットの管理、パッケージへのアクションのバンドル、およびアクションがイベントに応答できるようにするためのトリガーおよびルールの作成を行うことができます。

{{site.data.keyword.openwhisk_short}} CLI プラグインをインストールするため、以下のコマンドを実行します。
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

詳しくは、[ {{site.data.keyword.openwhisk_short}} CLI プラグインのセットアップ (Setting up the OpenWhisk CLI plug-in) ](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)を参照してください。

## SDK Generator CLI プラグインのインストール
{: #idt-install-sdk-gen}

{{site.data.keyword.cloud_notm}} の開発者は、このプラグインを使用して [Open API 仕様 ](https://www.openapis.org/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") 準拠の REST API 定義から SDK を生成することができます。 REST API 定義を変更する際、このプラグインを使用することで、プロジェクト全体を再生成する代わりに SDK のみを再生成することができます。

SDK ジェネレーター CLI プラグインをインストールするため、以下のコマンドを実行します。
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

詳しくは、[SDK ジェネレーター](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)を参照してください。
