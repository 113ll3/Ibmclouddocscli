---

copyright:
  years: 2018, 2021
lastupdated: "2021-08-30"

keywords: iam, iam access, api keys, service ids, access groups, trusted profiles, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}
{:external: target="_blank" .external}

# Managing IAM access, API keys, trusted profiles, service IDs, and access groups (ibmcloud iam)
{: #ibmcloud_commands_iam}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage API keys, service IDs, access groups, and authorization policies for users, services, and access groups.
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

List all service IDs:
```
ibmcloud iam service-ids [--uuid]
```

<strong>Command Options</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Show UUID of service IDs only.</dd>
</dl>

<strong>Examples</strong>:

List UUID of all service IDs under current account:
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Display details of a service ID:
```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service, exclusive with UUID.</dd>
  <dt>UUID (required)</dt>
  <dd>UUID of the service, exclusive with NAME.</dd>
  <dt>--uuid</dt>
  <dd>Display the UUID of the service ID.</dd>
</dl>

<strong>Examples</strong>:

Show details of service ID `sample-test`:
```
ibmcloud iam service-id sample-test
```
{: codeblock}

Show details of service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Create a service ID:
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service.</dd>
  <dt>-d, --description</dt>
  <dd>Description of the service ID.</dd>
  <dt>--lock</dt>
  <dd>Lock the service ID during creation.</dd>
</dl>

<strong>Examples</strong>:

Create a service ID with service name `sample-test` and description `hello, world!`:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

Create a locked service ID with service name `sample-test` and description `hello, world!`:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

Update a service ID:
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service, exclusive with UUID.</dd>
  <dt>UUID (required)</dt>
  <dd>UUID of the service, exclusive with NAME.</dd>
  <dt>-n, --name</dt>
  <dd>New name of the service.</dd>
  <dt>-d, --description</dt>
  <dd>New description of the service.</dd>
  <dt>-f, --force</dt>
  <dd>Update without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Rename service ID `sample-test` to `sample-test-2` without confirmation:
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

Update description of service `sample-test`:
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

Rename service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` to `sample-test-3` with new description:
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Delete a service ID:
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service, exclusive with UUID.</dd>
  <dt>UUID (required)</dt>
  <dd>UUID of the service, exclusive with NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Delete service ID `sample-teset` without confirmation:
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

Delete service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Lock a service ID:
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service, exclusive with UUID.</dd>
  <dt>UUID (required)</dt>
  <dd>UUID of the service, exclusive with NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Lock without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Lock service ID `sample-teset` without confirmation:
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

Lock service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Unlock a service ID:
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service, exclusive with UUID.</dd>
  <dt>UUID (required)</dt>
  <dd>UUID of the service, exclusive with NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Unlock without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Unlock service ID `sample-teset` without confirmation:
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

Unlock service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

List all {{site.data.keyword.cloud_notm}} platform API keys:
```
ibmcloud iam api-keys [--uuid]
```
{: codeblock}

<strong>Command Options</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Show UUID of the API key.</dd>
</dl>

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Create an {{site.data.keyword.cloud_notm}} platform API key:
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

Using the {{site.data.keyword.cloud_notm}} CLI login with an API Key does not work with the legacy SL API Key that is found on `control.softlayer.com` option. An upgraded {{site.data.keyword.cloud_notm}} Account where Infrastructure is managed through [cloud.ibm.com](https://cloud.ibm.com/registration){: external} is required for the {{site.data.keyword.cloud_notm}} CLI login with an API Key.
{: note}

<strong>Command options</strong>:
<dl>
<dt>NAME (required)</dt>
<dd>Name of the API key to be created.</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Description of the API key.</dd>
<dt>--file <i>FILE</i></dt>
<dd>Save API key information to the specified file.</dd>
<dt>--lock</dt>
<dd>Lock the API key when it is created.</dd>
</dl>

<strong>Examples</strong>:

Create an API key and save to a file:
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

Create a locked API key with name "test-key":
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Update a {{site.data.keyword.cloud_notm}} platform API key:
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Command options</strong>:
<dl>
<dt>NAME (required)</dt>
<dd>The old name of the API key to be updated, exclusive with UUID.</dd>
<dt>UUID (required)</dt>
<dd>The UUID of the API key to be updated, exclusive with NAME.</dd>
<dt>-n <i>NAME</i> (optional)</dt>
<dd>The new name of the API key.</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>The new description of the API key.</dd>
</dl>

<strong>Examples</strong>:

Update the description of an API key:
```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

The `iam-identity.apikey.manage` privilege is required for the account when the NAME and UUID command options are used. For more information, see [Managing user API keys](/docs/account?topic=account-userapikey&interface=ui#manage-user-keys) and [IAM Identity Service](/docs/account?topic=account-iam-service-roles-actions#iam-identity-service).
{: note}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

Delete a {{site.data.keyword.cloud_notm}} platform API key:
```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
<dt>NAME (required)</dt>
<dd>Name of the API key to be deleted, exclusive with UUID.</dd>
<dt>UUID (required)</dt>
<dd>UUID of the API key to be deleted, exclusive with NAME.</dd>
<dt>-f, --force</dt>
<dd>Force deletion without confirmation.</dd>
</dl>

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

Lock a platform API key:
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
<dt>NAME (required)</dt>
<dd>Name of the API key to be locked, exclusive with UUID.</dd>
<dt>UUID (required)</dt>
<dd>UUID of the API key to be locked, exclusive with NAME.</dd>
<dt>-f, --force</dt>
<dd>Force lock without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Lock API key test-api-key:
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

Lock API key with given UUID without confirmation:
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Unlock a platform API key:
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
<dt>NAME (required)</dt>
<dd>Name of the API key to be unlocked, exclusive with UUID.</dd>
<dt>UUID (required)</dt>
<dd>UUID of the API key to be unlocked, exclusive with NAME.</dd>
<dt>-f, --force</dt>
<dd>Unlock an API key without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Unlock API key test-api-key:
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

Unlock API key with given UUID without confirmation:
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

List all API keys of a service:
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Display service API keys without confirmation.</dd>
</dl>

<strong>Examples</strong>:

List all API keys of service `sample-service`:
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

List details of a service API key:
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID.</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>--uuid</dt>
  <dd>Display the UUID of service API key.</dd>
  <dt>-f, --force</dt>
  <dd>Display service API key without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Show details of service API key `sample-key` of service `sample-service`:
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Create a service API key:
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the service ID or newly created service API key.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-d, --description</dt>
  <dd>Description of the API key.</dd>
  <dt>--file FILE</dt>
  <dd>Save API key information to the specified file.</dd>
  <dt>-f, --force</dt>
  <dd>Force creation without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Create a service API key `sample-key` for service `sample-service` without confirmation:
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Update a service API key:
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID.</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-n, --name</dt>
  <dd>New name of the service API key.</dd>
  <dt>-d, --description</dt>
  <dd>New description of the service API key.</dd>
  <dt>-f, --force</dt>
  <dd>Update without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Rename service API key `sample-key` to `new-sample-key`:
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Delete a service API key:
```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID.</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Delete service API key `sample-key` of service ID `sample-service`:
```
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Lock a service API key:
```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID.</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Lock without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Lock service API key `sample-key` of service ID `sample-service`:
```
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Unlock a service API key:
```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID.</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME.</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID.</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME.</dd>
  <dt>-f, --force</dt>
  <dd>Unlock without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Unlock service API key `sample-key` of service ID `sample-service`:
```
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

List all access policies for a specified user:
```
ibmcloud iam user-policies USER_NAME
```

<strong>Command options</strong>:
<dl>
<dt>USER_NAME (required)</dt>
<dd>User name to whom the policies belong.</dd>
</dl>

<strong>Examples</strong>:
 
List policies of user `name@example.com`:
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Display details of an access policy for a user:
```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>Command options</strong>:
<dl>
<dt>USER_NAME (required)</dt>
<dd>User name to whom the policy belongs.</dd>
<dt>POLICY_ID (required)</dt>
<dd>ID of the policy.</dd>
</dl>

<strong>Examples</strong>:

List policy `0bb730daa` of user `name@example.com`:
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Create an access policy for the specified user in the current account:
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]}
```

<strong>Command options</strong>:
<dl>
<dt>USER_NAME (required)</dt>
<dd>User name to whom the policy belongs to.</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>JSON file of policy definition. You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-id` options.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-name` options.</dd>
<dt>--account-management (optional)</dt>
<dd>Give access to all account management services.</dd>
<dt>--attributes <i>name=value,name=value...</i></dt>
<dd>Set resource attributes in the form of `name=value,name=value....`</dd>
</dl>

<strong>Examples</strong>:

Create user policy for user `name@example.com` from policy JSON file `policy.json`:
```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```
{: codeblock}

Give `name@example.com` `Administrator` role for all instances of `sample-service` service:
```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```
{: codeblock}

Give `name@example.com` `Editor` role and a custom role `Responder` for all instances of `sample-service` service:
```
ibmcloud iam user-policy-create name@example.com --roles Editor,Responder --service-name sample-service
```
{: codeblock}

Give `name@example.com` `Editor` role for resource `key123` of sample service instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Give `name@example.com` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `name@example.com` `Viewer` role for the members of resource group `sample-resource-group`:
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Give `name@example.com` `Viewer` role for the members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `name@example.com` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Update an access policy for the specified user in the current account:
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]}
```

<strong>Command options</strong>:
<dl>
<dt>USER_NAME (required)</dt>
<dd>User name to whom the policy belongs to.</dd>
<dt>POLICY_ID (required)</dt>
<dd>ID of the policy to update.</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>JSON file of policy definition.</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME` option. This option is exclusive with the `--file` option.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-id` options.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file`, `--resource` and `--resource-group-name` options.</dd>
<dt>--account-management (optional)</dt>
<dd>Give access to all account management services.</dd>
<dt>--attributes <i>name=value,name=value...</i></dt>
<dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
</dl>

