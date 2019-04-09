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

# Activation de l'exécution automatique de shell pour l'interface CLI {{site.data.keyword.cloud_notm}} (Linux/MacOS uniquement)
{: #shell-autocomplete}

Depuis la version `0.7.0`, les programmes d'installation de l'interface CLI {{site.data.keyword.cloud_notm}} n'activent pas automatiquement l'exécution automatique de shell. Pour pouvoir bénéficier de cette fonction, vous devez l'activer manuellement. Les scripts d'exécution automatique sont installés aux emplacements suivants :

* Exécution automatique `Bash` : `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* Exécution automatique `Zsh` : `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Activation de l'exécution automatique pour Linux
{: #shell-autocomplete-linux}

* Si vous utilisez `Bash`, ajoutez
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` dans un des fichiers suivants. 

  * Pour un shell de connexion : `~/.bash_profile`
  * Pour les autres types de shell : `~/.bash_rc`
  
* Si vous utilisez `Zsh`, ajoutez
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` dans `~/.zshrc`.

## Activation du support d'exécution automatique pour MacOS
{: #shell-autocomplete-macos}

* Si vous utilisez `Bash`, ajoutez
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` dans `~/.bash_profile`.

* Si vous utilisez `Zsh`, ajoutez
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` dans `~/.zshrc`.
