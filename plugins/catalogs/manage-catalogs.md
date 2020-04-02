---

copyright:
  years: 2019, 2020
lastupdated: "2020-04-02"

keywords: catalog management cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# Catalog management CLI
{: #manage-catalogs-plugin}


The {{site.data.keyword.cloud}} catalog management command-line interface (CLI) provides extra capabilities for catalogs. You can use this {{site.data.keyword.cloud_notm}} CLI to manage your private catalogs that are only available to users in your account, onboard new private software offerings, and manage catalog visibility between the public catalog and your private catalogs.
{:shortdesc} 

## Before you begin
{: #prereqs-managecatalogs}

* Install the {{site.data.keyword.cloud_notm}} CLI. For more information, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started). The prefix for running commands by using the {{site.data.keyword.cloud_notm}} CLI is `ibmcloud`.
* Before you run the registry commands, log in to {{site.data.keyword.cloud_notm}} with the `ibmcloud login` command to generate an access token and authenticate your session.


## Installing the catalog management plug-in
{: #manage-catalogs-plugin}

To install the catalog management plug-in, run the following command:

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
ibmcloud catalog get --catalog CATALOG [--public] [--output FORMAT]
```

### Command options
{: #get-catalog-options}

  <dl>
  <dt>--catalog CATALOG</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--public (optional)</dt>
  <dd>Retreives all the offerings which are in the public catalog and private offerings which have been published to the account.</dd>
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


<!--## ibmcloud catalog filter - waiting for Gil to update
{: #catalog-filter}

Use this command to view and modify account and catalog filters. 

```
ibmcloud catalog filter -- 
```

### Command options
{: #catalog-filter-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>

### Example
{: #filter-example}

Create a filter that includes specific IBM products. This filtered view applies to all users with access to your private catalog.

```
ibmcloud catalog filter create --catalog "My first catalog" --exclude-all true  --provider IBM
```-->


<!--## ibmcloud catalog filter create - waiting for Gil to update
{: #filter-create}

Use this command to create a new filter. If a filter already exists, this will override the current filter. 

```
ibmcloud catalog filter create -- 
```

### Command options
{: #filter-create-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>

### Example
{: #filter-create-example}

Create a filter that includes only {{site.data.keyword.cloud_notm}} offerings in the catalog and excludes {{site.data.keyword.appid_short_notm}} from the catalog.
    
```
ibmcloud catalog filter create --include-all false --provider ibm_created --exclude-list appid
```-->


<!--## ibmcloud catalog filter delete - waiting for Gil to update
{: #filter-delete}

Use this command to delete the filter. This defaults to the account level unless a catalog is specified. it will reset filter include the whole public catalog.

```
ibmcloud catalog filter delete -- 
```

### Command options
{: #filter-delete-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>

### Example
{: #filter-delete-example}

Remove the existing filter that you created in the previous steps.
    
```
ibmcloud catalog filter delete
```-->


<!--## ibmcloud catalog filter get - waiting for Gil to update
{: #filter-get}

use this command to get filter details for either the account or a particular catalog.

```
ibmcloud catalog filter get -- 
```

### Command options
{: #filter-get-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>

### Example
{: #filter-get-example}

Run the following command to validate that you can view Cloudant and Kubernetes Service in your private catalog:

```
ibmcloud catalog filter get --catalog "My first catalog"
```-->


<!--## ibmcloud catalog filter options - waiting for Gil to update
{: #filter-get}

Use this command to get filter ooptions for eeach filter category. 

```
ibmcloud catalog filter options -- 
```

### Command options
{: #filter-options-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>


### Example
{: #filter-options-example}-->


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


<!--## ibmcloud catalog offering add-category - waiting for Gil to update
{: #offering-add-category}

Use this command to add a category tag to an offering.

```
ibmcloud catalog offering add-category -- 
```

### Command options
{: #offering-add-category-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl>

### Example
{: #offering-add-category-example}

Add the **Developer Tools** category to the offering.  
    
```
ibmcloud catalog offering add-category --catalog "My first catalog" --offering "apache-two-instances" --category "Developer Tools"
```-->


## ibmcloud catalog offering list
{: #list-offering-options}

Run the following command to get details about the offerings in your catalogs. This command provides the ability to filter by private catalog, offering, and version.

```
ibmcloud catalog offering list [--catalog CATALOG] [--offering OFFERING_NAME] [--version VERSION] [--output FORMAT]
```

### Command options
{: #list-offering-options}

  <dl>
  <dt>--catalog CATALOG (optional)</dt>
  <dd>The catalog name or ID.</dd>
  <dt>--offering OFFERING_NAME (optional)</dt>
  <dd>The offering name or ID.</dd>
  <dt>--version VERSION (optional)</dt>
  <dd>The version name or ID.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Specifies output format. Default is terminal-friendly and the only supported alternative is JSON. For example: `--output json`</dd>
  </dl> 
  
### Example
{: #get-example}

List all of the offerings that are in the `dev-catalog`.

```
ibmcloud catalog offering list --catalog dev-catalog
```


### Output
{: #get-offering-output}

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


<!-- ## ibmcloud catalog offering delete
{: #delete-offering-options}
Use this command to an offering catalogs, and provides ability to filter by catalog, offering, and version.
```
ibmcloud catalog offering delete --catalog dev-catalog
``` -->

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
  

<!--## ibmcloud catalog offering deprecate - waiting for Gil to update
{: #offering-deprecate}

Use this command to deprecate an offering version.

```
ibmcloud catalog offering deprecate --
```

### Command options
{: #offering-deprecate-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl> 

### Example
{: #offering-deprecate-example}

Deprecate a version of your software offering.
    
```
ibmcloud catalog offering deprecate --version-locator <VERSION_LOCATOR>
```-->

<!--## ibmcloud catalog offering restore - waiting for Gil to update
{: #offering-restore}

Use this command to restore a previously deprecated offering version. 

```
ibmcloud catalog offering restore --
```

### Command options
{: #offering-restore-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl> 

### Example
{: #offering-restore-example}

Restore the offering. This action creates a draft version of the deprecated version.
    
```
ibmcloud catalog offering restore --version-locator <VERSION_LOCATOR>
```-->


<!--## ibmcloud catalog search - waiting for Gil to update
{: #catalog-search}

Use this command to search the public catalog for published offerings. This include managed services, software, and software published from your own account.

```
ibmcloud catalog search --
```

### Command options
{: #catalog-search-options}

  <dl>
  <dt>--</dt>
  <dd></dd>
  </dl> 

### Example
{: #search-example} -->


<!-- These commands below will NOT go public and will always remain internal until we remove them entirely in favor of the provider portal which will be used to onboard content offerings to the public catalog. Is this still true? -->

<!--## ibmcloud catalog offering publish-to-ibm
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
  </dl> -->


