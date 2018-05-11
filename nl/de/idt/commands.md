---
copyright:
years: 2017, 2018
lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}}-CLI-Befehle (bx dev)
{: #idt-cli}

Version: 1.2.0
Freigegeben: 8. März 2018

Verwenden Sie die folgenden {{site.data.keyword.dev_cli_notm}}-CLI-Befehle (bx dev), um ein Projekt zu erstellen, bereitzustellen, zu debuggen und zu testen.

- [build](#build): Erstellt das Projekt in einem lokalen Container.
- [code](#code): Lädt Code aus einem Projekt herunter.
- [console](#console): Öffnet die IBM Cloud-Konsole für ein Projekt.
- [create](#create): Erstellt ein neues Projekt und bietet die Möglichkeit, Services hinzuzufügen.
- [debug](#debug): Debuggt Ihre Anwendung in einem lokalen Container.
- [delete](#delete): Löscht ein Projekt aus Ihrem Bereich.
- [deploy](#deploy): Stellt eine Anwendung in IBM Cloud bereit.
- [enable](#enable): Fügt IBM Cloud-Dateien zu einem vorhandenen Projekt hinzu.
- [get-credentials](#get-credentials): Ruft für das Projekt erforderliche Berechtigungsnachweise ab, um die Nutzung gebundener Services zu aktivieren. 
- [help](#help): Hilfe zu IDT-Syntax und -Argumenten
- [list](#list): Listet alle IBM Cloud-Projekte in einem Bereich auf.
- [run](#run): Führen Sie Ihre Anwendung in einem lokalen Container aus.
- [shell](#shell): Öffnet eine Shell in einem lokalen Container.
- [status](#status): Prüft den Status der von der Befehlszeilenschnittstelle verwendeten Container. 
- [stop](#stop): Stoppt einen Container.
- [test](#test): Testet Ihre Anwendung in einem lokalen Container.
- [view](#view): Zeigt die bereitgestellte URL der App zum Testen und Anzeigen an. 
- [compound commands](#compound): Führt mehrere Befehle in einer Befehlszeilenanweisung aus. 



## build
{: #build}

Sie können Ihre Anwendung mithilfe des Befehls `build` erstellen. Die Befehle `test`, `debug` und `run` setzen ein kompiliertes Projekt voraus, deshalb müssen Sie zunächst eine `build`-Operation ausführen.  

Das Konfigurationselement `build-cmd-debug` wird zum Erstellen der Anwendung für alle Verwendungszwecke, mit Ausnahme von `run`, verwendet. Sie erstellen Ihre Anwendung für das Debuggen, indem Sie die Befehlszeilenoption `--debug` angeben.  Das Konfigurationselement `build-cmd-run` wird beim Erstellen der Anwendung für den Einsatz mit dem Befehl `run` verwendet. 

Für eine Erstellung mit mehreren Containern muss Ihr Projekt entweder eine [Compose](https://docs.docker.com/compose/overview/)-Datei enthalten, die in der `cli-config.yml` angegeben ist, oder Sie können den Befehlsparameter `dockerfile-tools` verwenden, um eine anzugeben. Weitere Informationen finden Sie unter [Compose-Datei](/docs/apps/projects/compose_file.html).

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu erstellen:  

```
bx dev build [--debug]
```
{: codeblock}


[Buildbefehlsparameter](#command-parameters)


## code
{: #code}

Verwenden Sie den Befehl `code`, um ein zuvor erstelltes Projekt mit Anwendungsvorlagencode und Konfigurationsdateien für {{site.data.keyword.Bluemix_notm}} herunterzuladen.  Dies ist nützlich, wenn Sie eine zweite Kopie eines von Ihnen erstellten Projekts extrahieren müssen. 

Führen Sie den folgenden Befehl aus, um den Code aus einem angegebenen Projekt herunterzuladen.

```
bx dev code <projektname>
```
{: codeblock}


## console
{: #console}

Verwenden Sie den Befehl `console`, um in einem Web-Browser die Webkonsole Ihrer Anwendung unter IBM Cloud zu öffnen.  Sie können den Befehl `bx dev console` aus dem Ordner Ihres Projekts heraus ausführen und die Befehlszeilenschnittstelle versucht, ein passendes Projekt in der IBM Cloud zu finden, das dieselbe Projekt-ID wie das aktuelle Verzeichnis hat. Falls das System keinen passenden Namen finden kann, wird statt des spezifischen Projekts das Dashboard für Web-Apps und mobile Apps in IBM Cloud geöffnet.

Sie können einen Projektnamen bereitstellen und die Befehlszeilenschnittstelle überspringt den Abgleich auf der Grundlage des Ordner-/Anwendungsnamens. In diesem Fall öffnet die Befehlszeilenschnittstelle die Konsole des genannten Projekts in einem Web-Browser.  

Führen Sie den folgenden Befehl aus, um einen Web-Browser in der Webkonsole Ihrer Anwendung zu öffnen.

```
bx dev console [projectName]
```
{: codeblock}


## create
{: #create}

Erstellen Sie ein Projekt, wobei Sie zur Angabe aller Informationen wie Ressourcentyp, Sprache, Starter-Kit und DevOps-Toolchainoptionen aufgefordert werden. Das Projekt wird im aktuellen Verzeichnis erstellt.

Führen Sie den folgenden Befehl aus, um ein Projekt im aktuellen Verzeichnis zu erstellen und ihm Services zuzuordnen:

```
bx dev create
```
{: codeblock}


## debug
{: #debug}

Sie können Ihre Anwendung mithilfe des Befehls `debug` debuggen. Zunächst muss ein Build für das Projekt fertiggestellt werden, indem Sie den Buildbefehl mit dem Argument `--debug` absetzen. Wenn Sie den Befehl `debug` starten, wird ein Container gestartet, der einen oder mehrere Debugports bereitstellt, wie im Wert `container-port-map-debug` in der cli-config.yml definiert bzw. wie in der Befehlszeile angegeben. Verbinden Sie Ihr bevorzugtes Debugging-Tool mit dem Port oder den Ports und Sie können Ihre Anwendung wie üblich debuggen.

Kompilieren Sie zunächst Ihr Projekt:

```
bx dev build --debug
```
{: codeblock}

Führen Sie zunächst den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu debuggen:

```
bx dev debug
```
{: codeblock}

Um das Debugging auszuführen, hängen Sie Ihr Debugging-Tool an den angegebenen Port an.

Geben Sie `STRG-C` ein, um die Debugsitzung zu beenden.


### Debugbefehlsparameter
{: #debug-parameters}

Die folgenden Parameter stehen ausschließlich dem Befehl `debug` zur Verfügung und
unterstützen Sie beim Debugging einer Anwendung. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `container-port-map-debug`
{: #port-map-debug}

* Portzuordnungen für den Debugport. Der erste Wert ist der Port, der im Hostbetriebssystem verwendet werden soll, der zweite Wert ist der Port im Container [host-port:container-port].
* Verwendung: `bx dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parameter zum Erstellen von Code für DEBUG.
* Verwendung: `bx dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parameter zum Angeben eines Befehls zum Aufrufen des Debuggers im Toolscontainer. Verwenden Sie diesen Parameter, wenn `build-cmd-debug` Ihre Anwendung im Debugger startet.
* Verwendung: `bx dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Setzen Sie den Befehl `delete` ab, um Projekte aus Ihrem {{site.data.keyword.Bluemix}}-Bereich zu entfernen. Sie können den Befehl ohne Parameter ausführen, um verfügbare Projekte aufzulisten und das zu löschende Projekt in der nummerierten Liste auszuwählen. Projektcode und -verzeichnisse werden nicht aus Ihrem lokalen Festplattenspeicher gelöscht.

Führen Sie den folgenden Befehl aus, um Ihr Projekt aus {{site.data.keyword.Bluemix}} zu löschen:

```
bx dev delete <projektname>
```
{: codeblock}


**Hinweis:** {{site.data.keyword.Bluemix}}-Services werden **nicht** entfernt.


## deploy
{: #deploy}

Sie können eine Anwendung als Cloud Foundry-Anwendung oder als Container bereitstellen.

Um eine Anwendung als Cloud Foundry-Anwendung in {{site.data.keyword.Bluemix}} bereitzustellen, muss eine `manifest.yml`-Datei im Stammverzeichnis Ihres Projekts vorhanden sein.

Um eine Anwendung als Container bereitzustellen, müssen Sie [Kubernetes](https://kubernetes.io/) und [Helm](https://github.com/kubernetes/helm) lokal installieren. Stellen Sie sicher, dass die Version des Helm-Clients nicht aktueller als die Helm-Serverversion ist. Beide Angaben erhalten Sie, indem Sie `helm version` ausführen. Wir empfehlen Version 2.4.2 für den Client.

In der `cli-config.yml` können Sie die Position eines Helm-Diagramms in der Eigenschaft `chart-path` definieren, das Element `deploy-target` auf `container` festlegen und `deploy-image-target` wie im Beispiel gezeigt definieren. Das Element `deploy-image-target` in der `cli-config.yml` wird statt der Elemente `repository` und `tag` in der Datei `chart/values.yml` verwendet. Um gezielt in {{site.data.keyword.Bluemix}} bereitzustellen, legen Sie das Konfigurationselement `ibm-cluster` auf den Namen des Kubernetes-Clusters fest, den Sie in {{site.data.keyword.Bluemix}} erstellt haben, wie im [Lernprogramm: Cluster erstellen](/docs/containers/cs_tutorials.html#cs_cluster_tutorial) beschrieben.

Weitere Informationen zur Bereitstellung, Konfiguration und Implementierung in einem Kubernetes-Cluster finden Sie im Lernprogramm [Skalierbare Webanwendung in Kubernetes bereitstellen](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud-Region>.bluemix.net/<Containerregistry-Namensbereich>/<App-Name>"

    ibm-cluster: "mycluster"
```

Wenn Sie diese in der cli-config.yml nicht konfigurieren, müssen Sie die Bereitstellung mit dem Parameter `-t container` durchführen und werden aufgefordert, alle anderen Werte anzugeben.

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu erstellen:  

```
bx dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihr Projekt bereitzustellen:

```
bx dev deploy
```
{: codeblock}


### Bereitstellungsbefehlsparameter
{: #deploy-parameters}

Die folgenden Parameter können mit dem Befehl `deploy` verwendet werden oder indem Sie die Datei `cli-config.yml` des Projekts direkt aktualisieren. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `chart-path`
{: #chart-path}

* Parameter für eine Containerbereitstellung zur Angabe der Position des Helm-Diagramms, das für die Bereitstellung verwendet wird.
* Verwendung: `bx dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Optionaler Parameter zum Angeben des Typs der fertigzustellenden Bereitstellung.  Der Standardbereitstellungstyp ist ein Buildpack.
* Verwendung: `bx dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter zur Verwendung mit einer Containerbereitstellung als Zielimagename für die Bereitstellung (z. B. zum Kennzeichnen einer Docker-Registry).  Der Wert darf keine Version enthalten, z. B.: image-name:{version}, weil die Version von `deploy` inkrementiert und angehängt wird.
* Verwendung: `bx dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Optionaler Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung in {{site.data.keyword.Bluemix}}.
* Verwendung: `bx dev deploy --ibm-cluster [cluster-name]`


## enable
{: #enable}

Aktivieren Sie ein vorhandenes Projekt für die {{site.data.keyword.Bluemix_notm}}-Bereitstellung. Der Befehl `enable` versucht, die Sprache eines vorhandenen Projekts automatisch zu erkennen und dann zur Angabe weiterer Informationen aufzufordern. Dadurch werden Dateien generiert und hinzugefügt, die für lokale Docker-Container, für eine CloudFoundry-Bereitstellung oder für eine Kubernetes-/Container-Bereitstellung verwendet werden können.

Führen Sie den folgenden Befehl aus, um ein vorhandenes Projekt im aktuellen Verzeichnis für die {{site.data.keyword.Bluemix_notm}}-Bereitstellung zu aktivieren:

```
bx dev enable
```
{: codeblock}

Das Vorhandensein erforderlicher Dateien macht eine Erkennung der Projektsprache für eine gültige Projektstruktur möglich.  

* Das Vorhandensein einer Datei `package.json` gibt ein Node.js-Projekt an.
* Das Vorhandensein einer Datei `package.swift` gibt ein Swift-Projekt an.
* Das Vorhandensein einer Datei `setup.py` oder `requirements.txt` gibt ein Python-Projekt an.
* Das Vorhandensein einer Datei `pom.xml` oder `build.gradle` gibt ein Java-Projekt an.
	* Das Vorhandensein einer Datei `pom.xml` gibt ein Maven-Projekt an.
	* Das Vorhandensein einer Datei `build.gradle` gibt ein Gradle-Projekt an.

Optional können Sie auch die erkannte Projektsprache mithilfe des Arguments `--language` überschreiben.  Allerdings werden nur gültige und abgeschlossene Projekte unterstützt. Der Befehl 'enable' ändert Ihren Quellcode nicht.

Sprachenoptionen sind unter anderem:
* node
* swift
* python
* java-ee (interpretiert als Java - Java EE)
* java-mp (interpretiert als Java - Java MicroProfile)
* java-spring (interpretiert als Java - Spring Framework)

Mit dem Befehl `bx dev enable` erstellte Dateien, die Namenskonflikte mit vorhandenen Dateien im Projektordner aufweisen, werden mit einer Dateierweiterung `.merge` gespeichert.  

### Aktivierungsbefehlsparameter
{: #enable-parameters}

Die folgenden Parameter können mit dem Befehl `enable` verwendet werden oder indem Sie die Datei `cli-config.yml` des Projekts direkt aktualisieren. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `language`
{: #enable-language}

* Parameter zum Angeben der Sprache des zu aktivierenden Projekts.
* Verwendung: `bx dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parameter zum Erzwingen einer erneuten Aktivierung eines bereits aktivierten Projekts.
* Verwendung: `bx dev enable -f|--force`


## get-credentials
{: #get-credentials}

Ruft für das Projekt erforderliche Berechtigungsnachweise ab, um die Nutzung gebundener Services zu aktivieren.


## help
{: #help}

Wenn keine Aktion oder keine Argumente übergeben werden oder wenn die Aktion 'help' angegeben wird, zeigt dieser Befehl standardmäßig einen allgemeinen Hilfetext an. Allgemeine Hilfetexte enthalten eine Beschreibung der Basisargumente sowie eine Liste der verfügbaren Aktionen.  

Führen Sie den folgenden Befehl aus, um allgemeine Hilfeinformationen anzuzeigen:

```
bx dev help
```
{: codeblock}


## list
{: #list}

Sie können alle {{site.data.keyword.Bluemix_notm}}-Projekte in einem Bereich auflisten.

Führen Sie den folgenden Befehl aus, um Ihre Projekte aufzulisten:

```
bx dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
bx dev edit
```
{: codeblock}
-->


## run
{: #run}

Sie können Ihre Anwendung mithilfe des Befehls `run` ausführen. Zunächst muss ein Build für das Projekt fertiggestellt werden, indem Sie den Befehl `build` absetzen. Wenn Sie den Befehl `run` aufrufen, wird der Ausführungscontainer gestartet und stellt die Ports bereit, wie durch den Parameter `container-port-map` definiert. Der Parameter `run-cmd` kann verwendet werden, um die Anwendung aufzurufen, falls die Dockerfile des Ausführungscontainers keinen Eingangspunkt umfasst, um diesen Schritt abzuschließen.

Für eine Ausführung mit mehreren Containern sollte Ihr Projekt entweder eine [Compose](https://docs.docker.com/compose/overview/)-Datei enthalten, die in der `cli-config.yml` angegeben ist, oder Sie können den Befehlsparameter `dockerfile-run` verwenden, um eine anzugeben. Weitere Informationen finden Sie unter [Compose-Datei](/docs/apps/projects/compose_file.html).

Kompilieren Sie zunächst Ihr Projekt:

```
bx dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um Ihre Anwendung zu starten:

```
bx dev run
```
{: codeblock}

Geben Sie `STRG-C` ein, um die Sitzung zu beenden.


### Ausführungsbefehlsparameter
{: #run-parameters}

Die folgenden Parameter stehen ausschließlich dem Befehl `run` zur Verfügung und
unterstützen Sie beim Verwalten Ihrer Anwendung im Ausführungscontainer.
Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `container-name-run`
{: #container-name-run}

* Containername für den Ausführungscontainer.
* Verwendung: `bx dev run --container-name-run [<projectName>]`

#### `container-path-run`
{: #container-path-run}

* Gemeinsam zu verwendende Position im Container bei Ausführung.
* Verwendung: `bx dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Im Container bei Ausführung gemeinsam zu verwendende Position im Hostsystem.
* Verwendung: `bx dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile für den Ausführungscontainer.
* Wenn Sie eine Ausführung mit mehreren Containern planen, sollte dies eine Compose-Datei sein.
* Um mehrere Compose-Dateien zu verwenden, schließen Sie eine durch Kommas begrenzte Liste der Dateinamen in doppelte Anführungszeichen ein.
* Verwendung: `bx dev run --dockerfile-run [/path/to/Dockerfile]`
* Verwendung: `bx dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Zu erstellendes Image aus `dockerfile-run`.
* Verwendung: `bx dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parameter zum Ausführen von Code im Ausführungscontainer. Verwenden Sie diesen Parameter, wenn Ihr Image Ihre Anwendung startet.
* Verwendung: `bx dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

Sie können die Shell innerhalb des Ausführungs- oder Toolscontainers mit dem Befehl `shell` öffnen.

Führen Sie einfach diesen Befehl aus:

```
bx dev shell
```

Die {{site.data.keyword.dev_cli_short}}-CLI öffnet eine interaktive Shell in den Docker-Container der Anwendung. Der Standardzielcontainer für den Shell-Befehl wird durch den Wert `container-shell-target` in der Datei `cli-config.yml` definiert, wobei die gültigen Werte `run` oder `tools` lauten. Ist dieser Wert nicht definiert oder wird ein ungültiger Wert angegeben, verwendet der Befehl `shell` standardmäßig den Container `tools`. Der Shellbefehl öffnet den Container zum dem in der Anweisung `WORKDIR` in der entsprechenden Dockerfile angegebenen Verzeichnis. Wenn `WORKDIR` nicht in der Dockerfile aufgelistet ist, wird das Containerstammverzeichnis als Arbeitsverzeichnis verwendet. Weitere Informationen finden Sie in dieser [Referenz](https://docs.docker.com/engine/reference/builder/#workdir).

Alternativ können Sie entweder `run` oder `tools` als Argument an den Befehl übergeben und der jeweilige Container wird aufgerufen und die Shell für diesen Container wird geöffnet. Entsprechend können Sie den Parameter `container-name` verwenden, um den Namen des Containers zu übergeben, in dem Sie eine Shell öffnen möchten. Allerdings sollte dieses Flag für den Fall reserviert sein, wenn keine Container ausgeführt werden. Die Argumente `run` und `tools` sind flexibler und ermöglichen Ihnen, zwischen Containern zu wechseln, wenn einer aktuell ausgeführt wird. Wenn beispielsweise der Container 'tools' ausgeführt wird und Sie `bx dev shell run` absetzen, wird der Container `tools` gestoppt und der Container `run` gestartet und umgekehrt.

Falls der Zielcontainer `run` oder `tools` noch nicht ausgeführt wird, wenn Sie den Befehl `shell` absetzen, wird der Zielcontainer gestartet. Dabei wird jedoch der Standardwert `Cmd` oder `Entrypoint` in der Dockerfile überschrieben, um die Shell direkt zu öffnen, statt den Serverprozess zu starten. Auf diese Weise können Sie den Container `run` oder `tools` starten und den Server manuell mit Ihren eigenen beliebigen oder angepassten Befehlen starten.


Sie können auch die ausführbare Shelldatei angeben, die Sie öffnen möchten, indem Sie den Parameter `container-shell` verwenden. Standardmäßig wird `/bin/sh` verwendet. Wenn Sie lieber die Bash-Shell verwenden, geben Sie als Wert für `container-shell` `/bin/bash` an. Beachten Sie jedoch, dass Bash nicht automatisch in allen Linux-Varianten verfügbar ist.

Alle zusätzlichen Argumente, die Sie neben Flags an den Befehl übergeben, werden für den auszuführenden Befehl analysiert, wenn die Shell geöffnet wird. Wenn Sie einen auszuführenden Befehl angeben, wird die Shell innerhalb des Containers bei Ausführung des Befehls beendet und an das Terminal zurückgegeben.

Sie können beispielsweise den Linux-Befehl `ls` innerhalb der Containershell 'tools' ausführen, indem Sie `bx dev shell tools ls` aufrufen.   Sie können auch zusätzliche Flags angeben, die an die Shellbefehlsausführung übergeben werden sollen, indem Sie die Argumente in Anführungszeichen einschließen, z. B. `bx dev shell "ls -la"`.

### shell-Befehlsparameter
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Name des Containers, dessen Shell Sie öffnen möchten.
* Verwendung: `bx dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Gibt an, welche Shell innerhalb des Containers ausgeführt werden soll (Standardwert ist '/bin/sh').
* Verwendung: `bx dev shell --container-shell [path/to/shell]`


## status
{: #status}

Sie können den Status der Container abfragen, die von der {{site.data.keyword.dev_cli_short}}-CLI verwendet werden, wie durch `container-name-run` und `container-name-tools` definiert. 

Führen Sie den folgenden Befehl in Ihrem aktuellen Projektverzeichnis aus, um den Containerstatus zu prüfen:

```
bx dev status
```
{: codeblock}


[Statusbefehlparameter](#command-parameters)


## stop
{: #stop}

Sie können Ihre Container mithilfe des Befehls `stop` stoppen.

Führen Sie den folgenden Befehl aus, um die Container 'tools' und 'run' wie in Ihrer Datei `cli-config.yml` definiert zu stoppen:

```
bx dev stop
```
{: codeblock}

Um einen Container zu stoppen, der nicht in der Datei `cli-config.yml` definiert ist, können Sie einen zusätzlichen Befehlszeilenparameter angeben, um ihn zu überschreiben.  Wenn keine Container in der Datei `cli-config.yml` oder in der Befehlszeile angegeben sind, wird der Stoppbefehl einfach zurückgegeben.

### Stoppbefehlsparameter
{: #stop-parameters}

Die folgenden Parameter werden für den Befehl `stop` verwendet. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `container-name-run`
{: #container-name-run}

* Containername für den Container 'run'.
* Verwendung: `bx dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* Containername für den Container 'tools'.
* Verwendung: `bx dev stop --container-name-tools [<projectName>]`



## test
{: #test}

Sie können Ihre Anwendung mithilfe des Befehls `test` stoppen. Zunächst muss ein Build für das Projekt fertiggestellt werden, indem Sie den Befehl `build --debug` absetzen. Der Container 'tools' wird dann verwendet, um `test-cmd` für die Anwendung aufzurufen.

Kompilieren Sie zunächst Ihr Projekt:

```
bx dev build --debug
```
{: codeblock}

Führen Sie den folgenden Befehl aus, um Ihre Anwendung zu testen:

```
bx dev test
```
{: codeblock}


### Testbefehlsparameter
{: #test-parameters}

Der folgende Parameter wird ausschließlich mit dem Befehl `test` verwendet.  Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `test-cmd`
{: #test-cmd}

* Parameter zum Angeben eines Befehls zum Testen von Code im Container 'tools'.
* Verwendung: `bx dev test --test-cmd /the/test/command`


## view
{: #view}

Mit dem Befehl `view` können Sie die URL anzeigen, unter der Ihre Anwendung bereitgestellt wird. Führen Sie diesen Befehl im Stammverzeichnis der Anwendung aus, die Sie anzeigen möchten. Der Befehl `view` öffnet die URL auch in Ihrem Standardbrowser.

Bei Anwendungen, die in Cloud Foundry bereitgestellt werden, besteht die URL aus dem Hostnamen und der Domäne der Anwendung.

Bei Anwendungen, die in Kubernetes bereitgestellt werden, besteht die URL aus der IP-Adresse des Knotens, unter dem sie bereitgestellt wird, und dem öffentlichen Port. Wenn der Befehl feststellt, dass die App in Kubernetes bereitgestellt wurde, wird das CLI-Tool eine Bestätigung anfordern. Wenn Sie angeben, dass die Anwendung nicht in Kubernetes bereitgestellt wurde, wird die Cloud Foundry-URL angezeigt. Falls Sie erwartet haben, dass der Befehl die URL für eine in Kubernetes bereitgestellte Anwendung anzeigt, dies aber nicht der Fall ist, müssen Sie entweder sicherstellen, dass die `cli-config.yml` einen Eingangspunkt für `chart-path` enthält oder Sie müssen diesen wie [hier](#chart-path) gezeigt über die Befehlszeile angeben.

Führen Sie den folgenden Befehl aus, um Ihre Anwendung anzuzeigen:

```
bx dev view
```
{: codeblock}

### Anzeigebefehlsparameter
{: #view-parameters}

Die folgenden Parameter werden ausschließlich mit dem Befehl `view` verwendet.

#### `deploy-target`

* Optionaler Parameter zum Angeben des Typs von Bereitstellung, um die Eingabeaufforderung zu umgehen.
* Verwendung: `bx dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Parameter, der angibt, dass der Browser nicht geöffnet werden soll.
* Verwendung: `bx dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Stammverzeichnis des Projekts, das an die URL der Kubernetes-App angehängt werden soll.
* Verwendung: `bx dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster}

* Optionaler Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung.
* Verwendung: `bx dev view --ibm-cluster [cluster-name]`


## Zusammengesetzte Befehle
{: #compound}

Sie können mehrere Befehle in einer Befehlszeilenanweisung ausführen, indem Sie die einzelnen IDT-Befehle mit dem Begrenzungszeichen `/` trennen. Zusätzliche Befehlszeilenflags können im Anschluss an die zusammengesetzten Befehle angegeben werden.  Die folgenden Befehle sind Beispiele für die Verwendung von zusammengesetzten Befehlen:

```
bx dev build/run
bx dev build/deploy --trace -t buildpack
bx dev build/debug --debug --trace
bx dev build/deploy/view -t container --trace
```
{: codeblock}

Alle Flags müssen auf den finalen Befehl folgen und werden auf alle Befehle angewendet, denen das jeweilige Flag zugeordnet ist. In dem vorstehenden Beispiel gilt das Flag `--trace` für alle drei Befehle, während das Flag `-t` nur für die letzten zwei Befehle gilt und deshalb nicht auf den Befehl `build` angewendet wird.

Dies sind die Befehle, die mit diesem Feature verwendet werden können:
`build, debug, deploy, get-credentials, run, stop, test, view`

Falls ein Befehl fehlschlägt, werden die nachfolgenden Befehle nicht ausgeführt. Falls Befehle auf `debug` oder `run` folgen, wird die Ausführung nur fortgesetzt, wenn `debug` oder `run` auf andere Weise beendet wird als dass der Prozess im aktuellen Terminalfenster abgebrochen wird. `STRG+C` bricht den Prozess ab und die nachfolgenden Befehle werden nicht ausgeführt. Sie können beispielsweise `bx dev stop` in einem anderen Terminalfenster ausführen, um den laufenden Container zu stoppen und die Ausführung des nachfolgenden Befehls fortzusetzen.


## Parameter für 'build', 'debug', 'run' und 'test'
{: #command-parameters}

Die folgenden Parameter können mit den Befehlen `build|debug|run|test` verwendet werden oder indem Sie die Datei `cli-config.yml` des Projekts direkt aktualisieren. Zusätzliche Parameter sind für die Befehle [`debug`](#debug-parameters) und [`run`](#run-parameters) verfügbar.

**Hinweis**: Befehlsparameter, die in der Befehlszeile eingegeben werden, haben Vorrang vor der `cli-config.yml`-Konfiguration.

#### `config-file`  
{: #config-file}

* Geben Sie eine Datei 'cli-config.yml' für die Verwendung mit einem Befehl an.
* Verwendung: `bx dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run}

* Containername für den Container 'run'.
* Verwendung: `bx dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools}

* Containername für den Container 'tools'.
* Verwendung: `bx dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

#### `host-path-tools`
{: #host-path-tools}

* Gemeinsam zu verwendende Position auf dem Host für 'build', 'debug', 'test'.
* Verwendung: `bx dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Gemeinsam zu verwendende Position im Container für 'build', 'debug', 'test'.
* Verwendung: `bx dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Portzuordnungen für den Container. Der erste Wert ist der Port, der im Hostbetriebssystem verwendet werden soll, der zweite Wert ist der Port im Container [host-port:container-port].
* Verwendung: `bx dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile für den Ccontainer 'tools'.
* Verwendung: `bx dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Zu erstellendes Image aus `dockerfile-tools`.
* Verwendung: `bx dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Verwenden Sie diese Option, um Mounts zwischen dem Hostsystem und dem Container 'run' zu definieren.
* Die Werte `host-path-run` und `container-path-run` werden am Anfang dieser Liste eingefügt.
* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist es, für 'build' und 'run' dieselben Mounteinstellungen zu verwenden.
* Verwendung: `bx dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Verwenden Sie diese Option, um Mounts zwischen dem Hostsystem und dem Container 'tools' zu definieren.
* Die Werte `host-path-tools` und `container-path-tools` werden am Anfang dieser Liste eingefügt.* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist es, für 'build' und 'debug' dieselben Mounteinstellungen zu verwenden.
* Verwendung: `bx dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parameter zum Angeben eines Befehls zum Erstellen von Code für alle Verwendungszwecke außer DEBUG.
* Verwendung: `bx dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Verwenden Sie diesen Parameter, um eine ausführliche Ausgabe bereitzustellen.
* Verwendung: `bx dev <build|debug|run|test> --trace`

