---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-26"

keywords: sdk generator, open api, ibmcloud sdk, ibmcloud sdk generate, generate, sdk validate, sdk list, cloud foundry, rest api 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK Generator
{: #sdk-cli}

The {{site.data.keyword.IBM}} SDK Generator plug-in can be installed in the {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

As a developer on {{site.data.keyword.cloud_notm}}, you can use this plug-in to generate SDKs from your [Open API Specification](https://www.openapis.org/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") compliant REST API definition. As you make changes to your REST API definition, you can use this plug-in to regenerate only the SDK instead of regenerating the entire project.

You can also see if your Cloud Foundry apps in a given space have REST API definitions that are valid for SDK generation. Finally, you can use the {{site.data.keyword.IBM_notm}} SDK Generator plug-in to validate any REST API definitions to ensure that they comply with the SDK generator requirements.

This {{site.data.keyword.IBM_notm}} SDK Generator plug-in allows you to easily integrate your backend services to your app with a generated SDK. When a change to a REST API occurs, you can re-generate the SDK and replace the old one for a seamless SDK upgrade. You can also integrate the CLI into a devops pipeline and ensure that the SDK is always consistent with the API spec each time the app is built.

The REST API definition must be valid and either hosted on a live server endpoint or a local file on your system. If the REST API definition is hosted, the relative URL must be defined in the `OPENAPI_SPEC` environment variable.

## Requirements
{: #prereqs}

Ensure that you satisfy the following requirements.

* You have an [{{site.data.keyword.cloud_notm}}](https://{DomainName}){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") account.
* A valid API definition that conforms to the [Open API](https://www.openapis.org/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") specification.

## Installation
{: #sdk-installation}

Install the [{{site.data.keyword.cloud_notm}} developer tools](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

## Commands
{: #commands}

Use the following commands to generate an SDK, validate Open API definition files, or list Cloud Foundry apps.

### Generating an SDK
{: #gen}

Use `ibmcloud sdk generate [arguments...] [command options]`.

#### Arguments
{: #gen-args}

* `APP_NAME` - the name of the Cloud Foundry app in your current space
* `OPENAPI_DOC_LOCATION` - a URL or a relative file path to the raw REST API definition JSON or Yaml
* `GENERATED_SDK_NAME` (optional) - the name of the generated SDK


#### Options
{: #gen-options}

* `PLATFORM` (required)
   * `--android` - generate an Android SDK
   * `--ios` - generate an iOS Swift SDK
   * `--swift` - generate a Swift server SDK
   * `--js` - generate a JavaScript SDK
* `LOCATION` (required) - specifies the type for `OPENAPI_DOC_LOCATION`
   * `-r` - remote URL
   * `-f` - file
   * `-a` - app that runs on {{site.data.keyword.cloud_notm}}
   * `-l` - localhost URL
* `--output "YOUR_RELATIVE_PATH"` (optional) - places the generated SDK in the directory that is specified by `YOUR_RELATIVE_PATH` (overwrites if existing SDK is present)
* `--unzip` (optional) - extracts the generated SDK (overwrites if existing SDK artifacts are present)


#### Usage
{: #gen-usage}

To generate an SDK from a Cloud Foundry app that is running in {{site.data.keyword.cloud_notm}}, you can use the app's name as a parameter to the CLI. The following command uses the app's name as the `SDK_Name`.

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

To generate an SDK from a URL to an Open API definition file or a local JSON or Yaml file, use the following command.

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Validating Open API definitions
{: #validating}

Use `ibmcloud sdk validate [argument]`.


#### Arguments
{: #val-args}

* `APP_NAME` - the name of the Cloud Foundry app in your current space
* `OPENAPI_DOC_LOCATION` - a URL or a relative file path to the raw REST API definition JSON or Yaml


#### Usage
{: #val-usage}

To validate a Cloud Foundry app's API spec that is running in {{site.data.keyword.cloud_notm}}, you can use the app's name as a parameter to the CLI.

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

To validate an SDK from the URL to an API spec document or a local JSON or Yaml file, use the following command.

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### List Apps (Cloud Foundry)
{: #list-apps}

Use `ibmcloud sdk list [argument] [option]` to list apps and validate API specs. You must have the `OPENAPI_SPEC` environment variable set to relative url path hosting your spec.


#### Arguments
{: #list-args}

* `SPACE_NAME` (optional) - the name of the Cloud Foundry space within your current organization that you want to search for apps. If not provided, the current space is searched.


#### Options
{: #list-options}

* `--url` (optional) - to display a fully formed URL to the Open API definition for each app in the list


#### Usage
{: #list-usage}

To list apps in the current space, use the following command.

```
ibmcloud sdk list
```
{: codeblock}

To list apps in the current space and display the API spec URL, use the following command.

```
ibmcloud sdk list --url
```
{: codeblock}

To list apps in a specific space, use the following command.

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

To list apps in a specific space and display the API spec URL, use the following command.

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
