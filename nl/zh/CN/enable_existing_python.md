---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, ibmcloud dev enable, python, cloud enable python, django, deploy python, build python, python debug, python troubleshoot, python cloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 启用现有 Python 应用程序以进行云部署
{: #enable-existing-python}

您可以通过使用 [{{site.data.keyword.dev_cli_long}} CLI enable 命令](/docs/cli/idt?topic=cloud-cli-idt-cli#enable)，生成支持 Python 应用程序在 {{site.data.keyword.cloud}} 上运行所需的文件。

## 启用 Python 应用程序
{: #enable-app-python}

从 Python 项目的根目录中输入以下命令：
```
ibmcloud dev enable
```
{: codeblock}

* 系统提示您验证检测到的项目框架 **Python - Flask** 或 **Python - Django** 时，请回复 `y`。 
* 然后，将会提示您 **Connect to an IBM Cloud app**。选择 **Generate assets, create a new IBM Cloud app and connect to it** 或 **Generate assets without connecting to an IBM Cloud app** 选项以连接您的应用程序。
* `enable` 命令还可以创建服务并将其绑定到应用程序。对于此基本示例，请回复 `n`。

请参阅以下样本输出：
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
{: screen}

## 构建和部署云支持的 Python 应用程序
{: #build-deploy-python}

接下来，使用 [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) 命令构建应用程序：
```
ibmcloud dev build
```
{: codeblock}

如果成功完成构建，您可以使用以下 [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) 命令将应用程序部署到 {{site.data.keyword.cloud_notm}}：
```
ibmcloud dev deploy
```
{: codeblock}

## 如果已启用的应用程序未构建或部署，该怎么做
{: #build-failure-python}

`enable` 命令并不能成功启用所有应用程序。例如，当项目名称与包含 `wsgi.py` 和 `settings.py` 文件的目录名称不同时，可能会发生以下错误：
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

`<projectname>.wsgi` 文件名是正在启用的项目的名称。

如果在运行 `ibmcloud dev enable` 后未构建或部署应用程序，那么可以修改生成的文件以完成云支持。

### 手动配置生成的云支持文件
{: #manual-enable-python}

要启用使用 Django 框架的 Python 应用程序，请将 Dockerfile 中的 `CMD` 行更新为通常用于运行项目的命令。

例如，如果用于运行项目的命令是：
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

在 Dockerfile 中更新 `CMD` 条目，例如：
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## 后续步骤
{: #next_steps_existing_python notoc}

有关更多信息，请参阅 [IBM Cloud Developer Tools CLI](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli)。
