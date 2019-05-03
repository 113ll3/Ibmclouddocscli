---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: shell autocompletion, bash, linux shell, macos shell, autocompletion, autocompletion support, shell

subcollection: cloud-cli

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} CLI の shell オートコンプリート機能の有効化 (Linux/MacOS のみ)
{: #shell-autocomplete}

バージョン `0.7.0` 以降、{{site.data.keyword.cloud_notm}} CLI インストーラーは shell オートコンプリート機能を自動的には有効にしません。 オートコンプリート機能がサポートされるようにするには、手動で有効にする必要があります。 オートコンプリート機能スクリプトは、以下の場所にインストールされます。

* `Bash` オートコンプリート機能: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* `Zsh` オートコンプリート機能: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Linux のオートコンプリート機能の有効化
{: #shell-autocomplete-linux}

* `Bash` を使用している場合、`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` を以下のいずれかのファイルに追加します。

  * ログイン shell の場合: `~/.bash_profile`
  * 非ログイン shell の場合: `~/.bash_rc`
  
* `Zsh` を使用している場合、`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` を `~/.zshrc` に追加します。

## MacOS のオートコンプリート機能サポートの有効化
{: #shell-autocomplete-macos}

* `Bash` を使用している場合、`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` を `~/.bash_profile` に追加します。

* `Zsh` を使用している場合、`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` を `~/.zshrc` に追加します。
