---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# スタンドアロン {{site.data.keyword.cloud_notm}} CLI のインストール
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI は、{{site.data.keyword.cloud_notm}} のリソースを管理するためのコマンド・ライン・インターフェースを提供します。 引き続き `cf` CLI を使用して {{site.data.keyword.cloud_notm}} にログインすることもできますが、それは {{site.data.keyword.cloud_notm}} 内の Cloud Foundry サービスで動作します。 

最新の {{site.data.keyword.cloud}} CLI と、{{site.data.keyword.cloud_notm}} 用のアプリケーションを開発するための推奨されるその他のプラグインおよびツールの両方をインストールする場合は、[{{site.data.keyword.cloud_notm}} CLI の概説](/docs/cli?topic=cloud-cli-getting-started)を参照してください。
{: tip}

## 始める前に
{: #before-download-cli}

32 ビット・バージョン、または {{site.data.keyword.cloud_notm}} 専用環境用の最新バージョン以外の旧バージョンを使用する必要がある場合は、[{{site.data.keyword.cloud_notm}} CLI リリース](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")を参照してください。

## インストーラーを使用したインストール
{: #ibmcloud-cli-installer}

最新のスタンドアロン {{site.data.keyword.cloud_notm}} CLI をインストールするには、以下の手順を実行します。

1. ブラウザーを使用して公式 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub リポジトリーにアクセスし、ご使用の OS のインストーラーを**選択**してダウンロードを開始します。 サポートされるオペレーティング・システムは、macOS X 64 ビット、Windows&trade; 64 ビット、Linux&trade; x86 64 ビット、および Linux&trade; LE 64 ビット (ppc64le) です。

2. インストーラーを次のように実行します。
  * Mac および Windows&trade; の場合、インストーラーを実行します。
  * Linux&trade; の場合、パッケージを解凍し、`install` スクリプトを実行します。

3. {{site.data.keyword.cloud_notm}} にログインします。
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  これで、{{site.data.keyword.cloud_notm}} リソースを管理する準備ができました。 `ibmcloud help` を実行し、コマンド説明を表示します。

  フェデレーテッド ID を使用している場合には、[ワンタイム・パスコードまたは API キーを使用してログイン](/docs/iam?topic=iam-federated_id)します。
  {: tip}

## シェルからのインストール
{: #shell_install}

ご使用の OS 用の最新の CLI をシェルから手動でインストールするには、対象 OS 向けの以下のコマンドを使用します。

* **Mac** の場合、以下のコマンドを端末にコピー・アンド・ペーストして実行します。
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* **Linux&trade;** の場合、以下のコマンドを端末にコピー・アンド・ペーストして実行します。
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* **Windows&trade;** の場合は、以下のコマンドを [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") 端末コンソールにコピー・アンド・ペーストして実行します。
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## カスタム・ディレクトリーへのインストール
{: #install-custom-dir}

インストーラーまたはシェル・スクリプトを使用して {{site.data.keyword.cloud_notm}} CLI をインストールする場合、システム・ディレクトリーにインストールされます。 別のディレクトリーを指定する場合は、以下の手順を実行します。

1. ブラウザーを使用して公式 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub リポジトリーにアクセスし、ご使用のプラットフォームに合ったバイナリーを**選択**してダウンロードを開始します。 サポートされるプラットフォームは、macOS、linux32、linux64、ppc64le、win32、および win64 です。

2. 指定したディレクトリーにパッケージを解凍します。

   以下の解凍済みコンテンツを確認できます。

   Linux&trade; および Mac の場合:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   Windows&trade; の場合:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. `PATH` 環境変数に追加し、shell オートコンプリート機能を有効にします。
  * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` を `PATH` 環境変数に追加します。
  * shell オートコンプリート機能サポート (Mac および Linux&trade; のみ) については、[IBM Cloud CLI の shell オートコンプリート機能の有効化](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)を参照してください。

## {{site.data.keyword.cloud_notm}} CLI の更新
{: #update-ibmcloud-cli}

最新バージョンの CLI を使用する必要があります。 最新バージョンを使用していない場合、以下のコマンドを実行して CLI を更新します。

```
ibmcloud update
```
{: codeblock}

使用している {{site.data.keyword.cloud_notm}} CLI バージョンを判別するには、以下のコマンドを実行します。
```
ibmcloud -v
```
{: codeblock}

現行リリースを実行している場合には、以下の出力が表示されます。
```
更新を確認しています...
更新は不要です。 CLI は既に最新です。
```
{: screen}

新しい {{site.data.keyword.cloud_notm}} CLI リリースについての通知を受け取るには、[{{site.data.keyword.cloud_notm}} CLI リリース・リポジトリー](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") にサブスクライブします。
