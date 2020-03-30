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

# Viewing usage for accounts, orgs, resource groups, and resources 
{: #ibmcloud_billing}

Use the following commands to retrieve resource usage and billing information.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Show monthly usage of the current account (account admin only):
```
ibmcloud billing account-usage [-d YYYY-MM]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
</dl>

<strong>Examples</strong>:

Show current account's usage and cost report in 2016-06:
```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Show monthly usage for an org (account admin or org billing manager only):
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>ORG_NAME (required)</dt>
  <dd>Name of the org.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Show monthly usage for a resource group (account admin or resource group admin only):
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>GROUP_NAME (required)</dt>
  <dd>Name of the resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Show monthly resource instances usage under the current account:
```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>-o ORG_NAME (optional)</dt>
  <dd>Filter instances by organization.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filter instance by resource group.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Display data for month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

Show enterprise usage reports:
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

<dl>
  <dt>--account ACCOUNT_NAME (optional)</dt>
  <dd>Name of target account.</dd>
  <dt>--account-id ACCOUNT_ID (optional)</dt>
  <dd>ID of target account.</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME (optional)</dt>
  <dd>Name of target account group.</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID (optional)</dt>
  <dd>ID of target account group.</dd>
  <dt>--children (optional)</dt>
  <dd>Show children usage reports.</dd>
  <dt>--month MONTH (optional)</dt>
  <dd>Target month. Default to current month.</dd>
</dl>
