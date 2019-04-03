---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-01"

keywords: IBM Cloud Developer Tools CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.cloud_notm}} CLI の概説
{: #ibmcloud-cli}

このチュートリアルでは、一連の {{site.data.keyword.cloud}} 開発者ツールをインストールし、インストールを検証して、環境を構成します。 {{site.data.keyword.cloud_notm}} 開発者ツールは、Web アプリケーション、モバイル・アプリケーション、およびマイクロサービス・アプリケーションを作成、開発、およびデプロイするためのコマンド・ライン・アプローチを提供します。
{: shortdesc}

このインストールによって、スタンドアロン {{site.data.keyword.cloud_notm}} CLI および以下のツールを取得できます。

* `Homebrew` (Mac のみ)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} プラグイン
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} プラグイン
* {{site.data.keyword.registrylong_notm}} プラグイン
* {{site.data.keyword.containerlong_notm}} プラグイン
* `sdk-gen` プラグイン

## 始める前に
{: #idt-prereq}

[{{site.data.keyword.cloud_notm}} アカウント](https://cloud.ibm.com/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") と以下のシステム要件が必要です。

* Windows を実行している場合、一部の機能は、Windows 10 Pro を実行していないとサポートされません。
* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## ステップ 1. インストール・コマンドの実行
{: #step1-install-idt}

* Mac および Linux の場合、次のコマンドを実行します。
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Windows 10 Pro の場合、管理者として次のコマンドを実行します。
  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Windows PowerShell アイコンを右クリックして、**「管理者として実行」**を選択します。
  {: tip}

  この [GitHub repo](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") からインストーラー・スクリプトをダウンロードすることもできます。

<!--Uncomment when this linked topic goes to prod.
  For the steps to install these tools manually, see [Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->

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

2. Cloud Foundry サービスを使用するには、組織とスペースをターゲットにします。
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  オプションで、上記のコマンドの出力を使用して、次のコマンドで組織とスペースを手動で設定することができます。
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## 次のステップ
{: #next-steps}

最初のアプリケーションの開発およびデプロイに取り掛かることができます。 詳しくは、[CLI を使用したアプリの作成およびデプロイ](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)を参照してください。
