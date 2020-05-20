---

copyright:
  years: 2019, 2020
lastupdated: "2020-05-20"

keywords: cli

subcollection: cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# Catalogs management CLI plug-in
{: #manage-catalogs-plugin}


The {{site.data.keyword.cloud}} catalogs management command-line interface (CLI) provides extra capabilities for catalogs. You can use this {{site.data.keyword.cloud_notm}} CLI to manage your private catalogs that are only available to users in your account, onboard new private software offerings, and manage catalog visibility between the public catalog and your private catalogs.
{:shortdesc} 

## Before you begin
{: #prereqs-managecatalogs}

* Install the {{site.data.keyword.cloud_notm}} CLI. For more information, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started). The prefix for running commands by using the {{site.data.keyword.cloud_notm}} CLI is `ibmcloud`.
* Before you run the registry commands, log in to {{site.data.keyword.cloud_notm}} with the `ibmcloud login` command to generate an access token and authenticate your session.


## Installing the catalogs management plug-in
{: #install-managecatalogs}

To install the catalogs management plug-in, run the following command:

```
ibmcloud plugin install catalogs-management
```

In the command line, you are notified when updates to the `ibmcloud` CLI and `catalogs-management` CLI plug-in are available. Ensure that you keep your CLI up-to-date so that you can use all the available commands and flags.

If you want to view the current version of your `catalogs-management` CLI plug-in, run `ibmcloud plugin list`.

Don't put personal information in your catalog names or catalog descriptions.
{: important}

## ibmcloud catalog create
{: #create-catalog}

Use this command to create a new private catalog in your account. A private catalog is used to organize a set of offerings, private ones you add or references to public IBM Cloud catalog offerings, for users in your account to access. A user must have access to your private catalog through an IAM access policy and the resource group that contains your private catalog to see the offerings.

You must target a resource group to create a catalog, as the catalog will exist in the context of a particular resource group. To get list of resource groups, you can run `ibmcloud resource groups`, and then `ibmcloud target -g "resource group"`.
{: important}

```
ibmcloud catalog create --name CATALOG [--catalog-description "DESCRIPTION"]
```

### Command options
{: #create-catalog-options}

   <dl>
   <dt>--name CATALOG</dt>
   <dd>The catalog name.</dd>
   <dt>--catalog-description DESCRIPTION (optional)</dt>
   <dd>Short description for the new catalog.</dd>
   </dl>
   
### Example
{: #create-example}

Create a catalog called `dev-catalog` with the description `a catalog for development and testing purpsoses`.

```
ibmcloud catalog create --name dev-catalog --catalog-description "a catalog for development and testing purposes"
```

## ibmcloud catalog list
{: #get-catalogs}

Run the following command to retrieve list of catalogs in this particular account.

```
ibmcloud catalog list [--output FORMAT]
```

### Command options
{: #get-catalogs-options}

  <dl>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl>

### Output
{: #get-catalogs-output}

The command returns the following output:

```
Name                                           ID                                     Description                   Last Updated
dev-catalog                                    93f592fb-e09b-4a53-bbd9-92f6ab9e253b   short-description             2019-11-21 21:28:28.347 +0000 UTC         
ABDemoTestCatalog                              7a246530-e191-45e2-87cc-07c8c7033d2b   short-description             2019-08-19 17:43:48.59 +0000 UTC
```
{: screen}


## ibmcloud catalog get
{: #get-catalog}

Run the following command to retrieve information for a particular catalog in this account.

```
ibmcloud catalog get --catalog CATALOG [--output FORMAT]
```

### Command options
{: #get-catalog-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl>

### Output
{: #get-catalog-output}

The command returns the following output:

```
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

```
ibmcloud catalog delete --catalog CATALOG
```

### Command options
{: #delete-catalog-options}

  <dl>
   <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  </dl>

## ibmcloud catalog search
{: #search-catalog}

Run the following command to search the public catalog for published offerings. This includes managed services, software, and software published from your own account.

```
ibmcloud catalog search <QUERY> [--catalog CATALOG] [--type TYPE] [-r, --region REGION] [-k, --kind KIND] [--fields FIELDS] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--global]
```

### Command options
{: #search-catalog-options}

  <dl>
  <dt>--type TYPE (optional)</dt>
  <dd>Optional. Default is "services". Valid options are "services" and "software".<dd>
  <dt>--catalog CATALOG (optional)</dt>
  <dd>Search for the software published by your account. Specify the catalog name or ID to search by.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only alternative options are "json" and "csv". json`</dd>
  <dt>--kind KIND (optional)</dt>
  <dd>Flag is only valid for services search. Provide a comma separated list of offering kinds.s</dd>
  <dt>--region REGION (optional)</dt>
  <dd>Flag is only valid for services search. Provide a comma separated list of regions. Run "ibmcloud cs regions" for valid list.</dd>
  <dt>--price PRICE (optional)</dt>
  <dd>Flag is only valid for services search. Provide a comma separated list of pricing types.</dd>
  <dt>--tag TAG (optional)</dt>
  <dd>Flag is only valid for services search. Provide a comma separated list of tags.</dd>
  <dt>--global (optional)</dt>
  <dd>Flag is only valid for services search. Use it to operate in global scope.</dd>
  <dt>--sort-by TYPE (optional)</dt>
  <dd>Flag is only valid for services search and used to order the search result. Available options **name**, **displayname**, **kind**, **provider**, **created**, and **updated**.</dd>
  <dt>--reverse (optional)</dt>
  <dd>Flag is only valid for services search. Use it to reverse order the sorting order.</dd>
  <dt>--fields FIELDS (optional)</dt>
  <dd>Flag is only valid for services search. Customize table(i.e., --fields name,kind,metadata.service.iam_compatible</dd>
  </dl>

### Output
{: #search-catalog-output}

The command returns the following output:

```
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

```
ibmcloud catalog filter get --catalog CATALOG [--output FORMAT]
```

### Command options
{: #get-filter-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl>

### Output
{: #get-filter-output}

The command returns the following output:

```
Account: the IBM catalog is visible to all users in this account.

Filter:
Including IBM Cloud Catalog

Type           Include   Tags
Pricing plan   false     Free
Provider       false     Third Party
```
{: screen}

## ibmcloud catalog filter create
{: #create-filter}

Run the following command to create a new filter. If a filter already exists, this will override the current filter.

```
ibmcloud catalog filter create [--catalog CATALOG] [--category CATEGORY] [--compliance COMPLIANCE] [--deployment-target TARGET] [--exclude-list LIST] [--include-all ALL] [--include-list LIST] [--offering-format FORMAT] [--pricing-plan PLAN] [--provider PROVIDER] [--release RELEASE] [--type TYPE]
```

### Command options
{: #create-filter-options}

  <dl>
  <dt>--catalog CATALOG (optional)</dt>
  <dd>Specify the catalog name or ID. If not specified, the filter will be created on the account level.</dd>
  <dt>hide-ibm-catalog (optional)</dt>
  <dd>By default, the catalog is visible to all users in this account. By providing this flag, You can make products available only to the users you choose by turning off visibility to the IBM Cloud catalog and adding the products to your private catalogs.
  <dt>--include-all BOOLEAN (optional)</dt>
  <dd>Default is true if flag not provided. Valid values are "true" and "false". if true, the filter defaults to include the whole public catalog, and subsequent filters are exclusions. If false, the filter excludes the whole public catalog, and subsequent flags are inclusions.</dd>
  <dt>--offering-format FORMAT (optional)</dt>
  <dt>--category CATEGORY (optional)</dt>
  <dd>Provide comma separated list of category names or tags you would like to include or exclude. Run "ibmcloud catalog offering category-options" to see all options</dd>
  <dt>--compliance TYPE (optional)</dt>
  <dd>Provide comma separated list of compliance categories you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--deployment-target TARGET (optional)</dt>
  <dd>Provide comma separated list of deployment targets you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--exclude-list LIST (optional)</dt>
  <dd>Provide comma separated list of offerings IDs or names that must be excluded in filtered public catalog.</dd>
  <dt>--include-list LIST (optional)</dt>
  <dd>Provide comma separated list of offerings IDs or names that must be included in filtered public catalog.</dd>
  <dd>Provide comma separated list of offering formats you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--pricing-plan PLAN (options)</dt>
  <dd>Provide comma separated list of pricing plans you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--provider PROVIDER (optional)</dt>
  <dd>Provide comma separated list of providers you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--release RELEASE (optional)</dt>
  <dd>Provide comma separated list of release categories you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  <dt>--type TYPE (optional)</dt>
  <dd>Provide comma separated list of types you would like to include or exclude. Run 'ibmcloud catalog filter options' to see all options</dd>
  </dl>

## ibmcloud catalog filter delete
{: #delete-filter}

Run the following command to delete the filter. This defaults to the account level unless a catalog is specified. It will reset filter to include the whole public catalog.

```
ibmcloud catalog filter delete --catalog CATALOG
```

### Command options
{: #delete-filter-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  </dl>

## ibmcloud catalog filter hide-ibm-public-catalog
{: #hide-catalog-filter}

By default, the IBM public catalog is visible to all users in this account. You can make products available only to the users you choose by turning off visibility to the IBM Cloud catalog and adding the products to your private catalogs.

```
ibmcloud catalog filter hide-ibm-public-catalog
```

## ibmcloud catalog filter show-ibm-public-catalog
{: #show-catalog-filter}

By default, the IBM public catalog is visible to all users in this account. You can make products available only to the users you choose by turning off visibility to the IBM Cloud catalog and adding the products to your private catalogs.

```
ibmcloud catalog filter show-ibm-public-catalog
```


## ibmcloud catalog filter options
{: #options-filter}

Run the following command to retrieve the filter options for each filter category.

```
ibmcloud catalog filter options
```

### Command options
{: #options-filter-options}

  <dl>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl>

### Output
{: #options-filter-output}

The command returns the following output:

```
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

Run the following command to create a new offering in private catalog in this account.

```
ibmcloud catalog offering create --catalog CATALOG --zipurl URL [--include-config]
```

### Command options
{: #create-offering-options}

  <dl>
  <dt>--catalog CATALOG_NAME</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--zipurl URL</dt>
  <dd>URL pointing to zip of the offering</dd>
  <dt>--include-config (optional)</dt>
  <dd>If provided, all configuration values are included and available when you create the offering in the account.</dd>
  </dl>

## ibmcloud catalog offering list
{: #list-offering-options}

Run the following command to get details about the offerings in your catalogs. This command provides the ability to filter by private catalog, offering, and version.

```
ibmcloud catalog offering list [--catalog CATALOG] [--offering OFFERING_NAME] [--version VERSION] [--output FORMAT]
```

### Command options
{: #list-offering-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl> 
  
### Example
{: #list-example}

List all of the offerings that are in the `dev-catalog`.

```
ibmcloud catalog offering list --catalog dev-catalog
```


### Output
{: #list-offering-output}

The command returns the following output:

```
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

Run the following command to get details about the offerings in your catalogs. This command provides the ability to filter by private catalog, offering, and version.

```
ibmcloud catalog offering search [--catalog CATALOG] [--offering OFFERING_NAME] [--version VERSION] [--output FORMAT]
```

### Command options
{: #search-offering-options}

  <dl>
  <dt>--catalog CATALOG (optional)</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--offering OFFERING (optional)</dt>
  <dd>The offering name or ID.</dd>
  <dt>--version VERSION (optional)</dt>
  <dd>The version name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl> 
  
### Example
{: #search-example}

List all of the offerings that are in the `dev-catalog`.

```
ibmcloud catalog offering list --catalog dev-catalog
```


### Output
{: #search-offering-output}

The command returns the following output:

```
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

Run the following command to get details about an offering in the catalog.

```
ibmcloud catalog offering get --catalog CATALOG --offering OFFERING_NAME [--output FORMAT]
```

### Command options
{: #get-offering-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--offering OFFERING_NAME</dt>
  <dd>The offering name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl>

### Output
{: #get-offering-output}

The command returns the following output:

```
Name           Current State   Version Locator
dev-offering
|__
   |__1.0.0    Draft           480fb4e3-d7ba-4e9b-9d4c-42f0ab811040.a92f5409-ebd9-413c-88ae-7ed311c1b793
```
{: screen}


## ibmcloud catalog offering import-version
{: #import-offering-version}

Run the following command to import a new version of an offering in your private catalog.

```
ibmcloud catalog offering import-version --catalog CATALOG --offering OFFERING_NAME --zipurl URL [--target-version APP_VERSION] [--include-config]
```
      
### Command options
{: #import-offering-version-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--offering OFFERING_NAME</dt>
  <dd>The offering name or ID.</dd>
  <dt>--zipurl URL</dt>
  <dd>URL pointing to zip of the offering</dd>
  <dt>--target-version APP_VERSION (optional)</dt>
  <dd>The application version of the \"tgz\" being imported.</dd>
  <dt>--include-config (optional)</dt>
  <dd>If provided, all configurations values are included and available when you create the offering in the account.</dd>
  </dl> 

## ibmcloud catalog offering preinstall
{: #preinstall-offering}

Run the following command to run the preinstallation script for a particular offering.

```
ibmcloud catalog offering preinstall --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME
```

### Command options
{: #preinstall-offering-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering and version that you'd like to use.</dd>
  <dt>--cluster CLUSTER_ID</dt>
  <dd>Provide the cluster ID of the cluster where you want to install this offering.</dd>
  <dt>--namespace NAME</dt>
  <dd>Provide the namespace you'd like to use. You can specify a new one and it is automatically created as part of the preinstallation.</dd>
  </dl> 
  
### Example
{: #preinstall-example}

Run the preinstallation script for an offering with a version locator number of `b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4` in cluster with ID `bn5ebho206o7fg45f2e0` in the namespace called `test-namespace`. 

```
ibmcloud catalog offering preinstall --version-locator b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4 --cluster bn5ebho206o7fg45f2e0 --namespace test-namespace
```

## ibmcloud catalog offering preinstall-status
{: #preinstall-status-offering}

Run the following command to get the preinstallation status of an ongoing preinstallation.

```
ibmcloud catalog offering preinstall-status --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME [--output FORMAT]
```

### Command options
{: #preinstall-status-offering-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering and version that you'd like to use.</dd>
  <dt>--cluster CLUSTER_ID</dt>
  <dd>Provide the cluster ID of the cluster where the preinstallation was run.</dd>
  <dt>--namespace NAME</dt>
  <dd>Provide the namespace used for the preinstallation.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`.</dd>
  </dl> 

## ibmcloud catalog offering validate
{: #validate-offering}

Run the following command to validate a new version of an offering in your private catalog. Offerings must be validated to ensure that they work as expected before they can be published to the account for other users to create an instance from the private catalog.

```
ibmcloud catalog offering validate --version-locator VERSION_NUMBER --cluster CLUSTER_ID --namespace NAME [--overrride-values VALUES|FILENAME]
```

### Command options
{: #validate-offering-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering/version you'd like to use.</dd>
  <dt>--cluster CLUSTER_ID</dt>
  <dd>Provide the cluster ID of the cluster where you want to install this offering.</dd>
  <dt>--namespace NAME</dt>
  <dd>Provide the namespace you'd like to use. You can specify a new one and it is automatically created as part of the preinstallation.</dd>
  <dt>--override-values VALUES|FILENAME (optional)</dt>
  <dd>Provide any custom configurations for the installation. You can provide this either in line or by using a JSON or TXT file, for example `override-values values.json`</dd>
  </dl> 
  
### Example
{: #validate-example}

Validate an offering with the version locator `b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4` in a cluster with the ID `bn5ebho206o7fg45f2e0` within a namespace called `test-namespace`. This installation has custom configurations, so the values are provided by using a `values.json` file.

```
ibmcloud catalog offering validate --version-locator b636d651-8489-4425-bd6a-f30af1603577.18aad484-c78b-4269-808b-52027621abd4 --cluster bn5ebho206o7fg45f2e0 --namespace test-namespace --overrride-values values.json
```

Override values example format from the `values.json` file:

```
{
  "username": "provision-test-1",
  "password": "passw0rd"
}
```

## ibmcloud catalog offering validate-status
{: #validate-status-offering}

Run the following command to get the validation status of an ongoing validation.

```
ibmcloud catalog offering validate-status --version-locator VERSION_NUMBER [--output FORMAT]
```

### Command options
{: #validate-status-offering-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`.</dd>
  </dl> 


## ibmcloud catalog offering category-options
{: #category-options-offering}

Run the following command to retrieve list of category choices.

```
ibmcloud catalog offering category-options [--output FORMAT]
```

### Command options
{: #category-options-offering-options}

  <dl>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`.</dd>
  </dl>

### Example
{: #categroy-options-offering-example}

```
ibmcloud catalog offering category-options
```


### Output
{: #category-options-offering-output}

The command returns the following output:

```
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

Run the following command to add a category tag to an offering. You can provide either the category name or tag, which you can find by running ibmcloud catalog offering category-options. The Offerings must be placed in a category to be visible in the catalog.

```
ibmcloud catalog offering category-options [--output FORMAT]
```

### Command options
{: #add-category-offering-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--offering OFFERING</dt>
  <dd>The offering name or ID.</dd>
  <dt>--category CATEGORY</dt>
  </dl>category ID</dt>

### Example
{: #categroy-options-offering-example}

```
ibmcloud catalog offering add-category --catalog dev-catalog --offering dev-offering --category dev_ops
```

## ibmcloud catalog offering create-draft
{: #create-offering-draft}

Run the following command to create a draft of an existing version. This is useful for making changes to an existing version that you would like to publish without introducing a new version. Some changes, like changing the source file, do require revalidating the offering.

```
ibmcloud catalog offering create-draft --version-locator VERSION_NUMBER [--output FORMAT]
```

### Command options
{: #create-offering-draft-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`.</dd>
  </dl> 

## ibmcloud catalog offering refresh-version
{: #refresh-offering-version}

Run the following command to create a change the source file of a draft version. This is useful for updating an existing version. 

```
ibmcloud catalog offering refresh-version --version-locator VERSION_NUMBER --zipurl URL [--include-config]
```

### Command options
{: #refresh-offering-version-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  <dt>--zipurl URL</dt>
  <dd>URL pointing to zip of the offering</dd>
  <dt>--include-config (optional)</dt>
  <dd>If provided, all configuration values are included and available when you create the offering in the account.</dd>
  </dl> 

## ibmcloud catalog offering merge-draft
{: #merge-offering-draft-version}

Run the following command to merge a draft version of an offering.

```
ibmcloud catalog offering merge-draft --version-locator VERSION_NUMBER
```

### Command options
{: #merge-offering-draft-version-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 


## ibmcloud catalog offering publish-to-account
{: #publish-offering-to-account}

Run the following command to publish a new version or offering from your private catalog to the account. After the offering is published, users in the account with access to the private catalog and its containing resource group can create an instance and start using it.

```
ibmcloud catalog offering publish-to-account --version-locator VERSION_NUMBER
```

### Command options
{: #publish-offering-to-account-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 
  
<!-- These commands below will NOT go public and will always remain internal until we remove them entirely in favor of the provider portal which will be used to onboard content offerings to the public catalog. -->

## ibmcloud catalog offering publish-to-ibm
{: #publish-offering-to-ibm}

Run the following command to publish an offering that is already availble in your account to all IBMers. This part of the publication process creates a tile in the staging and production catalogs that is visible only to IBMers. Publishing to IBMers only enables you to test out the offering in production before you make it available to all users in the IBM Cloud catalog.

```
ibmcloud catalog offering publish-to-ibm --version-locator VERSION_NUMBER
```

### Command options
{: #publish-offering-to-ibm-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 

## ibmcloud catalog offering publish-to-public
{: #publish-offering-to-public}

Run the following command to publish your private offering to the IBM Cloud catalog for all users to see and use. To get to this step in the publication process, you must first publish the offering to your account and to all IBMers to complete the testing process. After your testing is complete, you can run this command. 

This option does require an approval process from offering management. As soon as your approval is complete, your tile is available for all IBM Cloud customers to see and use.
{: important}

```
ibmcloud catalog offering publish-to-public --version-locator VERSION_NUMBER
```

### Command options
{: #publish-offering-to-public-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 

## ibmcloud catalog offering deprecate
{: #publish-offering-deprecate}

Run the following command to deprecate a previously published offering version in the IBM Cloud catalog.

```
ibmcloud catalog offering deprecate --version-locator VERSION_NUMBER
```

### Command options
{: #publish-offering-deprecate-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 

## ibmcloud catalog offering restore
{: #publish-offering-restore}

Run the following command to restore a previously deprecated offering version in the IBM Cloud catalog. Restoring it will place the version in draft state. After validating it, you will be able to restore the original version to the published state it was in prior to being deprecated.

```
ibmcloud catalog offering restore --version-locator VERSION_NUMBER
```

### Command options
{: #publish-offering-restore-options}

  <dl>
  <dt>--version-locator VERSION_NUMBER</dt>
  <dd>To get the version locator for this offering, run `ibmcloud catalog offering list` and locate the specified offering or version you want to use.</dd>
  </dl> 
