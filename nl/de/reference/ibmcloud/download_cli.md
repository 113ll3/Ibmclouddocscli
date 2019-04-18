---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI stellt die Befehlszeilenschnittstelle für das Verwalten von Ressourcen in {{site.data.keyword.cloud_notm}} bereit. Sie können die Befehlszeilenschnittstelle `cf` weiter für die Anmeldung bei {{site.data.keyword.cloud_notm}} verwenden. In {{site.data.keyword.cloud_notm}} kann Sie jedoch nur mit einem Cloud Founry-Service eingesetzt werden. 

Wenn Sie sowohl die {{site.data.keyword.cloud}}-CLI als auch andere empfohlene Plug-ins und Tools für die Entwicklung von Anwendungen für {{site.data.keyword.cloud_notm}} installieren möchten, informieren Sie sich unter [Einführung in die {{site.data.keyword.cloud_notm}}-CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Führen Sie zum Einrichten der eigenständigen {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle die folgenden Schritte aus:

1. Wählen Sie das jeweilige Installationsprogramm für Ihr Betriebssystem zum Herunterladen aus.

   Mac OS X 64 Bit: [Installationsprogramm](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 Bit: [Installationsprogramm](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 Bit: [Installationsprogramm](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 Bit (ppc64le): [Installationsprogramm](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Rufen Sie für 32-Bit-Versionen und ältere Versionen zum Herunterladen die Seite [Releases der {{site.data.keyword.cloud_notm}}-CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) auf.

2. Führen Sie das Installationsprogramm aus.
   * Führen Sie für MacOS und Windows&trade; einfach das Installationsprogramm aus.
   * Für Linux&trade; müssen Sie das Paket extrahieren und das Script `install` ausführen.

3. Wählen Sie einen API-Endpunkt als Ziel aus und melden Sie sich bei {{site.data.keyword.cloud_notm}} an:
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Jetzt können Sie {{site.data.keyword.cloud_notm}}-Ressourcen verwalten. Geben Sie `ibmcloud help` ein, damit Beschreibungen der einzelnen Befehle angezeigt werden.

Wenn Sie eine föderierte ID verwenden, folgen Sie den [hier](/docs/iam?topic=iam-federated_id#federated_id) angegebenen Anweisungen zum Anmelden mit einem einmaligen Kenncode oder einem API-Schlüssel.  
{: tip}

Zusätzlich zu den Installationsprogrammen stehen weitere Optionen für die Installation der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle zur Verfügung:

* Installation über eine Shell
* Download des Binärpakets und Installation in einem benutzerdefinierten Verzeichnis

## Installation über eine Shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Kopieren Sie den folgenden Befehl und fügen Sie ihn auf einem Terminal Ihres Mac OS ein und führen Sie ihn aus:
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Kopieren Sie den folgenden Befehl, fügen Sie ihn an einem Terminal Ihres Linux&trade;-Betriebssystems ein und führen Sie ihn aus:
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Kopieren Sie den folgenden Befehl, fügen Sie ihn in einer [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window}-Terminalkonsole ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") ein und führen Sie ihn aus:
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Installation in einem benutzerdefinierten Verzeichnis
{: #install-custom-dir}

Wenn Installationsprogramme oder ein Shell-Script für die Installation der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle verwendet werden, werden die Binärdateien in den Systemverzeichnissen gespeichert. Wenn Sie ein anderes Verzeichnis angeben möchten, führen Sie die folgenden Schritte aus.

### Schritt 1: Binärpaket auf der Basis des jeweiligen Betriebssystems über die folgenden Links herunterladen.
{: #step1-custom-dir}

| Plattform | Downloads | Kontrollsumme |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Schritt 2: Paket in ein Verzeichnis extrahieren, das Sie angeben.
{: #step2-custom-dir}

   Nach dem Extrahieren des Pakets sieht der Inhalt wie folgt aus:

   Für Linux&trade; und MacOS:

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
{: #step3-custom-dir}

   * Fügen Sie die Angabe `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` zur Umgebungsvariablen `PATH` hinzu.
   * Informationen zur Unterstützung der automatischen Vervollständigung für die Shell (nur MacOS und Linux&trade;) finden Sie in [diesem Handbuch](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle deinstallieren
{: #uninstall-ibmcloud-cli}

Die folgenden Abschnitte enthalten detaillierte Informationen dazu, wie Sie die eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle auf bestimmten Plattformen deinstallieren.

### Deinstallation unter Windows
{: #uninstall-cli-windows}

1. Klicken Sie auf die Schaltfläche `Start` und wählen Sie dann die `Systemsteuerung` aus.
2. Klicken Sie im Popup-Fenster auf `Programme und Funktionen - Programm deinstallieren oder ändern`.
3. Suchen Sie in der Popup-Liste der Anwendungen die `IBM Cloud-Befehlszeilenschnittstelle`.
4. Klicken Sie mit der rechten Maustaste auf die `IBM Cloud-Befehlszeilenschnittstelle` und wählen Sie `Deinstallieren` aus.
5. Das Deinstallationsprogramm wird gestartet. Führen Sie die entsprechenden Anweisungen aus, um die Deinstallation fertigzustellen.

### Deinstallation unter Linux und MacOS
{: #uninstall-cli-linux-macos}

#### Versionen vor `0.9.0`

1. Öffnen Sie ein Terminal und führen Sie die folgenden Befehle aus:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Bereinigen Sie die Scripts für automatische Vervollständigung, sofern Sie diese konfiguriert haben. Ausführliche Informationen finden Sie in [Automatische Vervollständigung für die Shell der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle aktivieren (nur Linux und MacOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Ab Version `0.9.0`

1. Öffnen Sie ein Terminal und führen Sie den folgenden Befehl aus:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Bereinigen Sie alle angepassten Scripts für automatische Vervollständigung. Ausführliche Informationen finden Sie in [Automatische Vervollständigung für die Shell der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle aktivieren (nur Linux und MacOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Links mit weiterführenden Informationen zur {{site.data.keyword.cloud_notm}}-CLI
{: #other-cli-links}

* [{{site.data.keyword.cloud_notm}}-CLI mit Plug-ins erweitern](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [Allgemeine CLI-Befehle (ibmcloud)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Probleme melden und Feedback abgeben
{: #issues}

Verwenden Sie die folgenden Optionen, um Probleme zu melden oder Anforderungen für neue Features abzuschicken:
* Problemmeldungen in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
* Nachrichten im [{{site.data.keyword.cloud_notm}}-Tech-Slack-Kanal für Entwicklertools (#developer-tools)](https://ibm-cloud-tech.slack.com){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") posten - Teamzugriff [hier](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") anfordern.
