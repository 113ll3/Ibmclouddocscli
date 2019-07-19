---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 通过 Docker 容器使用 {{site.data.keyword.dev_cli_notm}}
{: #using-idt-from-docker}

通过 {{site.data.keyword.dev_cli_notm}} Docker 容器，您可获得 {{site.data.keyword.cloud}} CLI 以及以下工具：

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 插件
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 插件
* {{site.data.keyword.registrylong_notm}} 插件
* {{site.data.keyword.containerlong_notm}} 插件
* `sdk-gen` 插件

## 开始之前
{: #idt-docker-prereq}

您需要 [{{site.data.keyword.cloud_notm}} 帐户](https://{DomainName}){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")，并且必须安装最新的稳定 Docker 版本，才能执行以下步骤。

## 步骤 1.从 Docker Hub 中拉出 Docker 镜像。
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步骤 2. 启动 Docker 容器。
{: #step2-start-docker}

使用以下命令启动 {{site.data.keyword.dev_cli_notm}} Docker 容器。

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步骤 3. 使用 IBM 标识登录到 {{site.data.keyword.cloud_notm}}。
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

如果凭证被拒绝，说明您可能使用的是联合标识。有关更多详细信息，请参阅[使用联合标识进行登录](/docs/iam?topic=iam-federated_id#federated_id)。
{: tip}

{{site.data.keyword.dev_cli_notm}} CLI 插件使用两个容器来帮助构建和测试应用程序。第一个是 tools 容器，包含用于构建和测试应用程序的必要实用程序。此容器的 `Dockerfile` 由 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 参数定义。您可将其视为开发容器，因为它包含通常用于开发特定运行时的工具。

另一个容器是 run 容器，它能高度模拟应用程序在部署到云之后的实际运行时环境。此容器的形式适合部署以供在 {{site.data.keyword.cloud_notm}} 等中使用。因此，将定义用于启动应用程序的入口点。选择通过 {{site.data.keyword.dev_cli_notm}} CLI 插件来运行应用程序时，它将使用此容器。此容器的 `Dockerfile` 由 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) 参数定义。

现在，您可以开始使用 {{site.data.keyword.dev_cli_notm}} 来管理 {{site.data.keyword.cloud_notm}} 资源以及开发和部署应用程序。
