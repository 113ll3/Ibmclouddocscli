---

copyright:
  years: 2018, 2020
lastupdated: "2020-12-15"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing classic infrastructure users (ibmcloud sl user)
{: #manage-sl-users}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure users.
{: shortdesc}

## ibmcloud sl user create
{: #sl_user_create}

Creates a user:
```bash
ibmcloud sl user create USERNAME [OPTIONS]
```

**Command options**:

--email
:   Email address for this user. Required for creation.

--password
:   Password to set for this user. If no password is provided, the user is sent an email to generate one, which expires in 24 hours. Specify the '-p generate' option to generate a password for you. Passwords require 8+ characters, uppercase and lowercase, a number and a symbol.

--from-user
:   Base user to use as a template for creating this user. The default is to use the user that is running this command. Information provided in --template supersedes this template.

--template
:   A JSON string that describes https://softlayer.github.io/reference/datatypes/SoftLayer_User_Customer/.
--api-key
:   Create an API key for this user.

--vpn-password
:   VPN password to set for this user.

-f, --force
:   Force operation without confirmation.

**Examples**:

Create a user with the username `my@email.com`.
```bash
ibmcloud sl user create my@email.com --email my@email.com --password generate --api-key --template '{"firstName": "Test", "lastName": "Testerson"}'
```
{: codeblock}

Remember to set the permissions and access for this new user.

## ibmcloud sl user delete
{: #sl_user_delete}

Sets a user's status to `CANCEL_PENDING`, which immediately disables the account, and is eventually removed from the account by an automated internal process:
```bash
ibmcloud sl user delete IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:

Delete a user with the ID `userId`.
```bash
ibmcloud sl user delete userId
```
{: codeblock}


## ibmcloud sl user detail
{: #sl_user_detail}

View a user's details:
```bash
ibmcloud sl user detail IDENTIFIER [OPTIONS]
```

**Command options**:

--keys
:   Show the users API key.

--permissions
:   Display permissions that are assigned to this user. Master users do not show permissions.

--hardware
:   Display hardware this user has access to.

--virtual
:   Display virtual guests this user has access to.

--logins
:   Show login history of this user for the last 24 hours.

--events
:   Show audit log for this user.

## ibmcloud sl user detail-edit
{: #sl_user_detail_edit}

Edit a user's details:
```bash
ibmcloud sl user detail-edit IDENTIFIER [OPTIONS]
```

**Command options**:

--template
:   A JSON string that describes https://softlayer.github.io/reference/datatypes/SoftLayer_User_Customer/.

**Examples**:

This command edit a user's details.
```bash
ibmcloud sl user detail-edit USER_ID --template '{"firstName": "Test", "lastName": "Testerson"}'
```
{: codeblock}

## ibmcloud sl user list 
{: #sl_user_list} 

To list users:
```bash
ibmcloud sl user list [OPTIONS]
```

**Command options**:

--column
:   Column to display. options are: id,username,email,displayName,status,hardwareCount,virtualGuestCount. This option can be specified multiple times.

## ibmcloud sl user permission-edit
{: #sl_user_permission_edit}

Enable or disable specific user permissions:
```bash
ibmcloud sl user permission-edit IDENTIFIER [OPTIONS]
```

**Command options**:

--enable
:   Enable or disable selected permissions. Accepted inputs are `true` and `false`. The default is `true`.

--permission
:   Permission `keyName` to set, multiple instances allowed. Use keyword `ALL` to select ALL permissions.

--from-user
:   Set permissions to match this user's permissions. Adds and removes the appropriate permissions.
</dl>

## ibmcloud sl user permissions
{: #sl_user_permissions}

View user permissions:
```bash
ibmcloud sl user permissions IDENTIFIER
```
