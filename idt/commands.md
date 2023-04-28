---

copyright: 
  years: 2017, 2023
lastupdated: "2023-04-28"

keywords: cli, ibmcloud dev commands, developer cli, dev commands, devtools, developer tools, dev tools, ic dev commands, cli private endpoints, tekton pipelines, classic pipelines, toolchains

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} CLI {{site.data.keyword.dev_cli_short}} (`ibmcloud dev`) commands
{: #idt-cli}

The {{site.data.keyword.cloud}} Command Line Interface includes the {{site.data.keyword.dev_cli_short}} (`ibmcloud dev`) or (`ic dev`) commands to manage classic pipelines, Tekton pipelines, and toolchains.
{: shortdesc}

## help
{: #help}

By default, if no action or arguments are passed in, or if the 'help' action is provided, this command shows a general "Help" text. General help displayed includes a description of the base arguments and a listing of the available actions.  

Run the following command to display General help information:
```bash
ibmcloud dev help
```
{: codeblock}

## pipeline-get
{: #pipeline-get}

View the details of a Classic pipeline.

```bash
ibmcloud dev pipeline-get [PIPELINE_ID] [--output JSON]
```
{: codeblock}

### pipeline-get command parameters
{: #pipeline-get-command-parameters}

#### `json`
{: #json-get}

* Parameter that is used to output the pipeline details in JSON format.
* Usage: `ibmcloud dev pipeline-get [PIPELINE_ID] --output JSON`

The following parameter can be used with the `pipeline-get` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #pipeline-get-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-get [PIPELINE_ID] --trace`

## pipeline-run
{: #pipeline-run}

Run a Classic pipeline.
```bash
ibmcloud dev pipeline-run [PIPELINE_ID] [--stage-id stageID] [--output JSON] 
```
{: codeblock}

### pipeline-run command parameters
{: #pipeline-run-command-parameters}

The following parameters can be used with the `pipeline-run` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `stage-id`
{: #run-stage-id}

* Parameter optionally used to select a pipeline's stage to run
* Usage: `ibmcloud dev pipeline-run [PIPELINE_ID] --stage-id [stageID]`

#### `json`
{: #json-run}

* Parameter that is used to output the pipeline's invocation details in JSON format.
* Usage: `ibmcloud dev pipeline-run [PIPELINE_ID] --output JSON`

#### `trace`
{: #pipeline-run-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-run [PIPELINE_ID] --trace`

## pipeline-log
{: #pipeline-log}

View recent Classic pipeline logs by using the `pipeline-log` command.

* If the pipeline ID is specified as an argument, all logs for all jobs in all stages are printed for that pipeline.
* If the stage ID flag is populated, the logs are filtered by that stage in the pipeline. 
* If the job ID is specified with the stage ID, the logs are filtered to just the job in the stage. 
* If the job execution ID is specified along with the stage ID and job ID, a search is done among all available logs that match the job execution ID specified.

Usage:
```bash
ibmcloud dev pipeline-log [PIPELINE_ID] [--stage-id stageID] [--job-id jobID] [--job-exec-id jobExecutionID]
```
{: codeblock}

### pipeline-log command parameters
{: #pipeline-log-command-parameters}

The following parameters can be used with the `pipeline-log` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `job-id`
{: #job-id}

* Parameter that is used to filter the logs by the job ID.
* Requires the `stage-id` flag.
* Usage: `ibmcloud dev pipeline-log [PIPELINE_ID]  --stage-id [stageID] --job-id [jobID]`

#### `job-exec-id`
{: #job-exec-id}

* Parameter that is used to filter the logs by the job execution ID.
* Requires the `stage-id` flag.
* Requires the `job-id` flag.
* Usage: `ibmcloud dev pipeline-log [PIPELINE_ID]  --stage-id [stageID] --job-id [jobID] --job-exec-id [jobExecutionID]`

#### `stage-id`
{: #log-stage-id}

* Parameter that is used to filter the logs by the stage ID.
* Usage: `ibmcloud dev pipeline-log [PIPELINE_ID]  --stage-id [stageID]`

#### `trace`
{: #pipelog-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-log [PIPELINE_ID] --trace`

## pipeline-open
{: #pipeline-open}

View the URL for the Classic pipeline through the `pipeline-open` command. The `pipeline-open` command also opens the URL in your default browser.
```bash
ibmcloud dev pipeline-open [PIPELINE_ID]
```
{: codeblock}

### pipeline-open command parameters
{: #pipeopen-parameters}

The following parameter can be used with the `pipeline-open` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #pipeline-open-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-open [PIPELINE_ID] --trace`

## tekton-info
{: #tekton-info}

View the details of a Tekton pipeline.

```bash
ibmcloud dev tekton-info [PIPELINE_ID] [--verbose][--output JSON]
```
{: codeblock}

### tekton-info command parameters
{: #tekton-info-command-parameters}

The following parameters can be used with the `tekton-info` command.

#### `verbose`
{: #tekton-info-verbose}

* Use this parameter to provide all details of a pipeline in JSON format.
* Usage: `ibmcloud dev tekton-info [PIPELINE_ID] --verbose`

#### `json`
{: #json-tekton-info}

* Parameter that is used to output the pipeline details in JSON format.
* Usage: `ibmcloud dev tekton-info [PIPELINE_ID] --output JSON`

#### `trace`
{: #tekton-info-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-info [PIPELINE_ID] --trace`

## tekton-logs
{: #tekton-logs}

View recent Tekton pipeline run logs by using the `tekton-logs` command.

* The pipeline run ID is a required argument.
* If the task name is specified as an argument, only the logs for this task are retrieved.

Usage:
```bash
ibmcloud dev tekton-logs [PIPELINE_ID] --run-id [pipelinerunID] [--task-name taskName] [--output JSON]
```
{: codeblock}

### tekton-logs command parameters
{: #tekton-logs-command-parameters}

The following parameters can be used with the `tekton-logs` command.

#### `run-id` (required)
{: #run-id}

* Parameter that identifies the pipeline run for the log retrieval.
* Usage: `ibmcloud dev tekton-logs [PIPELINE_ID]  --run-id [pipelinerunID]`

#### `task-name`
{: #task-name}

* Parameter that is used to filter the logs by the pipeline run task name.
* Usage: `ibmcloud dev tekton-logs [PIPELINE_ID]  --run-id [pipelinerunID] --task-name [taskName]`

#### `json`
{: #json-tekton-logs}

* Parameter that is used to output the log details in JSON format.
* Usage: `ibmcloud dev tekton-logs [PIPELINE_ID]  --run-id [pipelinerunID] --output JSON`

#### `trace`
{: #tekton-logs-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-logs [PIPELINE_ID]  --run-id [pipelinerunID] --trace`

## tekton-pipeline-cancel
{: #tekton-pipeline-cancel}

Cancel an ongoing Tekton pipeline run.

```bash
ibmcloud dev tekton-pipeline-cancel [PIPELINE_ID] --run-id [pipelinerunID] [--trace]`
```
{: codeblock}

### tekton-pipeline-cancel command parameters
{: #tekton-pipeline-cancel-command-parameters}

The following parameters can be used with the `tekton-pipeline-cancel` command.

#### `run-id` (required)
{: #tekton-pipeline-cancel-run-id}

* Parameter that identifies the pipeline run to cancel.
* Usage: `ibmcloud dev tekton-pipeline-cancel [PIPELINE_ID] --run-id [pipelinerunID]`

#### `trace`
{: #tekton-pipeline-cancel-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-pipeline-cancel [PIPELINE_ID] --run-id [pipelinerunID] --trace`

## tekton-pipelinerun
{: #tekton-pipelinerun}

View the details of a Tekton pipeline run or use the `ls` parameter to list all pipeline runs for the pipeline.

Usage:
```bash
ibmcloud dev tekton-pipelinerun [PIPELINE_ID] --run-id [pipelinerunID] [--output JSON]
ibmcloud dev tekton-pipelinerun ls [PIPELINE_ID]
```
{: codeblock}

### tekton-pipelinerun command parameters
{: #tekton-pipelinerun-command-parameters}

The following parameters can be used with the `tekton-pipelinerun` command.

#### `run-id` (required)
{: #tekton-pipelinerun-run-id}

* Parameter that identifies the pipeline run to retrieve.
* Usage: `ibmcloud dev tekton-pipelinerun [PIPELINE_ID] --run-id [pipelinerunID]`

#### `json`
{: #json-tekton-pipelinerun}

* Parameter that is used to output the pipeline run details in JSON format.
* Usage: `ibmcloud dev tekton-pipelinerun [PIPELINE_ID] --run-id [pipelinerunID] --output JSON`

#### `trace`
{: #tekton-pipelinerun-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-pipelinerun [PIPELINE_ID] --run-id [pipelinerunID] --trace`

## tekton-pipelineruns
{: #tekton-pipelineruns}

View a list of pipeline runs for a Tekton pipeline.

Usage:
```bash
ibmcloud dev tekton-pipelineruns [PIPELINE_ID] [--output JSON]
```
{: codeblock}

### tekton-pipelineruns command parameters
{: #tekton-pipelineruns-command-parameters}

The following parameters can be used with the `tekton-pipelineruns` command.

#### `json`
{: #json-tekton-pipelineruns}

* Parameter that is used to output the pipeline runs in JSON format.
* Usage: `ibmcloud dev tekton-pipelineruns [PIPELINE_ID] --output JSON`

#### `trace`
{: #tekton-pipelineruns-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-pipelineruns [PIPELINE_ID] --trace`

## tekton-trigger
{: #tekton-trigger}

Run a Tekton pipeline.

Usage:
```bash
ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName [--trigger-properties propertiesJSON] [--secure-trigger-properties securePropertiesJSON] [--trigger-headers headerJSON] [--trigger-body bodyJSON] [--output JSON]
```
{: codeblock}

### tekton-trigger command parameters
{: #tekton-trigger-command-parameters}

The following parameters can be used with the `tekton-trigger` command.

#### `trigger-name` (required)
{: #tekton-trigger-name}

* Use this parameter to indicate the trigger to be run.
* Usage: `ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName`

#### `trigger-properties` (optional)
{: #tekton-trigger-properties}

* Optional. Use this parameter to override or append to defined trigger properties. For example,`'{"pipeline-debug":"true"}'`.
* Usage: `ibmcloud dev tekton-trigger pipePIPELINE_IDlineID --trigger-name triggerName --trigger-properties propertiesJSON`

#### `secure-trigger-properties` (optional)
{: #tekton-secure-trigger-properties}

* Optional. Use this parameter to override or append to defined trigger properties whose values should be concealed behind dots or asterisks in later outputs. For example, `'{"deployer-api-key":"s0mEThING_v3Ry_s3CReT"}'`
* Usage: `ibmcloud dev tekton-trigger pipePIPELINE_IDlineID --trigger-name triggerName --secure-trigger-properties securePropertiesJSON`


#### `trigger-headers` (optional)
{: #tekton-trigger-header}

* Optional. Use this parameter to specify the headers that are used in triggerBinding of a Tekton pipelineRun. For example,`'{"source":"cli","flag":"enable"}'`.
* Usage: `ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName --trigger-headers headerJSON`

#### `trigger-body` (optional)
{: #tekton-trigger-body}

* Optional. Use this parameter to specify the body that is used in triggerBinding of a Tekton pipelineRun. For example,`'{"message":"hello world","flag":"enable"}'`.
* Usage: `ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName --trigger-body bodyJSON`

#### `json`
{: #json-tekton-trigger}

* Use this parameter to output the trigger results in JSON format.
* Usage: `ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName --output JSON`

#### `trace`
{: #tekton-trigger-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-trigger PIPELINE_ID --trigger-name triggerName --trace`


## toolchain-delete
{: #toolchain-delete}

Delete a toolchain. If no toolchain name is provided, you can select one from a list. The list of toolchains depends on the currently targeted resource group and region.

The targeted Resource Group is found in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target).
```bash
ibmcloud dev toolchain-delete [toolchainName] [--force,-f]
```
{: codeblock}

### toolchain-delete command parameters
{: #toolchain-delete-command-parameters}

The following parameters can be used with the `toolchain-delete` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `force`
{: #toolchain-delete-force}

* Parameter that is used to skip the prompt confirmation for deleting a toolchain.
* Usage: `ibmcloud dev toolchain-delete [toolchainName] --force`

#### `trace`
{: #toolchain-delete-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-delete [toolchainName] --trace`

## toolchain-get
{: #toolchain-get}

View the details of a toolchain. If no toolchain name is provided, you can select one from a list. 

Uses the targeted resource group in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target). Some Cloud Foundry-based toolchains might not be compatible with this command.
```bash
ibmcloud dev toolchain-get [toolchainName] [--output JSON]
```
{: codeblock}

### toolchain-get command parameters
{: #toolchain-get-command-parameters}

The following parameters can be used with the `toolchain-get` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `json`
{: #json-toolchain-get}

* Parameter that is used to output the toolchain details in JSON format.
* Usage: `ibmcloud dev toolchain-get [toolchainName] --output JSON`

#### `trace`
{: #toolchain-get-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-get [toolchainName] --trace`

## toolchain-open
{: #toolchain-open}

View the URL for the toolchain through the `toolchain-open` command. The `toolchain-open` command also opens the URL in your default browser. If no toolchain name is provided, a list of toolchains is provided to select from.
```bash
ibmcloud dev toolchain-open [toolchainName]
```
{: codeblock}

### toolchain-open command parameters
{: #toolchain-open-parameters}

The following parameter can be used with the `toolchain-open` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #toolchain-open-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-open [toolchainName] --trace`

## toolchains
{: #toolchains}

View a list of toolchains in the current resource group. 

Uses the targeted Resource Group in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target). Some Cloud Foundry-based toolchains might not be compatible with this command.

```bash
ibmcloud dev toolchains [--output JSON]
```
{: codeblock}

### toolchains command parameters
{: #toolchains-command-parameters}

The following parameters can be used with the `toolchains` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `json`
{: #json-toolchains}

* Parameter that is used to output the toolchains in JSON format.
* Usage: `ibmcloud dev toolchains --output JSON`

#### `trace`
{: #toolchains-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchains --trace`
