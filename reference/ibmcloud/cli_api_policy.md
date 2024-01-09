---

copyright:
  years: 2018, 2024
lastupdated: "2024-01-08"

keywords: iam, iam access, api keys, service ids, access groups, trusted profiles, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli, cli private endpoints

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing IAM access, API keys, trusted profiles, service IDs, and access groups (ibmcloud iam)
{: #ibmcloud_commands_iam}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage API keys, service IDs, access groups, and authorization policies for users, services, trusted profiles, and access groups.
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

List all service IDs:
```bash
ibmcloud iam service-ids [--uuid]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_ids_options}

--uuid
:   Show UUID of service IDs only.

### Examples
{: #ibmcloud_iam_service_ids_examples}

List UUID of all service IDs under current account:
```bash
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Display details of a service ID:
```bash
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

### Command options
{: #ibmcloud_iam_service_id_options}

NAME (required)
:   Name of the service, exclusive with UUID.

UUID (required)
:   UUID of the service, exclusive with NAME.

--uuid
:   Display the UUID of the service ID.

### Examples
{: #ibmcloud_iam_service_id_examples}

Show details of service ID `sample-test`:
```bash
ibmcloud iam service-id sample-test
```
{: codeblock}

Show details of service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Create a service ID:
```bash
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_id_create_options}

NAME (required)
:   Name of the service.

-d, --description
:   Description of the service ID.

--lock
:   Lock the service ID during creation.

### Examples
{: #ibmcloud_iam_service_id_create_examples}

Create a service ID with service name `sample-test` and description `hello, world!`:
```bash
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

Create a locked service ID with service name `sample-test` and description `hello, world!`:
```bash
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

Update a service ID:
```bash
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_id_update_options}

NAME (required)
:   Name of the service, exclusive with UUID.

UUID (required)
:   UUID of the service, exclusive with NAME.

-n, --name
:   New name of the service.

-d, --description
:   New description of the service.

-f, --force
:   Update without confirmation.

### Examples
{: #ibmcloud_iam_service_id_update_examples}

Rename service ID `sample-test` to `sample-test-2` without confirmation:
```bash
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

Update description of service `sample-test`:
```bash
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

Rename service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` to `sample-test-3` with new description:
```bash
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Delete a service ID:
```bash
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_id_delete_options}

NAME (required)
:   Name of the service, exclusive with UUID.

UUID (required)
:   UUID of the service, exclusive with NAME.

-f, --force
:   Delete without confirmation.

### Examples
{: #ibmcloud_iam_service_id_delete_examples}

Delete service ID `sample-teset` without confirmation:
```bash
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

Delete service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Lock a service ID:
```bash
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_id_lock_options}

NAME (required)
:   Name of the service, exclusive with UUID.

UUID (required)
:   UUID of the service, exclusive with NAME.

-f, --force
:   Lock without confirmation.

### Examples
{: #ibmcloud_iam_service_id_lock_examples}

Lock service ID `sample-teset` without confirmation:
```bash
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

Lock service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Unlock a service ID:
```bash
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_id_unlock_options}

NAME (required)
:   Name of the service, exclusive with UUID.

UUID (required)
:   UUID of the service, exclusive with NAME.

-f, --force
:   Unlock without confirmation.

### Examples
{: #ibmcloud_iam_service_id_unlock_examples}

Unlock service ID `sample-teset` without confirmation:
```bash
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

Unlock service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

List all {{site.data.keyword.cloud_notm}} platform API keys:
```bash
ibmcloud iam api-keys [--uuid]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_api_keys_options}

--uuid
:   Show UUID of the API key.

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Create an {{site.data.keyword.cloud_notm}} platform API key:
```bash
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```
{: codeblock}

Using the {{site.data.keyword.cloud_notm}} CLI login with an API Key does not work with the legacy SL API Key that is found on `control.softlayer.com` option. An upgraded {{site.data.keyword.cloud_notm}} Account where Infrastructure is managed through [cloud.ibm.com](https://cloud.ibm.com/registration){: external} is required for the {{site.data.keyword.cloud_notm}} CLI login with an API Key.
{: note}

### Command options
{: #ibmcloud_iam_api_key_create_options}

NAME (required)
:   Name of the API key to be created.

-d *DESCRIPTION* (optional)
:   Description of the API key.

--file *FILE*
:   Save API key information to the specified file.

--lock
:   Lock the API key when it is created.

### Examples
{: #ibmcloud_iam_api_key_create_examples}

Create an API key and save to a file:
```bash
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

Create a locked API key with name "test-key":
```bash
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Update a {{site.data.keyword.cloud_notm}} platform API key:
```bash
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_api_key_update_options}

NAME (required)
:   The old name of the API key to be updated, exclusive with UUID.

UUID (required)
:   The UUID of the API key to be updated, exclusive with NAME.

-n *NAME* (optional)
:   The new name of the API key.

-d *DESCRIPTION* (optional)
:   The new description of the API key.

### Examples
{: #ibmcloud_iam_api_key_update_examples}

Update the description of an API key:
```bash
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

The `iam-identity.apikey.manage` privilege is required for the account when the NAME and UUID command options are used. For more information, see [Managing user API keys](/docs/account?topic=account-userapikey&interface=ui#manage-user-keys) and [IAM Identity Service](/docs/account?topic=account-iam-service-roles-actions#iam-identity-roles).
{: note}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

Delete a {{site.data.keyword.cloud_notm}} platform API key:
```bash
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_api_key_delete_options}

NAME (required)
:   Name of the API key to be deleted, exclusive with UUID.

UUID (required)
:   UUID of the API key to be deleted, exclusive with NAME.

-f, --force
:   Force deletion without confirmation.

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

Lock a platform API key:
```bash
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_api_key_lock_options}

NAME (required)
:   Name of the API key to be locked, exclusive with UUID.

UUID (required)
:   UUID of the API key to be locked, exclusive with NAME.

-f, --force
:   Force lock without confirmation.

### Examples
{: #ibmcloud_iam_api_key_lock_examples}

Lock API key test-api-key:
```bash
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

Lock API key with given UUID without confirmation:
```bash
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Unlock a platform API key:
```bash
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_api_key_unlock_options}

NAME (required)
:   Name of the API key to be unlocked, exclusive with UUID.

UUID (required)
:   UUID of the API key to be unlocked, exclusive with NAME.

-f, --force
:   Unlock an API key without confirmation.

### Examples
{: #ibmcloud_iam_api_key_unlock_examples}

Unlock API key test-api-key:
```bash
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

Unlock API key with given UUID without confirmation:
```bash
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

List all API keys of a service:
```bash
ibmcloud iam service-api-keys ([-a, --all], SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_keys_options}

-a, --all
:   Display all API keys that are associated with all services.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-f, --force
:   Display service API keys without confirmation.

### Examples
{: #ibmcloud_iam_service_api_keys_examples}

List all API keys of service `sample-service`:
```bash
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

List details of a service API key:
```bash
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_options}

APIKEY_NAME (required)
:   Name of the API key, exclusive with APIKEY_UUID.

APIKEY_UUID (required)
:   UUID of the API key, exclusive with APIKEY_NAME.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

--uuid
:   Display the UUID of service API key.

-f, --force
:   Display service API key without confirmation.


### Examples
{: #ibmcloud_iam_service_api_key_examples}

Show details of service API key `sample-key` of service `sample-service`:
```bash
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Create a service API key:
```bash
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_create_options}

NAME (required)
:   Name of the service ID or newly created service API key.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-d, --description
:   Description of the API key.

--file FILE
:   Save API key information to the specified file.

-f, --force
:   Force creation without confirmation.

### Examples
{: #ibmcloud_iam_service_api_key_create_examples}

Create a service API key `sample-key` for service `sample-service` without confirmation:
```bash
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Update a service API key:
```bash
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_update_options}

APIKEY_NAME (required)
:   Name of the API key, exclusive with APIKEY_UUID.

APIKEY_UUID (required)
:   UUID of the API key, exclusive with APIKEY_NAME.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-n, --name
:   New name of the service API key.

-d, --description
:   New description of the service API key.

-f, --force
:   Update without confirmation.

### Examples
{: #ibmcloud_iam_service_api_key_update_examples}

Rename service API key `sample-key` to `new-sample-key`:
```bash
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Delete a service API key:
```bash
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_delete_options}

APIKEY_NAME (required)
:   Name of the API key, exclusive with APIKEY_UUID.

APIKEY_UUID (required)
:   UUID of the API key, exclusive with APIKEY_NAME.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-f, --force
:   Delete without confirmation.

### Examples
{: #ibmcloud_iam_service_api_key_delete_examples}

Delete service API key `sample-key` of service ID `sample-service`:
```bash
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Lock a service API key:
```bash
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_lock_options}

APIKEY_NAME (required)
:   Name of the API key, exclusive with APIKEY_UUID.

APIKEY_UUID (required)
:   UUID of the API key, exclusive with APIKEY_NAME.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-f, --force
:   Lock without confirmation.

### Examples
{: #ibmcloud_iam_service_api_key_lock_examples}

Lock service API key `sample-key` of service ID `sample-service`:
```bash
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Unlock a service API key:
```bash
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_api_key_unlock_options}

APIKEY_NAME (required)
:   Name of the API key, exclusive with APIKEY_UUID.

APIKEY_UUID (required)
:   UUID of the API key, exclusive with APIKEY_NAME.

SERVICE_ID_NAME (required)
:   Name of the service ID, exclusive with SERVICE_ID_UUID.

SERVICE_ID_UUID (required)
:   UUID of the service ID, exclusive with SERVICE_ID_NAME.

-f, --force
:   Unlock without confirmation.

### Examples
{: #ibmcloud_iam_service_api_key_unlock_examples}

Unlock service API key `sample-key` of service ID `sample-service`:
```bash
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

List all access policies for a specified user:
```bash
ibmcloud iam user-policies USER_NAME
```
{: codeblock}

### Command options
{: #ibmcloud_iam_user_policies_options}

USER_NAME (required)
:   User name to whom the policies belong.

### Examples
{: #ibmcloud_iam_user_policies_examples}

List policies of user `name@example.com`:
```bash
ibmcloud iam user-policies name@example.com
```
{: codeblock}

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Display details of an access policy for a user:
```bash
ibmcloud iam user-policy USER_NAME POLICY_ID [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_user_policy_options}

USER_NAME (required)
:   User name to whom the policy belongs.

POLICY_ID (required)
:   ID of the policy.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_user_policy_examples}

List policy `0bb730daa` of user `name@example.com`:
```bash
ibmcloud iam user-policy name@example.com 0bb730daa
```
{: codeblock}

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Create an access policy for the specified user in the current account:
```bash
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_user_policy_create_options}

USER_NAME (required)
:   User name to whom the policy belongs to.

--file *FILE* (optional)
:   JSON file of policy definition. You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).

--roles *ROLE_NAME1,ROLE_NAME2...* (optional)
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.

--service-name *SERVICE_NAME* (optional)
:   Service name of the policy definition. This option is exclusive with the `--file` option.

--service-instance *SERVICE_INSTANCE_GUID* (optional)
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

--region *REGION* (optional)
:   Region of the policy definition. This option is exclusive with the `--file` option.

--resource-type *RESOURCE_TYPE* (optional)
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

--resource *RESOURCE* (optional)
:   Resource of the policy definition. This option is exclusive with the `--file` option.

--resource-group-name *RESOURCE_GROUP_NAME* (optional)
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-id` options.

--resource-group-id *RESOURCE_GROUP_ID* (optional)
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-name` options.

--account-management (optional)
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of `name=value,name=value....`

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.


### Examples
{: #ibmcloud_iam_user_policy_create_examples}

Create user policy for user `name@example.com` from policy JSON file `policy.json`:
```bash
ibmcloud iam user-policy-create name@example.com --file @policy.json
```
{: codeblock}

Give `name@example.com` `Administrator` role for all instances of `sample-service` service:
```bash
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```
{: codeblock}

Give `name@example.com` `Editor` role and a custom role `Responder` for all instances of `sample-service` service:
```bash
ibmcloud iam user-policy-create name@example.com --roles Editor,Responder --service-name sample-service
```
{: codeblock}

Give `name@example.com` `Editor` role for resource `key123` of sample service instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```bash
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Give `name@example.com` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `name@example.com` `Viewer` role for the members of resource group `sample-resource-group`:
```bash
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Give `name@example.com` `Viewer` role for the members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `name@example.com` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```bash
ibmcloud iam user-policy-create name@example.com --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Update an access policy for the specified user in the current account:
```bash
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_user_policy_update_options}

USER_NAME (required)
:   User name to whom the policy belongs to.

POLICY_ID (required)
:   ID of the policy to update.
--file *FILE* (optional)
:   JSON file of policy definition.

--roles *ROLE_NAME1,ROLE_NAME2...* (optional)
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME` option. This option is exclusive with the `--file` option.

--service-name *SERVICE_NAME* (optional)
:   Service name of the policy definition. This option is exclusive with the `--file` option.

--service-instance *SERVICE_INSTANCE_GUID* (optional)
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

--region *REGION* (optional)
:   Region of the policy definition. This option is exclusive with the `--file` option.

--resource-type *RESOURCE_TYPE* (optional)
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

--resource *RESOURCE* (optional)
:   Resource of the policy definition. This option is exclusive with the `--file` option.

--resource-group-name *RESOURCE_GROUP_NAME* (optional)
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-id` options.

--resource-group-id *RESOURCE_GROUP_ID* (optional)
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-name` options.

--account-management (optional)
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of 'name=value,name=value....'

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_user_policy_update_examples}

Update user policy with the one in JSON file：
```bash
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```
{: codeblock}

Update user policy to give `name@example.com` `Administrator` role for all instances of `sample-service` service：
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```
{: codeblock}

Update user policy to give `name@example.com` `Editor` role and a custom role `Responder` for all instances of `sample-service` service：
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Editor,Responder --service-name sample-service
```
{: codeblock}

Update user policy to give `name@example.com` `Editor` role for resource `key123` of sample service instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```bash
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Update user policy to give `name@example.com` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for members of resource group `sample-resource-group`:
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for service `is` resources with attribute `instance` equal to `*`:
```bash
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Delete an access policy for the specified user:
```bash
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_user_policy_delete_options}

-f, --force
:   Delete user policy without confirmation.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_user_policy_delete_examples}

Delete policies `user-policy-id` of user `name@example.com`:
```bash
ibmcloud iam user-policy-delete name@example.com user-policy-id
```
{: codeblock}

Delete policies `user-policy-id` of user `name@example.com` without confirmation:
```bash
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```
{: codeblock}

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

List all access policies for a specified service ID:
```bash
ibmcloud iam service-policies SERVICE_ID [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```

### Command options
{: #ibmcloud_iam_service_policies_options}

SERVICE_ID (required)
:   Name or UUID of service ID.

-f, --force (optional)
:   Display service policies without confirmation.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.


### Examples
{: #ibmcloud_iam_service_policies_examples}

List policies of service `test`:
```bash
ibmcloud iam service-policies test
```
{: codeblock}

List policies of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Display details of an access policy for a specified service ID:
```bash
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_policy_options}

SERVICE_ID (required)
:   Name or UUID of service ID.

POLICY_ID (required)
:   ID of the service policy.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force (optional)
:   Display service policy without confirmation.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_service_policy_examples}

Show policy `140798e2-8ea7db3` of service `test`:
```bash
ibmcloud iam service-policies test 140798e2-8ea7db3
```
{: codeblock}

Show policy `140798e2-8ea7db3` of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```
{: codeblock}

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Create an access policy and assign it to a service ID:
```bash
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_policy_create_options}

SERVICE_ID (required)
:   Name or UUID of service ID.

--file
:   JSON file of policy definition. This option is exclusive with the `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `--resource-group-name` and `--resource-group-id` options.  You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).

-r, --roles
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME` option. This option is exclusive with the `--file` option.

--service-name
:   Service name of the policy definition. This option is exclusive with the `--file` option.

--service-instance *SERVICE_INSTANCE_GUID*
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

-region
:   Region of the policy definition. This option is exclusive with the `--file` option.

--resource-type
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

--resource
:   Resource of the policy definition. This option is exclusive with the `--file` option.

--resource-group-name
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` options.

--resource-group-id
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` options.

--account-management (optional)
:   Give access to all account management services.

--account-management (optional)
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of 'name=value,name=value....'

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

-f, --force
:   Create service policy without confirmation.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_service_policy_create_examples}

