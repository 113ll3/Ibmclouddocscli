---

copyright:
  years: 2017, 2019
lastupdated: "2019-05-21"

keywords: cli, ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools für Visual Studio Code
{: #ibm-dev-tools-for-vscode}

Die IBM Cloud Developer Tools-Erweiterung für Visual Studio Code ermöglicht den Zugriff auf Funktionen über die IBM Developer-Befehlszeilenschnittstelle direkt in der Befehlspalette des Visual Studio Code-Editors. Sie können schnell auf eine Teilmenge von `ibmcloud dev`-Befehlen für Docker- und Cloud Foundry-Workflows zugreifen (darunter Befehle zum Bereitstellen, Starten, Stoppen und erneuten Starten von Apps in {{site.data.keyword.cloud}} sowie zum Anzeigen von fernen App-Protokollen und weitere Befehle), ohne den Kontext des Editors zu verlassen.
{:shortdesc}

![Screenshot der IBM Developer-Downloadanzeige für Erweiterungen](vscode.png "Downloadanzeige für Erweiterungen in Visual Studio Code")

## Abhängigkeiten
{: #vscode-dependencies}

Für die IBM Cloud Developer Tools-Erweiterung für Visual Studio Code benötigen Sie die [{{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) und das Plug-in für die {{site.data.keyword.cloud_notm}}-CLI, das auf dem System installiert ist.

## Installation
{: #vscode-installation}

Die einfachste Methode zum Installieren der {{site.data.keyword.dev_cli_notm}}-Erweiterung, ist die Verwendung des Visual Studio Code-Befehls 'quick open':

1. Öffnen Sie die 'quick open'-Befehlspalette im Editor mit den folgenden Tastenkombinationen:

  * **Mac:** `cmd + p`
  * **Windows/Linux:** `strg + p`

2. Geben Sie den Befehl `ext install ibm-developer` ein und drücken Sie die Eingabetaste, um die {{site.data.keyword.dev_cli_notm}}-Erweiterung im Visual Studio Code-Editor zu installieren.

Alternativ können Sie die {{site.data.keyword.dev_cli_notm}}-Erweiterung über das Verwaltungsfenster "Erweiterungen" installieren.

1. Öffnen Sie die Seitenleiste **Erweiterungen** im Visual Studio Code-Editor und suchen Sie dann nach der Zeichenfolge `publisher:IBM Developer`. Die {{site.data.keyword.dev_cli_notm}}-Erweiterung wird in den Suchergebnissen angezeigt.  
2. Klicken Sie auf **Installieren**, um die Installation zu starten.

Sie können auf die [IBM Cloud Developer Tools-Erweiterung auch direkt in Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") zugreifen.

## Verwendung
{: #vscode-usage}

Sie können die Befehle der Erweiterung über die Befehlspalette von Visual Studio Code starten.

Öffnen Sie zunächst die Befehlspalette mithilfe der folgenden Tastenkombinationen:

* **Mac:** `cmd + shift + p`
* **Windows/Linux:** `strg + umschalt + p`

Geben Sie dann den zu startenden Befehl ein oder wählen Sie ihn aus. Sie können 'ibmcloud' in der Befehlspalette eingeben, um eine Liste aller verfügbaren Kommentare anzuzeigen.

### IBM Developer-Erweiterung for Docker-Workflows (Docker-Container) verwenden
{: #usage-docker}

Der Einstieg in die `ibmcloud dev`-Workflows umfasst nur wenige Schritte:
* Erstellen Sie ein Projekt mithilfe einer der beiden folgenden Methoden:
  * Verwenden Sie die [{{site.data.keyword.cloud_notm}}-Webkonsole ](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und laden Sie den generierten Code herunter.
  * Verwenden Sie das CLI-Plug-in von {{site.data.keyword.cloud_notm}} Developer Tools und generieren Sie mit dem Befehl [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create) ein Projekt.
* Öffnen Sie den Projektordner lokal im Visual Studio Code-Editor.
* Verwenden Sie den Befehl `ibmcloud dev build`, um die App in einem Docker-Image zu erstellen.
* Verwenden Sie den Befehl `ibmcloud dev debug`, um die App in einer lokalen Docker-Instanz für die Entwicklung auszuführen.
> Hinweis: Zum Debuggen einer Node.js-Anwendung, die in einem lokalen Docker-Container ausgeführt wird, müssen Sie [eine Debugkonfiguration für den lokalen Container hinzufügen](https://github.com/IBM-Cloud/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link").
* Verwenden Sie den Befehl `ibmcloud dev run`, um die App in einer lokalen Docker-Instanz im Freigabemodus auszuführen.
* Verwenden Sie den Befehl `ibmcloud dev deploy`, um die App in einer Cloud Foundry-Laufzeitumgebung unter {{site.data.keyword.cloud_notm}} bereitzustellen.

### IBM Developer-Erweiterung für Cloud Foundry-Workflows verwenden
{: #usage-cloud-foundry}

Für Benutzer, die zurzeit Apps für Cloud Foundry-Laufzeitumgebungen in {{site.data.keyword.cloud_notm}} bereitstellen, ist auch Unterstützung für `cf`-Operationen verfügbar.

Der Einstieg in Cloud Foundry-Workflows umfasst nur wenige Schritte:
* Erstellen Sie eine neue Cloud Foundry-App.
  * Verwenden Sie die [{{site.data.keyword.cloud_notm}}-Webkonsole ](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und laden Sie den Startercode herunter.
  * Erstellen Sie manuell eine neue Cloud Foundry-App.
* Öffnen Sie den Projektordner lokal im Visual Studio Code-Editor.
* Verwenden Sie `ibmcloud cf apps`, um alle Ihre Apps aufzulisten.
* Verwenden Sie `ibmcloud cf push`, um einen Build Ihrer App per Push-Operation in die Cloud Foundry-Laufzeit zu übertragen.
* Verwenden Sie `ibmcloud cf <start/stop/restage/restart>`, um den Status Ihrer App zu ändern.
* Verwenden Sie `ibmcloud cf logs`, um den Live-Protokolldatenstrom für Ihre App anzuzeigen.
  * Verwenden Sie `ibmcloud cf logs`, um den Protokolldatenstrom zu stoppen.
