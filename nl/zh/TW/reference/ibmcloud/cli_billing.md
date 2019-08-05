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

# 檢視帳戶、組織、資源群組和資源的用量 
{: #ibmcloud_billing}

請使用下列指令擷取資源用量及計費資訊。
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

顯示現行帳戶的每月用量（僅限帳戶管理者）：
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

<strong>範例</strong>：

顯示現行帳戶在 2016-06 的用量和費用報告：
```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

顯示組織的每月用量（僅限帳戶管理者或組織帳單管理員）：
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>ORG_NAME（必要）</dt>
  <dd>組織的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

顯示資源群組的每月用量（僅帳戶管理者或資源群組管理者）：
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>GROUP_NAME（必要）</dt>
  <dd>資源群組的名稱。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

顯示現行帳戶下的每月資源實例用量：
```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>-o ORG_NAME（選用）</dt>
  <dd>依組織過濾實例。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>依資源群組過濾實例。</dd>
  <dt>-d MONTH_DATE（選用）</dt>
  <dd>顯示使用 YYYY-MM 格式指定之月份和日期的資料。如果未指定，則會顯示現行月份的用量。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

顯示企業用量報告：
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

<dl>
  <dt>--account ACCOUNT_NAME（選用）</dt>
  <dd>目標帳戶的名稱。</dd>
  <dt>--account-id ACCOUNT_ID（選用）</dt>
  <dd>目標帳戶的 ID。</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME（選用）</dt>
  <dd>目標帳戶群組的名稱。</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID（選用）</dt>
  <dd>目標帳戶群組的 ID。</dd>
  <dt>--children（選用）</dt>
  <dd>顯示子項用量報告。</dd>
  <dt>--month MONTH（選用）</dt>
  <dd>目標月份。預設為現行月份。</dd>
  <dt>--output FORMAT（選用）</dt>
  <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>