Create service policy from JSON file for service `test`:
```bash
ibmcloud iam service-policy-create test --file @policy.json
```
{: codeblock}

Create service policy from JSON file for service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```
{: codeblock}

Grant service `test` the `Administrator` role for all account management services:
```bash
ibmcloud iam service-policy-create test --roles Administrator --account-management
```
{: codeblock}

Grant service `test` the `Viewer` role for all resources in account:
```bash
ibmcloud iam service-policy-create test --roles Viewer
```
{: codeblock}

Grant service `test` the `Viewer` role and a custom role `Responder` for all `sample` service instances in account:
```bash
ibmcloud iam service-policy-create test --roles Viewer,Responder --service-name sample
```
{: codeblock}

Give service `test` the `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```bash
ibmcloud iam service-policy-create sample-service --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Update an access policy for a service ID:
```bash
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_policy_update_options}

SERVICE_ID (required)
:   Name or UUID of service ID.

POLICY_ID (required)
:   ID of the service policy.

--file
:   JSON file of policy definition. This option is exclusive with the `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `resource-group-name`, and `resource-group-id` options.

-r, --roles
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file`.

-service-name
:   Service name of the policy definition. This option is exclusive with the `--file` option.

-service-instance *SERVICE_INSTANCE_GUID*
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

-region
:   Region of the policy definition. This option is exclusive with the `--file` option.

-resource-type
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

-resource
:   Resource of the policy definition. This option is exclusive with the `--file` option.

--resource-group-name
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` options.

--resource-group-id
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` options.

--account-management (optional)
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of 'name=value,name=value....'

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

-f, --force
:   Update service policy without confirmation.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_service_policy_update_examples}

Update service policy `140798e2-8ea7db3` from JSON file for service `test`:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
{: codeblock}

Update service policy `140798e2-8ea7db3` from JSON file for service `test`:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Administrator` role for all account management services:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role for all resources in account:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role and a custom role `Responder` for all `sample` service instances in account:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer,Responder --service-name sample
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```bash
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Delete an access policy for a service ID:
```bash
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_service_policy_delete_options}

SERVICE_ID (required)
:   Name or UUID of service ID.

POLICY_ID (required)
:   ID of the service policy.

-f, --force
:   Delete without confirmation.

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_service_policy_delete_examples}

Delete policy `140798e2-8ea7db3` of service `test`:
```bash
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
{: codeblock}

Delete policy `140798e2-8ea7db3` of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```
{: codeblock}

## ibmcloud iam logins
{: #ibmcloud_iam_logins}

Retrieve and display recent login history:
```bash
ibmcloud iam logins
```
{: codeblock}

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Retrieve and display the OAuth tokens for the current session:
```bash
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

List platform, service-defined, and custom roles:
```bash
ibmcloud iam roles [--service SERVICE_NAME [--resource-type RESOURCE_TYPE] [--source-service SOURCE_SERVICE_NAME]] [--roles ROLE_NAME]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_roles_options}

--resource-type
:   Resource type of the service. '--service' must be set along with this option.

--roles ROLE_NAME1,ROLE_NAME2...
:   Show details of specific roles

--service SERVICE_NAME
:   Name of the service. Only list platform-defined roles if not specified.

--source-service
:   Name of the service. Only list platform-defined roles if not specified. **This option does not support private endpoints.**


### Examples
{: #ibmcloud_iam_roles_examples}

List platform default access roles and custom roles:
```bash
ibmcloud iam roles
```
{: codeblock}

List details of platform default access policy roles `Administrator`, `Operator`:
```bash
ibmcloud iam roles --roles Administrator,Operator
```
{: codeblock}

List details of access policy role `Writer` of `cloud-object-storage` service in JSON format:
```bash
ibmcloud iam roles --service cloud-object-storage --roles Writer --output JSON
```
{: codeblock}

List access policy roles for all account management service in JSON:
```bash
ibmcloud iam roles --service allacctmgmtroles --output JSON
```
{: codeblock}

List details of resource group access policy role `Administrator`:
```bash
ibmcloud iam roles --service resource-controller --roles Administrator
```
{: codeblock}

List details of access policy roles of resource type `image` of service `is`:
```bash
ibmcloud iam roles --service is --resource-type image
```
{: codeblock}

List authorization roles for source service `cloud-object-storage` and target service `kms`:
```bash
ibmcloud iam roles --source-service cloud-object-storage --service kms
```
{: codeblock}

## ibmcloud iam role-create
{: #ibmcloud_iam_role_create}

Create a role:
```bash
ibmcloud iam role-create ROLE_NAME --display-name DISPLAY_NAME --service-name SERVICE_NAME [-a, --actions ROLE_ACTION1 [ROLE_ACTION2...]] [-d, --description DESCRIPTION] [--output FORMAT] [-q --quiet]
```
{: codeblock}

## Command options
{: #ibmcloud_iam_role_create_options}

--display-name DISPLAY_NAME
:   The display name of the role that is shown in the console.

--service-name SERVICE_NAME
:   The name of the service.

-a, --actions ROLE_ACTION1,ROLE_ACTION2...
:   The actions of the role. For more information, see [IAM roles and actions](/docs/account?topic=account-iam-service-roles-actions).

-d, --description DESCRIPTION
:   The description of the role.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_role_create_examples}

Create a role to perform any Cloudant database action:
```bash
ibmcloud iam role-create CloudDBAdmin --display-name "Cloudant DB Administrator" --service-name cloudantnosqldb --actions cloudantnosqldb.db.any
```
{: codeblock}

Create a role for read-only access to Certificate Manager by using multiple role actions:
```bash
ibmcloud iam role-create ReadonlyCertManager --display-name "Readonly Certificate Manager" --service-name cloudcerts --actions cloudcerts.certificate-metadata.read,cloudcerts.notifications-channel.list
```
{: codeblock}

Create a role to view toolchain dashboards and return the role in JSON format:
```bash
ibmcloud iam role-create PreviewCDCI --display-name "Preview Toolchains" --service-name toolchain --actions toolchain.dashboard.view --output JSON
```
{: codeblock}

Create a role that has a description:
```bash
ibmcloud iam role-create ServiceIDCreator --display-name "Service ID Creator" --service-name iam-identity --actions iam-identity.serviceid.create --description "Can only create service keys"
 ```
{: codeblock}

## ibmcloud iam access-policies
{: #ibmcloud_iam_access_policies}

List all access policies under the current account:
```bash
ibmcloud iam access-policies [-t, --type user | service_id | access_group | trusted_profile] [--sort-by id | type | href | created_at | created_by_id | last_modified_at | last_modified_by_id | state ] [--output FORMAT] [-q, --quiet ] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policies_options}

