---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# プラグインを使用した {{site.data.keyword.Bluemix_notm}} CLI の拡張
{: #plug-ins}

{{site.data.keyword.Bluemix_notm}} CLI は、機能を拡張するためにプラグイン・フレームワークをサポートしています。 リポジトリーまたは Web URL からプラグインをインストールしたり、ローカルにプラグイン・バイナリーをインストールしたりすることができます。

[{{site.data.keyword.Bluemix_notm}} CLI プラグイン・リポジトリー](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) は、プラグインがホストされている公式リポジトリーです。

プラグインを管理するためのその他のコマンドについては、`ibmcloud plugin` を実行してヘルプ・メッセージを表示してください。
{: tip}

## {{site.data.keyword.Bluemix_notm}} CLI リポジトリーからのプラグインのインストール

### ステップ 1: プラグインの検索

1. リポジトリーでプラグインを探すには、コマンド `ibmcloud plugin repo-plugins -r REPO_NAME` を使用します。
2. {{site.data.keyword.Bluemix_notm}} CLI には、`Bluemix` という名前の公式リポジトリーがあります。以下の例に示すように、この公式プラグインを検索できます。

  ```
  $ ibmcloud plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### ステップ 2: プラグインのインストール

プラグインをインストールするには、`ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` コマンドを使用します。 例えば、公式 IBM プラグイン・リポジトリー `Bluemix` からプラグインをインストールするには、以下のコマンドを使用します。

  ```
  $ ibmcloud plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## ローカルでのプラグインのインストール

ローカル・マシンにプラグイン・バイナリーをインストールするには、`ibmcloud plugin install LOCAL_FILE_NAME` コマンドを使用します。 例えば次のようにします。

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Web URL からのプラグインのインストール

Web URL から直接プラグインをインストールするには、`ibmcloud plugin install URL` コマンドを使用します。 次に例を示します。

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
