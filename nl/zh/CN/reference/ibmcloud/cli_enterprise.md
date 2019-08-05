---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理企业、帐户组和帐户
{: #ibmcloud_enterprise}

使用以下命令可管理企业、帐户组和帐户。
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

创建一个企业。
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>NAME（必需）</dt>
<dd>企业名称。</dd>
<dt>-d, --domain DOMAIN_NAME（可选）</dt>
<dd>域名。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID（可选）</dt>
<dd>企业的主要联系人用户标识。</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

更新企业信息。
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>-f, --force（可选）</dt>
<dd>更新而不确认。</dd>
<dt>-n, --name NEW_NAME（必需）</dt>
<dd>企业的新名称。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

显示企业的详细信息。
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

创建一个帐户组。
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>NAME（必需）</dt>
<dd>帐户组名称。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（可选）</dt>
<dd>父帐户组的名称。如果省略，父代将为当前企业。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID（可选）</dt>
<dd>帐户组的主要联系人用户标识。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

更新帐户组。
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--id ID（必需）</dt>
<dd>目标帐户组的标识。此选项与 `-n, --name` 互斥。</dd>
<dt>-n, --name NAME（必需）</dt>
<dd>目标帐户组的名称。此选项与 `--id` 互斥。</dd>
<dt>--new-name NEW_NAME（必需）</dt>
<dd>目标帐户组的新名称。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

显示帐户组的详细信息。
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--id ID（必需）</dt>
<dd>帐户组的标识。此选项与 `-n, --name` 互斥。</dd>
<dt>-n, --name NAME（必需）</dt>
<dd>帐户组的名称。此选项与 `--id` 互斥。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

列出帐户组。
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（可选）</dt>
<dd>父帐户组的名称。此选项与 `--parent-account-group-id` 互斥。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（可选）</dt>
<dd>父帐户组的标识。此选项与 `--parent-account-group` 互斥。</dd>
<dt>--recursive（可选）</dt>
<dd>显示后代帐户组。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

创建一个帐户。
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>NAME（必需）</dt>
<dd>帐户组名称。</dd>
<dt>--owner USER_ID（可选）</dt>
<dd>帐户组的用户标识。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（可选）。</dt>
<dd>父帐户组的名称。如果省略，父代将为当前企业。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

将帐户移至其他父代下。
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--id ID（必需）</dt>
<dd>目标帐户的标识。此选项与 `-n, --name` 互斥。</dd>
<dt>-n, --name NAME（必需）</dt>
<dd>目标帐户的名称。此选项与 `--id` 互斥。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（必需）</dt>
<dd>父帐户组的名称。此选项与 `--parent-account-group-id` 和 `--parent-enterprise` 互斥。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（必需）</dt>
<dd>父帐户组的标识。此选项与 `--parent-account-group` 和 `--parent-enterprise` 互斥。</dd>
<dt>--parent-enterprise（必需）</dt>
<dd>将企业设置为父代。此选项与 `--parent-account-group` 和 `--parent-account-group-id` 互斥。</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

显示帐户的详细信息。
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--id ID（必需）</dt>
<dd>帐户的标识。此选项与 `-n, --name` 互斥。</dd>
<dt>-n, --name NAME（必需）</dt>
<dd>帐户的名称。此选项与 `--id` 互斥。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

列出帐户。
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（可选）</dt>
<dd>父帐户组的名称。此选项与 `--parent-account-group-id` 互斥。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（可选）</dt>
<dd>父帐户组的标识。此选项与 `--parent-account-group` 互斥。</dd>
<dt>--recursive（可选）</dt>
<dd>显示后代帐户。</dd>
<dt>--output FORMAT（可选）</dt>
<dd>指定输出格式，仅支持“JSON”。</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

导入独立帐户。
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
<dt>--account-id</dt>
<dd>源帐户的标识。</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP（可选）</dt>
<dd>父帐户组的名称。此选项与 `--parent-account-group-id` 互斥。</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID（可选）</dt>
<dd>父帐户组的标识。此选项与 `--parent-account-group` 互斥。</dd>
</dl>
