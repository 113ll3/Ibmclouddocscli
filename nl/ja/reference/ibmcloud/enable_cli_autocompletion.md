---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI の shell オートコンプリート機能の有効化 (Linux/MacOS のみ)

バージョン `0.7.0` 以降、{{site.data.keyword.Bluemix_notm}} CLI インストーラーは shell オートコンプリート機能を自動的には有効にしません。 オートコンプリート機能がサポートされるようにするには、手動で有効にする必要があります。 オートコンプリート機能スクリプトは、以下の場所にインストールされます。

* `Bash` オートコンプリート機能: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* `Zsh` オートコンプリート機能: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Linux のオートコンプリート機能の有効化

* `Bash` を使用している場合は、次のようにします。 

`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` を以下のいずれかのファイルに追加します。

  * ログイン shell の場合: `~/.bash_profile`
  * 非ログイン shell の場合: `~/.bash_rc`
  
* `Zsh` を使用している場合は、次のようにします。 

`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` を `~/.zshrc` に追加します。

## MacOS のオートコンプリート機能サポートの有効化

* `Bash` を使用している場合は、次のようにします。 

`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` を `~/.bash_profile` に追加します。
* `Zsh` を使用している場合は、次のようにします。 

`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` を `~/.zshrc` に追加します。
