---

copyright:
  years: 2018, 2023
lastupdated: "2023-06-01"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Searching and managing the {{site.data.keyword.cloud_notm}} catalog (ibmcloud catalog)
{: #ibmcloud_catalog}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage the {{site.data.keyword.cloud_notm}} catalog entries, query templates, runtimes, and geolocations of data centers.
{: shortdesc}

There are extra CLI commands and capabilities for catalogs. You can use the Catalogs management CLI plug-in to manage your private catalogs and onboard new private software. For more information, see [Catalogs management CLI plug-in](/docs/cli?topic=cli-manage-catalogs-plugin). 
{: note}

{{site.data.keyword.ibmcf_full}} is deprecated with an end-of-support date of 1 June 2023. For more information, see [Deprecation of IBM Cloud Foundry](/docs/cloud-foundry-public?topic=cloud-foundry-public-deprecation).
{: deprecated}
  
## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Get a catalog entry:
```bash
ibmcloud catalog entry ID [--children] [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_options}

--children
:   Get all children for the catalog entry

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_examples}

Get entry with ID `a0ef1-d3b4j0`:
```bash
ibmcloud catalog entry 'a0ef1-d3b4j0'
```
{: codeblock}

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}

Create a catalog entry (catalog admin of an account only):
```bash
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_create_options}

-p, --parent
:   Parent ID of the object

-c
:   Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_create_examples}

Create resource from JSON file with parent ID `a0ef1-d3b4j0`:
```bash
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```
{: codeblock}

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}

Update an existing catalog entry (catalog admin or editor of an account only):
```bash
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_update_options}

-c
:   Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_update_examples}

Update resource `j402-dnf1i` from JSON file:
```bash
ibmcloud catalog entry-update 'j402-dnf1i' -c update
```
{: codeblock}

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}

Delete a catalog entry(catalog admin of an account only)
```bash
ibmcloud catalog entry-delete ID [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_delete_options}

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_delete_examples}

Delete resource `j402-dnf1i`:
```bash
ibmcloud catalog delete `j402-dnf1i`
```
{: codeblock}

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Get the visibility for a catalog entry(catalog admin of an account only)
```bash
ibmcloud catalog entry-visibility ID [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_visibility_options}

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_visibility_examples}

Get visibility of resource `j402-dnf1i` in global scope:
```bash
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```
{: codeblock}

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}

Update the visibility of an existing catalog entry(catalog admin of an account only):
```bash
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_entry_visibility_set_options}

--includes-add
:   Adding an account (or list of comma-separated accounts) to the includes list, granting visibility to the entry. Email or Account GUIDs are acceptable.

--includes-remove
:   Removing an account (or list of comma-separated accounts) from the includes list, revoking visibility to the entry. Email or Account GUIDs are acceptable.
  
--excludes-add
:   Adding an account (or list of comma-separated accounts) to the excludes list. Email or Account GUIDs are acceptable.

--excludes-remove
:   Removing an account (or list of comma-separated accounts) from the excludes list, revoking visibility to the entry. If the account was set by global admins, the account admins can't remove the account. Email or Account GUIDs are acceptable.

--owner
:   Changing the owner of an object. Email or Account GUIDs are acceptable.

--restrict
:   Changing the restriction of the visibility object to 'Private'.

--unrestrict
:   Changing the restriction of the visibility object to 'Public'.
  
-c
:   Valid JSON object that contains catalog-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see documentation for the particular catalog entry.

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_entry_visibility_set_examples}

Set visibility of resource `j402-dnf1i` from JSON file:
```bash
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```
{: codeblock}

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}

List service offerings in the marketplace:
```bash
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_service_marketplace_options}

--cf
:   Show Cloud Foundry services only

--rc
:   Show RC compatible services only

--global
:   Operate in global scope

### Examples
{: #ibmcloud_catalog_service_marketplace_examples}

Show service offerings in global scope:
```bash
ibmcloud catalog service-marketplace --global
```
{: codeblock}

## ibmcloud catalog service
{: #ibmcloud_catalog_service}

View details of a service in the catalog, including a description, tags, compatibility information, and available plans. 

```bash
ibmcloud catalog service NAME_OR_ID [--global]
```

### Command options
{: #ibmcloud_catalog_service_options}

--global
:   Operate in a global scope

### Examples
{: #ibmcloud_catalog_service_examples}

Show details of the `container-kubernetes` service:
```bash
ibmcloud catalog service container-kubernetes
```
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

View the boilerplate templates on {{site.data.keyword.cloud_notm}}.
```bash
ibmcloud catalog templates [-d]
```

### Command options
{: #ibmcloud_catalog_templates_options}

 -d (optional)
 :   If the *-d* option is specified, the description of each template is also displayed. Otherwise, only the ID and name of each template is shown.
 

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

View the detailed information of a specified boilerplate template.
```bash
ibmcloud catalog template TEMPLATE_ID
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_template_options}

 TEMPLATE_ID (required)
 :   The ID of the boilerplate template. Use *ibmcloud templates* to view all templates' IDs.

### Examples
{: #ibmcloud_catalog_template_examples}

View details of the template `mobileBackendStarter`:
```bash
ibmcloud catalog template mobileBackendStarter
```
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Create a cf application that is based on the specified template with the specified URL and description. By default, the new app is started automatically.

```bash
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_template_run_options}

 TEMPLATE_ID (required)
 :   The template that the application is based on during creation. Use *ibmcloud templates* to see all templates' ID.
 
 CF_APP_NAME (required)
 :   The name of the cf application to be created.
 
 -n*HOSTNAME*
 :   The host name of the CF application. If not specified, the route is set by {{site.data.keyword.cloud_notm}} automatically based on your app name and default domain.
 
 -d*DOMAINNAME*
 :   The domain of the CF application. If not specified, the route is set by {{site.data.keyword.cloud_notm}} automatically based on your app name and default domain.
 
 --desc *DESCRIPTION* (optional)
 :   Description of the application.
 
 --no-start (optional)
 :   Don't start the application automatically after creation. If not specified, the application is started automatically after creation.

### Examples
{: #ibmcloud_catalog_template_run_examples}

Create a `cf` app that is named `my-app` based on a `javaHelloWorld` template:
```bash
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

Create an app `my-ruby-app` based on `rubyHelloWorld` template with a description:
```bash
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

Create an app `my-python-app` based on `pythonHelloWorld` template without automatic start:
```bash
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Get a choice subset of regions in your choice of format.
```bash
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--global] [--csv]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_locations_options}

-i, --id
:   Specify geography by id.

-k, --kind
:   Get a list of entries for the specified kind.

--col
:   Specify more columns for the table. Currently, "group", "provider", and "tags".

--global
:   Operate in a global scope.

--csv
:   Output CSV file

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

View the details of a runtime. This command is only available for public cloud.
```bash
ibmcloud catalog runtime RUNTIME_ID
```
{: codeblock}

### Examples
{: #ibmcloud_catalog_locations_examples}

Show details of runtime "nodejsHelloWorld":
```bash
ibmcloud catalog runtime nodejsHelloWorld
```
{: codeblock}

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

List all runtimes. This command is only available for public cloud.
```bash
ibmcloud catalog runtimes [-d]
```
{: codeblock}

### Command options
{: #ibmcloud_catalog_runtimes_options}

-d
:   Show the description of each runtime

### Examples
{: #ibmcloud_catalog_runtimes_examples}

List all runtimes along with their descriptions:
```bash
ibmcloud catalog runtimes -d
```
{: codeblock}