-t, --type ACCESS_POLICY_TYPE
:   List all access policies under current account filtered by policy type. Valid options are: `user` | `service_id` | `access_group` | `trusted_profile`

--sort-by ATTRIBUTE
:   Sort the policies based on attributes. Valid options are: id | type | href | created_at | created_by_id | last_modified_at | last_modified_by_id | state. Prepend a minus (for example, `-id`, `-type`) for reverse sorting.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_access_policies_examples}

List all access policies under the current account:
```bash
ibmcloud iam access-policies
```
{: codeblock}

List all user access policies under the current account:
```bash
ibmcloud iam access-policies --type user
```
{: codeblock}

List all service ID access policies under the current account:
```bash
ibmcloud iam access-policies --type service_id
```
{: codeblock}

List all access group access policies under the current account:
```bash
ibmcloud iam access-policies --type access_group
```
{: codeblock}

List all trusted profile access policies under the current account:
```bash
ibmcloud iam access-policies --type trusted_profile
```
{: codeblock}

List all trusted profile access policies sorted by `created_at` in ascending order under the current account:
```bash
ibmcloud iam access-policies --type trusted_profile --sort-by created_at
```
{: codeblock}

List all trusted user policies sorted by `last_modified_at` in descending order under the current account:
```bash
ibmcloud iam access-policies --type user --sort-by -last_modified_at
```
{: codeblock}

## ibmcloud iam account-policies
{: #ibmcloud_iam_account_policies}

List all account policies under current account:
```bash
ibmcloud iam account-policies [-t, --type access | auth] [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_policies_options}

-t, --type access | auth
:   List all policies under current account filtered by policy type. Valid options are: `access` | `auth`

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_account_policies_examples}

List all account policies under current account:
```bash
ibmcloud iam account-policies
```
{: codeblock}

List all authorization policies under current account. Provides the same list as `ibmcloud iam authorization-policies`:
```bash
ibmcloud iam account-policies -t auth
```
{: codeblock}

List all access policies under current account. Provides the same list as `ibmcloud iam access-policies`:
```bash
ibmcloud iam account-policies -t access
```
{: codeblock}

## ibmcloud iam access-policy-template
{: #ibmcloud_iam_access_policy_template}

Show details of an access policy template under current account:
```bash
ibmcloud iam access-policy-template (TEMPLATE_ID | TEMPLATE_NAME) [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_access_policy_template_examples}

Show access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template AccessPolicyUserTemplate
```
{: codeblock}

## ibmcloud iam access-policy-templates
{: #ibmcloud_iam_access_policy_templates}

List all access policy templates under current account:
```bash
ibmcloud iam access-policy-templates [--output FORMAT] [-q, quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_templates_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_templates_examples}

List all access policy template under current account

```bash
ibmcloud iam access-policy-templates
```
{: codeblock}

## ibmcloud iam access-policy-template-create
{: #ibmcloud_iam_access_policy_template_create}

Create an access policy template:
```bash
ibmcloud iam access-policy-template-create --file JSON_FILE
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_create_options}

--file JSON_FILE
:   JSON file of access policy template definition

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_template_create_examples}

Create an access policy template

```bash
imcloud iam access-policy-template-create --file /path/to/access_policy_template.json
```
{: codeblock}

## ibmcloud iam access-policy-template-version
{: #ibmcloud_iam_access_policy_template_version}

Get a version of an access policy template:
```bash
ibmcloud iam access-policy-template-version (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q, --quiet] [--output JSON]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_version_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_template_version_examples}

Show version `1` of access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template-version AccessPolicyUserTemplate 1
```
{: codeblock}

## ibmcloud iam access-policy-template-version-create
{: #ibmcloud_iam_access_policy_template_version_create}

Create a new version of an access policy template:
```bash
ibmcloud iam access-policy-template-version-create (TEMPLATE_ID | TEMPLATE_NAME) [--file JSON_FILE] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_version_create_options}

--file JSON_FILE
:   JSON file of access policy template definition

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_template_version_create_examples}

Create a new version for access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template-version-create AccessPolicyUserTemplate --file /path/to/access_policy_template.json
```

## ibmcloud iam access-policy-template-version-update
{: #ibmcloud_iam_access_policy_template_version_update}

Update an existing version of an access policy template:
```bash
ibmcloud iam access-policy-template-update (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION --file JSON_FILE [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_version_update_options}

--file JSON_FILE
:   JSON file of access policy template definition

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_template_version_update_examples}

Update version `1` of access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template-version-create AccessPolicyUserTemplate 1 --file /path/to/access_policy_template.json
```
{: codeblock}

## ibmcloud iam access-policy-template-version-delete
{: #ibmcloud_iam_access_policy_template_version_delete}

Delete a version of an access policy template:
```bash
ibmcloud iam access-policy-template-version-delete (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q, --quiet] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_version_delete_options}

-f, --force
:   Force deletion without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_template_version_delete_examples}

Delete version `2` of access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template-version-delete AccessPolicyUserTemplate 2
```
{: codeblock}

## ibmcloud iam access-policy-template-version-commit
{: #ibmcloud_iam_access_policy_template_version_commit}

Commit a version of an access policy template:
```bash
ibmcloud iam access-policy-template-version-commit (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_version_commit_options}

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_access_policy_template_version_commit_examples}

Commit version `1` of access policy template `AccessPolicyUserTemplate`

```bash
ibmcloud iam access-policy-template-version-commit AccessPolicyUserTemplate 1
```

## ibmcloud iam access-policy-assignment
{: #ibmcloud_iam_access_policy_assignment}

Show details of an access policy assignment:
```bash
ibmcloud iam access-policy-assignment ASSIGNMENT_ID [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_template_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_access_policy_assignment_examples}

Show access policy assignment `AccessPolicyAssignment-adee40a7f8324d6fbcd4c4a67b326eb5`

```bash
ibmcloud iam access-policy-assignment AccessPolicyAssignment-adee40a7f8324d6fbcd4c4a67b326eb5
```
{: codeblock}

## ibmcloud iam access-policy-assignments
{: #ibmcloud_iam_access_policy_assignments}

List all access policy assignments on current account:
```bash
ibmcloud iam access-policy-templates [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_policy_assignments_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_policy_assignments_examples}

List all access policy template assignments under current account

```bash
ibmcloud iam access-policy-assignments
```
{: codeblock}

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Create an authorization policy to allow a service instance access to another service instance:
```bash
ibmcloud iam authorization-policy-create { SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-service-account ACCOUNT_GUID] [--source-resource-group-id RESOURCE_GROUP_ID] [--source-resource-type RESOURCE_TYPE] [--source-resource RESOURCE] [--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--target-resource-group-id RESOURCE_GROUP_ID] [--target-resource-type RESOURCE_TYPE] [--target-resource RESOURCE] | --file JSON_FILE } [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_authorization_policy_create_options}

SOURCE_SERVICE_NAME
:   The source service that can be authorized to access. To find the service's name, run the `ibmcloud catalog service-marketplace` command.

TARGET_SERVICE_NAME
:   The target service that the source service can be authorized to access. To find the service's name, run the `ibmcloud catalog service-marketplace` command.

ROLE_NAME1,ROLE_NAME2...
:   The roles that provide access for the source service.

--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME
:   Source service instance name, mutually exclusive with `--source-service-instance-id` and `--source-service-account`. If source service instance not specified, all instances of source service will be authorized to access.

--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID
:   Source service instance ID, mutually exclusive with `--source-service-instance-name`. If not specified, all instances of the source service are authorized to access.

--source-service-account ACCOUNT_GUID
:   Account GUID of source service, mutually exclusive with `--source-service-instance-name`. Use this option if source service is from another account.

--source-resource-group-id RESOURCE_GROUP_ID
:   Source resource group ID, mutually exclusive with '--source-service-instance-id'.

--source-resource-type
:   Resource type of source service.

--source-resource
:   Resource of source service.
--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME
:   Target service instance name, mutually exclusive with `--target-service-instance-id`. If not specified, all instances of the target service are authorized to access.

--target-service-instance-id TARGET_SERVICE_INSTANCE_ID
:   Target service instance ID, mutually exclusive with `--target-service-instance-name`. If not specified, all instances of the target service are authorized to access.

--target-resource-group-id RESOURCE_GROUP_ID
:   Target resource group ID, mutually exclusive with '--target-service-instance-id'.

--target-resource-type
:   Resource type of target service.

--target-resource
:   Resource of target service.

--file FILE
:   JSON file of policy definition.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

Currently, some combination of `--source-service` and `--service` might fail under private endpoints. Use `--file` as a workaround, or you can create the policy from public endpoints or the UI console.
{: note}

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Delete an authorization policy:
```bash
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_authorization_policy_delete_options}

AUTHORIZATION_POLICY_ID
:   ID of authorization policy to be deleted.

-f, --force
:   Delete without confirmation.

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Show details of an authorization policy:
```bash
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```
{: codeblock}

### Command options
{: #ibmcloud_iam_authorization_policy_options}

AUTHORIZATION_POLICY_ID
:   ID of authorization policy to show.

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

List authorization policies under the current account:
```bash
ibmcloud iam authorization-policies
```
{: codeblock}

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

List access groups under current account:
```bash
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME | -p (PROFILE_NAME | PROFILE_ID)] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_groups_options}

-u
:   List access groups the user belongs to. This option is exclusive to '-s' and '-p'.

-s
:   List access groups the service ID belongs to. This option is exclusive to '-u' and '-p'.

-p
:   List access groups the trusted profile belongs to. This option is exclusive to '-s' and '-u'.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_groups_examples}

List all access groups:
```bash
ibmcloud iam access-groups
```
{: codeblock}

List all access groups the trusted profile `test_profile` belongs to:
```bash
ibmcloud iam access-groups -p test_profile
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Show details of an access group:
```bash
ibmcloud iam access-group GROUP_NAME [--id]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_options}

-id
:   Show the ID only.


### Examples
{: #ibmcloud_iam_access_group_examples}

Show details of access group `example_group`:
```bash
ibmcloud iam access-group example_group
```
{: codeblock}

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Create an access group:
```bash
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_create_options}

