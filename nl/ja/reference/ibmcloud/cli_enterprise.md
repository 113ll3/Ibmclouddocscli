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

# エンタープライズ、アカウント・グループ、およびアカウントの管理
{: #ibmcloud_enterprise}

以下のコマンドを使用して、エンタープライズ、アカウント・グループ、およびアカウントを管理します。
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

エンタープライズを作成します。
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>NAME (必須)</dt>
<dd>エンタープライズ名。</dd>
<dt>-d, --domain DOMAIN_NAME (オプション)</dt>
<dd>ドメイン名。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (オプション)</dt>
<dd>エンタープライズの 1 次連絡先ユーザー ID。</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

エンタープライズ情報を更新します。
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>-f, --force (オプション)</dt>
<dd>確認を求めずに更新します。</dd>
<dt>-n, --name NEW_NAME (必須)</dt>
<dd>エンタープライズの新しい名前。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

エンタープライズの詳細を表示します。
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

アカウント・グループを作成します。
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>NAME (必須)</dt>
<dd>アカウント・グループ名。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (オプション)</dt>
<dd>親アカウント・グループの名前。省略された場合、親は現在のエンタープライズになります。</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (オプション)</dt>
<dd>アカウント・グループの 1 次連絡先ユーザー ID。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

アカウント・グループを更新します。
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--id ID (必須)</dt>
<dd>ターゲット・アカウント・グループの ID。このオプションは、`-n, --name` と同時に指定することはできません。</dd>
<dt>-n, --name NAME (必須)</dt>
<dd>ターゲット・アカウント・グループの名前。このオプションは、`--id` と同時に指定することはできません。</dd>
<dt>--new-name NEW_NAME (必須)</dt>
<dd>ターゲット・アカウント・グループの新しい名前。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

アカウント・グループの詳細を表示します。
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--id ID (必須)</dt>
<dd>アカウント・グループの ID。このオプションは、`-n, --name` と同時に指定することはできません。</dd>
<dt>-n, --name NAME (必須)</dt>
<dd>アカウント・グループの名前。このオプションは、`--id` と同時に指定することはできません。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

アカウント・グループをリストします。
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (オプション)</dt>
<dd>親アカウント・グループの名前。このオプションは、`--parent-account-group-id` と同時に指定することはできません。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (オプション)</dt>
<dd>親アカウント・グループの ID。このオプションは、`--parent-account-group` と同時に指定することはできません。</dd>
<dt>--recursive (オプション)</dt>
<dd>子孫アカウント・グループを表示します。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

アカウントを作成します。
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>NAME (必須)</dt>
<dd>アカウント・グループ名。</dd>
<dt>--owner USER_ID (オプション)</dt>
<dd>アカウント・グループのユーザー ID。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (オプション)。</dt>
<dd>親アカウント・グループの名前。省略された場合、親は現在のエンタープライズになります。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

別の親の下にアカウントを移動します。
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--id ID (必須)</dt>
<dd>ターゲット・アカウントの ID。このオプションは、`-n, --name` と同時に指定することはできません。</dd>
<dt>-n, --name NAME (必須)</dt>
<dd>ターゲット・アカウントの名前。このオプションは、`--id` と同時に指定することはできません。</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (必須)</dt>
<dd>親アカウント・グループの名前。このオプションは、 `--parent-account-group-id` および `--parent-enterprise` と同時に指定することはできません。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (必須)</dt>
<dd>親アカウント・グループの ID。このオプションは、 `--parent-account-group` および `--parent-enterprise` と同時に指定することはできません。</dd>
<dt>--parent-enterprise (必須)</dt>
<dd>エンタープライズを親として設定します。このオプションは、 `--parent-account-group` および `--parent-account-group-id` と同時に指定することはできません。</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

アカウントの詳細を表示します。
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--id ID (必須)</dt>
<dd>アカウントの ID。このオプションは、`-n, --name` と同時に指定することはできません。</dd>
<dt>-n, --name NAME (必須)</dt>
<dd>アカウントの名前。このオプションは、`--id` と同時に指定することはできません。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

アカウントをリストします。
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (オプション)</dt>
<dd>親アカウント・グループの名前。このオプションは、`--parent-account-group-id` と同時に指定することはできません。</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (オプション)</dt>
<dd>親アカウント・グループの ID。このオプションは、`--parent-account-group` と同時に指定することはできません。</dd>
<dt>--recursive (オプション)</dt>
<dd>子孫アカウントを表示します。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、「JSON」のみがサポートされています。</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

スタンドアロン・アカウントをインポートします。
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
<dt>--account-id</dt>
<dd>ソース・アカウントの ID。</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (オプション)</dt>
<dd>親アカウント・グループの名前。このオプションは、`--parent-account-group-id` と同時に指定することはできません。</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (オプション)</dt>
<dd>親アカウント・グループの ID。このオプションは、`--parent-account-group` と同時に指定することはできません。</dd>
</dl>
