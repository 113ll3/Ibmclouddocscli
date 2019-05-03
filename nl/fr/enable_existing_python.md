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

# Activation d'applications Python existantes pour le déploiement en cloud
{: #enable-existing-python}

Vous pouvez générer les fichiers qui permettent à votre application Python de s'exécuter sur {{site.data.keyword.cloud}} en utilisant la [commande enable de l'interface de ligne de commande {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-idt-cli#enable).

## Activation de votre application Python
{: #enable-app-python}

Entrez la commande suivante depuis le répertoire racine de votre projet Python :
```
ibmcloud dev enable
```
{: codeblock}

* Quand vous êtes invité à vérifier l'infrastructure détectée pour le projet, **Python - Flask** ou **Python - Django**, répondez `y`. 
* Vous êtes ensuite invité à exécuter la commande **Connecter à une application IBM Cloud**. Sélectionnez l'option **Générer des actifs, créer une nouvelle application IBM Cloud et s'y connecter** ou l'option **Générer des actifs sans se connecter à une application IBM Cloud** dans votre application.
* La commande `enable` peut aussi créer des services et les lier à votre application. Dans cet exemple de base, répondez `n`.

Voir la sortie exemple suivante :
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

## Génération et déploiement d'une application Python optimisée pour le cloud
{: #build-deploy-python}

Ensuite, générez votre application avec la commande [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) :
```
ibmcloud dev build
```
{: codeblock}

Si la génération réussit, vous pouvez déployer votre application dans {{site.data.keyword.cloud_notm}} avec la commande [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) suivante :
```
ibmcloud dev deploy
```
{: codeblock}

## Que faire si votre application activée n'est pas générée ou déployée ?
{: #build-failure-python}

Toutes les applications ne s'activent pas correctement à l'aide de la commande `enable`. Ainsi, l'erreur suivante peut se produire quand le nom du projet diffère du nom du répertoire qui contient les fichiers `wsgi.py` et `settings.py` :
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

Le nom de fichier `<projectname>.wsgi` correspond au nom du projet en cours d'activation. 

Si votre application n'est pas générée ou déployée après exécution d'`ibmcloud dev enable`, vous pouvez modifier les fichiers générés pour terminer l'activation de cloud.

### Configuration manuelle des fichiers d'activité de cloud générés
{: #manual-enable-python}

Pour activer des applications Python utilisant l'infrastructure Django, mettez à jour la ligne `CMD` dans Dockerfile, dans la commande que vous utilisez normalement pour exécuter votre projet.

Ainsi, si la commande que vous utilisez pour exécuter le projet est :
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Mettez à jour l'entrée `CMD` dans votre Dockerfile, de la façon suivante :
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Etapes suivantes
{: #next_steps_existing_python notoc}

Pour plus d'informations, voir [Interface de ligne de commande IBM Cloud Developer Tools](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
