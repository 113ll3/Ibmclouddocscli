---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

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
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
状況             名前                                   バージョン                       説明
更新が使用可能   container-service/kubernetes-service   0.2.99, 0.2.95, 0.2.80...      Kubernetes クラスター管理用の IBM Cloud Kubernetes サービス (IBM Cloud Kubernetes Service for management of Kubernetes clusters)
更新が使用可能   cloud-functions                        1.0.30, 1.0.29, 1.0.28...      IBM Cloud Functions 用の IBM Cloud CLI プラグイン (IBM Cloud CLI plug-in for IBM Cloud Functions)
...
```
{: screen}

### ステップ 2: プラグインのインストール
{: step2-install-plugin}

プラグインをインストールするには、`ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` コマンドを使用します。 例えば、公式 IBM プラグイン・リポジトリー「IBM Cloud」からプラグインをインストールするには、次のコマンドを使用します。

```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
リポジトリー 'IBM Cloud' から 'auto-scaling' を検索しています...
プラグイン 'auto-scaling 0.2.7' がリポジトリー 'IBM Cloud' 内で見つかりました
バイナリー・ファイルをダウンロードしようとしています...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 バイトがダウンロードされました
バイナリーをインストールしています...
OK
プラグイン 'auto-scaling 0.2.7' は
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
```
{: screen}

## ローカルでのプラグインのインストール
{: #install-plugin-locally}

ローカル・マシンにプラグイン・バイナリーをインストールするには、`ibmcloud plugin install LOCAL_FILE_NAME` コマンドを使用します。 以下に例を示します。

```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
プラグイン './auto-scaling-darwin-amd64-0.2.7' をインストールしています...
OK
プラグイン 'auto-scaling 0.2.7' は
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
$
```
{: screen}

## Web URL からのプラグインのインストール
{: install-plugin-from-url}

Web URL から直接プラグインをインストールするには、`ibmcloud plugin install URL` コマンドを使用します。 以下に例を示します。
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

出力:
```
バイナリー・ファイルをダウンロードしようとしています...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 バイトがダウンロードされました
バイナリーをインストールしています...
OK
プラグイン 'auto-scaling 0.2.7' は
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
$
```
{: screen}
