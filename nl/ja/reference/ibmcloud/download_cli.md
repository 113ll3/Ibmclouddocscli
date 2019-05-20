---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

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

最新の {{site.data.keyword.cloud}} CLI と、{{site.data.keyword.cloud_notm}} 用のアプリケーションを開発するための推奨されるその他のプラグインおよびツールの両方をインストールする場合は、[{{site.data.keyword.cloud_notm}} CLI の概説](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)を参照してください。
{: tip}

## 始める前に
{: #before-download-cli}

32 ビット・バージョン、または {{site.data.keyword.cloud_notm}} 専用環境用の最新バージョン以外の旧バージョンを使用する必要がある場合は、[{{site.data.keyword.cloud_notm}} CLI リリース](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")を参照してください。

## インストーラーを使用したインストール
{: #ibmcloud-cli-installer}

最新のスタンドアロン {{site.data.keyword.cloud_notm}} CLI をインストールするには、以下の手順を実行します。

1. 以下のように、ダウンロードするための、ご使用の OS のインストーラーを選択します。
  *  macOS X 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * Windows 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * Linux x86 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * Linux LE 64 ビット (ppc64le): [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")

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

1. 以下のリンクを使用して、ご使用の OS 用のバイナリー・パッケージをダウンロードします。
  * macOS: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * linux32: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * linux64: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * ppc64le: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * win32: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") /[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")
  * win64: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")

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

   Windows の場合:
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
  * shell オートコンプリート機能サポート (Mac および Linux&trade; のみ) については、[こちらのガイド](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)を参照してください。

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
