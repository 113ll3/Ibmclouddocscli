---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-27"

keywords: developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Apps entwickeln und bereitstellen
{: #developing}

Das Entwickeln von cloudnativen Apps mithilfe der {{site.data.keyword.dev_cli_notm}}-CLI ist ein relativ unkomplizierter Vorgang:

1. [Erstellen oder aktivieren Sie eine App](#idt-create).
2. Verwenden Sie die Aktionen zum lokalen [Codieren, Erstellen und Ausführen](#code-build-run) Ihrer App mithilfe von Containern.
3. Verwenden Sie die Aktion [Bereitstellen](#cli-deploy), um Ihre App in {{site.data.keyword.cloud_notm}} beritzustellen.

## App erstellen oder aktivieren
{: #idt-create}

Es gibt mehrere Möglichkeiten, eine App zu erstellen.
- [App Services-Webkonsole](https://cloud.ibm.com/developer/appservice/dashboard) für generische Web-Apps und Mikroservices
- [Watson-Dashboard](https://cloud.ibm.com/developer/watson/dashboard) für Starter-Apps, die für Watson-basierte Funktionalität aktiviert sind
    - Andere branchen- und technologiebasierte Dashboards sind verfügbar, wenn Sie auf der {{site.data.keyword.cloud_notm}}-Homepage auf die "Hamburger"-Menüschaltfläche klicken. Alle verfolgen denselben Ansatz des Einsatzes von Starter-Kits zum Erstellen neuer Apps.
- Befehl [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle (CLI) zum Erstellen einer neuen App.
- Befehl [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle (CLI) zum raschen Aktivieren der Cloud in einer vorhandenen serverseitigen App.

Für alle oben aufgeführten Erstellungsmethoden ist der Ablauf derselbe. Sie können den Projekttyp, die Implementierungssprache und das zu verwendende App-Muster auswählen. Sie können auch Services zu Ihrer App hinzufügen (z. B. Authentifizierung oder Persistenz). Schließlich können Sie DevOps-Funktionalität für die App aktivieren, die eine vollständige Toolchain von der Quellcodeverwaltung bis zur Teamkommunikation liefert, sowie eine Pipeline, die bei jedem Commit ausgelöst wird, um Ihre App zu validieren, zu erstellen und in der {{site.data.keyword.cloud_notm}} bereitzustellen.

![Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle](create_flow.png "Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle") <br> Abbildung 2. Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle

Die {{site.data.keyword.dev_cli_notm}}-CLI ist nahtlos integriert für eine möglichst benutzerfreundliche Entwicklung. Projekte, die mit einer der Webkonsolen erstellt wurden, haben eine Schaltfläche **Code herunterladen**, um den generierten Quellcode zur weiteren Entwicklung auf Ihre Workstation herunterzuladen.

### Hilfreiche CLI-Befehle
{: #helpful}

Die folgenden CLI-Befehle unterstützen Sie bei der Arbeit mit Ihrem Projekt und den Webkonsolen:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) für das direkte Herunterladen des generierten Quellcodes einer App auf Ihre Workstation.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) für das Öffnen Ihres Browsers auf der Projektseite der aktuellen App in {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) für das Erstellen einer neuen App.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) für das Löschen der aktuellen App aus dem {{site.data.keyword.cloud_notm}}-Projektbereich.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) für das Bereitstellen einer vorhandenen serverseitigen App in der Cloud.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) für das Abrufen von für das Projekt erforderlichen Berechtigungsnachweisen zum Aktivieren der Verwendung von gebundenen Services.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) für das Auflisten aller Apps, die Sie in der/dem aktuell ausgewählten Organisation/Bereich erstellt haben, entweder über die CLI oder die Konsolen.

### Untersuchen der Projektstruktur der App
{: #exploring-project}

Projekte, die für die Verwendung mit dem Tool erstellt oder aktiviert werden, haben vorkonfigurierte Einstellungen in der Datei `cli-config.yml`. Die Datei `cli-config.yml` enthält Standardeinträge, die von den Befehlen des Tools verwendet werden, die durch an die Befehlszeile übergebene Werte überschrieben werden können.

### Referenz-Blogs und -Videos
{: #ref1}

- Video: [{{site.data.keyword.cloud_notm}}-Entwicklertools unter Ubuntu Linux installieren](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
- Blog: [Vorhandene Projekte für IBM Cloud mit der IBM Cloud Developer Tools-CLI aktivieren](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

## Codieren, Erstellen und Ausführen
{: #code-build-run}

Sobald Ihr Projekt erstellt ist, können Sie es für Ihre Zwecke anpassen. Der grundsätzliche Ablauf besteht aus dem Bearbeiten des Quellcodes und dem anschließenden Ausführen von [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build), um die App in einem lokalen Container zu kompilieren, der für die Sprache und Konfiguration Ihrer App spezifisch ist. Abhängig von der Sprache und dem Generator Ihrer Apps können mehrere Container verfügbar sein, die die Erstellung und lokale Ausführung unterstützen. Typischerweise gibt es einen Container 'tools' für Builds und lokales Debugging. Dieser Container enthält zusätzliche Tools und Funktionalitäten, die Sie bei der Entwicklung unterstützen. Es gibt auch einen Container 'run', der die tatsächliche Laufzeit Ihrer App abbildet, sobald sie in der Cloud bereitgestellt wurde - entweder in Cloud Foundry oder in einer Kubernetes-basierten Containerumgebung von IBM.

Sie können eine beliebige IDE oder einen beliebigen Editor verwenden, um Ihre Anwendung zu codieren. Wir bieten
eine Erweiterung für den Microsoft VisualStudio Code-Editor (VSCode) an, mit der Sie direkt auf alle IDE-Befehle zugreifen können.

Wenn das Projekt erstellt ist, führen Sie Ihre App mit dem Befehl [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) oder [`ibmcloud dev debug`](/docs/cli/iddt/commands.html#debug) aus. Dadurch wird die App in dem entsprechenden Container ausgeführt. Manche App-Muster unterstützen mehrere externe Container außerhalb Ihrer Apps. Diese Container werden während der Ausführung oder beim Debugging automatisch gestartet und konfiguriert. Außerdem gibt es einen Befehl [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test), der alle zugeordneten Testfälle für die App ausführt.

### Vorgehensweise zur Verwendung lokaler Container
{: #local-containers}

Die {{site.data.keyword.dev_cli_long}}-CLI verwendet zwei Container zum Erstellen und Testen Ihrer Anwendung. Der erste ist der Container 'tools', der die erforderlichen Dienstprogramme zum Erstellen und Testen Ihrer Anwendung enthält. Die Dockerfile für diesen Container ist durch den Parameter [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) definiert. Sie können ihn als Entwicklungscontainer ansehen, denn er enthält die Tools, die üblicherweise für die Entwicklung einer bestimmten Laufzeit verwendet werden.

Der zweite Container ist der Container 'run'. Dieser Container hat ein Format, das beispielsweise für die Verwendung in {{site.data.keyword.cloud}} geeignet ist. In der Folge wird ein Eingangspunkt definiert, der Ihre Anwendung startet. Wenn Ihre Anwendung über die {{site.data.keyword.dev_cli_short}}-CLI ausgeführt werden soll, verwendet sie diesen Container. Die Dockerfile für diesen Container ist durch den Parameter [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) definiert.

### Hilfreiche CLI-Befehle
{: #helpful2}

Die folgenden CLI-Befehle unterstützen Sie bei der Arbeit mit Ihrem Projekt in den Codierungs-, Erstellungs- und Ausführungsphasen:
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) - Erstellt das Projekt in einem lokalen Container.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) - Führt das Debugging der Anwendung in einem lokalen Container aus.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) - Führt die Anwendung in einem lokalen Container aus.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) - Öffnet eine Shell in einen lokalen Container.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) - Überprüft den Status der von der {{site.data.keyword.dev_cli_notm}}-CLI verwendeten Container.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) - Stoppt einen Container.
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) - Testet Ihre Anwendung in einem lokalen Container.

### Lokale Apps debuggen
{: #ref2}

- [Lokale Apps debuggen](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Bereitstellen
{: #cli-deploy}

In einer ordnungsgemäßen cloudnativen Umgebung verwenden Sie eine voll funktionsfähige DevOps-Pipeline, um alle Bereitstellungen und eine Vielzahl anderer Funktionen zu verwalten. Während des Erstellens können Sie Ihre App für die Verwendung mit DevOps von IBM Cloud einrichten. Wenn Sie nicht bereit sind, die integrierten DevOps zu verwenden, können Sie Ihre App entweder manuell mit [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) bereitstellen oder den Befehl 'deploy' in Ihrer eigenen DevOps-Pipeline verwenden.  

### Hilfreiche CLI-Befehle
{: #helpful3}

Die folgenden CLI-Befehle unterstützen Sie bei der Arbeit mit Ihrem Projekt während des Bereitstellungsprozesses:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) - Öffnet die {{site.data.keyword.cloud_notm}}-Konsole für ein Projekt.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) - Stellt eine Anwendung in {{site.data.keyword.cloud_notm}} bereit.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) - Zeigt die URL Ihres Projekts an.

### Referenz-Blogs und -Videos
{: #ref3}

- Blog: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
- Blog: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
