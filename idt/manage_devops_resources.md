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

# Managing DevOps resources with the CLI
{: #managing-devops-resources-cli}

You can use the [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started) to manage DevOps resources directly from the command line. Learn to use the CLI to view DevOps toolchains, pipelines, and pipeline logs.
{: shortdesc}

## Before you begin
{: #set-toolchain-view}

The toolchain view depends on the currently targeted resource group. Use the following commands to identify your currently targeted resource group, and change it if want to.

* To view the currently targeted resource group, run:
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* If no resource group is set, or if you would like to change the resource group, run: 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Viewing a toolchain
{: #viewing-toolchains}

You can view toolchain information from the command line or view it in a browser.

* To view toolchains in the targeted resource group, run:
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* To view details about that toolchain, run:
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* To view the toolchain details in the browser, run:
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Viewing a pipeline
{: #viewing-pipeline}

To get the details required to invoke a pipeline, run `ibmcloud dev toolchains` to get the name of the toolchain. If the name is already known, run `ibmcloud dev toolchain-get [toolchain-name]` to get the details of the toolchain. 

* To get the details of a pipeline and its stages, identify the pipeline and its ID to run the following command:
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* Using the pipeline ID from the previous command, you can run the pipeline:
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  This command invokes an execution of the stage and its jobs. A successful execution results in the job execution for each job in the selected stage.

## Viewing pipeline logs
{: #viewing-pipeline-logs}

* To view the logs from a pipeline's execution, run:
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* To filter the logs by stage, apply the previous command and add the stage ID:
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Helpful DevOps commands
{: #helpful-devops-commands}

Use the following `ibmcloud dev` commands to manage DevOps resources.

### Toolchain commands
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) View a list of toolchains in the targeted resource group.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) View the details for a selected toolchain in the targeted resource group.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) Open the selected toolchain in the browser.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) Delete a toolchain.

### Pipeline commands
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) View the details of a toolchain's pipeline.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) Run a pipeline.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) Open the pipeline in the browser.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) View the logs of a pipeline's execution.

For more information, see the full `ibmcloud dev` [command reference](/docs/cli/idt?topic=idt-cli).
