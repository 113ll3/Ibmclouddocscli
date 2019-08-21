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

# Ativando a conclusão automática do shell para a CLI do {{site.data.keyword.cloud_notm}} (somente Linux/MacOS)
{: #shell-autocomplete}

Iniciando na versão `0.7.0`, os instaladores da CLI do {{site.data.keyword.cloud_notm}} não ativarão a conclusão automática do shell automaticamente. Para ter o suporte de conclusão automática, é necessário ativá-lo manualmente. Os scripts de conclusão automática são instalados nos locais a seguir:

* Conclusão automática ` Bash ` :  ` /usr/local/ibmcloud/autocomplete/bash_autocomplete `
* Conclusão automática ` Zsh ` :  ` /usr/local/ibmcloud/autocomplete/zsh_autocomplete `

## Ativando a conclusão automática para o Linux
{: #shell-autocomplete-linux}

* Se você estiver usando `Bash`, inclua
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` em um dos arquivos a seguir:

  * Para o shell de login:  ` ~/.bash_profile `
  * Para o shell de Não-login:  ` ~/.bash_rc `
  
* Se você estiver usando o `Zsh`: inclua `source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` no `~/.zshrc`.

## Ativando o suporte de conclusão automática para MacOS
{: #shell-autocomplete-macos}

* Se você estiver usando `Bash`: inclua
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` no `~/.bash_profile`.

* Se você estiver usando o `Zsh`: inclua `source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` no `~/.zshrc`.
