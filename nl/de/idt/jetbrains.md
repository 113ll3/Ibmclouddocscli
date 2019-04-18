---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-27"

keywords: ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools für JetBrains-IDEs
{: #ibm-dev-tools-for-jetbrains}

Die Erweiterung der {{site.data.keyword.cloud}}-Entwicklertools für Jetbrains-IDEs enthält `IntelliJ`, `WebStorm`, `Android Studio` sowie weitere Komponenten und stellt neue Menüeinträge für den direkten Zugriff auf {{site.data.keyword.dev_cli_notm}}-CLI-Befehle über die IDE bereit. Sie können schnell auf eine Teilmenge von `ibmcloud dev`-Befehlen für Docker- und Cloud Foundry-Workflows zugreifen (darunter Befehle zum Bereitstellen, Starten, Stoppen und erneuten Starten von Apps in {{site.data.keyword.cloud_notm}} sowie zum Anzeigen von fernen App-Protokollen und weitere Befehle), ohne den Kontext des Editors zu verlassen.
{:shortdesc}

![Screenshot der Ausführung von IBM Cloud Developer Tools in WebStorm IDE](jetbrains.png "Beispielmenü für die {{site.data.keyword.cloud_notm}}-Entwicklertools in WebStorm IDE")


## Abhängigkeiten
{: #jetbrains-dependencies}

Wenn Sie die Erweiterung der {{site.data.keyword.cloud_notm}}-Entwicklertools für Jetbrains-basierte IDEs verwenden möchten, muss die [{{site.data.keyword.dev_cli_notm}}-CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) auf Ihrem System installiert sein.

## Installation
{: #jetbrains-installation}

Die beste Methode zum Installieren der Erweiterung der {{site.data.keyword.cloud_notm}}-Entwicklertools für Jetbrains IDE ist das Aufrufen der Seite [{{site.data.keyword.cloud_notm}} Developer Tools CLI - Helper for Jetbrains IDEs](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und das Ausführen der dort angegebenen Anweisungen.

## Verwendung
{: #jetbrains-usage}

Sie können entweder mit einer vorhandenen serverseitigen App beginnen und diese für {{site.data.keyword.cloud_notm}} aktivieren oder die Befehlszeilenschnittstelle von {{site.data.keyword.dev_cli_notm}} verwenden, um eine neue App auf der Basis eines Starter-Kits (ibmcloud dev create) zu erstellen. Wenn das Projekt für Ihre App vorhanden ist, öffnen Sie es in Ihrer JetBrains-IDE.

Wählen Sie bei einer generischen serverseitigen App 'Tools > IBM Cloud Developer Tools > App für {{site.data.keyword.cloud_notm}} aktivieren' aus. Diese Option sucht nach allen erforderlichen Dateien, fügt alle fehlenden Dateien lokal in der App hinzu und stellt sie in {{site.data.keyword.cloud_notm}} mithilfe einer Cloud Foundry-App oder in einem Kubernetes-Cluster bereit.

Entwickeln Sie Ihre cloudnative App mithilfe der Basisaktionen für die Erstellung, Ausführung und Bereitstellung im Menü der {{site.data.keyword.cloud_notm}}-Entwicklertools. Wenn Sie Aktionen ausführen möchten, die nicht im Menü enthalten sind, öffnen Sie einfach die Registerkarte 'Terminal' und geben Sie die gewünschten Befehle manuell ein.
