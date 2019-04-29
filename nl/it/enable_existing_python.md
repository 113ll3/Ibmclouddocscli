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

# Abilitazione delle applicazioni Python esistenti per la distribuzione cloud
{: #enable-existing-python}

Puoi generare i file necessari per abilitare la tua applicazione Python all'esecuzione su {{site.data.keyword.cloud}} utilizzando il [comando enable della CLI {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-idt-cli#enable).

## Abilitazione della tua applicazione Python
{: #enable-app-python}

Immetti il seguente comando dalla directory root del tuo progetto Python:
```
ibmcloud dev enable
```
{: codeblock}

* Quando ti viene richiesto di verificare il framework rilevato per il progetto, **Python - Flask** o **Python - Django**, rispondi `y`. 
* Ti viene in seguito richiesto **Connect to an IBM Cloud app**. Seleziona l'opzione **Generate assets, create a new IBM Cloud app and connect to it** o **Generate assets without connecting to an IBM Cloud app** per la tua applicazione.
* Il comando `enable` può anche creare i servizi e associarli alla tua applicazione. Per questo esempio di base, rispondi `n`.

Consulta il seguente output di esempio:
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

## Crea e distribuisci un'applicazione Python abilitata per il cloud
{: #build-deploy-python}

Successivamente, crea la tua applicazione con il comando [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build):
```
ibmcloud dev build
```
{: codeblock}

Se la creazione viene completata correttamente, puoi distribuire la tua applicazione a {{site.data.keyword.cloud_notm}} con il seguente comando [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy):
```
ibmcloud dev deploy
```
{: codeblock}

## Cosa fare se la tua applicazione abilitata non viene creata o distribuita
{: #build-failure-python}

Non tutte le applicazioni vengo abilitate correttamente dal comando `enable`. Ad esempio, si potrebbe verificare il seguente errore quando il nome del progetto è diverso dal nome della directory che contiene i file `wsgi.py` e `settings.py`:
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

Il nome del file `<projectname>.wsgi` è il nome del progetto che sta venendo abilitato.

Se la tua applicazione non viene creata o distribuita dopo aver eseguito `ibmcloud dev enable`, puoi modificare i file generati per completare l'abilitazione cloud.

### Configurazione manuale dei file di abilitazione cloud generati
{: #manual-enable-python}

Per abilitare le applicazioni Python che utilizzano il framework Django, aggiorna la riga `CMD` nel Dockerfile con il comando che normalmente utilizzi per eseguire il tuo progetto.

Ad esempio, se il comando che utilizzi per eseguire il progetto è:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Aggiorna la voce `CMD` nel tuo Dockerfile in questo modo:
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Passi successivi
{: #next_steps_existing_python notoc}

Per ulteriori informazioni, consulta [CLI IBM Cloud Developer Tools](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
