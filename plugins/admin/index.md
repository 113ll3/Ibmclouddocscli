---

copyright:
  years: 2015, 2019
lastupdated: "2019-11-14"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}
{:external: target="_blank" .external}

# {{site.data.keyword.cloud_notm}} admin CLI
{: #ibmcloud-admincli}

You can manage your {{site.data.keyword.cloud_notm}} Local or {{site.data.keyword.cloud_notm}} Dedicated environment by using the Cloud Foundry command line interface (CLI) with the {{site.data.keyword.cloud_notm}} admin CLI plug-in. For example, you can add users from an LDAP registry.

Before you begin, install the Cloud Foundry CLI. The {{site.data.keyword.cloud_notm}} admin CLI plug-in
requires `cf` version 6.11.2 or later. [Download Cloud Foundry command line interface](https://github.com/cloudfoundry/cli/releases){: external}.

The Cloud Foundry CLI is not supported by Cygwin. Use the Cloud Foundry CLI in a command line window other than the Cygwin command line window.

{{site.data.keyword.cloud_notm}} admin CLI is only used for {{site.data.keyword.cloud_notm}} Local and {{site.data.keyword.cloud_notm}} Dedicated environment. It is not supported by {{site.data.keyword.cloud_notm}} Public.
{: note}

## Adding the {{site.data.keyword.cloud_notm}} admin CLI plug-in
{: #add-admin-cli}

After you install the Cloud Foundry CLI, you can add the {{site.data.keyword.cloud_notm}} admin CLI plug-in.

If you previously installed the {{site.data.keyword.cloud_notm}} admin plug-in, you might need to uninstall the plug-in, delete the repository, and then install again to get the latest updates.
{: tip}

Complete the following steps to add the repository and install the plug-in:

1. To add the {{site.data.keyword.cloud_notm}} admin plug-in repository, run the following command:
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  You can find the same command with the actual endpoint on your admin console CLI page: `https://<customer_console_endpoint>.bluemix.net/cli`.
  {: note}

2. To install the {{site.data.keyword.cloud_notm}} admin CLI plug-in, run the following command:
  ```
  cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
  ```
  {: codeblock}

## Uninstalling the {{site.data.keyword.cloud_notm}} admin CLI plug-in
{: #remove-admin-cli}

Complete the following steps to uninstall the plug-in. 

1. Uninstall the plug-in:
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. Remove the plug-in repository:
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

Then, you can add the updated repository and install the latest plug-in.

## Managing users
{: #managing_users_cli}

### Adding a user
{: #admin_add_user}

To add a user to your {{site.data.keyword.cloud_notm}} environment from the
user registry for your environment, use the following command:
```
cf ba add-user user_name organization first_name last_name
```
{: codeblock}

To add a user to a specific organization, you must be an admin with the users.write (or Superuser) permission. If you're an organization manager, you can also be provided with the capability to add users to your organization by a Superuser who runs the **`enable-managers-add-users`** command. For more information, see [Enabling managers to add users](#clius_emau).

<dl>
<dt>user_name</dt>
<dd>The name of the user in the LDAP registry.</dd>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org to add the user to.</dd>
<dt>first_name</dt>
<dd>The first name of the user to be added to the organization.</dd>
<dt>last_name</dt>
<dd>The last name of the user to be added to the organization.</dd>
</dl>

You can also use **`ba au`** as an alias for the longer **`ba add-user`** command name.
{: tip}

### Inviting a user from {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_invite_public}

Each {{site.data.keyword.Bluemix_dedicated_notm}} environment has a public, client-owned, corporate account in {{site.data.keyword.cloud_notm}}. In order for users in the Dedicated environment to create clusters with the {{site.data.keyword.containershort}}, the administrator must add the users to this public corporate account. When the users are added to the public corporate account, their Dedicated and public accounts are linked together. Users can then use their IBMid to log in to both Dedicated and public simultaneously, and can create resources in the public account from the Dedicated interface.

To invite Dedicated users to the public account:
```
cf ba invite-users-to-public -userid=user_email -organization=dedicated_org_id -apikey=public_api_key -public_org_id=public_org_id
```
{: pre}

To add Dedicated environment users to your {{site.data.keyword.cloud_notm}} public account, you must be an Admin of the Dedicated account.

<dl>
<dt>user_email</dt>
<dd>If you are inviting a single user, the email of the user.</dd>
<dt>dedicated_org_id</dt>
<dd>If you are inviting all users currently in a Dedicated account organization, the Dedicated account organization ID.</dd>
<dt>public_api_key</dt>
<dd>An API key for inviting users to the public account. The key must be generated by the admin of the public account.</dd>
<dt>public_org_id</dt>
<dd>The ID of the public account organization you are inviting users to.</dd>
</dl>

### Listing users who are invited from {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_list}

If you invite Dedicated environment users to your {{site.data.keyword.cloud_notm}} account with the [**`invite-users-to-public`** command](#admin_dedicated_invite_public), you can list the users in your account to see their invite status. Invited users with an existing IBMid have an ACTIVE status. Invited users that didn't have an existing IBMid have a status of either PENDING or ACTIVE, depending on whether the invitation was accepted.

To list the users in your {{site.data.keyword.cloud_notm}} account:
```
cf ba invite-users-status -apikey=public_api_key
```
{: pre}

To add Dedicated environment users to your {{site.data.keyword.cloud_notm}} public account, you must be an admin of the Dedicated account.

<dl>
<dt>public_api_key</dt>
<dd>The API key that was used to invite the users to the account. The key must be generated by the admin of the public account.</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### Searching for a user
{: #admin_search_user}

To search for a user, use the following command with the optional search filter parameters (name, permission, organization, and role):
```
cf ba search-users -name=user_name -permission=permission_value -organization=organization_value -role=role_value
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>permission_value</dt>
<dd>The permission that is assigned to the user. The available permissions are admin (or superuser), log in (or basic), catalog.read, catalog.write, reports.read, reports.write, users.read, or users.write. You can't use this parameter with the organization parameter in the same query.</dd>
<dt>organization_value</dt>
<dd>The organization name that the user belongs to. You can't use this parameter with the permission parameter in the same query.</dd>
<dt>role_value</dt>
<dd>The organization role that is assigned to the user. The available roles are auditors, managers, and billing_managers. You must specify the organization with this parameter.</dd>
</dl>

You can also use **`ba su`** as an alias for the longer **`ba search-users`** command name.
{: tip}

### Setting permissions for a user
{: #admin_setperm_user}

You can set one permission at a time. To set permissions for a specified user, use the following command:
```
cf ba set-permissions user_name permission access
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>permission</dt>
<dd>Set the permission that is assigned to the user. The available permissions are admin (or superuser), log in (or basic), catalog.read, catalog.write, reports.read, reports.write, users.read, or users.write. You can't use this parameter with the organization parameter in the same query.</dd>
<dt>access</dt>
<dd>For the catalog, reports, or user permissions, you must also set the level of access as `read` or `write`.</dd>
</dl>

You can also use **`ba sp`** as an alias for the longer **`ba set-permissions`** command name.
{: tip}

<!-- staging-only commands end -->

### Removing a user
{: #admin_remov_user}

To remove a user from your {{site.data.keyword.cloud_notm}} environment, use the following command:
```
cf ba remove-user user_name
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>The name of the user in {{site.data.keyword.cloud_notm}}.</dd>
</dl>

You can also use the **`ba ru`** as an alias for the longer **`ba remove-user`** command name.
{: tip}

### Enabling managers to add users
{: #clius_emau}

If you have the Superuser permission in your {{site.data.keyword.cloud_notm}} environment, you can enable organization managers to add users to the organizations they manage.

To enable managers to add users, use the following command:
```
cf ba enable-managers-add-users
```
{: codeblock}

You can also use the **`ba emau`** as an alias for the longer **`ba enable-managers-add-users`** command name.
{: tip}

### Disabling managers from adding users
{: #clius_dmau}

To disable managers from adding users, use the following command:
```
cf ba disable-managers-add-users
```
{: codeblock}

You can also use the **`ba dmau`** command as an alias for the longer **`ba disable-managers-add-users`** command name.
{: tip}

## Administering organizations
{: #admin_orgs}

### Adding an organization
{: #admin_add_org}

To add an organization, use the following command:
```
cf ba create-org organization manager
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org to add.</dd>
<dt>manager</dt>
<dd>The user name of the manager for the org.</dd>
</dl>

You can also use **`ba co`** as an alias for the longer **`ba create-org`** command name.
{: tip}

### Deleting an organization
{: #admin_delete_org}

To delete an organization, use the following command:
```
cf ba delete-org organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org to delete.</dd>
</dl>

You can also use **`ba do`** as an alias for the longer **`ba delete-org`** command name.
{: tip}

### Assigning a user to an organization
{: #admin_ass_user_org}

To assign a user in your {{site.data.keyword.cloud_notm}} environment to a particular organization, use the following command:
```
cf ba set-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org to assign the user to.</dd>
<dt>role</dt>
<dd>The role of the user. Valid values are OrgManager, BillingManager, OrgAuditor. See [Roles](/docs/iam?topic=iam-userroles#userroles) for the role descriptions.</dd>
</dl>

You can also use **`ba so`** as an alias for the longer **`ba set-org`** command name.
{: tip}

### Unassigning a user from an organization
{: #admin_unass_user_org}

To unassign a user in your {{site.data.keyword.cloud_notm}} environment from a particular organization, use the following command:
```
cf ba unset-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org.</dd>
<dt>role</dt>
<dd>The role of the user. Valid values are OrgManager, BillingManager, OrgAuditor. See [Roles](/docs/iam?topic=iam-userroles#userroles) for the role descriptions.</dd>
</dl>

You can also use **`ba uo`** as an alias for the longer **`ba unset-org`** command name.
{: tip}

### Setting a quota for an organization
{: #admin_set_org_quota}

To set the usage quota for a particular organization, use the following command:
```
cf ba set-quota organization plan
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the {{site.data.keyword.cloud_notm}} org to set the quota for.</dd>
<dt>plan</dt>
<dd>The quota plan for an organization.</dd>
</dl>

You can also use **`ba sq`** as an alias for the longer **`ba set-quota`** command name.
{: tip}


### Finding container quotas for an organization
{: #admin_find_containquotas}

To find the quota for containers for an organization, use the following command:
```
cf ibmcloud-admin containers-quota organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or ID of the organization in {{site.data.keyword.cloud_notm}}. This parameter is required.</dd>
</dl>

You can also use **`ba cq`** as an alias for the longer **`ibmcloud-admin containers-quota`** command name.
{: tip}

### Setting container quotas for an organization
{: #admin_set_containquotas}

To set the quota for containers in an organization, use the following command with at least one of the options included:
```
cf ibmcloud-admin set-containers-quota organization options
```
{: codeblock}

You can include multiple options, but you must include at least one.
{: note}

<dl>
<dt>organization</dt>
<dd>The name or ID of the {{site.data.keyword.cloud_notm}} org to set the quota for.</dd>
<dt>options</dt>
<dd>The choices are floating-ips-max value (short name fim), memory-max value (short name mm), memory-space-default value (short name msd), or image-limit value (short name il). The value must be an integer.</dd>
</dl>

Optionally, you can provide a file that contains specific configuration parameters in a valid JSON object. If you use the **`-file`** option, it takes precedence and the other options are ignored.

To provide a file instead of setting the options, use the following command:
```
cf ibmcloud-admin set-containers-quota organization -file path_to_JSON_file
```
{: codeblock}

See the following JSON example:
```json
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: pre}

You can also use **`ba scq`** as an alias for the longer **`ibmcloud-admin set-containers-quota`** command name.
{: tip}

## Administering spaces
{: #admin_spaces}

### Adding a space to the organization

To add a space in the organization, use the following command:
```
cf ibmcloud-admin create-space organization space_name
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the org to add the space to.</dd>
<dt>space_name</dt>
<dd>The name of the space that you are adding to the org.</dd>
</dl>

You can also use **`ba cs`** as an alias for the longer **`ba create-space`** command name.
{: tip}

### Deleting a space from the organization

To remove a space from the organization, use the following command:
```
cf ibmcloud-admin delete-space organization space_name
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the org that the space is to be removed from.</dd>
<dt>space_name</dt>
<dd>The name of the space that you are removing from the org.</dd>
</dl>

You can also use **`ba cs`** as an alias for the longer **`ba delete-space`** command name.
{: tip}

### Adding a user to a space with a role

To create a user in a space with a specified role, use the following command:
```
cf ibmcloud-admin set-space organization space_name user_name role
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the org that the user is being added to.</dd>
<dt>space_name</dt>
<dd>The name of the space that the user is being added to.</dd>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>role</dt>
<dd>The role of the user. Valid values are Manager, Developer, or Auditor.</dd>
</dl>

You can also use **`ba ss`** as an alias for the longer **`ba set-space`** command name.
{: tip}


### Removing the role of a user in a space

To remove the role of a user in a space, use the following command:
```
cf ibmcloud-admin unset-space organization space_name user_name role
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>The name or GUID of the org that the user belongs to.</dd>
<dt>space_name</dt>
<dd>The name of the space that the user belongs to.</dd>
<dt>user_name</dt>
<dd>The name of the user.</dd>
<dt>role</dt>
<dd>The role of the user. Valid values are Manager, Developer, or Auditor.</dd>
</dl>

You can also use **`ba us`** as an alias for the longer **`ba unset-space`** command name.
{: tip}

## Administering the catalog
{: #admin_catalog}

### Enabling services for all organizations
{: #admin_ena_service_org}

To enable a service to be displayed in the
{{site.data.keyword.cloud_notm}} catalog for all organizations, use the following command:
```
cf ba enable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>The name or GUID of the service plan that you want to enable. If you enter a non-unique service plan name, for example "Standard" or "Basic," you're prompted to select a service plan. To identify a service plan name, select the service category from the home page, then select <b>Add</b> to view the services for that category. Click the service name to open the details view, then you can view the names of the service plans that are available for that service. </dd>
</dl>

You can also use **`ba esp`** as an alias for the longer **`ba enable-service-plan`** command name.
{: tip}

### Disabling services for all organizations
{: #admin_dis_service_org}

To disable a service from being visible in the {{site.data.keyword.cloud_notm}} catalog for all organizations, use the following command:
```
cf ba disable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>The name or GUID of the service plan that you want to enable. If you enter a non-unique service plan name, for example "Standard" or "Basic," you're prompted to select a service plan. To identify a service plan name, select the service category from the home page, then select <b>Add</b> to view the services for that category. Click the service name to open the details view, then you can view the names of the service plans that are available for that service.</dd>
</dl>

You can also use **`ba dsp`** as an alias for the longer **`ba disable-service-plan`** command name.
{: tip}

### Adding service visibility for organizations
{: #admin_addvis_service_org}

You can add an organization from the list of organizations that can see a specific service in the {{site.data.keyword.cloud_notm}} catalog.

To allow an organization to view a specific service in the catalog, use the following command:
```
cf ba add-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>The name or GUID of the service plan that you want to enable. If you enter a non-unique service plan name, for example "Standard" or "Basic," you're prompted to select a service plan. To identify a service plan name, select the service category from the home page, then select <b>Add</b> to view the services for that category. Click the service name to open the details view, then you can view the names of the service plans that are available for that service.</dd>
<dt>organization</dt>
<dd>The name or GUID of the org to add to the service's visibility list.</dd>
</dl>

You can also use **`ba aspv`** as an alias for the longer **`ba add-service-plan-visibility`** command name.
{: tip}

### Removing service visibility for organizations
{: #admin_remvis_service_org}

You can remove an organization from the list of organizations that can see a
specific service in the {{site.data.keyword.cloud_notm}} catalog.

To remove the visibility of a service in the catalog for an organization, use the following command:
```
cf ba remove-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>The name or GUID of the service plan that you want to enable. If you enter a non-unique service plan name, for example "Standard" or "Basic," you're prompted to select a service plan. To identify a service plan name, select the service category from the home page, then select <b>Add</b> to view the services for that category. Click the service name to open the details view, then you can view the names of the service plans that are available for that service.</dd>
<dt>organization</dt>
<dd>The name or GUID of the org to remove from the service's visibility list.</dd>
</dl>

You can also use **`ba rspv`** as an alias for the longer **`ba remove-service-plan-visibility`** command name.
{: tip}

### Editing service visibility for organizations
{: #admin_editvis_service_org}

You can edit and replace the list of services that specific
organizations can see in the {{site.data.keyword.cloud_notm}} catalog.

To replace all existing visible services for an organization or multiple organizations, use the following command:
```
cf ba edit-service-plan-visibilities plan_identifier organization_1 optional_organization_2
```
{: codeblock}

This command replaces existing visible services for the specified organizations with the service that you specify in the command.

<dl>
<dt>plan_identifier</dt>
<dd>The name or GUID of the service plan that you want to enable. If you enter a non-unique service plan name, for example "Standard" or "Basic," you're prompted to select a service plan. To identify a service plan name, select the service category from the home page, then select <b>Add</b> to view the services for that category. Click the service name to open the details view, then you can view the names of the service plans that are available for that service.</dd>
<dt>organization</dt>
<dd>The name or GUID of the org to add visibility for. You can enable visibility of the service for more than one organization by entering more organization names or GUIDs in the command.</dd>
</dl>

You can also use **`ba espv`** as an alias for the longer **`ba edit-service-plan-visibility`** command name.
{: tip}

## Administering reports
{: #admin_add_report}

### Adding reports
{: #admin_adding_report}

To add a security report, use the following command:
```
cf ba add-report category date PDF|TXT|LOG RTF
```
{: codeblock}

If you have write access for the reports permission, you can create a new category and add a report in any of the accepted formats for your users. Enter the new category name for the **`category`** parameter, or add your new report to an existing category.

<dl>
<dt>category</dt>
<dd>The category for the report. If there's a space in the name, use quotation marks.</dd>
<dt>date</dt>
<dd>The report date in the format of YYYYMMDD.</dd>
<dt>PDF|TXT|LOG</dt>
<dd>The path for the report PDF, text file, or log file to upload.</dd>
<dt>RTF</dt>
<dd>An option to include a Rich Text Format (RTF) version of the PDF. This option applies only if you include a path to the report PDF. The RTF version is used for indexing and searching.</dd>
</dl>

You can also use **`ba ar`** as an alias for the longer **`ba add-report`** command name.
{: tip}

### Deleting reports
{: #admin_del_report}

To delete a security report, use the following command:
```
cf ba delete-report category date name
```
{: codeblock}

<dl>
<dt>category</dt>
<dd>The category for the report. If there's a space in the name, use quotation marks.</dd>
<dt>date</dt>
<dd>The report date in the format of YYYYMMDD.</dd>
<dt>name</dt>
<dd>The name of the report.</dd>
</dl>

You can also use **`ba d`r** as an alias for the longer **`ba delete-report`** command name.
{: tip}

### Retrieving reports
{: #admin_retr_report}

To retrieve a security report, use the following command:
```
cf ba retrieve-report search
```
{: codeblock}

<dl>
<dt>search</dt>
<dd>The file name of the report. If there is a space in the name, use quotation marks around the
name.</dd>
</dl>

You can also use **`ba rr`** as an alias for the longer **`ba retrieve-report`** command name.
{: tip}

## Viewing resource metric information
{: #cliresourceusage}

You can view resource metric information, including memory, disk, and CPU usage. You can see a summary of the available physical and reserved resources and the usage of physical and reserved resources. You can also see droplet execution agents (DEAs) and cells (Diego architecture) usage data.

To view the resource metric information, use the following command:
```
cf ba resource-metrics
```
{: codeblock}

You can also use **`ba rsm`** as an alias for the longer **`ba resource-metrics`** command name.
{: tip}

## Viewing resource metric history
{: #cliresourceusagehistory}

You can retrieve resource metric history for memory and disk usage. The metrics that are returned include the amount of resources that are used out of the total available, for both physical and reserved resources. Historical data for memory and disk usage can be displayed hourly, daily, or monthly. You can specify start and end dates to retrieve data within a specific date range. The default historical data, when no dates are specified, are hourly memory data for the latest 48 hours. Data is displayed in descending order, with more recent dates shown first.

To view the resource metric history information, use the following command:
```
cf ba resource-metrics-history hourly|daily|monthly  memory|disk   start|end
```
{: codeblock}

<dl>
<dt>--hourly</dt>
<dd>View the historical data for the last 48 hours. 48 hours is the default value.</dd>
<dt>--daily</dt>
<dd>View the historical data daily average for the last 30 days.</dd>
<dt>--monthly</dt>
<dd>View the historical data monthly average for the last 6 months.</dd>
<dt>--memory</dt>
<dd>View the used and total reserved and physical memory.</dd>
<dt>--disk</dt>
<dd>View the used and total reserved and physical disk.</dd>
<dt>--start</dt>
<dd>Specify a start date for daily or monthly in the format of mm-dd-yyyy, or start date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone.</dd>
<dt>--end</dt>
<dd>Specify an end date for daily or monthly in the format of mm-dd-yyyy, or end date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone.</dd>
</dl>

### Examples
{: #cliresourceusagehistoryex}

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

You can view the previous list of command parameters and examples by using the following command:
```
cf ba resource-metrics-history -help
```

You can also use **`ba rsmh`** as an alias for the longer **`ba resource-metrics-history`** command name.
{: tip}

## Administering service brokers
{: #admin_servbro}

### Listing service brokers
{: #clilistservbro}

To list service brokers, use the following command:
```
cf ba service-brokers broker_name
```
{: codeblock}

To list all service brokers, enter the command without the **`broker_name`** parameter.

<dl>
<dt>broker_name</dt>
<dd>The name of the custom service broker. Use this parameter, if you want to get information for a specific service broker. Optional.</dd>
</dl>

You can also use **`ba sb`** as an alias for the longer **`ba service-brokers`** command name.
{: tip}

### Adding a service broker
{: #cliaddservbro}

To add a service broker so that you can add a custom service to the {{site.data.keyword.cloud_notm}} catalog, use the following command:
```
cf ba add-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>The name of the custom service broker.</dd>
<dt>user_name</dt>
<dd>The user name for the account that has access to the service broker.</dd>
<dt>password</dt>
<dd>The password for the account that has access to the service broker.</dd>
<dt>broker_url</dt>
<dd>The URL for the service broker.</dd>
</dl>

You can also use **`ba asb`** as an alias for the longer **`ba add-service-broker`** command name.
{: tip}

### Deleting a service broker
{: #clidelservbro}

To delete a service broker that removes the custom service from the
{{site.data.keyword.cloud_notm}} catalog, use the following command:
```
cf ba delete-service-broker service_broker
```
{: codeblock}

<dl>
<dt>service_broker</dt>
<dd>The name or GUID of the custom service broker.</dd>
</dl>

You can also use **`ba dsb`** as an alias for the longer **`ba delete-service-broker`** command name.
{: tip}

### Updating a service broker
{: #cliupdservbro}

To update a service broker, use the following command:
```
cf ba update-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>The name of the custom service broker.</dd>
<dt>user_name</dt>
<dd>The user name for the account that has access to the service broker.</dd>
<dt>password</dt>
<dd>The password for the account that has access to the service broker.</dd>
<dt>broker_url</dt>
<dd>The URL for the service broker.</dd>
</dl>

You can also use **`ba usb`** as an alias for the longer **`ba update-service-broker`** command name.
{: tip}

## Administering application security groups
{: #admin_secgro}

To work with application security groups (ASGs), you must be a full access administrator for the local or dedicated environment. All users of the environment can list the available ASGs for the organization that is being targeted with the command. However, to create, update, or bind ASGs, you must be an administrator for the {{site.data.keyword.cloud_notm}} environment.

ASGs function as virtual firewalls that control outbound traffic from the apps in your {{site.data.keyword.cloud_notm}} environment. Each ASG consists of a list of rules that allow specific traffic and communication to and from the outside network. You can bind one or more ASGs to a specific security group set. For example, by applying global access for a group set or binding to spaces within an organization in your {{site.data.keyword.cloud_notm}} environment.

{{site.data.keyword.cloud_notm}} is initially set up with all access to the outside network restricted. Two IBM-created security groups, `public_networks` and `dns`, enable global access to the outside network when you bind these groups to default Cloud Foundry security group sets. The two security group sets in Cloud Foundry that are used to apply global access are the **Default Staging** and **Default Running** group sets. These group sets apply the rules for allowing traffic to all running apps or all staging apps. If you do not want to bind to these two security group sets, you can unbind from the Cloud Foundry group sets, and then bind the security group to a specific space. For more information, see [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: external}.

Unbinding the **Default Staging** or **Default Running** group sets from the two IBM-created security groups, `public_networks` and `dns` disables global access to the outside network. Use unbinding with caution and awareness of its potential impact on the running and staging apps in your environment.
{: important}

Use the following commands to work with security groups that are based on the Cloud Foundry 1.6 version. For more information, including required and optional fields, see [Creating Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: external}.

### Listing security groups
{: #clilissecgro}

To list all security groups, use the following command:
```
cf ba security-groups
```
{: codeblock}

To display details for a specific security group, use the following command:
```
cf ba security-groups security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>The name of the security group.</dd>
</dl>

You can also use **`ba sg`** as an alias for the longer **`ba security-groups`** command name.
{: tip}

### Creating a security group
{: #clicreasecgro}

To create a security group, use the following command:
```
cf ba create-security-group security-group path-to-rules-file
```
{: codeblock}

Each security group that you create has the prefix `adminconsole_` added to the name to distinguish it from the IBM-created security groups.

<dl>
<dt>security-group</dt>
<dd>The name of the security group.</dd>
<dt>path-to-rules-file</dt>
<dd>The absolute or relative path to a rules file.</dd>
</dl>

You can also use **`ba csg`** as an alias for the longer **`ba create-security-group`** command name.
{: tip}

For more information about creating security groups and the rules that define outgoing traffic, see [Creating Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: external}.

### Updating a security group
{: #cliupdsecgro}

To update a security group, use the following command:
```
cf ba update-security-group security-group path-to-rules-file
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>The name of the security group.</dd>
<dt>path-to-rules-file</dt>
<dd>The absolute or relative path to a rules file.</dd>
</dl>

You can also use **`ba usg`** as an alias for the longer **`ba update-security-group`** command name.
{: tip}

### Deleting a security group
{: #clidelsecgro}

To delete a security group, use the following command:
```
cf ba delete-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Name of your security group</dd>
</dl>

You can also use **`ba dsg`** as an alias for the longer **`ba delete-security-group`** command name.
{: tip}

### Binding security groups
{: #clibindsecgro}

To bind to the Default Staging security group set, use the following command:
```
cf ba bind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Name of your security group</dd>
</dl>

You can also use **`ba bssg`** as an alias for the longer **`ba bind-staging-security-group`** command name.
{: tip}

To bind to the Default Running security group set, use the following command:
```
cf ba bind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd class="pd">Name of your security group</dd>
</dl>

You can also use **`ba brsg`** as an alias for the longer **`ba bind-running-security-group`** command name.
{: tip}

To bind a security group to a space, use the following command:
```
cf ba bind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>The name of the security group.</dd>
<dt>org</dt>
<dd>The name of the organization to bind the security group to.</dd>
<dt>space</dt>
<dd>The name of the space within the organization to bind the security group to.</dd>
</dl>

You can also use **`ba bsg`** as an alias for the longer **`ba bind-security-group`** command name.
{: tip}

For more information about binding security groups, see [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: external}.

### Unbinding security groups
{: #cliunbindsecgro}

Unbinding the Default Staging group set from the two IBM-created security groups, `public_networks` and `dns`, disables global access to the outside network. Use caution and understand the ramifications it has on all staging apps in your environment.

To unbind from a Default Staging security group set, use the following command:
```
cf ba unbind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>The name of your security group.</dd>
</dl>

You can also use **`ba ussg`** as an alias for the longer **`ba unbind-staging-security-group`** command name.
{: tip}

Unbinding the Default Running group set from the two IBM-created security groups, `public_networks` and `dns` disables global access to the outside network and must be used with caution and understanding of the ramifications it has on all running apps in your environment.

To unbind from a Default Running security group set, use the following command:
```
cf ba unbind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>The name of your security group.</dd>
</dl>

You can also use **`ba brsg`** as an alias for the longer **`ba unbind-running-security-group`** command name.
{: tip}

To unbind a security group to a space, use the following command:
```
cf ba unbind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>The name of the security group.</dd>
<dt>org</dt>
<dd>The name of the organization to unbind the security group from.</dd>
<dt>space</dt>
<dd>The name of the space within the organization to unbind the security group from.</dd>
</dl>

You can also use **`ba usg`** as an alias for the longer **`ba unbind-security-group`** command name.
{: tip}

For more information about unbinding security groups, see [Unbinding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: external}.

## Administering buildpacks
{: #admin_buildpack}

### Listing buildpacks
{: #clilistbuildpack}

If you have the apps catalog write permissions, you can list buildpacks.

To list all buildpacks or view a specific buildpack, use the following command:
```
cf ba buildpacks buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>An optional parameter to specify a particular buildpack to view.</dd>
</dl>

You can also use **`ba lb`** as an alias for the longer **`ba buildpacks`** command name.
{: tip}

### Creating and uploading a buildpack
{: #clicreupbuildpack}

If you have the apps catalog write permissions, you can create and upload a buildpack. You can upload any compressed file that has a `.zip` file type.

To upload a buildpack, use the following command:
```
cf ba create-buildpack buildpack_name file_path position
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>The name of the buildpack to upload.</dd>
<dt>file_path</dt>
<dd>The path to the buildpack compressed file.</dd>
<dt>position</dt>
<dd>The order in which the buildpacks are checked during buildpack auto-detection.</dd>
</dl>

You can also use **`ba cb`** as an alias for the longer **`ba create-buildpack`** command name.
{: tip}

### Updating a buildpack
{: #cliupdabuildpack}

If you have the apps catalog write permissions, you can update an existing buildpack.

To update a buildpack, use the following command:
```
cf ba update-buildpack buildpack_name position enabled locked
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>The name of the buildpack to update.</dd>
<dt>position</dt>
<dd>The order in which the buildpacks are checked during buildpack auto-detection.</dd>
<dt>enabled</dt>
<dd>Indicates whether the buildpack is used for staging.</dd>
<dt>locked</dt>
<dd>Indicates whether the buildpack is locked to prevent updates.</dd>
</dl>

You can also use **`ba ub`** as an alias for the longer **`ba update-buildpack`** command name.
{: tip}

### Deleting a buildpack
{: #clidelbuildpack}

If you have the apps catalog write permissions, you can delete an existing buildpack.

To delete a buildpack, use the following command:
```
cf ba delete-buildpack buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>The name of the buildpack to delete.</dd>
</dl>

You can also use **`ba db`** as an alias for the longer **`ba delete-buildpack`** command name.
{: tip}
