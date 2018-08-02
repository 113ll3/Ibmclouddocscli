---



copyright:

  years: 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 啟用 {{site.data.keyword.Bluemix_notm}} CLI 的 Shell 自動完成（僅限 Linux/MacOS）

從 `0.7.0` 版開始，{{site.data.keyword.Bluemix_notm}} CLI 安裝程式將不會自動啟用 Shell 自動完成。若要具備自動完成支援，您需要手動啟用它。自動完成 Script 安裝在下列位置：

* `Bash` 自動完成：`/usr/local/ibmcloud/bx/bash_autocomplete`
* `Zsh` 自動完成：`/usr/local/ibmcloud/bx/zsh_autocomplete`

## 啟用 Linux 的自動完成

* 如果您使用 `Bash`，請將 

`source /usr/local/ibmcloud/bx/bash_autocomplete` 新增至下列其中一個檔案：

  * 若為登入 Shell：`~/.bash_profile`
  * 若為非登入 Shell：`~/.bash_rc`
  
* 如果您使用 `Zsh`，請將 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` 新增至 `~/.zshrc`。

## 啟用 MacOS 的自動完成支援

* 如果您使用 `Bash`，請將 

`source /usr/local/ibmcloud/bx/bash_autocomplete` 新增至 `~/.bash_profile`。
* 如果您使用 `Zsh`，請將 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` 新增至 `~/.zshrc`。
