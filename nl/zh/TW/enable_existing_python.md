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

# 啟用現有 Python 應用程式進行雲端部署
{: #enable-existing-python}

您可以使用 [{{site.data.keyword.dev_cli_long}} CLI enable 指令](/docs/cli/idt?topic=cloud-cli-idt-cli#enable)，來產生讓 Python 應用程式在 {{site.data.keyword.cloud}} 上執行所需的檔案。

## 啟用 Python 應用程式
{: #enable-app-python}

從 Python 專案的根目錄中，輸入下列指令：
```
ibmcloud dev enable
```
{: codeblock}

* 系統提示您驗證專案的偵測到架構時，請選取 **Python - Flask** 或 **Python - Django**，並回覆 `y`。 
* 然後，系統會提示您 **Connect to an IBM Cloud app**。請針對您的應用程式選取 **Generate assets, create a new IBM Cloud app and connect to it** 或 **Generate assets without connecting to an IBM Cloud app** 選項。
* `enable` 指令也可以建立服務，並將它們連結至應用程式。對於這個基本範例，請回覆 `n`。

請參閱下列輸出範例：
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

## 建置並部署具備雲端功能的 Python 應用程式
{: #build-deploy-python}

接下來，請使用 [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) 指令來建置應用程式：
```
ibmcloud dev build
```
{: codeblock}

如果建置順利完成，您可以使用下列 [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) 指令，將應用程式部署至 {{site.data.keyword.cloud_notm}}：
```
ibmcloud dev deploy
```
{: codeblock}

## 如果已啟用的應用程式無法建置或部署，應該如何處理
{: #build-failure-python}

並非所有應用程式都會順利由 `enable` 指令啟用。例如，當專案名稱與包含 `wsgi.py` 和 `settings.py` 檔案的目錄不同時，可能會發生下列錯誤：
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

`<projectname>.wsgi` 檔案名稱就是所啟用之專案的名稱。

如果在執行 `ibmcloud dev enable` 之後您的應用程式無法建置或部署，您可以修改產生的檔案，以完成雲端啟用。

### 手動配置產生的雲端啟用檔案
{: #manual-enable-python}

若要啟用使用 Django 架構的 Python 應用程式，請將 Dockerfile 中的 `CMD` 行更新為您通常用來執行專案的指令。

例如，如果您用來執行專案的指令是：
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

請如下更新 Dockerfile 中的 `CMD` 項目：
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## 後續步驟
{: #next_steps_existing_python notoc}

如需相關資訊，請參閱 [IBM Cloud Developer Tools CLI](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli)。
