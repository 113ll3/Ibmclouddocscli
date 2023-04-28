---

copyright:
  years: 2019, 2023
lastupdated: "2023-04-28"

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

## How can I be notified about new CLI releases?
{: #cli-get-notified}
{: faq}
{: support}

When you run an {{site.data.keyword.cloud_notm}} CLI command, you're notified if a new version is available. You can also subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external} to stay up to date on the latest releases.

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
