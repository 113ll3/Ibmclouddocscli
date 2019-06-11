---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

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

Lösungen zu häufig auftretenden Problemen finden Sie in der {{site.data.keyword.dev_cli_short}}-Befehlszeilenschnittstelle (Command Line Interface, CLI). In vielen Fällen können Sie diese Probleme durch Ausführen weniger einfacher Schritte beheben.
{: shortdesc}

## Warum wird ein Hostnamenfehler gemeldet, wenn ich eine Anwendung mit einem nicht mobilen Muster erstelle?
{: #ts-cli-hostname-error}
{: troubleshoot}

Wenn Sie eine Anwendung über die {{site.data.keyword.dev_cli_short}}-CLI in Cloud Foundry bereitstellen, wird möglicherweise der folgende Fehler angezeigt. Diese Meldung wird gegebenenfalls auch noch nach Eingabe eines eindeutigen Hostnamens angezeigt.
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
{: #ts-cli-general-failures}
{: troubleshoot}

Wenn Sie den Befehl `create`, `delete`, `list` oder `code` verwenden, wird möglicherweise der folgende Fehler angezeigt:
```
Failed to <command> app.
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
{: #ts-cli-nosuchimage}
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
{: #ts-cli-object-storage}
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
{: #retrieve-code-error}
{: troubleshoot}

Wenn Sie die Befehlszeilenschnittstelle (CLI) zum Erstellen einer App verwenden, wird möglicherweise der folgende Fehler angezeigt:
```
FAILED                            
App created, but could not get code
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

   Ersetzen Sie `<your-app-name>` durch den App-Namen, den Sie bei der App-Erstellung angegeben haben.

* Öffnen Sie die {{site.data.keyword.dev_console}}.

	1. Wählen Sie Ihre [App](https://cloud.ibm.com/resources){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") in der {{site.data.keyword.dev_console}} aus.

	2. Klicken Sie auf **Code herunterladen**.
{: tsResolve}

## Warum kann ich den Befehl `ibmcloud dev run` nicht für Node.js-Apps ausführen?
{: #ts-cli-node}
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

Dieser Fehler tritt auf, wenn das Modul `appmetrics` in einer anderen Architektur installiert ist. Native NPM-Module, die in einer Architektur installiert sind, funktionieren nicht in einer anderen. Die enthaltenen Docker-Images basieren auf dem Linux&trade;-Kernel.
{: tsCauses}

Löschen Sie den Ordner `node_modules` und führen Sie den Befehl `ibmcloud dev run` erneut aus.
{: tsResolve}

## Warum gelingt mir die Bereitstellung auf {{site.data.keyword.cloud_notm}} nicht?
{: #ts-cli-deploy-issues}
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
{: #ts-cli-kube-deploy}
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

Das Problem ist wahrscheinlich darauf zurückzuführen, dass ein Clustername nicht gültig ist. Bestätigen Sie diese Annahme, indem Sie denselben Befehl mit `--trace` ausführen. Die folgenden Details können in der Fehlernachricht enthalten sein:
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
{: #ts-deploy-image-target}
{: troubleshoot}

Nachdem Sie zur Angabe des Bereitstellungsimageziels aufgefordert wurden, wird möglicherweise der folgende Fehler angezeigt:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

Das Problem ist wahrscheinlich darauf zurückzuführen, dass ein Bereitstellungsimageziel nicht gültig ist. Genauer gesagt, ist wahrscheinlich der Namensbereich, bei dem es sich um den mittleren Wert im Bereitstellungsimageziel handelt, nicht gültig.
{: tsCauses}

Stellen Sie sicher, dass der Namensbereich im Bereitstellungsimageziel mit einem der Namensbereiche übereinstimmt, die angezeigt werden, wenn Sie den folgenden Befehl ausführen:
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Warum kann die Sprache für meine App nicht ermittelt werden?
{: #ts-cli-determine-language}
{: troubleshoot}

Der folgende Fehler wird möglicherweise angezeigt, wenn Sie Ihre App starten:
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

Dieser Fehler kann eine der folgenden Ursachen haben:
- Der Befehl [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) wurde in einem Verzeichnis ausgeführt, das nicht das Quellenverzeichnis Ihrer App ist.
- Der Befehl [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) wurde für eine App einer Sprache ausgeführt, die nicht erkannt wird.
{: tsCauses}

Stellen Sie sicher, dass Sie den Befehl in dem App-Verzeichnis ausführen, das den Quellcode für die App enthält. Wenn das Problem dadurch nicht behoben werden kann und als Sprache eine der [unterstützten Sprachen](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options) verwendet wird, verwenden Sie den Parameter `--language`, um die Sprache anzugeben.
{: tsResolve}

## Warum kann ich keine App erstellen oder ausführen, die für die Cloudbereitstellung aktiviert wurde?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

Möglicherweise sind verschiedene Probleme aufgetreten, als Sie eine App, die für die Cloudbereitstellung aktiviert wurde, mit [build](/docs/cli/idt?topic=cloud-cli-idt-cli#build) erstellen oder mit [run](/docs/cli/idt?topic=cloud-cli-idt-cli#run) ausführen wollten.
{: tsSymptoms}

Die vielfältigen verschiedenen möglichen Ursachen sind jeweils unter den folgenden Links aufgeführt.
{: tsCauses}

- Weitere Informationen zum Beheben derartiger Probleme bei einer Spring-App finden Sie in [Vorhandene Spring Boot-Apps für die Cloudbereitstellung aktivieren](/docs/java-spring?topic=java-spring-enable_existing#enable_existing).
- Weitere Informationen zum Beheben derartiger Probleme bei einer `Node.js`-App finden Sie in [Vorhandene Node.js-Apps für die Cloudbereitstellung aktivieren](/docs/node?topic=nodejs-enable_existing#enable_existing).
{: tsResolve}

## Vorgehensweise zur manuellen separaten Installation der Komponenten der {{site.data.keyword.dev_cli_notm}}-CLI
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

Zur manuellen, separaten Installation der Komponenten der {{site.data.keyword.dev_cli_notm}}-CLI können Sie diesen [Schritten](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually) folgen.

## Warum kann ich das Docker-Image nicht erstellen?
{: $ts-cli-docker}
{: troubleshoot}

Möglicherweise wird der folgende Fehler angezeigt: 
```
FAILED
An error exit status 1 was encountered while building the Docker 
image.
```
{: screen}

Dieser Fehler kann eine der folgenden Ursachen haben:
- Docker ist nicht installiert.
- Der Docker-Dämon wird nicht ausgeführt.
{: tsCauses}

Stellen Sie sicher, dass Docker installiert und aktiv ist:
- Installation oder Starten von [Docker für Mac](https://docs.docker.com/docker-for-mac/install/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
- Installation oder Starten von [Docker für Windows&trade;](https://docs.docker.com/docker-for-windows/install/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
- Installation oder Starten von [Docker für Linux&trade;](https://docs.docker.com/v17.12/install/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
{: tsResolve}

## Wie lassen sich inkompatible Helm-Versionen auflösen?
{: ts-cli-helm}
{: troubleshoot}

Wenn die Client- und die Server-Helm-Version nicht synchronisiert sind, werden möglicherweise die folgenden Fehler angezeigt:
```
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED: 
configmaps is forbidden: User "system:serviceaccount:kube-system:default" 
cannot list resource "configmaps" in API group "" in the namespace 
"kube-system"
```
{: screen}

```
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

Zur Behebung des Problems müssen Sie die Version des Clients auf die der Clusterversion setzen. Um beispielsweise die Helm-Version 2.8.1 zu installieren, führen Sie folgende Befehle aus:
{: tsResolve}

* Führen Sie für Mac und Linux&trade; die folgenden Befehle aus:
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* Für Windows&trade;: Laden Sie als Administrator die Binärdatei `helm` von [https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") herunter und installieren Sie sie.
  
  Führen Sie über das PowerShell-Terminal die folgenden Befehle aus:
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```
  {: codeblock}

## Warum schlägt 'ibmcloud dev build' bei Verwendung eines Benutzernamens, der "@" enthält, fehl?
{: ts-cli-username}
{: troubleshoot}
Während des Image-Erstellungsprozesses wird Ihr Benutzername für den Benutzer im Docker-Tool-Image verwendet. Wenn der Benutzername Sonderzeichen wie '@' oder '-' enthält, schlägt der Erstellungsprozess des Docker-Images fehl und der folgende Fehler wird angezeigt:
```
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Speicherauszug aus dem Befehl:
```
{: screen}

Zur Behebung des Problems entfernen Sie eventuell vorhandene Sonderzeichen aus Ihrem Benutzernamen oder geben Sie das folgende Flag an, um stattdessen den Rootbenutzer zu verwenden:
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
