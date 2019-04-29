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

# Habilitación del rellenado automático de shell para la CLI de {{site.data.keyword.cloud_notm}} (solo Linux/MacOS)
{: #shell-autocomplete}

A partir de la versión `0.7.0`, los instaladores de CLI de {{site.data.keyword.cloud_notm}} no habilitarán de manera automática el rellenado automático del shell. Para tener el soporte de rellenado automático, debe habilitarlo manualmente. Los scripts de rellenado automático se instalan en las siguientes ubicaciones:

* Rellenado automático de `Bash`: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* Rellenado automático de `Zsh`: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Habilitación del rellenado automático para Linux
{: #shell-autocomplete-linux}

* Si utiliza `Bash`, añada
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` en uno de los archivos siguientes:

  * Para el shell de inicio de sesión: `~/.bash_profile`
  * Para el shell de no inicio de sesión: `~/.bash_rc`
  
* Si utiliza `Zsh`: añada
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` en `~/.zshrc`.

## Habilitación del soporte de rellenado automático para MacOS
{: #shell-autocomplete-macos}

* Si utiliza `Bash`: añada
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` en `~/.bash_profile`.

* Si utiliza `Zsh`: añada
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` en `~/.zshrc`.
