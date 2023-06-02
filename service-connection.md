---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-02"

keywords: isolation for IBM Cloud CLI, service endpoints for IBM Cloud CLI, private network for IBM Cloud CLI, network isolation in IBM Cloud CLI, non-public routes for IBM Cloud CLI, private connection for IBM Cloud CLI, private endpoints, regions that support private endpoints, private service endpoints, cli private endpoints

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Securing your connection when using the {{site.data.keyword.cloud_notm}} CLI
{: #service-connection}

To ensure that you have enhanced control and security over your data when you use the {{site.data.keyword.cloud}} Command Line Interface, you have the option of using private routes to {{site.data.keyword.cloud_notm}} endpoints. Private routes are not accessible or reachable over the internet. By using the {{site.data.keyword.cloud_notm}} private endpoints feature, you can protect your data from threats from the public network and logically extend your private network.
{: shortdesc}

The CLI uses the private endpoint support that is provided by the {{site.data.keyword.cloud_notm}} platform. Platform services that are used by the core CLI, such as IAM, provide private endpoint support.

If your deployment uses the VPC environment of {{site.data.keyword.cloud_notm}}, private endpoints are exposed through global endpoints. If your deployment uses the Classic environment, regional support is provided for a limited number of CLI commands. The following regions support private endpoints in Classic environments:
* `us-south`
* `us-east`

## Enabling virtual routing and forwarding
{: #cli-private-vrf}

You must first enable virtual routing and forwarding in your account, and then you can enable the use of {{site.data.keyword.cloud_notm}} private service endpoints. For more information about setting up your account to support the private connectivity option, see [Enabling VRF and service endpoints](/docs/account?topic=account-vrf-service-endpoint).

To learn more about private connections on {{site.data.keyword.cloud_notm}}, see [Secure access to services using service endpoints](/docs/account?topic=account-service-endpoints-overview).

## Logging in to the CLI with a private endpoint
{: #cli-private-login}

You can log in to either a private endpoint for Classic or for VPC. To log in using Classic infrastructure, [log in](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_login) to a private endpoint by using the CLI by using the following command:

```text
ibmcloud login -a private.cloud.ibm.com
```

To [log in](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_login) by using the VPC infrastructure, add the `--vpc` flag to the command:

```text
ibmcloud login -a private.cloud.ibm.com --vpc
```

## Targeting a supported region (required for Classic use)
{: #cli-private-region}

To use private endpoints for deployments in the Classic environment, a region must be targeted when a private endpoint is set in the {{site.data.keyword.cloud_notm}} CLI.

To [target](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_target) a supported region, use the following command:

```text
ibmcloud target -r [region]
```

## Configuring a private endpoint gateway (required for VPC use)
{: #cli-private-vpc}

To use private endpoints for deployments in the VPC environment, you must configure a virtual private endpoint gateway. For more information, see [About virtual private endpoint gateways](/docs/vpc?topic=vpc-about-vpe).

A list of all {{site.data.keyword.cloud_notm}} services that are configurable through a virtual private endpoint gateway is at [VPE Supported Services](/docs/vpc?topic=vpc-vpe-supported-services).

To ensure basic CLI capability against the private endpoint, you must configure the gateway to include these services:
* Account Management: Endpoint URL `(https://private.accounts.cloud.ibm.com)`{: external}
* Global Catalog: [Endpoint URL](/apidocs/resource-catalog/global-catalog#endpoint-url)
* Global Search: [Endpoint URL](/apidocs/search#endpoint-url)
* Global Tagging: [Endpoint URL](/apidocs/tagging#endpoint-url)
* Usage Metering: [Endpoint URL](/apidocs/usage-metering#endpoint)
* Enterprise Management: [Endpoint URL](/apidocs/enterprise-apis/enterprise#endpoint-urls)
* Resource Controller: [Endpoint URL](/apidocs/resource-controller/resource-controller#endpoint-urls)
* User Management: [Endpoint URL](/apidocs/user-management#endpoint-urls)

## Determining which CLI plug-ins support private endpoints
{: #cli-private-plugins}

The [`ibmcloud plugin list`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_list) command reports whether an installed CLI plug-in supports private endpoints. If a plug-in that you use does not show private support, you must continue to use it with your API set to the public endpoint `cloud.ibm.com`.

## Determining which commands support private endpoints
{: #cli-private-commands}

The following commands support private endpoints:
- `api`
- `login`
- `target`
- `logout`

Most commands under the following namespaces work when you are using private endpoints:
- `account`
- `billing`
- `iam`
- `resource`
- `catalog`

If the CLI is set to access private endpoints and you try to run a command or plug-in that does not yet support private endpoints, you might see an error.
{: note}

The following core commands do not yet support private endpoints:

```text
account
  domain-cert
  domain-cert-add
  domain-cert-remove
  org
  org-account
  org-create
  org-rename
  org-replicate
  org-role-set
  org-role-unset
  org-roles
  org-user-add
  org-user-remove
  org-users
  orgs
  space
  space-create
  space-delete
  space-rename
  space-role-set
  space-role-unset
  space-roles
  space-users
  spaces
    audit-logs
    update
billing
  org-usage
catalog
  template-run
dev
  all commands
cf
  all commands
sl
  all commands
app (deprecated)
  all commands
service (deprecated)
  all commands
```
