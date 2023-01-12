---

copyright:
  years: 2018, 2021
lastupdated: "2021-09-09"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Viewing billing and usage information (ibmcloud billing)
{: #ibmcloud_billing}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to retrieve resource usage and billing information.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Show monthly usage of the current account (account admin only):
```bash
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT] [-q, --quiet]
```

### Command options
{: #ibmcloud_billing_account_usage_options}

-d MONTH_DATE (optional)
:   Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.

--output FORMAT (optional)
:   Specify output format. Accepted inputs are JSON and CSV.

-q, --quiet (optional)
:   Suppress verbose output.

### Examples
{: #ibmcloud_billing_account_usage_examples}

Show current account's usage and cost report in 2016-06:
```bash
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Show monthly usage for an org (account admin or org billing manager only):
```bash
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT] [-q, --quiet]
```

### Command options
{: #ibmcloud_billing_org_usage_options}

ORG_NAME (required)
:   Name of the org.

-d MONTH_DATE (optional)
:   Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.

--output FORMAT (optional)
:   Specify output format. Only JSON is supported.</dd>

-q, --quiet (optional)
:   Suppress verbose output.

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Show monthly usage for a resource group (account admin or resource group admin only):
```bash
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT] [-q, --quiet]
```

### Command options
{: #ibmcloud_billing_resource_group_usage_options}

GROUP_NAME (required)
:    Name of the resource group.

-d MONTH_DATE (optional)
:   Display data for the month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.

--output FORMAT (optional)
:   Specify output format. Only JSON is supported.

-q, --quiet (optional)
:   Suppress verbose output.

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Show monthly resource instances usage under the current account:
```bash
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT] [-q, --quiet]
```

### Command options
{: #ibmcloud_billing_resource_instances_usage_options}

-o ORG_NAME (optional)
:   Filter instances by organization.

-g GROUP_NAME
:   Filter instance by resource group.

-d MONTH_DATE (optional)
:   Display data for month and date that is specified by using the YYYY-MM format. If not specified, usage of the current month is shown.

--output FORMAT (optional)
:   Specify output format. Accepted inputs are JSON and CSV.

-q, --quiet (optional)
:   Suppress verbose output.

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

Show enterprise usage reports:
```bash
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT] [-q, --quiet]
```

### Command options
{: #ibmcloud_billing_enterprise_usage_options}

--account ACCOUNT_NAME (optional)
:   Name of target account.

--account-id ACCOUNT_ID (optional)
:   ID of target account.

--account-group ACCOUNT_GROUP_NAME (optional)
:   Name of target account group.

--account-group-id ACCOUNT_GROUP_ID (optional)
:   ID of target account group.

--children (optional)
:   Show children usage reports.

--month MONTH (optional)
:   Target month. Default to current month.

--output FORMAT (optional)
:   Specify output format. Only JSON is supported.

-q, --quiet (optional)
:   Suppress verbose output.
