---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 计费 
{: #ibmcloud_billing}

使用以下命令可检索资源使用情况和计费信息。
{: shortdesc}

<table summary="可用于管理 {{site.data.keyword.Bluemix_notm}} 计费和使用情况的 ibmcloud 命令。">
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

显示当前帐户的每月使用情况（仅限帐户管理员）

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

显示组织的每月使用情况（仅限帐户管理员或组织记帐管理员）

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

显示资源组的每月使用情况（仅限帐户管理员或资源组管理员）

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

显示当前帐户的每月资源实例使用情况。

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
