---

copyright:

  years: 2015, 2018

lastupdated: "2018-11-15"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} CLI の概説
{: #overview}

このチュートリアルでは、一連の {{site.data.keyword.Bluemix}} 開発者ツールをインストールし、インストールを検証して、ご使用の環境を構成します。 {{site.data.keyword.Bluemix}} 開発者ツールは、Web アプリケーション、モバイル・アプリケーション、およびマイクロサービス・アプリケーションをエンドツーエンドで作成、開発、およびデプロイするためのコマンド・ライン・アプローチを提供します。
{:shortdesc}

このインストールによって、スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI および以下のツールを取得できます。

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
{: #prereq}

[{{site.data.keyword.Bluemix_notm}} アカウント](https://console.bluemix.net/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") と以下のシステム要件が必要です。

* Windows を実行している場合、一部の機能は、Windows 10 Pro を実行していないとサポートされません。
* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## ステップ 1. インストール・コマンドの実行
{: #step1}

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

  [GitHub repo](https://github.com/IBM-Cloud/ibm-cloud-developer-tools) からインストーラー・スクリプトをダウンロードすることもできます。

  これらのツールを手動でインストールする手順については、[ツールの再インストール](/docs/cli/ts_createapps.html#appendix)を参照してください。

## ステップ 2. インストールの検証
{: #step2}

CLI と開発者ツールが正常にインストールされたことを検証するには、`help` コマンドを実行します。

```
ibmcloud dev help
```
{: codeblock}
<br>
出力には、使用方法の説明、現行バージョン、およびサポートされるコマンドがリストされます。

## ステップ 3. 環境の構成
{: #step3}

1. ご使用の {{site.data.keyword.Bluemix_notm}} ロケーションの API エンドポイントに接続します。 例えば、{{site.data.keyword.Bluemix_notm}} のダラス・ロケーションに接続するには、以下のコマンドを入力します。

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. IBM ID を使用して {{site.data.keyword.Bluemix_notm}} にログインします。

	```
	ibmcloud login
	```
	{: codeblock}
    <br>

	資格情報が拒否された場合、統合 ID を使用している可能性があります。 詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam/login_fedid.html#federated_id)を参照してください。
	{: tip}

3. 組織とスペースを設定します。

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

最初のアプリケーションの開発およびデプロイに取り掛かることができます。 詳しくは、[CLI を使用したアプリの作成およびデプロイ](/docs/apps/create-deploy-cli.html)を参照してください。
