---

copyright:

   years: 2017, 2018

lastupdated: "2018-08-28"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Befehle des CLI-Plug-ins von {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Version: 1.2.0
Freigegeben: 8. März 2018

Ab Mai 2018 wird an Stelle der {{site.data.keyword.Bluemix_notm}}-CLI-Befehle `bluemix` und `bx` künftig der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch auch weiterhin noch so lange verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

Verwenden Sie die folgenden Befehle des Plug-ins für die Befehlszeilenschnittstelle von {{site.data.keyword.dev_cli_notm}} (ibmcloud dev), um eine Anwendung zu erstellen, zu verwalten, bereitzustellen, zu debuggen und zu testen.

- [build](#build): Anwendung in einem lokalen Container erstellen.
- [code](#code): Code für eine Anwendung herunterladen.
- [console](#console): IBM Cloud-Konsole für eine Anwendung öffnen.
- [create](#create): Neue Anwendung erstellen und Hinzufügen von Services ermöglichen.
- [debug](#debug): Anwendung in einem lokalen Container debuggen.
- [delete](#delete): Anwendung aus Ihrem Bereich löschen.
- [deploy](#deploy): Anwendung in IBM Cloud bereitstellen.
- [diag](#diag): Zeigt Versionsinformationen zu installierten Abhängigkeiten an.
- [edit](#edit): Services zu einer vorhandenen Anwendung hinzufügen oder aus dieser entfernen.
- [enable](#enable): Vorhandene Anwendung für die Verwendung mit IBM Cloud Developer Tools aktualisieren.
- [get-credentials](#get-credentials): Berechtigungsnachweise abrufen, die die Anwendung benötigt, um die Verwendung verbundener IBM Cloud-Services zu ermöglichen.
- [help](#help): Hilfe für die Syntax und die Argumente der Befehlszeilenschnittstelle.
- [list](#list): Alle IBM Cloud-Anwendungen in einer Ressourcengruppe auflisten.
- [run](#run): Anwendung in einem lokalen Container ausführen.
- [shell](#shell): Eine Shell für einen lokalen Container öffnen.
- [status](#status): Status der von der Befehlszeilenschnittstelle verwendeten Container überprüfen.
- [stop](#stop): Container stoppen.
- [test](#test): Anwendung in einem lokalen Container testen.
- [view](#view): Bereitgestellte URL der Anwendung zum Testen und Anzeigen anzeigen.
- [compound commands](#compound): Mehrere Befehle in einer einzelnen Befehlszeilenanweisung ausführen.



## build
{: #build}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können Ihre Anwendung mithilfe des Befehls `build` erstellen. Die Befehle `test`, `debug` und `run` setzen eine kompilierte Anwendung voraus, daher müssen Sie zuvor eine `build`-Operation durchführen.  

Das Konfigurationselement `build-cmd-debug` wird zum Erstellen der Anwendung für alle Verwendungszwecke, mit Ausnahme von `run`, verwendet. Sie erstellen Ihre Anwendung für das Debuggen, indem Sie die Befehlszeilenoption `--debug` angeben.  Das Konfigurationselement `build-cmd-run` wird beim Erstellen der Anwendung für den Einsatz mit dem Befehl `run` verwendet.

Für einen Build mit mehreren Containern muss die Anwendung entweder eine [Compose](https://docs.docker.com/compose/overview/)-Datei enthalten, die in `cli-config.yml` angegeben ist, oder Sie können mithilfe des Befehlsparameters `dockerfile-tools` eine solche Datei angeben. Weitere Informationen finden Sie unter [Compose-Datei](/docs/apps/projects/compose_file.html).

Führen Sie den folgenden Befehl in Ihrem aktuellen Anwendungsverzeichnis aus, um die Anwendung zu erstellen:  

```
ibmcloud dev build [--debug]
```
{: codeblock}



## code
{: #code}

Verwenden Sie den Befehl `code`, um eine zuvor erstellte Anwendung mit Anwendungsvorlagencode und Konfigurationsdateien für {{site.data.keyword.Bluemix_notm}} herunterzuladen.  Dies ist nützlich, wenn Sie eine zweite Kopie einer von Ihnen erstellten Anwendung extrahieren müssen.

Führen Sie den folgenden Befehl aus, um den Code aus einer angegebenen Anwendung herunterzuladen.

```
ibmcloud dev code <applicationName>
```
{: codeblock}


## console
{: #console}

Verwenden Sie den Befehl `console`, um in einem Web-Browser die Webkonsole Ihrer Anwendung unter IBM Cloud zu öffnen.  Sie können den Befehl `ibmcloud dev console` vom Ordner Ihrer Anwendung aus ausführen; die Befehlszeilenschnittstelle versucht dann, eine entsprechende Anwendung in IBM Cloud zu finden, deren Anwendungs-ID mit dem aktuellen Verzeichnis übereinstimmt. Falls das System keinen übereinstimmenden Namen findet, wird anstelle der spezifischen Anwendung das Dashboard für Webanwendungen und mobile Anwendungen in IBM Cloud geöffnet.

Wenn Sie einen Anwendungsname angeben, überspringt die Befehlszeilenschnittstelle den Abgleich des Ordner-/Anwendungsnamens. In diesem Fall öffnet die Befehlszeilenschnittstelle die Konsole der angegebenen Anwendung in einem Web-Browser.  

Führen Sie den folgenden Befehl aus, um einen Web-Browser in der Webkonsole Ihrer Anwendung zu öffnen.

```
ibmcloud dev console [applicationName]
```
{: codeblock}


## create
{: #create}

Mit diesem Befehl wird eine Anwendung erstellt, wobei zur Eingabe aller Informationen aufgefordert wird, z. B. Ressourcentyp, Sprache, Starter-Kit und DevOps-Toolchain-Optionen. Die Anwendung wird im aktuellen Verzeichnis erstellt.

Führen Sie den folgenden Befehl aus, um eine Anwendung im aktuellen Verzeichnis zu erstellen und ihr Services zuzuordnen:

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können Ihre Anwendung mithilfe des Befehls `debug` debuggen. Zuerst muss für die Anwendung ein Build durchgeführt werden, indem der Befehl 'build' mit dem Argument `--debug` verwendet wird. Wenn Sie den Befehl `debug` starten, wird ein Container gestartet, der einen oder mehrere Debugports bereitstellt, wie im Wert `container-port-map-debug` in der cli-config.yml definiert bzw. wie in der Befehlszeile angegeben. Verbinden Sie Ihr bevorzugtes Debugging-Tool mit dem Port oder den Ports und Sie können Ihre Anwendung wie üblich debuggen.

Kompilieren Sie zuerst Ihre Anwendung:

```
ibmcloud dev build --debug
```
{: codeblock}

Führen Sie zuerst den folgenden Befehl im aktuellen Anwendungsverzeichnis aus, um die Anwendung zu debuggen:

```
ibmcloud dev debug
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
* Syntax: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parameter zum Erstellen von Code für DEBUG.
* Syntax: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parameter zum Angeben eines Befehls zum Aufrufen des Debuggers im Container 'tools'. Verwenden Sie diesen Parameter, wenn `build-cmd-debug` Ihre Anwendung im Debugger startet.
* Syntax: `ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Mit dem Befehl `delete` können Sie Anwendungen aus Ihrem {{site.data.keyword.Bluemix}}-Bereich entfernen. Sie können den Befehl ohne Parameter ausführen, um verfügbare Anwendungen aufzulisten, und die zu löschende Anwendung in der nummerierten Liste auswählen. Der Anwendungscode und die Anwendungsverzeichnisse werden nicht aus dem lokalen Plattenspeicher entfernt.

Führen Sie den folgenden Befehl aus, um die Anwendung aus {{site.data.keyword.Bluemix}} zu löschen:

```
ibmcloud dev delete <applicationName>
```
{: codeblock}


**Hinweis:** {{site.data.keyword.Bluemix}}-Services werden **nicht** entfernt.


## deploy
{: #deploy}

Sie können eine Anwendung als Cloud Foundry-Anwendung oder als Container bereitstellen.

Bevor Sie eine Anwendung als Cloud Foundry-Anwendung in {{site.data.keyword.Bluemix}} bereitstellen, muss eine `manifest.yml`-Datei im Stammverzeichnis Ihrer Anwendung vorhanden sein.

Bevor Sie eine Anwendung als Container bereitstellen, müssen Sie [Kubernetes](https://kubernetes.io/) und [Helm](https://github.com/kubernetes/helm) lokal installieren. Stellen Sie sicher, dass die Version des Helm-Clients nicht aktueller als die Helm-Serverversion ist. Beide Angaben erhalten Sie, indem Sie `helm version` ausführen. Wir empfehlen Version 2.4.2 für den Client.

Für die Bereitstellung der Anwendung in Kubernetes müssen Sie entweder für `deploy-target` den Wert `container` in `cli-config.yml` angeben oder den Parameter `-t container` verwenden.

Weitere Parameter, die für die Konfiguration der Kubernetes-Bereitstellung erforderlich sind, können ebenfalls in `cli-config.yml`, wie nachfolgend dargestellt, oder mithilfe von Befehlszeilenargumenten angegeben werden. Wenn Sie diese in `cli-config.yml` nicht definieren, müssen Sie die Bereitstellung mit dem Parameter `-t container` durchführen und werden zur Eingabe aller anderen Werte aufgefordert.

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud-Region>.bluemix.net/<Containerregistry-Namensbereich>/<App-Name>"

    ibm-cluster: "mycluster"
```

In `cli-config.yml` können Sie die Position eines Helm-Diagramms in der Eigenschaft `chart-path` definieren und `deploy-image-target` konfigurieren, wie im Beispiel dargestellt. Das Element `deploy-image-target` in der `cli-config.yml` wird statt der Elemente `repository` und `tag` in der Datei `chart/values.yml` verwendet. Um gezielt in {{site.data.keyword.Bluemix}} bereitzustellen, legen Sie das Konfigurationselement `ibm-cluster` auf den Namen des Kubernetes-Clusters fest, den Sie in {{site.data.keyword.Bluemix}} erstellt haben, wie im [Lernprogramm: Cluster erstellen](/docs/containers/cs_tutorials.html#cs_cluster_tutorial) beschrieben.

Weitere Informationen zur Bereitstellung, Konfiguration und Implementierung in einem Kubernetes-Cluster finden Sie im Lernprogramm [Skalierbare Webanwendung in Kubernetes bereitstellen](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

Führen Sie den folgenden Befehl in Ihrem aktuellen Anwendungsverzeichnis aus, um die Anwendung zu erstellen:  

```
ibmcloud dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen Anwendungsverzeichnis aus, um die Anwendung bereitzustellen:

```
ibmcloud dev deploy
```
{: codeblock}


### Bereitstellungsbefehlsparameter
{: #deploy-parameters}

Die folgenden Parameter können mit dem Befehl `deploy` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der Anwendung angegeben werden. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `chart-path`
{: #chart-path}

* Parameter für eine Containerbereitstellung zur Angabe der Position des Helm-Diagramms, das für die Bereitstellung verwendet wird.
* Syntax: `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Optionaler Parameter zum Angeben des Typs der fertigzustellenden Bereitstellung.  Der Standardbereitstellungstyp ist ein Buildpack.
* Syntax: `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter zur Verwendung mit einer Containerbereitstellung als Zielimagename für die Bereitstellung (z. B. zum Kennzeichnen einer Docker-Registry). Der Wert darf keine Version enthalten, z. B.: image-name:{version}, weil die Version von `deploy` inkrementiert und angehängt wird.
* Syntax: `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Optionaler Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung in {{site.data.keyword.Bluemix}}.
* Syntax: `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `Host`
{: #host}

* Optionaler Parameter zur Definition des Hostnamens der Anwendung bei der Bereitstellung in Cloud Foundry.
* Syntax: `ibmcloud dev deploy --host [hostname]`

#### `Domäne`
{: #domain}

* Optionaler Parameter zur Definition der Domäne der Anwendung bei der Bereitstellung in Cloud Foundry.
* Sybtax: `ibmcloud dev deploy --domain [domain]`


## diag
{: #diag}

Dieser Befehl wird zu Diagnosezwecken verwendet und dient zur Anzeige der Versionsinformationen installierter Abhängigkeiten für die {{site.data.keyword.dev_cli_notm}}-CLI. Dies ist besonders hilfreich, wenn Sie feststellen möchten, ob Abhängigkeiten fehlen oder um Fehler zu beheben.

Führen Sie den folgenden Befehl aus, um die Versionen der installierten Abhängigkeiten anzuzeigen:

```
ibmcloud dev diag
```
{: codeblock}


## edit
{: #edit}

Sie können die Anwendung bearbeiten, indem Sie neue Services hinzufügen, Verbindungen zu vorhandenen Services herstellen und trennen oder vorhandene Services entfernen. Führen Sie den folgenden Befehl im Stammverzeichnis eines Anwendungsverzeichnisses aus:

```
ibmcloud dev edit
```
{: codeblock}

Wenn Ihr Konto keine vorhandenen Services enthält, wird mit diesem Befehl eine Liste mit Servicegruppen angezeigt, in der Sie einen Service auswählen können, der mit Ihrer Anwendung verbunden wird.

Wenn Ihr Konto jedoch vorhandene Services enthält, wird mit diesem Befehl eine Liste dieser Services angezeigt und angegeben, ob die einzelnen Services mit der Anwendung verbunden sind.

Wenn Sie einen verbundenen Service auswählen, können Sie entweder die Verbindung dieses Service zu Ihrer Anwendung trennen oder den Service aus Ihrem Konto löschen, wodurch die Verbindungen des betreffenden Service zu allen Anwendungen, mit denen er verbunden ist, getrennt werden.

Wenn Sie einen nicht verbundenen Service auswählen, können Sie entweder diesen Service mit Ihrer Anwendung verbinden oder den Service aus Ihrem Konto löschen. Durch das Verbinden eines vorhandenen Service werden auch Dateien, wie z. B. Berechtigungsnachweisdateien oder Quellcode, heruntergeladen, damit mit der Verwendung dieses Service begonnen werden kann.

Darüber hinaus können Sie die Option zum Hinzufügen eines neuen Service zu Ihrer Anwendung auswählen. Daraufhin werden eine Reihe von Eingabeaufforderungen zur Serviceauswahl angezeigt und es werden zusätzliche Dateien, wie z. B. Berechtigungsnachweisdateien oder Quellcode, heruntergeladen, damit mit der Verwendung des neuen Service begonnen werden kann.



## enable
{: #enable}

Vorhandene Anwendung für die {{site.data.keyword.Bluemix_notm}}-Bereitstellung aktivieren. Der Befehl `enable` versucht, die Sprache einer vorhandenen Anwendung automatisch zu erkennen und dann zur Angabe zusätzlicher, erforderlicher Informationen aufzufordern. Dadurch werden Dateien generiert und hinzugefügt, die für lokale Docker-Container, für eine CloudFoundry-Bereitstellung oder für eine Kubernetes-/Container-Bereitstellung verwendet werden können.

Führen Sie den folgenden Befehl aus, um eine vorhandene Anwendung im aktuellen Verzeichnis für die {{site.data.keyword.Bluemix_notm}}-Bereitstellung zu aktivieren:

```
ibmcloud dev enable
```
{: codeblock}

Das Vorhandensein erforderlicher Dateien macht eine Erkennung der Anwendungssprache für eine gültige Anwendungsstruktur möglich.  

* Das Vorhandensein der Datei `package.json` gibt eine Node.js-Anwendung an.
* Das Vorhandensein der Datei `package.swift` gibt eine Swift-Anwendung an.
* Das Vorhandensein der Datei `setup.py` oder `requirements.txt` gibt eine Python-Anwendung an.
* Das Vorhandensein der Datei `pom.xml` oder `build.gradle` gibt eine Java-Anwendung an.
	* Das Vorhandensein der Datei `pom.xml` gibt eine Maven-Anwendung an.
	* Das Vorhandensein der Datei `build.gradle` gibt eine Gradle-Anwendung an.

Optional können Sie auch die erkannte Anwendungssprache mithilfe des Arguments `--language` überschreiben.  Allerdings werden nur gültige und abgeschlossene Anwendungen unterstützt. Der Befehl 'enable' ändert Ihren Quellcode nicht.

Sprachenoptionen sind unter anderem:
* node
* swift
* python
* java-ee (interpretiert als Java - Java EE)
* java-mp (interpretiert als Java - Java MicroProfile)
* java-spring (interpretiert als Java - Spring Framework)

Mit dem Befehl `ibmcloud dev enable` erstellte Dateien, die Namenskonflikte mit vorhandenen Dateien im Anwendungsordner aufweisen, werden mit der Dateierweiterung `.merge` gespeichert.  

### Aktivierungsbefehlsparameter
{: #enable-parameters}

Die folgenden Parameter können mit dem Befehl `enable` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der Anwendung angegeben werden. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `language`
{: #enable-language}

* Parameter zum Angeben der Sprache der aktivierenden Anwendung.
* Syntax: `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parameter zum Erzwingen einer erneuten Aktivierung einer bereits aktivierten Anwendung.
* Syntax: `ibmcloud dev enable -f|--force`


## get-credentials
{: #get-credentials}

Mit diesem Befehl werden die Berechtigungsnachweise abgerufen, die von der Anwendung benötigt werden, um die Verwendung verbundener Services zu ermöglichen.


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

Es können alle {{site.data.keyword.Bluemix_notm}}-Anwendungen in einer Ressourcengruppe aufgelistet werden.

Führen Sie den folgenden Befehl aus, um Ihre Anwendungen aufzulisten:

```
ibmcloud dev list
```
{: codeblock}


## run
{: #run}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können Ihre Anwendung mithilfe des Befehls `run` ausführen. Zuerst muss für die Anwendung ein Build durchgeführt werden, indem der Befehl `build` verwendet wird. Wenn Sie den Befehl `run` aufrufen, wird der Ausführungscontainer gestartet und stellt die Ports bereit, wie durch den Parameter `container-port-map` definiert. Der Parameter `run-cmd` kann verwendet werden, um die Anwendung aufzurufen, falls die Dockerfile des Ausführungscontainers keinen Eingangspunkt umfasst, um diesen Schritt abzuschließen.

Für eine Ausführung mit mehreren Containern muss die Anwendung entweder eine [Compose](https://docs.docker.com/compose/overview/)-Datei enthalten, die in `cli-config.yml` angegeben ist, oder Sie können mithilfe des Befehlsparameters `dockerfile-run` eine solche Datei angeben. Weitere Informationen finden Sie unter [Compose-Datei](/docs/apps/projects/compose_file.html).

Kompilieren Sie zuerst Ihre Anwendung:

```
ibmcloud dev build
```
{: codeblock}

Führen Sie den folgenden Befehl in Ihrem aktuellen Anwendungsverzeichnis aus, um die Anwendung zu starten:

```
ibmcloud dev run
```
{: codeblock}

Geben Sie `STRG-C` ein, um die Sitzung zu beenden.


### Ausführungsbefehlsparameter
{: #run-parameters}

Die folgenden Parameter stehen ausschließlich dem Befehl `run` zur Verfügung und
unterstützen Sie beim Verwalten Ihrer Anwendung im Ausführungscontainer.
Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `container-name-run`
{: #container-name-run2}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev run --container-name-run [<applicationName>]`

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
* Wenn Sie eine Ausführung mit mehreren Containern planen, sollte dies eine Compose-Datei sein.
* Wenn Sie mehrere Compose-Dateien verwenden möchten, schließen Sie eine durch Kommas begrenzte Liste mit den Dateinamen in doppelte Anführungszeichen ein.
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

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können die Shell innerhalb des Containers 'run' oder 'tools' mit dem Befehl `shell` öffnen.

Führen Sie hierzu diesen Befehl aus:

```
ibmcloud dev shell
```

Die {{site.data.keyword.dev_cli_short}}-Befehlszeilenschnittstelle öffnet eine interaktive Shell für den Docker-Container der Anwendung. Der Standardzielcontainer für den Shell-Befehl wird durch den Wert `container-shell-target` in der Datei `cli-config.yml` definiert, wobei die gültigen Werte `run` oder `tools` lauten. Ist dieser Wert nicht definiert oder wird ein ungültiger Wert angegeben, verwendet der Befehl `shell` standardmäßig den Container `tools`. Der Shellbefehl öffnet den Container zum dem in der Anweisung `WORKDIR` in der entsprechenden Dockerfile angegebenen Verzeichnis. Wenn `WORKDIR` nicht in der Dockerfile aufgelistet ist, wird das Containerstammverzeichnis als Arbeitsverzeichnis verwendet. Weitere Informationen finden Sie in dieser [Referenz](https://docs.docker.com/engine/reference/builder/#workdir).

Alternativ können Sie entweder `run` oder `tools` als Argument an den Befehl übergeben und der jeweilige Container wird aufgerufen und die Shell wird für diesen Container geöffnet. Entsprechend können Sie den Parameter `container-name` verwenden, um den Namen des Containers anzugeben, für den die Shell geöffnet werden soll. Allerdings sollte dieses Flag für den Fall reserviert sein, wenn keine Container ausgeführt werden. Die Argumente `run` und `tools` sind flexibler und ermöglichen Ihnen, zwischen Containern zu wechseln, wenn einer aktuell ausgeführt wird. Wenn beispielsweise der Container 'tools' ausgeführt wird und Sie `ibmcloud dev shell run` absetzen, wird der Container `tools` gestoppt und der Container `run` gestartet und umgekehrt.

Falls der Zielcontainer `run` oder `tools` noch nicht ausgeführt wird, wenn Sie den Befehl `shell` absetzen, wird der Zielcontainer gestartet. Dabei wird jedoch der Standardwert `Cmd` oder `Entrypoint` in der Dockerfile überschrieben, um die Shell direkt zu öffnen, statt den Serverprozess zu starten. Auf diese Weise können Sie den Container `run` oder `tools` starten und den Server manuell mit Ihren eigenen beliebigen oder angepassten Befehlen starten.


Sie können auch die ausführbare Shelldatei angeben, die Sie öffnen möchten, indem Sie den Parameter `container-shell` verwenden. Standardmäßig wird `/bin/sh` verwendet. Wenn Sie lieber die Bash-Shell verwenden, geben Sie als Wert für `container-shell` `/bin/bash` an. Beachten Sie jedoch, dass Bash nicht automatisch in allen Linux-Varianten verfügbar ist.

Alle zusätzlichen Argumente, die Sie neben Flags an den Befehl übergeben, werden für den auszuführenden Befehl analysiert, wenn die Shell geöffnet wird. Wenn Sie einen auszuführenden Befehl angeben, wird die Shell innerhalb des Containers bei Ausführung des Befehls beendet und an das Terminal zurückgegeben.

Sie können beispielsweise den Linux-Befehl `ls` innerhalb der Containershell 'tools' ausführen, indem Sie `ibmcloud dev shell tools ls` aufrufen.   Sie können auch zusätzliche Flags angeben, die an die Shellbefehlsausführung übergeben werden sollen, indem Sie die Argumente in Anführungszeichen einschließen, z. B. `ibmcloud dev shell "ls -la"`.

### shell-Befehlsparameter
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Name des Containers, für den Sie die Shell öffnen möchten.
* Syntax: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Gibt an, welche Shell innerhalb des Containers ausgeführt werden soll (Standardwert ist '/bin/sh').
* Syntax: `ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können den Status der Container abfragen, die von der {{site.data.keyword.dev_cli_short}}-CLI verwendet werden, wie durch `container-name-run` und `container-name-tools` definiert.

Führen Sie den folgenden Befehl im aktuellen Anwendungsverzeichnis aus, um den Containerstatus zu überprüfen:

```
ibmcloud dev status
```
{: codeblock}


[Statusbefehlsparameter](#command-parameters)


## stop
{: #stop}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können Ihre Container mithilfe des Befehls `stop` stoppen.

Führen Sie den folgenden Befehl aus, um die Container 'tools' und 'run' wie in Ihrer Datei `cli-config.yml` definiert zu stoppen:

```
ibmcloud dev stop
```
{: codeblock}

Um einen Container zu stoppen, der nicht in der Datei `cli-config.yml` definiert ist, können Sie einen zusätzlichen Befehlszeilenparameter angeben, um ihn zu überschreiben.  Wenn keine Container in der Datei `cli-config.yml` oder in der Befehlszeile angegeben sind, wird der Stoppbefehl einfach zurückgegeben.

### Stoppbefehlsparameter
{: #stop-parameters}

Die folgenden Parameter werden für den Befehl `stop` verwendet. Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `container-name-run`
{: #container-name-run}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* Containername für den Container 'tools'.
* Syntax: `ibmcloud dev stop --container-name-tools [<applicationName>]`



## test
{: #test}

Wenn Sie mit Windows&trade; arbeiten, müssen Sie Windows 10 Pro oder höher ausführen.

Sie können Ihre Anwendung mithilfe des Befehls `test` stoppen. Zuerst muss für die Anwendung ein Build durchgeführt werden, indem der Befehl `build --debug` verwendet wird. Der Container 'tools' wird dann verwendet, um `test-cmd` für die Anwendung aufzurufen.

Kompilieren Sie zuerst Ihre Anwendung:

```
ibmcloud dev build --debug
```
{: codeblock}

Führen Sie den folgenden Befehl aus, um Ihre Anwendung zu testen:

```
ibmcloud dev test
```
{: codeblock}


### Testbefehlsparameter
{: #test-parameters}

Der folgende Parameter wird ausschließlich mit dem Befehl `test` verwendet.  Es gibt [zusätzliche Parameter](#command-parameters), die mit anderen Befehlen gemeinsam verwendet werden.

#### `test-cmd`
{: #test-cmd}

* Parameter zum Angeben eines Befehls zum Testen von Code im Container 'tools'.
* Syntax: `ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

Mit dem Befehl `view` können Sie die URL anzeigen, unter der Ihre Anwendung bereitgestellt wird. Führen Sie diesen Befehl im Stammverzeichnis der Anwendung aus, die Sie anzeigen möchten. Der Befehl `view` öffnet die URL auch in Ihrem Standardbrowser.

Bei Anwendungen, die in Cloud Foundry bereitgestellt werden, besteht die URL aus dem Hostnamen und der Domäne der Anwendung.

Bei Anwendungen, die in Kubernetes bereitgestellt werden, besteht die URL aus der IP-Adresse des Knotens, unter dem sie bereitgestellt wird, und dem öffentlichen Port. Wenn der Befehl feststellt, dass die App in Kubernetes bereitgestellt wurde, wird das CLI-Tool eine Bestätigung anfordern. Wenn Sie angeben, dass die Anwendung nicht in Kubernetes bereitgestellt wurde, wird die Cloud Foundry-URL angezeigt. Falls Sie erwartet haben, dass der Befehl die URL für eine in Kubernetes bereitgestellte Anwendung anzeigt, dies aber nicht der Fall ist, müssen Sie entweder sicherstellen, dass die `cli-config.yml` einen Eingangspunkt für `chart-path` enthält oder Sie müssen diesen wie [hier](#chart-path) gezeigt über die Befehlszeile angeben.

Führen Sie den folgenden Befehl aus, um Ihre Anwendung anzuzeigen:

```
ibmcloud dev view
```
{: codeblock}

### Anzeigebefehlsparameter
{: #view-parameters}

Die folgenden Parameter werden ausschließlich mit dem Befehl `view` verwendet.

#### `deploy-target`

* Optionaler Parameter zum Angeben des Typs von Bereitstellung, um die Eingabeaufforderung zu umgehen.
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

* Optionaler Parameter zum Definieren des Namens des Kubernetes-Clusters für eine Containerbereitstellung.
* Syntax: `ibmcloud dev view --ibm-cluster [cluster-name]`


## Zusammengesetzte Befehle
{: #compound}

Sie können mehrere Befehle in einer einzelnen Befehlszeilenanweisung ausführen, indem Sie die Befehle der {{site.data.keyword.Bluemix_notm}}-Entwicklertools durch den Begrenzer `/` trennen. Zusätzliche Befehlszeilenflags können im Anschluss an die zusammengesetzten Befehle angegeben werden.  Die folgenden Befehle sind Beispiele für die Verwendung von zusammengesetzten Befehlen:

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Alle Flags müssen auf den finalen Befehl folgen und werden auf alle Befehle angewendet, denen das jeweilige Flag zugeordnet ist. Im oben dargestellten letzten Beispiel gilt das Flag `--trace` für alle 3 Befehle, während das Flag `-t` nur für die beiden letzten Befehle gilt und daher für den Befehl `build` nicht angewendet wird.

Dies sind die Befehle, die mit diesem Feature verwendet werden können:
`build, debug, deploy, get-credentials, run, stop, test, view`

Falls ein Befehl fehlschlägt, werden die nachfolgenden Befehle nicht ausgeführt.

Falls Befehle auf `debug` oder `run` folgen, wird die Ausführung nur fortgesetzt, wenn `debug` oder `run` auf andere Weise beendet wird als dass der Prozess im aktuellen Terminalfenster abgebrochen wird. `STRG+C` bricht den Prozess ab und die nachfolgenden Befehle werden nicht ausgeführt. Sie können beispielsweise `ibmcloud dev stop` in einem anderen Terminalfenster ausführen, um den laufenden Container zu stoppen und die Ausführung des nachfolgenden Befehls fortzusetzen.


## Parameter für 'build', 'debug', 'run' und 'test'
{: #command-parameters}

Die folgenden Parameter können mit den Befehlen `build|debug|run|test` oder unmittelbar durch die Aktualisierung der Datei `cli-config.yml` der Anwendung angegeben werden. Zusätzliche Parameter sind für die Befehle [`debug`](#debug-parameters) und [`run`](#run-parameters) verfügbar.

**Hinweis**: Befehlsparameter, die in der Befehlszeile eingegeben werden, haben Vorrang vor der `cli-config.yml`-Konfiguration.

#### `config-file`  
{: #config-file}

* Geben Sie eine Datei 'cli-config.yml' für die Verwendung mit einem Befehl an.
* Syntax: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Containername für den Ausführungscontainer.
* Syntax: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Containername für den Container 'tools'.
* Syntax: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

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

* Portzuordnungen für den Container. Der erste Wert ist der Port, der im Hostbetriebssystem verwendet werden soll, der zweite Wert ist der Port im Container [host-port:container-port].
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
* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist es, für 'build' und 'run' dieselben Mounteinstellungen zu verwenden.
* Syntax: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Verwenden Sie diese Option, um Mounts zwischen dem Hostsystem und dem Container 'tools' zu definieren.
* Die Werte `host-path-tools` und `container-path-tools` werden am Anfang dieser Liste eingefügt.* Eine Best Practice, um unerwartete Ergebnisse zu vermeiden, ist es, für 'build' und 'debug' dieselben Mounteinstellungen zu verwenden.
* Syntax: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parameter zum Angeben eines Befehls zum Erstellen von Code für alle Verwendungszwecke außer DEBUG.
* Syntax: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Verwenden Sie diesen Parameter, um eine ausführliche Ausgabe bereitzustellen.
* Syntax: `ibmcloud dev <build|debug|run|test> --trace`
