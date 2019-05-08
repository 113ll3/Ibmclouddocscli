---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-29"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

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

1. [Erstellen oder Aktivieren einer App für die Entwicklung](#idt-create).
2. [Codieren, Build erstellen und ausführen](#code-build-run) der App sollte lokal mithilfe von Containern erfolgen.
3. [Bereitstellen](#cli-deploy) der App in {{site.data.keyword.cloud_notm}}.

## Erstellen oder Aktivieren einer App für die Cloudbereitstellung
{: #idt-create}

Es gibt mehrere Möglichkeiten, eine App zu erstellen.
- [App Services-Webkonsole](https://cloud.ibm.com/developer/appservice/dashboard) für generische Web-Apps und Mikroservices
- [Watson-Dashboard](https://cloud.ibm.com/developer/watson/dashboard) für Starter-Apps, die für Watson-basierte Funktionalität aktiviert sind
    - Andere branchen- und technologiebasierte Dashboards sind verfügbar, wenn Sie auf der {{site.data.keyword.cloud_notm}}-Homepage auf die "Hamburger"-Menüschaltfläche klicken. Alle verfolgen denselben Ansatz des Einsatzes von Starter-Kits zum Erstellen neuer Apps.
- Befehl [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle (CLI) zum Erstellen einer neuen App.
- Befehl [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle (CLI) zum raschen Aktivieren der Cloud in einer vorhandenen serverseitigen App.

Für alle oben aufgeführten Erstellungsmethoden ist der Ablauf derselbe. Wählen Sie den Projekttyp, die Implementierungssprache und das zu verwendende App-Muster aus. Sie können auch Services zu Ihrer App hinzufügen (z. B. Authentifizierung oder Persistenz). Schließlich können Sie DevOps-Funktionalität für die App hinzufügen, die eine vollständige Toolchain von der Quellcodeverwaltung bis zur Teamkommunikation liefert. Dies schließt eine Pipeline ein, die bei jedem Commit ausgelöst wird, um Ihre App zu validieren, einen Build zu erstellen und in der {{site.data.keyword.cloud_notm}} bereitzustellen.

![Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-CLI](create_flow.png "Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-CLI") <br> Abbildung 2. Beispielablauf für die Erstellung mit der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle

Die {{site.data.keyword.dev_cli_notm}}-CLI ist nahtlos integriert für eine möglichst benutzerfreundliche Entwicklung. Projekte, die von einer der Webkonsolen aus erstellt wurden, haben eine Schaltfläche **Code herunterladen**, um den generierten Quellcode zur weiteren Entwicklung auf Ihre Workstation herunterzuladen.

### Hilfreiche CLI-Befehle
{: #helpful}

Die folgenden `ibmcloud dev`-CLI-Befehle unterstützen Sie bei der Arbeit mit Ihrem Projekt und den Webkonsolen:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) wird zum Herunterladen eines App-Quellcodes auf Ihre Workstation verwendet. 
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) öffnet den Browser auf der Projektseite der aktuellen App in {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) erstellt eine neue App. 
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) wird zum Löschen der aktuellen App aus dem {{site.data.keyword.cloud_notm}}-Projektbereich verwendet.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) wird zum Aktivieren einer vorhandenen serverseitigen App für die Cloud verwendet. 
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) werden verwendet, um Berechtigungsnachweise abzurufen, die für das Projekt erforderlich sind, um die Verwendung von gebundenen Services zu aktivieren. 
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) listet alle Apps auf, die in der/dem aktuell ausgewählten Organisation/Bereich entweder über die CLI oder die Konsolen erstellt wurden. 

### Untersuchen der Projektstruktur der App
{: #exploring-project}

Projekte, die für die Verwendung mit den Entwicklertools erstellt oder aktiviert werden, haben vorkonfigurierte Einstellungen in der Datei `cli-config.yml`. Die Datei `cli-config.yml` enthält Standardeinträge, die von den `ibmcloud dev`-Befehlen verwendet werden, die mit an die Befehlszeile übergebenen Werten überschrieben werden können. 

### Referenz-Blogs und -Videos
{: #ref1}

- Video: [{{site.data.keyword.cloud_notm}}-Entwicklertools unter Ubuntu Linux&trade; installieren](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
- Blog: [Vorhandene Projekte für IBM Cloud mit der {{site.data.keyword.dev_cli_short}}-CLI aktivieren](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

## Codieren, Build erstellen und ausführen
{: #code-build-run}

Sobald Ihr Projekt erstellt ist, können Sie es für Ihre Zwecke anpassen. Der grundsätzliche Ablauf besteht aus dem Bearbeiten des Quellcodes und dem anschließenden Ausführen von [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build), um die App in einem lokalen Container zu kompilieren, der für die Sprache und Konfiguration Ihrer App spezifisch ist. Abhängig von der Sprache und dem Generator Ihrer Apps können mehrere Container verfügbar sein, die standardmäßig einen Wert annehmen, der die lokale Builderstellung und Ausführung unterstützt. Typischerweise gibt es einen Container 'tools' für Builds und lokales Debugging. Dieser Container enthält zusätzliche Tools und Funktionalitäten, die Sie bei der Entwicklung unterstützen. Es gibt auch einen Container 'run', der die Laufzeit Ihrer App abbildet, sobald sie in der Cloud bereitgestellt wurde - entweder in Cloud Foundry oder in einer Kubernetes-basierten Containerumgebung von IBM. 

Sie können eine beliebige IDE oder einen beliebigen Editor verwenden, um Ihre Anwendung zu codieren. {{site.data.keyword.IBM_notm}} bietet
eine Erweiterung für den Microsoft&trade; VisualStudio Code-Editor (VSCode) an, mit der Sie direkt auf alle IDE-Befehle zugreifen können.

Wenn das Projekt erstellt ist, führen Sie Ihre App mit dem Befehl [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) oder [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) aus. Die App wird innerhalb des entsprechenden Containers ausgeführt. Manche App-Muster unterstützen mehrere externe Container außerhalb Ihrer Apps. Die Apps werden während der Ausführung oder beim Debugging automatisch gestartet und konfiguriert. Außerdem gibt es einen Befehl [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test), der alle zugeordneten Testfälle für die App ausführt.

### Vorgehensweise zur Verwendung lokaler Container
{: #local-containers}

Die {{site.data.keyword.dev_cli_long}}-CLI verwendet zwei Container zum Erstellen und Testen Ihrer Anwendung. Der erste ist der Container 'tools', der die erforderlichen Dienstprogramme zum Erstellen und Testen Ihrer Anwendung enthält. Die Dockerfile für diesen Container ist durch den Parameter [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) definiert. Sie können ihn als Entwicklungscontainer ansehen, denn er enthält die Tools, die üblicherweise für die Entwicklung einer bestimmten Laufzeit verwendet werden.

Der zweite Container ist der Container 'run'. Dieser Container hat ein Format, das beispielsweise für die Verwendung in {{site.data.keyword.cloud}} geeignet ist. In der Folge wird ein Eingangspunkt definiert, der Ihre Anwendung startet. Wenn Ihre Anwendung über die {{site.data.keyword.dev_cli_short}}-CLI ausgeführt werden soll, verwendet sie diesen Container. Die Dockerfile für diesen Container ist durch den Parameter [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) definiert.

### Hilfreiche CLI-Befehle
{: #helpful2}

Die folgenden CLI-Befehle unterstützen Sie bei der Fehlerbehebung für Ihr Projekt:
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

In einer ordnungsgemäßen cloudnativen Umgebung verwenden Sie eine voll funktionsfähige DevOps-Pipeline, um alle Bereitstellungen und eine Vielzahl anderer Funktionen zu verwalten. Während des Erstellens können Sie Ihre App für die Verwendung mit DevOps von IBM Cloud einrichten. Wenn Sie nicht bereit sind, die integrierten DevOps zu verwenden, können Sie [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) entweder manuell ausführen, um Ihre App bereitzustellen, oder Sie können den Befehl `deploy` innerhalb Ihrer eigenen DevOps-Pipeline verwenden.

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
