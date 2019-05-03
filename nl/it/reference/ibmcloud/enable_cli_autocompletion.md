---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, shell autocompletion, bash, linux shell, macos shell, autocompletion, autocompletion support, shell

subcollection: cloud-cli

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.cloud_notm}} (solo Linux/MacOS)
{: #shell-autocomplete}

A partire dalla versione `0.7.0`, i programmi di installazione della CLI {{site.data.keyword.cloud_notm}} non abiliteranno il completamento automatico della shell in modo automatico. Per disporre del supporto di completamento automatico, devi abilitarlo manualmente. Gli script di completamento automatico sono installati nelle seguenti posizioni:

* Completamento automatico `Bash`: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* Completamento automatico `Zsh`: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Abilitazione del completamento automatico per Linux
{: #shell-autocomplete-linux}

* Se stai utilizzando `Bash`, aggiungi
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` in uno dei seguenti file:

  * Per la shell di accesso: `~/.bash_profile`
  * Per la shell non di accesso: `~/.bash_rc`
  
* Se stai utilizzando `Zsh`: aggiungi
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` in `~/.zshrc`.

## Abilitazione del supporto di completamento automatico per MacOS
{: #shell-autocomplete-macos}

* Se stai utilizzando `Bash`: aggiungi
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` in `~/.bash_profile`.

* Se stai utilizzando `Zsh`: aggiungi
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` in `~/.zshrc`.
