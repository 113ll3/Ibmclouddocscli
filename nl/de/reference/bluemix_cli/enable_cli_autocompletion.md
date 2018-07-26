---



copyright:

  years: 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Automatische Vervollständigung für die Shell für die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle aktivieren (nur Linux/MacOS)

Ab Version `0.7.0` wird die automatische Vervollständigung für die Shell nicht automatisch von den Installationsprogrammen der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle aktiviert. Wenn die automatische Vervollständigung unterstützt werden soll, müssen Sie diese Unterstützung manuell aktivieren. Die Scripts für die automatische Vervollständigung sind an den folgenden Speicherpositionen installiert:

* Automatische Vervollständigung für `Bash`: `/usr/local/ibmcloud/bx/bash_autocomplete`
* Automatische Vervollständigung für `Zsh`: `/usr/local/ibmcloud/bx/zsh_autocomplete`

## Automatische Vervollständigung für Linux aktivieren

* Bei der Verwendung von `Bash` 

`source /usr/local/ibmcloud/bx/bash_autocomplete` zu einer der folgenden Dateien hinzufügen:

  * Anmeldeshell: `~/.bash_profile`
  * Keine Anmeldeshell: `~/.bash_rc`
  
* Bei der Verwendung von `Zsh` 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` zu `~/.zshrc` hinzufügen.

## Unterstützung der automatischen Vervollständigung für MacOS aktivieren

* Bei der Verwendung von `Bash` 

`source /usr/local/ibmcloud/bx/bash_autocomplete` zu `~/.bash_profile` hinzufügen.
* Bei der Verwendung von `Zsh` 

`source /usr/local/ibmcloud/bx/zsh_autocomplete` zu `~/.zshrc` hinzufügen.
