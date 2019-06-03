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

# 既存の Python アプリケーションのクラウド・デプロイメント使用可能化
{: #enable-existing-python}

[{{site.data.keyword.dev_cli_long}} CLI enable コマンド](/docs/cli/idt?topic=cloud-cli-idt-cli#enable)を使用して、Python アプリケーションを {{site.data.keyword.cloud}} で実行できるようにするために必要なファイルを生成できます。

## Python アプリの使用可能化
{: #enable-app-python}

Python プロジェクトのルート・ディレクトリーから、次のコマンドを入力します。
```
ibmcloud dev enable
```
{: codeblock}

* プロジェクトの検出されたフレームワークである **Python - Flask** または **Python - Django** を検証するようプロンプトが表示されたら、「`y`」と応答します。 
* 次に、**IBM Cloud アプリに接続**するよう、プロンプトが表示されます。 アプリに対して**「アセットを生成し、新規 IBM Cloud アプリを作成し、それに接続する (Generate assets, create a new IBM Cloud app and connect to it)」**オプション、または**「IBM Cloud アプリに接続しないでアセットを生成する (Generate assets without connecting to an IBM Cloud app)」**オプションのいずれかを選択します。
* `enable` コマンドは、サービスを作成して、それをアプリにバインドすることもできます。 この基本的な例では、「`n`」と応答します。

次の出力例を参照してください。
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

## クラウド対応の Python アプリのビルドおよびデプロイ
{: #build-deploy-python}

次に、[`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) コマンドを使用してアプリをビルドします。
```
ibmcloud dev build
```
{: codeblock}

ビルドが正常に完了した場合は、次の [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) コマンドを使用して {{site.data.keyword.cloud_notm}} にアプリをデプロイできます。
```
ibmcloud dev deploy
```
{: codeblock}

## 使用可能アプリがビルドまたはデプロイされていない場合の対応
{: #build-failure-python}

`enable` コマンドによってすべてのアプリが正常に使用可能になる訳ではありません。 例えば、`wsgi.py` ファイルおよび `settings.py` ファイルが含まれるディレクトリー名とプロジェクト名が異なる場合は、次のエラーが発生する可能性があります。
```
ImportError: No module named <projectname>.wsgi
```
{: screen}

`<projectname>.wsgi` ファイル名は、有効化されているプロジェクトの名前です。

`ibmcloud dev enable` を実行した後にアプリがビルドやデプロイを行わない場合は、生成されたファイルを変更してクラウド使用可能化を完了できます。

### 生成されたクラウド使用可能化ファイルの手動による構成
{: #manual-enable-python}

Django フレームワークを使用する Python アプリを使用可能にするには、Dockerfile の `CMD` 行を、プロジェクトを実行するために通常使用するコマンドに更新します。

例えば、プロジェクトを実行するのに使用するコマンドが以下の場合:
```
gunicorn -b 0.0.0.0:3000 --env DJANGO_SETTINGS_MODULE=<projectname>.settings.production <projectname>.wsgi
```
{: codeblock}

Dockerfile の `CMD` エントリーを次のように更新します。
```
CMD ["gunicorn", "-b", "0.0.0.0:3000", "--env", "DJANGO_SETTINGS_MODULE=<projectname>.settings.production", "<projectname>.wsgi"]
```
{: codeblock}

## 次のステップ
{: #next_steps_existing_python notoc}

詳しくは、[IBM Cloud Developer Tools CLI](/docs/cli/idt?topic=cloud-cli-idt-cli#idt-cli)を参照してください。
