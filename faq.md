---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Frequently Asked Questions (FAQ)
{: #ibm-cli-faq}

## What is the file structure for {{site.data.keyword.cloud_notm}} applications?
{: #cli-file-structure}

Applications that are created or enabled from the CLI come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` contains default entries that are used by the commands of the CLI that can be overridden by values that are passed through the command line.

Applications that have deployed to a DevOps Toolchain may also contain files such as `toolchain.yml` and `pipeline.yml`. Applications that are being manually deployed can contain a `manifest.yml` and Helm chart files (for deployment to Cloud Foundry or Kubernetes, for example).

## How are local containers used?
{: #cli-faq-containers}

The {{site.data.keyword.dev_cli_long}} CLI plug-in uses two containers to facilitate building and testing your application. The first is the tools container, which contains the necessary utilities to build and test your application. The `Dockerfile` for this container is defined by the [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) parameter. You might think of it as a development container, as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container, which closely mimics the actual runtime environment of your app once that it is deployed to the cloud. This container is in a form that is suitable to be deployed for use, for example, in {{site.data.keyword.cloud_notm}}. As a result, an entry point is defined that starts your application. When you select to run your application through the {{site.data.keyword.dev_cli_long}} CLI Plug-in CLI, it uses this container. The `Dockerfile` for this container is defined by the [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) parameter.

# How do I deploy existing code?
To deploy an existing codebase, follow these steps to enable your app[enable your app](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Reference blogs, videos, and documentation
{: #cli-faq-reference}

### Blogs
{: #cli-blogs}

- [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Videos
{: #cli-videos}

- [How to deploy to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [How to deploy existing projects to {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Create, debug, and deploy a Node.js app with the {{site.data.keyword.dev_cli_long}} CLI Plug-in and VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Documentation and tutorials
- [Continuous Deployment to Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Troubleshooting for {{site.data.keyword.dev_cli_long}} CLI Plug-in](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} CLI Plug-in (ibmcloud dev) commands](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Local application debugging for the {{site.data.keyword.dev_cli_long}} CLI Plug-in](/docs/cli/idt?topic=cloud-cli-local-debug)

**To report issues or provide feedback you can use the [{{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Request team access [here](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**