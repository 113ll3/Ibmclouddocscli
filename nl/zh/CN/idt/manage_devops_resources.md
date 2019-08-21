---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# 使用 CLI 管理 DevOps 资源
{: #managing-devops-resources-cli}

可以使用 [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started) 直接通过命令行来管理 DevOps 资源。了解如何使用 CLI 来查看 DevOps 工具链、管道和管道日志。
{: shortdesc}

## 开始之前
{: #set-toolchain-view}

工具链视图取决于当前目标资源组。使用以下命令来识别当前目标资源组，并在需要时对其进行更改。

* 要查看当前目标资源组，请运行以下命令：
  ```
ibmcloud target
``` 
  {: codeblock}

* 如果未设置资源组，或者要更改资源组，请运行以下命令： 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## 查看工具链
{: #viewing-toolchains}

可以通过命令行来查看工具链信息，或在浏览器中查看工具链信息。

* 要查看目标资源组中的工具链，请运行以下命令：
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* 要查看有关该工具链的详细信息，请运行以下命令：
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* 要在浏览器中查看工具链详细信息，请运行以下命令：
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## 查看管道
{: #viewing-pipeline}

要获取调用管道所需的详细信息，请运行 `ibmcloud dev toolchains` 以获取工具链的名称。如果已经知道名称，请运行 `ibmcloud dev toolchain-get [toolchain-name]` 来获取该工具链的详细信息。 

* 要获取管道及其阶段的详细信息，请识别管道及其标识以运行以下命令：
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* 通过使用先前命令中的管道标识，可以运行管道：
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  此命令调用阶段及其作业的执行。成功执行会为所选阶段中的每个作业生成作业执行。

## 查看管道日志
{: #viewing-pipeline-logs}

* 要查看来自管道执行的日志，请运行以下命令：
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* 要按阶段过滤日志，请应用上一个命令并添加阶段标识：
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## 有帮助的 DevOps 命令
{: #helpful-devops-commands}

使用以下 `ibmcloud dev` 命令来管理 DevOps 资源。

### 工具链命令
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains)：查看目标资源组中工具链的列表。
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get)：查看目标资源组中所选工具链的详细信息。
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open)：在浏览器中打开所选工具链。
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete)：删除工具链。

### 管道命令
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get)：查看工具链的管道的详细信息。
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run)：运行管道。
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open)：在浏览器中打开管道。
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log)：查看管道执行的日志。

有关更多信息，请参阅完整的 `ibmcloud dev` [命令参考](/docs/cli/idt?topic=idt-cli)。
