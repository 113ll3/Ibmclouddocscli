---

copyright:
  years: 2018, 2022
lastupdated: "2022-12-14"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing accounts, users, and Cloud Foundry orgs (ibmcloud account)
{: #ibmcloud_commands_account}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage accounts, users in an account, and the org, space, and roles of public Cloud Foundry environments.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

List all organizations:
```bash
ibmcloud account orgs [-r REGION_NAME] [--guid] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```
{: codeblock}

### Command options
{: #ibmcloud_account_orgs_options}

-r REGION_NAME
:   Region name. List the organizations in the region specified. Default to current region if not specified. If set to 'all', list the organizations in all regions.

--guid
:   Display the guid of the organizations. This option is exclusive with `--output`.

-c ACCOUNT_ID
:   Account ID. List the organizations under the account. Default to current account if not specified. If set to `all`, list organizations under all accounts. This option is exclusive with `-u`.

-u ACCOUNT_OWNER
:   Account owner name. List the organizations under the accounts that are owned by the user. Default to current account if not specified. If set to 'all', list organizations under all accounts. This option is exclusive with `-c`.

### Examples
{: #iibmcloud_account_orgs_examples}

List all the organizations in region `us-south` with the GUID displayed:
```bash
ibmcloud account orgs -r us-south --guid
```
{: codeblock}

List all the organizations in JSON format:
```bash
ibmcloud account orgs --output JSON
```
{: codeblock}

## ibmcloud account org
{: #ibmcloud_account_org}

Show the information of the specified organization:
```bash
ibmcloud account org ORG_NAME [-r REGION] [--guid]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_options}

ORG_NAME (required)
:   The name of the organization.

-r REGION
:   Region name. If not specified, the default is current region. If set to `all`, orgs with the given name in all regions are listed.

--guid
:   Retrieve and display the org's guid. All other output for the org is suppressed. This option is exclusive with `--output`.

### Examples
{: #ibmcloud_account_org_examples}

Show the information of organization `IBM` with the GUID displayed:
```bash
ibmcloud account org IBM --guid
```
{: codeblock}

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Create an organization. This operation can be run only by the account owner.
```bash
ibmcloud account org-create ORG_NAME [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_create_options}

ORG_NAME (required)
:   The name of the organization to be created.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


### Examples
{: #ibmcloud_account_org_create_examples}

Create an organization named `IBM`:
```bash
ibmcloud account org-create IBM
```
{: codeblock}

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replicate an org from the current region to another region:
```bash
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_replicate_options}

ORG_NAME (required)
:   The name of the existing org that is to be replicated.

REGION_NAME (required)
:   The name of the region that hosts the replicated org.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.

### Examples
{: #ibmcloud_account_org_replicate_examples}

Replicate the org `myorg` to the region `eu-gb`:
```bash
ibmcloud account org-replicate myorg eu-gb
```
{: codeblock}

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rename an organization. This operation can be done only by an org manager.
```bash
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_rename_options}

OLD_ORG_NAME (required)
:   The old name of the org that is to be renamed.

NEW_ORG_NAME (required)
:   The new name of the org that is to be renamed.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

List all account spaces:
```bash
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```
{: codeblock}

### Command options
{: #ibmcloud_account_spaces_options}

-o ORG_NAME (optional)
:   Organization name. List the spaces under the organization specified. Default to current organization if not specified.

-r REGION-NAME (optional)
:   Region name. List the spaces under the region specified. Default to current region if not specified.

### Examples
{: #ibmcloud_account_spaces_examples}

List all spaces:
```bash
ibmcloud account spaces
```
{: codeblock}

List all spaces of org `org_example` in JSON format:
```bash
ibmcloud account spaces -o org_example --output JSON
```
{: codeblock}

## ibmcloud account space
{: #ibmcloud_account_space}

Show the information of a specific space:
```bash
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid] [--security-group-rules]
```
{: codeblock}

### Command options
{: #ibmcloud_account_space_options}

SPACE_NAME (required)
:   Name of space to be shown.

-o ORG_NAME
:   Organization name. Default to current organization if not specified.

--guid
:   Retrieve and display the space's guid. All other output for the space is suppressed. This option is exclusive with `--output`.

--security-group-rules
:   Retrieve the rules for all the security groups associated with the space.

### Examples
{: #ibmcloud_account_space_examples}

Show the information of space `space_example`:
```bah
ibmcloud account space space_example
```
{: codeblock}

Show the GUID of space `space_example`:
```bash
ibmcloud account space space_example --guid
```
{: codeblock}

Show the information of space `space_example` in JSON format:
```bash
ibmcloud account space space_example --output JSON
```
{: codeblock}

Show the security group rules of space `space_example`:
```bash
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
```bash
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_users_options}

ORG_NAME (required)
:   The name of the organization.

-a, -all (optional)
:   List all the users in the specified organization, not grouped by role.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Add a user into org (org manager required):
```bash
ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_user_add_options}

USER_NAME (required)
:   The name of the user.
ORG (required)
:   The name of the organization.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Remove a user from org (org manager or user only):
```bash
ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

### Command options
{: #ibmcloud_account_org_user_remove_options}

--force, -f
:   Force deletion without confirmation.


## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Get all organization roles of the current user:
```bash
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_roles_options}

-u
:   User ID. If not specified, default to current user.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assign an organization role to a user. This operation must be run by an organization manager.
```bash
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_role_set_options}

USER_NAME (required)
:   The name of the user to be assigned.

ORG_NAME (required)
:   The name of the organization this user is assigned to.

ORG_ROLE (required)
:   The name of the organization role this user is assigned to. For example:

 OrgManager: This role can invite and manage users, select and change plans, and set spending limits.

 BillingManager: This role can create and manage the billing account and payment information.

 OrgAuditor: This role has read-only access to org information and reports.



-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


### Examples
{: #ibmcloud_account_org_role_set_examples}

Assign user `Mary` to the organization `IBM` as `OrgManager` role:
```bash
ibmcloud account org-role-set Mary IBM OrgManager
```
{: codeblock}

You can set org and space roles by using the CLI, but if you want to set the other permissions, you must use the UI. For more information, see [Managing access to resources](/docs/account?topic=account-assign-access-resources).
{: note}

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Remove an organization role from a user. This operation can be run by an organization manager.
```bash
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_role_unset_options}

USER_NAME (required)
:   The name of the user to be removed.

ORG_NAME (required)
:   The name of the organization this user is removed from.

ORG_ROLE (required)
:   The name of the organization role this user is removed from. For example:

 OrgManager: This role can invite and manage users, select and change plans, and set spending limits.

 BillingManager: This role can create and manage the billing account and payment information.

 OrgAuditor: This role has read-only access to org information and reports.



-r, --region REGION (optional)
:   Region name. Default to current region if not specified.

### Examples
{: #ibmcloud_account_org_role_unset_examples}

Remove user `Mary` from the organization `IBM` as `OrgManager` role:
```bash
ibmcloud account org-role-unset Mary IBM OrgManager
```
{: codeblock}

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Display users in the specified space by role:
```bash
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_space_users_options}

ORG_NAME (required)
:   The name of the organization.

SPACE_NAME (required)
:   The name of the space.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

Get all space roles of current user under specific org:
```bash
ibmcloud account space-roles ORG [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_space_roles_options}

ORG (required)
:   The name of the organization.

-r (optional)
:   Region name. Default to current region if not specified.

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assign a space role to a user. This operation can be run only by a space manager.
```bash
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_space_role_set_options}

USER_NAME (required)
:   The name of the user to be assigned.

ORG_NAME (required)
:   The name of the organization this user is assigned to.

SPACE_NAME (required)
:   The name of the space this user is assigned to.

SPACE_ROLE (required)
:   The name of the space role this user is assigned to. For example:

 SpaceManager: This role can invite and manage users, and enable features.

 SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.

 SpaceAuditor: This role can view logs, reports, and settings for the space.

-r, --region REGION (optional)
:   Region name. Default to current region if not specified.

### Examples
{: #ibmcloud_account_space_role_set_examples}

Assign user `Mary` to the organization `IBM` and space `Cloud` as `SpaceManager` role:
```bash
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```
{: codeblock}

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Remove a space role from a user. This operation can be run only by a space manager.
```bash
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_space_role_unset_options}

USER_NAME (required)
:   The name of the user to be removed.

ORG_NAME (required)
:   The name of the organization this user is removed from.

SPACE_NAME (required)
:   The name of the space this user is removed from.

SPACE_ROLE (required)
:   The name of the space role this user is removed from. For example:

 SpaceManager: This role can invite and manage users, and enable features.

 SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.

 SpaceAuditor: This role can view logs, reports, and settings for the space.


-r, --region REGION (optional)
:   Region name. Default to current region if not specified.


### Examples
{: #ibmcloud_account_space_role_unset_examples}

Remove user `Mary` from the organization `IBM` and space `Cloud` as `SpaceManager` role:
```bash
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```
{: codeblock}

## ibmcloud account list
{: #ibmcloud_account_list}

List all accounts of the current user:
```bash
ibmcloud account list
```
{: codeblock}

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Display the account of specified organization(org user required).
```bash
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid]
```
{: codeblock}

### Command options
{: #ibmcloud_account_org_account_options}

-r (optional)
:   Region name. Default to current region if not specified.

--guid (optional)
:   Display account ID only

## ibmcloud account show
{: #ibmcloud_account_show}

Show account details:
```bash
ibmcloud account show
```
{: codeblock}

### Examples
{: #ibmcloud_account_show_examples}

Show details of currently targeted account:
```bash
ibmcloud account show
```
{: codeblock}

## ibmcloud account update
{: #ibmcloud_account_update}

Update a specific account:
```bash
ibmcloud account update (--service-endpoint-enable true | false)
```
{: codeblock}

### Command options
{: #ibmcloud_account_update_options}

--service-endpoint-enable true | false
:   Enable or disable service endpoints connectivity for a SoftLayer account.


### Examples
{: #ibmcloud_account_update_examples}

Enable service endpoint connectivity for current account:
```bash
ibmcloud account update --service-endpoint-enable true
```
{: codeblock}

## Classic infrastructure account audit-logs
{: #classic_account_audit_logs}

List SoftLayer account audit logs:
```bash
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```
{: codeblock}

### Command options
{: #classic_account_audit_logs_options}

-a, --action *ACTION*
:   Action. List audit logs with the action.

-e, --end-date *END_DATE*
:   End date. List audit logs before the end date. Supported formats are yyyy-MM-ddTHH:mm:ss.

o, --object *OBJECT*
:   Object. List audit logs with the object.

t, --object-type *OBJECT_TYPE*
:   Object type. List audit logs with the object type.

s, --start-date *START_DATE*
:   Start date. List audit logs after the start date. Supported formats are yyyy-MM-ddTHH:mm:ss.

u, --user-name *USER_NAME*
:   User name. List audit logs with the user name.

### Examples
{: #classic_account_audit_logs_examples}

List audit logs:
```bash
ibmcloud account audit-logs
```
{: codeblock}

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

List account audit logs:
```bash
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE]
```
{: codeblock}

### Command options
{: #ibmcloud_account_audit_logs_options}

--user-name *USER_NAME* (optional)
:   List audit logs with the user name.

--object-type *OBJECT_TYPE* (optional)
:   List audit logs with the object type.

--object *OBJECT* (optional)
:   List audit logs with the object.

--action *ACTION* (optional)
:   List audit logs with the action.

--start-date *START_DATE* (optional)
:   List audit logs after the start date. Supported formats are yyyy-MM-ddTHH:mm:ss.

--end-date *END_DATE* (optional)
:   List audit logs before the end date. Supported formats are yyyy-MM-ddTHH:mm:ss.


## ibmcloud account users
{: #ibmcloud_account_users}

Displays users that are associated with the account. To view the required permissions to run this command,
see [Retrieve users in the account](/apidocs/user-management#list-users).
```bash
ibmcloud account users [-c, --account-id ACCOUNT_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_account_users_options}

-c (optional)
:   Account ID. If not specified, default to current account.

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Remove a user from an account (account owner only).
```bash
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_remove_options}

USER_ID (required)
:   User ID

-c ACCOUNT_ID
:   Account ID. If not specified, default to current account.

-f, --force
:   Force removal without confirmation.

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invite a user to the account:
```bash
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]] [-r, --region REGION]
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_invite_options}

USER_EMAIL (required)
:   The email of the user to be invited.

-o, --org ORG (deprecated)
:   Organization to invite user to.

--org-role ORG_ROLE (deprecated)
:   Organization role. Valid inputs are: `OrgManager`, `BillingManager`, `OrgAuditor`, and `OrgUser`. If omitted, the `OrgUser` role is set.

-s, --space SPACE (deprecated)
:   Space to invite user to.

--space-role SPACE_ROLE (deprecated)
:   Space role. Valid inputs are: `SpaceManager`, `SpaceDeveloper`, and `SpaceAuditor`.

-r, --region REGION (deprecated)
:   Region name. Defaults to current region if not specified.


If you aren't ready to assign access, or want to assign an IAM policy instead of Cloud Foundry access, you can invite a user and assign it later. For more information about assigning access to users, see [Managing access to resources](/docs/account?topic=account-assign-access-resources).
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Resend invitation to a user (account admin):
```bash
ibmcloud account user-reinvite USER_EMAIL
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_reinvite_options}

USER_EMAIL (required)
:   The email of the user to be invited again.

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

Show user preference details:
```bash
ibmcloud account user-preference
```
{: codeblock}

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

Update user preferences:
```bash
ibmcloud account user-preference-update (--position NEW_POSITION)
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_preference_update_options}

--position *NEW_POSITION* (optional)
:   Set a user's position, such as `manager` or `student`.

## ibmcloud account user-status
{: #ibmcloud_account_user_status}

Show user's status:
```bash
ibmcloud account user-status [USER_ID] [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_status_options}

USER_ID
:   User ID. If not specified, default to current user. Required if `--status` is used.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

## ibmcloud account user-status-update
{: #ibmcloud_account_user_status_update}

Update user's status:
```bash
ibmcloud account user-status-update USER_ID NEW_STATUS [--output FORMAT] [-q, --quiet]
```
{: codeblock}

### Command options
{: #ibmcloud_account_user_status_update_options}

USER_ID (required)
:   User ID.

NEW_STATUS (required)
:   Set a user's status, such as `SUSPENDED` or `ACTIVE`. For more information, see [User account status](https://cloud.ibm.com/apidocs/user-management#user-states) for a list of possible statuses. This option can also take in values in lowercase such as `suspended` or `active`.

--output FORMAT
:   Specify output format. Only 'JSON' is supported.

-q, --quiet
:   Suppress verbose output.

### Examples
{: #ibmcloud_account_user_status_update_examples}

Suspend user `user@ibm.com`:
```bash
ibmcloud account user-status-update user@ibm.com SUSPENDED
```

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

Subscribe platform notification:
```bash
ibmcloud account platform-notification-subscribe (--type TYPE)
```
{: codeblock}

### Command options
{: #ibmcloud_account_platform_notification_subscribe_options}

--type *TYPE* (optional)
:   Notification type, one of `unplanned_events`, `planned_maintenance`.

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

Unsubscribe platform notification:
```bash
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
{: codeblock}

### Command options
{: #ibmcloud_account_platform_notification_unsubscribe_options}

--type *TYPE* (optional)
:   Notification type, one of `unplanned_events`, `planned_maintenance`.


## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

List the certificate information of a domain:
```bash
ibmcloud account domain-cert DOMAIN_NAME
```
{: codeblock}

### Command options
{: #ibmcloud_account_domain_cert_options}

DOMAIN_NAME (required)
:   The domain that hosts the certificate.

### Examples
{: #ibmcloud_account_domain_cert_examples}

View the certificate information of the domain `ibmcxo-eventconnect.com`:
```bash
ibmcloud account domain-cert ibmcxo-eventconnect.com
```
{: codeblock}

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

Add a certificate to the specified domain in the current org:
```bash
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```
{: codeblock}

### Command options
{: #ibmcloud_account_domain_cert_add_options}

DOMAIN (required)
:   The domain that the certificate is added to.

-k *PRIVATE_KEY_FILE* (required)
:   The private key file path.

-c *CERT_FILE* (required)
:   The certificate file path.

-p *PASSWORD* (optional)
:   The password for the certificate.

-i *INTERMEDIATE_CERT_FILE* (optional)
:   The intermediate certificate file path.

-t *TRUST_STORE_FILE* (optional)
:   The truststore file.

### Examples
{: #ibmcloud_account_domain_cert_add_examples}

Add a certificate to the domain `ibmcxo-eventconnect.com`:
```bash
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```
{: codeblock}

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

Remove a certificate from the specified domain in current org:
```bash
ibmcloud account domain-cert-remove DOMAIN [-f]
```
{: codeblock}

### Command options
{: #ibmcloud_account_domain_cert_remove_options}

DOMAIN (required)
:   Domain to remove the certificate from.

-f  (optional)
:   Force deletion without confirmation.
