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

# 管理企業、帳戶群組和帳戶
{: #ibmcloud_enterprise}

使用下列指令可管理企業、帳戶群組和帳戶。
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

建立一個企業。
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>NAME（必要）</dt>
<dd>企業名稱。</dd>
<dt>-d, --domain DOMAIN_NAME（選用）</dt>
<dd>網域名稱。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID（選用）</dt>
<dd>企業的主要聯絡使用者 ID。</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

更新企業資訊。
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>-f, --force（選用）</dt>
<dd>更新而不確認。</dd>
<dt>-n, --name NEW_NAME（必要）</dt>
<dd>企業的新名稱。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

顯示企業的詳細資料。
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

建立一個帳戶群組。
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>NAME（必要）</dt>
<dd>帳戶群組名稱。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（選用）</dt>
<dd>母項帳戶群組的名稱。若省略，母項將為現行企業。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID（選用）</dt>
<dd>帳戶群組的主要聯絡使用者 ID。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

更新帳戶群組。
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--id ID（必要）</dt>
<dd>目標帳戶群組的 ID。此選項不能與 `-n, --name` 同時使用。</dd>
<dt>-n, --name NAME（必要）</dt>
<dd>目標帳戶群組的名稱。此選項不能與 `--id` 同時使用。</dd>
<dt>--new-name NEW_NAME（必要）</dt>
<dd>目標帳戶群組的新名稱。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

顯示帳戶群組的詳細資料。
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--id ID（必要）</dt>
<dd>帳戶群組的 ID。此選項不能與 `-n, --name` 同時使用。</dd>
<dt>-n, --name NAME（必要）</dt>
<dd>帳戶群組的名稱。此選項不能與 `--id` 同時使用。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

列出帳戶群組。
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（選用）</dt>
<dd>母項帳戶群組的名稱。此選項不能與 `--parent-account-group-id` 同時使用。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（選用）</dt>
<dd>母項帳戶群組的 ID。此選項不能與 `--parent-account-group` 同時使用。</dd>
<dt>--recursive（選用）</dt>
<dd>顯示後代帳戶群組。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

建立一個帳戶。
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>NAME（必要）</dt>
<dd>帳戶群組名稱。</dd>
<dt>--owner USER_ID（選用）</dt>
<dd>帳戶群組的使用者 ID。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（選用）。</dt>
<dd>母項帳戶群組的名稱。若省略，母項將為現行企業。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

將帳戶移至其他母項下。
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--id ID（必要）</dt>
<dd>目標帳戶的 ID。此選項不能與 `-n, --name` 同時使用。</dd>
<dt>-n, --name NAME（必要）</dt>
<dd>目標帳戶的名稱。此選項不能與 `--id` 同時使用。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（必要）</dt>
<dd>母項帳戶群組的名稱。此選項不能與 `--parent-account-group-id` 及 `--parent-enterprise` 同時使用。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（必要）</dt>
<dd>母項帳戶群組的 ID。此選項不能與 `--parent-account-group` 及 `--parent-enterprise` 同時使用。</dd>
<dt>--parent-enterprise（必要）</dt>
<dd>將企業設定為母項。此選項不能與 `--parent-account-group` 及 `--parent-account-group-id` 同時使用。</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

顯示帳戶的詳細資料。
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--id ID（必要）</dt>
<dd>帳戶的 ID。此選項不能與 `-n, --name` 同時使用。</dd>
<dt>-n, --name NAME（必要）</dt>
<dd>帳戶的名稱。此選項不能與 `--id` 同時使用。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

列出帳戶。
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME（選用）</dt>
<dd>母項帳戶群組的名稱。此選項不能與 `--parent-account-group-id` 同時使用。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID（選用）</dt>
<dd>母項帳戶群組的 ID。此選項不能與 `--parent-account-group` 同時使用。</dd>
<dt>--recursive（選用）</dt>
<dd>顯示後代帳戶。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>指定輸出格式，只支援 'JSON'。</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

匯入獨立式帳戶。
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
<dt>--account-id</dt>
<dd>來源帳戶的 ID。</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP（選用）</dt>
<dd>母項帳戶群組的名稱。此選項不能與 `--parent-account-group-id` 同時使用。</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID（選用）</dt>
<dd>母項帳戶群組的 ID。此選項不能與 `--parent-account-group` 同時使用。</dd>
</dl>
