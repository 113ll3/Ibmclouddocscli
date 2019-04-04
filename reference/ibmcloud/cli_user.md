---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing classic infrastructure users
{: #manage-sl-users}

Use the following commands to manage {{site.data.keyword.cloud}} classic infrastructure users.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

To create a user:
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Command options</strong>:
<dl>
<dt>--email</dt>
<dd>Email address for this user. Required for creation.</dd>
<dt>--password</dt>
<dd>Password to set for this user. If no password is provided, the user is sent an email to generate one, which expires in 24 hours. Specify the '-p generate' option to generate a password for you. Passwords require 8+ characters, upper and lowercase, a number and a symbol.</dd>
<dt>--from-user</dt>
<dd>Base user to use as a template for creating this user. The default is to use the user that is running this command. Information provided in --template supersedes this template.</dd>
<dt>--template</dt>
<dd>A JSON string that describes https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
<dt>--api-key</dt>
<dd>Create an API key for this user.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Sets a user's status to `CANCEL_PENDING`, which immediately disables the account, and is eventually removed from the account by an automated internal process.
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

To view a user's details:
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>--keys</dt>
<dd>Show the users API key.</dd>
<dt>--permissions</dt>
<dd>Display permissions assigned to this user. Master users will show no permissions.</dd>
<dt>--hardware</dt>
<dd>Display hardware this user has access to.</dd>
<dt>--virtual</dt>
<dd>Display virtual guests this user has access to.</dd>
<dt>--logins</dt>
<dd>Show login history of this user for the last 30 days.</dd>
<dt>--events</dt>
<dd>Show audit log for this user.</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

To edit a user's details:
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>--template</dt>
<dd>A JSON string that describes https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

To enable or disable specific user permissions:
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>--enable</dt>
<dd>Enable or Disable selected permissions. Accepted inputs are 'true' and 'false'. The default is 'true'.</dd>
<dt>--permission</dt>
<dd>Permission `keyName` to set, multiple instances allowed. Use keyword ALL to select ALL permissions.</dd>
<dt>--from-user</dt>
<dd>Set permissions to match this user's permissions. Adds and removes the appropriate permissions.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

To list users:
```
ibmcloud sl user list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--columns</dt>
<dd>Columns to display. [options: id,username,email,displayName,status,hardwareCount,virtualGuestCount]  [default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

To view user permissions:
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

