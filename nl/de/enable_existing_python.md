---

copyright:
  years: 2019
lastupdated: "2019-04-03"

keywords: cli, ibmcloud dev enable, python, cloud enable python, django, deploy python, build python, python debug, python troubleshoot, python cloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Vorhandene Python-Anwendungen für die Cloudbereitstellung aktivieren
{: #enable-existing-python}

Sie können die Dateien generieren, die benötigt werden, um Ihre Python-Anwendung für die Ausführung unter {{site.data.keyword.cloud}} zu aktivieren, indem Sie den [{{site.data.keyword.dev_cli_long}}-Befehlzeilenschnittstellenbefehl 'enable'](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) verwenden.

## Python-Anwendung aktivieren
{: #enable-app-python}

Geben Sie im Stammverzeichnis Ihres Python-Projekts den folgenden Befehl ein:
```
ibmcloud dev enable
```
{: codeblock}

* Wenn Sie dazu aufgefordert werden, das erkannte Framework für das Projekt zu prüfen, **Python - Flask** oder **Python - Django**, antworten Sie mit `y` für 'Ja'. 
* Sie werden dann zur **Herstellung einer Verbindung mit einer IBM Cloud-App** aufgefordert. Wählen Sie für Ihre Anwendung entweder die Option zum **Generieren von Assets, Erstellen einer neuen IBM Cloud-App und Herstellen einer Verbindung mit ihr** oder die Option zum **Generieren von Assets ohne Herstellung einer Verbindung mit einer IBM Cloud-App** aus.
* Mit dem Befehl `enable` können auch Services erstellt und an Ihre Anwendung gebunden werden. Antworten Sie im Falle dieses Basisbeispiels mit `n` für 'Nein'.

Sehen Sie sich die folgene Beispielausgabe an:
```
> ibmcloud dev enable
The enable feature is currently in Beta.
Please provide your experience and feedback at: https://ibm-cloud-tech.slack.com/messages/developer-tools/
Only server-side applications are supported by the enable feature

? Python - Flask application discovered. Do you want to proceed with this
language choice? [y/n]> y


Using the resource group default (default) of your account

--------------------------------------------------------------------------------
Connect to an IBM Cloud app:
--------------------------------------------------------------------------------

This is required to use the capabilities of IBM Cloud.
Generate cloud enablement and deployment assets and optionally connect to an
IBM Cloud app.

--------------------------------------------------------------------------------
 1. MyStarterkitApplication
--------------------------------------------------------------------------------
2. Generate assets, create a new IBM Cloud app and connect to it
3. Generate assets without connecting to an IBM Cloud app
--------------------------------------------------------------------------------
 0. Exit
--------------------------------------------------------------------------------
? Enter selection number:> 2

? Do you want to select a service to connect to this application? [y/n]> n


This app already has a git repo therefore Toolchain creation must be completed
in the IBM Cloud console. Use bx dev console to access the console.

The application <appname> has been created in IBM Cloud.


The following files were added to your application:

.cfignore
.dockerignore
Dockerfile
Dockerfile-tools
README.md
cli-config.yml
manage.py
manifest.yml
run-dev
.bluemix/deploy.json
.bluemix/pipeline.yml
.bluemix/toolchain.yml
.bluemix/scripts/container_build.sh
.bluemix/scripts/kube_deploy.sh
chart/getstartedpython/Chart.yaml
chart/getstartedpython/bindings.yaml
chart/getstartedpython/values.yaml
chart/getstartedpython/templates/basedeployment.yaml
chart/getstartedpython/templates/deployment.yaml
chart/getstartedpython/templates/hpa.yaml
chart/getstartedpython/templates/istio.yaml
chart/getstartedpython/templates/service.yaml
LICENSE
.gitignore

The application, <appname>, has been successfully saved
into the current directory.
```

## Cloud-fähige Python-Anwendung erstellen und bereitstellen
{: #build-deploy-python}

Erstellen Sie als Nächstes Ihre Anwendung mit dem Befehl [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build):
```
ibmcloud dev build
```
{: codeblock}

Wenn das Erstellen erfolgreich abgeschlossen ist, können Sie Ihre Anwendung mit dem folgenden Befehl [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) für {{site.data.keyword.cloud_notm}} bereitstellen:
```
ibmcloud dev deploy
```
{: codeblock}

## Maßnahmen für den Fall, dass Ihre aktivierte Anwendung nicht erstellt oder bereitgestellt wird
{: #build-failure-python}

Nicht alle Anwendungen werden durch den Befehl `enable` erfolgreich aktiviert. Der folgende Fehler kann beispielsweise auftreten, wenn sich der Projektname von dem Namen des Verzeichnisses unterscheidet, das die Dateien `wsgi.py` und `settings.py` enthält:
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

Der Dateiname `<projectname>.wsgi` ist der Name des Projekts, das aktiviert wird.

Wenn Ihre Anwendung nach der Ausführung von `ibmcloud dev enable` nicht erstellt oder bereitgestellt wird, können Sie die generierten Dateien so ändern, dass die Cloud-Aktivierung abgeschlossen wird.

### Generierte Cloudaktivierungsdateien manuell konfigurieren
{: #manual-enable-python}

Um Python-Apps zu aktivieren, die das Django-Framework verwenden, ändern Sie die `CMD`-Zeile in der Dockerfile so, dass sie den Befehl enthält, den Sie normalerweise für die Ausführung Ihres Projekts verwenden.

Beispiel: Wenn Sie für die Ausführung des Projekts den folgenden Befehl verwenden:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Aktualisieren Sie den `CMD`-Eintrag in Ihrer Dockerfile wie folgt:
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Nächste Schritte
{: #next_steps_existing_python notoc}

Weitere Informationen finden Sie im Abschnitt zur [IBM Cloud Developer Tools-Befehlszeilenschnittstelle](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
