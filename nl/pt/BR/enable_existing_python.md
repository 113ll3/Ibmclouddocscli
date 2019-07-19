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

# Ativando aplicativos Python existentes para implementação na nuvem
{: #enable-existing-python}

É possível gerar os arquivos que são necessários para permitir que o aplicativo Python seja executado no {{site.data.keyword.cloud}} usando o [comando enable da CLI do {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-idt-cli#enable).

## Ativando seu aplicativo Python
{: #enable-app-python}

Insira o comando a seguir por meio do diretório raiz de seu projeto Python:
```
Ibmcloud dev enable
```
{: codeblock}

* Quando for solicitado que você verifique a estrutura detectada para o projeto, **Python - Flask** ou **Python - Django**, responda `y`. 
* Então, será solicitado: **Conectar a um app IBM Cloud**. Selecione as opções **Gerar ativos, criar um novo app do IBM Cloud e conectar-se a ele** ou **Gerar ativos sem se conectar a um app do IBM Cloud** para seu aplicativo.
* O comando `enable` também pode criar serviços e ligá-los ao seu aplicativo. Para esse exemplo básico, responda `n`.

Consulte a seguinte saída de amostra:
```
> ibmcloud dev enable
The enable feature is currently in Beta.
Please provide your experience and feedback at: https://ibm-cloud-tech.slack.com/messages/developer-tools/
Only server-side applications are supported by the enable feature

? Python - Flask application discovered. Do you want to proceed with this language choice? [ y/n ] > y


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

## Construa e implemente um aplicativo Python ativado para nuvem
{: #build-deploy-python}

Em seguida, construa seu aplicativo com o comando [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build):
```
ibmcloud dev build
```
{: codeblock}

Se a construção for concluída com êxito, será possível implementar seu aplicativo no {{site.data.keyword.cloud_notm}} com o comando [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) a seguir:
```
ibmcloud dev deploy
```
{: codeblock}

## O que fazer se o aplicativo ativado não construir nem implementar
{: #build-failure-python}

Nem todos os aplicativos são ativados com êxito pelo comando `enable`. Por exemplo, o erro a seguir pode ocorrer quando o nome do projeto é diferente do nome de diretório que contém os arquivos `wsgi.py` e `settings.py`:
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

O nome do arquivo `<projectname>.wsgi` é o nome do projeto que está sendo ativado.

Se o seu aplicativo não for construído nem implementado depois de você executar `ibmcloud dev enable`, será possível modificar os arquivos gerados para concluir a ativação da nuvem.

### Configurando manualmente os arquivos de ativação de nuvem gerados
{: #manual-enable-python}

Para ativar apps Python que usam a estrutura Django, atualize a linha `CMD` no Dockerfile para o comando que você normalmente usa para executar seu projeto.

Por exemplo, se o comando que você usa para executar o projeto for:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Atualize a entrada `CMD` em seu Dockerfile assim:
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## Próximas Eta
{: #next_steps_existing_python notoc}

Para obter mais informações, consulte a [CLI do IBM Cloud Developer Tools](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli).
