---



copyright:

  years: 2015, 2018
lastupdated: "2018-11-15"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Eigenständige {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle installieren
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI stellt die Befehlszeilenschnittstelle für das Verwalten von Ressourcen in {{site.data.keyword.Bluemix_notm}} bereit. Sie können die Cloud Foundry-CLI (`cf`-CLI) weiterhin für die Anmeldung bei {{site.data.keyword.Bluemix_notm}} verwenden, sie kann in {{site.data.keyword.Bluemix_notm}} jedoch nur mit einem Cloud Foundry-Service eingesetzt werden. 

Wenn Sie sowohl die {{site.data.keyword.Bluemix}}-CLI als auch andere empfohlene Plug-ins und Tools für die Anwendungsentwicklung für {{site.data.keyword.Bluemix_notm}} installieren möchten, verwenden Sie die [hier](/docs/cli/index.html) beschriebene Methode.
{: tip}

Führen Sie zum Einrichten der eigenständigen {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle die folgenden Schritte aus:

1. Wählen Sie das Installationsprogramm für Ihr Betriebssystem zum Herunterladen aus.

   Mac OS X 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 Bit (ppc64le): [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Wählen Sie für 32-Bit-Versionen und ältere Versionen die Seite [Alle Versionen](/docs/cli/reference/ibmcloud/all_versions.html) aus, um sie herunterzuladen.

1. Führen Sie das Installationsprogramm aus.
   * Für Mac OS und Windows führen Sie einfach das Installationsprogramm aus.
   * Für Linux müssen Sie das Paket extrahieren und das Script `install` ausführen.

1. Wählen Sie einen API-Endpunkt als Ziel aus und melden Sie sich bei {{site.data.keyword.Bluemix_notm}} an.

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Jetzt können Sie {{site.data.keyword.Bluemix_notm}}-Ressourcen verwalten. Geben Sie `ibmcloud help` ein, damit Beschreibungen der einzelnen Befehle angezeigt werden.

Wenn Sie eine föderierte ID verwenden, folgen Sie den [hier](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) angegebenen Anweisungen zur Anmeldung mit einem einmaligen Kenncode oder einem API-Schlüssel.  
{: tip}

Neben den Installationsprogrammen stehen weitere Optionen für die Installation der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle zur Verfügung:

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

### Schritt 1: Binärpaket auf der Basis des jeweiligen Betriebssystems über die folgenden Links herunterladen.

| Plattform | Downloads | Kontrollsumme |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### Schritt 2: Paket in ein Verzeichnis extrahieren, das Sie angeben.

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
### Schritt 3: Angabe zur Umgebungsvariablen `PATH` hinzufügen und automatische Vervollständigung für die Shell aktivieren.

   * Fügen Sie die Angabe `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` zur Umgebungsvariablen `PATH` hinzu.
   * Informationen zur Unterstützung der automatischen Vervollständigung für die Shell (nur MacOS und Linux) finden Sie in [Automatische Vervollständigung für die Befehlszeilenschnittstelle aktivieren](enable_cli_autocompletion.html).
   
## Eigenständige {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle deinstallieren

Die folgenden Abschnitte enthalten detaillierte Informationen dazu, wie Sie die eigenständige {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle auf bestimmten Plattformen deinstallieren.

### Deinstallation unter Windows

1. Klicken Sie auf die Schaltfläche `Start` und wählen Sie dann die `Systemsteuerung` aus.
2. Klicken Sie im Popup-Fenster auf `Programme und Funktionen - Programm deinstallieren oder ändern`.
3. Suchen Sie in der Pop-up-Liste der Anwendungen die `IBM Cloud-Befehlszeilenschnittstelle`.
4. Klicken Sie mit der rechten Maustaste auf `IBM Cloud-Befehlszeilenschnittstelle` und wählen Sie die Option `Deinstallieren` aus.
5. Das Deinstallationsprogramm wird gestartet. Führen Sie die entsprechenden Anweisungen aus, um die Deinstallation fertigzustellen.

### Deinstallation unter Linux/macOS

#### Vor Version `0.9.0`

1. Öffnen Sie ein Terminal und führen Sie die folgenden Befehle aus:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. Bereinigen Sie die Scripts für automatische Vervollständigung, sofern Sie diese konfiguriert haben. Weitere Informationen finden Sie in [Automatische Vervollständigung für die Befehlszeilenschnittstelle aktivieren](enable_cli_autocompletion.html).

#### Ab Version `0.9.0`

1. Öffnen Sie ein Terminal und führen Sie den folgenden Befehl aus:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Bereinigen Sie die Scripts für automatische Vervollständigung, sofern Sie diese konfiguriert haben. Weitere Informationen finden Sie in [Automatische Vervollständigung für die Befehlszeilenschnittstelle aktivieren](enable_cli_autocompletion.html).


## Links mit weiterführenden Informationen zur {{site.data.keyword.Bluemix_notm}}-CLI

* [Leistungsspektrum der {{site.data.keyword.Bluemix_notm}}-CLI mit Plug-ins erweitern](/docs/cli/reference/ibmcloud/extend_cli.html)
* [{{site.data.keyword.Bluemix_notm}}-CLI-Referenz](/docs/cli/reference/ibmcloud/bx_cli.html)

## Probleme melden und Feedback abgeben
{: #issues}

Verwenden Sie die folgenden Optionen, um Probleme zu melden oder Anforderungen für neue Features abzuschicken:
 * Problemmeldungen in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg) erstellen.
 * Nachrichten im [Slack-Kanal für Entwicklertools (#developer-tools) von IBM Cloud Tech](https://ibm-cloud-tech.slack.com) posten - Teamzugriff [hier](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} anfordern ![Symbol für externen Link](../../../icons/launch-glyph.svg).
