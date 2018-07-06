---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Fehlerbehebung für {{site.data.keyword.Bluemix_notm}} Developer Tools
{: #troubleshoot}

Allgemeine Probleme bei Verwendung der {{site.data.keyword.dev_cli_short}}-CLI zum Erstellen von Apps sind beispielsweise Bereitstellungsfehler oder Code, der beim Erstellen eines Projekts nicht abgerufen werden kann. In vielen Fällen können Sie diese Probleme durch Ausführen weniger einfacher Schritte beheben.
{:shortdesc}

## Hostnamenfehler beim Erstellen einer App mit einem nicht mobilen Muster
{: #hostname-error}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie eine App über die {{site.data.keyword.dev_cli_short}}-CLI in Cloud Foundry bereitstellen. Wenn Sie einen Hostnamen eingeben, den Sie für eindeutig halten, wird möglicherweise trotzdem diese Nachricht angezeigt.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.
{: tsCauses}

Melden Sie sich erneut an.

```
bx login
```
{: codeblock}
{: tsResolve}

## Allgemeine Fehler mit der {{site.data.keyword.dev_cli_short}}-CLI
{: #general}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie die {{site.data.keyword.dev_cli_short}}-CLI-Befehle `create`, `delete`, `list` oder `code` verwenden:

```
Failed to <befehl> application.
```
{: codeblock}
{: tsSymptoms}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.
{: tsCauses}

Melden Sie sich erneut an.

```
bx login
```
{: codeblock}
{: tsResolve}

## Fehler 'No such image', wenn Sie eine neue App ausführen
{: #nosuchimage}

Möglicherweise wird der folgende Fehler angezeigt, wenn Sie eine App ausführen, ohne sie zunächst zu erstellen.

```
$ bx dev run
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
{: tsSymptoms}

Sie müssen eine App erstellen, bevor Sie sie ausführen.
{: tsCauses}

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App zu erstellen:

```
bx dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App zu starten:

```
bx dev run
```
{: tsResolve}

## Service-Broker-Fehler beim Hinzufügen der {{site.data.keyword.objectstorageshort}}-Funktionalität
{: #os}

Möglicherweise wird der folgende Fehler angezeigt, wenn Sie die {{site.data.keyword.dev_cli_short}}-CLI verwenden, um zwei Apps mit der {{site.data.keyword.objectstorageshort}}-Funktionalität zu erstellen:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Dieser Fehler wird vom {{site.data.keyword.objectstorageshort}}-Service verursacht, der nur eine Instanz des freien {{site.data.keyword.objectstorageshort}}-Plans bereitstellen kann.
{: tsCauses}

Sie werden aufgefordert, einen anderen Plan auszuwählen, um diesen Fehler zu vermeiden.
{: tsResolve}

## Fehler beim Abrufen des Codes während der Erstellung einer App
{: #code}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie die {{site.data.keyword.dev_cli_short}}-CLI verwenden, um eine App zu erstellen:

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Dieser Fehler wird durch eine interne Zeitlimitüberschreitung verursacht.
{: tsCauses}

Sie können den Code auf eine der folgenden Arten abrufen:

* Führen Sie den folgenden Befehl in der CLI aus:

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   Ersetzen Sie `<your-app-name>` durch den Namen der App, die Sie während der App-Erstellung angegeben haben.

* Öffnen Sie die {{site.data.keyword.dev_console}}.

	1. Wählen Sie Ihre [App ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://console.bluemix.net/developer/appservice/apps) in der {{site.data.keyword.dev_console}} aus.

	2. Klicken Sie auf **Code herunterladen**.

{: tsResolve}

## Fehler beim Ausführen von `bx dev run` für Node.js-Apps
{: #node}

Möglicherweise wird der folgende Fehler ausgegeben, wenn Sie `bx dev run` in der {{site.data.keyword.dev_cli_short}}-CLI für Web- oder BFF-Apps mit Node.js ausführen:

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
{: tsSymptoms}

Dieser Fehler tritt auf, wenn das Modul `appmetrics` in einer anderen Architektur installiert ist. Native NPM-Module, die in einer Architektur installiert sind, funktionieren nicht in einer anderen. Die eingeschlossenen Docker-Images basieren auf dem Linux-Kernel.
{: tsCauses}

Löschen Sie den Ordner `node_modules` und führen Sie den Befehl `bx dev run` erneut aus.
{: tsResolve}

## Fehler bei der Bereitstellung in {{site.data.keyword.Bluemix_notm}}

Es tritt ein Fehler auf, wenn Sie die Bereitstellung in {{site.data.keyword.Bluemix_notm}} über die {{site.data.keyword.dev_cli_short}}-CLI versuchen, aber es wird kein Fehler angezeigt.
{: tsSymptoms}

Möglicherweise sind Sie nicht bei Ihrem Konto angemeldet.
{: tsCauses}

Melden Sie sich an und versuchen Sie es erneut.

```
bx login
```
{: tsResolve}

## Fehler bei der Bereitstellung in Kubernetes unter {{site.data.keyword.Bluemix_notm}}

Möglicherweise wird der folgende Fehler angezeigt, nachdem Sie aufgefordert wurden, Ihren Clusternamen anzugeben.

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

Dies liegt wahrscheinlich daran, dass der Clustername nicht gültig ist. Bestätigen Sie diese Annahme, indem Sie denselben Befehl mit `--trace` ausführen. Die folgenden Details können in der Fehlernachricht enthalten sein:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Stellen Sie sicher, dass Sie den korrekten Cluster verwenden und dass Sie Ihren Cluster für die Bereitstellung konfiguriert haben, indem Sie den folgenden Befehl ausführen:

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## Fehler bei der Bereitstellung eines Imageziels

Möglicherweise wird der folgende Fehler angezeigt, nachdem Sie zur Angabe des Bereitstellungsimageziels aufgefordert wurden:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

Dies liegt wahrscheinlich daran, dass das Bereitstellungsimageziel nicht gültig ist. Genauer gesagt, ist wahrscheinlich der Namensbereich, bei dem es sich um den mittleren Wert im Bereitstellungsimageziel handelt, nicht gültig.

Stellen Sie sicher, dass der Namensbereich im Bereitstellungsimageziel einem der Namensbereiche entspricht, die während der Ausführung des folgenden Befehls gefunden werden:

```
bx cr namespaces
```
{: tsResolve}

## Tools erneut installieren
{: #appendix}

Für die meisten Benutzer werden alle Voraussetzungen mithilfe der Plattforminstallationsprogramme installiert. Im Folgenden finden Sie Anweisungen, falls Sie weitere Komponenten manuell installieren müssen:

Zum Installieren des Entwickler-Plug-ins müssen Sie zunächst die [IBM Cloud-CLI](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started) installieren.

Zum Verwenden des Entwickler-Plug-ins müssen Sie es mithilfe dieses Befehls installieren: `bx plugin install dev -r Bluemix`

Zum lokalen Ausführen und Debuggen von Apps müssen Sie auch [Docker](https://www.docker.com/get-docker) installieren.

Zum Bereitstellen einer App als Container müssen Sie auch Kubernetes, Helm und die folgenden IBM Cloud-CLI-Plug-ins installieren:

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

Gehen Sie wie folgt vor, um das Plug-in 'container-registry' zu installieren:
`bx plugin install container-registry`

Gehen Sie wie folgt vor, um das Plug-in 'container-service' zu installieren: `bx plugin install container-service`
