---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-03"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cli

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing classic infrastructure users (ibmcloud sl user)
{: #manage-sl-users}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure users.
{: shortdesc}

## ibmcloud sl user create
{: #sl_user_create}

Creates a user:
```
ibmcloud sl user create USERNAME [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--email</dt>
<dd>Email address for this user. Required for creation.</dd>
<dt>--password</dt>
<dd>Password to set for this user. If no password is provided, the user is sent an email to generate one, which expires in 24 hours. Specify the '-p generate' option to generate a password for you. Passwords require 8+ characters, uppercase and lowercase, a number and a symbol.</dd>
<dt>--from-user</dt>
<dd>Base user to use as a template for creating this user. The default is to use the user that is running this command. Information provided in --template supersedes this template.</dd>
<dt>--template</dt>
<dd>A JSON string that describes https://softlayer.github.io/reference/datatypes/SoftLayer_User_Customer/.</dd>
<dt>--api-key</dt>
<dd>Create an API key for this user.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:

Create a user with the username `my@email.com`.
```
ibmcloud sl user create my@email.com --email my@email.com --password generate --api-key --template '{"firstName": "Test", "lastName": "Testerson"}'
```
{: codeblock}

Remember to set the permissions and access for this new user.

## ibmcloud sl user delete
{: #sl_user_delete}

Sets a user's status to `CANCEL_PENDING`, which immediately disables the account, and is eventually removed from the account by an automated internal process:
```
ibmcloud sl user delete IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:

Delete a user with the ID `userId`.
```
ibmcloud sl user delete userId
```
{: codeblock}


## ibmcloud sl user detail
{: #sl_user_detail}

View a user's details:
```
ibmcloud sl user detail IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--keys</dt>
<dd>Show the users API key.</dd>
<dt>--permissions</dt>
<dd>Display permissions that are assigned to this user. Master users do not show permissions.</dd>
<dt>--hardware</dt>
<dd>Display hardware this user has access to.</dd>
<dt>--virtual</dt>
<dd>Display virtual guests this user has access to.</dd>
<dt>--logins</dt>
<dd>Show login history of this user for the last 24 hours.</dd>
<dt>--events</dt>
<dd>Show audit log for this user.</dd>
</dl>


## ibmcloud sl user detail-edit
{: #sl_user_detail_edit}

Edit a user's details:
```
ibmcloud sl user detail-edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--template</dt>
<dd>A JSON string that describes https://softlayer.github.io/reference/datatypes/SoftLayer_User_Customer/.</dd>
</dl>

**Examples**:

This command edit a user's details.
```
ibmcloud sl user detail-edit USER_ID --template '{"firstName": "Test", "lastName": "Testerson"}'
```
{: codeblock}

## ibmcloud sl user list 
{: #sl_user_list} 

To list users:
```
ibmcloud sl user list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--column</dt>
<dd>Column to display. options are: id,username,email,displayName,status,hardwareCount,virtualGuestCount. This option can be specified multiple times.</dd>
</dl>

## ibmcloud sl user permission-edit
{: #sl_user_permission_edit}

Enable or disable specific user permissions:
```
ibmcloud sl user permission-edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--enable</dt>
<dd>Enable or disable selected permissions. Accepted inputs are `true` and `false`. The default is `true`.</dd>
<dt>--permission</dt>
<dd>Permission `keyName` to set, multiple instances allowed. Use keyword `ALL` to select ALL permissions.</dd>
<dt>--from-user</dt>
<dd>Set permissions to match this user's permissions. Adds and removes the appropriate permissions.</dd>
</dl>

## ibmcloud sl user permissions
{: #sl_user_permissions}

View user permissions:
```
ibmcloud sl user permissions IDENTIFIER
```
