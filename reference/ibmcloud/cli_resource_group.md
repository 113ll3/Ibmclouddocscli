---

copyright:
  years: 2018, 2023
lastupdated: "2023-01-23"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Working with resources and resource groups (ibmcloud resource)
{: #ibmcloud_commands_resource}

A resource group is a way for you to organize your account resources in customizable groupings. Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} resources in a resource group.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

List resource groups.
```bash
ibmcloud resource groups [--default]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_groups_options}

--default
:   Get the default group of the current account.

### Examples
{: #ibmcloud_resource_groups_examples}

List all resource groups under the currently targeted account:
```bash
ibmcloud resource groups
```
{: codeblock}

List default group of currently targeted account:
```bash
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

Show details of a resource group
```bash
ibmcloud resource group NAME [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_group_options}

NAME (required)
:   Name of the resource group

--id
:   Show ID only


### Examples
{: #ibmcloud_resource_group_examples}

Show resource group `example-group`:
```bash
ibmcloud resource group example-group
```
{: codeblock}

Show only ID of resource group `example-group`:
```bash
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Create a resource group:
```bash
ibmcloud resource group-create NAME
```
{: codeblock}

### Command options
{: #ibmcloud_resource_group_create_options}

NAME (required)
:   Name of the resource group

### Examples
{: #ibmcloud_resource_group_create_examples}

Create a resource group `example-group`:
```bash
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Update an existing resource group
```bash
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_group_update_options}

NAME (required)
:   Name of the target resource group

-n, --name
:   New name of the resource group

-f, --force
:   Force update without confirmation



### Examples
{: #ibmcloud_resource_group_update_examples}

Rename resource group `example-group` to `trial-group`:
```bash
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

## ibmcloud resource group-delete
{: #ibmcloud_resource_group_delete}

Delete an existing resource group
```bash
ibmcloud resource group-delete NAME [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_group_delete_options}

NAME (required)
:   Name of the target resource group

-f, --force
:   Force deletion without confirmation



### Examples
{: #ibmcloud_resource_group_delete_examples}

Delete resource group `example-group`:
```bash
ibmcloud resource group-delete example-group -f
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

List all quota definitions.
```bash
ibmcloud resource quotas
```
{: codeblock}

### Examples
{: #ibmcloud_resource_quotas_examples}

List all quota definitions:
```bash
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Show details of a quota definition.
```bash
ibmcloud resource quota NAME
```
{: codeblock}

### Command options
{: #ibmcloud_resource_quota_options}

NAME (required)
:   Name of the quota



### Examples
{: #ibmcloud_resource_quota_examples}

Show details of quota `free`:
```bash
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrate a Cloud Foundry service instance into resource group:
```bash
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_cf_service_instance_migrate_options}

SERVICE_INSTANCE_NAME or SERVICE_INSTANCE_ID (required)
:   Name or ID of the service instance

--resource-group-name
:   Name of the resource group. This option is exclusive with '--resource-group-id'. If none of them is specified, default to currently targeted resource group.

--resource-group-id
:   ID of the resource group. This option is exclusive with'--resource-group-name'. If none of them is specified, default to currently targeted resource group.

-f, --force
:   Migrate without confirmation.



## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

List service instances.
```bash
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP | --all-resource-groups] [--long]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instances_options}

--service-name *SERVICE_NAME*
:   Name of belonging service

--location *LOCATION*
:   Filter by location

--type *INSTANCE_TYPE*
:   Type of instances. `service_instance` type is used if not specified, use all to list all types of instances.

-g *RESOURCE_GROUP*
:   Resource group name

--all-resource-groups
:   Query all resource groups

--long
:   Show more fields in output.



### Examples
{: #ibmcloud_resource_service_instances_examples}

List service instances of service `test-service`:
```bash
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Show details of a service instance.

```bash
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_options}

NAME (required), exclusive with ID
:   Name of the service instance

ID (required), exclusive with NAME
:   ID of the service instance

--location
:   Filter by location

--id
:   Display the ID of service instance



### Examples
{: #ibmcloud_resource_service_instance_examples}

Show details of service instance `my-service-instance`:
```bash
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Create a service instance.
```bash
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [--allow-cleanup] [--lock]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_create_options}

NAME (required)
:   Name of the service instance

SERVICE_NAME or SERVICE_ID (required)
:   Name or ID of the service. To list service offerings, use the `ibmcloud catalog service-marketplace`[command](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_catalog#ibmcloud_catalog_service_marketplace).

SERVICE_PLAN_NAME or SERVICE_PLAN_ID (required)
:   Name or ID of the service plan

LOCATION (required)
:   Target location or environment to create the service instance

-d, --deployment *DEPLOYMENT_NAME*
:   Name of the deployment

-p, --parameters *@JSONFILE or JSON_STRING*
:   JSON file or JSON string of parameters to create service instance

-g *RESOURCE_GROUP*
:   Resource group name

--service-endpoints *SERVICE_ENDPOINTS_TYPE*
:   Types of the service endpoints. Possible values are 'public', 'private', 'public-and-private'.

--allow-cleanup
:   Whether the service instance should be deleted (cleaned up) during the processing of a region instance delete call

--lock
:   Whether to create the service instance with locked state



### Examples
{: #ibmcloud_resource_service_instance_create_examples}

Create a service instance that is named `my-service-instance`, that uses service plan `test-service-plan` of service `test-service` on location `eu-gb`:
```bash
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Update service instance.
```bash
ibmcloud resource service-instance-update ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_update_options}

Name (required)
:   Name of the service instance, exclusive with ID

ID (required)
:   ID of the service instance, exclusive with NAME

-n, --name *NEW_NAME*
:   New service instance name

--service-plan-id *SERVICE_PLAN_ID*
:   New Service Plan ID

-p, --parameters *@JSON_FILE | JSON_STRING*
:   JSON file or JSON string of parameters to create service instance

-g *RESOURCE_GROUP*
:   Resource group name

--service-endpoints *SERVICE_ENDPOINTS_TYPE*
:   Types of the service endpoints. Possible values are 'public', 'private', 'public-and-private'.

-f, --force
:   Force update without confirmation



### Examples
{: #ibmcloud_resource_service_instance_update_examples}

Update service instance `my-service-instance`, change its name to `new-service-instance`:
```bash
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Delete service instance. If provisioning is in progress, the command attempts to cancel the provisioning process. Some services might not support cancellation.
```bash
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_delete_options}

Name (required)
:   Name of the service instance, exclusive with ID

ID (required)
:   ID of the service instance, exclusive with NAME

-f, --force
:   Force deletion without confirmation

--recursive
:   Delete all belonging resources



### Examples
{: #ibmcloud_resource_service_instance_delete_examples}

Delete resource service-instance `my-service-instance`:
```bash
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-lock
{: #ibmcloud_resource_service_instance_lock}

Lock service instance.
```bash
ibmcloud resource service-instance-lock ( NAME | ID ) [-g RESOURCE_GROUP] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_lock_options}

Name (required)
:   Name of the service instance, exclusive with ID

ID (required)
:   ID of the service instance, exclusive with NAME

-g *RESOURCE_GROUP*
:   Resource group name

-f, --force
:   Force locking without confirmation



### Examples
{: #ibmcloud_resource_service_instance_lock_examples}

Lock resource service-instance `my-service-instance`:
```bash
ibmcloud resource service-instance-lock my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-unlock
{: #ibmcloud_resource_service_instance_unlock}

Unlock service instance.
```bash
ibmcloud resource service-instance-unlock ( NAME | ID ) [-g RESOURCE_GROUP] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_instance_unlock_options}

Name (required)
:   Name of the service instance, exclusive with ID

ID (required)
:   ID of the service instance, exclusive with NAME

-g *RESOURCE_GROUP*
:   Resource group name

-f, --force
:   Force locking without confirmation



### Examples
{: #ibmcloud_resource_service_instance_unlock_examples}

Unlock resource service-instance `my-service-instance`:
```bash
ibmcloud resource service-instance-unlock my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Show bindings to the service alias.
```bash
ibmcloud resource service-bindings SERVICE_ALIAS
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_bindings_options}

SERVICE_ALIAS (required)
:   Service alias name


### Examples
{: #ibmcloud_resource_service_bindings_examples}

Show resource bindings to service alias `my-service-alias`:
```bash
ibmcloud resource bindings my-service-alias
```
{: codeblock}

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Show details of a service binding.
```bash
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_binding_options}

ALIAS_NAME (required)
:   Service alias name

APP_NAME
:   CloudFoundry application name

--id
:   Display the ID. All other output for the service binding is suppressed. This option is exclusive with '--output'.



### Examples
{: #ibmcloud_resource_service_binding_examples}

Show details of service binding between service alias `my-service-alias` and app `my-app`:
```bash
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Create a service binding.
```bash
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_binding_create_options}

SERVICE_ALIAS_NAME (required)
:   Service alias name

APP_NAME (required)
:   CloudFoundry application name

ROLE_NAME (required)
:   Name of the user role

--service-id *SERVICE_ID*
:   Name or UUID of the service ID, which the role belongs to

-p, --parameter *@JSON_FILE | JSON_TEXT*
:   Parameters JSON file or JSON string

--service-endpoint *SERVICE_ENDPOINT_TYPE*
:   Type of the service endpoint. Possible values are 'public', 'private'.

-f, --force
:   Force creation without confirmation



### Examples
{: #ibmcloud_resource_service_binding_create_examples}

Create a service binding between service alias `my-service-alias` and app `my-app` with role `Administrator`:
```bash
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Delete a service binding.
```bash
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_binding_delete_options}

SERVICE_ALIAS_NAME (required)
:   Service alias name

APP_NAME
:   CloudFoundry application name

-f, --force
:   Force deletion without confirmation



### Examples
{: #ibmcloud_resource_service_binding_delete_examples}

Delete the service binding between service alias `my-service-alias` and app `my-app`:
```bash
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

List service keys of service instance or service alias.
```bash
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_keys_options}

--instance-id
:   Service Instance ID

--instance-name
:   Service Instance Name

--alias-id
:   Service Alias ID

--alias-name
:   Service Alias Name



### Examples
{: #ibmcloud_resource_service_keys_examples}

List service keys of service instance `my-service-instance`:
```bash
ibmcloud resource service-keys --instance-name my-service-instance
```
{: codeblock}

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Displays the details of any number of service keys, where the first *n* characters of the service key name matches the supplied KEY_NAME.
```bash
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_key_options}

NAME
:   Name of the key

ID
:   ID of the key

-g
:   Resource group name

--id
:   Display the ID of service key. This option is exclusive with '--output'.

-g RESOURCE_GROUP
:   Resource group name

### Examples
{: #ibmcloud_resource_service_key_examples}

Show details of service keys `my-service-key`:
```bash
ibmcloud resource service-key my-service-key
```
{: codeblock}

Show details of service key with ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79`:

```bash
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```
{: codeblock}

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Create a service key.
```bash
ibmcloud resource service-key-create NAME [ROLE_NAME] ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force] [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_key_create_options}

NAME (required)
:   Name of the key.

ROLE_NAME (optional)
:   Name of the IAM service role. The specified role cannot be one of the default platform roles. You can verify eligibility of any role for use with this option by running `ibmcloud iam roles --service <your-service>` and checking that `serviceRole` appears in the role's CRN.

--instance-id *SERVICE_INSTANCE_ID*
:   Service instance ID.

--instance-name *SERVICE_INSTANCE_NAME*
:   Service instance name.

--alias-id *SERVICE_ALIAS_ID*
:   Service alias ID.

--alias-name *SERVICE_ALIAS_NAME*
:   Service alias name.

--service-id *SERVICE_ID*
:   Name or UUID of the service ID, which the role belongs to.

-p, --parameters *@JSON_FILE | JSON_TEXT*
:   Parameters JSON file or JSON string.

-g *RESOURCE_GROUP*
:   Resource group name.

--service-endpoint *SERVICE_ENDPOINT_TYPE*
:   Type of the service endpoint. Possible values are 'public' or 'private'.

--output FORMAT (optional)
:   Specify the output format. Only JSON is supported.

-f, --force
:   Force creation without confirmation

-q, --quite
:   Suppress verbose output.



### Examples
{: #ibmcloud_resource_service_key_create_examples}

Create a service key named `my-service-key` with role `Administrator` for service instance `my-service-instance`:
```bash
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```
{: codeblock}

Create a service key named `my-service-key` without any role for a non-iam-enabled service instance `my-service-instance`:
```bash
ibmcloud resource service-key-create my-service-key --instance-name my-service-instance
```
{: codeblock}

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Update a service key.
```bash
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_key_update_options}

NAME | ID
:   Name or ID of the key

-n, --name NEW_NAME
:   New name of the key

-g RESOURCE_GROUP
:   ID of the resource group to which the key belongs

-f, --force
:   Force update without confirmation



### Examples
{: #ibmcloud_resource_service_key_update_examples}

Update a service key named `my-service-key`, give it a new name `my-service-key-2`:
```bash
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```
{: codeblock}

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Delete a service key.
```bash
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_key_delete_options}

KEY_NAME | KEY_ID
:   Name of the key or the ID of the key

-f, --force
:   Force deletion without confirmation



### Examples
{: #ibmcloud_resource_service_key_delete_examples}

Delete service key `my-service-key`:
```bash
ibmcloud resource service-key-delete my-service-key
```
{: codeblock}

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

List aliases for a service instance.
```bash
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_aliases_options}

--instance-id
:   ID of the belonging service instance.

--instance-name
:   Name of the belonging service instance.



### Examples
{: #ibmcloud_resource_service_aliases_examples}

List service aliases for service instance `my-service-instance`:
```bash
ibmcloud resource service-aliases my-service-instance
```
{: codeblock}

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Show details of a service alias.
```bash
ibmcloud resource service-alias ALIAS_NAME [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_alias_options}

ALIAS_NAME (required)
:   Name of the service alias

--id
:   Display the service alias's ID. All other output for the alias is suppressed. This option is exclusive with '--output'.



### Examples
{: #ibmcloud_resource_service_alias_examples}

Show details of service alias `my-service-alias`:
```bash
ibmcloud resource service-alias  my-service-alias
```
{: codeblock}

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Create an alias of a service instance.
```bash
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_alias_create_options}

ALIAS_NAME (required)
:   Name of the service alias

--instance-id
:   ID of the belonging service instance.

--instance-name
:   Name of the belonging service instance.

-s
:   Name of the space in which the alias is created. Default is the current space.

-t, --tags
:   Tags list.

-p, --parameters
:   Parameters JSON file or JSON string.



### Examples
{: #ibmcloud_resource_service_alias_create_examples}

Create a service alias named `my-service-alias` of service instance `my-service-instance`:
```bash
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```
{: codeblock}

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Update a service alias.
```bash
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_alias_update_options}

ALIAS_NAME (required)
:   Name of the service alias

-n, --name
:   New name of the service alias.

-t, --tags
:   Tags list.

-p, --parameters
:   Parameters JSON file or JSON string.

-f, --force
:   Force update without user confirmation.



### Examples
{: #ibmcloud_resource_service_alias_update_examples}

Update service alias `my-service-alias`, change its name to `new-service-alias`:
```bash
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```
{: codeblock}

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Delete a service alias.
```bash
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_service_alias_delete_options}

ALIAS_NAME (required)
:   Name of the service alias

-f, --force
:   Force deletion without confirmation



### Examples
{: #ibmcloud_resource_service_alias_delete_examples}

Delete service alias `my-service-alias`:
```bash
ibmcloud resource service-alias-delete my-service-alias
```
{: codeblock}

## ibmcloud resource search
{: #ibmcloud_resource_search}

Search resources by using Lucene query syntax.
```bash
ibmcloud resource search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER] [-ir, --is-reclaimed (false, true, any)] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_search_options}

-ir, --is-reclaimed
:   Search for account resources that have been reclaimed. By default the search returns only active resources, however you can set is-reclaimed to any to search for resources whether they have been reclaimed or not. Set this option to `true` to apply the search criteria only to reclaimed resources. Set this option to `false` to search only for active resources. `false` is the default behavior.

-o, -offset
:   Starting resource position number

-l, -limit
:   Number of resources to return, up to a maximum of 10000.

-s, --sort-by
:   Property to sort by. Accepted values are `name`, `family`, `region`, `type`, `crn`.

-p, --provider
:   Display classic infrastructure resources. The only supported value is `classic-infrastructure`.

### Searchable attributes
{: #ibmcloud_resource_search_attributes}

You can search for the following attributes:

name
:   The user-defined name of the resource.

region
:   The geographical location where the resource is provisioned. For example: us-south, us-east, au-syd, eu-gb, eu-de, and jp-tok.

service_name
:   The name of the service as it appears in the Name column of the output of 'ibmcloud catalog service-marketplace'.

family
:   The cloud component to which your resource belongs. The allowed values are cloud_foundry, containers,  resource_controller, vmware or ims.

organization_id
:   The Cloud Foundry organization GUID.

doc.space_id
:   The Cloud Foundry space GUID.

doc.resource_group_id
:   The ID of the resource group.

type
:   The resource type. The allowed values are k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup.

creation_date
:   The date on which the resource is created.

modification_date
:   The last modification date of the resource. It is in the format yyyy-mm-ddThh:mm:ssZ

_objectType
:   The type of the classic infrastructure resource. Allowed values are SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall and SoftLayer_Virtual_Guest.

tags, tagReferences.tag.name
:   The tag attached to a resource. Use tagReferences.tag.name when searching for tags attached to classic infrastructure resources

### Examples
{: #ibmcloud_resource_search_examples}

Search for Cloud Foundry apps whose name starts with a specified text:
```bash
ibmcloud resource search "name:my* AND type:cf-application"
```
{: codeblock}

Search for Cloud Foundry service instances of the specified service name:
```bash
ibmcloud resource search "service_name:messagehub AND type:cf-service-instance"
```
{: codeblock}

Search for Cloud Foundry service bindings in the organization with the specified ID:
```bash
ibmcloud resource search "organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding"
```
{: codeblock}

Search for Cloud Foundry spaces with the specified name and located in one of the two specified regions:
```bash
ibmcloud resource search "name:dev AND type:cf-space AND region:(us-south OR eu-gb)"
```
{: codeblock}

Search for resources whose name contains the word dev in the Cloud Foundry space with the specified ID:
```bash
ibmcloud resource search "name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7"
```
{: codeblock}

Search for Resource Controller resources in the specified location (i.e. in us-south region):
```bash
ibmcloud resource search "region:us-south AND family:resource_controller"
```
{: codeblock}

Search for resources or aliases in the resource group with the specified ID:
```bash
ibmcloud resource search "(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)"
```
{: codeblock}

Search for resource groups with name default:
```bash
ibmcloud resource search "name:default AND type:resource-group"
```
{: codeblock}

Search for resource bindings for the specified service name:
```bash
ibmcloud resource search "service_name:cloud-object-storage AND type:resource-binding"
```
{: codeblock}

Search for a resource with the specified Cloud Resource Name (CRN):
```bash
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```
{: codeblock}

Search for a resource with the specified tag:
```bash
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

Search for Classic Infrastructure Virtual Guest resource with the specified id (only with -p classic-infrastructure):
```bash
ibmcloud resource search "id:12345678 _objectType:SoftLayer_Virtual_Guest"
```
{: codeblock}

Search for Classic Infrastructure Hardware resource with the specified tag name (only with -p classic-infrastructure):
```bash
ibmcloud resource search "tagReferences.tag.name:name _objectType:SoftLayer_Hardware"
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

List all tags in your billing account

```bash
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT]  [-p, --provider classic-infrastructure] [-d, --details true] [-a, --attached true] [--output FORMAT] [--tag-type TAG_TYPE] [--account-id ACCOUNT_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_tags_options}

--offset value, -o value
:   Starting resource position number (default: 0).

--limit value, -l value
:   Number of resources to return (maximum 1000) (default: 100).

--provider value, -p value
:   Display Classic Infrastructure resources, only value allowed is: classic-infrastructure. Use it for resources of type SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress or SoftLayer_Network_Vlan.

--details value, -d value
:   Show additional attributes for each tag, only value allowed is true.

--attached value, -a value
:   Show only filtered attached tags to a resource, only value allowed is true.

--tag-type value
:   Type of the tag. Only allowed values are: user, service or access (default value : user).

--account-id value
:   The ID of the account that owns the tags that you want to list (required if tag-type is set to service).

--output value
:   Specify output format, only JSON is supported now.

-q, --quiet
:   Suppress verbose output.

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Create an access management tag:
```bash
ibmcloud resource tag-create --tag-names TAG_NAMES
```
{: codeblock}

### Command options
{: #ibmcloud_resource_tag_create_options}

--tag-names value
:   Comma separated list of tag names.

-q, --quiet
:   Suppress verbose output.

This command is only valid for access management tags. For example:

* Run the following command to create the access management tag `project:myproject`:
   ```bash
   ibmcloud resource tag-create —tag-names “project:myproject”
   ```
   {: codeblock}

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Attach one or more tags to a resource:
```bash
ibmcloud resource tag-attach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE] [--tag-type TAG_TYPE] [--account-id ACCOUNT_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_tag_attach_options}

--tag-names value
:   Comma-separated list of tag names.

--resource-name value
:   Name of the resource on which the tags should be attached.

--resource-id value
:   CRN of the resource on which the tags should be attached (for Classic Infrastructure resource, it is the ID of the resource).

--resource-type value
:   Type of the tag. Only allowed values are: user, service or access (default value : user).

--tag-type value
:   The type of the tag. The only allowed values are `user` or `service`. The default value is `user`.

--account-id value
:   The ID of the account that owns the resources to be tagged (required if tag-type is set to service).

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_resource_tag_attach_examples}

* To attach the user tag `MyTag` to a Kubernetes cluster named `MyCluster`, first look for the CRN of the cluster you would like to tag:
    ```bash
    ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
    ```
    {: codeblock}

    Take note of the CRN, which is a string similar to the following example:
    ```bash
    crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
    ```
    {: screen}

    To attach the tag, run the following command:
    ```bash
    ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
    ```
    {: codeblock}

* To attach the user tag `MyTag` to a resource named `MyResource`:
    ```bash
    ibmcloud resource tag-attach --tag-name MyTag --resource-name  'MyResource'
    ```
    {: codeblock}


* To attach the user tag `MyTag` to a classic infrastructure virtual guest named `MyVM`, first look for the ID of the virtual guest you would like to tag:
    ```bash
    ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
    ```
    {: codeblock}

    Take a note of the ID, which is a string similar to `48373549`.

    To attach the tag, run the following command:
    ```bash
    ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest
    ```
    {: codeblock}

* To attach the access management tag `project:myproject`, that you previously created, to an instance of IBM Cloud Object Storage called `Project data`, run the following command:
    ```bash
    ibmcloud resource tag-attach --tag-names "project:myproject" --resource-name Project data -—tag-type access
    ```
    {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Detaching one or more tags from a resource:
```bash
ibmcloud resource tag-detach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE] [--tag-type TAG_TYPE] [--account-id ACCOUNT_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_tag_detach_options}

--tag-names value
:   Comma-separated list of tag names.

--resource-name value
:   Name of the resource on which the tags should be attached.

--resource-id value
:   CRN of the resource on which the tags should be attached (for Classic Infrastructure resource, it is the ID of the resource).

--resource-type value
:   Resource type on which the tags should be attached (required for Classic Infrastructure resource of type SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress or SoftLayer_Network_Vlan only).

--tag-type value
:   Type of the tag. Only allowed values are: user, service or access (default value : user).

--account-id value
:   The ID of the account that owns the resources to be detached (required if tag-type is set to service).

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_resource_tag_detach_examples}

* To detach the user tag `MyTag` from a Kubernetes cluster named `MyCluster`, first look for the CRN of the cluster you would like to detach the tag from:
    ```bash
    ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
    ```
    {: codeblock}

    Take note of the CRN, which is a string similar to the following example:
    ```bash
    crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
    ```
    {: screen}

* To detach the tag, run the following command:
    ```bash
    ibmcloud resource tag-detach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
    ```
    {: codeblock}

* To detach the user tag `MyTag` to a resource named `MyResource`:
    ```bash
    ibmcloud resource tag-detach --tag-name MyTag --resource-name 'MyResource'
    ```
    {: codeblock}


* To detach the user tag `MyTag` to a classic infrastructure virtual guest named `MyVM`, first look for the ID of the virtual guest you would like to detach the tag from:
    ```bash
    ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
    ```
    {: codeblock}

    Take a note of the ID, which is a string similar to `48373549`.

* To detach the tag, run the following command:
    ```bash
    ibmcloud resource tag-detach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest
    ```
    {: codeblock}

* To detach the access management tag `project:myproject` from an instance of IBM Cloud Object Storage called `Project data`, run the following command:
    ```bash
    ibmcloud resource tag-detach --tag-names "project:myproject" --resource-name Project data -—tag-type access
    ```
    {: codeblock}


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Delete a tag:
```bash
ibmcloud resource tag-delete (--tag-name TAG_NAME | -a, --all  [-f, --force]) [-p, --provider PROVIDER] [--tag-type TAG_TYPE] [--account-id ACCOUNT_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_tag_delete_options}

--tag-name value
:   Tag name to be deleted.

--provider value, -p value
:   Delete the tag in the specified provider (only supported value is classic-infrastructure). Use it for resources of type SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress or SoftLayer_Network_Vlan.

--tag-type value
:   Type of the tag. Only allowed values are: user, service or access (default value : user).

account-id value
:   The ID of the account that owns the tags to be deleted (required if tag-type is set to service).

--force, -f
:   Delete the tags without confirmation.

--all, -a
:   Delete all tags not attatched to any resources.

-q, --quiet
:   Suppress verbose output.



A tag can be deleted only if it isn't attached to any resource.

### Examples
{: #ibmcloud_resource_tag_delete_examples}

* To delete the user tag `MyTag` from the account:
    ```bash
    ibmcloud resource tag-delete --tag-name "MyTag"
    ```
    {: codeblock}

* To delete the access management tag `project:myproject` from the account:
    ```bash
    ibmcloud resource tag-delete --tag-name "project:myproject" --tag-type access
    ```
    {: codeblock}

* To delete all unused user tags from the account:
    ```bash
    ibmcloud resource tag-delete -a
    ```
    {: codeblock}

* To delete all unused access management tags from the account:
    ```bash
    ibmcloud resource tag-delete -a --tag-type access
    ```
    {: codeblock}


## ibmcloud resource reclamations
{: #ibmcloud_resource_reclamations}

List reclaimed resources that can be restored or deleted:
```bash
ibmcloud resource reclamations [--resource-instance-id INSTANCE_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_reclamations_options}

--resource-instance-id
:   The globally unique ID (GUID) of the resource instance

### Examples
{: #ibmcloud_resource_reclamations_examples}

List all resource reclamations:
```bash
ibmcloud resource reclamations
```
{: codeblock}

List resource reclamations of a particular service instance:
```bash
ibmcloud resource reclamations --resource-instance-id abcd1234-ef56-486e-b293-22d6c7eb6699
```
{: codeblock}

## ibmcloud resource reclamation
{: #ibmcloud_resource_reclamation}

Show details of a resource reclamation:
```bash
ibmcloud resource reclamation RECLAMATION_ID
```
{: codeblock}

### Command options
{: #ibmcloud_resource_reclamation_options}

RECLAMATION_ID
:   Resource reclamation ID


### Examples
{: #ibmcloud_resource_reclamation_examples}

Show details of a resource reclamation:
```bash
ibmcloud resource reclamation daf12d343ef
```
{: codeblock}

## ibmcloud resource reclamation-restore
{: #ibmcloud_resource_reclamation_restore}

Restore a reclaimed resource so that the resource is available again:
```bash
ibmcloud resource reclamation-restore ID [--comment COMMENT]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_reclamation_restore_options}

ID
:   ID of the resource reclamation

--comment
:   Comments about the action


### Examples
{: #ibmcloud_resource_reclamation_restore_examples}

Restore a resource reclamation with ID `d9fendfwlw`:
```bash
ibmcloud resource reclamation-restore "d9fendfwlw"
```
{: codeblock}

Restore a resource reclamation with ID `d9fendfwlw`, leave a comment of `need to use for another 3 months`, and show JSON output:

```bash
ibmcloud resource reclamation-restore "d9fendfwlw" --comment "need to use for another 3 months" --output JSON
```
{: codeblock}

## ibmcloud resource reclamation-delete
{: #ibmcloud_resource_reclamation_delete}

Delete a reclaimed resource so that the resource can no longer be restored:
```bash
ibmcloud resource reclamation-delete ID [--comment COMMENT] [--f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_resource_reclamation_delete_options}

ID
:   ID of the resource reclamation

--comment
:   Comments about the action

-f, --force
:   Force deletion without confirmation


### Examples
{: #ibmcloud_resource_reclamation_delete_examples}

Delete a resource reclamation with ID `d9fendfwlw`:
```bash
ibmcloud resource reclamation-delete "d9fendfwlw"
```
{: codeblock}

Delete a resource reclamation with ID `d9fendfwlw` and leave a comment of `no longer needed` without confirmation:

```bash
ibmcloud resource reclamation-delete "d9fendfwlw" --comment "no longer needed" -f
```
{: codeblock}
