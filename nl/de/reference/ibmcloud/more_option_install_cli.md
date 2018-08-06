---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Weitere Optionen zum Installieren der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle
{: #more_options_install}

Zusätzlich zu den [Installationsprogrammen](install_use_cli.html#getting_started) stehen weitere Optionen für die Installation der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle zur Verfügung:

* Installation über eine Shell
* Download des Binärpakets und Installation in einem benutzerdefinierten Verzeichnis

## Installation über eine Shell
{: #shell_install}

### MacOS

Kopieren Sie den folgenden Befehl und fügen Sie ihn auf einem Terminal Ihres Mac OS ein und führen Sie ihn aus:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Kopieren Sie den folgenden Befehl und fügen Sie ihn auf einem Terminal Ihres Linux-Betriebssystems ein und führen Sie ihn aus:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Kopieren Sie den folgenden Befehl und fügen Sie ihn in eine [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window}-Terminalkonsole ein und führen Sie ihn aus:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Installation in einem benutzerdefinierten Verzeichnis

Wenn für die Installation der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle Installationsprogramme oder ein Shell-Script verwendet wird, werden die Binärdateien in den Systemverzeichnissen gespeichert. Wenn Sie ein anderes Verzeichnis angeben möchten, führen Sie die folgenden Schritte aus.

1. Die Binärdateien herunterladen.

   Verwenden Sie die folgenden Links zum Herunterladen des Binärpakets für das jeweilige Betriebssystem.

   | Plattform | Downloads | Kontrollsumme |
   |----|----| --- |
   | macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. Paket in ein Verzeichnis extrahieren, das Sie angeben.

   Nach dem Extrahieren des Pakets sieht der Inhalt wie folgt aus:

   Für Linux und MacOS

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   Für Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

1. Angabe zur Umgebungsvariablen `PATH` hinzufügen und automatische Vervollständigung für die Shell aktivieren.

   * Fügen Sie die Angabe `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` zur Umgebungsvariablen `PATH` hinzu.
   * Informationen zur Unterstützung der automatischen Vervollständigung für die Shell (nur MacOS und Linux) finden Sie in [diesem Handbuch](enable_cli_autocompletion.html).