<strong>Examples</strong>:

Update user policy with the one in JSON file：
```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```
{: codeblock}

Update user policy to give `name@example.com` `Administrator` role for all instances of `sample-service` service：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```
{: codeblock}

Update user policy to give `name@example.com` `Editor` role and a custom role `Responder` for all instances of `sample-service` service：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Editor,Responder --service-name sample-service
```
{: codeblock}

Update user policy to give `name@example.com` `Editor` role for resource `key123` of sample service instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Update user policy to give `name@example.com` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for members of resource group `sample-resource-group`:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update user policy to give `name@example.com` `Viewer` role for service `is` resources with attribute `instance` equal to `*`:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Delete an access policy for the specified user:
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Delete user policy without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Delete policies `user-policy-id` of user `name@example.com`:
```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```
{: codeblock}

Delete policies `user-policy-id` of user `name@example.com` without confirmation:
```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```
{: codeblock}

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

List all access policies for a specified service ID:
```
ibmcloud iam service-policies SERVICE_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID (required)</dt>
  <dd>Name or UUID of service ID.</dd>
  <dt>-f, --force (optional)</dt>
  <dd>Display service policies without confirmation.</dd>
</dl>

<strong>Examples</strong>:

List policies of service `test`:
```
ibmcloud iam service-policies test
```
{: codeblock}

List policies of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Display details of an access policy for a specified service ID:
```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID (required)</dt>
  <dd>Name or UUID of service ID.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>ID of the service policy.<dd>
  <dt>-f, --force (optional)</dt>
  <dd>Display service policy without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Show policy `140798e2-8ea7db3` of service `test`:
```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
{: codeblock}

Show policy `140798e2-8ea7db3` of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```
{: codeblock}

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Create an access policy and assign it to a service ID:
```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID (required)</dt>
  <dd>Name or UUID of service ID.</dd>
  <dt>--file</dt>
  <dd>JSON file of policy definition. This option is exclusive with the `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `--resource-group-name` and `--resource-group-id` options.  You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).</dd>
  <dt>-r, --roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME` option. This option is exclusive with the `--file` option.</dd>
  <dt>--service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>--resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>--resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` options.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` options.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Give access to all account management services.</dd>
  <dt>-f, --force</dt>
  <dd>Create service policy without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Create service policy from JSON file for service `test`:
```
ibmcloud iam service-policy-create test --file @policy.json
```
{: codeblock}

Create service policy from JSON file for service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```
{: codeblock}

Grant service `test` the `Administrator` role for all account management services:
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```
{: codeblock}

Grant service `test` the `Viewer` role for all resources in account:
```
ibmcloud iam service-policy-create test --roles Viewer
```
{: codeblock}

Grant service `test` the `Viewer` role and a custom role `Responder` for all `sample` service instances in account:
```
ibmcloud iam service-policy-create test --roles Viewer,Responder --service-name sample
```
{: codeblock}

Give service `test` the `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```
ibmcloud iam service-policy-create sample-service --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Update an access policy for a service ID:
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]} [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID (required)</dt>
  <dd>Name or UUID of service ID.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>ID of the service policy.<dd>
  <dt>--file</dt>
  <dd>JSON file of policy definition. This option is exclusive with the `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `resource-group-name`, and `resource-group-id` options.</dd>
  <dt>-r, --roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>--resource-group-name</dt>
  <dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` options.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` options.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--attributes <i>name=value,name=value...</i></dt>
  <dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
  <dt>-f, --force</dt>
  <dd>Update service policy without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Update service policy `140798e2-8ea7db3` from JSON file for service `test`:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
{: codeblock}

Update service policy `140798e2-8ea7db3` from JSON file for service `test`:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Administrator` role for all account management services:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role for all resources in account:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role and a custom role `Responder` for all `sample` service instances in account:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer,Responder --service-name sample
```
{: codeblock}

Update service policy `140798e2-8ea7db3` to grant service `test` the `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Delete an access policy for a service ID:
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>SERVICE_ID (required)</dt>
  <dd>Name or UUID of service ID.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>ID of the service policy.<dd>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Delete policy `140798e2-8ea7db3` of service `test`:
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
{: codeblock}

Delete policy `140798e2-8ea7db3` of service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```
{: codeblock}

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Retrieve and display the OAuth tokens for the current session:
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

List platform, service-defined, and custom roles:
```
ibmcloud iam roles [--service SERVICE_NAME [--resource-type RESOURCE_TYPE] [--source-service SOURCE_SERVICE_NAME]] [--roles ROLE_NAME]
```
{: codeblock}

<strong>Command Options</strong>:
<dl>
  <dt>--resource-type</dt>
  <dd>Resource type of the service. '--service' must be set along with this option.</dd>
  <dt>--roles ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Show details of specific roles</dd>
  <dt>--service SERVICE_NAME</dt>
  <dd>Name of the service. Only list platform-defined roles if not specified.</dd>
  <dt>--source-service<dt>
  <dd>Name of the service. Only list platform-defined roles if not specified. <b>This option does not support private endpoints.</b></dd>
</dl>

<strong>Examples</strong>:

List platform default access roles and custom roles:
```
ibmcloud iam roles
```
{: codeblock}

List details of platform default access policy roles `Administrator`, `Operator`:
```
ibmcloud iam roles --roles Administrator,Operator
```
{: codeblock}

List details of access policy role `Writer` of `cloud-object-storage` service in JSON format:
```
ibmcloud iam roles --service cloud-object-storage --roles Writer --output JSON
```
{: codeblock}

List access policy roles for all account management service in JSON:
```
ibmcloud iam roles --service allacctmgmtroles --output JSON
```
{: codeblock}

List details of resource group access policy role `Administrator`:
```
ibmcloud iam roles --service resource-controller --roles Administrator
```
{: codeblock}

List details of access policy roles of resource type `image` of service `is`:
```
ibmcloud iam roles --service is --resource-type image
```
{: codeblock}

List authorization roles for source service `cloud-object-storage` and target service `kms`:
```
ibmcloud iam roles --source-service cloud-object-storage --service kms
```
{: codeblock}

