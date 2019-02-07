---

copyright:
  years: 2015, 2019
lastupdated: "2019-01-30"

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
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Fehlerbehebung für das Plug-in der {{site.data.keyword.cloud_notm}} Developer Tools-Befehlszeilenschnittstelle (CLI)
{: #troubleshoot}

Allgemeine Probleme bei der Verwendung der {{site.data.keyword.dev_cli_short}}-Befehlszeilenschnittstelle (CLI) zum Erstellen von Apps sind beispielsweise Fehler bei der Bereitstellung oder Code, der nicht abgerufen werden kann. In vielen Fällen können Sie diese Probleme durch Ausführen weniger einfacher Schritte beheben.
{: shortdesc}

## Warum wird ein Hostnamenfehler gemeldet, wenn ich eine App mit einem nicht mobilen Muster erstelle?
{: #hostname-error}
{: troubleshoot}

Wenn Sie eine App über die {{site.data.keyword.dev_cli_short}}-CLI in Cloud Foundry bereitstellen, wird möglicherweise der folgende Fehler angezeigt. Diese Meldung wird gegebenenfalls auch noch nach Eingabe eines eindeutigen Hostnamens angezeigt.

```
The hostname <myHostname> is taken.
```
{: screen}
{: tsSymptoms}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.
{: tsCauses}

Melden Sie sich durch Ausführen des folgenden Befehls erneut an:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Warum wird das Fehlschlagen eines allgemeinen Befehls gemeldet?
{: #general}
{: troubleshoot}

Wenn Sie den Befehl `create`, `delete`, `list` oder `code` verwenden, wird möglicherweise der folgende Fehler angezeigt:

```
Failed to <befehl> application.
```
{: screen}
{: tsSymptoms}

Dieser Fehler wird durch ein abgelaufenes Anmeldetoken verursacht.
{: tsCauses}

Melden Sie sich durch Ausführen des folgenden Befehls erneut an:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Warum wird das Image für meine neue App nicht erkannt?
{: #nosuchimage}
{: troubleshoot}

Wenn Sie versuchen, `ibmcloud dev run` für eine App auszuführen, ohne zuvor einen Build der App zu erstellen, wird möglicherweise der folgende Fehler angezeigt. 

```
Die Option run-cmd wurde nicht angegeben.
Container 'testProject' wird gestoppt...
Der Container 'testProject' wurde nicht gefunden.
Image ibmcloud-dev-testProject wird auf der Basis einer Dockerfile erstellt...
OK
Container 'testProject' wird auf der Basis dieses Images erstellt...
FEHLGESCHLAGEN
Der Container 'testProject' konnte nicht erstellt werden:
Fehler: Image nicht vorhanden: ibmcloud-dev-testProject
```
{: screen}
{: tsSymptoms}

Sie müssen eine App erstellen, bevor Sie sie ausführen. Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus:
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App zu starten:
```
ibmcloud dev run
```
{: tsResolve}

## Warum wird ein Service-Broker-Fehler gemeldet, wenn ich die {{site.data.keyword.objectstorageshort}}-Funktion hinzufüge?
{: #os}
{: troubleshoot}

Wenn Sie die Befehlszeilenschnittstelle (CLI) verwenden, um zwei Apps mit der {{site.data.keyword.objectstorageshort}}-Funktion zu erstellen, wird möglicherweise der folgende Fehler angezeigt:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

Dieser Fehler wird vom {{site.data.keyword.objectstorageshort}}-Service verursacht, der nur eine Instanz des freien {{site.data.keyword.objectstorageshort}}-Plans bereitstellen kann.
{: tsCauses}

Wählen Sie einen anderen Plan aus.
{: tsResolve}

## Warum wird mein Code nicht abgerufen, wenn ich eine App erstelle?
{: #code}
{: troubleshoot}

Wenn Sie die Befehlszeilenschnittstelle (CLI) zum Erstellen einer App verwenden, wird möglicherweise der folgende Fehler angezeigt:

```
FAILED                            
Application created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

Dieser Fehler wird durch eine interne Zeitlimitüberschreitung verursacht.
{: tsCauses}

Rufen Sie den Code auf eine der folgenden Arten ab:

* Führen Sie den folgenden Befehl aus:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Ersetzen Sie `<your-app-name>` durch den Namen der App, die Sie während der App-Erstellung angegeben haben.

* Öffnen Sie die {{site.data.keyword.dev_console}}.

	1. Wählen Sie Ihre [App ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://console.bluemix.net/developer/appservice/apps) in der {{site.data.keyword.dev_console}} aus.

	2. Klicken Sie auf **Code herunterladen**.
{: tsResolve}

## Warum kann ich den Befehl `ibmcloud dev run` nicht für Node.js-Apps ausführen?
{: #node}
{: troubleshoot}

Wenn Sie den Befehl `ibmcloud dev run` für Node.js-Web- oder BFF-Apps ausführen, wird möglicherweise der folgende Fehler angezeigt:

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
{: screen}
{: tsSymptoms}

Dieser Fehler tritt auf, wenn das Modul `appmetrics` in einer anderen Architektur installiert ist. Native NPM-Module, die in einer Architektur installiert sind, funktionieren nicht in einer anderen. Die eingeschlossenen Docker-Images basieren auf dem Linux-Kernel.
{: tsCauses}

Löschen Sie den Ordner `node_modules` und führen Sie den Befehl `ibmcloud dev run` erneut aus.
{: tsResolve}

## Warum gelingt mir die Bereitstellung auf {{site.data.keyword.cloud_notm}} nicht?
{: troubleshoot}

Der Versuch der Bereitstellung in {{site.data.keyword.cloud_notm}} schlägt fehl, aber es wird kein Fehler angezeigt.
{: tsSymptoms}

Möglicherweise sind Sie nicht bei Ihrem Konto angemeldet.
{: tsCauses}

Melden Sie sich durch Ausführen des folgenden Befehls an und wiederholen Sie den Versuch.
```
ibmcloud login
```
{: tsResolve}

## Warum gelingt mir die Bereitstellung in Kubernetes auf {{site.data.keyword.cloud_notm}} nicht?
{: troubleshoot}

Nachdem Sie aufgefordert wurden, Ihren Clusternamen anzugeben, wird möglicherweise der folgende Fehler angezeigt:
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

Dies liegt wahrscheinlich daran, dass der Clustername nicht gültig ist. Bestätigen Sie diese Annahme, indem Sie denselben Befehl mit `--trace` ausführen. Die folgenden Details können in der Fehlernachricht enthalten sein:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Stellen Sie sicher, dass Sie den korrekten Cluster verwenden und dass dieser für die Bereitstellung konfiguriert ist, indem Sie den folgenden Befehl ausführen: 
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## Warum kann ich kein Imageziel bereitstellen?
{: troubleshoot}

Nachdem Sie zur Angabe des Bereitstellungsimageziels aufgefordert wurden, wird möglicherweise der folgende Fehler angezeigt:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

Dies liegt wahrscheinlich daran, dass das Bereitstellungsimageziel nicht gültig ist. Genauer gesagt, ist wahrscheinlich der Namensbereich, bei dem es sich um den mittleren Wert im Bereitstellungsimageziel handelt, nicht gültig.
{: tsCauses}

Stellen Sie sicher, dass der Namespace im Implementierungsimageziel mit einem der Namensbereiche übereinstimmt, die angezeigt werden, wenn Sie den folgenden Befehl ausführen:
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Warum kann die Sprache für meine App nicht ermittelt werden?
{: troubleshoot}

Bei dem Versuch, Ihre App zu starten, wird möglicherweise der folgende Fehler angezeigt:
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: screen}
{: tsSymptoms}

Dieser Fehler kann eine der folgenden Ursachen haben:
- Der Befehl [enable](/docs/cli/idt/commands.html#enable) wurde in einem Verzeichnis ausgeführt, das nicht das Quellenverzeichnis Ihrer Anwendung ist.
- Der Befehl [enable](/docs/cli/idt/commands.html#enable) wurde für eine App einer Sprache ausgeführt, die nicht erkannt wird.
{: tsCauses}

Stellen Sie sicher, dass Sie den Befehl in dem App-Verzeichnis ausführen, das den Quellcode für die App enthält. Wenn das Problem dadurch trotzdem nicht behoben werden kann und als Sprache eine der [unterstützten Sprachen](/docs/cli/idt/commands.html#enable-language-options) verwendet wird, verwenden Sie den Parameter `--language`, um die Sprache anzugeben.
{: tsResolve}

## Warum kann ich keine App erstellen oder ausführen, die für die Cloudbereitstellung aktiviert wurde?
{: troubleshoot}

Der Versuch, eine App, die entsprechend aktiviert wurde, mit [build](/docs/cli/idt/commands.html#build) zu erstellen oder mit [run](/docs/cli/idt/commands.html#run) auszuführen, führt möglicherweise zu mehreren Fehlschlägen.
{: tsSymptoms}


Die vielfältigen verschiedenen möglichen Ursachen sind jeweils unter den folgenden Links aufgeführt.
{: tsCauses}

- Weitere Informationen zum Beheben derartiger Probleme bei einer Spring-App finden Sie in [Vorhandene Spring Boot-Anwendungen für die Cloudbereitstellung aktivieren](/docs/java-spring/enable_existing.html#enable_existing).
- Weitere Informationen zum Beheben derartiger Probleme bei einer `Node.js`-App finden Sie in [Vorhandene Node.js-Anwendungen für die Cloudbereitstellung aktivieren](/docs/node/enable_existing.html#enable_existing).
{: tsResolve}

## Wie kann ich die {{site.data.keyword.Bluemix_notm}}-Entwicklertools manuell installieren? 
{: #appendix}
Für die meisten Benutzer werden alle Voraussetzungen mithilfe der Plattforminstallationsprogramme installiert. Im Folgenden finden Sie Anweisungen für die einzelnen Komponenten, falls Sie weitere Komponenten manuell installieren müssen.
Zum Installieren des Entwickler-Plug-ins müssen Sie zunächst die [IBM Cloud-CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use) installieren.
Zum Verwenden des Entwickler-Plug-ins müssen Sie das Plug-in mithilfe des folgenden Befehls installieren: 
```
ibmcloud plugin install dev
```
{: codeblock}
 
Zum lokalen Ausführen und Debuggen von Apps müssen Sie auch [Docker](https://www.docker.com/get-docker) installieren.
 
Zum Bereitstellen einer App als Container müssen Sie auch Kubernetes, Helm und die folgenden IBM Cloud-CLI-Plug-ins installieren.
 
### Gehen Sie wie folgt vor, um Kubernetes zu installieren:
Mac-Benutzer:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Linux-Benutzer:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Windows-Benutzer:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### Gehen Sie wie folgt vor, um Helm zu installieren:
Mac-und Linux-Benutzer:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Windows-Benutzer:
Laden Sie die [Binärdatei](https://github.com/kubernetes/helm/releases/tag/v2.7.2) herunter und installieren Sie sie.

### Gehen Sie wie folgt vor, um das Plug-in 'container-registry' zu installieren:
```
ibmcloud plugin install container-registry
```
{: codeblock}

### Gehen Sie wie folgt vor, um das Plug-in 'container-service' zu installieren:
```
ibmcloud plugin install container-service
```
{: codeblock}
