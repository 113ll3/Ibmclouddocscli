---

copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools für Jetbrains-IDEs
{: #ibm-dev-tools-for-jetbrains}

Die IBM Developer-Erweiterung für Jetbrains-IDEs, die IntelliJ, WebStorm, Android Studio und mehr umfasst, stellt neue Menüeinträge bereit, um in der IDE direkt auf IDT-CLI-Befehle zuzugreifen. Sie ermöglicht schnellen Zugriff auf eine Teilmenge der `bx dev`-Befehle sowohl für Docker- als auch für CloudFoundry-Workflows, einschließlich App-Bereitstellung, Starten/Stoppen/Neustarten von Apps in {{site.data.keyword.Bluemix_notm}}, Anzeigen von Protokollen ferner Apps und vieles mehr – ohne den Kontext des Editors dafür verlassen zu müssen.
{:shortdesc}

![Screenshot von IBM Developer Tools in WebStorm-IDE](jetbrains.png "Beispiel für das IDT-Menü in WebStorm-IDE")

## Abhängigkeiten
{: #dependencies}

Um die IBM Developer Tools-Erweiterung für Jetbrains-basierte IDEs nutzen zu können, muss auch die [IBM Cloud Developer Tools-CLI](index.html) auf Ihrem System installiert sein. 

## Installation
{: #installation}

Der einfachste Weg, die IBM Developers Tools-Erweiterung für Jetbrains-IDE zu installieren, ist, zur Seite [IBM Cloud Developer Tools CLI - Helper for Jetbrains IDEs](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) zu wechseln und die Anweisungen zu befolgen. 

## Verwendung
{: #usage}

Sie können entweder mit einer vorhandenen serverseitigen App starten und sie für die IBM Cloud aktivieren oder Sie verwenden die IDT-CLI, um eine neue App aus dem Starter-Kit zu erstellen (bx dev create). Sobald Sie Ihr App-Projekt erstellt haben, öffnen Sie es in Ihrer JetBrains-IDE. 

Wählen Sie bei einer generischen serverseitigen App 'Tools' > 'IBM Cloud Developer Tools' > 'App für IBM Cloud aktivieren' aus. Dies prüft auf alle erforderlichen Dateien und fügt fehlende hinzu, damit Sie die App lokal erstellen sowie mithilfe einer Cloud Foundry-App in IBM Cloud oder innerhalb eines Kubernetes-Clusters bereitstellen können. 

Entwickeln Sie Ihre cloudnative App mithilfe der grundlegenden Erstellen-/Ausführen-/Bereitstellen-Aktionen im IDT-Menü. Wenn Sie Aktionen ausführen müssen, die nicht im Menü enthalten sind, öffnen Sie einfach die Registerkarte 'Terminal' und geben die gewünschten Befehle manuell ein. 

