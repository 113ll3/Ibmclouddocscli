---
copyright:
  years: 2017, 2018
lastupdated: "2018-05-23"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# 有关 IBM Cloud Developer Tools 的故障诊断
{: #ts}

下面列出了所记录的 {{site.data.keyword.dev_cli_notm}} 的一些已知问题及其变通方法。
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## 已知问题
{: #knownissues}

以下各部分描述了已知问题和可能的解决方法。


### 使用非移动模式创建项目时发生主机名错误
{: #hostname}

如果使用 {{site.data.keyword.dev_cli_short}} 通过 Web 应用程序、BFF 或微服务模式来创建项目，那么可能会看到以下错误：

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### 原因
{: #hostname-cause}

导致此错误的原因是登录令牌已到期。


#### 解决方法
{: #hostname-resolution}

请重新登录。

```
ibmcloud login
```
{: codeblock}


### 有关 {{site.data.keyword.dev_cli_short}} 的一般故障
{: #general}

如果使用 {{site.data.keyword.dev_cli_short}} CLI 的 create、delete、list 或 code 命令，那么可能会看到以下错误：

```
Failed to <command> project.
```
{: codeblock}


#### 原因
{: #general-cause}

导致此错误的原因是登录令牌已到期。


#### 解决方法
{: #general-resolution}

请重新登录。

```
ibmcloud login
```
{: codeblock}


### 运行新项目时发生错误：没有此类映像
{: #nosuchimage}

未首先构建项目就运行项目时，可能会看到以下错误。

```
$ ibmcloud dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### 原因
{: #nosuchimage-cause}

必须先构建项目，然后才能运行项目。



#### 解决方法
{: #nosuchimage-resolution}

在当前项目目录中运行以下命令来构建应用程序：

```
ibmcloud dev build
```
{: codeblock}

在当前项目目录中运行以下命令来启动应用程序：

```
ibmcloud dev run
```


### 添加 {{site.data.keyword.objectstorageshort}} 功能时发生服务代理程序错误
{: #os}

如果使用 {{site.data.keyword.dev_cli_short}} 创建具有 {{site.data.keyword.objectstorageshort}} 功能的两个项目，那么可能会看到以下错误：

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### 原因
{: #os-cause}

导致此错误的原因是 {{site.data.keyword.objectstorageshort}} 服务仅在免费套餐中提供一个 {{site.data.keyword.objectstorageshort}} 实例。


#### 解决方法
{: #os-resolution}

系统会提示您选择其他套餐以避免此错误。



### 创建项目期间获取代码失败
{: #code}

如果使用 {{site.data.keyword.dev_cli_short}} 来创建项目，那么可能会看到以下错误：

```
FAILED
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### 原因
{: #code-cause}

导致此错误的原因是内部超时。



#### 解决方法
{: #code-resolution}

可以通过以下任一方式来获取代码：

* 使用 CLI 运行以下命令：

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   将 `<your-project-name>` 替换为在项目创建期间指定的项目名称。

* 使用 {{site.data.keyword.dev_console}}。

	1. 在 {{site.data.keyword.dev_console}} 中选择[项目 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://console.{DomainName}/developer/projects)，然后单击**获取代码**。

	2. 单击**生成代码**。

	3. 生成代码后，单击**下载代码**。



### 对 Node.js 项目运行 `ibmcloud dev run` 时出错
{: #node}

如果要使用 {{site.data.keyword.dev_cli_short}} 对 Node.js Web 或 BFF 项目运行 `ibmcloud dev run`，那么可能会看到以下错误：

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### 原因
{: #node-cause}

`appmetrics` 模块安装在其他体系结构上时，会发生此错误。安装在一个体系结构上的本机 npm 模块不能在另一个体系结构上运行。包含的 Docker 映像基于 Linux 内核。



#### 解决方法
{: #node-resolution}

删除 `node_modules` 文件夹，然后再次运行 `ibmcloud dev run`。


### 未能部署到 {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

您可能尝试使用 {{site.data.keyword.dev_cli_short}} 部署到 {{site.data.keyword.Bluemix_notm}}，但发现没有部署到 {{site.data.keyword.Bluemix_notm}}，而且没有错误。


#### 原因
{: #cause1}

这可能是因为您未登录到帐户。

#### 解决方法
{: #resolution1}

请登录并重试。

```
ibmcloud login
```


### 未能部署到 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes
{: #failuretodeploytokube}

在初始提示输入集群名称后，可能会看到以下失败：

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### 原因
{: #cause2}

导致此错误的最可能的原因是集群名称无效，您可以通过运行带有 `--trace` 的相同命令来进行确认，此时可能会看到以下错误输出：

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### 解决方法
{: #resolution2}

确保使用的集群正确，并且已通过运行以下命令将集群配置为用于部署：

```
ibmcloud cs cluster-config <cluster-name>
```


### 未能部署到 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes

在提示输入部署映像目标后，可能会看到以下失败：

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### 原因
{: #cause3}

导致此错误的最可能的原因是部署映像目标无效。更具体地说，可能是名称空间（部署映像目标中的中间值）无效。


#### 解决方法
{: #resolution3}

确保部署映像目标中的名称空间与通过运行以下命令而找到的其中一个名称空间相匹配：

```
ibmcloud cr namespaces
```



## 附录
{: #appendix}

对于大多数用户，所有必备软件都将使用本页面顶部的平台安装程序进行安装。如果需要手动安装任何组件，请按以下指示信息进行操作：

要安装 dev 插件，必须先安装 [IBM Cloud CLI](../reference/bluemix_cli/get_started.md#getting-started)。

要使用 dev 插件本身，必须运行以下命令来安装该插件：`ibmcloud plugin install dev -r Bluemix`

要在本地运行和调试应用程序，还必须安装 [Docker ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://www.docker.com/get-docker)。

要将应用程序部署为容器，还必须安装 Kubernetes、Helm 和以下 IBM Cloud CLI 插件：

安装 Kubernetes：
* Mac 用户：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux 用户：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows 用户：
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

安装 Helm：
* Mac 和 Linux 用户：
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows 用户：
下载并安装二进制文件：https://github.com/kubernetes/helm/releases/tag/v2.6.0

安装 container-registry 插件：
`ibmcloud plugin install container-registry`

安装 container-service 插件：
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## 获取帮助与支持
{: #gettinghelp}

有关 {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} 或 {{site.data.keyword.dev_cli_notm}} 的问题或疑问，您可以通过在论坛中搜索信息或提问来获取帮助。您还可以开具支持凭单。


在论坛中提问时，可以为问题加上标记，以便通知 {{site.data.keyword.Bluemix_notm}} 开发团队。

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

有关使用 {{site.data.keyword.dev_console}} 或 {{site.data.keyword.dev_cli_notm}} 开发或部署应用程序的技术问题，您可以：

* 在 [Stack Overflow ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) 上发布问题，并为问题加上 `bluemix-dev-services` 和 `ibm-bluemix` 标记。
* 在 [Slack ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://ibm-cloud-tech.slack.com/) 上的 `bluemix-dev-services` 通道中发布问题。请立即[注册 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://ibm.biz/IBMCloudNativeSlack)。


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

有关使用这些论坛的更多详细信息，请参阅[获取帮助 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](/docs/support/index.html#getting-help)。

有关开具 {{site.data.keyword.IBM}} 支持凭单的信息，或有关支持级别和凭单严重性的信息，请参阅[联系支持人员 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](/docs/support/index.html#contacting-support)。

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
