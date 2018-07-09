---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-27"

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

このインストールでは、{{site.data.keyword.Bluemix_notm}} CLI および以下のツールが用意されています。 

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

* Microsoft Windows&trade; を使用する場合、Windows 10 以降を使用する必要があります。
* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## ステップ 1: インストール・コマンドの実行
{: #step1}

* Mac および Linux の場合、次のコマンドを実行します。

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br><br>

* Windows 10 の場合、管理者として次のコマンドを実行します。

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br><br>
  Windows PowerShell アイコンを右クリックして、**「管理者として実行」**を選択します。
  {: tip}

## ステップ 2: インストールの検証
{: #step2}

CLI と開発者ツールが正常にインストールされたことを検証するには、`help` コマンドを実行します。

```
ibmcloud dev help
```
{: codeblock}
<br><br>
出力には、使用方法の説明、現行バージョン、およびサポートされるコマンドがリストされます。

## ステップ 3: 環境の構成
{: #step3}

1. ご使用の {{site.data.keyword.Bluemix_notm}} 地域の API エンドポイントに接続します。 例えば、{{site.data.keyword.Bluemix_notm}} 米国南部地域に接続するには、以下のコマンドを入力します。

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. IBM ID を使用して {{site.data.keyword.Bluemix_notm}} にログインします。

	```
	ibmcloud login
	```
	{: codeblock}
<br><br>
	資格情報が拒否された場合、統合 ID を使用している可能性があります。 詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam/login_fedid.html#using-an-api-key)を参照してください。
	{: tip}

3. 組織とスペースを設定します。

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 次のステップ
{: #next-steps}

これで、最初のアプリを開発してデプロイする準備ができました。 詳しくは、[アプリの開発とデプロイ](/docs/cli/idt/index.html)を参照してください。