## ibmcloud iam access-policies
{: #ibmcloud_iam_access_policies}

List all access policies under current account:
```
ibmcloud iam access-policies [-t, --type user | service_id | access_group | trusted_profile]
```
{: codeblock}

<strong>Command Options</strong>:
<dl>
  <dt>-t, --type ACCESS_POLICY_TYPE</dt>
  <dd>List all access policies under current account filtered by policy type. Valid options are: `user` | `service_id` | `access_group` | `trusted_profile`</dd>
</dl>

<strong>Examples</strong>:

List all access policies under current account:
```
ibmcloud iam access-policies
```
{: codeblock}

List all user access policies under current account:
```
ibmcloud iam access-policies --type user
```
{: codeblock}

List all service ID access policies under current account:
```
ibmcloud iam access-policies --type service_id
```
{: codeblock}

List all access group access policies under current account:
```
ibmcloud iam access-policies --type access_group
```
{: codeblock}

List all trusted profile access policies under current account:
```
ibmcloud iam access-policies --type trusted_profile
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Disconnect the public IBMid with dedicated non-IBMid:
```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Force disconnect without confirmation.</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Create an authorization policy to allow a service instance access to another service instance:
```
ibmcloud iam authorization-policy-create { SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-group-id RESOURCE_GROUP_ID] [--source-resource-type RESOURCE_TYPE] [--source-resource RESOURCE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--target-resource-group-id RESOURCE_GROUP_ID] [--target-resource-type RESOURCE_TYPE] [--target-resource RESOURCE] | --file FILE}
```

<strong>Command Options</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>The source service that can be authorized to access. To find the service's name, run the `ibmcloud catalog service-marketplace` command.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>The target service that the source service can be authorized to access. To find the service's name, run the `ibmcloud catalog service-marketplace` command.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>The roles that provide access for the source service.</dd>
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Source service instance name, mutually exclusive with `--source-service-instance-id`. If not specified, all instances of the source service are authorized to access.</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>Source service instance ID, mutually exclusive with `--source-service-instance-name`. If not specified, all instances of the source service are authorized to access.</dd>
  <dt>--source-resource-group-id RESOURCE_GROUP_ID<dt>
  <dd>Source resource group ID, mutually exclusive with '--source-service-instance-id'.</dd>
  <dt>--source-resource-type</dt>
  <dd>Resource type of source service.</dd>
  <dt>--source-resource</dt>
  <dd>Resource of source service.</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Target service instance name, mutually exclusive with `--target-service-instance-id`. If not specified, all instances of the target service are authorized to access.</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>Target service instance ID, mutually exclusive with `--target-service-instance-name`. If not specified, all instances of the target service are authorized to access.</dd>
  <dt>--target-resource-group-id RESOURCE_GROUP_ID<dt>
  <dd>Target resource group ID, mutually exclusive with '--target-service-instance-id'.</dd>
  <dt>--target-resource-type</dt>
  <dd>Resource type of target service.</dd>
  <dt>--target-resource</dt>
  <dd>Resource of target service.</dd>
  <dt>--file FILE</dt>
  <dd>JSON file of policy definition.</dd>
</dl>

<b>Note:</b> Currently, some combination of `--source-service` and `--service` might fail under private endpoints. Use `--file` as a workaround, or you can create the policy from public endpoints or the UI console.

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Delete an authorization policy:
```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID of authorization policy to be deleted.</dd>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Show details of an authorization policy:
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```
{: codeblock}

<strong>Command Options</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID of authorization policy to show.</dd>
</dl> 

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

List authorization policies under the current account:
```
ibmcloud iam authorization-policies
```
{: codeblock}

<strong>Command options</strong>:
   <dl>
   </dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

List access groups under current account:
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Command Options</strong>:
<dl>
  <dt>-u</dt>
  <dd>List access groups the user belongs to. This option is exclusive to '-s'.</dd>
  <dt>-s</dt>
  <dd>List access groups the service ID belongs to. This option is exclusive to '-u'.</dd>
</dl>

<strong>Examples</strong>:

List all access groups:
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Show details of an access group:
```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Command Options</strong>:
<dl>
  <dt>-id</dt>
  <dd>Show the ID only.</dd>
</dl>

<strong>Examples</strong>:

Show details of access group `example_group`:
```
ibmcloud iam access-group example_group
```
{: codeblock}

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Create an access group:
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Command Options</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Description of access group.</dd>
</dl>

<strong>Examples</strong>:

Create an access group `example_group`:
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Update an access group:
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>New access group name.</dd>
  <dt>-d, --description</dt>
  <dd>New description.</dd>
  <dt>-f, --force</dt>
  <dd>Force update without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Rename access group `example_group` to `hello_world_group`:
```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```
{: codeblock}

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Delete an access group:
```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive] [-a, --all]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation.</dd>
  <dt>-r, --recursive</dt>
  <dd>Delete an access group and its members.</dd>
  <dt>-a, --all</dt>
  <dd>Force to delete access groups with the same name.</dd>
</dl>

<strong>Examples</strong>:

Delete access group `example_group`:
```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

List users in an access group:
```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Examples</strong>:

List all users in access group `example_group`:
```
ibmcloud iam access-group-users example_group
```
{: codeblock}

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Add users to an access group:
```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Examples</strong>:

Add user `name@example.com` to access group `example_group`:
```
ibmcloud iam access-group-user-add example_group name@example.com
```
{: codeblock}

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Remove a user from an access group:
```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Examples</strong>:

Remove user `name@example.com` from access group `example_group`:
```
ibmcloud iam access-group-user-remove example_group name@example.com
```
{: codeblock}

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Remove user from all access groups:
```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Remove user `name@example.com` from all access groups:
```
ibmcloud iam access-group-user-purge name@example.com -f
```
{: codeblock}

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

List service IDs in an access group:
```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Examples</strong>:

List all service IDs in access group `example_group`:
```
ibmcloud iam access-group-service-ids example_group
```
{: codeblock}

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Add service ID to an access group:
```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Examples</strong>:

Add service ID `example-service` to access group `example_group`:
```
ibmcloud iam access-group-service-id-add example_group example-service
```
{: codeblock}

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Remove a service ID from an access group:
```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Examples</strong>:

Remove service ID `example-service` from access group `example_group`:
```
ibmcloud iam access-group-service-id-remove example_group example-service
```
{: codeblock}

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Remove service ID from all access groups:
```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Remove service ID `example-service` from all access groups:
```
ibmcloud iam access-group-service-id-purge example --force
```
{: codeblock}

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

List policies of an access group:
```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Examples</strong>:

List all policies of access group `example_group`:
```
ibmcloud iam access-group-policies example_group
```
{: codeblock}

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Show details of an access group policy:
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Examples</strong>:

Show details of policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```
{: codeblock}

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Create an access group policy:
```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]}
```

<strong>Command Options</strong>:
<dl>
  <dt>--file</dt>
  <dd>JSON file of policy definition. You can use advanced operators in a JSON policy document to grant access to resources that satisfy specific naming conventions. For more information about using advanced operators to create wildcard policies, see [Assigning access by using wildcard policies](/docs/account?topic=account-wildcard).</dd>
  <dt>-roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.</dd>
  <dt>-service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` option.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` option.</dd>
  <dt>--account-management</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--attributes <i>name=value,name=value...</i></dt>
  <dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
</dl>

<strong>Examples</strong>:

Create an access group policy from a JSON file:
```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```
{: codeblock}

Give `example_group` `Administrator` role for all `sample-service` resources:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Give `example_group` `Editor` role and a custom role `Responder` for all instances of `sample-service` in `us-south` region:
```
ibmcloud iam access-group-policy-create example_group --roles Editor,Responder --service-name sample-service --region us-south
```
{: codeblock}

Give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```
{: codeblock}

Give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `example_group` `Viewer` role for the members of resource group `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Give `example_group` `Viewer` role for the members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Give `example_group` `Administrator` role for all account management services:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --account-management
```
{: codeblock}

Give `example_group` `Viewer` role for all resources in account:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer
```
{: codeblock}

Give `example_group` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Update an access group policy:
```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management] [--attributes name=value,name=value...]}
```

<strong>Command Options</strong>:
<dl>
  <dt>--file</dt>
  <dd>JSON file of policy definitions.</dd>
  <dt>--roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run `ibmcloud iam roles --service SERVICE_NAME`. This option is exclusive with the `--file` option.</dd>
  <dt>-service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with the `--file` option.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-id` option.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID of the resource group. `*` means all resource groups. This option is exclusive with the `--file` and `--resource-group-name` option.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--attributes <i>name=value,name=value...</i></dt>
  <dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
</dl>

<strong>Examples</strong>:

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` with the one in policy JSON file:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Administrator` role for all `sample-service` resources:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Editor` role and a custom role `Responder` for all instances of `sample-service` in `us-south` region:
```
ibmcloud iam access-group-policy-update example_group --roles Editor,Responder --service-name sample-service --region us-south
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for members of resource group `sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Administrator` role for all account management services:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --account-management
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for all resources in account:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer
```
{: codeblock}

Update access group policy `b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4` to give `example_group` `Viewer` role for service `is` resources with attribute `instanceId` equal to `*`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --service-name is --attributes "instanceId=*"
```
{: codeblock}

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Delete an access group policy:
```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation.</dd>
</dl>

<strong>Examples</strong>:

Delete policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
{: codeblock}

## ibmcloud iam trusted-profile-create
{: #ibmcloud_iam_trusted_profile_create}

Create a trusted profile:
```
ibmcloud iam trusted-profile-create NAME [-d, --description DESCRIPTION] [--output FORMAT] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME (required)</dt>
  <dd>Name of the new profile.</dd>
  <dt>-d, --description DESCRIPTION</dt>
  <dd>Description of the profile.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Create trusted profile with name `sample-test` and description "sample trusted profile":
```
ibmcloud iam trusted-profile-create sample-test -d "sample trusted profile" 
```
{: codeblock}

