---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# プラグインを使用した {{site.data.keyword.cloud_notm}} CLI の拡張
{: #plug-ins}

{{site.data.keyword.cloud}} CLI は、機能を拡張するためにプラグイン・フレームワークをサポートしています。 リポジトリーまたは Web URL からプラグインをインストールしたり、ローカルにプラグイン・バイナリーをインストールしたりすることができます。

[{{site.data.keyword.cloud_notm}} CLI プラグイン・リポジトリー](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) は、プラグインがホストされている公式リポジトリーです。

プラグインを管理するためのその他のコマンドについては、`ibmcloud plugin` を実行してヘルプ・メッセージを表示してください。
{: tip}

## {{site.data.keyword.cloud_notm}} CLI リポジトリーからのプラグインのインストール
{: #install-from-repo}

### ステップ 1: プラグインの検索
{: #step1-search-plugin}

1. リポジトリーでプラグインを探すには、`ibmcloud plugin repo-plugins -r REPO_NAME` コマンドを使用します。
2. {{site.data.keyword.cloud_notm}} CLI には、「IBM Cloud」という名前の公式リポジトリーがあります。以下の例に示すように、この公式プラグインを検索できます。

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### ステップ 2: プラグインのインストール
{: step2-install-plugin}

プラグインをインストールするには、`ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` コマンドを使用します。 例えば、公式 IBM プラグイン・リポジトリー「IBM Cloud」からプラグインをインストールするには、次のコマンドを使用します。

  ```
  $ ibmcloud plugin install auto-scaling 
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## ローカルでのプラグインのインストール
{: #install-plugin-locally}

ローカル・マシンにプラグイン・バイナリーをインストールするには、`ibmcloud plugin install LOCAL_FILE_NAME` コマンドを使用します。 以下に例を示します。

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Web URL からのプラグインのインストール
{: install-plugin-from-url}

Web URL から直接プラグインをインストールするには、`ibmcloud plugin install URL` コマンドを使用します。 以下に例を示します。

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
