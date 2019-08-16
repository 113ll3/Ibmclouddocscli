---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-15"

keywords: cli, shell autocompletion, bash, linux shell, macos shell, autocompletion, autocompletion support, shell

subcollection: cloud-cli

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Enabling shell autocompletion for {{site.data.keyword.cloud_notm}} CLI (Linux and MacOS only)
{: #shell-autocomplete}

Starting from version `0.7.0`, the {{site.data.keyword.cloud_notm}} CLI installers don't enable shell autocompletion automatically. To have the autocompletion support, you need to manually enable it. The autocompletion scripts are installed in the following locations:

* `Bash` autocompletion: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* `Zsh` autocompletion: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Enabling autocompletion for Linux
{: #shell-autocomplete-linux}

* If you're using `Bash`, add 
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` into one of the following files:

  * For Login shell: `~/.bash_profile`
  * For Non-login shell: `~/.bash_rc`
  
* If you're using `Zsh`: add 
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` into `~/.zshrc`.

## Enabling autocompletion support for MacOS
{: #shell-autocomplete-macos}

* If you're using `Bash`: add 
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` into `~/.bash_profile`.

* If you're using `Zsh`: add 
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` into `~/.zshrc`.
