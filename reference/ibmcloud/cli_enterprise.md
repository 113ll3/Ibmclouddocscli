---

copyright:
  years: 2018, 2020
lastupdated: "2020-03-31"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing enterprises, account groups, and accounts (ibmcloud enterprise)
{: #ibmcloud_enterprise}

Use the following commands to manage enterprise, account groups, and accounts.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Create an enterprise.
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>NAME (required)</dt>
<dd>Enterprise name.</dd>
<dt>-d, --domain DOMAIN_NAME (optional)</dt>
<dd>Domain name.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)</dt>
<dd>Primary contact user ID of the enterprise.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Update enterprise information.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>-f, --force (optional)</dt>
<dd>Update without confirmation.</dd>
<dt>-n, --name NEW_NAME (required)</dt>
<dd>New name of the enterprise.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Display details of the enterprise.
```
ibmcloud enterprise show
```

<strong>Prerequisites</strong>:  Endpoint, Login

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Create an account group.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>NAME (required)</dt>
<dd>Account group name.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name of the parent account group. If omitted, the parent would be the current enterprise.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)</dt>
<dd>Primary contact user ID of the account group.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Update an account group.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME)
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--id ID (required)</dt>
<dd>ID of target account group. This option is exclusive with `-n, --name`.</dd>
<dt>-n, --name NAME (required)</dt>
<dd>Name of target account group. This option is exclusive with `--id`.</dd>
<dt>--new-name NEW_NAME (required)</dt>
<dd>New name of target account group.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Display details of account group.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID)
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--id ID (required)</dt>
<dd>ID of the account group. This option is exclusive with `-n, --name`.</dd>
<dt>-n, --name NAME (required)</dt>
<dd>Name of the account group. This option is exclusive with `--id`.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

List account groups.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name of the parent account group. This option is exclusive with `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID of the parent account group. This option is exclusive with `--parent-account-group`.</dd>
<dt>--recursive (optional)</dt>
<dd>Show descendant account groups.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Create an account.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>NAME (required)</dt>
<dd>Account group name.</dd>
<dt>--owner USER_ID (optional)</dt>
<dd>User ID of the account group.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional).</dt>
<dd>Name of the parent account group. If omitted, the parent would be the current enterprise.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Move an account under different parent.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--id ID (required)</dt>
<dd>ID of target account. This option is exclusive with `-n, --name`.</dd>
<dt>-n, --name NAME (required)</dt>
<dd>Name of target account. This option is exclusive with `--id`.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (required)</dt>
<dd>Name of parent account group. This option is exclusive with `--parent-account-group-id` and `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (required)</dt>
<dd>ID of parent account group. This option is exclusive with `--parent-account-group` and `--parent-enterprise`.</dd>
<dt>--parent-enterprise (required)</dt>
<dd>Set enterprise as the parent. This option is exclusive with `--parent-account-group` and `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Display details of an account.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID)
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--id ID (required)</dt>
<dd>ID of the account. This option is exclusive with `-n, --name`.</dd>
<dt>-n, --name NAME (required)</dt>
<dd>Name of the account. This option is exclusive with `--id`.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

List accounts.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name of the parent account group. This option is exclusive with `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID of the parent account group. This option is exclusive with `--parent-account-group`.</dd>
<dt>--recursive (optional)</dt>
<dd>Show descendant accounts.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Import a stand-alone account.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
<dt>--account-id</dt>
<dd>ID of source account.</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (optional)</dt>
<dd>Name of the parent account group. This option is exclusive with `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID of the parent account group. This option is exclusive with `--parent-account-group`.</dd>
</dl>
