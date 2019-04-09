---

copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools für JetBrains-IDEs
{: #ibm-dev-tools-for-jetbrains}

Mit der {{site.data.keyword.Bluemix_notm}} Developer Tools-Erweiterung für JetBrains-IDEs, die `IntelliJ`, `WebStorm`, `Android Studio` und mehr umfasst, stehen neue Menüeinträge zur Verfügung, über die von der IDE aus direkter Zugriff auf Befehle der Befehlszeilenschnittstelle von {{site.data.keyword.dev_cli_notm}} besteht. Sie ermöglicht schnellen Zugriff auf ein Subset der `ibmcloud dev`-Befehle sowohl für Docker- als auch für CloudFoundry-Workflows, einschließlich App-Bereitstellung, Starten/Stoppen/Neustarten von Apps in {{site.data.keyword.Bluemix_notm}}, Anzeigen von Protokollen ferner Apps und vieles mehr – ohne den Kontext des Editors dafür verlassen zu müssen.
{:shortdesc}

![Screenshot von IBM Cloud Developer Tools bei der Ausführung in der WebStorm-IDE.](jetbrains.png "Beispiel für das {{site.data.keyword.Bluemix_notm}} Developer Tools-Menü, das in der WebStorm-IDE ausgeführt wird")

## Abhängigkeiten
{: #dependencies}

Damit Sie die {{site.data.keyword.Bluemix_notm}} Developer Tools-Erweiterung für JetBrains-basierte IDEs nutzen können, muss auch die [Befehlszeilenschnittstelle von {{site.data.keyword.dev_cli_notm}}](index.html) auf dem System installiert sein.

## Installation
{: #installation}

Die einfachste Methode, die {{site.data.keyword.Bluemix_notm}} Developer Tools-Erweiterung für die JetBrains-IDE zu installieren, besteht darin, die GitHub-Seite [{{site.data.keyword.Bluemix_notm}} Developer Tools-Befehlszeilenschnittstelle - Helper für JetBrains-IDEs](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) aufzurufen und die Anweisungen auszuführen.

## Verwendung
{: #usage}

Sie können entweder mit einer vorhandenen serverseitigen App beginnen und diese für {{site.data.keyword.Bluemix_notm}} aktivieren oder die Befehlszeilenschnittstelle von {{site.data.keyword.dev_cli_notm}} verwenden, um eine neue App auf der Basis eines Starter-Kits (ibmcloud dev create) zu erstellen. Sobald das Projekt für Ihre App vorhanden ist, öffnen Sie es in der JetBrains-IDE.

Wählen Sie bei einer generischen serverseitigen App 'Tools' > 'IBM Cloud Developer Tools' > 'App für IBM Cloud aktivieren' aus. Damit wird eine Überprüfung auf alle erforderlichen Dateien durchgeführt und alle fehlenden Dateien werden hinzugefügt. Dies ermöglicht es Ihnen, die App lokal zu erstellen und mithilfe einer Cloud Foundry-App oder innerhalb eines Kubernetes-Clusters in {{site.data.keyword.Bluemix_notm}} bereitzustellen.

Entwickeln Sie Ihre cloudnative App mithilfe der Basisaktionen für die Erstellung, Ausführung und Bereitstellung im {{site.data.keyword.Bluemix_notm}} Developer Tools-Menü. Wenn Sie Aktionen ausführen müssen, die nicht im Menü enthalten sind, öffnen Sie die Registerkarte 'Terminal' und geben Sie die gewünschten Befehle manuell ein.
