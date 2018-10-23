---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 通过 Docker 容器使用 {{site.data.keyword.dev_cli_notm}}

通过 {{site.data.keyword.dev_cli_notm}} Docker 容器，您可获得 {{site.data.keyword.Bluemix}} CLI 以及以下工具：

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
{: #prereq}

您需要 [{{site.data.keyword.Bluemix_notm}} 帐户](https://console.bluemix.net/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")，并且必须安装最新的稳定 Docker 版本后，才可执行以下步骤。

## 步骤 1.从 Docker Hub 中拉出 Docker 镜像。
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步骤 2. 启动 Docker 容器。
{: #step2}

使用以下命令启动 {{site.data.keyword.dev_cli_notm}} Docker 容器。

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 步骤 3. 使用 IBM 标识登录到 {{site.data.keyword.Bluemix_notm}}。
{: #step3}

```
ibmcloud login
```
{: codeblock}


如果凭证被拒绝，说明您可能使用的是联合标识。有关更多详细信息，请参阅[使用联合标识进行登录](/docs/iam/login_fedid.html#federated_id)。
{: tip}

现在，您已准备好使用 {{site.data.keyword.dev_cli_notm}} 来管理 {{site.data.keyword.Bluemix_notm}} 资源并开发和部署应用程序。