## ibmcloud iam trusted-profile
{: #ibmcloud_iam_trusted_profile}

Get a trusted profile by name or ID:
```
ibmcloud iam trusted-profile NAME|ID [--id | --output FORMAT] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile.</dd>
  <dt>--id</dt>
  <dd>Show ID of the profile only.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Retrieve trusted profile with name `sample-test`:
```
ibmcloud iam trusted-profile sample-test
```
{: codeblock}

Retrieve trusted profile with profile ID `Profile-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam trusted-profile Profile-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam trusted-profiles
{: #ibmcloud_iam_trusted_profiles}

List trusted profiles under current account
```
ibmcloud iam trusted-profiles [--id | --output FORMAT] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>--id</dt>
  <dd>Show ID of profiles only.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

List ID of all trusted profiles under current account:
```
ibmcloud iam trusted-profiles --id
```
{: codeblock}

## ibmcloud iam trusted-profile-update
{: #ibmcloud_iam_trusted_profile_update}

Update a trusted profile
```
ibmcloud iam trusted-profile-update NAME|ID [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to update.</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>New name of the trusted profile.</dd>
  <dt>-d, --description NEW_DESCRIPTION</dt>
  <dd>New description of the profile. Providing an empty description will clear the description of the profile.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Update trusted profile with name `sample-test` to new name of `test`:
```
ibmcloud iam trusted-profile-update sample-test -n test
```
{: codeblock}

Update trusted profile `sample-test` with new description of `testing trusted profile update`:
```
ibmcloud iam trusted-profile-update sample-test -d "testing trusted profile update"
```
{: codeblock}

## ibmcloud iam trusted-profile-delete
{: #ibmcloud_iam_trusted_profile_delete}

Delete a trusted profile
```
ibmcloud iam trusted-profile-delete NAME|ID [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to delete.</dd>
  <dt>-f, --force</dt>
  <dd>Delete a trusted profile without confirmation.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Delete trusted profile with name `sample-test`:
```
ibmcloud iam trusted-profile-delete sample-test
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-create
{: #ibmcloud_iam_trusted_profile_policy_create}

Create an access policy and assign it to a trusted profile
```
ibmcloud iam trusted-profile-policy-create (NAME|ID) {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--tags name1:value1,name2:value2...] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to assign the new policy to</dd>
  <dt>--account-management</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--attributes name=value,name-value...</dt>
  <dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
  <dt>--file JSON_FILE</dt>
  <dd>JSON file of policy definition.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>--region REGION</dt>
  <dd>Region of the policy definition. This option is exclusive with '--file'. For supported regions, run 'ibmcloud regions'.</dd>
  <dt>--resource RESOURCE</dt>
  <dd>Resource of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--resource-group-id RESOURCE_GROUP_ID</dt>
  <dd>ID of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-name'.</dd>
  <dt>--resource-group-name RESOURCE_GROUP_NAME</dt>
  <dd>Name of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-id'.</dd>
  <dt>--resource-type RESOURCE_TYPE</dt>
  <dd>Resource type of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--roles ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.</dd>
  <dt>--service-instance SERVICE_INSTANCE_GUID</dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--service-name SERVICE_NAME</dt>
  <dd>Service name of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--tags name1:value1,name2:value2...</dt>
  <dd>Access tags of the resource.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Create a trusted profile policy for `my-profile` from a JSON file:
```
iam trusted-profile-policy-create my-profile --file policy.json
```
{: codeblock}

Give `my-profile` Viewer role for the members of resource group `sample-resource-group`:
```
iam trusted-profile-policy-create my-profile --roles Viewer --resource-group-id sample-resource-group
```
{: codeblock}

Give `my-profile` Viewer role for all resources in account:
```
iam trusted-profile-policy-create my-profile --roles Viewer
```
{: codeblock}

## ibmcloud iam trusted-profile-policy
{: #ibmcloud_iam_trusted_profile_policy}

Display details of an access policy for a specified trusted profile
```
ibmcloud iam trusted-profile-policy (NAME|ID) POLICY_ID [--output FORMAT] [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>The ID of the policy to retrieve.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Get policy `bdf62c30-35dd-4852-bcb8-2f0dd3929701` of trusted profile `my-profile`:
```
ibmcloud iam trusted-profile-policy my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701
```
{: codeblock}

## ibmcloud iam trusted-profile-policies
{: #ibmcloud_iam_trusted_profile_policies}

List all access policies for a specified trusted profile
```
ibmcloud iam trusted-profile-policies (NAME|ID) [--output FORMAT] [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

List all policies of trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701`:
```
ibmcloud iam trusted-profile-policies Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-update
{: #ibmcloud_iam_trusted_profile_policy_update}

Update an access policy for a trusted profile
```
ibmcloud iam trusted-profile-policy-update (NAME|ID) POLICY_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--tags name1:value1,name2:value2...] [--account-management] [--attributes name=value,name=value...]} [--output FORMAT] [-q, --quiet] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to assign the new policy to update.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>The ID of the policy to update.</dd>
  <dt>--account-management</dt>
  <dd>Give access to all account management services.</dd>
  <dt>--attributes name=value,name-value...</dt>
  <dd>Set resource attributes in the form of 'name=value,name=value....'</dd>
  <dt>--file JSON_FILE</dt>
  <dd>JSON file of policy definition.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>--region REGION</dt>
  <dd>Region of the policy definition. This option is exclusive with '--file'. For supported regions, run 'ibmcloud regions'.</dd>
  <dt>--resource RESOURCE</dt>
  <dd>Resource of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--resource-group-id RESOURCE_GROUP_ID</dt>
  <dd>ID of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-name'.</dd>
  <dt>--resource-group-name RESOURCE_GROUP_NAME</dt>
  <dd>Name of the resource group. '*' means all resource groups. This option is exclusive with '--file' and '--resource-group-id'.</dd>
  <dt>--resource-type RESOURCE_TYPE</dt>
  <dd>Resource type of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--roles ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.</dd>
  <dt>--service-instance SERVICE_INSTANCE_GUID</dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--service-name SERVICE_NAME</dt>
  <dd>Service name of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>--tags name1:value1,name2:value2...</dt>
  <dd>Access tags of the resource.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Update policy `85f3a4d6-c2e1-417e-b2d5-7199d610c160` to give trusted profile `my-profile` Administrator role for all account management services:
```
ibmcloud iam trusted-profile-policy-update my-profile 85f3a4d6-c2e1-417e-b2d5-7199d610c160 --roles Administrator --acount-management
```
{: codeblock}

Update policy `bdf62c30-35dd-4852-bcb8-2f0dd3929701` from `my-profile` with contents in JSON file:
```
ibmcloud iam trusted-profile-policy-update my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701 --file @policy.json 
```
{: codeblock}

## ibmcloud iam trusted-profile-policy-delete
{: #ibmcloud_iam_trusted_profile_policy_delete}

Delete an access policy for a trusted profile
```
ibmcloud iam trusted-profile-policy-delete (NAME|ID) POLICY_ID [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile which contains the policy to delete.</dd>
  <dt>POLICY_ID (required)</dt>
  <dd>The ID of the policy to delete.</dd>
  <dt>-f, --force</dt>
  <dd>Delete access policy without confirmation.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Delete policy ID `bdf62c30-35dd-4852-bcb8-2f0dd3929701` from `my-profile` without confirmation:
```
ibmcloud iam trusted-profile-policy-delete my-profile bdf62c30-35dd-4852-bcb8-2f0dd3929701 -f
```
{: codeblock}

## ibmcloud iam trusted-profile-link-create
{: #ibmcloud_iam_trusted_profile_link_create}

Create a link to a compute resource for a trusted profile
```
ibmcloud iam trusted-profile-link-create (NAME|ID) --name LINK_NAME --cr-type CR_TYPE --link-crn CRN [--link-namespace NAMESPACE --link-name NAME] [--output FORMAT] [-q, --quiet] [-f, --force]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to link the compute resource to</dd>
  <dt>--name</dt>
  <dd>Name for the link</dd>
  <dt>--cr-type (required)</dt>
  <dd>The compute resource type. VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift</dd>
  <dt>--link-crn (required)</dt>
  <dd>CRN of the VSI instance / cluster instance</dd>
  <dt>--link-namespace</dt>
  <dd>Namespace of the service account for IKS_SA or ROKS_SA, required if IKS_SA or ROKS_SA</dd>
  <dt>--link-name</dt>
  <dd>Name of the service account for IKS_SA or ROKS_SA, required if IKS_SA or ROKS_SA</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Create link named `my_link` for trusted profile `my-profile` for an `IKS_SA` compute resource with service account name `default`, `default` namespace, and `my_compute_resource_crn` CRN:
```
ibmcloud iam trusted-profile-link-create my_profile --name my_link --cr-type IKS_SA --link-name default  --link-namespace default --link-crn my_compute_resource_crn
```
{: codeblock}

Create link named `my_link` for trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701` for an `IKS_SA` compute resource with service account name `default` in the namespace `my_namespace` and with a CRN of `my_resource_crn`:
```
ibmcloud iam trusted-profile-link-create Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701 --name my_link --cr-type IKS_SA --link-name default --link-namespace my_namespace --link-crn my_resource_crn
```
{: codeblock}


Create link named `my_link` for trusted profile ID `Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701` for a `VSI` compute resource with a CRN of `my_resource_crn`:
```
ibmcloud iam trusted-profile-link-create Profile-bdf62c30-35dd-4852-bcb8-2f0dd3929701 --name my_link --cr-type VSI --link-crn my_resource_crn
```
{: codeblock}

## ibmcloud iam trusted-profile-links
{: #ibmcloud_iam_trusted_profile_links}

List all links to compute resources for a specified trusted profile
```
ibmcloud iam trusted-profile-links (NAME|ID) [--id | --output FORMAT] [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the trusted profile to retrieve links</dd>
  <dt>--id</dt>
  <dd>Show ID of links only.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Display ID of all links in the trusted profile `my-profile`:
```
ibmcloud iam trusted-profile-links my-profile --id
```
{: codeblock}

Display all of the links in the trusted profile `my-profile` in JSON format:
```
ibmcloud iam trusted-profile-links my-profile --output JSON
```
{: codeblock}

## ibmcloud iam trusted-profile-link-delete
{: #ibmcloud_iam_trusted_profile_link_delete}

Delete a link to a compute resource for a trusted profile:
```
ibmcloud iam trusted-profile-link-delete (NAME|ID) (LINK_NAME|LINK_ID) [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile which contains the link to delete.</dd>
  <dt>LINK_NAME|LINK_ID (required)</dt>
  <dd>Name or ID of the link to delete.</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Delete the link `my_link` from trusted profile `my-profile` without confirmation:
```
ibmcloud iam trusted-profile-link-delete my-profile my_link -f
```
{: codeblock}

## ibmcloud iam trusted-profile-rule-create
{: #ibmcloud_iam_trusted_profile_rule_create}

Create a rule for a trusted profile:
```
ibmcloud iam trusted-profile-rule-create (NAME|UUID) --name RULE_NAME --type RULE_TYPE  [--realm-name REALM_NAME] --conditions <LIST_OF_CONDITIONS> [--expiration EXPIRATION_SEC] [--cr-type CR_TYPE] [--output FORMAT] [-q, --quiet] [-f, --force]
```

To view a full list of valid operator conditions for a claim rule, see [Trusted Profiles API](/apidocs/iam-identity-token-api#create-claim-rule)
{: note}

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile to create a rule for</dd>
  <dt>--type (required)</dt>
  <dd>'Profile-SAML' for a SAML rule or 'Profile-CR' for a compute resource rule</dd>
  <dt>--conditions (required)</dt>
  <dd>List of conditions, provided as comma separated list of triple values "claim:CLAIM,operator:OPERATOR,value:VALUE". To specify mutiple conditions, specify the flag multiple times --conditions "claim:CLAIM1,operator:OPERATOR1,value:VALUE1" --conditions "claim:CLAIM2,operator:OPERATOR2,value:VALUE2"</dd>
  <dt>--expiration</dt>
  <dd>Specify an expiration in seconds for SAML rules. Must not be provided for trusts established to Compute Resources (type = Profile-CR)</dd>
  <dt>--name</dt>
  <dd>Name for the rule</dd>
  <dt>--cr-type</dt>
  <dd>The compute resource type the rule applies to, required only if type is specified as 'Profile-CR'. Values are VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift</dd>
  <dt>--realm-name</dt>
  <dd>Issuer Id for trusts established via IBMid with federation, or appid:// for trusts established via App ID federation. Must not be provided for trusts established to Compute Resources (type = Profile-CR)</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Create a `Profile-SAML` rule with rule name `my-rule`, realm name set to `https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20`, expiration set to `1200` seconds for trusted profile `my-profile` with the rule conditions: `cn EQUALS my_user`
```
ibmcloud iam trusted-profile-rule-create my-profile --name my-rule --type Profile-SAML --conditions claim:cn,operator:EQUALS,value:my_user --realm-name https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20 --expiration 1200
```
Create a `Profile-SAML` rule with realm name set to `https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20` and expiration set to `1200` seconds for trusted profile `my-profile` with the rule conditions: `cn EQUALS my_user` and `blueGroups NOT_EQUALS jaas_master`

```
ibmcloud iam trusted-profile-rule-create my-profile --type Profile-SAML --conditions claim:cn,operator:EQUALS,value:my_user --conditions claim:blueGroups,operator:NOT_EQUALS,value:jaas_master --realm-name https://w3id.sso.ibm.com/auth/sps/samlidp2/saml20 --expiration 1200
```

Create a `Profile-CR` rule with rule name `my-rule`, compute resource type `IKS_SA`, and with the rule conditions: `namespace EQUALS default` and `crn EQUALS crn:test:bluemix:public:containers-kubernetes:us-south:a/test::`

```
ibmcloud iam trusted-profile-rule-create my-profile --name my-rule --type Profile-CR --conditions claim:namespace,operator:EQUALS,value:default --conditions claim:crn,operator:EQUALS,value:crn:test:bluemix:public:containers-kubernetes:us-south:a/test:: --cr-type IKS_SA
```
{: codeblock}

## ibmcloud iam trusted-profile-rules
{: #ibmcloud_iam_trusted_profile_rules}

List all rules for a specified trusted profile:
```
ibmcloud iam trusted-profile-rules (NAME|ID) [--output FORMAT] [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the trusted profile to retrieve rules for</dd>
  <dt>--output FORMAT</dt>.
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple profiles are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Display all rules in trusted profile `my-profile`:
```
ibmcloud iam trusted-profile-rules my-profile 
```
{: codeblock}

## ibmcloud iam trusted-profile-rule-update
{: #ibmcloud_iam_trusted_profile_rule_update}

Update a rule for a trusted profile:
```
ibmcloud iam trusted-profile-rule-update (NAME|ID) (RULE_NAME|RULE_ID) --name RULE_NAME --type RULE_TYPE  [--realm-name REALM_NAME] --conditions <LIST_OF_CONDITIONS> [--cr-type CR_TYPE] [--expiration EXPIRATION_SEC] [--output FORMAT] [-q, --quiet] [-f, --force]
```

To view a full list of valid operator conditions for a claim rule, see [Trusted Profiles API](/apidocs/iam-identity-token-api#update-claim-rule)
{: note}

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the trusted profile to to update a rule for</dd>
  <dt>RULE_NAME|RULE_ID (required)</dt>
  <dd>The name or ID of the rule to update.</dd>
  <dt>--type</dt>
  <dd>'Profile-SAML' for a SAML rule or 'Profile-CR' for a compute resource rule</dd>
  <dt>--conditions</dt>
  <dd>List of conditions, provided as comma separated list of triple values "claim:CLAIM,operator:OPERATOR,value:VALUE". To specify mutiple conditions, specify the flag multiple times --conditions "claim:CLAIM1,operator:OPERATOR1,value:VALUE1" --conditions "claim:CLAIM2,operator:OPERATOR2,value:VALUE2"</dd>
  <dt>--cr-type</dt>
  <dd>The compute resource type the rule applies to, required only if type is specified as 'Profile-CR'. Values are VSI for Virtual Service Instance on VPC, IKS_SA for Service Accounts on Kubernetes clusters, or ROKS_SA for managed Red Hat OpenShift</dd>
  <dt>--expiration</dt>
  <dd>Specify an expiration in seconds for SAML rules. Must not be provided for trusts established to Compute Resources (type = Profile-CR)</dd>
  <dt>--name</dt>
  <dd>New name for the rule</dd>
  <dt>--realm-name</dt>
  <dd>Issuer Id for trusts established via IBMid with federation, or appid:// for trusts established via App ID federation. Must not be provided for trusts established to Compute Resources (type = Profile-CR)</dd>
  <dt>--output FORMAT</dt>
  <dd>Specify output format, only 'JSON' is supported.</dd>
  <dt>-f, --force</dt>
  <dd>Force failure if multiple rules are found.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Update rule `ClaimRule-test-id ` in profile `my-profile` with new name `test-rule`:
```
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-test-id --name test-rule
```
{: codeblock}

Update `Profile-SAML` rule `my-rule` in profile `my-profile` with new realm name `https://www.example.org/my-nice-idp`:
```
ibmcloud iam trusted-profile-rule-update my-profile my-rule --realm-name https://www.example.org/my-nice-idp
```
{: codeblock}

Update rule conditions and expiration time for `Profile-SAML` rule `ClaimRule-a448e998-311f-4e23-8af8-66b855c5da11` in profile `my-profile`:
```
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-a448e998-311f-4e23-8af8-66b855c5da11 --conditions claim:cn,operator:EQUALS,value:my_user --expiration 1200
```
{: codeblock}

Update rule conditions and compute resource type for `Profile-CR` rule `ClaimRule-cb8e3a2c-2d16-422b-b691-8791355b53bc` in profile `my-profile`:
```
ibmcloud iam trusted-profile-rule-update my-profile ClaimRule-cb8e3a2c-2d16-422b-b691-8791355b53bc --conditions claim:crn,operator:EQUALS,value:crn:v1:bluemix:public:containers-redhat:us-south:a/test:: --cr-type ROKS_SA
```
{: codeblock}

## ibmcloud iam trusted-profile-rule-delete
{: #ibmcloud_iam_trusted_profile_rule_delete}

Delete a rule for a trusted profile:
```
ibmcloud iam trusted-profile-rule-delete (NAME|ID) (RULE_NAME|RULE_ID) [-f, --force] [-q, --quiet]
```

<strong>Command Options</strong>:
<dl>
  <dt>NAME|ID (required)</dt>
  <dd>Name or ID of the profile which contains the rule to delete.</dd>
  <dt>RULE_NAME|RULE_ID (required)</dt>
  <dd>The name or ID of the rule to delete.</dd>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation.</dd>
  <dt>-q, --quiet</dt>
  <dd>Suppress verbose output.</dd>
</dl>

<strong>Examples</strong>:

Delete rule `my-rule` from trusted profile `my-profile` without confirmation:
```
ibmcloud iam trusted-profile-rule-delete my-profile my-rule -f
```