-d, --description
:   Description of access group.

### Examples
{: #ibmcloud_iam_access_group_create_examples}

Create an access group `example_group`:
```bash
ibmcloud iam access-group-create example_group -d "example access group"
```
{: codeblock}

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Update an access group:
```bash
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_update_options}

-n, --name
:   New access group name.

-d, --description
:   New description.

-f, --force
:   Force update without confirmation.

### Examples
{: #ibmcloud_iam_access_group_update_examples}

Rename access group `example_group` to `hello_world_group`:
```bash
ibmcloud iam access-group-update example_group --name "hello_world_group"
```
{: codeblock}

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Delete an access group:
```bash
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive] [-a, --all]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_delete_options}

-f, --force
:   Force deletion without confirmation.

-r, --recursive
:   Delete an access group and its members.

-a, --all
:   Force to delete access groups with the same name.

### Examples
{: #ibmcloud_iam_access_group_delete_examples}

Delete access group `example_group`:
```bash
ibmcloud iam access-group-delete example_group --force
```
{: codeblock}

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

List users in an access group:
```bash
ibmcloud iam access-group-users GROUP_NAME
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_users_examples}

List all users in access group `example_group`:
```bash
ibmcloud iam access-group-users example_group
```
{: codeblock}

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Add users to an access group:
```bash
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_user_add_examples}

Add user `name@example.com` to access group `example_group`:
```bash
ibmcloud iam access-group-user-add example_group name@example.com
```
{: codeblock}

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Remove a user from an access group:
```bash
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_user_remove_examples}

Remove user `name@example.com` from access group `example_group`:
```bash
ibmcloud iam access-group-user-remove example_group name@example.com
```
{: codeblock}

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Remove user from all access groups:
```bash
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_user_purge_options}

-f, --force
:   Delete without confirmation.


### Examples
{: #ibmcloud_iam_access_group_user_purge_examples}

Remove user `name@example.com` from all access groups:
```bash
ibmcloud iam access-group-user-purge name@example.com -f
```
{: codeblock}

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

List service IDs in an access group:
```bash
ibmcloud iam access-group-service-ids GROUP_NAME
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_service_ids_examples}

List all service IDs in access group `example_group`:
```bash
ibmcloud iam access-group-service-ids example_group
```
{: codeblock}

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Add service ID to an access group:
```bash
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_service_id_add_examples}

Add service ID `example-service` to access group `example_group`:
```bash
ibmcloud iam access-group-service-id-add example_group example-service
```
{: codeblock}

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Remove a service ID from an access group:
```bash
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```
{: codeblock}

### Examples
{: #ibmcloud_iam_access_group_service_id_remove_examples}

Remove service ID `example-service` from access group `example_group`:
```bash
ibmcloud iam access-group-service-id-remove example_group example-service
```
{: codeblock}

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Remove service ID from all access groups:
```bash
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_service_id_purge_options}

-f, --force
:   Delete without confirmation.


### Examples
{: #ibmcloud_iam_access_group_service_id_purge_examples}

Remove service ID `example-service` from all access groups:
```bash
ibmcloud iam access-group-service-id-purge example --force
```
{: codeblock}

## ibmcloud iam access-group-trusted-profiles
{: #ibmcloud_iam_access_group_trusted_profiles}

List trusted profiles of an access group:
```bash
ibmcloud iam access-group-trusted-profiles GROUP_NAME [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_trusted_profiles_options}

GROUP_NAME (required)
:   Name of the access group.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_trusted_profiles_examples}

List all trusted profiles in access group `example_group`:
```bash
ibmcloud iam access-group-trusted-profiles example_group
```
{: codeblock}

## ibmcloud iam access-group-trusted-profile-add
{: #ibmcloud_iam_access_group_trusted_profile_add}

Add trusted profile(s) to an access group:
```bash
ibmcloud iam access-group-trusted-profile-add GROUP_NAME (PROFILE_NAME | PROFILE_ID) [PROFILE_NAME2 | PROFILE_ID2...] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_trusted_profile_add_options}

GROUP_NAME (required)
:   Name of the access group.

PROFILE_NAME | PROFILE_ID (required)
:   Name(s) or ID(s) of the trusted profiles to add to the access group.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_trusted_profile_add_examples}

Add trusted profile `my-profile` to access group `example_group`:
```bash
ibmcloud iam access-group-trusted-profile-add example_group my-profile
```
{: codeblock}

## ibmcloud iam access-group-trusted-profile-remove
{: #ibmcloud_iam_access_group_trusted_profile_remove}

Remove a trusted profile from an access group:
```bash
ibmcloud iam access-group-trusted-profile-remove GROUP_NAME (PROFILE_NAME | PROFILE_ID) [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_trusted_profile_remove_options}

GROUP_NAME (required)
:   Name of the access group.

PROFILE_NAME | PROFILE_ID (required)
:   Name or ID of the trusted profile to remove from the access group.

-f, --force
:   Remove without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_trusted_profile_remove_examples}

Remove trusted profile `my-profile` from access group `example_group`:
```bash
ibmcloud iam access-group-trusted-profile-remove example_group my-profile
```
{: codeblock}

## ibmcloud iam access-group-trusted-profile-purge
{: #ibmcloud_iam_access_group_trusted_profile_purge}

Remove a trusted profile from all access groups:
```bash
ibmcloud iam access-group-trusted-profile-purge (PROFILE_NAME | PROFILE_ID) [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_trusted_profile_purge_options}


PROFILE_NAME | PROFILE_ID (required)
:   Name or ID of the trusted profile to remove from all access groups.

-f, --force
:   Purge without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_trusted_profile_purge_examples}

Remove trusted profile `my-profile` from all access groups:
```bash
ibmcloud iam access-group-trusted-profile-purge my-profile
```
{: codeblock}

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

List policies of an access group:
```bash
ibmcloud iam access-group-policies GROUP_NAME [--output FORMAT] [-q, --quiet] [--api-version v1 |v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_policies_options}

GROUP_NAME
:   Name of the access group.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_access_group_policies_examples}

List all policies of access group `example_group`:
```bash
ibmcloud iam access-group-policies example_group
```
{: codeblock}

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Show details of an access group policy:
```bash
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_policy_options}

GROUP_NAME
:   Name of the access group.

POLICY_ID
:   The ID of the policy to retrieve.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_access_group_policy_examples}

Show details of policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:
```bash
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```
{: codeblock}

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Create an access group policy:
```bash
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--tags name1:value1,name2:value2...] [--account-management] [--attributes name=value,name=value...]}} [--output FORMAT] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_policy_create_options}

--file
:   JSON file of policy definition. You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).

-roles
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.

-service-name
:   Service name of the policy definition. This option is exclusive with the `--file` option.

-service-instance *SERVICE_INSTANCE_GUID*
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

-region
:   Region of the policy definition. This option is exclusive with the `--file` option.

-resource-type
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

-resource
:   Resource of the policy definition. This option is exclusive with the `--file` option.

-resource-group-name
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` option.

-resource-group-id
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` option.

-tags
:   Access tags of the resource. Use tags to organize, track usage costs, or manage access to your resources. For more information on tags, see [Working with tags](/docs/account?topic=account-tag&interface=cli).

--account-management
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of 'name=value,name=value....'

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_access_group_policy_create_examples}

Create an access group policy from a JSON file:
```bash
ibmcloud iam access-group-policy-create example_group -f @policy.json
```
{: codeblock}

Give `example_group` `Administrator` role for all `sample-service` resources:
```bash
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```
{: codeblock}

Give `example_group` `Editor` role and a custom role `Responder` for all instances of `sample-service` in `us-south` region:
```bash
ibmcloud iam access-group-policy-create example_group --roles Editor,Responder --service-name sample-service --region us-south
```
{: codeblock}

Give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```bash
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `example_group` `Viewer` role for the members of resource group `sample-resource-group`:
```bash
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Give `example_group` `Viewer` role for the members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `example_group` `Administrator` role for all account management services:
```bash
ibmcloud iam access-group-policy-create example_group --roles Administrator --account-management
```
{: codeblock}

Give `example_group` `Viewer` role for all resources in account:
```bash
ibmcloud iam access-group-policy-create example_group --roles Viewer
```
{: codeblock}

Give `example_group` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```bash
ibmcloud iam access-group-policy-create example_group --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

Create access tags for the resource:
```bash
ibmcloud iam access-group-policy-create --tags env:dev,env:test
```
{: codeblock}

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Update an access group policy:
```bash
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [--api-version v1| v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_policy_update_options}

--file
:   JSON file of policy definitions.

--roles
:   Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.

-service-name
:   Service name of the policy definition. This option is exclusive with the `--file` option.

-service-instance *SERVICE_INSTANCE_GUID*
:   GUID of service instance of the policy definition. This option is exclusive with the `--file` option.

-region
:   Region of the policy definition. This option is exclusive with the `--file` option.

-resource-type
:   Resource type of the policy definition. This option is exclusive with the `--file` option.

-resource
:   Resource of the policy definition. This option is exclusive with the `--file` option.

-resource-group-name
:   Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` option.

-resource-group-id
:   ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` option.

--account-management (optional)
:   Give access to all account management services.

--attributes *name=value,name=value...*
:   Set resource attributes in the form of 'name=value,name=value....'

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_access_group_policy_update_examples}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` with the one in policy JSON file:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Administrator` role for all `sample-service` resources:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Editor` role and a custom role `Responder` for all instances of `sample-service` in `us-south` region:
```bash
ibmcloud iam access-group-policy-update example_group --roles Editor,Responder --service-name sample-service --region us-south
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```bash
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for members of resource group `sample-resource-group`:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```bash
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Administrator` role for all account management services:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --account-management
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for all resources in account:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```bash
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Delete an access group policy:
```bash
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force] [-q, --quiet] [--api-version v1 |v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_policy_delete_options}

--api-version
:   Version of the access policy API.

-f, --force
:   Force deletion without confirmation.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_access_group_policy_delete_examples}

Delete policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:
```bash
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
{: codeblock}

