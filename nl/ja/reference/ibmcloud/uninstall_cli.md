---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI のアンインストール

特定のプラットフォームで {{site.data.keyword.Bluemix_notm}} をアンインストールする手順については、以下のセクションを参照してください。

## Windows でのアンインストール

* `「スタート」`ボタンをクリックし、`「コントロール パネル」`を選択します。
* ポップアップ・ウィンドウで、`「プログラムのアンインストール」`をクリックします。
* ポップアップしたアプリケーション・リストで、`「IBM Cloud コマンド・ライン・インターフェース」`を見つけます。
* `「IBM Cloud コマンド・ライン・インターフェース」`を右クリックして、`「アンインストール」`を選択します。
* アンインストーラーが起動します。指示に従ってアンインストールを完了します。

## Linux/macOS でのアンインストール

### バージョン `0.9.0` より前

* 端末を開き、以下のコマンドを実行します。
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* オートコンプリート機能スクリプトを構成している場合は、それをクリーンアップします。詳しくは、[CLI オートコンプリート機能の有効化](enable_cli_autocompletion.html)を参照してください。

### バージョン `0.9.0` 以降

* 端末を開き、次のコマンドを実行します。
  * `/usr/local/ibmcloud/uninstall`
* オートコンプリート機能スクリプトを構成している場合は、それをクリーンアップします。詳しくは、[CLI オートコンプリート機能の有効化](enable_cli_autocompletion.html)を参照してください。
