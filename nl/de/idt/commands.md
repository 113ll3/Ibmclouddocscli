---

copyright:
   years: 2017, 2019
lastupdated: "2019-07-12"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer plugin cli, dev plugin commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Befehle des CLI-Plug-ins von {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Version: 2.1.18
Freigegeben: 28. März 2019

Ab Mai 2018 wird an Stelle der {{site.data.keyword.cloud}}-CLI-Befehle `bluemix` und `bx` der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch weiterhin verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

Verwenden Sie die Befehle der {{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle (`ibmcloud dev`), um eine Anwendung zu erstellen, zu verwalten, bereitzustellen, zu debuggen und zu testen.

Führen Sie mehrere Befehle in einer einzigen Befehlszeilenanweisung mit [zusammengesetzten Befehlen](#compound) aus.
{: tip}

## build
{: #build}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können Ihre App mithilfe des Befehls `build` erstellen. Die Befehl `test`, `debug` und `run` setzen eine kompilierte App voraus, daher müssen Sie zuvor eine Operation `build` durchführen.

Das Konfigurationselement `build-cmd-debug` wird zum Erstellen der Anwendung für alle Verwendungszwecke, mit Ausnahme von `run` verwendet. Sie erstellen Ihre App für das Debuggen, indem Sie die Befehlszeilenoption `--debug` angeben. Das Konfigurationselement `build-cmd-run` wird beim Erstellen der App für den Einsatz mit dem Befehl `run` verwendet.

Für den Build mit mehreren Containern muss die Anwendung entweder eine [Compose-Datei](https://docs.docker.com/compose/overview/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") enthalten, die in der Datei `cli-config.yml` angegeben ist, oder Sie können mit dem Befehlsparameter `dockerfile-tools` eine solche Datei angeben.

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um den Build zu starten:  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

Verwenden Sie den Befehl `code`, um eine zuvor erstellte App mit App-Vorlagencode und Konfigurationsdateien für {{site.data.keyword.cloud_notm}} herunterzuladen. Sie können diesen Befehl verwenden, wenn Sie eine zweite Kopie einer App extrahieren müssen.

Führen Sie den folgenden Befehl aus, um den Code aus einer angegebenen App herunterzuladen.
```
ibmcloud dev code <appName>
```
{: codeblock}

## console
{: #console}

Verwenden Sie den Befehl `console`, um in einem Web-Browser die Webkonsole Ihrer App unter {{site.data.keyword.cloud_notm}} zu öffnen. Sie können den Befehl `ibmcloud dev console` vom Ordner Ihrer App aus ausführen. Die CLI versucht dann, eine entsprechende App in {{site.data.keyword.cloud_notm}} zu finden, die über dieselbe App-ID verfügt wie das aktuelle Verzeichnis. Falls das System keinen übereinstimmenden Namen findet, wird anstelle der spezifischen App das Dashboard für **Webanwendungen und mobile Anwendungen** in {{site.data.keyword.cloud_notm}} geöffnet.

Wenn Sie einen App-Namen angeben, überspringt die Befehlszeilenschnittstelle den Abgleich des Ordner- oder App-Namens. In diesem Fall öffnet die CLI die Konsole der angegebenen App in einem Web-Browser.  

Führen Sie den folgenden Befehl aus, um die Webkonsole Ihrer App in einem Web-Browser zu öffnen.
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

Erstellen Sie eine App, in der zur Eingabe aller Informationen (z. B. Ressourcentyp, Sprache, Starter-Kitt und DevOps-Toolchain-Optionen) aufgefordert wird. Dies schließt IBM Cloud Foundry oder Cloud Foundry Enterprise Environment und Kubernetes ein. Die App wird im aktuellen Verzeichnis erstellt.

Führen Sie den folgenden Befehl aus, um eine App im aktuellen Verzeichnis zu erstellen und ihr Services zuzuordnen:
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können Ihre App mithilfe des Befehls `debug` debuggen. Zuerst muss für die App ein Build erstellt werden, indem der Befehl 'build' mit dem Argument `--debug` verwendet wird. Wenn Sie den Befehl `debug` starten, wird ein Container gestartet, der einen oder mehrere Debugports bereitstellt, wie im Wert `container-port-map-debug` in der cli-config.yml definiert bzw. wie in der Befehlszeile angegeben. Verbinden Sie Ihr bevorzugtes Debugging-Tool mit dem Port oder den Ports und Sie können Ihre App wie üblich debuggen.

Kompilieren Sie zuerst Ihre App:
```
ibmcloud dev build --debug
```
{: codeblock}

Führen Sie zuerst den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um mit dem Debugging zu beginnen:
```
ibmcloud dev debug
```
{: codeblock}

Um das Debugging auszuführen, hängen Sie Ihr Debugging-Tool an den angegebenen Port an.

Geben Sie `STRG-C` ein, um die Debugsitzung zu beenden.

### Parameter des Befehls 'debug'
{: #debug-parameters}

Die folgenden Parameter stehen ausschließlich für den Befehl `debug` zur Verfügung und unterstützen das Debugging für eine App. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `container-port-map-debug`
{: #port-map-debug}

* Portzuordnungen für den Debugport. Der erste Wert ist der Port, der im Hostbetriebssystem verwendet werden soll, der zweite Wert ist der Port im Container [`host-port:container-port`].
* Syntax: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parameter zum Erstellen von Code für DEBUG.
* Syntax: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parameter zum Angeben eines Befehls zum Starten des Debuggers im Container 'tools'. Verwenden Sie diesen Parameter, wenn
`build-cmd-debug` Ihre App im Debugger startet.
* Syntax: `ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

Mit dem Befehl `delete` können Sie Apps aus Ihrem {{site.data.keyword.cloud_notm}}-Bereich entfernen. Sie können den Befehl ohne Parameter ausführen, um verfügbare Apps aufzulisten und die zu löschende App in der nummerierten Liste auszuwählen. Der App-Code und die App-Verzeichnisse werden nicht aus dem lokalen Plattenspeicher entfernt.

Führen Sie den folgenden Befehl aus, um Ihre App aus {{site.data.keyword.cloud_notm}} zu löschen:
```
ibmcloud dev delete [appName] [--force,-f]
```
{: codeblock}

{{site.data.keyword.cloud_notm}}-Services werden nicht entfernt.
{: note}


### Parameter des Befehls 'delete'
{: #delete-command-parameters}

#### `force`
{: #delete-force}

* Optionaler Parameter zum Überspringen der Eingabeaufforderungsbestätigung zum Löschen einer Anwendung.
* Syntax: `ibmcloud dev delete [appName] --force`

## deploy
{: #deploy}

Sie können eine App als Cloud Foundry-App oder als einen Container bereitstellen.

Bevor Sie eine App als Cloud Foundry-App in {{site.data.keyword.cloud_notm}} bereitstellen, muss eine Datei `manifest.yml` im Stammverzeichnis Ihrer Anwendung vorhanden sein.

Bevor Sie eine App als Container bereitstellen, müssen Sie [Kubernetes](https://kubernetes.io/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und [Helm](https://github.com/helm/helm){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") lokal installieren. Die Version des Helm-Clients darf nicht neuer als die Version des Helms-Servers sein. Beide Angaben erhalten Sie, indem Sie `helm version` ausführen. Für die Clientversion wird Version 2.4.2 empfohlen.

Für die Bereitstellung der App in Kubernetes müssen Sie entweder für `deploy-target` den Wert `container` in `cli-config.yml` angeben oder den Parameter `-t container` verwenden.

Weitere Parameter, die für die Konfiguration der Kubernetes-Bereitstellung erforderlich sind, können ebenfalls in der Datei `cli-config.yml` mithilfe von Befehlszeilenargumenten angegeben werden. Wenn Sie diese Parameter nicht in der Datei `cli-config.yml` definieren, müssen Sie die Bereitstellung mit dem Parameter `-t container` durchführen und werden zur Eingabe aller anderen Werte aufgefordert.

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

In `cli-config.yml` können Sie die Position eines Helm-Diagramms in der Eigenschaft `chart-path` definieren und `deploy-image-target` konfigurieren, wie im Beispiel dargestellt. Das Element `deploy-image-target` in der `cli-config.yml` wird statt der Elemente `repository` und `tag` in der Datei `chart/values.yml` verwendet. Um gezielt in {{site.data.keyword.cloud_notm}} bereitzustellen, legen Sie das Konfigurationselement `ibm-cluster` auf den Namen des Kubernetes-Clusters fest, den Sie in {{site.data.keyword.cloud_notm}} erstellt haben.

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App zu erstellen:  
```
ibmcloud dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App bereitzustellen:
```
ibmcloud dev deploy
```
{: codeblock}

### In {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment bereitstellen 
{: #deploy-cfee}

Sie können Ihre Anwendung in {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment bereitstellen. Konfigurieren Sie dazu Ihre lokale Umgebung für diese Umgebung mithilfe von `ibmcloud target --cf` und wählen Sie dann in der Liste die richtige Umgebung aus. Anschließend können Sie den Befehl `deploy` so verwenden wie für {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### Parameter des Befehls 'deploy'
{: #deploy-parameters}

Die folgenden Parameter können mit dem Befehl `deploy` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der App angegeben werden. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `chart-path`
{: #chart-path}

* Parameter für eine Containerbereitstellung zur Angabe der Position des Helm-Diagramms, das für die Bereitstellung verwendet wird.
* Syntax: `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Parameter zum Angeben des Typs der fertigzustellenden Bereitstellung. Der Standardbereitstellungstyp ist ein Buildpack.
* Syntax: `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter, der bei einer Containerbereitstellung als Zielimagename für die Bereitstellung verwendet wird. Der Wert darf keine Version enthalten (z. B. image-name:{version}), da die Version von `deploy` automatisch inkrementiert und angehängt wird.
* Syntax: `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung in {{site.data.keyword.cloud_notm}}.
* Syntax: `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Parameter, der verwendet wird, um den Hostnamen der App zu definieren, wenn die Bereitstellung in Cloud Foundry erfolgt.
* Syntax: `ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* Parameter, der verwendet wird, um die Domäne der App zu definieren, wenn die Bereitstellung in Cloud Foundry erfolgt.
* Syntax: `ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

Der Befehl `diag` wird zu Diagnosezwecken verwendet und dient zur Anzeige der Versionsinformationen installierter Abhängigkeiten für die {{site.data.keyword.dev_cli_notm}}-CLI. Die Ausführung von `diag` ist hilfreich, wenn Sie feststellen möchten, ob Abhängigkeiten fehlen oder um Fehler zu beheben.

Führen Sie den folgenden Befehl aus, um die Versionen der installierten Abhängigkeiten anzuzeigen:
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

Bearbeiten Sie Ihre App mit Optionen wie dem Verbinden mit einer vorhandenen {{site.data.keyword.cloud_notm}}-App und Verwalten von {{site.data.keyword.cloud_notm}} und der zugehörigen {{site.data.keyword.cloud_notm}}-Toolchain, die in {{site.data.keyword.cloud_notm}} Kubernetes, Cloud Foundry oder Cloud Foundry Enterprise Environment bereitgestellt wird. Verwenden Sie bei einer lokalen App, die mit einer App in {{site.data.keyword.cloud_notm}} verbunden ist, den Befehl `edit` zum Hinzufügen neuer Services, zum Herstellen und Trennen von Verbindungen zu vorhandenen Services sowie zum Entfernen vorhandener Services in Ihrem Konto. Darüber hinaus können Sie eine {{site.data.keyword.cloud_notm}}-Toolchain für die App erstellen oder anzeigen. Führen Sie den folgenden Befehl im Stammverzeichnis Ihres App-Verzeichnisses aus:
```
ibmcloud dev edit
```
{: codeblock}

Wenn in Ihrem Konto keine Services vorhanden sind, wird mit diesem Befehl eine Liste der Servicegruppen angezeigt, in der Sie einen Service auswählen, der mit Ihrer App verbunden werden soll.

Wenn in Ihrem Konto jedoch Services vorhanden sind, wird mit diesem Befehl eine Liste dieser Services angezeigt und angegeben, ob die einzelnen Services mit der App verbunden sind.

* Wenn Sie einen verbundenen Service auswählen, können Sie entweder die Verbindung dieses Service zu Ihrer App trennen oder den Service aus Ihrem Konto löschen, wodurch die Verbindungen zu allen Apps getrennt werden.

* Wenn Sie einen nicht verbundenen Service auswählen, können Sie entweder diesen Service mit Ihrer App verbinden oder den Service aus Ihrem Konto löschen. Durch das Verbinden eines vorhandenen Service werden auch Dateien (z. B. Berechtigungsnachweise oder Quellcode) heruntergeladen.

Sie können auch einen Service zu Ihrer App hinzufügen. In diesem Fall wird eine Abfolge von Eingabeaufforderungen für die Serviceauswahl angezeigt und es werden zusätzliche Daten (z. B. Berechtigungsnachweisdateien oder Quellcode) heruntergeladen.

## enable
{: #enable}

Vorhandene App für die {{site.data.keyword.cloud_notm}}-Bereitstellung aktivieren. Der Befehl `enable` versucht, die Sprache einer vorhandenen App automatisch zu erkennen und dann zur Angabe zusätzlicher, erforderlicher Informationen aufzufordern. Es werden Dateien generiert, die für lokale Docker-Container, für die Cloud Foundry-Bereitstellung bzw. für die Cloud Foundry Enterprise Environment- oder die Kubernetes Container-Bereitstellung verwendet werden. Alle Bereitstellungsumgebungen können über den manuellen Befehl `deploy` oder mithilfe einer DevOps-Toolchain verwendet werden.

Wenn Sie bei {{site.data.keyword.cloud_notm}} angemeldet sind, können Sie die lokale App mit einer bereits in {{site.data.keyword.cloud_notm}} vorhandenen App verbinden oder eine neue {{site.data.keyword.cloud_notm}}-App erstellen. Die Vorteile von {{site.data.keyword.cloud_notm}}-Features wie Services und DevOps-Toolchains können Sie nur mit einer App in {{site.data.keyword.cloud_notm}} nutzen. Wird eine {{site.data.keyword.cloud_notm}}-App für eine vom Git-Repository geklonte App erstellt, enthält die {{site.data.keyword.cloud_notm}}-App das Repository in der zugehörigen Konfiguration. 

Der Befehl `enable` ist ein Beta-Feature. Wenn Sie Probleme mit dem Befehl `enable` haben, lesen Sie die Informationen im Abschnitt [Fehlerbehebung](/docs/cli?topic=cloud-cli-troubleshoot). Insbesondere ist zu beachten, dass `enable` nicht für mobile Apps oder Frameworks konzipiert ist. Bei komplexeren Apps, die mehrere bereitstellbare Assets erzeugen, muss jede Komponente der App einzeln aktiviert werden. 

Führen Sie den folgenden Befehl aus, um eine vorhandene App im aktuellen Verzeichnis zu aktivieren:
```
ibmcloud dev enable
```
{: codeblock}

Das Vorhandensein erforderlicher Dateien macht eine Erkennung der App-Sprache für eine gültige Projektstruktur möglich.  

* Das Vorhandensein der Datei `package.json` gibt eine Node.js-App an.
* Das Vorhandensein einer Datei `package.swift` gibt eine Swift-App an.
* Das Vorhandensein einer Datei `setup.py` oder `requirements.txt` gibt eine Python-App an.
* Das Vorhandensein einer Datei `pom.xml` oder `build.gradle` gibt eine Java&trade;-App an.
	* Das Vorhandensein einer Datei `pom.xml` gibt eine Maven-App an.
	* Das Vorhandensein einer Datei `build.gradle` gibt eine Gradle-App an.

Sie können Sie die erkannte App-Sprache auch mithilfe des Arguments `--language` überschreiben. Nur gültige und vollständige Apps werden unterstützt. Der Befehl 'enable' ändert Ihren Quellcode nicht.

### enable language options
{: #enable-language-options}

Sprachenoptionen sind unter anderem:
* Node
* Swift
* Python
* Java EE (interpretiert als Java&trade; - Java&trade; EE)
* Java-mp (interpretiert als Java&trade; - Java&trade; MicroProfile)
* Java-spring (interpretiert als Java&trade; - Spring Framework)

Dateien, die mit dem Befehl `ibmcloud dev enable` erstellt werden, werden mit der Dateierweiterung `.merge` gespeichert, wenn sie Namenskonflikte mit vorhandenen Dateien im App-Ordner aufweisen.

### Parameter des Befehls 'enable'
{: #enable-parameters}

Die folgenden Parameter können mit dem Befehl `enable` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der App angegeben werden. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `language`
{: #enable-language}

* Parameter zum Angeben der Sprache der zu aktivierenden App.
* Syntax: `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parameter zum Erzwingen der erneuten Aktivierung einer bereits aktivierten App.
* Syntax: `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Parameter zum Verhindern des Erstellens einer App in {{site.data.keyword.cloud_notm}}, während Aktivierungsdateien lokal erstellt werden.
* Syntax: `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

Für die App erforderliche Berechtigungsnachweise zum Aktivieren der Verwendung von gebundenen Services abrufen.

## help
{: #help}

Wenn keine Aktion oder keine Argumente übergeben werden oder wenn die Aktion 'help' angegeben wird, zeigt dieser Befehl standardmäßig einen allgemeinen Hilfetext an. Allgemeine Hilfetexte enthalten eine Beschreibung der Basisargumente sowie eine Liste der verfügbaren Aktionen.  

Führen Sie den folgenden Befehl aus, um allgemeine Hilfeinformationen anzuzeigen:
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

Sie können alle {{site.data.keyword.cloud_notm}}-Apps in einer Ressourcengruppe auflisten.

Führen Sie den folgenden Befehl aus, um Ihre Apps aufzulisten:
```
ibmcloud dev list
```
{: codeblock}

## pipeline-get
{: #pipeline-get}

Zeigen Sie die Details einer Pipeline an.

```
ibmcloud dev pipeline-get [pipelineID] [--json]
```
{: codeblock}

### Parameter des Befehls 'pipeline-get'
{: #pipeline-get-command-parameters}

#### `json`
{: #json-get}

* Parameter, der zum Ausgeben der Pipelindetails im JSON-Format verwendet wird.
* Syntax: `ibmcloud dev pipeline-get [pipelineID] --json`

## pipeline-run
{: #pipeline-run}

Führen Sie eine Pipeline aus.
```
ibmcloud dev pipeline-run [pipelineID] [--stage-id stageID] [--json] 
```
{: codeblock}

### Parameter des Befehls 'pipeline-run'
{: #pipeline-run-command-parameters}

#### `stage-id`
{: #run-stage-id}

* Optionaler Parameter zum Auswählen der auszuführenden Pipeline-Stage.
* Syntax: `ibmcloud dev pipeline-run [pipelineID] --stage-id [stageID]`

#### `json`
{: #json-run}

* Parameter, der zum Ausgaben der Aufrufdetails der Pipeline im JSON-Format verwendet wird.
* Syntax: `ibmcloud dev pipeline-run [pipelineID] --json`

## pipeline-log
{: #pipeline-log}

Zeigen Sie mithilfe des Befehls `pipeline-log` aktuelle Pipelineprotokolle an. 

* Wenn die Pipeline-ID als Argument angegeben wird, werden alle Protokolle für alle Jobs in allen Stages für diese Pipeline gedruckt.
* Wenn das Flag für die Stage-ID gefüllt ist, werden die Protokolle anhand dieser Stage in der Pipeline gefiltert. 
* Wenn die Job-ID mit der Stage-ID angegeben wird, werden die Protokolle allein nach dem Job in der Stage gefiltert. 
* Wenn die Jobausführungs-ID zusammen mit der Stage-ID und der Job-ID angegeben wird, wird eine Suche unter allen verfügbaren Protokollen durchgeführt, die mit der angegebenen Jobausführungs-ID übereinstimmen.

Syntax:
```
ibmcloud dev pipeline-log [pipelineID] [--stage-id stageID] [--job-id jobID] [--job-exec-id jobExecutionID]
```
{: codeblock}

### Parameter des Befehls 'pipeline-log'
{: #pipeline-log-command-parameters}

#### `stage-id`
{: #log-stage-id}

* Parameter, mit dem die Protokolle anhand der Stage-ID gefiltert werden.
* Syntax: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID]`

#### `job-id`
{: #job-id}

* Parameter, mit dem die Protokolle anhand der Job-ID gefiltert werden.
* Erfordert das Flag `stage-id`.
* Syntax: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID]`

#### `job-exec-id`
{: #job-exec-id}

* Parameter, mit dem die Protokolle anhand der Jobausführungs-ID gefiltert werden.
* Erfordert das Flag `stage-id`.
* Erfordert das Flag `job-id`.
* Syntax: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID] --job-exec-id [jobExecutionID]`

## pipeline-open
{: #pipeline-open}

Zeigen Sie die URL für die Pipeline mithilfe des Befehls `pipeline-open` an. Mit dem Befehl `pipeline-open` wird die URL auch in Ihrem Standardbrowser geöffnet.
```
ibmcloud dev pipeline-open [pipelineID]
```
{: codeblock}

## run
{: #run}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können Ihre App mithilfe des Befehls `run` ausführen. Zuerst muss für die App ein Build durchgeführt werden, indem der Befehl `build` verwendet wird. Wenn Sie den Befehl `run` ausführen, wird der Ausführungscontainer gestartet und stellt die Ports bereit, wie durch den Parameter `container-port-map` definiert werden. Der Parameter `run-cmd` kann verwendet werden, um die App aufzurufen, falls die `Dockerfile` des Containers 'run' keinen Eingangspunkt enthält, um diesen Schritt abzuschließen.

Für die Ausführung mit mehreren Containern muss die Anwendung entweder eine [Compose-Datei](https://docs.docker.com/compose/overview/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") enthalten, die in der Datei `cli-config.yml` angegeben ist, oder Sie können mit dem Befehlsparameter `dockerfile-run` eine solche Datei angeben.

Kompilieren Sie zuerst Ihre App:
```
ibmcloud dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen App-Verzeichnis aus, um Ihre App zu starten:
```
ibmcloud dev run
```
{: codeblock}

Geben Sie `STRG-C` ein, um die Sitzung zu beenden.

### Ausführungsbefehlsparameter
{: #run-parameters}

Die folgenden Parameter stehen ausschließlich für den Befehl `run` zur Verfügung
und unterstützen Sie beim Verwalten Ihrer App im Ausführungscontainer. Es gibt [Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `container-name-run`
{: #container-name-run2}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev run --container-name-run [<appName>]`

#### `container-path-run`
{: #container-path-run}

* Gemeinsam zu verwendende Position im Container bei Ausführung.
* Syntax: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Im Container bei Ausführung gemeinsam zu verwendende Position im Hostsystem.
* Syntax: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile für den Ausführungscontainer.
* Wenn Sie eine Ausführung mit mehreren Containern planen, verwenden Sie eine Compose-Datei.
* Wenn Sie mehrere Compose-Dateien verwenden möchten, schließen Sie eine durch Kommas getrennte Liste mit den Dateinamen in doppelte Anführungszeichen ein.
* Syntax: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Syntax: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Zu erstellendes Image aus `dockerfile-run`.
* Syntax: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parameter zum Ausführen von Code im Ausführungscontainer. Verwenden Sie diesen Parameter, wenn Ihr Image Ihre Anwendung startet.
* Syntax: `ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können die Shell innerhalb des Containers 'run' oder 'tools' mit dem Befehl `shell` öffnen.

Führen Sie dazu den folgenden Befehl aus:
```
ibmcloud dev shell
```
{: codeblock}

Die {{site.data.keyword.dev_cli_short}}-CLI öffnet eine interaktive Shell für den Docker-Container der App. Der Standardzielcontainer für den Shell-Befehl wird durch den Wert `container-shell-target` in der Datei `cli-config.yml` definiert, wobei die gültigen Werte `run` oder `tools` lauten. Ist dieser Wert nicht definiert oder wird ein ungültiger Wert angegeben, verwendet der Befehl `shell` standardmäßig den Container `tools`. Der Shellbefehl öffnet den Container zum dem in der Anweisung `WORKDIR` in der entsprechenden Dockerfile angegebenen Verzeichnis. Wenn `WORKDIR` nicht in der Dockerfile aufgelistet ist, wird das Containerstammverzeichnis als Arbeitsverzeichnis verwendet. Weitere Informationen finden Sie in [dieser Referenz](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link").

Alternativ können Sie entweder `run` oder `tools` als Argument an den Befehl übergeben und der jeweilige Container wird aufgerufen und die Shell wird für diesen Container geöffnet. Entsprechend können Sie den Parameter `container-name` verwenden, um den Namen des Containers anzugeben, für den die Shell geöffnet werden soll. Allerdings ist dieses Flag für den Fall reserviert, wenn keine Container ausgeführt werden. Die Argumente `run` und `tools` sind flexibler und ermöglichen Ihnen, zwischen Containern zu wechseln, wenn ein Container aktiv ist. Wenn beispielsweise der Container 'tools' ausgeführt wird und Sie `ibmcloud dev shell run` absetzen, wird der Container `tools` gestoppt und der Container `run` gestartet (bzw. umgekehrt).

Falls der Zielcontainer `run` oder `tools` noch nicht ausgeführt wird, wenn Sie den Befehl `shell` absetzen, wird der Zielcontainer gestartet. Der Standardwert `Cmd` oder `Entrypoint` in der Dockerfile wird jedoch überschrieben, damit anstelle des Serverprozesses direkt die Shell gestartet wird. Auf diese Weise können Sie den Container `run` oder `tools` starten und den Server dann manuell mit Ihren eigenen beliebigen oder angepassten Befehlen starten.

Sie können auch die Shell-Datei angeben, die Sie öffnen möchten, indem Sie den Parameter `container-shell` verwenden. Standardmäßig wird `/bin/sh` verwendet. Wenn Sie lieber die Bash-Shell verwenden möchten, geben Sie als Wert für `container-shell` `/bin/bash` an. Beachten Sie jedoch, dass Bash nicht automatisch in allen Linux&trade;-Varianten verfügbar ist.

Alle zusätzlichen Argumente, die Sie neben Flags an den Befehl übergeben, werden für den auszuführenden Befehl analysiert, wenn die Shell geöffnet wird. Wenn Sie einen Befehl angeben, wird die Shell innerhalb des Containers bei Ausführung des Befehls beendet und an das Terminal zurückgegeben.

Sie können beispielsweise den Linux-Befehl &trade; `ls` innerhalb der Containershell 'tools' ausführen, indem Sie `ibmcloud dev shell tools ls` aufrufen. Sie können auch Flags angeben, die an die Shellbefehlsausführung übergeben werden sollen, indem Sie die Argumente in Anführungszeichen einschließen, z. B. `ibmcloud dev shell "ls -la"`.

### shell-Befehlsparameter
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Der Name des Containers, für den die Shell geöffnet werden soll.
* Syntax: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Gibt an, welche Shell innerhalb des Containers ausgeführt werden soll (der Standardwert ist /bin/sh).
* Syntax: `ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können den Status der Container abfragen, die von der {{site.data.keyword.dev_cli_short}}-CLI verwendet werden, wie durch `container-name-run` und `container-name-tools` definiert.

Führen Sie den folgenden Befehl im aktuellen App-Verzeichnis aus, um den Containerstatus zu überprüfen:
```
ibmcloud dev status
```
{: codeblock}

[Statusbefehlsparameter](#command-parameters)

## stop
{: #stop}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können Ihre Container mithilfe des Befehls `stop` stoppen.

Führen Sie den folgenden Befehl aus, um die Container 'tools' und 'run' wie in Ihrer Datei `cli-config.yml` definiert zu stoppen:
```
ibmcloud dev stop
```
{: codeblock}

Um einen Container zu stoppen, der nicht in der Datei `cli-config.yml` definiert ist, können Sie einen zusätzlichen Befehlszeilenparameter angeben, um ihn zu überschreiben. Wenn keine Container in der Datei `cli-config.yml` oder in der Befehlszeile angegeben sind, wird der Stoppbefehl einfach zurückgegeben.

### Stoppbefehlsparameter
{: #stop-parameters}

Die folgenden Parameter werden für den Befehl `stop` verwendet. Es gibt [Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `container-name-run`
{: #container-name-run}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`
{: #container-name-tools}

* Containername für den Container 'tools'.
* Syntax: `ibmcloud dev stop --container-name-tools [<appName>]`

## test
{: #test}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows&trade; 10 Pro oder höher ausführen.

Sie können Ihre App mithilfe des Befehls `test` testen. Zuerst muss für die App ein Build durchgeführt werden, indem der Befehl `build --debug` verwendet wird. Anschließend wird der Container 'tools' verwendet, um `test-cmd` für die App zu starten.

Kompilieren Sie zuerst Ihre App:
```
ibmcloud dev build --debug
```
{: codeblock}

Führen Sie den folgenden Befehl aus, um Ihre App zu testen:
```
ibmcloud dev test
```
{: codeblock}

### Parameter des Befehls 'test'
{: #test-parameters}

Der folgende Parameter wird ausschließlich mit dem Befehl `test` verwendet. Es gibt [Parameter](#command-parameters), die mit anderen Befehlen gemeinsam genutzt werden.

#### `test-cmd`
{: #test-cmd}

* Parameter zum Angeben eines Befehls zum Testen von Code im Container 'tools'.
* Syntax: `ibmcloud dev test --test-cmd /the/test/command`

## toolchain-delete
{: #toolchain-delete}

Löschen Sie eine Toolchain. Wenn kein Toolchain-Name angegeben ist, können Sie eine Toolchain aus einer Liste auswählen. Die Liste der Toolchains hängt von der aktuell ausgewählten Ressourcengruppe und Region ab.

Die Ressourcengruppe, die als Ziel angegeben ist, befinden sich im API-Schlüssel (`IBMCLOUD API Key`). Weitere Informationen finden Sie unter [Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target).
```
ibmcloud dev toolchain-delete [toolchainName] [--force,-f]
```
{: codeblock}

### Parameter des Befehls 'toolchain-delete'
{: #toolchain-delete-command-parameters}

#### `force`
{: #force}

* Parameter zum Überspringen der Eingabeaufforderungsbestätigung zum Löschen einer Toolchain.
* Syntax: `ibmcloud dev toolchain-delete [toolchainName] --force`

## toolchain-get
{: #toolchain-get}

Zeigen Sie die Details einer Toolchain an. Wenn kein Toolchain-Name angegeben ist, können Sie eine Toolchain aus einer Liste auswählen.  

Verwendet die Zielressourcengruppe im API-Schlüssel (`IBMCLOUD API Key`). Weitere Informationen finden Sie unter [Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target). Einige Cloud Foundry-basierten Toolchains sind möglicherweise nicht mit diesem Befehl kompatibel.
```
ibmcloud dev toolchain-get [toolchainName] [--json]
```
{: codeblock}

### Parameter des Befehls 'toolchain-get'
{: #toolchain-get-command-parameters}

#### `json`
{: #json-toolchain-get}

* Parameter, der zum Ausgeben der Toolchain-Details im JSON-Format verwendet wird.
* Syntax: `ibmcloud dev toolchain-get [toolchainName] --json`.

## toolchain-open
{: #toolchain-open}

Zeigen Sie die URL für die Toolchain mithilfe des Befehls `toolchain-open` an. Mit dem Befehl `toolchain-open` wird die URL auch in Ihrem Standardbrowser geöffnet. Wenn kein Toolchain-Name angegeben ist, können Sie eine Toolchain aus einer Liste auswählen.
```
ibmcloud dev toolchain-open [toolchainName]
```
{: codeblock}

## toolchains
{: #toolchains}

Zeigen Sie eine Liste der Toolchains in der aktuellen Ressourcengruppe an. 

Verwendet die Zielressourcengruppe im API-Schlüssel (`IBMCLOUD API Key`). Weitere Informationen finden Sie unter [Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target). Einige Cloud Foundry-basierten Toolchains sind möglicherweise nicht mit diesem Befehl kompatibel.
```
ibmcloud dev toolchains [--json]
```
{: codeblock}

### Parameter des Befehls 'toolchains'
{: #toolchains-command-parameters}

#### `json`
{: #json-toolchains}

* Parameter, der zum Ausgeben der Toolchains im JSON-Format verwendet wird.
* Syntax: `ibmcloud dev toolchains --json`

## view
{: #view}

Mit dem Befehl `view` können Sie die URL anzeigen, unter der Ihre App bereitgestellt wird. Führen Sie diesen Befehl im Stammverzeichnis der App aus, die Sie anzeigen möchten. Der Befehl `view` öffnet die URL auch in Ihrem Standardbrowser.

Bei Apps, die in Cloud Foundry bereitgestellt werden, besteht die URL aus dem Hostnamen und der Domäne der App.

Bei Apps, die in Kubernetes bereitgestellt werden, besteht die URL aus der IP-Adresse des Knotens, unter dem sie bereitgestellt wird, und dem öffentlichen Port. Wenn der Befehl feststellt, dass die App in Kubernetes bereitgestellt wurde, fordert das CLI-Tool eine Bestätigung an. Wenn Sie angeben, dass die App nicht in Kubernetes bereitgestellt wurde, wird die Cloud Foundry-URL angezeigt. Falls Sie erwartet haben, dass der Befehl die URL für eine in Kubernetes bereitgestellte App anzeigt, dies jedoch nicht der Fall ist, müssen Sie entweder sicherstellen, dass die Datei `cli-config.yml` einen Eingangspunkt für `chart-path` enthält, oder Sie müssen diesen über die Befehlszeile angeben, wie [hier](#chart-path) gezeigt.

Führen Sie den folgenden Befehl aus, um Ihre App anzuzeigen:
```
ibmcloud dev view
```
{: codeblock}

### Parameter des Befehls 'view'
{: #view-parameters}

Die folgenden Parameter werden ausschließlich mit dem Befehl `view` verwendet.

#### `deploy-target`
{: #commands-deploy-target}

* Parameter zum Angeben des Typs von Bereitstellung, um die Eingabeaufforderung zu umgehen.
* Syntax: `ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* Parameter, der angibt, dass der Browser nicht geöffnet werden soll.
* Syntax: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Stammverzeichnis des Projekts, das an die URL der Cloud Foundry- und Kubernetes-App angehängt werden soll.
* Syntax: `ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung.
* Syntax: `ibmcloud dev view --ibm-cluster [cluster-name]`

## Zusammengesetzte Befehle
{: #compound}

Sie können mehrere Befehle in einer einzelnen Befehlszeilenanweisung ausführen, indem Sie die Befehle der {{site.data.keyword.cloud_notm}}-Entwicklertools durch den Begrenzer `/` trennen. Weitere Befehlszeilenflags können im Anschluss an die zusammengesetzten Befehle angegeben werden. Die folgenden Befehle sind Beispiele für die Verwendung von zusammengesetzten Befehlen:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Alle Flags müssen auf den finalen Befehl folgen und werden auf alle Befehle angewendet, denen das jeweilige Flag zugeordnet ist. Beispiel: Durch den Befehl `ibmcloud dev build/deploy/view -t container --trace` wird das Flag `--trace` auf alle drei Befehle angewendet, während der Befehl `-t` nur auf die beiden letzten Befehle angewendet wird und nicht auf den Befehl `build`.

Dies sind die Befehle, die mit diesem Feature verwendet werden können:
`build, debug, deploy, get-credentials, run, stop, test, view`

Falls ein Befehl fehlschlägt, werden die nachfolgenden Befehle nicht ausgeführt.

Falls Befehle auf `debug` oder `run` folgen, wird die Ausführung nur fortgesetzt, wenn `debug` oder `run` auf andere Weise als durch Beenden des Prozesses im aktuellen Terminalfenster abgebrochen wird. Geben Sie `STRG+C` ein, um den Prozess zu beenden, und führen Sie die nachfolgenden Befehle nicht aus. Sie können `ibmcloud dev stop` beispielsweise in einem anderen Terminalfenster ausführen, um den laufenden Container zu stoppen und die Ausführung des nachfolgenden Befehls fortzusetzen.

## Parameter für 'build', 'debug', 'run' und 'test'
{: #command-parameters}

Die folgenden Parameter können mit den Befehlen `build|debug|run|test` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der App angegeben werden. Zusätzliche Parameter sind für die Befehle [`debug`](#debug-parameters) und [`run`](#run-parameters) verfügbar.

Befehlsparameter, die in der Befehlszeile eingegeben werden, haben Vorrang vor der `cli-config.yml`-Konfiguration.
{: note}

#### `config-file`  
{: #config-file}

* Geben Sie eine Datei `cli-config.yml` für die Verwendung mit einem Befehl an.
* Syntax: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev <run|status|stop> --container-name-run [<appName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Containername für den Container 'tools'.
* Syntax: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<appName>]`

#### `host-path-tools`
{: #host-path-tools}

* Gemeinsam zu verwendende Position auf dem Host für 'build', 'debug', 'test'.
* Syntax: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Gemeinsam zu verwendende Position im Container für 'build', 'debug', 'test'.
* Syntax: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Portzuordnungen für den Container. Der erste Wert ist der Port, der im Hostbetriebssystem verwendet werden soll, der zweite Wert ist der Port im Container [`host-port:container-port`].
* Syntax: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile für den Container 'tools'.
* Syntax: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Zu erstellendes Image aus `dockerfile-tools`.
* Syntax: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Verwenden Sie diese Option, um Mounts zwischen dem Hostsystem und dem Container 'run' zu definieren.
* Die Werte `host-path-run` und `container-path-run` werden am Anfang dieser Liste eingefügt.
* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist die Verwendung derselben Mounteinstellungen für 'build' und 'run'.
* Syntax: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Verwenden Sie diese Option, um Mounts zwischen dem Hostsystem und dem Container 'tools' zu definieren.
* Die Werte `host-path-tools` und `container-path-tools` werden am Anfang dieser Liste eingefügt.* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist die Verwendung derselben Mounteinstellungen für 'build' und 'debug'.
* Syntax: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parameter zum Angeben eines Befehls zum Erstellen von Code für alle Verwendungszwecke außer DEBUG.
* Syntax: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Verwenden Sie diesen Parameter, um eine ausführliche Ausgabe bereitzustellen.
* Syntax: `ibmcloud dev <build|debug|run|test> --trace`
