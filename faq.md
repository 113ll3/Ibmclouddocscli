---

copyright:
  years: 2019, 2023
lastupdated: "2023-05-19"


keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help, cli private endpoints

subcollection: cli

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQs for the {{site.data.keyword.cloud_notm}} CLI
{: #ibm-cli-faq}

FAQs for the {{site.data.keyword.cloud}} Command Line Interface include questions about CLI versioning, updates, and working with apps. To find all FAQs for {{site.data.keyword.cloud_notm}}, see the [FAQ library](/docs/faqs).
{: shortdesc}

## Do I have to use the latest version of the {{site.data.keyword.cloud_notm}} CLI?
{: #cli-latest-version}
{: faq}

Yes, you must use the latest version. You can check which version you are using by running the following command:

```bash
ibmcloud -v
```
{: codeblock}

## How do I update the CLI?
{: #cli-update-version}
{: faq}
{: support}

Run the following command to update to the latest version of the CLI:

```bash
ibmcloud update
```
{: codeblock}

## How do I install the {{site.data.keyword.cloud_notm}} CLI along with developer plug-ins and tools?
{: #cli-install-devtools-manually}
{: faq}

To install the latest IBM Cloud CLI and recommended plug-ins and tools for developing applications for IBM Cloud, follow the steps in [Getting started with the IBM Cloud CLI](/docs/cli?topic=cli-getting-started) and [Installing the tools and plug-ins manually](/docs/cli?topic=cli-install-devtools-manually).

To install only the stand-alone IBM Cloud CLI without any plug-ins or tools, see [Installing the stand-alone IBM Cloud CLI](/docs/cli?topic=cli-install-ibmcloud-cli).

## How do I install a plug-in from a URL?
{: #cli-install-plugin-url}
{: faq}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a URL. For more information, see [Installing a plug-in from a web URL](/docs/cli?topic=cli-plug-ins#install-plugin-from-url).

## How do I install a plug-in locally?
{: #cli-install-plugin-local}
{: faq}

Use the `ibmcloud plugin install LOCAL_FILE_NAME` command to install a plug-in on your computer. For more information, see [Installing a plug-in locally](/docs/cli?topic=cli-plug-ins#install-plugin-locally).

## How do I download a plug-in?
{: #cli-install-plugin-local}
{: faq}

Use the `ibmcloud plugin download PLUGIN_NAME` command to download a plug-in. For more information, see [`ibmcloud plugin download`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_download).

## How can I be notified about new CLI releases?
{: #cli-get-notified}
{: faq}
{: support}

When you run an {{site.data.keyword.cloud_notm}} CLI command, you're notified if a new version is available. You can also subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external} to stay up to date on the latest releases.

## How do I install the {{site.data.keyword.cloud_notm}} CLI along with developer plug-ins and tools?
{: #cli-install-devtools-manually}
{: faq}

To install the latest {{site.data.keyword.cloud_notm}} CLI and recommended plug-ins and tools for developing applications for {{site.data.keyword.cloud_notm}}, follow the steps in [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started) and [Extending IBM Cloud CLI with plug-ins](/docs/cli?topic=cli-plug-ins).

To install only the stand-alone {{site.data.keyword.cloud_notm}} CLI without any plug-ins or tools, see [Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-install-ibmcloud-cli).

## How do I download a plug-in?
{: #cli-install-download-local}
{: faq}

Use the `ibmcloud plugin download PLUGIN_NAME` command to download a plug-in. For more information, see [`ibmcloud plugin download`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_download).

Example: `ibmcloud plugin download container-service -v 0.1.425`

## How do I install a plug-in locally?
{: #cli-install-plugin-local}
{: faq}

Use the `ibmcloud plugin install LOCAL_FILE_NAME` command to install a plug-in binary on your local computer. For example:
```bash
ibmcloud plugin install ./code-engine-darwin-amd64-1.23.2
```
{: codeblock}

```text
Installing plugin './code-engine-darwin-amd64-1.23.2'...
OK
Plug-in 'code-engine 1.23.2' was successfully installed into /Users/username/.bluemix/plugins/code-engine. Use 'ibmcloud plugin show code-engine' to show its details.
$
```
{: screen}

## How do I install a plug-in from a URL?
{: #cli-install-plugin-url}
{: faq}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a URL. For example:
```bash
ibmcloud plugin install http://example.com/downloads/my-plugin
```
{: codeblock}


## Which CLI plug-ins support private endpoints?
{: #cli-private-endpoint-plugins-faq}
{: faq}
{: support}

To find out which installed CLI plug-ins support private endpoints, use the [`ibmcloud plugin list`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_list) command.

## Which regions support private endpoints?
{: #cli-private-endpoint-faq}
{: faq}
{: support}

Regions that support private endpoints are `us-east` and `us-south`.

A region must be targeted when a private endpoint is set in the {{site.data.keyword.cloud_notm}} CLI.

For more information about regions, see [Locations for resource deployment](/docs/overview?topic=overview-locations) and [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).
