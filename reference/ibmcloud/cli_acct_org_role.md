---

copyright:

  years: 2018


lastupdated: "2018-08-15"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commands for Managing Accounts, Orgs, and Roles
 {: #ibmcloud_commands_account}

<table summary="ibmcloud commands that you can use to manage accounts, orgs, spaces and roles.">
<caption>Table 1. Commands for managing accounts, orgs, spaces and roles</caption>
 <thead>
 <th colspan="5">Commands for managing accounts, orgs, spaces, and roles</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
  <td>[ibmcloud app domain-cert](cli_acct_org_role.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](cli_acct_org_role.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](cli_acct_org_role.html#ibmcloud_app_domain_cert_remove)</td>
 </tr>
 </tbody>
 </table>

 ### ibmcloud account orgs
{: #ibmcloud_account_orgs}

List all organizations

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>-r <i>REGION</i> (optional)</dt>
   <dd>For which region the organization information is shown. If set to 'all', all organizations in all regions are listed.</dd>
   <dt>--guid (optional)</dt>
   <dd>Display the GUID of the organizations.</dd>
   </dl>

<strong>Examples</strong>:

List all the organizations in region: `us-south` with the GUID displayed

```
ibmcloud account orgs -r us-south --guid
```

### ibmcloud account org
{: #ibmcloud_account_org}

Show the information for the specified organization.

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>--guid (optional)</dt>
   <dd>Display the GUID of the organization.</dd>
   </dl>

<strong>Examples</strong>:

Show the information of organization `IBM` with the GUID displayed

```
ibmcloud account org IBM --guid
```

### ibmcloud account org-create
{: #ibmcloud_account_org_create}

Create a new organization. This operation can only be performed by account owner.

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization being created.</dd>
   <dt>-f</dt>
   <dd>Force creation without confirmation.</dd>
   </dl>

<strong>Examples</strong>:

Create an organization named `IBM`.

```
ibmcloud account org-create IBM
```

### ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replicate an org from the current region to another region.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the existing org that is to be replicated.</dd>
   <dt>REGION_NAME (required)</dt>
   <dd>The name of the region that hosts the replicated org.</dd>
   </dl>

<strong>Examples</strong>:

Replicate the org `myorg` to the region `eu-gb`:

```
ibmcloud account org-replicate myorg eu-gb
```

### ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rename an organization. This operation can be done only by an org manager.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>OLD_ORG_NAME (required)</dt>
   <dd>The old name of the org that is to be renamed.</dd>
   <dt>NEW_ORG_NAME (required)</dt>
   <dd>The new name of the org that it is renamed to.</dd>
   </dl>

### ibmcloud account spaces
{: #ibmcloud_account_spaces}

List all spaces

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Command options</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Organization name. List the spaces under the organization specified. Default to current organization if not specified.</dd>
   <dt>-r</dt>
   <dd>Region name. List the spaces under the region specified. Default to current region if not specified.</dd>
   </dl>

### ibmcloud account space
{: #ibmcloud_account_space}

This command has the same function and options as the [cf space ![External link icon](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} command.

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

This command has the same function and options as the [cf create-space ![External link icon](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} command.

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


This command has the same function and options as the [cf rename-space ![External link icon](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} command.

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


This command has the same function and options as the [cf delete-space ![External link icon](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} command.

### ibmcloud account org-users
{: #ibmcloud_account_org_users}

Display users in the specified organization by role.

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>ORG_NAME (required)</dt>
<dd>The name of the organization.</dd>
<dt>-a (optional)</dt>
<dd>List all the users in the specified organization, not grouped by role.</dd>
</dl>

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Add a user into org (org manager required).

```
 ibmcloud account org-user-add USER_NAME ORG
```

### ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Remove a user from org (org manager or user him/herself only)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Command options</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Force deletion without confirmation.</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Get all organization roles of the current user

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>-u</dt>
   <dd>User ID. If not specified, default to current user.</dd>
  </dl>

### ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assign an organization role to a user. This operation can be performed only by an organization manager.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user being assigned.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>ORG_ROLE (required)</dt>
   <dd>The name of the organization role this user is assigned to. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
  </dl>

<strong>Examples</strong>:

Assign user `Mary` to the organization `IBM` as `OrgManager` role:

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Note**: You can set org/space roles using the CLI, but if you want to set the other permissions, you have to use the UI. For further details, see [Assigning user access](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

### ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Remove an organization role from a user. This operation can be performed only by an organization manager.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user being removed.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>ORG_ROLE (required)</dt>
   <dd>The name of the organization role this user is removed from. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
    </dl>

<strong>Examples</strong>:

Remove user `Mary` from the organization `IBM` as `OrgManager` role:

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

### ibmcloud account space-users
{: #ibmcloud_account_space_users}

Display users in the specified space by role.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space.</dd>
   </dl>

### ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assign a space role to a user. This operation can be performed only by a space manager.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user being assigned.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space this user is assigned to.</dd>
   <dt>SPACE_ROLE (required)</dt>
   <dd>The name of the space role this user is assigned to. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a given space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
    </dl>

<strong>Examples</strong>:

Assign user `Mary` to the organization `IBM` and space `Cloud` as `SpaceManager` role:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

### ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Remove a space role from a user. This operation can be performed only by a space manager.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user being removed.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space this user is removed from.</dd>
   <dt>SPACE_ROLE (required)</dt>
   <dd>The name of the space role this user is removed from. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a given space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
    </dl>


<strong>Examples</strong>:

Remove user `Mary` from the organization `IBM` and space `Cloud` as `SpaceManager` role:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

### ibmcloud account list
{: #ibmcloud_account_list}

List all accounts of the current user

```
ibmcloud account list
```

<strong>Prerequisites</strong>:  Endpoint, Login

### ibmcloud account org-account
{: #ibmcloud_account_org_account}

Display the account of specified organization(org user required)

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>--guid (optional)</dt>
  <dd>Display account ID only</dd>
</dl>

### ibmcloud account users
{: #ibmcloud_account_users}

Displays users associated with the account. This operation can be performed only by the account owner.

```
ibmcloud account users
```

### ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Remove a user from an account(account owner only)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>USER_ID (required)</dt>
<dd>User id</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Account ID. If not specified, default to current account.</dd>
<dt>-f, --force</dt>
<dd>Force removal without confirmation.</dd>
</dl>

### ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invite a user to the account

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being invited.</dd>
   <dt>-o ORG</dt>
   <dd>Organization to invite user to</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Organization role. Valid inputs are: OrgManager, BillingManager, OrgAuditor and OrgUser. If omitted, the OrgUser role will be set.</dd>
   <dt>-s SPACE</dt>
   <dd>Space to invite user to</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Space role. Valid inputs are: SpaceManager, SpaceDeveloper and SpaceAuditor.</dd>
</dl>

### ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Resend invitation to a user (account admin)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user being re-invited.</dd>
</dl>

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

List access groups under current account

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-u</dt>
  <dd>List access groups the user belongs to. This flag is exclusive to '-s'.</dd>
  <dt>-s</dt>
  <dd>List access groups the service ID belongs to. This flag is exclusive to '-u'.</dd>
</dl>

<strong>Examples</strong>:

List all access groups:

```
ibmcloud iam access-groups
```

### ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Show details of an access group

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-id</dt>
  <dd>Show ID only</dd>
</dl>

<strong>Examples</strong>:

Show details of access group `example_group`:

```
ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Create an access group

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Description of access group</dd>
</dl>

<strong>Examples</strong>:

Create an access group `example_group`:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Update an access group

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>New access group name</dd>
  <dt>-d, --description</dt>
  <dd>New description</dd>
  <dt>-f, --force</dt>
  <dd>Force update without confirmation</dd>
</dl>

<strong>Examples</strong>:

Rename access group `example_group` to `hello_world_group`:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

### ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Delete an access group

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
  <dt>-r, --recursive</dt>
  <dd>Delete access group and its members</dd>
</dl>

<strong>Examples</strong>:

Delete access group `example_group`:

```
ibmcloud iam access-group-delete example_group --force
```

### ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

List users in an access group

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

List all users in access group `example_group`:

```
ibmcloud iam access-group-users example_group
```

### ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Add user(s) to an access group

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

Add user `name@example.com` to access group `example_group`:

```
ibmcloud iam access group-user-add example_group name@example.com
```

### ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Remove a user from an access group

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

Remove user `name@example.com` from access group `example_group`:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

### ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Remove user from all access groups

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation</dd>
</dl>

<strong>Examples</strong>:

Remove user `name@example.com` from all access groups:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

List service IDs in an access group

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

List all service IDs in access group `example_group`:

```
ibmcloud iam access-group-service-ids example_group
```

### ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Add service ID to an access group

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

Add service ID `example-service` to access group `example_group`:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

### ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Remove a service ID from an access group

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

Remove service ID `example-service` from access group `example_group`:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

### ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Remove service ID from all access groups

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Delete without confirmation</dd>
</dl>

<strong>Examples</strong>:

Remove service ID `example-service` from all access groups:

```
ibmcloud iam access-group-service-id-purge example --force
```

### ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

List policies of an access group

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

List all policies of access group `example_group`:

```
ibmcloud iam access-group-policies example_group
```

### ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Show details of an access group policy

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
</dl>

<strong>Examples</strong>:

Show details of policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Create an access group policy

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--file</dt>
  <dd>JSON file of policy definition</dd>
  <dt>-roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name of the resource group. This option is exclusive with '--file' and '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID of the resource group. This option is exclusive with '--file' and '--resource-group-name'.</dd>
</dl>

<strong>Examples</strong>:

Create an access group policy from a JSON file:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Give `example_group` `Administrator` role for all `sample-service` resources:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Give `example_group` `Viewer` role for the members of resource group `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Give `example_group` `Viewer` role for the members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Update an access group policy

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>--file</dt>
  <dd>JSON file of policy definition</dd>
  <dt>--roles</dt>
  <dd>Role names of the policy definition. For supported roles of a specific service, run 'ibmcloud iam roles --service SERVICE_NAME'. This option is exclusive with '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Service name of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID of service instance of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-region</dt>
  <dd>Region of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Resource type of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource</dt>
  <dd>Resource of the policy definition. This option is exclusive with '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Name of the resource group. This option is exclusive with '--file' and '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID of the resource group. This option is exclusive with '--file' and '--resource-group-name'.</dd>
</dl>

<strong>Examples</strong>:

Update access group policy with the one in policy JSON file:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Update access group policy to give `example_group` `Administrator` role for all `sample-service` resources:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Update access group policy to give `example_group` `Editor` role for resource `key123` of `sample-service` instance with GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in `us-south` region:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Update access group policy to give `example_group` `Operator` role for resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Update access group policy to give `example_group` `Viewer` role for members of resource group `sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Update access group policy to give `example_group` `Viewer` role for members of resource group with ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Delete an access group policy

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login

<strong>Command Options</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Force deletion without confirmation</dd>
</dl>

<strong>Examples</strong>:

Delete policy `51b9717e-76b0-4f6a-bda7-b8132431f926` of access group `example_group`:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```

### ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

List the certificate information of a domain.

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>DOMAIN_NAME (required)</dt>
<dd>The domain that hosts the certificate.</dd>
</dl>


<strong>Examples</strong>:

View the certificate information of the domain `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

### ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Add a certificate to the specified domain in the current org.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>DOMAIN (required)</dt>
   <dd>The domain that the certificate is added to.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (required)</dt>
   <dd>The private key file path.</dd>
   <dt>-c <i>CERT_FILE</i> (required)</dt>
   <dd>The certificate file path.</dd>
   <dt>-p <i>PASSWORD</i> (optional)</dt>
   <dd>The password for the certificate.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (optional)</dt>
   <dd>The intermediate certificate file path.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (optional)</dt>
   <dd>The trust store file.</dd>
   </dl>


<strong>Examples</strong>:

Add a certificate to the domain `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

### ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Remove a certificate from the specified domain in current org.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:

   <dl>
   <dt>DOMAIN (required)</dt>
   <dd>Domain to remove the certificate from.</dd>
   <dt>-f  (optional)</dt>
   <dd>Force deletion without confirmation.</dd>
   </dl>
