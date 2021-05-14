---

copyright:
  years: 2019, 2020
lastupdated: "2020-12-17"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cli

content-type: faq

---


{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:support: data-reuse='support'}

# FAQs for the {{site.data.keyword.cloud_notm}} CLI
{: #ibm-cli-faq}

FAQs for the {{site.data.keyword.cloud}} Command Line Interface include questions about CLI versioning, updates, and working with apps. To find all FAQs for {{site.data.keyword.cloud_notm}}, see our [FAQ library](https://{DomainName}/docs/faqs).
{: shortdesc}

## Is it required to use the latest version of the {{site.data.keyword.cloud_notm}} CLI?
{: #cli-latest-version}
{: faq}

Yes, you must use the latest version. You can check which version you are using by running the following command:

```
ibmcloud -v
```
{: codeblock}

## How do I update the CLI?
{: #cli-update-version}
{: faq}
{: support}

Run the following command to update to the latest version of the CLI:

```
ibmcloud update
```
{: codeblock}

## How do I manually install the {{site.data.keyword.dev_cli_notm}} commands?
{: #cli-install-devtools-manually}
{: faq}

To manually install the {{site.data.keyword.dev_cli_notm}} commands, see [Installing the tools and plug-ins manually](/docs/cli?topic=cli-install-devtools-manually).

## How can I be notified about new CLI releases?
{: #cli-get-notified}
{: faq}
{: support}

When you run an {{site.data.keyword.cloud_notm}} CLI command, you're notified if a new version is available. You can also subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external} to stay up-to-date on the latest releases.

## Which CLI plugins support private endpoints?
{: #cli-private-endpoint-plugins-faq}
{: faq}
{: support}

To find out which installed CLI plug-ins support private endpoints, use the [**plugin list**](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_list) command.

## Which regions support private endpoints?
{: #cli-private-endpoint-faq}
{: faq}
{: support}

Regions that support private endpoints are `us-east` and `us-south`.

A region must be targeted when a private endpoint is set in the {{site.data.keyword.cloud_notm}} CLI.

For more information about regions, see [Locations for resource deployment](/docs/overview?topic=overview-locations) and [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).

## What is the file structure for {{site.data.keyword.cloud_notm}} applications?
{: #cli-file-structure}
{: faq}
{: support}

Applications that are created or enabled from the CLI come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` contains default entries that are used by the commands of the CLI that can be overridden by values that are passed through the command line.

Apps that are deployed to a DevOps toolchain can also contain files such as `toolchain.yml` and `pipeline.yml`. Apps that are being manually deployed can contain a `manifest.yml` and Helm chart files (for deployment to Cloud Foundry or Kubernetes, for example).

## How are local containers used?
{: #cli-faq-containers}
{: faq}

The {{site.data.keyword.dev_cli_short}} (`ibmcloud dev`) commands use two containers to facilitate building and testing your app. The first is the tools container, which contains the necessary utilities to build and test your app. The `Dockerfile` for this container is defined by the [`dockerfile-tools`](/docs/cli?topic=cli-idt-cli#build-dockerfile-tools) parameter. You might think of it as a development container, as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container, which closely mimics the actual runtime environment of your app once it is deployed to the cloud. This container is in a form that is suitable to be deployed for use, for example, in {{site.data.keyword.cloud_notm}}. As a result, an entry point is defined that starts your app. When you select to run your app through the {{site.data.keyword.dev_cli_short}} (`ibmcloud dev`) commands, it uses this container. The `Dockerfile` for this container is defined by the [`dockerfile-run`](/docs/cli?topic=cli-idt-cli#run) parameter.

## How do I deploy existing code?
{: #faq-deploy-existing-code}
{: faq}

To deploy an existing code base, see [Generating deployment and cloud enablement assets](/docs/apps?topic=apps-create-deploy-app-cli#byoc-cli).

