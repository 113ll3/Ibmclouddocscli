---

copyright:
  years: 2019, 2021
lastupdated: "2021-11-04"

keywords: cli, catalogs management

subcollection: cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:important: .important}
{:tip: .tip}

# Catalogs management CLI plug-in
{: #manage-catalogs-plugin}

The {{site.data.keyword.cloud}} catalogs management command-line interface (CLI) provides extra capabilities for working with products in the {{site.data.keyword.cloud_notm}} catalog and the private catalogs in your account. You can use this CLI plug-in to manage your private catalogs that are only available to users in your account, onboard private software products, and manage catalog visibility between the public catalog and your private catalogs.
{: shortdesc} 

## Before you begin
{: #prereqs-managecatalogs}

* Install the {{site.data.keyword.cloud_notm}} CLI. For more information, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started). The prefix for running commands by using the {{site.data.keyword.cloud_notm}} CLI is `ibmcloud`.
* Before you run the registry commands, log in to {{site.data.keyword.cloud_notm}} with the `ibmcloud login` command to generate an access token and authenticate your session.


## Installing the catalogs management plug-in
{: #install-managecatalogs}

To install the catalogs management plug-in, run the following command:

```bash
ibmcloud plugin install catalogs-management
```
{: codeblock}

In the command line, you are notified when updates to the `ibmcloud` CLI and `catalogs-management` CLI plug-in are available. Ensure that you keep your CLI up-to-date so that you can use all the available commands and flags.

If you want to view the current version of your `catalogs-management` CLI plug-in, run `ibmcloud plugin list`.

To maintain privacy and security, don't put personal information in your catalog names or catalog descriptions.
{: important}

## ibmcloud catalog create
{: #create-catalog}

Use this command to create a new private catalog in your account. A private catalog is used to organize a set of products, private ones you add, or references to products in the {{site.data.keyword.cloud_notm}} catalog. A user must have access to your private catalog through an IAM access policy and the resource group that contains your private catalog to view and work with the products.

You must target a resource group to create a catalog because the catalog exists in the context of a particular resource group. To get the list of resource groups, you can run the `ibmcloud resource groups` command, and then the `ibmcloud target -g "resource group"` command.
{: important}

```bash
ibmcloud catalog create --name CATALOG [--catalog-description "DESCRIPTION"]
```
{: codeblock}

### Command options
{: #create-catalog-options}

--name CATALOG

:   The catalog name.

--catalog-description DESCRIPTION (optional)

:   Short description for the new catalog.

   
### Example
{: #create-example}

Create a catalog called `dev-catalog` with the description `a catalog for development and testing purpsoses`.

```bash
ibmcloud catalog create --name dev-catalog --catalog-description "a catalog for development and testing purposes"
```
{: codeblock}

## ibmcloud catalog list
{: #get-catalogs}

Run the following command to retrieve the list of catalogs in this particular account.

```bash
ibmcloud catalog list [--output FORMAT]
```
{: codeblock}

### Command options
{: #get-catalogs-options}

--output FORMAT (optional)

:   Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`

### Output
{: #get-catalogs-output}

The command returns the following output:

```bash
Name                                           ID                                     Description                   Last Updated
dev-catalog                                    93f592fb-e09b-4a53-bbd9-92f6ab9e253b   short-description             2019-11-21 21:28:28.347 +0000 UTC         
ABDemoTestCatalog                              7a246530-e191-45e2-87cc-07c8c7033d2b   short-description             2019-08-19 17:43:48.59 +0000 UTC
```
{: screen}


## ibmcloud catalog get
{: #get-catalog}

Run the following command to retrieve information for a particular catalog in the account.

```bash
ibmcloud catalog get --catalog CATALOG [--output FORMAT]
```
{: codeblock}

### Command options
{: #get-catalog-options}


--catalog CATALOG

:   The catalog name or ID.

--output FORMAT (optional)

:   Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`

### Output
{: #get-catalog-output}

The command returns the following output:

```bash
Name                                     Current State   Version Locator
dev-catalog
|__dev-offering
|  |__Openshift
|     |__1.0.0                           Draft           480fb4e3-d7ba-4e9b-9d4c-42f0ab811040.fd8f91a3-8027-4919-ad6d-c5189a4a8ee
```
{: screen}

## ibmcloud catalog delete
{: #delete-catalog}

Run the following command to delete a particular catalog in the account.

```bash
ibmcloud catalog delete --catalog CATALOG
```
{: codeblock}

### Command options
{: #delete-catalog-options}

--catalog CATALOG

:   The catalog name or ID.

## ibmcloud catalog search
{: #search-catalog}

Run the following command to search the public catalog for published products, including services and software.

```bash
ibmcloud catalog search <QUERY> [--catalog CATALOG] [--type TYPE] [-r, --region REGION] [-k, --kind KIND] [--fields FIELDS] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--global]
```
{: codeblock}

### Command options
{: #search-catalog-options}


--type TYPE (optional)

:   Optional. Default is `services`. Valid options are `services` and `software`.

--catalog CATALOG (optional)

:   Search for the software published by your account. Specify the catalog name or ID to search by.

--output FORMAT (optional)

:   Specifies output format. Default is terminal-friendly and the only alternative options are `json` and `csv`.

--kind KIND (optional)

:   Flag is only valid for services search. Provide a comma-separated list of types of products.

--region REGION (optional)

:   Flag is only valid for services search. Provide a comma-separated list of regions. Run `ibmcloud cs regions` to return a valid list.

--price PRICE (optional)

:   Flag is only valid for services search. Provide a comma-separated list of pricing types.

--tag TAG (optional)

:   Flag is only valid for services search. Provide a comma-separated list of tags.

--global (optional)

:   Flag is only valid for services search. Use it to operate in global scope.

--sort-by TYPE (optional)

:   Flag is only valid for services search and used to order the search result. Available options are `name`, `displayname`, `kind`, `provider`, `created`, and `updated`.

--reverse (optional)

:   Flag is only valid for services search. Use it to reverse the sorting order.

--fields FIELDS (optional)

:   Flag is only valid for services search. Customize the table, for example, `--fields name,kind,metadata.service.iam_compatible`.


### Output
{: #search-catalog-output}

The command returns the following output:

```bash
Name                                       ID                                                    Category
2 Zone VPC                                 f10d9ae9-ac94-4718-b24a-3994241ae2a4-global           Networking
Apache                                     Qml0bmFtaS1hcGFjaGU=-global                           Developer Tools
Apache Airflow                             Qml0bmFtaS1haXJmbG93-global                           Databases
Apache Airflow                             Qml0bmFtaS1haXJmbG93-global                           Developer Tools
```
{: screen}

## ibmcloud catalog filter get
{: #get-filter}

Run the following command to retrieve filter details for either the account or a particular catalog.

```bash
ibmcloud catalog filter get --catalog CATALOG [--output FORMAT]
```
{: codeblock}

### Command options
{: #get-filter-options}


--catalog CATALOG

:   The catalog name or ID.

--account-group ACCOUNT GROUP

:   The account group name or ID. This field applies only to enterprise accounts.

--output FORMAT (optional)

:   Specifies output format. Default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.


### Output
{: #get-filter-output}

The command returns the following output:

```
Account: The IBM Cloud catalog is visible to all users in this account.

Filter:
Including IBM Cloud catalog

Type           Include   Tags
Pricing plan   false     Free
Provider       false     Third Party
```
{: screen}

## ibmcloud catalog filter create
{: #create-filter}

Run the following command to create a new filter. If a filter exists, this command overrides the current filter.

```bash
ibmcloud catalog filter create [--catalog CATALOG] [--category CATEGORY] [--compliance COMPLIANCE] [--deployment-target TARGET] [--exclude-list LIST] [--include-all ALL] [--include-list LIST] [--offering-format FORMAT] [--pricing-plan PLAN] [--provider PROVIDER] [--release RELEASE] [--type TYPE]
```
{: codeblock}

### Command options
{: #create-filter-options}

--catalog CATALOG (optional)

:   Specify the catalog name or ID. If not specified, the filter is created at the account level.

--account-group ACCOUNT GROUP

:   The account group name or ID. This option applies only to enterprise accounts.

--hide-ibm-catalog (optional)

:   By default, the catalog is visible to all users in this account. By providing this flag, you can make products available only to the users you choose by turning off visibility to the {{site.data.keyword.cloud_notm}} catalog and adding the products to your private catalogs.

--include-all BOOLEAN (optional)

:   Default is true if flag not provided. Valid values are `true` and `false`. If set to true, the filter defaults to include the entire public catalog, and subsequent filters are excluded. If set to false, the filter excludes the entire public catalog, and subsequent flags are included. For more information, see [Managing catalog settings](/docs/account?topic=account-filter-account).

--offering-format FORMAT (optional)
  
--category CATEGORY (optional)

:   Provide a comma-separated list of category names or tags you want to include or exclude. Run the `ibmcloud catalog offering category-options` command to view all options. Default is `Developer tools`.

--compliance TYPE (optional)

:   Provide a comma-separated list of compliance categories you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--deployment-target TARGET (optional)

:   Provide a comma-separated list of deployment targets you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--exclude-list LIST (optional)

:   Provide a comma-separated list of product IDs or names that must be excluded in the filtered public catalog.

--include-list LIST (optional)

:   Provide a comma-separated list of product IDs or names that must be included in the filtered public catalog.</d
:   Provide a comma-separated list of product formats you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--pricing-plan PLAN (options)

:   Provide a comma-separated list of pricing plans you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--provider PROVIDER (optional)

:   Provide a comma-separated list of providers you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--release RELEASE (optional)

:   Provide a comma-separated list of categories you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

--type TYPE (optional)

:   Provide a comma-separated list of software types you want to include or exclude. Run the `ibmcloud catalog filter options` command to view all options.

## ibmcloud catalog filter delete
{: #delete-filter}

Run the following command to delete an applied filter. This filter defaults to the account level unless a catalog is specified. As a result, the filter is reset to include all products in the public catalog.

```bash
ibmcloud catalog filter delete --catalog CATALOG
```
{: codeblock}

### Command options
{: #delete-filter-options}


--catalog CATALOG

:   The catalog name or ID.

--account-group ACCOUNT GROUP

:   The account group name or ID. This option applies only to enterprise accounts.

## ibmcloud catalog filter offering
{: #offering-filter}

Update the filter to include or exclude a particular product and any applicable pricing plans. This filter defaults to the account level unless a catalog or account group is specified.

```bash
ibmcloud catalog filter offering --offering PRODUCT-NAME
```
{: codeblock}

### Command options
{: #get-filter-offering-options}


--catalog CATALOG

:   The catalog name or ID.

--account-group ACCOUNT GROUP

:   The account group name or ID. This option applies only to enterprise accounts.

--plans-list PLANS LIST

:   A comma-separated list of plan IDs or names to include or exclude.

--offering OFFERING

:   The product name or ID.

--include

:   The default value is true if a flag is not provided. Valid values are `true` and `false`. If set to true, the product and plans provided are visible to users in the account. If set to false, the product and plans aren't visible to users in the account.

## ibmcloud catalog filter hide-ibm-public-catalog
{: #hide-filter}

By default, the {{site.data.keyword.cloud_notm}} catalog is visible to all users in the account. You can make products available only to the users you choose by turning off visibility to the {{site.data.keyword.cloud_notm}} catalog and adding the products to your private catalogs.

```bash
ibmcloud catalog filter hide-ibm-public-catalog
```
{: codeblock}

## ibmcloud catalog filter show-ibm-public-catalog
{: #show-filter}

By default, the {{site.data.keyword.cloud_notm}} catalog is visible to all users in the account. You can make products available only to the users you choose by turning off visibility to the {{site.data.keyword.cloud_notm}} catalog and adding the products to your private catalogs.

```bash
ibmcloud catalog filter show-ibm-public-catalog
```
{: codeblock}

## ibmcloud catalog filter options
{: #options-filter}

Run the following command to retrieve the filter options for each filter category.

```bash
ibmcloud catalog filter options
```
{: codeblock}

### Command options
{: #options-filter-options}


--output FORMAT (optional)

:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.

### Output
{: #options-filter-output}

The command returns the following output:

```bash
Offering format   ID
Cloud Paks        cloud_pak
Helm charts       helm
Terraform         terraform

Compliance                   ID
EU Supported                 eu_access
HIPAA Enabled                hipaa
IAM-enabled                  rc_compatible
Service Endpoint Supported   service_endpoint_supported
```
{: screen}

## ibmcloud catalog offering create
{: #create-offering}

Run the following command to add a product to a private catalog in the account.

```bash
ibmcloud catalog offering create [--catalog CATALOG_NAME] [--zipurl URL] [--include-config] [--target-version VERSION] [--token TOKEN]
```
{: codeblock}

### Command options
{: #create-offering-options}

--catalog CATALOG_NAME

:   The catalog name or ID.

--zipurl URL

:   URL pointing to .zip file of the product.

--target-version VERSION

:   Specify the version of the product. 

--include-config (optional)

:   If provided, all configuration values are included and available when you add the product.

--token TOKEN (optional)

:   Specify the personal access token for a private repository. 

## ibmcloud catalog offering list
{: #list-offering}

Run the following command to get details about the products in your private catalogs. This command provides a filter by private catalog, product, and version.

```bash
ibmcloud catalog offering list [--catalog CATALOG] [--offering OFFERING_NAME] [--version VERSION] [--output FORMAT]
```
{: codeblock}

### Command options
{: #list-offering-options}


--catalog CATALOG

:   The catalog name or ID.

--output FORMAT (optional)

:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.

  
### Example
{: #get-example}

List all of the products that are in the `dev-catalog` catalog.

```bash
ibmcloud catalog offering list --catalog dev-catalog
```
{: codeblock}

### Output
{: #list-offering-output}

The command returns the following output:

```bash
Name                                   ID                                     Current State   Version Locator
Cloud Pak for Automation               cb90274e-398b-4373-9b28-d6428d3302df
|__OpenShift
   |__19.0.2                                                                  New             7b7e590f-259b-437b-b1f4-39e8615ed837.21d1d712-80ab-4318-9d05-73c6caaaee23
Cloud Pak for Data                     8993c7b1-1794-4447-9275-db83faa08ee4
|__OpenShift
   |__2.1.0.2                                                                 New             7b7e590f-259b-437b-b1f4-39e8615ed837.ab6ba56f-788d-4d6b-b880-a1001fca8451
harbor                                 927adb44-6784-4bec-a771-f639900f07f1
|__Kubernetes
   |__1.9.1                                                                   New             7b7e590f-259b-437b-b1f4-39e8615ed837.e437b06c-273f-49de-8c44-f55e408abf78
IBM Starter Collection for Openshift   fd1857f4-cf17-4e97-9443-b615bc71f6a0
|__OpenShift
   |__0.0.1                                                                   New             7b7e590f-259b-437b-b1f4-39e8615ed837.72e0f636-9dc4-49ae-b3c2-7a5de90487b9
tf_cloudless_sleepy-2.0                c260a67a-1b25-49fc-9896-46e7e6212990
|__
   |__1.0.0                                                                   New             7b7e590f-259b-437b-b1f4-39e8615ed837.965df91d-5760-4872-adf6-4019796c06b0
   |__1.0.1                                                                   New             7b7e590f-259b-437b-b1f4-39e8615ed837.aff4cecb-4c9b-41ba-ae3d-71f4217dc0bc
```
{: screen}

## ibmcloud catalog offering search
{: #search-offering-options}

Run the following command to get details about the products in your private catalogs. This command provides a filter by private catalog, product, and version.

```bash
ibmcloud catalog offering search [--catalog CATALOG] [--offering OFFERING_NAME] [--version VERSION] [--output FORMAT]
```
{: codeblock}

### Command options
{: #search-offering-options}


--catalog CATALOG (optional)

:   The catalog name or ID.

--offering OFFERING (optional)

:   The product name or ID.

--version VERSION (optional)

:   The version name or ID.

--output FORMAT (optional)

:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.

  
### Example
{: #search-example}

List all of the products that are in the `dev-catalog` catalog.

```bash
ibmcloud catalog offering list --catalog dev-catalog
```
{: codeblock}

### Output
{: #search-offering-output}

The command returns the following output:

```bash
Name                                     Current State          Version Locator
dev-catalog
|__dev-offering
|  |__Kubernetes
|     |__1.0.0                           Validated              b636d651-8489-4425-bd6a-f30af1603577.17ac792e-a603-4f1a-a1b6-48e90a46940c
|__dev-offering-2.0
|  |__Kubernetes
|     |__1.0.0                           Published to account   b636d651-8489-4425-bd6a-f30af1603577.decdb0e1-46d2-401a-b482-80f9d6855f98
```
{: screen}

## ibmcloud catalog offering get
{: #get-offering}

Run the following command to get details about a specific product in the catalog.

```bash
ibmcloud catalog offering get --catalog CATALOG --offering OFFERING_NAME [--output FORMAT]
```
{: codeblock}

### Command options
{: #get-offering-options}


--catalog CATALOG
:   The catalog name or ID.

--offering OFFERING_NAME
:   The product name or ID.

--output FORMAT (optional)
:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.


### Output
{: #get-offering-output}

The command returns the following output:

```bash
Name           Current State   Version Locator
dev-offering
|__
   |__1.0.0    Draft           480fb4e3-d7ba-4e9b-9d4c-42f0ab811040.a92f5409-ebd9-413c-88ae-7ed311c1b793
```
{: screen}


## ibmcloud catalog offering import-version
{: #import-offering-version}

Run the following command to import a new version of a product in your private catalog.

```bash
ibmcloud catalog offering import-version --catalog CATALOG --offering OFFERING_NAME --zipurl URL [--target-version APP_VERSION] [--include-config]
```
{: codeblock}

### Command options
{: #import-offering-version-options}


--catalog CATALOG
:   The catalog name or ID.

--offering OFFERING_NAME
:   :   The product name or ID.

--zipurl URL
:   URL pointing to the .zip file of the product.

--target-version APP_VERSION (optional)
:   The application version of the \"tgz\" being imported.

--include-config (optional)
:   If provided, all configurations values are included and available when you import the new version.


## ibmcloud catalog offering preinstall
{: #preinstall-offering}

Run the following command to run the preinstallation script for a particular product.

```bash
ibmcloud catalog offering preinstall --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME
```
{: codeblock}

### Command options
{: #preinstall-offering-options}


--version-locator VERSION_NUMBER
:   To get the version locator for this product, run the `ibmcloud catalog offering list` command and locate the specified product and version that you'd like to use.

--cluster CLUSTER_ID
:   Provide the cluster ID of the cluster where you want to install the product.

--namespace NAME
:   Provide the namespace you'd like to use. You can specify a new one and it is automatically created as part of the preinstallation.

  
### Example
{: #preinstall-example}

Run the preinstallation script for a product with a version locator number of `b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4` in cluster with ID `bn5ebho206o7fg45f2e0` in the namespace called `test-namespace`. 

```bash
ibmcloud catalog offering preinstall --version-locator b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4 --cluster bn5ebho206o7fg45f2e0 --namespace test-namespace
```
{: codeblock}

## ibmcloud catalog offering preinstall-status
{: #preinstall-status-offering}

Run the following command to get the status of an ongoing preinstallation.

```bash
ibmcloud catalog offering preinstall-status --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME [--output FORMAT]
```
{: codeblock}

### Command options
{: #preinstall-status-offering-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product and version that you'd like to use.

--cluster CLUSTER_ID
:   Provide the cluster ID of the cluster where the preinstallation was run.

--namespace NAME
:   Provide the namespace used for the preinstallation.

--output FORMAT (optional)
:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.


## ibmcloud catalog offering validate
{: #validate-offering}

Run the following command to validate a new version of a product in your private catalog. Products must be validated to ensure that they work as expected before they can be published to the account for other users to create an instance from the private catalog.

```bash
ibmcloud catalog offering validate --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME [--timeout TIMEOUT] [--wait WAIT] [--override-values VALUES|FILENAME] 
```
{: codeblock}

### Command options
{: #validate-offering-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product and version you'd like to use.

--cluster CLUSTER_ID
:   Provide the cluster ID of the cluster where you want to install the product.

--namespace NAME
:   Provide the namespace you'd like to use. You can specify a new one and it is automatically created as part of the preinstallation.

--timeout TIMEOUT
:   Specify in seconds how long the schematics workspace should wait before installing. Default is `180`.

--wait WAIT
:   Wait and track the progress of the schematics workspace job. If `true`, installation waits. If `false`, the software installs immediately. Default is `true`.

--override-values VALUES|FILENAME (optional)
:   Provide any custom configurations for the installation. You can provide this value either inline or by using a JSON or TXT file. For example, `override-values values.json`.
  
### Example
{: #validate-example}

Validate a product with the version locator `b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4` in a cluster with the ID `bn5ebho206o7fg45f2e0` within a namespace called `test-namespace`. This installation has custom configurations, so the values are provided by using a `values.json` file.

```bash
ibmcloud catalog offering validate --version-locator b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4 --cluster bn5ebho206o7fg45f2e0 --namespace test-namespace --override-values values.json
```
{: codeblock}

Override values example format from the `values.json` file:

```bash
{
  "username": "provision-test-1",
  "password": "passw0rd"
}
```
{: codeblock}

## ibmcloud catalog offering validate-status
{: #validate-status-offering}

Run the following command to get the status of an ongoing validation.

```bash
ibmcloud catalog offering validate-status --version-locator VERSION_NUMBER [--output FORMAT]
```
{: codeblock}

### Command options
{: #validate-status-offering-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list`command and locate the specified product or version you want to use.

--output FORMAT (optional)
:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.



## ibmcloud catalog offering category-options
{: #category-options-offering}

Run the following command to retrieve the list of category choices.

```bash
ibmcloud catalog offering category-options [--output FORMAT]
```
{: codeblock}

### Command options
{: #category-options-offering-options}


--output FORMAT (optional)
:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.


### Example
{: #category-options-offering-example}

```bash
ibmcloud catalog offering category-options
```
{: codeblock}


### Output
{: #category-options-offering-output}

The command returns the following output:

```bash
Name                    Tags                                                  Description
VPC Infrastructure      vpc                                                   Fully customizable, software-defined virtual network with superior isolation.
Compute                 compute,content,containers,openwhisk,vmware,runtime   Build your virtual environments
Containers              containers,clusters,registry                          Get started by creating a Kubernetes cluster, or manage your Docker images in the registry.
Networking              network                                               Order network.
Storage                 storage                                               Order storage.
```
{: screen}

## ibmcloud catalog offering add-category
{: #add-category-offering}

Run the following command to add a category tag to a product. You can provide either the category name or tag, which you can find by running the `ibmcloud catalog offering category-options` command. The products must be placed in a category to be visible in the catalog. Default is `Developer tools`.

```bash
ibmcloud catalog offering category-options [--output FORMAT]
```
{: codeblock}

### Command options
{: #add-category-offering-options}


--catalog CATALOG
:   The catalog name or ID.

--offering OFFERING
:   The product name or ID.

--category CATEGORY
:   The category ID.
  

### Example
{: #add-category-offering-example}

```bash
ibmcloud catalog offering add-category --catalog dev-catalog --offering dev-offering --category dev_ops
```
{: codeblock}

## ibmcloud catalog offering create-draft
{: #create-offering-draft}

Run the following command to create a draft of an existing version. This command is useful for changing an existing version that you want to publish without introducing a new version. Some changes, like changing the source file, require you to revalidate the product.

```bash
ibmcloud catalog offering create-draft --version-locator VERSION_NUMBER [--output FORMAT]
```
{: codeblock}

### Command options
{: #create-offering-draft-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product or version you want to use.

--output FORMAT (optional)
:   Specifies output format. The default is terminal-friendly and the only supported alternative is JSON, for example, `--output json`.


## ibmcloud catalog offering refresh-version
{: #refresh-offering-version}

Run the following command to create a change the source file of a draft version. This command is useful for updating an existing version. 

```bash
ibmcloud catalog offering refresh-version --version-locator VERSION_NUMBER --zipurl URL [--include-config]
```
{: codeblock}

### Command options
{: #refresh-offering-version-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product or version you want to use.

--zipurl URL
:   URL pointing to the .zip file of the product.

--include-config (optional)
:   If provided, all configuration values are included and available when you add the product.


## ibmcloud catalog offering merge-draft
{: #merge-offering-draft-version}

Run the following command to merge a draft version of a product.

```bash
ibmcloud catalog offering merge-draft --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #merge-offering-draft-version-options}

--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product or version you want to use.

## ibmcloud catalog offering publish-to-account
{: #publish-offering-to-account}

Run the following command to publish a new version or product from your private catalog to the account. After the product is published, users in the account who have access to the private catalog and its containing resource group can create an instance and start using it.

```bash
ibmcloud catalog offering publish-to-account --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #publish-offering-to-account-options}


--version-locator VERSION_NUMBER
:   To get the version locator for the product, run the `ibmcloud catalog offering list` command and locate the specified product or version you want to use.

## ibmcloud catalog offering workspaces
{: #get-workspaces}

Run the following command to get the schematics workspaces for a product version.

```bash
ibmcloud catalog offering workspaces [--version-locator VERSION_NUMBER] [output FORMAT] 
```
{: codeblock}

### Command options
{: #get-workspaces-options}

--version-locator VERSION_NUMBER

:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified version that you want to use.

--output FORMAT (optional)

:   Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example, `--output json`.

## ibmcloud catalog install
{: #install-software-version}

Run the following command to install a software version from the {{site.data.keyword.cloud_notm}} catalog.

```bash
ibmcloud catalog install [--version-locator VERSION_NUMBER] [--cluster CLUSTER_ID] [--namespace NAME] [--override-values VALUES] [--timeout TIMEOUT] [--wait WAIT] [--workspace-name NAME] [--workspace-tags TAGS]
```
{: codeblock}

### Command options
{: #install-software-version-options}

--version-locator VERSION_NUMBER

:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the version that you want to use.

--cluster CLUSTER_ID

:   Specify the cluster name or ID. 

--namespace NAME

:   Specify the namespace you'd like to use.

--override-values VALUES

:   Provide any custom configurations for the installation. You can provide this value either inline or by using a JSON or TXT file. For example, `override-values values.json`.

--timeout TIMEOUT

:   Specify in seconds how long the schematics workspace should wait before installing. Default is `180`.

--wait WAIT

:   Wait and track the progress of the schematics workspace job. If `true`, installation waits. If `false`, the software installs immediately. Default is `true`.

--workspace-name NAME (optional)

:   Provide a workspace name. Default is `OfferingName-Date`.

--workspace-tags TAGS (optional)

:   Provide a comma-separated list of tags.

<!-- These commands below will NOT go public and will always remain internal until we remove them entirely in favor of the provider portal which will be used to onboard content offerings to the public catalog. -->

## ibmcloud catalog offering publish-to-ibm
{: #publish-offering-to-ibm}

Run the following command to publish an offering that is already available in your account to all IBMers. This part of the publication process creates a tile in the staging and production catalogs that is visible only to IBMers. By publishing an offering to IBMers, you can test the offering in production before you make it available to all users in the {{site.data.keyword.cloud_notm}} catalog.

```bash
ibmcloud catalog offering publish-to-ibm --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #publish-offering-to-ibm-options}


--version-locator VERSION_NUMBER
:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.


## ibmcloud catalog offering publish-to-public
{: #publish-offering-to-public}

Run the following command to publish your private offering to the {{site.data.keyword.cloud_notm}} catalog for all users to see and use. To get to this step in the publication process, you must first publish the offering to your account and to all IBMers to complete the testing process. After your testing is complete, you can run this command. 

This option does require an approval process from offering management. As soon as your approval is complete, your tile is available for all {{site.data.keyword.cloud_notm}} customers to see and use.
{: important}

```bash
ibmcloud catalog offering publish-to-public --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #publish-offering-to-public-options}


--version-locator VERSION_NUMBER
:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.


## ibmcloud catalog offering deprecate
{: #publish-offering-deprecate}

Run the following command to deprecate a previously published offering version in the {{site.data.keyword.cloud_notm}}  catalog.

```bash
ibmcloud catalog offering deprecate --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #publish-offering-deprecate-options}


--version-locator VERSION_NUMBER
:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.


## ibmcloud catalog offering restore
{: #publish-offering-restore}

Run the following command to restore a previously deprecated offering version in the {{site.data.keyword.cloud_notm}} catalog. Restoring it places the version in draft state. After you validate it, you can restore the original version to the published state that it was in before it was deprecated.

```bash
ibmcloud catalog offering restore --version-locator VERSION_NUMBER
```
{: codeblock}

### Command options
{: #publish-offering-restore-options}

--version-locator VERSION_NUMBER

:   To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.
