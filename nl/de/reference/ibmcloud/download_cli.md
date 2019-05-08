---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}}-CLI stellt die Befehlszeilenschnittstelle für das Verwalten von Ressourcen in {{site.data.keyword.cloud_notm}} bereit. Sie können die Befehlszeilenschnittstelle `cf` weiter für die Anmeldung bei {{site.data.keyword.cloud_notm}} verwenden. In {{site.data.keyword.cloud_notm}} kann Sie jedoch nur mit einem Cloud Foundry-Service eingesetzt werden. 

Wenn Sie sowohl die aktuellste {{site.data.keyword.cloud}}-CLI als auch andere empfohlene Plug-ins und Tools für die Entwicklung von Anwendungen für {{site.data.keyword.cloud_notm}} installieren möchten, informieren Sie sich unter [Einführung in die {{site.data.keyword.cloud_notm}}-CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

## Vorbereitende Schritte
{: #before-download-cli}

Wenn Sie eine 32-Bit-Version oder eine andere als die aktuelle Version für {{site.data.keyword.cloud_notm}}-dedizierte Umgebungen verwenden müssen, informieren Sie sich in den [{{site.data.keyword.cloud_notm}}-CLI-Releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

## Installation mit einem Installationsprogramm
{: #ibmcloud-cli-installer}

Führen Sie zum Einrichten der aktuellsten, eigenständigen {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle die folgenden Schritte aus:

1. Wählen Sie das jeweilige Installationsprogramm für Ihr Betriebssystem zum Herunterladen aus:
  *  MacOS X 64 Bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * Windows 64 Bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * Linux x86 64 Bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * Linux LE 64-Bit (ppc64le): [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")

2. Führen Sie das Installationsprogramm aus.
  * Führen Sie für Mac und Windows&trade; einfach das Installationsprogramm aus.
  * Für Linux&trade; müssen Sie das Paket extrahieren und das Script `install` ausführen.

3. Melden Sie sich bei {{site.data.keyword.cloud_notm}} an:
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Jetzt können Sie {{site.data.keyword.cloud_notm}}-Ressourcen verwalten. Geben Sie `ibmcloud help` ein, damit Beschreibungen der einzelnen Befehle angezeigt werden.

  Wenn Sie eine föderierte ID verwenden, [melden Sie sich mit einem einmaligen Kenncode oder einem API-Schlüssel an]((/docs/iam?topic=iam-federated_id#federated_id). {: tip}

## Installation über die Shell
{: #shell_install}

Wenn Sie die neueste CLI für Ihr Betriebssystem manuell aus der Shell installieren möchten, verwenden Sie den folgenden Befehl für Ihr Betriebssystem:

* Für **Mac** kopieren Sie den folgenden Befehl, fügen ihn in einem Terminal ein und führen ihn aus. 
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* Für **Linux&trade;** kopieren Sie den folgenden Befehl, fügen ihn in einem Terminal ein und führen ihn aus: 
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* Für **Windows&trade;** kopieren Sie den folgenden Befehl, geben ihn in die Terminalkonsole einer [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") ein und führen ihn aus: 
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Installation in einem benutzerdefinierten Verzeichnis
{: #install-custom-dir}

Wenn Sie Installationsprogramme oder ein Shell-Script für die Installation der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle verwenden, wird sie in den Systemverzeichnissen gespeichert. Wenn Sie ein anderes Verzeichnis angeben möchten, führen Sie die folgenden Schritte aus.

1. Binärpaket für das jeweilige Betriebssystem über die folgenden Links herunterladen:
  * MacOS: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * linux32: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * linux64: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * ppc64le: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * win32: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
  * win64: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")

2. Paket in ein Verzeichnis extrahieren, das Sie angeben. 

   Sie können den folgenden extrahierten Inhalt sehen:

   Für Linux&trade; und Mac:
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
   {: screen}

   Für Windows:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Angabe zur Umgebungsvariablen `PATH` hinzufügen und automatische Vervollständigung für die Shell aktivieren. 
  * Fügen Sie die Angabe `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` zur Umgebungsvariablen `PATH` hinzu.
  * Informationen zur Unterstützung der automatischen Vervollständigung für die Shell (nur Mac und Linux&trade;) finden Sie in [diesem Handbuch](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Aktualisierung der {{site.data.keyword.cloud_notm}}-CLI
{: #update-ibmcloud-cli}

Sie müssen die neueste Version der Befehlszeilenschnittstelle verwenden. Wenn Sie die neueste Version nicht verwenden, führen Sie den folgenden Befehl aus, um die Befehlszeilenschnittstelle zu aktualisieren:

```
ibmcloud update
```
{: codeblock}

Führen Sie folgenden Befehl, um Ihre {{site.data.keyword.cloud_notm}}-CLI-Version zu ermitteln:
```
ibmcloud -v
```
{: codeblock}

Wenn Sie das aktuelle Release ausführen, wird die folgende Ausgabe angezeigt:
```
Suchen nach Aktualisierungen...
Keine Aktualisierung erforderlich. Ihre CLI ist bereits auf dem aktuellen Stand.
```
{: screen}

Um über neue {{site.data.keyword.cloud_notm}}-CLI-Releases stets auf dem Laufenden zu sein, abonnieren Sie das [Release-Repository der {{site.data.keyword.cloud_notm}}-CLI](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
