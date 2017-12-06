---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-20"

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

{{site.data.keyword.Bluemix_notm}} CLI は、機能を拡張するためにプラグイン・フレームワークをサポートしています。リポジトリーまたは Web URL からプラグインをインストールしたり、ローカルにプラグイン・バイナリーをインストールしたりすることができます。 

[{{site.data.keyword.Bluemix_notm}} CLI プラグイン・リポジトリー](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![「外部リンク」アイコン](../../../icons/launch-glyph.svg) は、プラグインがホストされている公式リポジトリーです。

プラグインを管理するためのその他のコマンドについては、`bluemix plugin` を実行してヘルプ・メッセージを表示してください。{: tip}

## {site.data.keyword.Bluemix_notm}} CLI リポジトリーからのプラグインのインストール

### ステップ 1: プラグインの検索

1. リポジトリーでプラグインを探すには、コマンド `bluemix plugin repo-plugins -r REPO_NAME` を使用します。
2. {{site.data.keyword.Bluemix_notm}} CLI は、デフォルトで `Bluemix` という名前を使用します。公式の `Bluemix` リポジトリー内のプラグインをリストすることができます。例えば次のようにします。
  
  ```
  $ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### ステップ 2: プラグインのインストール

プラグインをインストールするには、`bx plugin install PLUGIN_NAME -r REPO_NAME` コマンドを使用します。例えば次のようにします。

  ```
  $ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## ローカルでのプラグインのインストール

ローカル・マシンにプラグイン・バイナリーをインストールするには、`bluemix plugin install LOCAL_FILE_NAME` コマンドを使用します。例えば次のようにします。

  ```
  $ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Web URL からのプラグインのインストール

Web URL から直接プラグインをインストールするには、`bluemix plugin install URL` コマンドを使用します。次に例を示します。

  ```
  ~$ bluemix plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
