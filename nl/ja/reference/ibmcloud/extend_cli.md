---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-21"

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

### プラグインの検索
{: #cli-search-plugin}

リポジトリーでプラグインを探すには、`ibmcloud plugin repo-plugins -r REPO_NAME` コマンドを使用します。

{{site.data.keyword.cloud_notm}} CLI には、「IBM Cloud」という名前の公式プラグイン・リポジトリーがあります。これは、以下の例のように検索することができます。
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                        Versions                       Description   
Update Available   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Manage Cloud Functions 
...
```
{: screen}

### プラグインのインストール
{: #cli-install-plugin}

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
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。 'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
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
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。 'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
$
```
{: screen}

## Web URL からのプラグインのインストール
{: #install-plugin-from-url}

Web URL から直接プラグインをインストールするには、`ibmcloud plugin install URL` コマンドを使用します。 以下に例を示します。
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
バイナリー・ファイルをダウンロードしようとしています...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 バイトがダウンロードされました
バイナリーをインストールしています...
OK
プラグイン 'auto-scaling 0.2.7' は
/Users/username/.bluemix/plugins/auto-scaling に正常にインストールされました。 'ibmcloud plugin show auto-scaling' を使用して詳細を表示してください。
$
```
{: screen}
