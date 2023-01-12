---

copyright:
  years: 2018, 2022
lastupdated: "2022-03-17"

keywords: cli, general commands, ibmcloud commands, ibmcloud, cli commands, update, environment variables

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} CLI (ibmcloud) environment variables
{: #ibmcloud_env_var}

Use the {{site.data.keyword.cloud}} CLI (ibmcloud) environment variables to customize your {{site.data.keyword.cloud_notm}} CLI environment to suit your needs. For example, you can simplify API key-based login to have multiple different CLI sessions in parallel.
{: shortdesc}

## Get help on the {{site.data.keyword.cloud_notm}} CLI (ibmcloud) environment variables
{: #get_help}

```bash
ibmcloud --help
```
{: codeblock}

In your shell, set the following environment variables by using a `VARIABLE_NAME=VALUE` pair directly in front of the shell command, or by using `export VARIABLE_NAME=VALUE` as a separate command before you run the shell command. 

## IBMCLOUD_COLOR=false
{: #IBMCLOUD_COLOR}

Control colorized output by setting `IBMCLOUD_COLOR` to true or false.

## IBMCLOUD_VERSION_CHECK=false
{: #IBMCLOUD_VERSION_CHECK}

Control the regular versioning check for updating the CLI tool by setting `IBMCLOUD_VERSION_CHECK` to true or false.

## IBMCLOUD_HTTP_TIMEOUT=5
{: #IBMCLOUD_HTTP_TIMEOUT}

Control the time limit in seconds for HTTP requests.

## IBMCLOUD_API_KEY=api_key_value
{: #IBMCLOUD_API_KEY}

Use the `ibmcloud login` command to authenticate by using an API key. The key can be specified directly as value or by referencing the name of the file that contains the key by using `@filename`.

## IBMCLOUD_CR_TOKEN=cr_token_value
{: #IBMCLOUD_CR_TOKEN}

The compute resource token used for login, which can either be a token string or a path to a `@file`.

## IBMCLOUD_CR_PROFILE=profile_value
{: #IBMCLOUD_CR_PROFILE}

The name, ID, or CRN of the linked trusted IAM profile to be used when obtaining the IAM access token. If authenticating as a VPC VSI compute resource, specifying only a trusted profile CRN or ID is supported.

## IBMCLOUD_CR_VPC_URL=url_value
{: #IBMCLOUD_CR_VPC_URL}

The custom server URL to use when obtaining an instance identity token and IAM token as a VPC VSI compute resource. This value replaces the default server endpoint of the VPC VSI instance identity token service.

## IBMCLOUD_TRACE=true
{: #IBMCLOUD_TRACE}

Prints API request diagnostics to stdout. Use this variable to investigate how CLI commands are run. This variable prints many useful details to the standard output (your terminal). Use it to investigate how the CLI commands interact with the IBM Cloud platform and service APIs. 

## IBMCLOUD_TRACE=path/to/trace.log
{: #IBMCLOUD_TRACE_PATH}

Appends API request diagnostics to a log file. This variable prints many useful details to the specified log file. 

## IBMCLOUD_HOME=path/to/dir
{: #IBMCLOUD_PATH_TO_DIR}

Specifies the path to the configuration directory. The `ibmcloud` command reads and writes its session metadata to and from the specified path. Use the variable to work with multiple accounts or multiple sessions at the same time.

For more information about this environment variable, see [Working with multiple sessions with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-ibmcloud-home).
