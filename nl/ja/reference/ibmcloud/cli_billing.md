---

copyright:

  years: 2018


lastupdated: "2018-09-04"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 請求処理 
{: #ibmcloud_billing}

以下のコマンドを使用して、{{site.data.keyword.Bluemix_notm}} の請求および使用量を管理します。
{: shortdesc}

<table summary="{{site.data.keyword.Bluemix_notm}} の請求および使用量を管理するために使用できる ibmcloud コマンド。">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

現行アカウントの月々の使用量を表示します (アカウント管理者のみ)

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

組織の月々の使用量を表示します (アカウント管理者または組織の請求管理者のみ)

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

リソース・グループの月々の使用量を表示します (アカウント管理者またはリソース・グループ管理者のみ)

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

現行アカウントの月次リソース・インスタンス使用量を表示します。

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
