---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# General CLI (ibmcloud) commands
{: #ibmcloud_cli}

The {{site.data.keyword.cloud_notm}} command line interface (CLI) provides a set of commands that are grouped by namespace for users to interact with {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} command line client bundles a Cloud Foundry command line client in its installation. If you have your own cf cli installed, don't use both {{site.data.keyword.cloud_notm}} CLI commands `ibmcloud [command]` and Cloud Foundry CLI commands `cf [command]` of your own installation in the same context. Instead, use `ibmcloud cf [command]` if you want to use cf cli to manage Cloud Foundry resources in {{site.data.keyword.cloud_notm}} CLI context. Note that `ibmcloud cf api/login/logout/target` isn't allowed, and you must use `ibmcloud api/login/logout/target` instead.

As of May 2018 the {{site.data.keyword.cloud_notm}} CLI commands have changed from `bluemix` and `bx` to `ibmcloud`. However, you can still use the `bluemix` and `bx` CLI commands until they're removed later.
{: tip}

The following lists detailed commands that are supported by {{site.data.keyword.cloud_notm}} CLI, including their names, arguments, options, prerequisites, descriptions, and examples.
{: shortdesc}

*Prerequisites* list which actions are required before using the command. Commands that have no prerequisite actions list **None**. Otherwise, prerequisites might include one or more of the following actions:

<dl>
<dt>Endpoint</dt>
<dd>An API endpoint must be set through the <code>ibmcloud api</code> before using the command.</dd>
<dt>Login</dt>
<dd>Log in by using the <code>ibmcloud login</code> command is required before using this command.
If logging in with federated ID, use '--sso' option to authenticate with one time passcode, or use '--apikey' to authenticate with API key.
</dd>
<dt>Target</dt>
<dd>The <code>ibmcloud target</code> command must be used to set an org and space before using this command.</dd>
<dt>Docker</dt>
<dd>The Docker CLI (docker) must be installed to run this command.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Display the general help for first-level built-in commands and supported namespaces of {{site.data.keyword.cloud_notm}} CLI, or the help for a specific built-in command or namespace.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>Prerequisites</strong>: None

<strong>Command options</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (optional)</dt>
   <dd>The command or namespace that help is displayed for. If not specified, the general help for {{site.data.keyword.Bluemix_notm}} CLI is shown.</dd>
   </dl>

<strong>Examples</strong>:

Display general help for {{site.data.keyword.cloud_notm}} CLI:
```
ibmcloud help
```
{: codeblock}

Display help for the `info` command:
```
ibmcloud help info
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Set or view the {{site.data.keyword.cloud_notm}} API endpoint.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Prerequisites</strong>: None

<strong>Command options</strong>:
   <dl>
   <dt>API_ENDPOINT (optional)</dt>
   <dd>The API endpoint that is targeted, for example, `https://cloud.ibm.com`. If both *API_ENDPOINT* and `--unset` options aren't specified, the current API endpoint is displayed.</dd>
   <dt>--unset (optional)</dt>
   <dd>Remove the API endpoint setting.</dd>
   <dt>--skip-ssl-validation (optional)</dt>
   <dd>Bypass SSL validation of HTTP requests.</dd>
   </dl>
<strong>Examples</strong>:

Set the API endpoint to cloud.ibm.com:
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

View the current API endpoint:
```
ibmcloud api
```
{: codeblock}

Unset the API endpoint:
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Write default values to the configuration file.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>The timeout value for HTTP requests. The default value is 60 seconds.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Trace HTTP requests to the terminal or specified file.</dd>
   <dt>--color true|false</dt>
   <dd>Enable or disable color output. Color output is enabled by default.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Set a default locale. If LOCALE is <i>CLEAR</i>, the previous locale is deleted.</dd>
   <dt>--check-version true|false</dt>
   <dd>Enable or disable CLI version check.</dd>
   </dl>

Only one of these options can be specified at a time.

<strong>Examples</strong>:

Set HTTP request timeout to 30 seconds:
```
ibmcloud config --http-timeout 30
```
{: codeblock}

Enable trace output for HTTP requests:
```
ibmcloud config --trace true
```
{: codeblock}

Trace HTTP requests to a specified file */home/usera/my_trace*:
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Disable color output:
```
ibmcloud config --color false
```
{: codeblock}

Set the locale to zh_Hans:
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

Clear the locale settings:
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

The `ibmcloud info` command is no longer available as of CLI version `0.14`. To install the latest CLI version, see [Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

Invoke embedded CF CLI
```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Turn off message "Invoking cf command..."</dd>
</dl>

<strong>Examples</strong>:

List cf apps:

```
ibmcloud cf apps
```

List cf services without message "Invoking cf command...":
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Log in user.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>Prerequisites</strong>:  None

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Command options</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (optional)</dt>
  <dd> API endpoint (For example: cloud.ibm.com)</dd>
  <dt> --apikey <i>API_KEY or @API_KEY_FILE_PATH</i>
  <dd> API key content or the path of an API key file that is indicated by @</dd>
  <dt> --sso (optional) </dt>
  <dd> Use a one-time passcode to log in </dd>
  <dt> -u <i>USERNAME</i> (optional)</dt>
  <dd> Username</dd>
  <dt> -p <i>PASSWORD</i> (optional)</dt>
  <dd> Password</dd>
  <dt> -c <i>ACCOUNT_ID</i> (optional) </dt>
  <dd> ID of the target account. This option is exclusive with --no-account</dd>
  <dt> --no-account (optional) </dt>
  <dd> Force log in without account. This option isn't recommended. This option is exclusive with -c.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional) </dt>
  <dd> Name of the target resource group</dd>
  <dt> -r REGION</dt>
  <dd> Name of region, such as 'us-south' or 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> Force log in without targeting a region.</dd>
  <dt> -o <i>ORG</i> (optional)</dt>
  <dd> Name of the target organization (deprecated, use 'ibmcloud target -o ORG')</dd>
  <dt> -s <i>SPACE</i> (optional) </dt>
  <dd> Name of the target space (deprecated, use 'ibmcloud target -s SPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Force authentication with login server instead of public IAM</dd>
  <dt> --skip-ssl-validation (optional) </dt>
  <dd> Bypass SSL validation of HTTP requests. This option isn't recommended.</dd>
</dl>

<strong>Examples</strong>:

### Interactive login

```
ibmcloud login
```
{: codeblock}

Log in with user name and password, and set target account, org, and space:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Log in with one time passcode and set target account, org, and space
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### API key has account that is associated

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### API key has no account that is associated

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Note:</strong> If the API Key has an associated account, switching to another account isn't allowed.

### Use one time passcode
```
ibmcloud login -u UserID --sso
```
{: codeblock}

Then, the CLI provides a URL link and ask for passcode:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Open the link in browser, to get a passcode. Type in the given passcode in console, and you can log in.

## ibmcloud logout
{: #ibmcloud_logout}

Log out user.
```
ibmcloud logout
```
{: codeblock}

<strong>Prerequisites</strong>:  None

## ibmcloud regions
{: #ibmcloud_regions}

View the information for all regions on {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud regions
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint

## ibmcloud target
{: #ibmcloud_target}


Set or view the target account, region, organization, or space.
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (optional)</dt>
   <dd>Name of the region to be switched to, such as 'us-south' or 'eu-gb'.</dd>
   <dt>--unset-region</dt>
   <dd>Unset targeted region</dd>
   <dt>-c <i>ACCOUNT_ID</i> (optional)</dt>
   <dd>The ID of the account to be targeted.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (optional)</dt>
   <dd>Name of resource group</dd>
   <dt>--cf</dt>
   <dd>Interactively select the target organization and space</dd>
   <dt>-o <i>ORG_NAME</i> (optional)</dt>
   <dd>The name of the organization to be targeted.</dd>
   <dt>-s <i>SPACE_NAME</i> (optional)</dt>
   <dd>The name of the space to be targeted.</dd>
   </dl>
If none of the options are specified, the current account, region, org, and space are displayed.

<strong>Examples</strong>:

Set the current account, organization, and space:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Switch to a new region:
```
ibmcloud target -r eu-gb
```
{: codeblock}

View the current account, region, org, and space:
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Update the CLI to the latest version.
```
ibmcloud update [-f]
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:
<dl>
  <dt>-f</dt>
  <dd>Force update without confirmation. Root privilege is required.</dd>
</dl>


## General classic infrastructure service commands
{: #softlayer_cli}

Use classic infrastructure commands in the {{site.data.keyword.cloud_notm}} command line interface (CLI) to configure and manage Infrastructure services.

Run the `ibmcloud sl` command to see the list of available commands:
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

To view help information about a command, run:
```
ibmcloud sl [command] -h
```

The `ibmcloud sl init` command is no longer available as of CLI version `0.14`. To install the latest CLI version, see [Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

View help information for all commands to operate the classic infrastructure environment.
```
ibmcloud sl help
```
{: codeblock}

