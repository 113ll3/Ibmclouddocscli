---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-19"

keywords: cli, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# 入門チュートリアル
{: #getting-started}

このチュートリアルでは、一連の {{site.data.keyword.cloud}} 開発者ツールをインストールし、インストールを検証して、環境を構成します。 {{site.data.keyword.dev_cli_notm}} には、クラウド・アプリケーションを作成、開発、デプロイするためのコマンド・ライン・アプローチが備わっています。
{: shortdesc}

このチュートリアルのインストール・コマンドにより、入手可能な最新のスタンドアロン {{site.data.keyword.cloud_notm}} CLI バージョンと、以下のツールがインストールされます。

* `Homebrew` (Mac のみ)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} プラグイン
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} プラグイン
* {{site.data.keyword.cos_full_notm}} プラグイン
* {{site.data.keyword.registrylong_notm}} プラグイン
* {{site.data.keyword.containerlong_notm}} プラグイン

## 始める前に
{: #idt-prereq}

[{{site.data.keyword.cloud_notm}} アカウント](https://cloud.ibm.com/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") と以下のシステム要件が必要です。

* Windows&trade; を実行している場合、一部の機能は、Windows&trade; 10 Pro を実行していないとサポートされません。
* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## ステップ 1. インストール・コマンドの実行
{: #step1-install-idt}

以下のコマンドを実行すると、最新バージョンの {{site.data.keyword.cloud_notm}} CLI がインストールされます。

* Mac および Linux&trade; の場合、次のコマンドを実行します。
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Windows&trade; 10 Pro の場合、管理者として次のコマンドを実行します。
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Windows&trade; PowerShell アイコンを右クリックして、**「管理者として実行」**を選択します。
  {: tip}

この [GitHub repo](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") からインストーラー・スクリプトをダウンロードすることもできます。

32 ビット・バージョンの CLI、または {{site.data.keyword.cloud_notm}} 専用環境用の最新バージョン以外の旧バージョンを使用する必要がある場合は、[{{site.data.keyword.cloud_notm}} CLI リリース](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")を参照してください。
{: note}

## ステップ 2. インストールの検証
{: #step2-verify-idt}

CLI と開発者ツールが正常にインストールされたことを検証するには、`help` コマンドを実行します。
```
ibmcloud dev help
```
{: codeblock}

出力には、使用方法の説明、現行バージョン、およびサポートされるコマンドがリストされます。

## ステップ 3. 環境の構成
{: #step3-configure-idt-env}

1. IBMid を使用して {{site.data.keyword.cloud_notm}} にログインします。 複数のアカウントを持っている場合、使用するアカウントを選択するように求めるプロンプトが出されます。 `-r` フラグを使用して地域を指定していない場合、地域も選択しなければなりません。
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  資格情報が拒否された場合、統合 ID を使用している可能性があります。 フェデレーテッド ID を使用してログインするには、`--sso` フラグを使用します。 詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam/federated_id?topic=iam-federated_id#federated_id)を参照してください。
  {: tip}

2. Cloud Foundry サービスにアクセスするには、Cloud Foundry 組織およびスペースを指定する必要があります。 以下のコマンドを実行して、対話式に組織とスペースを特定できます。
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  あるいは、サービスが所属する組織とスペースが分かる場合は、以下のコマンドを使用できます。
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## 次のステップ
{: #next-steps}

* 最初のアプリの開発およびデプロイに取り掛かることができます。 詳しくは、[CLI を使用したアプリの作成およびデプロイ](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)を参照してください。

* 新しい {{site.data.keyword.cloud_notm}} CLI リリースに関する通知を受け取ることができます。 [{{site.data.keyword.cloud_notm}} CLI リリース・リポジトリー](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン") にサブスクライブします。
