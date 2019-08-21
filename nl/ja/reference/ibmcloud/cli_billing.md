---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# アカウント、組織、リソース・グループ、およびリソースの使用量の表示 
{: #ibmcloud_billing}

以下のコマンドを使用して、リソース使用量と請求情報を入手します。
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

現行アカウントの月々の使用量を表示します (アカウント管理者のみ)。
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

<strong>例</strong>:

2016 年 6 月の現行アカウントの使用量とコストのレポートを表示します。
```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

組織の月々の使用量を表示します (アカウント管理者または組織の請求管理者のみ)。
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>ORG_NAME (必須)</dt>
  <dd>組織の名前。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

リソース・グループの月々の使用量を表示します (アカウント管理者またはリソース・グループ管理者のみ)。
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>GROUP_NAME (必須)</dt>
  <dd>リソース・グループの名前。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

現行アカウントの月々のリソース・インスタンス使用量を表示します。
```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>-o ORG_NAME (オプション)</dt>
  <dd>組織を基準にしてインスタンスをフィルターに掛けます。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>リソース・グループを基準にしてインスタンスをフィルターに掛けます。</dd>
  <dt>-d MONTH_DATE (オプション)</dt>
  <dd>YYYY-MM 形式を使用して指定された日付のデータを表示します。 指定されていない場合、今月の使用量が表示されます。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

エンタープライズの使用レポートを表示します。
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

<dl>
  <dt>--account ACCOUNT_NAME (オプション)</dt>
  <dd>ターゲット・アカウントの名前。</dd>
  <dt>--account-id ACCOUNT_ID (オプション)</dt>
  <dd>ターゲット・アカウントの ID。</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME (オプション)</dt>
  <dd>ターゲット・アカウント・グループの名前。</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID (オプション)</dt>
  <dd>ターゲット・アカウント・グループの ID。</dd>
  <dt>--children (オプション)</dt>
  <dd>子の使用レポートを表示します。</dd>
  <dt>--month MONTH (オプション)</dt>
  <dd>ターゲット月。 デフォルトは現在の月です。</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>
