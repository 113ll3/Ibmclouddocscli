---

copyright:

  years: 2018, 2019


lastupdated: "2019-01-03"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Viewing usage for accounts, orgs, resource groups, and resources 
{: #ibmcloud_billing}

Use the following commands to retrieve resource usage and billing information.
{: shortdesc}

<table summary="ibmcloud commands that you can use to manage {{site.data.keyword.Bluemix_notm}} billing and usage.">
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

Show monthly usage of the current account (account admin only)

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format, only JSON is supported now.</dd>
</dl>

<strong>Examples</strong>:

Show current account's usage and cost report in 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Show monthly usage for an org (account admin or org billing manger only)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>ORG_NAME (required)</dt>
  <dd>Name of the org.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format, only JSON is supported now.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Show monthly usage for a resource group (account admin or resource group admin only)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>GROUP_NAME (required)</dt>
  <dd>Name of the resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format, only JSON is supported now.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Show monthly resource instances usage under the current account.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-o ORG_NAME (optional)</dt>
  <dd>Filter instances by organization.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filter instance by resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for month and date specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specify output format, only JSON is supported now.</dd>
</dl>
