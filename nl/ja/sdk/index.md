---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-23"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK ジェネレーター
{: #sdk-cli}

{{site.data.keyword.IBM}} SDK ジェネレーター・プラグインは、[{{site.data.keyword.Bluemix_notm}} CLI ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/cli/reference/bluemix_cli/all_versions.html)にインストールできます。

{{site.data.keyword.Bluemix_notm}} の開発者は、このプラグインを使用して[Open API Specification ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.openapis.org/) 準拠の REST API 定義から SDK を生成できます。 REST API 定義を変更する際、このプラグインを使用することで、プロジェクト全体を再生成する代わりに SDK のみを再生成することができます。

特定のスペースの Cloud Foundry アプリに、SDK の生成に有効な REST API 定義が含まれているかどうかを確認することもできます。 最後に、{{site.data.keyword.IBM_notm}} SDK ジェネレーター・プラグインを使用して、REST API 定義が SDK ジェネレーターの条件に準拠していることを確認することができます。

この {{site.data.keyword.IBM_notm}} SDK ジェネレーター・プラグインによって、開発者は、生成済みの SDK を使用してバックエンド・サービスをアプリに簡単に統合することができます。 REST API に変更が生じた場合、SDK を再生成して古い SDK と置き換えることによって、SDK のアップグレードを行うことができます。 また、CLI を DevOps パイプラインに統合することによって、アプリをビルドするたびに、SDK が API スペックに常に整合していることを確認することができます。

REST API 定義は有効であり、かつ稼働中のサーバー・エンドポイントでホストするか、システム上のローカル・ファイルである必要があります。 REST API 定義がホストされている場合、`OPENAPI_SPEC` 環境変数に相対 URL を定義する必要があります。


## 要件
{: #prereqs}

以下の要件を満たしていることを確認します。

* [{{site.data.keyword.Bluemix_notm}}![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://bluemix.net) アカウントを持っている
* [Open API ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.openapis.org/) 仕様に準拠した有効な API 定義


## インストール
{: #installation}

1. [{{site.data.keyword.Bluemix}} CLI ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://clis.ng.bluemix.net/ui/home.html)をインストールします。

2. [プラグイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/cli/reference/bluemix_cli/all_versions.html#install_plug-in)をインストールします。

	```
	ibmcloud plugin install sdk-gen
	```
	{: codeblock}


## command
{: #commands}

以下のコマンドを使用して SDK の生成、Open API 定義ファイルの検証、または Cloud Foundry アプリのリストを行います。


### SDK の生成
{: #gen}

Use `ibmcloud sdk generate [arguments...] [command options]`


#### arguments
{: #gen-args}

* `APP_NAME` - 現在のスペースにある Cloud Foundry アプリの名前
* `OPENAPI_DOC_LOCATION` - ロー REST API 定義の JSON または YAML への URL または相対ファイル・パス
* `GENERATED_SDK_NAME` (オプション) - 生成された SDK の名前


#### options
{: #gen-options}

* `PLATFORM` (必須)
   * `--android` - Android SDK を生成します
   * `--ios` - iOS Swift SDK を生成します
   * `--swift` - Swift Server SDK を生成します
   * `--js` - JavaScript SDK を生成します
* `LOCATION` (必須) - `OPENAPI_DOC_LOCATION` のタイプを指定します
   * `-r` - リモート URL
   * `-f` - ファイル
   * `-a` - {{site.data.keyword.Bluemix_notm}} 上で稼働するアプリ
   * `-l` - ローカル・ホスト URL
* `--output "YOUR_RELATIVE_PATH"` (オプション) - 生成された SDK を `YOUR_RELATIVE_PATH` で指定されたディレクトリーに置きます (既存の SDK がある場合は上書きします)
* `--unzip` (オプション) - 生成された SDK を解凍します (既存の SDK 成果物がある場合は上書きします)


#### 使用法
{: #gen-usage}

{{site.data.keyword.Bluemix_notm}} で稼働中の Cloud Foundry アプリから SDK を生成するには、アプリの名前を CLI のパラメーターに使用します。 以下のコマンドでは、アプリの名前を`SDK_Name` に使用します。

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

Open API 定義ファイルへの URL、またはローカルの JSON ファイルまたは YAML ファイルから SDK を生成するには、以下のコマンドを使用します。

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Open API 定義の検証
{: #validating}

`ibmcloud sdk validate [argument]` を使用します。


#### arguments
{: #val-args}

* `APP_NAME` - 現在のスペースにある Cloud Foundry アプリの名前
* `OPENAPI_DOC_LOCATION` - ロー REST API 定義の JSON または YAML への URL または相対ファイル・パス


#### 使用法
{: #val-usage}

{{site.data.keyword.Bluemix_notm}} で稼働中の Cloud Foundry アプリの API スペックを検証するには、アプリの名前を CLI のパラメーターに使用します。

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

API スペック文書への URL、またはローカルの JSON ファイルまたは YAML ファイルから SDK を検証するには、以下のコマンドを使用します。

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### アプリ (Cloud Foundry) のリスト
{: #list-apps}

アプリのリストおよび API スペックの検証には、次のコマンドを使用します: `ibmcloud sdk list [argument] [option]` `OPENAPI_SPEC` 環境変数を、スペックをホスティングする相対 URL パスに設定する必要があります。


#### arguments
{: #list-args}

* `SPACE_NAME` (オプション) - 現在の組織内でアプリを検索する Cloud Foundry スペースの名前。 指定しない場合、現在のスペースが検索されます。


#### options
{: #list-options}

* `--url` (オプション) - リストの個々のアプリの Open API 定義への完全修飾 URL を表示します。


#### 使用法
{: #list-usage}

現在のスペースのアプリをリストするには、以下のコマンドを使用します。

```
ibmcloud sdk list
```
{: codeblock}

現在のスペースのアプリをリストして、API スペックの URL を表示するには、以下のコマンドを使用します。

```
ibmcloud sdk list --url
```
{: codeblock}

特定のスペースのアプリをリストするには、以下のコマンドを使用します。

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

特定のスペースのアプリをリストして、API スペックの URL を表示するには、以下のコマンドを使用します。

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
