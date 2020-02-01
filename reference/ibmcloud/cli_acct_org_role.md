---

copyright:
  years: 2018, 2020
lastupdated: "2020-01-24"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}
{:external: target="_blank" .external}

# Managing accounts, users, and Cloud Foundry orgs
{: #ibmcloud_commands_account}

Use the following commands to manage accounts, users in an account, and the org, space, and roles of public Cloud Foundry environments.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

List all organizations:
```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Region name. List the organizations in the region specified. Default to current region if not specified. If set to 'all', list the organizations in all regions.</dd>
   <dt>--guid</dt>
   <dd>Display the guid of the organizations. This option is exclusive with `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format, only JSON is supported now. This option is exclusive with `--guid`.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>Account ID. List the organizations under the account. Default to current account if not specified. If set to `all`, list organizations under all accounts. This option is exclusive with `-u`.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Account owner name. List the organizations under the accounts that are owned by the user. Default to current account if not specified. If set to 'all', list organizations under all accounts. This option is exclusive with `-c`.</dd>
   </dl>

<strong>Examples</strong>:

List all the organizations in region `us-south` with the GUID displayed:
```
ibmcloud account orgs -r us-south --guid
```

List all the organizations in JSON format:
```
ibmcloud account orgs --output JSON
```
{: codeblock}

## ibmcloud account org
{: #ibmcloud_account_org}

Show the information of the specified organization:
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>-r REGION</dt>
   <dd>Region name. If not specified, the default is current region. If set to `all`, orgs with the given name in all regions are listed.</dd>
   <dt>--guid</dt>
   <dd>Retrieve and display the org's guid. All other output for the org is suppressed. This option is exclusive with `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format. Only JSON is supported. This option is exclusive with `--guid`.</dd>
   </dl>

<strong>Examples</strong>:

Show the information of organization `IBM` with the GUID displayed:
```
ibmcloud account org IBM --guid
```
{: codeblock}

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Create an organization. This operation can be run only by the account owner.
```
ibmcloud account org-create ORG_NAME [-r, --region REGION] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization to be created.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl>

<strong>Examples</strong>:

Create an organization named `IBM`:
```
ibmcloud account org-create IBM 
```
{: codeblock}

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replicate an org from the current region to another region:
```
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the existing org that is to be replicated.</dd>
   <dt>REGION_NAME (required)</dt>
   <dd>The name of the region that hosts the replicated org.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl>

<strong>Examples</strong>:

Replicate the org `myorg` to the region `eu-gb`:
```
ibmcloud account org-replicate myorg eu-gb
```
{: codeblock}

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rename an organization. This operation can be done only by an org manager.
```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>OLD_ORG_NAME (required)</dt>
   <dd>The old name of the org that is to be renamed.</dd>
   <dt>NEW_ORG_NAME (required)</dt>
   <dd>The new name of the org that is to be renamed.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

List all account spaces:
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>-o ORG_NAME (optional)</dt>
   <dd>Organization name. List the spaces under the organization specified. Default to current organization if not specified.</dd>
   <dt>-r REGION-NAME (optional)</dt>
   <dd>Region name. List the spaces under the region specified. Default to current region if not specified.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
   </dl>

<strong>Examples</strong>:

List all spaces:
```
ibmcloud account spaces
```
{: codeblock}

List all spaces of org `org_example` in JSON format:
```
ibmcloud account spaces -o org_example --output JSON
```
{: codeblock}

## ibmcloud account space
{: #ibmcloud_account_space}

Show the information of a specific space:
```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>SPACE_NAME (required)</dt>
   <dd>Name of space to be shown.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>Organization name. Default to current organization if not specified.</dd>
   <dt>--guid</dt>
   <dd>Retrieve and display the space's guid. All other output for the space is suppressed. This option is exclusive with `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specify output format. Only JSON is supported. All other output for the space is suppressed. This option is exclusive with `--guid`.</dd>
   <dt>--security-group-rules</dt>
   <dd>Retrieve the rules for all the security groups associated with the space.</dd>
   </dl>

<strong>Examples</strong>:

Show the information of space `space_example`:
```
ibmcloud account space space_example
```
{: codeblock}

Show the GUID of space `space_example`:
```
ibmcloud account space space_example --guid
```
{: codeblock}

Show the information of space `space_example` in JSON format:
```
ibmcloud account space space_example --output JSON
```
{: codeblock}

Show the security group rules of space `space_example`:
```
ibmcloud account space space_example --security-group-rules
```
{: codeblock}

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

This command has the same function and options as the [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: external} command.

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

This command has the same function and options as the [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: external} command.

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

This command has the same function and options as the [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: external} command.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Display users in the specified organization by role:
```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>-a, -all (optional)</dt>
   <dd>List all the users in the specified organization, not grouped by role.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Add a user into org (org manager required):
```
ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```

<strong>Command options</strong>:
<dl>
<dt>USER_NAME (required)</dt>
<dd>The name of the user.</dd>
<dt>ORG (required)</dt>
<dd>The name of the organization.</dd>
<dt>-r, --region REGION (optional)</dt>
<dd>Region name. Default to current region if not specified.</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Remove a user from org (org manager or user only):
```
ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Command options</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Force deletion without confirmation.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Get all organization roles of the current user:
```
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>-u</dt>
   <dd>User ID. If not specified, default to current user.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assign an organization role to a user. This operation must be run by an organization manager.
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user to be assigned.</dd>
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
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Assign user `Mary` to the organization `IBM` as `OrgManager` role:
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
You can set org and space roles by using the CLI, but if you want to set the other permissions, you must use the UI. For more information, see [Managing access to resources](/docs/iam?topic=iam-iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Remove an organization role from a user. This operation can be run by an organization manager.
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user to be removed.</dd>
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
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   </dl>

<strong>Examples</strong>:

Remove user `Mary` from the organization `IBM` as `OrgManager` role:
```
ibmcloud account org-role-unset Mary IBM OrgManager
```
{: codeblock}

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Display users in the specified space by role:
```
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space.</dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

Get all space roles of current user under specific org:
```
ibmcloud account space-roles ORG [-r, --region REGION] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
   <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>-r (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assign a space role to a user. This operation can be run only by a space manager.
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user to be assigned.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space this user is assigned to.</dd>
   <dt>SPACE_ROLE (required)</dt>
   <dd>The name of the space role this user is assigned to. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
   </dl>

<strong>Examples</strong>:

Assign user `Mary` to the organization `IBM` and space `Cloud` as `SpaceManager` role:
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```
{: codeblock}

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Remove a space role from a user. This operation can be run only by a space manager.
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

   <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user to be removed.</dd>
   <dt>ORG_NAME (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>SPACE_NAME (required)</dt>
   <dd>The name of the space this user is removed from.</dd>
   <dt>SPACE_ROLE (required)</dt>
   <dd>The name of the space role this user is removed from. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
   <dt>-r, --region REGION (optional)</dt>
   <dd>Region name. Default to current region if not specified.</dd>
    </dl>

<strong>Examples</strong>:

Remove user `Mary` from the organization `IBM` and space `Cloud` as `SpaceManager` role:
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```
{: codeblock}

## ibmcloud account list
{: #ibmcloud_account_list}

List all accounts of the current user:
```
ibmcloud account list [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format, only JSON is supported now.</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Display the account of specified organization(org user required).
```
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid | --output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
  <dt>-r (optional)</dt>
  <dd>Region name. Default to current region if not specified.</dd>
  <dt>--guid (optional)</dt>
  <dd>Display account ID only</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format. Only JSON is supported.</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Show account details:
```
ibmcloud account show [--output FORMAT]
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format. Only JSON is supported.</dd>
</dl>

<strong>Examples</strong>:

Show details of currently targeted account:
```
ibmcloud account show
```
{: codeblock}

## ibmcloud account update
{: #ibmcloud_account_update}

Update a specific account:
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Enable or disable service endpoints connectivity for a SoftLayer account.</dd>
</dl>

<strong>Examples</strong>:

Enable service endpoint connectivity for current account:
```
ibmcloud account update --service-endpoint-enable true
```
{: codeblock}

## Classic infrastructure account audit-logs
{: #classic_account_audit_logs}

List SoftLayer account audit logs:
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>Action. List audit logs with the action.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>End date. List audit logs before the end date. Supported formats are yyyy-MM-ddTHH:mm:ss.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>Object. List audit logs with the object.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>Object type. List audit logs with the object type.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>Start date. List audit logs after the start date. Supported formats are yyyy-MM-ddTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>User name. List audit logs with the user name.</dd>
</dl>

<strong>Examples</strong>:

List audit logs:
```
ibmcloud account audit-logs
```
{: codeblock}

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

List account audit logs:
```
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE] [--output FORMAT]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--user-name <i>USER_NAME</i> (optional)</dt>
   <dd>List audit logs with the user name.</dd>
   <dt>--object-type <i>OBJECT_TYPE</i> (optional)</dt>
   <dd>List audit logs with the object type.</dd>
   <dt>--object <i>OBJECT</i> (optional)</dt>
   <dd>List audit logs with the object.</dd>
   <dt>--action <i>ACTION</i> (optional)</dt>
   <dd>List audit logs with the action.</dd>
   <dt>--start-date <i>START_DATE</i> (optional)</dt>
   <dd>List audit logs after the start date. Supported formats are yyyy-MM-ddTHH:mm:ss.</dd>
   <dt>--end-date <i>END_DATE</i> (optional)</dt>
   <dd>List audit logs before the end date. Supported formats are yyyy-MM-ddTHH:mm:ss.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format, only JSON is supported now.</dd>
</dl>

## ibmcloud account users
{: #ibmcloud_account_users}

Displays users that are associated with the account. This operation must be run by the account owner.
```
ibmcloud account users [-c, --account-id ACCOUNT_ID] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>-c (optional)</dt>
<dd>Account ID. If not specified, default to current account.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Specify output format, only JSON is supported now.</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Remove a user from an account (account owner only).
```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>USER_ID (required)</dt>
<dd>User ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Account ID. If not specified, default to current account.</dd>
<dt>-f, --force</dt>
<dd>Force removal without confirmation.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invite a user to the account:
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]] [-r, --region REGION]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be invited.</dd>
   <dt>-o, --org ORG (deprecated)</dt>
   <dd>Organization to invite user to.</dd>
   <dt>--org-role ORG_ROLE (deprecated)</dt>
   <dd>Organization role. Valid inputs are: `OrgManager`, `BillingManager`, `OrgAuditor`, and `OrgUser`. If omitted, the `OrgUser` role is set.</dd>
   <dt>-s, --space SPACE (deprecated)</dt>
   <dd>Space to invite user to.</dd>
   <dt>--space-role SPACE_ROLE (deprecated)</dt>
   <dd>Space role. Valid inputs are: `SpaceManager`, `SpaceDeveloper`, and `SpaceAuditor`.</dd>
   <dt>-r, --region REGION (deprecated)</dt>
   <dd>Region name. Defaults to current region if not specified.</dd>
</dl>

If you aren't ready to assign access, or want to assign an IAM policy instead of Cloud Foundry access, you can invite a user and assign it later. For more information about assigning access to users, see [Managing access to resources](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Resend invitation to a user (account admin):
```
ibmcloud account user-reinvite USER_EMAIL
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be invited again.</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

Show user preference details:
```
ibmcloud account user-preference [--output FORMAT]
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

Update user preferences:
```
ibmcloud account user-preference-update (--position NEW_POSITION) [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--position <i>NEW_POSITION</i> (optional)</dt>
   <dd>Set a user's position, such as `manager` or `student`.</dd>
   <dt>--output FORMAT (optional)</dt>
   <dd>Specify output format. Only JSON is supported.</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

Subscribe platform notification:
```
ibmcloud account platform-notification-subscribe (--type TYPE)
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--type <i>TYPE</i> (optional)</dt>
   <dd>Notification type, one of `unplanned_events`, `planned_maintenance`.</dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

Unsubscribe platform notification:
```
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
   <dt>--type <i>TYPE</i> (optional)</dt>
   <dd>Notification type, one of `unplanned_events`, `planned_maintenance`.</dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

List the certificate information of a domain:
```
ibmcloud account domain-cert DOMAIN_NAME [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
<dl>
<dt>DOMAIN_NAME (required)</dt>
<dd>The domain that hosts the certificate.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Specify output format. Only JSON is supported.</dd>
</dl>

<strong>Examples</strong>:

View the certificate information of the domain `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert ibmcxo-eventconnect.com
```
{: codeblock}

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

Add a certificate to the specified domain in the current org:
```
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
   <dd>The truststore file.</dd>
   </dl>

<strong>Examples</strong>:

Add a certificate to the domain `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```
{: codeblock}

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

Remove a certificate from the specified domain in current org:
```
ibmcloud account domain-cert-remove DOMAIN [-f]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:

   <dl>
   <dt>DOMAIN (required)</dt>
   <dd>Domain to remove the certificate from.</dd>
   <dt>-f  (optional)</dt>
   <dd>Force deletion without confirmation.</dd>
   </dl>
