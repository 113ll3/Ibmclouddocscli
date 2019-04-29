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

# 管理经典基础架构用户
{: #manage-sl-users}

使用以下命令可管理 {{site.data.keyword.cloud}} 经典基础架构用户。
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

要创建用户，请执行以下操作：
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>命令选项</strong>：
<dl>
<dt>--email</dt>
<dd>此用户的电子邮件地址。创建时需要。</dd>
<dt>--password</dt>
<dd>要为此用户设置的密码。如果未提供密码，那么会向用户发送一封电子邮件以生成密码，此密码将在 24 小时后到期。指定“-p generate”选项，以便生成密码。 密码需要超过 8 个字符，包含大写、小写字符以及数字和符号。</dd>
<dt>--from-user</dt>
<dd>要用作创建此用户的模板的基本用户。缺省行为是使用正在运行此命令的用户。--template 中提供的信息将取代此模板。</dd>
<dt>--template</dt>
<dd>描述 https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ 的 JSON 字符串。</dd>
<dt>--api-key</dt>
<dd>为此用户创建 API 密钥。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

将用户的状态设置为 `CANCEL_PENDING`，这将立即禁用帐户，并最终会通过自动内部过程从帐户中除去。
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

要查看用户的详细信息，请执行以下操作：
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>--keys</dt>
<dd>显示用户 API 密钥。</dd>
<dt>--permissions</dt>
<dd>显示分配给此用户的许可权。主用户将不显示许可权。</dd>
<dt>--hardware</dt>
<dd>显示此用户有权访问的硬件。</dd>
<dt>--virtual</dt>
<dd>显示此用户有权访问的虚拟访客。</dd>
<dt>--logins</dt>
<dd>显示此用户最近 30 天的登录历史记录。</dd>
<dt>--events</dt>
<dd>显示此用户的审计日志。</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

要编辑用户的详细信息，请执行以下操作：
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>--template</dt>
<dd>描述 https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ 的 JSON 字符串。</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

要启用或禁用特定用户许可权，请执行以下操作：
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>--enable</dt>
<dd>启用或禁用所选许可权。接受的输入为“true”和“false”。缺省值为“true”。</dd>
<dt>--permission</dt>
<dd>要设置的许可权 `keyName`，允许使用多个实例。使用关键字 ALL 可选择所有许可权。</dd>
<dt>--from-user</dt>
<dd>将许可权设置为与此用户的许可权相匹配。添加和除去相应的许可权。</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

要列出用户，请执行以下操作：
```
ibmcloud sl user list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--column</dt>
<dd>要显示的列。[选项为：id、username、email、displayName、status、hardwareCount 或 virtualGuestCount]  [default: id,username,email,displayName]。</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

要查看用户许可权，请执行以下操作：
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

