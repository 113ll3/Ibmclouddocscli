---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI をインストールするためのその他のオプション
{: #more_options_install}

[インストーラー](install_use_cli.html#getting_started)以外にも、{{site.data.keyword.Bluemix_notm}} CLI をインストールするためのオプションがあります。

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

1. バイナリーをダウンロードします。

   以下のリンクを使用して、使用している OS に基づいたバイナリー・パッケージをダウンロードします。

   | プラットフォーム | ダウンロード | チェックサム |
   |----|----| --- |
   | macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. 指定したディレクトリーにパッケージを解凍します。

   パッケージを解凍した後、内容は次のようになります。

   Linux および MacOS

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
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
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

1. `PATH` 環境変数に追加し、shell オートコンプリート機能を有効にします。

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` を `PATH` 環境変数に追加します。
   * shell オートコンプリート機能サポート (MacOS および Linux のみ) については、[このガイド](enable_cli_autocompletion.html)を参照してください。

