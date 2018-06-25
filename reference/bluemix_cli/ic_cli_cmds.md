---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# General CLI (ibmcloud) commands
{: #ibmcloud_cli}

Version: 0.7.1

The {{site.data.keyword.Bluemix_notm}} command line interface (CLI) provides a set of commands that are grouped by namespace for users to interact with {{site.data.keyword.Bluemix_notm}}.

Starting from version 0.5.0, {{site.data.keyword.Bluemix_notm}} command line client bundles a Cloud Foundry command line client in its installation. If you have your own cf cli installed, do not use both {{site.data.keyword.Bluemix_notm}} CLI commands `ibmcloud [command]` and Cloud Foundry CLI commands `cf [command]` of your own installation in the same context. Instead, use `ibmcloud cf [command]` if you want to use cf cli to manage Cloud Foundry resources in {{site.data.keyword.Bluemix_notm}} CLI context.  Note that `ibmcloud cf api/login/logout/target` is not allowed, and you must use `ibmcloud api/login/logout/target` instead.

As of May 2018 the {{site.data.keyword.Bluemix_notm}} CLI commands have changed from `bluemix` and `bx` to `ibmcloud`. However you can still use the `bluemix` and `bx` CLI commands until they are removed at a later date.
{: tip}

The following lists detailed commands that are supported by {{site.data.keyword.Bluemix_notm}} CLI, including their names, arguments, options, prerequisites, descriptions, and examples.
{:shortdesc}

**Note:** *Prerequisites* list which actions are required before using the command. Commands that have no prerequisite actions list **None**. Otherwise, prerequisites might include one or more of the following actions:

<dl>
<dt>Endpoint</dt>
<dd>An API endpoint must be set through the <code>bluemix api</code> before using the command.</dd>
<dt>Login</dt>
<dd>Login by using the <code>bluemix login</code> command is required before using this command.
If logging in with federated ID, use '--sso' option to authenticate with one time passcode, or use '--apikey' to authenticate with API key. Go to {{site.data.keyword.Bluemix_notm}} console **Manage** &gt; **Security** &gt; **Platform API keys** to create API keys.
</dd>
<dt>Target</dt>
<dd>The <code>bluemix target</code> command must be used to set an org and space before using this command.</dd>
<dt>Docker</dt>
<dd>The Docker CLI (docker) must be installed to run this command.</dd>
</dl>


Use the indexes in the following table to refer to the frequently used ibmcloud commands.

## General ibmcloud commands
{: #ibmcloud_commands_index}

<table summary="General ibmcloud commands.">
<caption>Table 1. General ibmcloud commands</caption>
 <thead>
 <th colspan="5">General ibmcloud commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](ic_cli_cmds.html#ibmcloud_help)</td>
 <td>[ibmcloud api](ic_cli_cmds.html#ibmcloud_api)</td>
 <td>[ibmcloud config](ic_cli_cmds.html#ibmcloud_config)</td>
 <td>[ibmcloud info](ic_cli_cmds.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](ic_cli_cmds.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](ic_cli_cmds.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](ic_cli_cmds.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](ic_cli_cmds.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](ic_cli_cmds.html#ibmcloud_target)</td>
 <td>[ibmcloud update](ic_cli_cmds.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>
 
 ## ibmcloud help
{: #ibmcloud_help}
Display the general help for first-level built-in commands and supported namespaces of {{site.data.keyword.Bluemix_notm}} CLI, or the help for a specific built-in command or namespace.

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

Display general help for {{site.data.keyword.Bluemix_notm}} CLI:

```
ibmcloud help
```

Display help for the `info` command:

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
Set or view the {{site.data.keyword.Bluemix_notm}} API endpoint.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Prerequisites</strong>: None

<strong>Command options</strong>:
   <dl>
   <dt>API_ENDPOINT (optional)</dt>
   <dd>The API endpoint that is targeted, for example, `https://api.chinabluemix.net`. If both *API_ENDPOINT* and `--unset` options are not specified, the current API endpoint is displayed.</dd>
   <dt>--unset (optional)</dt>
   <dd>Remove the API endpoint setting.</dd>
   <dt>--skip-ssl-validation (optional)</dt>
   <dd>Bypass SSL validation of HTTP requests.</dd>
   </dl>
<strong>Examples</strong>:

Set the API endpoint to api.chinabluemix.net:

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

View the current API endpoint:

```
ibmcloud api
```

Unset the API endpoint:

```
ibmcloud api --unset
```

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

Enable trace output for HTTP requests:

```
ibmcloud config --trace true
```

Trace HTTP requests to a specified file */home/usera/my_trace*:

```
ibmcloud config --trace /home/usera/my_trace
```

Disable color output:

```
ibmcloud config --color false
```

Set the locale to zh_Hans:

```
ibmcloud config --locale zh_Hans
```

Clear the locale settings:

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

View the basic {{site.data.keyword.Bluemix_notm}} information, including the current region, the cloud controller version, and some useful endpoints, such as endpoints for login and exchanging access token.

```
ibmcloud info
```

<strong>Prerequisites</strong>:  Endpoint

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

## ibmcloud login
{: #ibmcloud_login}

Log in user.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>Prerequisites</strong>:  None

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Command options</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (optional)</dt>
  <dd> API endpoint (For example: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY or @API_KEY_FILE_PATH</i>
  <dd> API key content or the path of an API key file indicated by @</dd>
  <dt> --sso (optional) </dt>
  <dd> Use a one-time passcode to login </dd>
  <dt> -u <i>USERNAME</i> (optional)</dt>
  <dd> Username</dd>
  <dt> -p <i>PASSWORD</i> (optional)</dt>
  <dd> Password</dd>
  <dt> -c <i>ACCOUNT_ID</i> (optional) </dt>
  <dd> ID of the target account</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional) </dt>
  <dd> Name of the target resource group</dd>
  <dt> -o <i>ORG</i> (optional)</dt>
  <dd> Name of the target organization (deprecated, use 'ibmcloud target -o ORG')</dd>
  <dt> -s <i>SPACE</i> (optional) </dt>
  <dd> Name of the target space (deprecated, use 'ibmcloud target -s SPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Force authentication with login server instead of public IAM</dd>
  <dt> --skip-ssl-validation (optional) </dt>
  <dd> Bypass SSL validation of HTTP requests. This option is not recommended.</dd>
</dl>

<strong>Examples</strong>:

#### Interactive login

```
ibmcloud login
```

Log in with user name and password, and set target account, org and space:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Log in with one time passcode and set target account, org and space

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Log in with API key and set targets:

#### API key has account associated

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API key has no account associated

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Note:</strong> If the API Key has an associated account, switching to another account is not allowed.

#### Use one time passcode

```
ibmcloud login -u UserID --sso
```

Then the CLI will provide a URL link and ask for passcode:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Open the link in browser, which will guide you to get the passcode. Type in the given passcode in console, and you should be able to login.

## ibmcloud logout
{: #ibmcloud_logout}

Log out user.

```
ibmcloud logout
```

<strong>Prerequisites</strong>:  None

## ibmcloud regions
{: #ibmcloud_regions}

View the information for all regions on {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Prerequisites</strong>:  Endpoint

## ibmcloud target
{: #ibmcloud_target}


Set or view the target account, region, organization or space.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (optional)</dt>
   <dd>Name of the region to be switched to, such as 'us-south' or 'eu-gb'.</dd>
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
If none of the options are specified, the current account, region, org and space are displayed.

<strong>Examples</strong>:

Set the current account, organization and space:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Switch to a new region:

```
ibmcloud target -r eu-gb
```

View the current account, region, org and space:

```
ibmcloud target
```

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
