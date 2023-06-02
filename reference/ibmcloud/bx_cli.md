---

copyright:
  years: 2018, 2023
lastupdated: "2023-06-02"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# General {{site.data.keyword.cloud_notm}} CLI (ibmcloud) commands
{: #ibmcloud_cli}

The {{site.data.keyword.cloud}} Command Line Interface provides a set of commands that are grouped by namespace for users to interact with {{site.data.keyword.cloud_notm}}.
{: shortdesc}

The following commands are supported by the {{site.data.keyword.cloud_notm}} CLI, including their names, arguments, options, prerequisites, descriptions, and examples.

## Global prerequisites
{: #global-prereqs}

The prerequisites for each command describe which actions are required before you run the command. The prerequisites can include one or more of the following actions:

Docker
:   Install the Docker CLI.

Endpoint
:   Use the [`ibmcloud api` command](#ibmcloud_api) to set an API endpoint.

Log in
:   Use the [`ibmcloud login` command](#ibmcloud_login) to log in. If you log in with a federated ID, use the `--sso` option to authenticate with a one time passcode. Or use the `--apikey` option to authenticate with an API key.

Target
:   Use the [`ibmcloud target` command](#ibmcloud_target) to set or view the target account or region.

## Global options
{: #global-options}

The following options are available for most commands in the {{site.data.keyword.cloud_notm}} CLI. To check whether an option is available for a specific command, use the `-h, --help` option with the command.

### `--output FORMAT`
{: #global-option-output}

Specifies an output format. Only JSON is supported.

#### Examples
{: #global-option-output-examples}

Print available resource groups in JSON format:

```bash
ibmcloud resource groups --output json
```
{: codeblock}

### `-q, --quiet`
{: #global-option-quiet}

Suppresses verbose messages. Prompt messages like `Getting information from... as ...` do not display if `-q, --quiet` is specified.

#### Examples
{: #global-option-quiet-examples}

Print available resource groups in quiet mode:

```bash
ibmcloud resource groups -q
```
{: codeblock}

## ibmcloud help
{: #ibmcloud_help}

Displays the general help for first-level built-in commands and supported namespaces of {{site.data.keyword.cloud_notm}} CLI, or the help for a specific built-in command or namespace.

```bash
ibmcloud help [COMMAND|NAMESPACE]
```

### Prerequisites
{: #help-prereqs}

None.

### Command options
{: #help-options}

COMMAND|NAMESPACE
:   The command or namespace that help is displayed for. If not specified, the general help for {{site.data.keyword.cloud_notm}} CLI is shown. Optional.

### Examples
{: #help-examples}

Display general help for the {{site.data.keyword.cloud_notm}} CLI:

```bash
ibmcloud help
```
{: codeblock}

Display help for the `dev` command:

```bash
ibmcloud help dev
```
{: codeblock}

## ibmcloud version
{: #ibmcloud_version}

Print the version of the {{site.data.keyword.cloud_notm}} CLI.

```bash
ibmcloud version
```

### Prerequisites
{: #version-prereqs}

None.

### Command options
{: #version-options}

None.

### Examples
{: #version-examples}

Print the version of the {{site.data.keyword.cloud_notm}} CLI:

```bash
ibmcloud version
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Set or view the {{site.data.keyword.cloud_notm}} API endpoint.

```bash
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation] [--vpc]
```

### Prerequisites
{: #api-prereqs}

None.

### Command options
{: #api-options}

API_ENDPOINT
:   The API endpoint that is targeted, for example, `https://cloud.ibm.com`. If both the `API_ENDPOINT` and `--unset` options aren't specified, the current API endpoint is displayed. Optional.

--skip-ssl-validation
:   Bypass SSL validation of HTTP requests. This option isn't recommended.

--vpc 
:   Use a VPC connection for a private API endpoint.

--unset
:   Remove the API endpoint setting.

### Examples
{: #api-examples}

Set the API endpoint to `cloud.ibm.com`:

```bash
ibmcloud api cloud.ibm.com
```
{: codeblock}

Set the API endpoint to cloud.ibm.com and bypass SSL validation.

```bash
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

View the current API endpoint:

```bash
ibmcloud api
```
{: codeblock}

Remove the API endpoint:

```bash
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Writes default values to the configuration file.

```bash
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | 
         --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Prerequisites
{: #config-prereqs}

None.

### Command options
{: #config-options}

--check-version
:   Enable or disable CLI version checking. Valid values are `true` or `false`.

--color
:   Enable or disable color output. This option is disabled by default. Valid values are `true` or `false`.

--http-timeout
:   The timeout value for HTTP requests in seconds. The default value is 60 seconds.

--locale<
:   Set a default locale. If no value is specified, the previous locale is deleted.

--trace
:   Trace HTTP requests to the terminal or specified file. Valid values are `true` or `false`.

You can specify only one of the options at a time.
{: tip}

### Examples
{: #config-examples}

Set HTTP request timeout to 30 seconds:

```bash
ibmcloud config --http-timeout 30
```
{: codeblock}

Enable trace output for HTTP requests:

```bash
ibmcloud config --trace true
```
{: codeblock}

Trace HTTP requests to the `/home/usera/my_trace` file:

```bash
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Disable color output:

```bash
ibmcloud config --color false
```
{: codeblock}

Set the locale to `zh_Hans`:

```bash
ibmcloud config --locale zh_Hans
```
{: codeblock}

Clear the locale settings:

```bash
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Log in to the {{site.data.keyword.cloud_notm}} CLI:

```bash
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--cr-token (TOKEN | @CR_TOKEN_FILE) | --vpc-cri] [--profile PROFILE_ID | PROFILE_NAME | PROFILE_CRN] [-c (ACCOUNT_ID | ACCOUNT_OWNER_USER_ID) | --no-account] [--accept] [-g (RESOURCE_GROUP_NAME | RESOURCE_GROUP_ID)] [-r REGION | --no-region] [--vpc]
```
{: codeblock}

### Prerequisites
{: #login-prereqs}

None.

### Command options
{: #login-options}

-a API_ENDPOINT
:   The API endpoint. For example, `cloud.ibm.com`. Or, use `private.cloud.ibm.com` to log in by using a private endpoint. Using this flag saves the API endpoint to the configuration file.

--sso
:   Specify this option to [log in with a federated ID](/docs/account?topic=account-federated_id). Using this option prompts you to authenticate with your single sign-on provider and enter a one-time passcode to log in.

-u USERNAME
:   The user name. Optional.

-p PASSWORD
:   The user password. Optional.

--apikey API_KEY or @API_KEY_FILE_PATH
:   The API key content or the path of an API key file that is indicated by the @ symbol.

--cr-token TOKEN or @CR_TOKEN_FILE_PATH
:   The compute resource token content or the path of a compute resource token file that is indicated by the @ symbol. If provided, the `--profile` flag, or `IBMCLOUD_CR_PROFILE` environment variable, must also be provided or set.

--vpc-cri
:   Log in as a VPC VSI compute resource identity. For more information, see [Logging in as a Virtual Server Instance Compute Resource Identity](/docs/cli?topic=cli-vsi-cri-login).

--profile PROFILE_ID, PROFILE_NAME, or PROFILE_CRN
:   The name, ID, or CRN of the linked trusted IAM profile to be used when obtaining the IAM access token. If provided, the `--cr-token` flag, `IBMCLOUD_CR_TOKEN` environment variable, or `--vpc-cri` flag must also be provided or set. If authenticating as a VPC VSI compute resource, specifying only a trusted profile CRN or ID is supported.

-c ACCOUNT_ID
:   The ID of the target account. This option is exclusive with the `--no account` option.

--no-account
:   Forced login without the account. This option isn't recommended, and it is exclusive with the `-c` option.

--accept
:   Accept an invitation to join the targeted account. The provided account must be a valid account ID.

-g RESOURCE_GROUP<
:   The name or ID of the target resource group. Optional.

-r REGION
:   The name of the target region. For example, `us-south` or `eu-gb`.

--no-region
:   Forced login without targeting a region.

--skip-ssl-validation
:   Bypass the SSL validation of HTTP requests. This option isn't recommended.

--vpc
:   Use a VPC connection for a private API endpoint.

### Examples
{: #login-examples}

**Log in interactively:**

```bash
ibmcloud login
```
{: codeblock}

**Log in to a private endpoint:**

```bash
ibmcloud login -a private.cloud.ibm.com
```
{: codeblock}

Two regions are currently supported: `us-south` and `us-east`.

**Log in with a user name and password, and set a target account:**

```bash
ibmcloud login -u username -p password -c MyAccountID
```
{: codeblock}

**Log in with federated ID, and set a target account:**

```bash
ibmcloud login --sso -c MyAccountID
```
{: codeblock}

**Use an API key with an associated account:**

```bash
ibmcloud login --apikey api-key-string
```
{: codeblock}

```bash
ibmcloud login --apikey @filename
```
{: codeblock}

**Use an API key with no associated account:**

```bash
ibmcloud login --apikey api-key-string -c MyAccountID
```
{: codeblock}

```bash
ibmcloud login --apikey @fileName -c MyAccountID
```
{: codeblock}

If the API key has an associated account, switching to another account isn't supported.
{: note}

**Log in as a specific user with a federated ID:**

```bash
ibmcloud login -u UserID --ssobash
```
{: codeblock}

Then, the CLI provides a URL link and prompts you for the passcode:

```text
Get One Time Code from https://identity-1.us-south.iam.cloud.ibm.com/identity/passcode to proceed.
Open the URL in the default browser? [Y/n] > 
```
{: screen}

Open the link in a browser to get a passcode. Enter the passcode in the console to log in.

**Log in as an IKS Compute Resource linked to a trusted profile:**

```text
ibmcloud login --cr-token token-string --profile trusted_profile_name_id_or_crn
```
{: codeblock}

```text
ibmcloud login --cr-token @filename --profile trusted_profile_name_id_or_crn
```
{: codeblock}

```text
IBMCLOUD_CR_TOKEN=@filename ibmcloud login --profile trusted_profile_name_id_or_crn
```
{: codeblock}

```text
IBMCLOUD_CR_TOKEN=@filename IBMCLOUD_CR_PROFILE=trusted_profile_name_id_or_crn ibmcloud login
```
{: codeblock}

For more information about logging in as an IKS compute resource, see [Logging in with a Compute Resource token](/docs/cli?topic=cli-cri-login).

**Log in as a VPC VSI Compute Resource using the default trusted profile linked during instance provisioning:**

```text
ibmcloud login --vpc-cri
```
{: codeblock}

**Log in as a VPC VSI Compute Resource linked to the specified trusted profile:**

```text
ibmcloud login --vpc-cri --profile trusted_profile_id_or_crn
```
{: codeblock}

```text
IBMCLOUD_CR_PROFILE=trusted_profile_id_or_crn ibmcloud login --vpc-cri
```
{: codeblock}

For more information about logging in as a VPC VSI compute resource, see [Logging in as a Virtual Server Instance Compute Resource Identity](/docs/cli?topic=vpc-cri-login).

**Accept invitation to join a new account:**

```bash
ibmcloud login -c TargetedAccountID --accept
```
{: codeblock}

## ibmcloud logout
{: #ibmcloud_logout}

Log out of the CLI:

```bash
ibmcloud logout
```
{: codeblock}

### Prerequisites
{: #logout-prereqs}

None.

## ibmcloud regions
{: #ibmcloud_regions}

View the information for all regions on {{site.data.keyword.cloud_notm}}:

```bash
ibmcloud regions
```
{: codeblock}

### Prerequisites
{: #regions-prereqs}

Use the `ibmcloud api` command to set an API endpoint.

## ibmcloud target
{: #ibmcloud_target}

Set or view the target account or region:

```bash
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group]
```

### Prerequisites
{: #target-prereqs}

* Use the `ibmcloud api` command to set an API endpoint.
* Use the `ibmcloud login` command to log in. If you are logging in with a federated ID, use the `--sso` option to authenticate with a one time passcode, or use the `--apikey` option to authenticate with an API key.

### Command options
{: #target-options}

-c ACCOUNT_ID
:   The ID of the target account. Optional.

-r REGION
:   The name of the target region, for example, us-south or eu-gb. Optional.

-g RESOURCE_GROUP
:   The name of the target resource group. Optional.

--unset-region
:   Clear the targeted region.

--unset-resource-group
:   Clear the targeted resource group.

If none of the options are specified, the current account and region are displayed.
{: note}

### Examples
{: #target-examples}

Set the current account:

```bash
ibmcloud target -c MyAccountID
```
{: codeblock}

Switch to a new region:

```bash
ibmcloud target -r eu-gb
```
{: codeblock}

View the current account and region:

```bash
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Update the CLI to the most recent version:

```bash
ibmcloud update [-f]
```

### Prerequisites
{: #update-prereqs}

None.

### Command options
{: #update-options}

-f
:   Force an update without confirmation. Root privilege is required.

## General classic infrastructure service commands
{: #classic-service-commands}

Use classic infrastructure commands in the {{site.data.keyword.cloud_notm}} CLI to configure and manage infrastructure services.

Run the `ibmcloud sl` command to see the list of available commands:

```text
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Classic infrastructure Block Storage
   call-api        Call arbitrary API endpoints
   file            Classic infrastructure File Storage
   dns             Classic infrastructure Domain Name System
   globalip        Classic infrastructure Global IP addresses
   hardware        Classic infrastructure hardware servers
   image           Classic infrastructure Compute images
   ipsec           Classic infrastructure IPSEC VPN
   order           Classic infrastructure Orders
   placement-group Classic infrastructure Placement Group
   security        Classic infrastructure SSH Keys and SSL Certificates
   securitygroup   Classic infrastructure network security groups
   subnet          Classic infrastructure Network subnets
   ticket          Classic infrastructure Manage Tickets
   user            Classic infrastructure Manage Users
   vlan            Classic infrastructure Network VLANs
   vs              Classic infrastructure Virtual Servers
   help            Print command usage message
```
{: screen}

To view help information about a command, run the following command:

```bash
ibmcloud sl [command] -h
```

For detailed information about each command, see the related reference topics in this documentation.

The `ibmcloud sl init` command is no longer available as of CLI version `0.14`. To install the most recent CLI version, see [Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

View help information for all commands to operate the classic infrastructure environment:

```bash
ibmcloud sl help
```
{: codeblock}
