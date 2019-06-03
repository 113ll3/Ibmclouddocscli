---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: cli, ibmcloud dev enable, python, cloud enable python, django, deploy python, build python, python debug, python troubleshoot, python cloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 클라우드 배치에 기존 Python 애플리케이션 사용
{: #enable-existing-python}

[{{site.data.keyword.dev_cli_long}} CLI 사용 명령](/docs/cli/idt?topic=cloud-cli-idt-cli#enable)을 사용하여 Python 애플리케이션이 {{site.data.keyword.cloud}}에서 실행되도록 하는 데 필요한 파일을 생성할 수 있습니다.

## Python 앱 사용
{: #enable-app-python}

Python 프로젝트의 루트 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev enable
```
{: codeblock}

* 프로젝트, **Python - Flask** 또는 **Python-Django**에 대해 발견된 프레임워크를 확인하도록 프롬프트가 표시되면 `y`를 선택하십시오. 
* 그러면 **IBM Cloud 앱에 연결**하라는 프롬프트가 표시됩니다. 앱에 **Generate assets, create a new IBM Cloud app and connect to it** 또는 **Generate assets without connecting to an IBM Cloud app** 옵션을 선택하십시오.
* `enable` 명령은 서비스를 작성하여 앱에 바인드할 수도 있습니다. 이 기본 예제에서는 `n`을 선택하십시오.

다음 샘플 결과를 참조하십시오.
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

## 클라우드 지원 Python 앱 빌드 및 배치
{: #build-deploy-python}

다음으로 [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) 명령을 사용하여 앱을 빌드하십시오.
```
ibmcloud dev build
```
{: codeblock}

빌드가 완료되면 다음 [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) 명령을 사용하여 앱을 {{site.data.keyword.cloud_notm}}에 배치할 수 있습니다.
```
ibmcloud dev deploy
```
{: codeblock}

## 사용하도록 설정된 앱이 빌드 또는 배치되지 않는 경우 수행할 작업
{: #build-failure-python}

`enable` 명령으로 모든 앱을 사용으로 설정할 수 있는 것은 아닙니다. 예를 들어, 다음 오류는 프로젝트 이름이 `wsgi.py` 및 `settings.py` 파일이 포함된 디렉토리 이름과 다른 경우에 발생할 수 있습니다.
```
가져오기 오류: <projectname>.wsgi라는 이름의 모듈이 없음
```
{: screen}

`<projectname>.wsgi` 파일 이름은 사용으로 설정되는 프로젝트의 이름입니다.

`ibmcloud dev enable`을 실행한 후 앱이 빌드되거나 배치되지 않는 경우 생성된 파일을 수정하여 클라우드 사용 설정을 완료할 수 있습니다.

### 생성된 클라우드 사용 가능 파일을 수동으로 구성
{: #manual-enable-python}

Django 프레임워크를 사용하는 Python 앱을 사용으로 설정하려면 Dockerfile에서 `CMD` 행을 프로젝트를 실행하는 데 일반적으로 사용하는 명령으로 업데이트하십시오.

예를 들어, 프로젝트를 실행하는 데 사용하는 명령이 다음과 같은 경우:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

다음과 같이 Dockerfile에서 `CMD` 항목을 업데이트하십시오.
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## 다음 단계
{: #next_steps_existing_python notoc}

자세한 정보는 [IBM Cloud Developer Tools CLI ](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli)를 참조하십시오.
