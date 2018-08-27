---

copyright:

  years: 2018


lastupdated: "2018-08-20"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing Resource Groups and Resources
{: #ibmcloud_commands_resource}

<table summary="ibmcloud command that you can use to manage resource groups and resources.">
  <thead>
    <th colspan="5">Use the following commands to manage {site.data.keyword.Bluemix_notm}} resource groups and resources</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

List resource groups.

```
ibmcloud resource groups [--default]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--default</dt>
  <dd>Get the default group of the current account.</dd>
</dl>

<strong>Examples</strong>:

List all resource groups under the currently targeted account:

```
ibmcloud resource groups
```

List default group of currently targeted account:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Show details of a resource group

```
ibmcloud resource group NAME [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the resource group</dd>
  <dt>--id</dt>
  <dd>Show ID only</dd>
</dl>

<strong>Examples</strong>:

Show resource group `example-group`:

```
ibmcloud resource group example-group
```

Show only ID of resource group `example-group`:

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Create a resource group

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:

<strong>Examples</strong>:

Create a resource group `example-group` with quota `free`:

```
ibmcloud resource group-create example-group free
```

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Update an existing resource group

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the target resource group</dd>
  <dt>-n, --name</dt>
  <dd>New name of the resource group</dd>
  <dt>-q, --quota</dt>
  <dd>Name of the new quota definition</dd>
  <dt>-f</dt>
  <dd>Force update without confirmation</dd>
</dl>

<strong>Examples</strong>:

Rename resource group `example-group` to `trial-group`:

```
ibmcloud resource group-update example-group -n trial-group
```

Change the quota of resource group `example-group` to `free`:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

List all quota definitions

```
ibmcloud resource quotas
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

List all quota definitions:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Show details of a quota definition

```
ibmcloud resource quota NAME
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the quota</dd>
</dl>

<strong>Examples</strong>:
Show details of quota `free`:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrate a Cloudfoundry service instance into resource group

```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Prerequisites</strong>: Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME or SERVICE_INSTANCE_ID (required)</dt>
  <dd>Name or ID of the service instance</dd>
  <dt>--resource-group-name</dt>
  <dd>Name of the resource group. This option is exclusive with '--resource-group-id'. If none of them is specified, default to currently targeted resource group.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID of the resource group. This option is exclusive with'--resource-group-name'. If none of them is specified, default to currently targeted resource group.</dd>
  <dt>-f, --force</dt>
  <dd>Migrate without confirmation</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

List service instances

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Name of belonging service</dd>
  <dt>--location</dt>
  <dd>Filter by location</dd>
  <dt>--long</dt>
  <dd>Show additional fields in output</dd>
</dl>

<strong>Examples</strong>:

List service instances of service `test-service`:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Show details of a service instance

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required), exclusive with ID</dt>
  <dd>Name of the service instance</dd>
  <dt>ID (required), exclusive with NAME</dt>
  <dd>ID of the service instance</dd>
  <dt>--location</dt>
  <dd>Filter by location</dd>
  <dt>--id</dt>
  <dd>Display the ID of service instance</dd>
</dl>

<strong>Examples</strong>:

Show details of service instance `my-service-instance`:

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Create a service instance

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service instance</dd>
  <dt>SERVICE_NAME or SERVICE_ID (required)</dt>
  <dd>Name or ID of the service</dd>
  <dt>SERVICE_PLAN_NAME or SERVICE_PLAN_ID (required)</dt>
  <dd>Name or ID of the service plan</dd>
  <dt>LOCATION</dt>
  <dd>Target location or environment to create the service instance</dd>
  <dt>-t, --tags</dt>
  <dd>Tags</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON file or JSON string of parameters to create service instance</dd>
  <dt>-d, --deployment</dt>
  <dd>Name of the deployment</dd>
</dl>

<strong>Examples</strong>:
Create a service instance named `my-service-instance` using service plan `test-service-plan` of service `test-service` on location `eu-gb`:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Update service instance

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>Name (required)</dt>
  <dd>Name of the service instance, exclusive with ID</dd>
  <dt>ID (required)</dt>
  <dd>ID of the service instance, exclusive with NAME</dd>
  <dt>-n, --name</dt>
  <dd>New service instance name</dd>
  <dt>-t, --tags</dt>
  <dd>New tags</dd>
  <dt>--service-plan-id</dt>
  <dd>New Service Plan ID</dd>
  <dt>-f, --force</dt>
  <dd>Force update without confirmation</dd>
</dl>

<strong>Examples</strong>:
Update service instance `my-service-instance`, change its name to `new-service-instance`:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Delete service instance

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>Name (required)</dt>
  <dd>Name of the service instance, exclusive with ID</dd>
  <dt>ID (required)</dt>
  <dd>ID of the service instance, exclusive with NAME</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
  <dt>--recursive</dt>
  <dd>Delete all belonging resources</dd>
</dl>

<strong>Examples</strong>:
Delete resource service-instance `my-service-instance`:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Show bindings to the service alias

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ALIAS (required)</dt>
  <dd>Service alias name</dd>
</dl>

<strong>Examples</strong>:
Show resource bindings to service alias `my-service-alias`:

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Show details of a service binding

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Service alias name</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry application name</dd>
  <dt>--id</dt>
  <dd>Only display the ID. All other output for the service binding is suppressed.</dd>
</dl>

<strong>Examples</strong>:
Show details of service binding between service alias `my-service-alias` and app `my-app`:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Create a service binding

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (required)</dt>
  <dd>Service alias name</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry application name</dd>
  <dt>ROLE_NAME</dt>
  <dd>Name of the user role</dd>
  <dt>--service-id</dt>
  <dd>Name or UUID of the service ID which the role belongs to</dd>
  <dt>-p, --parameter</dt>
  <dd>Parameters JSON file or JSON string</dd>
  <dt>-f, --force</dt>
  <dd>Force creation without confirmation</dd>
</dl>

<strong>Examples</strong>:
Create a service bindings between service alias `my-service-alias` and app `my-app` with role `Administrator`:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Delete a service binding

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Prerequisites</strong>: None

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (required)</dt>
  <dd>Service alias name</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry application name</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
</dl>

<strong>Examples</strong>:
Delete the service binding between service alias `my-service-alias` and app `my-app`:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

List service keys of service instance or service alias

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Service Instance ID</dd>
  <dt>--instance-name</dt>
  <dd>Service Instance Name</dd>
  <dt>--alias-id</dt>
  <dd>Service Alias ID</dd>
  <dt>--alias-name</dt>
  <dd>Service Alias Name</dd>
</dl>

<strong>Examples</strong>:
List service keys of service instance `my-service-instance`:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Show details of a service key

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Name of the key</dd>
  <dt>--id</dt>
  <dd>Display the ID of service key</dd>
</dl>

<strong>Examples</strong>:
Show details of service keys `my-service-key`:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Create a service key

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>NAME</dt>
  <dd>Name of the key</dd>
  <dt>ROLE_NAME</dt>
  <dd>Name of the user role</dd>
  <dt>--instance-id</dt>
  <dd>Service Instance ID</dd>
  <dt>--instance-name</dt>
  <dd>Service Instance Name</dd>
  <dt>--alias-id</dt>
  <dd>Service Alias ID</dd>
  <dt>--alias-name</dt>
  <dd>Service Alias Name</dd>
  <dt>--service-id</dt>
  <dd>Name or UUID of the service ID which the role belongs to</dd>
  <dt>-p, --parameters</dt>
  <dd>Parameters JSON file or JSON string</dd>
  <dt>-f, --force</dt>
  <dd>Force creation without confirmation</dd>
</dl>

<strong>Examples</strong>:
Create a service key named `my-service-key` with role `Administrator` for service instance `my-service-instance`:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Delete a service key

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Name of the key</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
</dl>

<strong>Examples</strong>:
Delete service key `my-service-key`:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

List aliases for a service instance

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID of the belonging service instance.</dd>
  <dt>--instance-name</dt>
  <dd>Name of the belonging service instance.</dd>
</dl>

<strong>Examples</strong>:
List service aliases for service instance `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Show details of a service alias

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Name of the service alias</dd>
  <dt>--id</dt>
  <dd>Only display the given service alias's ID. All other output for the alias is suppressed.</dd>
</dl>

<strong>Examples</strong>:
Show details of service alias `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Create an alias of a service instance

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Name of the service alias</dd>
  <dt>--instance-id</dt>
  <dd>ID of the belonging service instance.</dd>
  <dt>--instance-name</dt>
  <dd>Name of the belonging service instance.</dd>
  <dt>-s</dt>
  <dd>Name of the space in which the alias is created. Default is the current space.</dd>
  <dt>-t, --tags</dt>
  <dd>Tags list.</dd>
  <dt>-p, --parameters</dt>
  <dd>Parameters JSON file or JSON string.</dd>
</dl>

<strong>Examples</strong>:
Create a service alias named `my-service-alias` of service instance `my-service-instance`:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Update an service alias

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Name of the service alias</dd>
  <dt>-n, --name</dt>
  <dd>New name of the service alias.</dd>
  <dt>-t, --tags</dt>
  <dd>Tags list.</dd>
  <dt>-p, --parameters</dt>
  <dd>Parameters JSON file or JSON string.</dd>
  <dt>-f, --force</dt>
  <dd>Force update without user confirmation.</dd>
</dl>

<strong>Examples</strong>:
Update service alias `my-service-alias`, change its name to `new-service-alias`:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Delete a service alias

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Name of the service alias</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
</dl>

<strong>Examples</strong>:
Delete service alias `my-service-alias`:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Search resources using Lucene query syntax

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Starting resource position number</dd>
  <dt>-l, -limit</dt>
  <dd>Number of resources to return (maximum 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Property to sort by. Accepted inputs are `name`, `family`, `region`, `type`, `crn`.</dd>
</dl>

<strong>Examples</strong>:
Search for Cloud Foundry applications whose name starts with a specified text:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Search for Cloud Foundry service instances of the specified service name:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Search for Cloud Foundry service bindings in the organization with the specified ID:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Search for Cloud Foundry spaces with the specified name and located in one of the two specified regions:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Search for resources whose name contains the word dev in the Cloud Foundry space with the specified ID:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Search for Resource Controller resources in the specified location (i.e. in us-south region):

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Search for resources or aliases in the resource group with the specified ID:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Search for resource groups with name default:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Search for resource bindings for the specified service name:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Search for a resource with the specified Cloud Resource Name (CRN):

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Search for a resource with the specified tag:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

List all tags

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Tag Type (supported values: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>Starting resource position number (default: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Number of resources to return (maximum 10000) (default: 10000)</dd>
</dl>

<strong>Examples</strong>:

List all tags

```
ibmcloud resource tags
```

List all restricted tags

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Show details of a tag

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name, exclusive with --tag-crn</dd>
  <dt>--tag-crn (required)</dt>
  <dd>Tag CRN, exclusive with --tag-name</dd>
</dl>

<strong>Examples</strong>:

Show details of tag "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Create a tag

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name</dd>
  <dt>--tag-type</dt>
  <dd>Tag type (supported values: user, restricted; default: user)</dd>
</dl>

<strong>Examples</strong>:

Create a user tag with name think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Create a restricted tag with name department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Create a user tag with name "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Create a restricted tag with name "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Delete a tag

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name, exclusive with --tag-crn</dd>
  <dt>--tag-crn (required)</dt>
  <dd>Tag CRN, exclusive with --tag-name</dd>
</dl>

<strong>Examples</strong>:

Deletag tag "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Add a tag to a resource

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name, exclusive with --tag-crn</dd>
  <dt>--tag-crn (required)</dt>
  <dd>Tag CRN, exclusive with --tag-name</dd>
  <dt>--resource-crn (required)</dt>
  <dd>Resource CRN</dd>
</dl>

<strong>Examples</strong>:

Add tag "Ray Brown" to resource whose crn is resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Remove a tag from a resource

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name, exclusive with --tag-crn</dd>
  <dt>--tag-crn (required)</dt>
  <dd>Tag CRN, exclusive with --tag-name</dd>
  <dt>--resource-crn (required)</dt>
  <dd>Resource CRN</dd>
</dl>

<strong>Examples</strong>:

Remove tag "Ray Brown" from resource whose crn is resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Switch user tag to restricted tag and vice versa

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>Tag Name, exclusive with --tag-crn</dd>
  <dt>--tag-crn (required)</dt>
  <dd>Tag CRN, exclusive with --tag-name</dd>
  <dt>--tag-type (required)</dt>
  <dd>Tag type</dd>
</dl>

<strong>Examples</strong>:

Switch tag "Ray Brown" to restricted tag

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
