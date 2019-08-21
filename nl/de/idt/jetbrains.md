---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools für JetBrains-IDEs
{: #ibm-dev-tools-for-jetbrains}

Die Erweiterung der {{site.data.keyword.cloud}}-Entwicklertools für JetBrains-IDEs enthält `IntelliJ`, `WebStorm`, `Android Studio` sowie weitere Komponenten und stellt neue Menüeinträge für den direkten Zugriff auf {{site.data.keyword.dev_cli_notm}}-CLI-Befehle über die IDE bereit. Sie können schnell auf eine Teilmenge der Befehle `ibmcloud dev` für Docker- und Cloud Foundry-Workflows zugreifen (darunter Befehle zum Bereitstellen, Starten und Stoppen von Apps in {{site.data.keyword.cloud_notm}} sowie zum Anzeigen von fernen App-Protokollen und weitere Befehl). Das alles ist möglich, ohne den Kontext des Editors zu verlassen.
{: shortdesc}

![Screenshot der in der WebStorm-IDE ausgeführten IBM Cloud-Entwicklertools.](../images/jetbrains.png "{{site.data.keyword.cloud_notm}}-Entwicklertools - In der WebStorm-IDE ausgeführtes Menübeispiel")

## Abhängigkeiten
{: #jetbrains-dependencies}

Wenn Sie die Erweiterung der {{site.data.keyword.cloud_notm}}-Entwicklertools für JetBrains-basierte IDEs verwenden möchten, muss die [{{site.data.keyword.dev_cli_notm}}-CLI](/docs/cli?topic=cloud-cli-getting-started) auf Ihrem System installiert sein.

## Installation
{: #jetbrains-installation}

Die beste Methode zum Installieren der Erweiterung der {{site.data.keyword.cloud_notm}}-Entwicklertools für JetBrains IDE ist das Aufrufen von [{{site.data.keyword.cloud_notm}} Developer Tools CLI - Helper for Jetbrains IDEs](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und das Ausführen der dort angegebenen Anweisungen.

## Verwendung
{: #jetbrains-usage}

Sie können entweder mit einer vorhandenen serverseitigen App beginnen und diese für die Cloud aktivieren oder die Benutzerschnittstelle von {{site.data.keyword.dev_cli_notm}} verwenden, um eine neue App auf der Basis eines Starter-Kits (`ibmcloud dev create`) zu erstellen. Wenn das Projekt für Ihre App vorhanden ist, öffnen Sie es in Ihrer JetBrains-IDE.

Wählen Sie **Tools** > **IBM Cloud Developer Tools** > **App für {{site.data.keyword.cloud_notm}}** aus, um eine generische, serverseitige App für die Cloud zu aktivieren. Alle erforderlichen Dateien werden geprüft und (bei Bedarf) für die Bereitstellung auf {{site.data.keyword.cloud_notm}} mithilfe einer Cloud Foundry-App oder innerhalb eines Kubernetes-Clusters hinzugefügt.

Entwickeln Sie Ihre cloudnative App mithilfe der Basisaktionen für die Erstellung, Ausführung und Bereitstellung im Menü der {{site.data.keyword.cloud_notm}}-Entwicklertools. Wenn Sie Aktionen ausführen möchten, die nicht im Menü enthalten sind, öffnen Sie einfach die Registerkarte 'terminal' und geben Sie die Befehle manuell ein.
