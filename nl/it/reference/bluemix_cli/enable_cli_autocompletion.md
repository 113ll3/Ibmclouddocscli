---



copyright:

  years: 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Abilitazione del completamento automatico della shell per la CLI {{site.data.keyword.Bluemix_notm}} (solo Linux/MacOS)

A partire dalla versione ` 0.7.0 `, i programmi di installazione della CLI {{site.data.keyword.Bluemix_notm}} non abiliteranno automaticamente il completamento automatico della shell. Per disporre del supporto di completamento automatico, devi abilitarlo manualmente. Gli script di completamento automatico sono installati nei seguenti percorsi:

* Completamento automatico `Bash`: `/usr/local/ibmcloud/bx/bash_autocomplete`
* Completamento automatico `Zsh`: `/usr/local/ibmcloud/bx/zsh_autocomplete`

## Abilitazione del completamento automatico per Linux

* Se stai utilizzando `Bash`, aggiungi 

`source /usr/local/ibmcloud/bx/bash_autocomplete` in uno dei seguenti file:

  * Per la shell di accesso: `~/.bash_profile`
  * Per la shell non di accesso: `~/.bash_rc`
  
* Se stai utilizzando `Zsh`: aggiungi 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` in `~/.zshrc`.

## Abilitazione del supporto di completamento automatico per MacOS

* Se stai utilizzando `Bash`: aggiungi 

`source /usr/local/ibmcloud/bx/bash_autocomplete` in `~/.bash_profile`.
* Se stai utilizzando `Zsh`: aggiungi 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` in `~/.zshrc`.
