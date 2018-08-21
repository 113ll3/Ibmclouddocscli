---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing Catalog, Plug-ins, and Billing Settings
{: #ibmcloud_commands_settings}

<table summary="ibmcloud commands that you can use to manage the {{site.data.keyword.Bluemix_notm}} catalog, plug-ins, billing, and security settings.">
<caption>Table 1. Commands for managing the {{site.data.keyword.Bluemix_notm}} catalog, plug-ins, billing, and security settings</caption>
 <thead>
 <th colspan="5">Commands for managing {{site.data.keyword.Bluemix_notm}} catalog, plug-ins, billing, and security settings</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Search catalog entries

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Specify the geographic region to search within. Currently only "us-south" and "united-kingdom" are supported</dd>
  <dt>-k, --kind</dt>
  <dd>Filter by kind of resources. Currently only "service-cf", "iaas", "runtime", "template", and "dashboard" are supported</dd>
  <dt>-p, --price</dt>
  <dd>Filter by price. Currently only "free", "paygo", "bluemix-subscription" are supported</dd>
  <dt>-t, --tag</dt>
  <dd>Filter by tag.</dd>
  <dt>--sort-by</dt>
  <dd>Property to sort by</dd>
  <dt>--col</dt>
  <dd>Specify additional columns for the table. Currently "group", "provider", and "tags"</dd>
  <dt>--reverse</dt>
  <dd>Whether to reverse the sorting order</dd>
  <dt>--json</dt>
  <dd>Output original JSON response</dd>
  <dt>--csv</dt>
  <dd>Output CSV file</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Search service `Automation test`:

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Get a catalog entry

```
ibmcloud catalog entry ID [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--children</dt>
  <dd>Get all children for the catalog entry</dd>
  <dt>--json</dt>
  <dd>Output original JSON response</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Get entry with ID `a0ef1-d3b4j0`:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Create a new catalog entry(catalog admin of an account only)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>Parent ID of the object</dd>
  <dt>-c</dt>
  <dd>Valid JSON object containing catalog-specific configuration parameters, provided either in-line or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Create resource from JSON file with parent ID `a0ef1-d3b4j0`:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Update an existing catalog entry(catalog admin or editor of an account only)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-c</dt>
  <dd>Valid JSON object containing catalog-specific configuration parameters, provided either in-line or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Update resource `j402-dnf1i` from JSON file:

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Delete a catalog entry(catalog admin of an account only)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Delete resource `j402-dnf1i`:

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Get the visibility for a catalog entry(catalog admin of an account only)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-json</dt>
  <dd>Output original JSON response</dd>
  <dt>-global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Get visibility of resource `j402-dnf1i` in global scope:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Update the visibility of an existing catalog entry(catalog admin of an account only)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Adding an account (or list of comma separated accounts) to the includes list, granting visibility to the entry. Email or Account GUIDs are acceptable</dd>
  <dt>--includes-remove</dt>
  <dd>Removing an account (or list of comma separated accounts) from the includes list, revoking visibility to the entry. Email or Account GUIDs are acceptable</dd>  
  <dt>--excludes-add</dt>
  <dd>Adding an account (or list of comma separated accounts) to the excludes list. Email or Account GUIDs are acceptable</dd>
  <dt>--excludes-remove</dt>
  <dd>Removing an account (or list of comma separated accounts) from the excludes list, revoking visibility to the entry. If the account was set by global admins, the account admins cannot remove the account.Email or Account GUIDs are acceptable</dd>
  <dt>--owner</dt>
  <dd>Changing the owner of an object. Email or Account GUIDs are acceptable.</dd>
  <dt>--restrict</dt>
  <dd>Changing the restriction of the visibility object to 'Private'</dd>
  <dt>--unrestrict</dt>
  <dd>Changing the restriction of the visibility object to 'Public'</dd>  
  <dt>-c</dt>
  <dd>Valid JSON object containing catalog-specific configuration parameters, provided either in-line or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Set visibility of resource `j402-dnf1i` from JSON file:

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
List service offerings in the marketplace

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Show Cloud Foundry services only</dd>
  <dt>--rc</dt>
  <dd>Show RC compatible services only</dd>
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Show service offerings in global scope:

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

View the boilerplate templates on {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

   <dl>
   <dt>-d (optional)</dt>
   <dd>If the <i>-d</i> option is specified, the description of each template is also displayed. Otherwise, only the ID and name of each template is shown.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

View the detailed information of a specified boilerplate template.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>TEMPLATE_ID (required)</dt>
   <dd>The ID of the boilerplate template. Use <i>ibmcloud templates</i> to view all templates' IDs.</dd>
   </dl>


<strong>Examples</strong>:

View details of the template `mobileBackendStarter`:

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Create a cf application that is based on the specified template with the specified URL and description. By default, the new app is started automatically.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>TEMPLATE_ID (required)</dt>
   <dd>The template that the application will be based on when it is created. Use <i>ibmcloud templates</i> to see all templates' ID.</dd>
   <dt>CF_APP_NAME (required)</dt>
   <dd>The name of the cf application to be created.</dd>
   <dt>-u <i>URL</i> (optional)</dt>
   <dd>The route of the application. If not specified, the route is set by {{site.data.keyword.Bluemix_notm}} automatically based on your app name and default domain.</dd>
   <dt>-d <i>DESCRIPTION</i> (optional)</dt>
   <dd>Description of the application.</dd>
   <dt>--no-start (optional)</dt>
   <dd>Do not start the application automatically after it is created. If not specified, the application is started automatically after it is created.</dd>
   </dl>


<strong>Examples</strong>:

Create a cf application `my-app` based on `javaHelloWorld` template:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Create an application `my-ruby-app` based on `rubyHelloWorld` template with route `myrubyapp.chinabluemix.net` and description `My first ruby app on {{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Create an application `my-python-app` based on `pythonHelloWorld` template without automatic start:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Get a choice subset of regions in your choice of format.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Command options</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Specify geography by id.</dd>
  <dt>-k, --kind</dt>
  <dd>Get a list of entries for the specified kind.</dd>
  <dt>--col</dt>
  <dd>Specify additional columns for the table. Currently "group", "provider", and "tags".</dd>
  <dt>--json</dt>
  <dd>Output of the original JSON response.</dd>
  <dt>--global</dt>
  <dd>Operate in a global scope.</dd>
  <dt>--csv</dt>
  <dd>Output CSV file</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

View the details of a runtime. This command is only available for public cloud.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Examples</strong>:

Show details of runtime "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

List all runtimes. This command is only available for public cloud.

```
ibmcloud catalog runtimes [-d]
```

<strong>Command options</strong>:

<dl>
  <dt>-d</dt>
  <dd>Show the description of each runtime</dd>
</dl>

<strong>Examples</strong>:

List all runtimes along with their descriptions:

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Show monthly usage of the current account (account admin only)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--json (optional)</dt>
  <dd>Display the usage result in JSON format.</dd>
</dl>

<strong>Examples</strong>:

Show current account's usage and cost report in 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Show monthly usage for an org (account admin or org billing manger only)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>ORG_NAME (required)</dt>
  <dd>Name of the org.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--json (optional)</dt>
  <dd>Display the usage result in JSON format.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Show monthly usage for a resource group (account admin or resource group admin only)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>GROUP_NAME (required)</dt>
  <dd>Name of the resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--json (optional)</dt>
  <dd>Display the usage result in JSON format.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Show monthly resource instances usage under the current account.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-o ORG_NAME (optional)</dt>
  <dd>Filter instances by organization.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filter instance by resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--json (optional)</dt>
  <dd>Display the usage result in JSON format.</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

List all plug-in repositories that are registered in {{site.data.keyword.Bluemix_notm}} CLI.

```
ibmcloud plugin repos
```

<strong>Prerequisites</strong>:  None

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Add a new plug-in repository to {{site.data.keyword.Bluemix_notm}} CLI.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:

   <dl>
   <dt>REPO_NAME (required)</dt>
   <dd>The name of the repository to be added. You can define your own name for each repository.</dd>
   <dt>REPO_URL (required)</dt>
   <dd>The URL of the repository to be added. The repository URL must contain the protocol (for example, http://plugins.ng.bluemix.net instead of plugins.ng.bluemix.net). http://plugins.ng.bluemix.net is the official plug-in repository of {{site.data.keyword.Bluemix_notm}} CLI.</dd>
    </dl>


<strong>Examples</strong>:

Add the official plug-in repository of {{site.data.keyword.Bluemix_notm}} CLI as `bluemix-repo`:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Remove a plug-in repository from {{site.data.keyword.Bluemix_notm}} CLI.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:
   <dl>
   <dt>REPO_NAME (required)</dt>
   <dd>The name of the repository to be removed.</dd>
   </dl>

<strong>Examples</strong>:

Remove `bluemix-repo` repository from {{site.data.keyword.Bluemix_notm}} CLI:

```
ibmcloud plugin repo-remove bluemix-repo
```

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

List all available plug-ins in all added repositories or a specific repository.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>List only the plugins in specified repository.</dd>
   </dl>

<strong>Examples</strong>:

List all plugins in all added repositories:

```
ibmcloud plugin repo-plugins
```

List all plug-ins in the `bluemix-repo` repository:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Show the details of a plug-in in the repository.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>The name of the repository. If no repository is specified, the command uses the default plug-in repository.å</dd>
   </dl>

<strong>Examples</strong>:

List details of plug-in "IBM-Containers" in repository "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

List details of plug-in "IBM-Containers" in default repository

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

List all installed plug-ins in {{site.data.keyword.Bluemix_notm}} CLI.

```
ibmcloud plugin list
```

<strong>Prerequisites</strong>:  None

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Show details of an installed plug-in.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Prerequisites</strong>:  None

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Install the specific version of plug-in to {{site.data.keyword.Bluemix_notm}} CLI from the specified path or repository.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

If no repository is specified, the command uses the default plug-in repository 'Bluemix'.
If no version is specified, the command selects the latest available version to install.

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (required)</dt>
   <dd>If -r <i>REPO_NAME</i> is not specified, plug-in is installed from the specified local path or remote URL.</dd>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>The name of the repository where the plug-in binary is located. If no repository is specified, the command uses the default plug-in repository 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (optional)</dt>
   <dd>The version of the plug-in to be installed. If not provided, the latest version of the plug-in is installed. This option is valid only when you install the plug-in from the repository.</dd>
   <dt>-f </dt>
   <dd>Force install of plug-in without confirmation.</dd>
    </dl>


The {{site.data.keyword.Bluemix_notm}} CLI has the official repository name of `Bluemix`.

<strong>Examples</strong>:

Install a plug-in from the local file:

```
ibmcloud plugin install /downloads/new_plugin
```

Install a plug-in from the remote URL:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Install the 'container-service' plug-in of the latest version from the 'Bluemix' repository:

```
ibmcloud plugin install container-service -r Bluemix
```

or simply:

```
ibmcloud plugin install container-service
```

Install the 'container-service' plug-in with the  version '0.1.425' from the official plugin repository:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Upgrade the plug-in from a repository.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

If no repository is specified, the command uses the default plug-in repository 'Bluemix'.
If no version is specified, the command selects the latest available version to install.

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Name of the plug-in to update. If not specified, the command checks upgrades for all plug-ins installed.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>The name of the repository where the plug-in binary is located. If not specified, the command uses the default plug-in repository 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (optional)</dt>
 <dd>The version of the plug-in to be updated to. If not provided, update the plug-in to the the latest available version.</dd>
 <dt>--all</dt>
 <dd>Update all available plug-ins</dd>
</dl>

<strong>Examples</strong>:

check for all available upgrade in the official plug-in repository 'Bluemix':

```
ibmcloud plugin update -r Bluemix
```

or simply:

```
ibmcloud plugin update
```

Upgrade plug-in 'container-service' in the official plug-in repository to the latest:

```
ibmcloud plugin update container-service
```

Update plug-in 'container-service' in the official plug-in repository to version '0.1.440':

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Uninstall the specified plug-in from {{site.data.keyword.Bluemix_notm}} CLI.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Prerequisites</strong>:  None

<strong>Command options</strong>:

   <dl>
   <dt>PLUGIN_NAME (required)</dt>
   <dd>The name of the plug-in to be uninstalled.</dd>
    </dl>

<strong>Examples</strong>:

Uninstall the 'container-service' plug-in that was previously installed:

```
ibmcloud plugin uninstall container-service
```
