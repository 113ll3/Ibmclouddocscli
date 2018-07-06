---
copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Fehlerbehebung für IBM Cloud Developer Tools
{: #ts}

Dokumentiert sind bekannte Probleme mit der {{site.data.keyword.dev_cli_notm}} und zugehörige Fehlerumgehungen.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Bekannte Probleme
{: #knownissues}

In den folgenden Abschnitten werden bekannte Probleme und mögliche Lösungen beschrieben.


### 'Hostname is taken'-Fehler beim Erstellen eines Projekts mit einem nicht mobilen Muster
{: #hostname}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie die {{site.data.keyword.dev_cli_short}} verwenden, um ein Projekt aus den Web-App-, BFF- oder Mikroservice-Mustern zu erstellen:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Ursache
{: #hostname-cause}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.


#### Lösung
{: #hostname-resolution}

Melden Sie sich erneut an.

```
ibmcloud login
```
{: codeblock}


### Allgemeine Fehler mit der {{site.data.keyword.dev_cli_short}}
{: #general}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie die {{site.data.keyword.dev_cli_short}}-CLI-Befehle 'create', 'delete', 'list' oder 'code' verwenden:

```
Failed to <command> project.
```
{: codeblock}


#### Ursache
{: #general-cause}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.


#### Lösung
{: #general-resolution}

Melden Sie sich erneut an.

```
ibmcloud login
```
{: codeblock}


### Fehler 'No such image', wenn Sie ein neues Projekt ausführen
{: #nosuchimage}

Möglicherweise wird der folgende Fehler angezeigt, wenn Sie ein Projekt ausführen, ohne es zunächst zu erstellen.

```
$ ibmcloud dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### Ursache
{: #nosuchimage-cause}

Sie müssen ein Projekt erstellen, bevor Sie es ausführen.


#### Lösung
{: #nosuchimage-resolution}

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu erstellen:

```
ibmcloud dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu starten:

```
ibmcloud dev run
```


### Service-Broker-Fehler beim Hinzufügen der {{site.data.keyword.objectstorageshort}}-Funktionalität
{: #os}

Möglicherweise wird der folgende Fehler angezeigt, wenn Sie die {{site.data.keyword.dev_cli_short}} verwenden, um zwei Projekte mit der {{site.data.keyword.objectstorageshort}}-Funktionalität zu erstellen:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Ursache
{: #os-cause}

Dieser Fehler wird vom {{site.data.keyword.objectstorageshort}}-Service verursacht, der nur eine Instanz des kostenlosen {{site.data.keyword.objectstorageshort}}-Plans bereitstellen kann.


#### Lösung
{: #os-resolution}

Sie werden aufgefordert, einen anderen Plan auszuwählen, um diesen Fehler zu vermeiden.


### Fehler beim Abrufen des Codes während der Erstellung eines Projekts
{: #code}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie die {{site.data.keyword.dev_cli_short}} verwenden, um ein Projekt zu erstellen:

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### Ursache
{: #code-cause}

Dieser Fehler wird durch eine interne Zeitlimitüberschreitung verursacht.


#### Lösung
{: #code-resolution}

Sie können den Code auf eine der folgenden Arten abrufen:

* Führen Sie den folgenden Befehl in der CLI aus:

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   Ersetzen Sie `<your-project-name>` durch den Namen des Projekts, das Sie während der Projekterstellung angegeben haben.

* Öffnen Sie die {{site.data.keyword.dev_console}}.

	1. Wählen Sie Ihr [Projekt ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://console.{DomainName}/developer/projects) in der {{site.data.keyword.dev_console}} aus und klicken Sie auf **Code abrufen**.

	2. Klicken Sie auf **Code generieren**.

	3. Klicken Sie auf **Code herunterladen**, nachdem der Code generiert wurde.


### Fehler beim Ausführen von `ibmcloud dev run` für Node.js-Projekte
{: #node}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie `ibmcloud dev run` in der {{site.data.keyword.dev_cli_short}} für Web- oder BFF-Projekte mit Node.js ausführen:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### Ursache
{: #node-cause}

Dieser Fehler tritt auf, wenn das Modul `appmetrics` in einer anderen Architektur installiert ist. Native NPM-Module, die in einer Architektur installiert sind, funktionieren nicht in einer anderen. Die eingeschlossenen Docker-Images basieren auf dem Linux-Kernel.


#### Lösung
{: #node-resolution}

Löschen Sie den Ordner `node_modules` und führen Sie den Befehl `ibmcloud dev run` erneut aus.


### Fehler bei der Bereitstellung in {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

Sie versuchen möglicherweise, mithilfe der {{site.data.keyword.dev_cli_short}} die Bereitstellung in {{site.data.keyword.Bluemix_notm}} zu erzielen und die Bereitstellung in {{site.data.keyword.Bluemix_notm}} funktioniert nicht, doch es wird kein Fehler gemeldet.


#### Ursache
{: #cause1}

Möglicherweise sind Sie nicht bei Ihrem Konto angemeldet.

#### Lösung
{: #resolution1}

Melden Sie sich an und versuchen Sie es erneut.

```
ibmcloud login
```


### Fehler bei der Bereitstellung in Kubernetes unter {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploytokube}

Dieser Fehler wird möglicherweise im Anschluss an die erste Eingabeaufforderung für Ihren Clusternamen angezeigt:

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### Ursache
{: #cause2}

Dies liegt wahrscheinlich an einem ungültigen Clusternamen. Sie können dies bestätigen, indem Sie denselben Befehl mit `--trace` ausführen. Sie sehen möglicherweise Folgendes in der Fehlernachricht:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Lösung
{: #resolution2}

Stellen Sie sicher, dass Sie den korrekten Cluster verwenden und dass Sie Ihren Cluster für die Bereitstellung konfiguriert haben, indem Sie den folgenden Befehl ausführen:

```
ibmcloud cs cluster-config <cluster-name>
```


### Fehler bei der Bereitstellung in Kubernetes unter {{site.data.keyword.Bluemix_notm}}

Dieser Fehler wird möglicherweise im Anschluss an die Eingabeaufforderung für das Bereitstellungsimageziel angezeigt:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### Ursache
{: #cause3}

Wahrscheinlich liegt dies an einem ungültigen Bereitstellungsimageziel. Genauer gesagt könnte es ein ungültiger Namensbereich sein, der mittlere Wert im Bereitstellungsimageziel.


#### Lösung
{: #resolution3}

Stellen Sie sicher, dass der Namensbereich im Bereitstellungsimageziel einem der Namensbereiche entspricht, die während der Ausführung des folgenden Befehls gefunden werden:

```
ibmcloud cr namespaces
```



## ANHANG
{: #appendix}

Für die meisten Benutzer, die Plattforminstallationsprogramme verwenden, werden alle Voraussetzungen installiert. Im Folgenden finden Sie Anweisungen, falls Sie weitere Komponenten manuell installieren müssen:

Zum Installieren des Entwickler-Plug-ins muss zunächst die [IBM Cloud-CLI](../reference/bluemix_cli/get_started.md#getting-started) installiert werden.

Zum Verwenden des Entwickler-Plug-ins müssen Sie es mithilfe dieses Befehls installieren: `ibmcloud plugin install dev -r Bluemix`

Zum lokalen Ausführen und Debuggen von Anwendungen müssen Sie auch [Docker ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://www.docker.com/get-docker) installieren.

Zum Bereitstellen einer App als Container müssen Sie auch `Kubernetes`, `Helm` und die folgenden IBM Cloud-CLI-Plug-ins installieren:

Gehen Sie wie folgt vor, um Kubernetes zu installieren:
* Mac-Benutzer:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux-Benutzer:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows-Benutzer:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Gehen Sie wie folgt vor, um Helm zu installieren:
* Mac- und Linux-Benutzer:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows-Benutzer:
Binärdatei unter https://github.com/kubernetes/helm/releases/tag/v2.6.0 herunterladen und installieren

Gehen Sie wie folgt vor, um das Plug-in 'container-registry' zu installieren: `ibmcloud plugin install container-registry`

Gehen Sie wie folgt vor, um das Plug-in 'container-service' zu installieren: `ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Hilfe und Support anfordern
{: #gettinghelp}

Bei Problemen mit der oder Fragen zur {{site.data.keyword.Bluemix_notm}}-{{site.data.keyword.dev_console}} oder der -{{site.data.keyword.dev_cli_notm}} erhalten Sie Hilfe, indem Sie in einem Forum nach Informationen suchen oder Fragen stellen. Sie können auch ein Support-Ticket öffnen.

Wenn Sie in den Foren Beiträge veröffentlichen, können Sie Ihre Fragen so taggen, dass die {{site.data.keyword.Bluemix_notm}}-Entwicklerteams benachrichtigt werden.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Wenn Sie technische Fragen zur Entwicklung oder Bereitstellung einer App mit der {{site.data.keyword.dev_console}} oder der {{site.data.keyword.dev_cli_notm}} haben:

* Veröffentlichen Sie Ihre Frage auf [Stack Overflow ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) und versehen Sie sie mit den Tags `bluemix-dev-services` und `ibm-bluemix`.
* Veröffentlichen Sie Ihre Frage auf [Slack ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm-cloud-tech.slack.com/) im `bluemix-dev-services`-Kanal. [Registrieren Sie sich ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm.biz/IBMCloudNativeSlack) noch heute.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Weitere Details zur Verwendung der Foren finden Sie unter [Hilfe anfordern ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/support/index.html#getting-help).

Informationen zum Öffnen eines {{site.data.keyword.IBM}} Support-Tickets oder zu Supportstufen und zu Prioritätsstufen von Tickets finden Sie unter [Support kontaktieren ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
