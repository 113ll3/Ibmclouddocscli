---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Enabling shell autocompletion for {{site.data.keyword.Bluemix_notm}} CLI (Linux/MacOS only)

Starting from version `0.7.0`, the {{site.data.keyword.Bluemix_notm}} CLI installers will not enable shell autocompletion automatically. To have the autocompletion support, you need to manually enable it. The autocompletion scripts are installed in the following locations:

* `Bash` autocompletion: `/usr/local/ibmcloud/bx/bash_autocomplete`
* `Zsh` autocompletion: `/usr/local/ibmcloud/bx/zsh_autocomplete`

## Enabling autocompletion for Linux

* If you are using `Bash`, add 

`source /usr/local/ibmcloud/bx/bash_autocomplete` into one of the following files:

  * For Login shell: `~/.bash_profile`
  * For Non-login shell: `~/.bash_rc`
  
* If you are using `Zsh`: add 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` into `~/.zshrc`.

## Enabling autocompletion support for MacOS

* If you are using `Bash`: add 

`source /usr/local/ibmcloud/bx/bash_autocomplete` into `~/.bash_profile`.
* If you are using `Zsh`: add 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` into `~/.zshrc`.
