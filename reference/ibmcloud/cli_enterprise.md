---

copyright:
  years: 2018, 2021
lastupdated: "2021-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing enterprises, account groups, and accounts (ibmcloud enterprise)
{: #ibmcloud_enterprise}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage enterprise, account groups, and accounts.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create}

Create an enterprise.
```bash
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_create_options}

NAME (required)
:   Enterprise name.

-d, --domain DOMAIN_NAME (optional)
:   Domain name.

--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)
:   Primary contact user ID of the enterprise.

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update}

Update enterprise information.
```bash
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_update_options}

-f, --force (optional)
:   Update without confirmation.

-n, --name NEW_NAME (required)
:   New name of the enterprise.

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show}

Display details of the enterprise.
```bash
ibmcloud enterprise show
```
{: codeblock}

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create}

Create an account group.
```bash
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_group_create_options}

NAME (required)
:   Account group name.

--parent-account-group ACCOUNT_GROUP_NAME (optional)
:   Name of the parent account group. If omitted, the parent would be the current enterprise.

--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)
:   Primary contact user ID of the account group.

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update}

Update an account group.
```bash
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME)
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_group_update_options}

--id ID (required)
:   ID of target account group. This option is exclusive with `-n, --name`.

-n, --name NAME (required)
:   Name of target account group. This option is exclusive with `--id`.

--new-name NEW_NAME (required)
:   New name of target account group.

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group}

Display details of account group.
```bash
ibmcloud enterprise account-group (-n, --name NAME | --id ID)
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_group_options}

--id ID (required)
:   ID of the account group. This option is exclusive with `-n, --name`.

-n, --name NAME (required)
:   Name of the account group. This option is exclusive with `--id`.

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups}

List account groups.
```bash
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_groups_options}

--parent-account-group ACCOUNT_GROUP_NAME (optional)
:   Name of the parent account group. This option is exclusive with `--parent-account-group-id`.

--parent-account-group-id ACCOUNT_GROUP_ID (optional)
:   ID of the parent account group. This option is exclusive with `--parent-account-group`.

--recursive (optional)
:   Show descendant account groups.

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create}

Create an account.
```bash
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_create_options}

NAME (required)
:   Account group name.

--owner USER_ID (optional)
:   User ID of the account group.

--parent-account-group ACCOUNT_GROUP_NAME (optional).
:   Name of the parent account group. If omitted, the parent would be the current enterprise.

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move}

Move an account under different parent.
```bash
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_move_options}

--id ID (required)
:   ID of target account. This option is exclusive with `-n, --name`.

-n, --name NAME (required)
:   Name of target account. This option is exclusive with `--id`.

--parent-account-group ACCOUNT_GROUP_NAME (required)
:   Name of parent account group. This option is exclusive with `--parent-account-group-id` and `--parent-enterprise`.

--parent-account-group-id ACCOUNT_GROUP_ID (required)
:   ID of parent account group. This option is exclusive with `--parent-account-group` and `--parent-enterprise`.

--parent-enterprise (required)
:   Set enterprise as the parent. This option is exclusive with `--parent-account-group` and `--parent-account-group-id`.

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show}

Display details of an account.
```bash
ibmcloud enterprise account-show (-n, --name NAME | --id ID)
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_show_options}

--id ID (required)
:   ID of the account. This option is exclusive with `-n, --name`.

-n, --name NAME (required)
:   Name of the account. This option is exclusive with `--id`.

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts}

List accounts.
```bash
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_accounts_options}

--parent-account-group ACCOUNT_GROUP_NAME (optional)
:   Name of the parent account group. This option is exclusive with `--parent-account-group-id`.

--parent-account-group-id ACCOUNT_GROUP_ID (optional)
:   ID of the parent account group. This option is exclusive with `--parent-account-group`.

--recursive (optional)
:   Show descendant accounts.

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import}

Import a stand-alone account.
```bash
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```
{: codeblock}

### Command options
{: #ibmcloud_enterprise_account_import_options}

--account-id
:   ID of source account.

--parent-account-group PARENT_ACCOUNT_GROUP (optional)
:   Name of the parent account group. This option is exclusive with `--parent-account-group-id`.

--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (optional)
:   ID of the parent account group. This option is exclusive with `--parent-account-group`.
