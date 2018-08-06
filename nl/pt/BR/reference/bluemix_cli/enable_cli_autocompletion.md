---



copyright:

  years: 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Ativando a conclusão automática do shell para a CLI do {{site.data.keyword.Bluemix_notm}} (somente Linux/MacOS)

Iniciando na versão `0.7.0`, os instaladores da CLI do {{site.data.keyword.Bluemix_notm}} não ativarão a conclusão automática do shell automaticamente. Para ter o suporte de conclusão automática, é necessário ativá-lo manualmente. Os scripts de conclusão automática são instalados nos locais a seguir:

* Autoconclusão ` bash ` :  ` /usr/local/ibmcloud/bx/bash_autocomplete `
* Conclusão automática do ` Zsh ` :  ` /usr/local/ibmcloud/bx/zsh_autocomplete `

## Ativando a conclusão automática para o Linux

* Se você estiver usando o  ` Bash `, inclua 

`source /usr/local/ibmcloud/bx/bash_autocomplete` em um dos arquivos a seguir:

  * Para o shell de login:  ` ~/.bash_profile `
  * Para o shell de Não-login:  ` ~/.bash_rc `
  
* Se você estiver usando o  ` Zsh `: inclua 

` source /usr/local/ibmcloud/bx/zsh_autocomplete `  em  ` ~/.zshrc `.

## Ativando o suporte de conclusão automática para MacOS

* Se você estiver usando o  ` Bash `: inclua 

` source /usr/local/ibmcloud/bx/bash_autocomplete `  em  ` ~/.bash_profile `.
* Se você estiver usando o  ` Zsh `: inclua 

` source /usr/local/ibmcloud/bx/zsh_autocomplete `  em  ` ~/.zshrc `.
