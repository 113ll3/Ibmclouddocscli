---

copyright:
  years: 2018, 2020
lastupdated: "2020-04-15"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Searching and managing the {{site.data.keyword.cloud_notm}} catalog (ibmcloud catalog)
{: #ibmcloud_catalog}

Use the following commands to manage the {{site.data.keyword.cloud}} catalog entries, query templates, runtimes, and geolocations of data centers.
{: shortdesc}

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Get a catalog entry:
```
ibmcloud catalog entry ID [--children] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--children</dt>
  <dd>Get all children for the catalog entry</dd>
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

Create a catalog entry (catalog admin of an account only):
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>Parent ID of the object</dd>
  <dt>-c</dt>
  <dd>Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
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

Update an existing catalog entry (catalog admin or editor of an account only):
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>-c</dt>
  <dd>Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
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
ibmcloud catalog delete `j402-dnf1i`
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
  <dt>--global</dt>
  <dd>Operate in global scope</dd>
</dl>

<strong>Examples</strong>:

Get visibility of resource `j402-dnf1i` in global scope:
```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}

Update the visibility of an existing catalog entry(catalog admin of an account only):
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Adding an account (or list of comma-separated accounts) to the includes list, granting visibility to the entry. Email or Account GUIDs are acceptable.</dd>
  <dt>--includes-remove</dt>
  <dd>Removing an account (or list of comma-separated accounts) from the includes list, revoking visibility to the entry. Email or Account GUIDs are acceptable.</dd>  
  <dt>--excludes-add</dt>
  <dd>Adding an account (or list of comma-separated accounts) to the excludes list. Email or Account GUIDs are acceptable.</dd>
  <dt>--excludes-remove</dt>
  <dd>Removing an account (or list of comma-separated accounts) from the excludes list, revoking visibility to the entry. If the account was set by global admins, the account admins can't remove the account. Email or Account GUIDs are acceptable.</dd>
  <dt>--owner</dt>
  <dd>Changing the owner of an object. Email or Account GUIDs are acceptable.</dd>
  <dt>--restrict</dt>
  <dd>Changing the restriction of the visibility object to 'Private'.</dd>
  <dt>--unrestrict</dt>
  <dd>Changing the restriction of the visibility object to 'Public'.</dd>  
  <dt>-c</dt>
  <dd>Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.</dd>
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

List service offerings in the marketplace:
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
{: codeblock}

## ibmcloud catalog service
{: #ibmcloud_catalog_service}

View details of a service in the catalog, including a description, tags, compatibility information, and available plans. 

```
ibmcloud catalog service NAME_OR_ID [--global]
```

<strong>Command options</strong>:

<dl>
  <dt>--global</dt>
  <dd>Operate in a global scope</dd>
</dl>

<strong>Examples</strong>:

Show details of the `container-kubernetes` service:
```
ibmcloud catalog service container-kubernetes
```
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

View the boilerplate templates on {{site.data.keyword.cloud_notm}}.
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
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Create a cf application that is based on the specified template with the specified URL and description. By default, the new app is started automatically.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>TEMPLATE_ID (required)</dt>
   <dd>The template that the application is based on during creation. Use <i>ibmcloud templates</i> to see all templates' ID.</dd>
   <dt>CF_APP_NAME (required)</dt>
   <dd>The name of the cf application to be created.</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>The host name of the CF application. If not specified, the route is set by {{site.data.keyword.cloud_notm}} automatically based on your app name and default domain.</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>The domain of the CF application. If not specified, the route is set by {{site.data.keyword.cloud_notm}} automatically based on your app name and default domain.</dd>
   <dt>--desc <i>DESCRIPTION</i> (optional)</dt>
   <dd>Description of the application.</dd>
   <dt>--no-start (optional)</dt>
   <dd>Don't start the application automatically after creation. If not specified, the application is started automatically after creation.</dd>
   </dl>


<strong>Examples</strong>:

Create a `cf` app that is named `my-app` based on a `javaHelloWorld` template:
```
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

Create an app `my-ruby-app` based on `rubyHelloWorld` template with a description:
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

Create an app `my-python-app` based on `pythonHelloWorld` template without automatic start:
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Get a choice subset of regions in your choice of format.
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--global] [--csv]
```

<strong>Command options</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Specify geography by id.</dd>
  <dt>-k, --kind</dt>
  <dd>Get a list of entries for the specified kind.</dd>
  <dt>--col</dt>
  <dd>Specify more columns for the table. Currently, "group", "provider", and "tags".</dd>
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
ibmcloud catalog runtime nodejsHelloWorld
```
{: codeblock}

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
{: codeblock}


