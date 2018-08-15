---



copyright:

  years: 2015, 2018
lastupdated: "2018-08-09"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI のインストール
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI は、{{site.data.keyword.Bluemix_notm}} でアプリケーション、コンテナー、インフラストラクチャー、サービス、およびその他のリソースを管理するためのコマンド・ライン・インターフェースを提供します。

{{site.data.keyword.Bluemix}} CLI と、{{site.data.keyword.Bluemix_notm}} 用のアプリケーションを開発するための推奨されるその他のプラグインおよびツールの両方をインストールする場合は、[ここ](/docs/cli/index.html)で説明されている方法に従ってください。
{: tip}

スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI をインストールするには、次の手順を実行します。

1. ダウンロードするための、ご使用の OS のインストーラーを選択します。

   Mac OS X 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 ビット (ppc64le): [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

1. インストーラーを実行します。
   * macOS および Windows の場合は、単純にインストーラーを実行します。
   * Linux の場合は、パッケージを解凍し、`install_bluemix_cli` スクリプトを実行します。

1. API エンドポイントをターゲットに指定し、{{site.data.keyword.Bluemix_notm}} にログインします。

   ```
   ibmcloud login
   ```
   {: codeblock}
   
これで、{{site.data.keyword.Bluemix_notm}} リソースを管理する準備ができました。 コマンド説明を表示するには、`ibmcloud help` と入力します。

フェデレーテッド ID を使用する場合は、[ここ](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)で説明する手順に従って、ワンタイム・パスコードまたは API キーを使用してログインします。  
{: tip}

インストーラー以外にも、{{site.data.keyword.Bluemix_notm}} CLI をインストールするためのオプションがあります。

* shell からのインストール
* バイナリー・パッケージをダウンロードしてカスタム・ディレクトリーへインストール

## shell からのインストール
{: #shell_install}

### MacOS

以下のコマンドを Mac OS の端末にコピー・アンド・ペーストし、実行します。

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

以下のコマンドを Linux OS の端末にコピー・アンド・ペーストし、実行します。

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

以下のコマンドを [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 端末コンソールにコピー・アンド・ペーストし、実行します。

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## カスタム・ディレクトリーへのインストール

インストーラーまたは shell スクリプトを使用して {{site.data.keyword.Bluemix_notm}} CLI をインストールすると、バイナリーがシステム・ディレクトリーに移動します。 別のディレクトリーを指定する場合は、以下の手順を実行します。

### ステップ 1: 使用している OS に基づいたバイナリー・パッケージを、以下のリンクを使用してダウンロードします。

| プラットフォーム | ダウンロード | チェックサム |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### ステップ 2: 指定したディレクトリーにパッケージを解凍します。

   パッケージを解凍した後、内容は次のようになります。

   Linux および MacOS

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
   {: codeblock}

   Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}
### ステップ 3: `PATH` 環境変数に追加し、shell オートコンプリート機能を有効にします。

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` を `PATH` 環境変数に追加します。
   * shell オートコンプリート機能サポート (MacOS および Linux のみ) については、[このガイド](enable_cli_autocompletion.html)を参照してください。
   
## スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI のアンインストール

以下のセクションでは、特定のプラットフォームでスタンドアロンの {{site.data.keyword.Bluemix_notm}} CLI をアンインストールする方法を詳しく説明します。

### Windows でのアンインストール

1. `「スタート」`ボタンをクリックし、`「コントロール パネル」`を選択します。
2. ポップアップ・ウィンドウで、`「プログラムのアンインストール」`をクリックします。
3. ポップアップしたアプリケーション・リストで、`「IBM Cloud コマンド・ライン・インターフェース」`を見つけます。
4. `「IBM Cloud コマンド・ライン・インターフェース」`を右クリックして、`「アンインストール」`を選択します。
5. アンインストーラーが起動します。 指示に従ってアンインストールを完了します。

### Linux/macOS でのアンインストール

#### バージョン `0.9.0` より前

1. 端末を開き、以下のコマンドを実行します。
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. オートコンプリート機能スクリプトを構成している場合は、それをクリーンアップします。 詳しくは、[CLI オートコンプリート機能の有効化](enable_cli_autocompletion.html)を参照してください。

#### バージョン `0.9.0` 以降

1. 端末を開き、次のコマンドを実行します。
  * `/usr/local/ibmcloud/uninstall`
2. オートコンプリート機能スクリプトを構成している場合は、それをクリーンアップします。 詳しくは、[CLI オートコンプリート機能の有効化](enable_cli_autocompletion.html)を参照してください。


## {{site.data.keyword.Bluemix_notm}} CLI をさらに探索するためのその他のリンク

* [プラグインを使用した {{site.data.keyword.Bluemix_notm}} CLI 機能の拡張](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [一般的な {{site.data.keyword.Bluemix_notm}} CLI コマンド使用法](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [一般的な {{site.data.keyword.Bluemix_notm}} (ibmcloud sl) コマンド使用法](/docs/cli/reference/softlayer/index.html)

## 問題の報告とフィードバックの送信
{: #issues}

問題を報告したり新しいフィーチャーの要求を送信したりするには、以下のオプションを使用してください。
 * [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) で問題を作成する。
 * [IBM Cloud Tech の Slack - #developer-tools チャネル](https://ibm-cloud-tech.slack.com)にメッセージを残す。‐ [ここ](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) でチーム・アクセスを要求。
