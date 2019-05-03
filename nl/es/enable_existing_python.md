---

copyright:
  years: 2019
lastupdated: "2019-03-08"

keywords: ibmcloud dev enable, python, cloud enable python, django, deploy python, build python, python debug, python troubleshoot, python cloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Habilitación de aplicaciones Python existentes para el despliegue en la nube
{: #enable-existing-python}

Puede generar los archivos necesarios para habilitar la aplicación Python para que se ejecute en
{{site.data.keyword.cloud}} utilizando el [mandato enable de la CLI de {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-idt-cli#enable).

## Habilitación de la aplicación Python
{: #enable-app-python}

Especifique el mandato siguiente desde el directorio raíz del proyecto Python:
```
ibmcloud dev enable
```
{: codeblock}

* Cuando se le solicite verificar la infraestructura detectada del proyecto, **Python - Flask** o **Python - Django**, responda `y`. 
* A continuación, se le indicará que se debe **Conectar a una app de IBM Cloud**. Seleccione las opciones **Generar activos, crear una nueva app de IBM Cloud y conectarse a ella** o **Generar activos sin conectarse a una app de IBM Cloud** para la aplicación.
* El mandato `enable` también puede crear servicios y enlazarlos a la aplicación. En este ejemplo básico, responda
`n`.

Consulte la salida de ejemplo siguiente:
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

## Compilar y desplegar una aplicación Python habilitada para la nube
{: #build-deploy-python}

A continuación, compile la aplicación con el mandato [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build):
```
ibmcloud dev build
```
{: codeblock}

Si la compilación finaliza correctamente, puede desplegar la aplicación en
{{site.data.keyword.cloud_notm}} con el mandato [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) siguiente:
```
ibmcloud dev deploy
```
{: codeblock}

## Qué hacer si la aplicación habilitada no se compila o despliega
{: #build-failure-python}

No todas las aplicaciones se habilitan correctamente mediante el mandato `enable`. Por ejemplo, es posible que se produzca el error siguiente cuando el nombre del proyecto es diferente del nombre del directorio que contiene los archivos
`wsgi.py` y `settings.py`:
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

El nombre de archivo `<projectname>.wsgi` es el nombre del proyecto que se va a habilitar.

Si la aplicación no se compila o despliega después de ejecutar `ibmcloud dev enable`, puede modificar los archivos generados para completar la habilitación en la nube.

### Configuración manual de los archivos de habilitación en la nube generados
{: #manual-enable-python}

Para habilitar apps Python que utilizan la infraestructura Django, actualice la línea
`CMD` del archivo de Docker al mandato que utilice normalmente para ejecutar su proyecto.

Por ejemplo, si el mandato que utiliza para ejecutar el proyecto es:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Actualice la entrada `CMD` en el archivo de Docker tal como se indica a continuación:
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Pasos siguientes
{: #next_steps_existing_python notoc}

Para obtener más información, consulte [CLI de IBM Cloud Developer Tools](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
