---

copyright:
  years: 2019, 2020
lastupdated: "2020-02-06"

keywords: cli, ibmcloud dev enable, python, cloud enable python, django, deploy python, build python, python debug, python troubleshoot, python cloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Enabling existing Python applications for cloud deployment
{: #enable-existing-python}

You can generate the files that are needed to enable your Python application to run on {{site.data.keyword.cloud}} by using the [{{site.data.keyword.dev_cli_long}} CLI enable command](/docs/cli/idt?topic=cloud-cli-idt-cli#enable).
{: shortdesc}

## Enabling your Python app
{: #enable-app-python}

Enter the following command from the root directory of your Python project:
```
ibmcloud dev enable
```
{: codeblock}

* When you're prompted to verify the detected framework for the project, **Python - Flask** or **Python - Django**, reply `y`. 
* You are then prompted to **Connect to an IBM Cloud app**. Select either the **Generate assets, create a new IBM Cloud app and connect to it** or **Generate assets without connecting to an IBM Cloud app** option to connect your app.
* The `enable` command can also create services and bind them to your app. For this basic example, reply `n`.

See the following sample output:
```
> ibmcloud dev enable
The enable feature is currently in Beta.
Please provide your experience and feedback at: https://ibm-cloud-tech.slack.com/messages/developer-tools/
Only server-side apps are supported by the enable feature

? Python - Flask app discovered. Do you want to proceed with this
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
in the IBM Cloud console. Use ibmcloud dev console to access the console.

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
{: screen}

## Build and deploy a cloud-enabled Python app
{: #build-deploy-python}

Next, build your app with the [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) command:
```
ibmcloud dev build
```
{: codeblock}

If the build completes successfully, you can deploy your app to {{site.data.keyword.cloud_notm}} with the following [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) command:
```
ibmcloud dev deploy
```
{: codeblock}

## What to do if your enabled app does not build or deploy
{: #build-failure-python}

Not all apps are successfully enabled by the `enable` command. For example, the following error might occur when the project name differs from the directory name that contains the `wsgi.py` and `settings.py` files:
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

The `<projectname>.wsgi` file name is the name of the project that is being enabled.

If your app does not build or deploy after you run `ibmcloud dev enable`, you can modify the generated files to complete cloud enablement.

### Manually configuring the generated cloud enablement files
{: #manual-enable-python}

To enable Python apps that use the Django framework, update the `CMD` line in the Dockerfile to the command that you normally use to run your project.

For example, if the command that you use to run the project is:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Update the `CMD` entry in your Dockerfile like so:
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Next Steps
{: #next_steps_existing_python notoc}

For more information, see [IBM Cloud Developer Tools CLI](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