## ibmcloud iam access-group-template-create
{: #ibmcloud_iam_access_group_template_create}

Create an access group template
```bash
ibmcloud iam access-group-template-create (TEMPLATE_NAME --access-group-name ACCESS_GROUP_NAME [-d, --description DESCRIPTION] | --file JSON_FILE) [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_create_options}

--access-group-name NAME
:   Access group name to create for the template

-d, --description DESCRIPTION
:   Description of the template

--file FILE
:   Description of the template

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_access_group_template_create_examples}

Create an access group template with specified name and access group name
```bash
ibmcloud iam access-group-template-create example-template-name --access-group-name example-access-group -d example-description
```
Create an access group template using a JSON file
```bash
ibmcloud iam access-group-template-create --file JSON_FILE
```
{: codeblock}

## ibmcloud iam access-group-template
{: #ibmcloud-iam-access-group-template}

Show details of an access group template
```bash
ibmcloud iam access-group-template (TEMPLATE_ID | TEMPLATE_NAME) [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_examples}

Show details of an access group template in JSON format
```bash
ibmcloud iam access-group-template --output JSON
```
{: codeblock}

## ibmcloud iam access-group-template-version
{: #ibmcloud_iam_access_group_template_version}

Show details of a specified version of an access group template
```bash
ibmcloud iam access-group-template-version (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_version_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_version_examples}

Show details of a specified version of an access group template in JSON format
```bash
ibmcloud iam access-group-template-version example-template-name 1 --output JSON
```
{: codeblock}

## ibmcloud iam access-group-template-version-commit
{: #ibmcloud_iam_access_group_template_version_commit}

Commit an access group template version
```bash
ibmcloud iam access-group-template-version-commit TEMPLATE_ID TEMPLATE_VERSION
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_version_commit_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: ##ibmcloud_iam_access_group_template_version_commit_examples}

Commit a specified version of an access group template
```bash
ibmcloud iam access-group-template-version-commit example-template-id 1
```
{: codeblock}

## ibmcloud iam access-group-template-version-create
{: #ibmcloud_iam_access_group_template_version_create}

Create an access group template version
```bash
ibmcloud iam access-group-template-version-create TEMPLATE_ID --file JSON_FILE
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_version_create_options}

--file FILE
:   Description of the template

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_version_create_examples}

Create a new version of an access group template
```bash
ibmcloud iam access-group-template-version-create example-template-id --file JSON_FILE
```
{: codeblock}

## ibmcloud iam access-group-template-version-delete
{: #ibmcloud_iam_access_group_template_version_delete}

Delete an access group template version
```bash
ibmcloud iam access-group-template-version-delete TEMPLATE_ID TEMPLATE_VERSION
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_version_delete_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_version_delete_examples}

Delete a specified version of an access group template
```bash
ibmcloud iam access-group-template-version-delete example-template-id 1
```
{: codeblock}

## ibmcloud iam access-group-template-version-update
{: #ibmcloud_iam_access_group_template_version_update}

Update an existing version of access group template version
```bash
ibmcloud iam access-group-template-version-update (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION --file JSON_FILE [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_version_update_options}

--file FILE
:   Description of the template

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_version_update_examples}

Update a specified version of an access group template with a JSON file
```bash
ibmcloud iam access-group-template-version-update example-template-name 1 --file JSON_FILE
```
{: codeblock}

## ibmcloud iam access-group-template-versions
{: #ibmcloud_iam_access_group_template_versions}

List the versions of an access group template
```bash
ibmcloud iam access-group-template-versions (TEMPLATE_ID | TEMPLATE_NAME) [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_template_versions_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_template_versions_examples}

List all versions of an access group template
```bash
ibmcloud iam access-group-template-versions example-template-name
```
{: codeblock}

## ibmcloud iam access-group-templates
{: #ibmcloud_iam_access_group_templates}

List all access group templates under current account
```bash
ibmcloud iam access-group-templates [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_templates_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_templates_examples}

List all access group templates under current account in JSON format
```bash
ibmcloud iam access-group-template-versions example-template-name --output JSON
```
{: codeblock}

## ibmcloud iam access-group-assignment
{: #ibmcloud_iam_access_group_assignment}

Show details of an access group assignment
```bash
ibmcloud iam access-group-assignment [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_assignment_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_assignment_examples}

Show details of an access group assignment in JSON format
```bash
ibmcloud iam access-group-assignments --output JSON
```
{: codeblock}

## ibmcloud iam access-group-assignment-create
{: #ibmcloud_iam_access_group_assignment_create}

Create an access group assignment
```bash
ibmcloud iam access-group-assignment-create TEMPLATE_ID TEMPLATE_VERSION --target-type TYPE --target TARGET
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_assignment_create_options}

--target value
:   ID of the entity targeted
--target-type value
:   Type of entity targeted
-q, --quiet
:   Suppress verbose output

### Examples
{: #ibmcloud_iam_access_group_assignment_create_examples}

Show details of an access group assignment in JSON format
```bash
ibmcloud iam access-group-assignment-create example-template-id 1 --target-type Account --target example-account-id
```
{: codeblock}

## ibmcloud iam access-group-assignment-delete
{: #ibmcloud_iam_access_group_assignment_delete}

Delete an access group assignment
```bash
ibmcloud iam access-group-assignment-delete ASSIGNMENT_ID
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_assignment_delete_options}

-q, --quiet
:   Suppress verbose output

### Examples
{: #ibmcloud_iam_access_group_assignment_delete_examples}

Delete a specified access group assignment
```bash
ibmcloud iam access-group-assignment-delete example-assignment-id
```
{: codeblock}

## ibmcloud iam access-group-assignment-update
{: #ibmcloud_iam_access_group_assignment_update}

Update an access group assignment
```bash
ibmcloud iam access-group-assignment-update ASSIGNMENT_ID
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_assignment_update_options}

-q, --quiet
:   Suppress verbose output

### Examples
{: #ibmcloud_iam_access_group_assignment_update_examples}

Update a specified access group assignment
```bash
ibmcloud iam access-group-assignment-update example-assignment-id
```
{: codeblock}

## ibmcloud iam access-group-assignments
{: #ibmcloud_iam_access_group_assignments}

Get all access group assignments in current account
```bash
ibmcloud iam access-group-assignments [-q, --quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_access_group_assignments_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_access_group_assignments_examples}

List all access group assignments under current account in JSON format
```bash
ibmcloud iam access-group-assignments --output JSON
```
{: codeblock}

## ibmcloud iam trusted-profile-create
{: #ibmcloud_iam_trusted_profile_create}

Create a trusted profile:
```bash
ibmcloud iam trusted-profile-create NAME [-d, --description DESCRIPTION] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_create_options}

NAME (required)
:   Name of the new profile.

-d, --description DESCRIPTION
:   Description of the profile.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_create_examples}

Create trusted profile with name `sample-test` and description "sample trusted profile":
```bash
ibmcloud iam trusted-profile-create sample-test -d "sample trusted profile"
```
{: codeblock}

## ibmcloud iam trusted-profile
{: #ibmcloud_iam_trusted_profile}

Get a trusted profile by name or ID:
```bash
ibmcloud iam trusted-profile NAME|ID [--id | --output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_options}

NAME|ID (required)
:   Name or ID of the profile.

--id
:   Show ID of the profile only.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_examples}

Retrieve trusted profile with name `sample-test`:
```bash
ibmcloud iam trusted-profile sample-test
```
{: codeblock}

Retrieve trusted profile with profile ID `Profile-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```bash
ibmcloud iam trusted-profile Profile-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam trusted-profiles
{: #ibmcloud_iam_trusted_profiles}

List trusted profiles under current account
```bash
ibmcloud iam trusted-profiles [--id | --output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profiles_options}

--id
:   Show ID of profiles only.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profiles_examples}

List ID of all trusted profiles under current account:
```bash
ibmcloud iam trusted-profiles --id
```
{: codeblock}

## ibmcloud iam trusted-profile-update
{: #ibmcloud_iam_trusted_profile_update}

Update a trusted profile
```bash
ibmcloud iam trusted-profile-update NAME|ID [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_update_options}

NAME|ID (required)
:   Name or ID of the profile to update.

-n, --name NEW_NAME
:   New name of the trusted profile.

-d, --description NEW_DESCRIPTION
:   New description of the profile. Providing an empty description will clear the description of the profile.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_update_examples}

Update trusted profile with name `sample-test` to new name of `test`:
```bash
ibmcloud iam trusted-profile-update sample-test -n test
```
{: codeblock}

Update trusted profile `sample-test` with new description of `testing trusted profile update`:
```bash
ibmcloud iam trusted-profile-update sample-test -d "testing trusted profile update"
```
{: codeblock}

## ibmcloud iam trusted-profile-delete
{: #ibmcloud_iam_trusted_profile_delete}

Delete a trusted profile
```bash
ibmcloud iam trusted-profile-delete NAME|ID [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_delete_options}

NAME|ID (required)
:   Name or ID of the profile to delete.

-f, --force
:   Delete a trusted profile without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_delete_examples}

Delete trusted profile with name `sample-test`:
```bash
ibmcloud iam trusted-profile-delete sample-test
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-create
{: #ibmcloud_iam_trusted_profile_policy_create}

Create an access policy and assign it to a trusted profile
```bash
ibmcloud iam trusted-profile-policy-create (NAME|ID) {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--tags name1:value1,name2:value2...] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_policy_create_options}

NAME|ID (required)
:   Name or ID of the profile to assign the new policy to

--account-management
:   Give access to all account management services.

--api-version
:   Version of the access policy API.

--attributes name=value,name-value...
:   Set resource attributes in the form of 'name=value,name=value....'

--file JSON_FILE
:   JSON file of policy definition.

-f, --force
:   Force failure if multiple profiles are found.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

--region REGION
:   Region of the policy definition. This option is exclusive with '--file'. For supported regions, run 'ibmcloud regions'.

--resource RESOURCE
:   Resource of the policy definition. This option is exclusive with '--file'.

--resource-group-id RESOURCE_GROUP_ID
:   ID of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-name'.

--resource-group-name RESOURCE_GROUP_NAME
:   Name of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-id'.

--resource-type RESOURCE_TYPE
:   Resource type of the policy definition. This option is exclusive with '--file'.

--roles ROLE_NAME1,ROLE_NAME2...
:   Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.

-q, --quiet
:   Suppress verbose output.

--service-instance SERVICE_INSTANCE_GUID
:   GUID of service instance of the policy definition. This option is exclusive with '--file'.

--service-name SERVICE_NAME
:   Service name of the policy definition. This option is exclusive with '--file'.

--tags name1:value1,name2:value2...
:   Access tags of the resource.

### Examples
{: #ibmcloud_iam_trusted_profile_policy_create_examples}

Create a trusted profile policy for `my-profile` from a JSON file:
```bash
iam trusted-profile-policy-create my-profile --file policy.json
```
{: codeblock}

Give `my-profile` Viewer role for the members of resource group `sample-resource-group`:
```bash
iam trusted-profile-policy-create my-profile --roles Viewer --resource-group-id sample-resource-group
```
{: codeblock}

Give `my-profile` Viewer role for all resources in account:
```bash
iam trusted-profile-policy-create my-profile --roles Viewer
```
{: codeblock}

## ibmcloud iam trusted-profile-policy
{: #ibmcloud_iam_trusted_profile_policy}

Display details of an access policy for a specified trusted profile
```bash
ibmcloud iam trusted-profile-policy (NAME|ID) POLICY_ID [--output FORMAT] [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_policy_options}

NAME|ID (required)
:   Name or ID of the profile.

POLICY_ID (required)
:   The ID of the policy to retrieve.

-f, --force
:   Force failure if multiple profiles are found.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_trusted_profile_policy_examples}

Get policy `bdf62c30-35dd-4852-bcb8-2f0dd3929701` of trusted profile `my-profile`:
```bash
ibmcloud iam trusted-profile-policy my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701
```
{: codeblock}

## ibmcloud iam trusted-profile-policies
{: #ibmcloud_iam_trusted_profile_policies}

List all access policies for a specified trusted profile
```bash
ibmcloud iam trusted-profile-policies (NAME|ID) [--output FORMAT] [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_policies_options}

NAME|ID (required)
:   Name or ID of the profile.

-f, --force
:   Force failure if multiple profiles are found.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_trusted_profile_policies_examples}

List all policies of trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701`:
```bash
ibmcloud iam trusted-profile-policies Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-update
{: #ibmcloud_iam_trusted_profile_policy_update}

Update an access policy for a trusted profile
```bash
ibmcloud iam trusted-profile-policy-update (NAME|ID) POLICY_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--tags name1:value1,name2:value2...] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_policy_update_options}

NAME|ID (required)
:   Name or ID of the profile to assign the new policy to update.

POLICY_ID (required)
:   The ID of the policy to update.

--account-management
:   Give access to all account management services.

--attributes name=value,name-value...
:   Set resource attributes in the form of 'name=value,name=value....'

--file JSON_FILE
:   JSON file of policy definition.

-f, --force
:   Force failure if multiple profiles are found.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

--region REGION
:   Region of the policy definition. This option is exclusive with '--file'. For supported regions, run 'ibmcloud regions'.

--resource RESOURCE
:   Resource of the policy definition. This option is exclusive with '--file'.

--resource-group-id RESOURCE_GROUP_ID
:   ID of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-name'.

--resource-group-name RESOURCE_GROUP_NAME
:   Name of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-id'.

--resource-type RESOURCE_TYPE
:   Resource type of the policy definition. This option is exclusive with '--file'.

--roles ROLE_NAME1,ROLE_NAME2...
:   Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.

--service-instance SERVICE_INSTANCE_GUID
:   GUID of service instance of the policy definition. This option is exclusive with '--file'.

--service-name SERVICE_NAME
:   Service name of the policy definition. This option is exclusive with '--file'.

--tags name1:value1,name2:value2...
:   Access tags of the resource.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_trusted_profile_policy_update_examples}

Update policy `85f3a4d6-c2e1-417e-b2d5-7199d610c160` to give trusted profile `my-profile` Administrator role for all account management services:
```bash
ibmcloud iam trusted-profile-policy-update my-profile 85f3a4d6-c2e1-417e-b2d5-7199d610c160 --roles Administrator --account-management
```
{: codeblock}

Update policy `bdf62c30-35dd-4852-bcb8-2f0dd3929701` from `my-profile` with contents in JSON file:
```bash
ibmcloud iam trusted-profile-policy-update my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701 --file @policy.json
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-delete
{: #ibmcloud_iam_trusted_profile_policy_delete}

Delete an access policy for a trusted profile
```bash
ibmcloud iam trusted-profile-policy-delete (NAME|ID) POLICY_ID [-f, --force] [-q, --quiet] [--api-version v1 | v2]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_policy_delete_options}

NAME|ID (required)
:   Name or ID of the profile which contains the policy to delete.

POLICY_ID (required)
:   The ID of the policy to delete.

-f, --force
:   Delete access policy without confirmation.

-q, --quiet
:   Suppress verbose output.

--api-version
:   Version of the access policy API.

### Examples
{: #ibmcloud_iam_trusted_profile_policy_delete_examples}

Delete policy ID `bdf62c30-35dd-4852-bcb8-2f0dd3929701` from `my-profile` without confirmation:
```bash
ibmcloud iam trusted-profile-policy-delete my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701 -f
```
{: codeblock}

## ibmcloud iam trusted-profile-link-create
{: #ibmcloud_iam_trusted_profile_link_create}

Create a link to a compute resource for a trusted profile
```bash
ibmcloud iam trusted-profile-link-create (NAME|ID) --name LINK_NAME --cr-type CR_TYPE --link-crn CRN [--link-namespace NAMESPACE --link-name NAME] [--output FORMAT] [-q, --quiet] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_link_create_options}

NAME|ID (required)
:   Name or ID of the profile to link the compute resource to.

--name
:   Name for the link.

--cr-type (required)
:   The compute resource type. VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift.

--link-crn (required)
:   CRN of the VSI instance / cluster instance.

--link-namespace
:   Namespace of the service account for IKS_SA or ROKS_SA, required if IKS_SA or ROKS_SA.

--link-name
:   Name of the service account for IKS_SA or ROKS_SA, required if IKS_SA or ROKS_SA.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_trusted_profile_link_create_examples}

Create link named `my_link` for trusted profile `my-profile` for an `IKS_SA` compute resource with service account name `default`, `default` namespace, and `my_compute_resource_crn` CRN:
```bash
ibmcloud iam trusted-profile-link-create my_profile --name my_link --cr-type IKS_SA --link-name default  --link-namespace default --link-crn my_compute_resource_crn
```
{: codeblock}

Create link named `my_link` for trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701` for an `IKS_SA` compute resource with service account name `default` in the namespace `my_namespace` and with a CRN of `my_resource_crn`:
```bash
ibmcloud iam trusted-profile-link-create Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701 --name my_link --cr-type IKS_SA --link-name default --link-namespace my_namespace --link-crn my_resource_crn
```
{: codeblock}

Create link named `my_link` for trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701` for a `VSI` compute resource with a CRN of `my_resource_crn`:
```bash
ibmcloud iam trusted-profile-link-create Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701 --name my_link --cr-type VSI --link-crn my_resource_crn
```
{: codeblock}

## ibmcloud iam trusted-profile-links
{: #ibmcloud_iam_trusted_profile_links}

List all links to compute resources for a specified trusted profile
```bash
ibmcloud iam trusted-profile-links (NAME|ID) [--id | --output FORMAT] [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_links_options}

NAME|ID (required)
:   Name or ID of the trusted profile to retrieve links.

--id
:   Show ID of links only.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_links_examples}

Display ID of all links in the trusted profile `my-profile`:
```bash
ibmcloud iam trusted-profile-links my-profile --id
```
{: codeblock}

Display all of the links in the trusted profile `my-profile` in JSON format:
```bash
ibmcloud iam trusted-profile-links my-profile --output JSON
```
{: codeblock}

## ibmcloud iam trusted-profile-link-delete
{: #ibmcloud_iam_trusted_profile_link_delete}

Delete a link to a compute resource for a trusted profile:
```bash
ibmcloud iam trusted-profile-link-delete (NAME|ID) (LINK_NAME|LINK_ID) [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_link_delete_options}

NAME|ID (required)
:   Name or ID of the profile which contains the link to delete.

LINK_NAME|LINK_ID (required)
:   Name or ID of the link to delete.

-f, --force
:   Force deletion without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_link_delete_examples}

Delete the link `my_link` from trusted profile `my-profile` without confirmation:
```bash
ibmcloud iam trusted-profile-link-delete my-profile my_link -f
```
{: codeblock}

## ibmcloud iam trusted-profile-identity
{: #ibmcloud_iam_trusted_profile_identity}

Retrieve and display a trusted profile identity
```bash
ibmcloud iam trusted-profile-identity (NAME|ID) (IDENTITY_IDENTIFIER|IDENTITY_ID) --id-type IDENTIFIER_TYPE [--id | --output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_identity_options}

NAME|ID (required)
:   Name or ID of the trusted profile.

IDENTITY_IDENTIFIER|IDENTITY_ID (required)
:   Identifier or ID of the Identity to retrieve.

--id-type (required)
:   The type of identifier to retrieve for the trusted profile. USER for a user IAM ID, SERVICEID for a service ID, or CRN for a service CRN

--id
:   Show ID of the identity only.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

## ibmcloud iam trusted-profile-identities
{: #ibmcloud_iam_trusted_profile_identities}

Retrieve and display trusted profile identities
```bash
ibmcloud iam trusted-profile-identities (NAME|ID) [--id-type IDENTIFIER_TYPE] [--id | --output FORMAT] [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_identities_options}

NAME|ID (required)
:   Name or ID of the trusted profile.

--id-type
:   The type of identifiers to retrieve for the trusted profile. USER for a user IAM ID, SERVICEID for a service ID, or CRN for a service CRN

--id
:   Show ID of the identities only.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force a failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.


## ibmcloud iam trusted-profile-identity-create
{: #ibmcloud_iam_trusted_profile_identity_create}

Connect a trusted profile to an identity
```bash
ibmcloud iam trusted-profile-identity-create (NAME|ID) --id IDENTIFIER_TO_CONNECT --id-type IDENTIFIER_TYPE [--description DESCRIPTION] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_identity_create_options}

NAME|ID (required)
:   Name or ID of the profile to connect the identity to.

--id (required)
:   ID for the identity.

--id-type (required)
:   The type of identifier to connect to the trusted profile. USER for a user IAM ID, SERVICEID for a service ID, or CRN for a service CRN

--description DESCRIPTION
:   Optional description for the connection to the trusted profile

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

## ibmcloud iam trusted-profile-identity-delete
{: #ibmcloud_iam_trusted_profile_identity_delete}

Disconnect a trusted profile from an identity
```bash
ibmcloud iam trusted-profile-identity-delete (NAME|ID) (IDENTITY_IDENTIFIER|IDENTITY_ID) --id-type IDENTIFIER_TYPE [--force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_identity_delete_options}

NAME|ID (required)
:   Name or ID of the profile to disconnect the identity from.

IDENTITY_IDENTIFIER|IDENTITY_ID (required)
:   Identifier or ID of the Identity to disconnect.

--id-type (required)
:   The type of identifier to disconnect from the trusted profile. USER for a user IAM ID, SERVICEID for a service ID, or CRN for a service CRN

-f, --force
:   Force deletion without confirmation.

-q, --quiet
:   Suppress verbose output.



## ibmcloud iam trusted-profile-rule-create
{: #ibmcloud_iam_trusted_profile_rule_create}

Create a rule for a trusted profile:
```bash
ibmcloud iam trusted-profile-rule-create (NAME|UUID) --name RULE_NAME --type RULE_TYPE  [--realm-name REALM_NAME] --conditions <LIST_OF_CONDITIONS> [--expiration EXPIRATION_SEC] [--cr-type CR_TYPE] [--output FORMAT] [-q, --quiet] [-f, --force]
```
{: codeblock}

To view a full list of valid operator conditions for a claim rule, see [Trusted Profiles API](/apidocs/iam-identity-token-api#create-claim-rule)
{: note}

### Command options
{: #ibmcloud_iam_trusted_profile_rule_create_options}

NAME|ID (required)
:   Name or ID of the profile to create a rule for.

--type (required)
:   'Profile-SAML' for a SAML rule or 'Profile-CR' for a compute resource rule

--conditions (required)
:   List of conditions, provided as comma separated list of triple values "claim:CLAIM,operator:OPERATOR,value:VALUE". To specify mutiple conditions, specify the flag multiple times --conditions "claim:CLAIM1,operator:OPERATOR1,value:VALUE1" --conditions "claim:CLAIM2,operator:OPERATOR2,value:VALUE2".

--expiration
:   Specify an expiration in seconds for SAML rules. Must not be provided for trusts established to Compute Resources (type = Profile-CR).

--name
:   Name for the rule.

--cr-type
:   The compute resource type the rule applies to, required only if type is specified as 'Profile-CR'. Values are VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift.

--realm-name
:   Issuer Id for trusts established via IBMid with federation, or appid:// for trusts established via App ID federation. Must not be provided for trusts established to Compute Resources (type = Profile-CR).

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_rule_create_examples}

Create a `Profile-SAML` rule with rule name `my-rule`, realm name set to `https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20`, expiration set to `1200` seconds for trusted profile `my-profile` with the rule conditions: `cn EQUALS my_user`
```bash
ibmcloud iam trusted-profile-rule-create my-profile --name my-rule --type Profile-SAML --conditions claim:cn,operator:EQUALS,value:my_user --realm-name https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20 --expiration 1200
```
{: codeblock}

Create a `Profile-SAML` rule with realm name set to `https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20` and expiration set to `1200` seconds for trusted profile `my-profile` with the rule conditions: `cn EQUALS my_user` and `blueGroups NOT_EQUALS jaas_master`

```bash
ibmcloud iam trusted-profile-rule-create my-profile --type Profile-SAML --conditions claim:cn,operator:EQUALS,value:my_user --conditions claim:blueGroups,operator:NOT_EQUALS,value:jaas_master --realm-name https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20 --expiration 1200
```
{: codeblock}

Create a `Profile-CR` rule with rule name `my-rule`, compute resource type `IKS_SA`, and with the rule conditions: `namespace EQUALS default` and `crn EQUALS crn:test:bluemix:public:containers-kubernetes:us-south:a/test::`

```bash
ibmcloud iam trusted-profile-rule-create my-profile --name my-rule --type Profile-CR --conditions claim:namespace,operator:EQUALS,value:default --conditions claim:crn,operator:EQUALS,value:crn:test:bluemix:public:containers-kubernetes:us-south:a/test:: --cr-type IKS_SA
```
{: codeblock}

## ibmcloud iam trusted-profile-rules
{: #ibmcloud_iam_trusted_profile_rules}

List all rules for a specified trusted profile:
```bash
ibmcloud iam trusted-profile-rules (NAME|ID) [--output FORMAT] [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_rules_options}

NAME|ID (required)
:   Name or ID of the trusted profile to retrieve rules for.

--output FORMAT.
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple profiles are found.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_rules_examples}

Display all rules in trusted profile `my-profile`:
```bash
ibmcloud iam trusted-profile-rules my-profile
```
{: codeblock}

## ibmcloud iam trusted-profile-rule-update
{: #ibmcloud_iam_trusted_profile_rule_update}

Update a rule for a trusted profile:
```bash
ibmcloud iam trusted-profile-rule-update (NAME|ID) (RULE_NAME|RULE_ID) --name RULE_NAME --type RULE_TYPE  [--realm-name REALM_NAME] --conditions <LIST_OF_CONDITIONS> [--cr-type CR_TYPE] [--expiration EXPIRATION_SEC] [--output FORMAT] [-q, --quiet] [-f, --force]
```
{: codeblock}

To view a full list of valid operator conditions for a claim rule, see [Trusted Profiles API](/apidocs/iam-identity-token-api#update-claim-rule)
{: note}

### Command options
{: #ibmcloud_iam_trusted_profile_rule_update_options}

NAME|ID (required)
:   Name or ID of the trusted profile to to update a rule for.

RULE_NAME|RULE_ID (required)
:   The name or ID of the rule to update.

--type
:   'Profile-SAML' for a SAML rule or 'Profile-CR' for a compute resource rule.

--conditions
:   List of conditions, provided as comma separated list of triple values "claim:CLAIM,operator:OPERATOR,value:VALUE". To specify mutiple conditions, specify the flag multiple times --conditions "claim:CLAIM1,operator:OPERATOR1,value:VALUE1" --conditions "claim:CLAIM2,operator:OPERATOR2,value:VALUE2".

--cr-type
:   The compute resource type the rule applies to, required only if type is specified as 'Profile-CR'. Values are VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift.

--expiration
:   Specify an expiration in seconds for SAML rules. Must not be provided for trusts established to Compute Resources (type = Profile-CR).

--name
:   New name for the rule.

--realm-name
:   Issuer Id for trusts established via IBMid with federation, or appid:// for trusts established via App ID federation. Must not be provided for trusts established to Compute Resources (type = Profile-CR).

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-f, --force
:   Force failure if multiple rules are found.

-q, --quiet
:   Suppress verbose output.


### Examples
{: #ibmcloud_iam_trusted_profile_rule_update_examples}

Update rule `ClaimRule-test-id` in profile `my-profile` with new name `test-rule`:
```bash
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-test-id --name test-rule
```
{: codeblock}

Update `Profile-SAML` rule `my-rule` in profile `my-profile` with new realm name `https://www.example.org/my-nice-idp`:
```bash
ibmcloud iam trusted-profile-rule-update my-profile my-rule --realm-name https://www.example.org/my-nice-idp
```
{: codeblock}

Update rule conditions and expiration time for `Profile-SAML` rule `ClaimRule-a448e998-311f-4e23-8af8-66b855c5da11` in profile `my-profile`:
```bash
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-a448e998-311f-4e23-8af8-66b855c5da11 --conditions claim:cn,operator:EQUALS,value:my_user --expiration 1200
```
{: codeblock}

Update rule conditions and compute resource type for `Profile-CR` rule `ClaimRule-cb8e3a2c-2d16-422b-b691-8791355b53bc` in profile `my-profile`:
```bash
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-cb8e3a2c-2d16-422b-b691-8791355b53bc --conditions claim:crn,operator:EQUALS,value:crn:v1:bluemix:public:containers-redhat:us-south:a/test:: --cr-type ROKS_SA
```
{: codeblock}

## ibmcloud iam trusted-profile-rule-delete
{: #ibmcloud_iam_trusted_profile_rule_delete}

Delete a rule for a trusted profile:
```bash
ibmcloud iam trusted-profile-rule-delete (NAME|ID) (RULE_NAME|RULE_ID) [-f, --force] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_rule_delete_options}

NAME|ID (required)
:   Name or ID of the profile which contains the rule to delete.

RULE_NAME|RULE_ID (required)
:   The name or ID of the rule to delete.

-f, --force
:   Force deletion without confirmation.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_rule_delete_examples}

Delete rule `my-rule` from trusted profile `my-profile` without confirmation:
```bash
ibmcloud iam trusted-profile-rule-delete my-profile my-rule -f
```
{: codeblock}

## ibmcloud iam trusted-profile-templates
{: #ibmcloud_iam_trusted_profile_templates}

List all profile templates in current account
```bash
ibmcloud iam trusted-profile-templates [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_templates_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_trusted_profile_templates_examples}

List trusted profile templates in table format
```bash
ibmcloud iam trusted-profile-templates
```
{: codeblock}

## ibmcloud iam trusted-profile-template-create
{: #ibmcloud_iam_trusted_profile_template_create}

Create a trusted profile template
```bash
ibmcloud iam trusted-profile-template-create --file JSON_FILE
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_create_options}

--file JSON_FILE
:   JSON file of the template definition

## ibmcloud iam trusted-profile-template-version
{: #ibmcloud_iam_trusted_profile_template_version}

Get a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION
```
{: codeblock}

### Examples
{: #ibmcloud_iam_trusted_profile_template_version_examples}

List details of a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version example-template-name 1
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_version_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

## ibmcloud iam trusted-profile-template-version-commit
{: #ibmcloud_iam_trusted_profile_template_version_commit}

Commit a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-commit (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_version_commit_options}

### Examples
{: #ibmcloud_iam_trusted_profile_template_version_commit_examples}

Commit a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-commit example-template-name 1
```
{: codeblock}

-q, --quiet
:   Suppress verbose output.

## ibmcloud iam trusted-profile-template-version-create
{: #ibmcloud_iam_trusted_profile_template_version_create}

Create a new version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-create (TEMPLATE_ID | TEMPLATE_NAME) --file JSON_FILE
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_version_create_options}

-q, --quiet
:   Suppress verbose output.

--file JSON_FILE
:   JSON file of the template definition.

### Examples
{: #ibmcloud_iam_trusted_profile_template_version_create_examples}

Create a new version of a specified template from a JSON file
```bash
ibmcloud iam trusted-profile-template-version-create example-template-name --file JSON_FILE
```

## ibmcloud iam trusted-profile-template-version-delete
{: #ibmcloud_iam_trusted_profile_template_version_delete}

Delete a specificed version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-delete TEMPLATE_ID TEMPLATE_VERSION
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_version_delete_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_template_version_delete_examples}

Delete a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-delete example-template-name 1
```
{: codeblock}

## ibmcloud iam trusted-profile-template-version-update
{: #ibmcloud_iam_trusted_profile_template_version_update}

Update a specified version of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-version-update (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION --file JSON_FILE
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_version_update_options}

-q, --quiet
:   Suppress verbose output.

--file JSON_FILE
:   JSON file of the template definition.

### Examples
{: #ibmcloud_iam_trusted_profile_template_version_update_examples}

Update a specified version of a trusted profile template with a JSON file
```bash
ibmcloud iam trusted-profile-template-version-update example-template-name 1 --file JSON_FILE
```
{: codeblock}

## ibmcloud iam trusted-profile-template-versions
{: #ibmcloud_iam_trusted_profile_template_versions}

List all versions of a trusted profile template
```bash
ibmcloud iam trusted-profile-template-versions TEMPLATE_ID | TEMPLATE_NAME
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_template_versions_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_trusted_profile_template_versions_examples}

List all versions of a trusted profile template in JSON format
```bash
ibmcloud iam trusted-profile-template-versions --output JSON
```
{: codeblock}

## ibmcloud iam trusted-profile-assignment
{: #ibmcloud_iam_trusted_profile_assignment}

Show details of a trusted profile assignment
```bash
ibmcloud iam trusted-profile-assignment ASSIGNMENT_ID
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_assignment_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_trusted_profile_assignment_examples}

Show details of a trusted profile assignment in JSON format
```bash
ibmcloud iam trusted-profile-assignment example-assignment-id --output JSON
```
{: codeblock}

## ibmcloud iam trusted-profile-assignment-create
{: #ibmcloud_iam_trusted_profile_assignment_create}

Create a trusted profile assignment
```bash
ibmcloud iam trusted-profile-assignment-create TEMPLATE_ID TEMPLATE_VERSION --target-type TYPE --target TARGET
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_assignment_create_options}

-q, --quiet
:   Suppress verbose output.

--target TARGET
:   ID of the entity targeted

--target-type TYPE
:   Type of entity targeted

### Examples
{: #ibmcloud_iam_trusted_profile_assignment_create_examples}

Create a trusted profile assignment in a specified target account
```bash
ibmcloud iam trusted-profile-assignment-create example-template-id 1 --target-type Account --target example-account-id
```
{: codeblock}

## ibmcloud iam trusted-profile-assignment-delete
{: #ibmcloud_iam_trusted_profile_assignment_delete}

Delete a trusted profile assignment
```bash
ibmcloud iam trusted-profile-assignment-delete ASSIGNMENT_ID
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_assignment_delete_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_assignment_delete_examples}

Create a trusted profile assignment in a specified target account
```bash
ibmcloud iam trusted-profile-assignment-create example-template-id 1 --target-type Account --target example-account-id
```
{: codeblock}

## ibmcloud iam trusted-profile-assignment-update
{: #ibmcloud_iam_trusted_profile_assignment_update}

Update a trusted profile assignment
```bash
ibmcloud iam trusted-profile-assignment-update ASSIGNMENT_ID TEMPLATE_VERSION
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_assignment_update_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_assignment_update_examples}

Update a trusted profile assignment
```bash
ibmcloud iam trusted-profile-assignment-update example-template-id 1
```
{: codeblock}

## ibmcloud iam trusted-profile-assignments
{: #ibmcloud_iam_trusted_profile_assignments}

Get all trusted profile assignments in current account
```bash
ibmcloud iam trusted-profile-assignments
```
{: codeblock}

### Command options
{: #ibmcloud_iam_trusted_profile_assignments_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_trusted_profile_assignments_examples}

List all trusted profile assignments in current account in JSON format
```bash
ibmcloud iam trusted-profile-assignments --output JSON
```
{: codeblock}

## ibmcloud iam account-settings
{: #ibmcloud_iam_account_settings}

List account setting values:
```bash
ibmcloud iam account-settings [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_options}

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

## ibmcloud iam account-settings-update
{: #ibmcloud_iam_account_settings_update}

Update settings under current acount:

```bash
ibmcloud iam account-settings-update [--restrict-create-service-id RESTRICTION_SETTING] [--restrict-create-platform-apikey RESTRICTION_SETTING] [--allowed-ip-addresses ADDRESS_LIST] [--mfa MFA] [--session-expiration-in-seconds SECONDS_EXP] [--session-invalidation-in-seconds SECONDS_INV] [--max-sessions-per-identity SESSIONS_MAX] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_update_options}

--restrict-create-service-id RESTRICTION_SETTING
:   The restriction level on Service ID creation (one of `RESTRICTED`, `NOT_RESTRICTED`, or `NOT_SET`).

--restrict-create-platform-apikey RESTRICTION_SETTING
:   The restriction level on API Key creation (one of `RESTRICTED`, `NOT_RESTRICTED`, or `NOT_SET`).

--allowed-ip-addresses ADDRESS_LIST
:   The IP addresses and subnets from which IAM tokens can be created (default is "").

--session-expiration-in-seconds SECONDS_EXP
:   The number of seconds after which the session expires (can also be `NOT_SET`, which resets the value to default).

--session-invalidation-in-seconds SECONDS_INV
:   The number of seconds of inactivity after which a session is invalidated (can also be "NOT_SET", which resets the value to default).

--max-sessions-per-identity SESSIONS_MAX
:   The maximum number of sessions per identity on the account (can also be `NOT_SET`, which resets the value to default).

--mfa MFA
:   The type of MFA on the account (one of `NONE`, `TOTP`, `TOTP4ALL`, `LEVEL1`, `LEVEL2`, or `LEVEL3`).

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_update_examples}

Update the multi-factor authentication setting of an account to `LEVEL3`:

```bash
ibmcloud iam account-settings-update --mfa LEVEL3
```
{: codeblock}

Update the number of seconds after which a session expires to default (with `NOT_SET`):

```bash
ibmcloud iam account-settings-update --session-expiration-in-seconds NOT_SET
```
{: codeblock}

## ibmcloud iam account-settings-template
{: #ibmcloud_iam_account_settings_template}

Show details of an account settings template:
```bash
ibmcloud iam account-settings-template (TEMPLATE_ID | TEMPLATE_NAME) [-q,--quiet] [--output JSON]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_template_examples}

Show details for account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template AccountSettingsEditorTemplate
```
{: codeblock}

## ibmcloud iam account-settings-templates
{: #ibmcloud_iam_account_settings_templates}

List account settings templates for an enterprise account:
```bash
ibmcloud iam account-settings-templates [-q,--quiet] [--output JSON]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_templates_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_templates_examples}

List account settings templates on current account

```bash
ibmcloud iam account-settings-templates
```
{: codeblock}

## ibmcloud iam account-settings-template-create
{: #ibmcloud_iam_account_settings_template-create}

Create a new account settings template for an enterprise account:
```bash
ibmcloud iam account-settings-template-create TEMPLATE_NAME [-d, --description DESCRIPTION] [--file JSON_FILE] [-q,--quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_create_options}

-d , --description DESCRIPTION
:   Description of the template

--file JSON_FILE
:   JSON file of the template definition

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_template_create_examples}

Create an account settings template on current account

```bash
ibmcloud iam account-settings-template-create AccountSettingsEditorTemplate --fie /path/to/account_settings_template.json
```
{: codeblock}

## ibmcloud iam account-settings-template-version
{: #ibmcloud_iam_account_settings_template_version}

Get a specific version of an account settings template in an enterprise account:
```bash
ibmcloud iam account-settings-template-version (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q,--quiet] [--output JSON]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_version_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_template_version_examples}

Show version `1` of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-create AccountSettingsEditorTemplate 1
```
{: codeblock}

## ibmcloud iam account-settings-template-versions
{: #ibmcloud_iam_account_settings_template_versions}

List versions of an account settings template in an enterprise account:
```bash
ibmcloud iam account-settings-template-versions (TEMPLATE_ID | TEMPLATE_NAME) [-q,--quiet] [--output JSON]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_versions_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_template_versions_examples}

List versions of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-versions AccountSettingsEditorTemplate
```
{: codeblock}

## ibmcloud iam account-settings-template-version-create
{: #ibmcloud_iam_account_settings_template_version_create}

Create a new version of an account settings template in an enterprise account:
```bash
ibmcloud iam account-settings-template-version-create {(TEMPLATE_ID |TEMPLATE_NAME) (--file JSON_FILE)} [-q,--quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_version_create_options}

--file JSON_FILE
:   JSON file of account settings template definition

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_template_version_create_examples}

Create a new version of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-version-create AccountSettingsEditorTemplate --file /path/to/account_settings_template.json
```
{: codeblock}

## ibmcloud iam account-settings-template-version-update
{: #ibmcloud_iam_account_settings_template-version-update}

Update a specific version of an account settings template in an enterprise account:
```bash
ibmcloud iam account-settings-template-version-update (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION --file JSON_FILE [-d, --description DESCRIPTION] [-q,--quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_version_update_options}

-d value, --description DESCRIPTION
:   Description of the template

--file JSON_FILE
:   JSON file of template definition

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_version_update_examples}

Update version `1` of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-version-update AccountSettingsEditorTemplate 1 --file /path/to/account_settings_template.json
```
{: codeblock}

## ibmcloud iam account-settings-template-version-delete
{: #ibmcloud_iam_account_settings_template-version-delete}

Delete a version of an account settings template for an enterprise account:
```bash
ibmcloud iam account-settings-template-version-delete (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q,--quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_version_delete_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_template_version_delete}

Delete version `2` of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-delete AccountSettingsEditorTemplate 2
```
{: #codeblock}

## ibmcloud iam account-settings-template-version-commit
{: #ibmcloud_iam_account_settings_template-version-commit}

Commit a specific version of an account settings template in an enterprise account:
```bash
ibmcloud iam account-settings-template-commit (TEMPLATE_ID | TEMPLATE_NAME) TEMPLATE_VERSION [-q,--quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_version_commit_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_template_version_commit_examples}

Commit version `1` of account settings template `AccountSettingsEditorTemplate`

```bash
ibmcloud iam account-settings-template-version-commit AccountSettingsEditorTemplate 1
```
{: codeblock}

## ibmcloud iam account-settings-assignments
{: #ibmcloud_iam_account_settings_assignments}

List assignments for account settings on an enterprise account:
```bash
ibmcloud iam account-settings-assignments [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_assignments_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_assignments_examples}

List assignments in current account
```bash
ibmcloud iam account-settings-assignments
```
{: codeblock}

## ibmcloud iam account-settings-assignment
{: #ibmcloud_iam_account_settings_assignment}

Get an assignment for an account settings template:
```bash
ibmcloud iam account-settings-assignment ASSIGNMENT_ID [-q,--quiet] [--output FORMAT]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_assignment_options}

-q, --quiet
:   Suppress verbose output.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

### Examples
{: #ibmcloud_iam_account_settings_assignment_examples}

Get account settings assignment `AccountSettingsAssignment-7c4345c7f2cb4c75a9f29b68fc1e1e88`
```bash
ibmcloud iam account-settings-assignment AccountSettingsAssignment-7c4345c7f2cb4c75a9f29b68fc1e1e88
```
{: codeblock}

## ibmcloud iam account-settings-assignment-create
{: #ibmcloud_iam_account_settings_assignment_create}

Create an assignment for an account settings template:
```bash
ibmcloud iam account-settings-assignment-create TEMPLATE_NAME TEMPLATE_VERSION TARGET_TYPE TARGET [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_template_assignment_create_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_template_assignment_create_examples}

Assign account settings template template to account
```bash
ibmcloud iam account-settings-assignment-create TemplateTest 1 Account f7fc6938256e46e1a25ee09e14ca9c20
```
{: codeblock}

Assign account settings template template to account group
```bash
ibmcloud iam account-settings-assignment-create TemplateTest 1 AccountGroup 955fc2274567474f8da802d5c376504b
```
{: codeblock}

## ibmcloud iam account-settings-assignment-update
{: #ibmcloud_iam_account_settings_assignment-update}

Update an assignment in order to retry failed assignments or migrate resources to a new version:
```bash
ibmcloud iam account-settings-assigment-update ASSIGNMENT_ID TEMPLATE_VERSION [-q,--quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_assignment_update_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_assignment_update_examples}

Update account settings assignment `AccountSettingsAssignment-63d65ed159ff463b8ec09ea77d22a05b` to a template version 2

```bash
ibmcloud iam account-settings-assignment-update AccountSettingsAssignment-63d65ed159ff463b8ec09ea77d22a05b 2
```
{: codeblock}

## ibmcloud iam account-settings-assignment-delete
{: #ibmcloud_iam_account_settings_assignment-delete}

Delete an account settings assignment. This will remove any resources created by this assignment:
```bash
ibmcloud iam account-settings-assigment-delete ASSIGNMENT_ID [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_iam_account_settings_assignment_delete_options}

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_iam_account_settings_assignment_delete_examples}

Delete account settings assignment `AccountSettingsAssignment-63d65ed159ff463b8ec09ea77d22a05b`

```bash
ibmcloud iam account-settings-assignment-delete AccountSettingsAssignment-63d65ed159ff463b8ec09ea77d22a05b
```
{: codeblock}
