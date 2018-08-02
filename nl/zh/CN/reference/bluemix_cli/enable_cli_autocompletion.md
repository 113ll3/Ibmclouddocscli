---



copyright:

  years: 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 启用 {{site.data.keyword.Bluemix_notm}} CLI 的 shell 自动完成（仅限 Linux/MacOS）

从 V`0.7.0` 开始，{{site.data.keyword.Bluemix_notm}} CLI 安装程序不会自动启用 shell 自动完成。要获得自动完成支持，您需要手动启用此项。自动完成脚本会安装在以下位置：

* `Bash` 自动完成：`/usr/local/ibmcloud/bx/bash_autocomplete`
* `Zsh` 自动完成：`/usr/local/ibmcloud/bx/zsh_autocomplete`

## 对 Linux 启用自动完成

* 如果使用的是 `Bash`，请将 

`source /usr/local/ibmcloud/bx/bash_autocomplete` 添加到以下其中一个文件中：

  * 对于登录 shell 程序：`~/.bash_profile`
  * 对于非登录 shell 程序：`~/.bash_rc`
  
* 如果使用的是 `Zsh`： 

将 `source /usr/local/ibmcloud/bx/zsh_autocomplete` 添加到 `~/.zshrc`。

## 对 MacOS 启用自动完成

* 如果使用的是 `Bash`： 

将 `source /usr/local/ibmcloud/bx/bash_autocomplete` 添加到 `~/.bash_profile`。
* 如果使用的是 `Zsh`： 

将 `source /usr/local/ibmcloud/bx/zsh_autocomplete` 添加到 `~/.zshrc`。
