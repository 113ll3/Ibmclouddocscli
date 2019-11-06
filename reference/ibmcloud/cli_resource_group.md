---

copyright:
  years: 2018, 2019
lastupdated: "2019-11-06"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Working with resources and resource groups
{: #ibmcloud_commands_resource}

A resource group is a way for you to organize your account resources in customizable groupings. Use the following commands to manage {{site.data.keyword.cloud}} resources in a resource group.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

List resource groups.
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--default</dt>
  <dd>Get the default group of the current account.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

List all resource groups under the currently targeted account:
```
ibmcloud resource groups
```
{: codeblock}

List default group of currently targeted account:
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

Show details of a resource group
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the resource group</dd>
  <dt>--id</dt>
  <dd>Show ID only</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

Show resource group `example-group`:
```
ibmcloud resource group example-group
```
{: codeblock}

Show only ID of resource group `example-group`:
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Create a resource group:
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the resource group</dd>
</dl>

<strong>Examples</strong>:

Create a resource group `example-group`:
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Update an existing resource group
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] 
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the target resource group</dd>
  <dt>-n, --name</dt>
  <dd>New name of the resource group</dd>
  <dt>-f</dt>
  <dd>Force update without confirmation</dd>
</dl>

<strong>Examples</strong>:

Rename resource group `example-group` to `trial-group`:
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

List all quota definitions.
```
ibmcloud resource quotas
```
{: codeblock}

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

List all quota definitions:
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Show details of a quota definition.
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the quota</dd>
</dl>

<strong>Examples</strong>:

Show details of quota `free`:
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrate a Cloud Foundry service instance into resource group:
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Prerequisites</strong>: Login, Target

<strong>Command options</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME or SERVICE_INSTANCE_ID (required)</dt>
  <dd>Name or ID of the service instance</dd>
  <dt>--resource-group-name</dt>
  <dd>Name of the resource group. This option is exclusive with '--resource-group-id'. If none of them is specified, default to currently targeted resource group.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID of the resource group. This option is exclusive with'--resource-group-name'. If none of them is specified, default to currently targeted resource group.</dd>
  <dt>-f, --force</dt>
  <dd>Migrate without confirmation.</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

List service instances.
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>Name of belonging service</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>Filter by location</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>Type of instances. `service_instance` type is used if not specified, use all to list all types of instances.</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Resource group name</dd>
  <dt>--long</dt>
  <dd>Show more fields in output.</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>Specify output format, only JSON is supported now. </dd>
</dl>

<strong>Examples</strong>:

List service instances of service `test-service`:
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Show details of a service instance.

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required), exclusive with ID</dt>
  <dd>Name of the service instance</dd>
  <dt>ID (required), exclusive with NAME</dt>
  <dd>ID of the service instance</dd>
  <dt>--location</dt>
  <dd>Filter by location</dd>
  <dt>--id</dt>
  <dd>Display the ID of service instance</dd>
  <dt>--output</dt>
  <dd>Specify output format, only JSON is supported now. This option is exclusive with '--id'.</dd>
</dl>

<strong>Examples</strong>:

Show details of service instance `my-service-instance`:
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Create a service instance.
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service instance</dd>
  <dt>SERVICE_NAME or SERVICE_ID (required)</dt>
  <dd>Name or ID of the service. To list service offerings, use the `ibmcloud catalog service-marketplace`[command](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_catalog#ibmcloud_catalog_service_marketplace).</dd>
  <dt>SERVICE_PLAN_NAME or SERVICE_PLAN_ID (required)</dt>
  <dd>Name or ID of the service plan</dd>
  <dt>LOCATION (required)</dt>
  <dd>Target location or environment to create the service instance</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>Name of the deployment</dd>
  <dt>-p, --parameters <i>@JSONFILE or JSON_STRING</i></dt>
  <dd>JSON file or JSON string of parameters to create service instance</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Resource group name</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Types of the service endpoints. Possible values are 'public', 'private', 'public-and-private'.</dd>
</dl>

<strong>Examples</strong>:

Create a service instance that is named `my-service-instance`, that uses service plan `test-service-plan` of service `test-service` on location `eu-gb`:
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Update service instance.
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>Name (required)</dt>
  <dd>Name of the service instance, exclusive with ID</dd>
  <dt>ID (required)</dt>
  <dd>ID of the service instance, exclusive with NAME</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>New service instance name</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>New Service Plan ID</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>JSON file or JSON string of parameters to create service instance</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Resource group name</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Types of the service endpoints. Possible values are 'public', 'private', 'public-and-private'.</dd>
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

Delete service instance.
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
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
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Show bindings to the service alias.
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>SERVICE_ALIAS (required)</dt>
  <dd>Service alias name</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

Show resource bindings to service alias `my-service-alias`:
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Show details of a service binding.
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Service alias name</dd>
  <dt>APP_NAME</dt>
  <dd>CloudFoundry application name</dd>
  <dt>--id</dt>
  <dd>Display the ID. All other output for the service binding is suppressed. This option is exclusive with '--output'.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now. This option is exclusive with '--id'.</dd>
</dl>

<strong>Examples</strong>:

Show details of service binding between service alias `my-service-alias` and app `my-app`:
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Create a service binding.
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (required)</dt>
  <dd>Service alias name</dd>
  <dt>APP_NAME (required)</dt>
  <dd>CloudFoundry application name</dd>
  <dt>ROLE_NAME (required)</dt>
  <dd>Name of the user role</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Name or UUID of the service ID, which the role belongs to</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Parameters JSON file or JSON string</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Type of the service endpoint. Possible values are 'public', 'private'.</dd>
  <dt>-f, --force</dt>
  <dd>Force creation without confirmation</dd>
</dl>

<strong>Examples</strong>:

Create a service binding between service alias `my-service-alias` and app `my-app` with role `Administrator`:
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Delete a service binding.
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Prerequisites</strong>: None

<strong>Command options</strong>:
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
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

List service keys of service instance or service alias.
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Service Instance ID</dd>
  <dt>--instance-name</dt>
  <dd>Service Instance Name</dd>
  <dt>--alias-id</dt>
  <dd>Service Alias ID</dd>
  <dt>--alias-name</dt>
  <dd>Service Alias Name</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

List service keys of service instance `my-service-instance`:
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Displays the details of any number of service keys, where the first *n* characters of the service key name matches the supplied KEY_NAME.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME</dt>
  <dd>Name of the key</dd>
  <dt>ID</dt>
  <dd>ID of the key</dd>
  <dt>-g</dt>
  <dd>Resource group name</dd>
  <dt>--id</dt>
  <dd>Display the ID of service key. This option is exclusive with '--output'.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Resource group name</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format, only JSON is supported now. This option is exclusive with '--id'.</dd>
</dl>

<strong>Examples</strong>:

Show details of service keys `my-service-key`:
```
ibmcloud resource service-key my-service-key
```
<strong>Examples</strong>:
Show details of service key with ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79`:

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Create a service key.
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the key</dd>
  <dt>ROLE_NAME (required)</dt>
  <dd>Name of the user role</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>Service Instance ID</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>Service Instance Name</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>Service Alias ID</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>Service Alias Name</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Name or UUID of the service ID, which the role belongs to</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Parameters JSON file or JSON string</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Resource group name</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Type of the service endpoint. Possible values are 'public', 'private'.</dd>
  <dt>-f, --force</dt>
  <dd>Force creation without confirmation</dd>
</dl>

<strong>Examples</strong>:

Create a service key named `my-service-key` with role `Administrator` for service instance `my-service-instance`:
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Update a service key.
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>Name or ID of the key</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>New name of the key</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>ID of the resource group to which the key belongs</dd>
  <dt>-f, --force</dt>
  <dd>Force update without confirmation</dd>
</dl>

<strong>Examples</strong>:

Update a service key named `my-service-key`, give it a new name `my-service-key-2`:
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Delete a service key.
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>Name of the key or the ID of the key</dd>
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

List aliases for a service instance.
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID of the belonging service instance.</dd>
  <dt>--instance-name</dt>
  <dd>Name of the belonging service instance.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

List service aliases for service instance `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Show details of a service alias.
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>ALIAS_NAME (required)</dt>
  <dd>Name of the service alias</dd>
  <dt>--id</dt>
  <dd>Display the service alias's ID. All other output for the alias is suppressed. This option is exclusive with '--output'.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Specify output format, only JSON is supported now. This option is exclusive with '--id'.</dd>
</dl>

<strong>Examples</strong>:

Show details of service alias `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Create an alias of a service instance.
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
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

Update a service alias.
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
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

Delete a service alias.
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command options</strong>:
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

Search resources by using Lucene query syntax.
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Starting resource position number</dd>
  <dt>-l, -limit</dt>
  <dd>Number of resources to return (maximum 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Property to sort by. Accepted inputs are `name`, `family`, `region`, `type`, `crn`.</dd>
  <dt>-p, --provider</dt>
  <dd>Display Classic Infrastructure resources. The only value allowed is: classic-infrastructure</dd>
</dl>

<strong>Searcheable attributes</strong>:
You can search for the following attributes:

<dl>
  <dt>name</dt>
  <dd>The user-defined name of the resource.</dd>
  <dt>region</dt>
  <dd>The geographical location where the resource is provisioned. For example: us-south, us-east, au-syd, eu-gb, eu-de, and jp-tok.</dd>
  <dt>service_name</dt>
  <dd>The name of the service as it appears in the Name column of the output of 'ibmcloud catalog service-marketplace'.</dd>
  <dt>family</dt>
  <dd>The cloud component to which your resource belongs. The allowed values are cloud_foundry, containers,  resource_controller, vmware or ims.</dd>
  <dt>organization_id</dt>
  <dd>The Cloud Foundry organization GUID.</dd>
  <dt>doc.space_id</dt>
  <dd>The Cloud Foundry space GUID.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>The ID of the resource group.</dd>
  <dt>type</dt>
  <dd>The resource type. The allowed values are k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup.</dd>
  <dt>creation_date</dt>
  <dd>The date on which the resource is created.</dd>
  <dt>modification_date</dt>
  <dd>The last modification date of the resource. It is in the format yyyy-mm-ddThh:mm:ssZ </dd>
  <dt>_objectType</dt>
  <dd>The type of the classic infrastructure resource. Allowed values are SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall and SoftLayer_Virtual_Guest. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>The tag attached to a resource. Use tagReferences.tag.name when searching for tags attached to classic infrastructure resources </dd> 
</dl>

<strong>Examples</strong>:

Search for Cloud Foundry apps whose name starts with a specified text:
```
ibmcloud resource search "name:my* AND type:cf-application"
```

Search for Cloud Foundry service instances of the specified service name:
```
ibmcloud resource search "service_name:messagehub AND type:cf-service-instance"
```

Search for Cloud Foundry service bindings in the organization with the specified ID:
```
ibmcloud resource search "organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding"
```

Search for Cloud Foundry spaces with the specified name and located in one of the two specified regions:
```
ibmcloud resource search "name:dev AND type:cf-space AND region:(us-south OR eu-gb)"
```

Search for resources whose name contains the word dev in the Cloud Foundry space with the specified ID:
```
ibmcloud resource search "name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7"
```

Search for Resource Controller resources in the specified location (i.e. in us-south region):
```
ibmcloud resource search "region:us-south AND family:resource_controller"
```

Search for resources or aliases in the resource group with the specified ID:
```
ibmcloud resource search "(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)"
```

Search for resource groups with name default:
```
ibmcloud resource search "name:default AND type:resource-group"
```

Search for resource bindings for the specified service name:
```
ibmcloud resource search "service_name:cloud-object-storage AND type:resource-binding"
```

Search for a resource with the specified Cloud Resource Name (CRN):
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Search for a resource with the specified tag:
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

Search for Classic Infrastructure Virtual Guest resource with the specified id (only with -p classic-infrastructure):
```
ibmcloud resource search "id:12345678 _objectType:SoftLayer_Virtual_Guest"
```
{: codeblock}

Search for Classic Infrastructure Hardware resource with the specified tag name (only with -p classic-infrastructure):
```
ibmcloud resource search "tagReferences.tag.name:name _objectType:SoftLayer_Hardware"
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

List all tags in your billing account

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Starting tag position number.</dd>
  <dt>-l, -limit</dt>
  <dd>Number of tags to return (maximum 1000, default 100).</dd>
  <dt>-p; --provider</dt> 
  <dd>Specify classic-infrastructure when you search for classic infrastructure tags.</dd>
  <dt>-d, --details</dt>
  <dd>Show the number of tagged resources.</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Attach one or more tags to a resource:
```
ibmcloud resource tag-attach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```
<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--tag-names(required)</dt>
  <dd>Comma-separated list of tag names</dd>
  <dt>--resource-name</dt>
  <dd>The name of the resource to which the tags are to be attached. This option cannot be used with classic infrastructure resources.</dd>
  <dt>--resource-id</dt>
  <dd>The CRN of the resource to which the tags are going to be attached; for classic infrastructure resources, it is the ID of the resource. You can obtain the CRN or the ID of the resource by using the `ibmcloud resource search` command.</dd>
  <dt>--resource-type</dt>
  <dd>The resource type of the classic infrastructure resource to which the tags are going to be attached. This parameter is required if you are attaching a tag to a classic infrastructure resource. Possible values for --resource-type are: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall and SoftLayer_Virtual_Guest. </dd>
</dl>

<strong>Examples</strong>:

* To attach the tag `MyTag` to a Kubernetes cluster named `MyCluster`, first look for the CRN of the cluster you would like to tag:
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  Take note of the CRN, which is a string similar to the following example: 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  To attach the tag, run the following command:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* To attach the tag `MyTag` to a resource names `MyResource`:
  ```
  ibmcloud resource tag-attach --tag-name MyTag --resource-name  'MyResource'
  ```
  {: codeblock}
  
  
* To attach the tag `MyTag` to a classic infrastructure virtual guest named `MyVM`, first look for the ID of the virtual guest you would like to tag:
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  Take a note of the ID, which is a string similar to `48373549`.

  To attach the tag, run the following command:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Detaching one or more tags from a resource:
```
ibmcloud resource tag-detach  --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--tag-names(required)</dt>
  <dd>Comma-separated list of tag names</dd>
  <dt>--resource-name</dt>
  <dd>The name of the resource from which the tags are to be detached. This option cannot be used with classic infrastructure resources.</dd>
  <dt>--resource-id</dt>
  <dd>The CRN of the resource from which the tags are going to be detached; for classic infrastructure resources, it is the ID of the resource. You can obtain the CRN or the ID of the resource by using `ibmcloud resource search` command.</dd>
  <dt>--resource-type</dt>
  <dd>The resource type of the classic infrastructure resource from which the tags are going to be detached; this parameter is required if you are attaching a tag to a classic infrastructure resource. Possible values for --resource-type are: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall and SoftLayer_Virtual_Guest. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Delete a tag:
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--tag-name (required)</dt>
  <dd>The name of the tag to be deleted.</dd>
  <dt>-p, --provider</dt>
  <dd>Specify `classic-infrastructure` when you delete a classic infrastructure tag.</dd>
</dl>

A tag can be deleted only if it isn't attached to any resource.

## ibmcloud resource reclamations
{: #ibmcloud_resource_reclamations}

List reclaimed resources that can be restored or deleted:
```
ibmcloud resource reclamations [--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID of the resource instance</dd>
  <dt>--instance-name</dt>
  <dd>Name of the resource instance</dd>
  <dt>--output</dt>
  <dd>Specify output format, only `JSON` is supported.</dd>
</dl>

<strong>Examples</strong>:

List all resource reclamations:
```
ibmcloud resource reclamations
```

List resource reclamation of service instance `test-cloudant`:
```
ibmcloud resource reclamations --instance-name "test-cloudant"
```

## ibmcloud resource reclamation-restore
{: #ibmcloud_resource_reclamation_restore}

Restore a reclaimed resource so that the resource is available again:
```
ibmcloud resource reclamation-restore --id RECLAMATION_ID [--comment COMMENT] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--id (required)</dt>
  <dd>ID of the resource reclamation</dd>
  <dt>--comment</dt>
  <dd>Comments about the action</dd>
  <dt>--output</dt>
  <dd>Specify output format, only `JSON` is supported.</dd>
</dl>

<strong>Examples</strong>:

Restore a resource reclamation with ID `d9fendfwlw`:
```
ibmcloud resource reclamation-restore --id "d9fendfwlw"
```

Restore a resource reclamation with ID `d9fendfwlw`, leave a comment of "need to use for another 3 months", and show JSON output:
```
ibmcloud resource reclamation-restore --id "d9fendfwlw" --comment "need to use for another 3 months" --output JSON
```

## ibmcloud resource reclamation-delete
{: #ibmcloud_resource_reclamation_delete}

Delete a reclaimed resource so that the resource can no longer be restored:
```
ibmcloud resource reclamation-delete --id RECLAMATION_ID [--comment COMMENT] [--f, --force] [--output FORMAT]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--id (required)</dt>
  <dd>ID of the resource reclamation</dd>
  <dt>--comment</dt>
  <dd>Comments about the action</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
  <dt>--output</dt>
  <dd>Specify output format, only `JSON` is supported.</dd>
</dl>

<strong>Examples</strong>:

Delete a resource reclamation with ID `d9fendfwlw`:
```
ibmcloud resource reclamation-delete --id "d9fendfwlw"
```

Delete a resource reclamation with ID `d9fendfwlw` and leave a comment of "no longer needed" without confirmation:
```
ibmcloud resource reclamation-delete --id "d9fendfwlw" --comment "no longer needed" -f
```

