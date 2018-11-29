---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Working with the Cloud Foundry Enterprise Environment service
{: #ibmcloud_commands_cfee}

With {{site.data.keyword.cfee_full}} (CFEE) you can instantiate multiple, isolated, enterprise-grade Cloud Foundry platforms on-demand. Instances of the IBM Cloud Foundry Enterprise service run within your own account in the IBM Cloud. The environment is deployed on isolated hardware (Kubernetes clusters). You have full control over the environment, including access control, capacity, version updates, resource usage and monitoring.

Use the following commands to manage CFEE environments, orgs, spaces, users and roles.
{: shortdesc}

<table summary="Manage Cloud Foundry Enterprise Environments (experimental)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 <td>[ibmcloud cfee create](cli_cfee.html#ibmcloud_cfee_create)</td>
 <td>[ibmcloud cfee create-locations](cli_cfee.html#ibmcloud_cfee_create_locations)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee create-permission-get](cli_cfee.html#ibmcloud_create_permission_get)</td>
 <td>[ibmcloud cfee create-permission-set](cli_cfee.html#ibmcloud_create_permission_set)</td>
 <td>[ibmcloud cfee create-status](cli_cfee.html#ibmcloud_create_status)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

List CFEE environments.

```
ibmcloud cfee environments
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Show details of a CFEE environment

```
ibmcloud cfee environment NAME [--id]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>NAME (required)</dt>
   <dd>The name of the environment to be shown.</dd>
   <dt>--id</dt>
   <dd>Show ID only</dd>
  </dl>

<strong>Examples</strong>:

Show details of a CFEE environment `env_example`:

```
ibmcloud cfee environment env_example
```

Show id of a CFEE environment `env_example`:

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

List all orgs

```
ibmcloud cfee orgs [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

List all orgs:

```
ibmcloud cfee orgs
```

List all orgs of CFEE environment `env_example`:

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Display details of an org

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>--guid</dt>
   <dd>Display org GUID only, all other output for the org is suppressed</dd>
  </dl>

<strong>Examples</strong>:

Show details of a CFEE org `org_example`:

```
ibmcloud cfee org org_example
```

Show details of a CFEE org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org org_example --env env_example
```

Show GUID of a CFEE org `org_example`:

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Create an org

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization being created.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>Quota to assign to the newly created org (use default quota if not specified)</dd>
  </dl>

<strong>Examples</strong>:

Create a CFEE org `org_example`:

```
ibmcloud cfee org-create org_example
```

Create a CFEE org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org-create org_example --env env_example
```

Create a CFEE org `org_example` with quota `quote_example`:

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Delete an org

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization being deleted.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>-f, --force</dt>
   <dd>Force deletion without confirmation</dd>
  </dl>

<strong>Examples</strong>:

Delete a CFEE org `org_example`:

```
ibmcloud cfee org-delete org_example
```

Delete a CFEE org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org-delete org_example --env env_example
```

Delete a CFEE org `org_example` without confirmation:

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Display users in specified organization by role

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>-a, --all</dt>
   <dd>List all users in the specified org</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Display users in CFEE org `org_example`:

```
ibmcloud cfee org-users org_example
```

Display users in CFEE org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org-users org_example --env env_example
```

List all users in CFEE org `org_example`:

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Assign an org role to a user (org manager required)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being assigned.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the organization role this user is assigned to. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Assign role `BillingManager` to user `test@exmaple.com` in org `org_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

Assign role `BillingManager` to user `test@exmaple.com` in org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Remove an org role from a user (org manager or user him/herself only)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being removed.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the organization role this user is removed from. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Remove role `BillingManager` of user `test@exmaple.com` from org `org_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

Remove role `BillingManager` of user `test@exmaple.com` from org `org_example` of CFEE environment `env_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

List all spaces

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

List all spaces

```
ibmcloud cfee spaces
```

List all spaces of org `org_example` and CFEE environment `env_example`

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Show the info of specified space

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space to be shown.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>--guid</dt>
   <dd>Retrieve and display the given space's guid. All other output for the space is suppressed.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
   <dt>--security-group-rules</dt>
   <dd>Retrieve the rules for all the security groups associated with the space.</dd>
  </dl>

<strong>Examples</strong>:

Show the info of space `space_example`:

```
ibmcloud cfee space space_example
```

Retrieve and display the guid of space `space_example`:

```
ibmcloud cfee space space_example --guid
```

Show the rules for all the security groups associated with space `space_example`:

```
ibmcloud cfee space space_example --security-group-rules
```

Show the info of space `space_example` of org `org_example` and CFEE environment `env_example`:

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Create a new space

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space being created.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Create a new space `space_example`:

```
ibmcloud cfee space-create space_example
```

Create a new space `space_example` under org `org_example` and CFEE environment `env_example`:

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Rename a space

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>OLD_NAME (required)</dt>
   <dd>The old name of the space that is to be renamed.</dd>
   <dt>NEW_NAME (required)</dt>
   <dd>The new name of the space that it is renamed to.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Rename space `space_example` to `new_pace_example`:

```
ibmcloud cfee space-rename space_example new_pace_example
```

Rename space `space_example` to `new_pace_example` under org `org_example` and CFEE environment `env_example`:

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Delete a space

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space to be deleted.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
   <dt>-f, --force</dt>
   <dd>Force deletion without confirmation.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Delete space `space_example`:

```
ibmcloud cfee space-delete space_example
```

Delete space `space_example` under org `org_example` and CFEE environment `env_example` without confirmation:

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Assign a space role to a user

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being assigned.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space this user is assigned to.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the space role this user is assigned to. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a given space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Assign user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Assign user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role under environment `env_example`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Remove a space role from a user

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being removed.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space this user is removed from.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the space role this user is removed from. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a given space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Remove user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Remove user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role under environment `env_example`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Get all space roles of current user under specific org

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Get all space roles of current user under org `org_example`:

```
ibmcloud cfee space-roles org_example
```

Get all space roles of current user under org `org_example` and environment `env_example`:

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Display users in specified space by role

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space.</dd>
   <dt>--env ENV</dt>
   <dd>CFEE environment name. Default to current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Display all users in space `space_example` and org `org_example`:

```
ibmcloud cfee space-users org_example space_example
```

Display all users in space `space_example` and org `org_example` and environment `env_example`:

```
ibmcloud cfee space-users org_example space_example --env env_example
```

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Make request to a create a new instance of Cloud Foundry Enterprise Environment

```
ibmcloud cfee create NAME LOCATION [--cells CELLS] [--isolation ISOLATION] [--private-vlan ID, --public-vlan ID] [--plan ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
  <dl>
   <dt>NAME (required)</dt>
   <dd>The name of the instance.</dd>
   <dt>LOCATION (required)</dt>
   <dd>The location to create the instance in.</dd>
   <dt>--cells CELLS</dt>
   <dd>Specify the number of cells for this CFEE. The default is 2, and minimum is 1. In a 1 cell CFEE, there cannot be high availability.</dd>
   <dt>--isolation ISOLATION</dt>
   <dd>Specifiy the isolation of the IBM Kubernetes cluster. Options are "dedicated" and "shared". The default is "shared", and a "dedicated" cluster does charge more.</dd>
   <dt>--private-vlan ID</dt>
   <dd>Specify ID of private VLAN. By default, we will find an available set of VLANs or create a pair for you.</dd>
   <dt>--public-vlan ID</dt>
   <dd>Specify ID of public VLAN. By default, we will find an available set of VLANs or create apair for you.</dd>
   <dt>--plan ID</dt>
   <dd>Specify ID of plan. By default, we will provision into Standard plan.</dd>
  </dl>

<strong>Examples</strong>:

Create an instance named `test-cfee` in `dal10`:

```
ibmcloud cfee create test-cfee dal10
```

Create a `dedicated` instance named `test-cfee` in `dal10` with `4` cells:

```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Make request to get a list of available datacenters for the targeted regions

```
ibmcloud cfee create-locations
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:


## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Check if a user has all the permissions required to create a CFEE instance. The command checks the following access policies for the target user: Editor to the CFEE services, administrator role to the Kubernetes Service, editor for the platform role and manager for the service access role to the Cloud Object Storage service, and developer role to the current space in the current org for provisioning Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>The name of the access group to check permissions in. The default access group is "cfee-provision-access-group".</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify permissions output format, only JSON is supported now.</dd>
  </dl>
  
<strong>Examples</strong>:

Check CFEE create permissions for user `name@example.com`:

```
ibmcloud cfee create-permission-get name@example.com
```

Check CFEE create permissions for user `name@example.com` and in access group `test-access-group`:

```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Give user all the permissions required to create a CFEE instance. The command creates the following access policies for the target user:  Editor role to the CFEE service, administrator role to the Kubernetes service, editor for the platform role and manager for the service access role to the Cloud Object Storage service, and developer role to the current space in the current org for provisioning Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>The name of the access group to give permissions in. The default access group is "cfee-provision-access-group".</dd>
  </dl>
  
<strong>Examples</strong>:

Give CFEE create permissions to user `name@example.com` via the default access group:

```
ibmcloud cfee create-permission-set name@example.com
```

Give CFEE create permissions to user `name@example.com` via access group `test-access-group`:

```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Check the provisioning status of a CFEE instance

```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>NAME or ID (required)</dt>
   <dd>The name or id of the CFEE instance.</dd>
   <dt>--poll</dt>
   <dd>Specify if you'd like to make this call recurring, to poll until in stable state</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify the status output format, only JSON is supported now.</dd>
  </dl>
