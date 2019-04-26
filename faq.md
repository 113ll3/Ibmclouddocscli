---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# FAQs
{: #ibm-cli-faq}

## Am I required to use the latest version of the {{site.data.keyword.cloud_notm}} CLI?
{: #cli-latest-version}

Yes, you must use the latest version. You can check which version you are using by running the following command:

```
ibmcloud -v
```
{: codeblock}

## How do I update my CLI?
{: #cli-update-version}

Run the following command to update to the latest version of the CLI:

```
ibmcloud update
```
{: codeblock}

## Can I get notified about new releases of the CLI?
{: #cli-get-notified}

Yes, you stay up to date on new releases of the CLI as they become available. Subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")

## What is the file structure for {{site.data.keyword.cloud_notm}} applications?
{: #cli-file-structure}

Applications that are created or enabled from the CLI come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` contains default entries that are used by the commands of the CLI that can be overridden by values that are passed through the command line.

Applications that have deployed to a DevOps Toolchain may also contain files such as `toolchain.yml` and `pipeline.yml`. Applications that are being manually deployed can contain a `manifest.yml` and Helm chart files (for deployment to Cloud Foundry or Kubernetes, for example).

## How are local containers used?
{: #cli-faq-containers}

The {{site.data.keyword.dev_cli_long}} CLI plug-in uses two containers to facilitate building and testing your application. The first is the tools container, which contains the necessary utilities to build and test your application. The `Dockerfile` for this container is defined by the [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) parameter. You might think of it as a development container, as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container, which closely mimics the actual runtime environment of your app once that it is deployed to the cloud. This container is in a form that is suitable to be deployed for use, for example, in {{site.data.keyword.cloud_notm}}. As a result, an entry point is defined that starts your application. When you select to run your application through the {{site.data.keyword.dev_cli_long}} CLI Plug-in CLI, it uses this container. The `Dockerfile` for this container is defined by the [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) parameter.

## How do I deploy existing code?

To deploy an existing code base, see [Generating deployment and cloud enablement assets](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

