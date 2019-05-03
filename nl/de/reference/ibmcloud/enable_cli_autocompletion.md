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

# Automatische Vervollständigung für die Shell für die {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle aktivieren (nur Linux/MacOS)
{: #shell-autocomplete}

Ab Version `0.7.0` wird die automatische Vervollständigung von den Installationsprogrammen der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle nicht automatisch aktiviert. Wenn die automatische Vervollständigung unterstützt werden soll, müssen Sie diese Unterstützung manuell aktivieren. Die Scripts für die automatische Vervollständigung sind an den folgenden Speicherpositionen installiert:

* Automatische Vervollständigung für `Bash`: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* Automatische Vervollständigung für `Zsh`: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Automatische Vervollständigung für Linux aktivieren
{: #shell-autocomplete-linux}

* Wenn Sie `Bash` verwenden, fügen Sie
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` zu einer der folgenden Dateien hinzu:

  * Anmeldeshell: `~/.bash_profile`
  * Keine Anmeldeshell: `~/.bash_rc`
  
* Wenn Sie `Zsh` verwenden, fügen Sie
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` in `~/.zshrc` hinzu.

## Unterstützung der automatischen Vervollständigung für MacOS aktivieren
{: #shell-autocomplete-macos}

* Wenn Sie `Bash` verwenden, fügen Sie
`source /usr/local/ibmcloud/autocomplete/bash_autocomplete` in `~/.bash_profile` hinzu.

* Wenn Sie `Zsh` verwenden, fügen Sie
`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete` in `~/.zshrc` hinzu.
