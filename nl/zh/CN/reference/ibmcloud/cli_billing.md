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

# 查看帐户、组织、资源组和资源的使用情况 
{: #ibmcloud_billing}

使用以下命令可检索资源使用情况和计费信息。
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

显示当前帐户的每月使用情况（仅限帐户管理员）：
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>

<strong>示例</strong>：

显示当前帐户 2016 年 6 月的使用情况和成本报告：
```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

显示组织的每月使用情况（仅限帐户管理员或组织记帐管理员）：
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>ORG_NAME（必需）</dt>
  <dd>组织的名称。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

显示资源组的每月使用情况（仅限帐户管理员或资源组管理员）：
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>GROUP_NAME（必需）</dt>
  <dd>资源组的名称。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

显示当前帐户的每月资源实例使用情况：
```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>-o ORG_NAME（可选）</dt>
  <dd>按组织过滤实例。</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>按资源组过滤实例。</dd>
  <dt>-d MONTH_DATE（可选）</dt>
  <dd>显示使用 YYYY-MM 格式指定的月份和日期的数据。如果未指定，那么会显示当月的使用情况。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

显示企业使用情况报告：
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

<dl>
  <dt>--account ACCOUNT_NAME（可选）</dt>
  <dd>目标帐户的名称。</dd>
  <dt>--account-id ACCOUNT_ID（可选）</dt>
  <dd>目标帐户的标识。</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME（可选）</dt>
  <dd>目标帐户组的名称。</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID（可选）</dt>
  <dd>目标帐户组的标识。</dd>
  <dt>--children（可选）</dt>
  <dd>显示子代使用情况报告。</dd>
  <dt>--month MONTH（可选）</dt>
  <dd>目标月份。缺省为当前月份。</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>
