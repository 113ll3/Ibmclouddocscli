---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-15"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Developing and deploying your apps
{: #developing}

Developing cloud-native applications with the {{site.data.keyword.dev_cli_notm}} CLI follows a fairly simple flow:

1. [Create or enable an app for deployment](#idt-create).
2. [Code, build, and run](#code-build-run) your app locally by using containers.
3. [Deploy](#cli-deploy) your app to {{site.data.keyword.cloud_notm}}.

## Create or enable an app for cloud deployment
{: #idt-create}

There are several ways that you can create an app.
- [App Services web console](https://cloud.ibm.com/developer/appservice/dashboard) for generic web apps and microservices
- [Watson Dashboard](https://cloud.ibm.com/developer/watson/dashboard) for creating Watson based capability enabled starter apps.
    - Other industry and technology-based dashboards are available from the "Hamburger" menu on the {{site.data.keyword.cloud_notm}} home page. All take a similar approach of using starter kits to create new apps.
- {{site.data.keyword.dev_cli_notm}} [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) command to create a new app.
- {{site.data.keyword.dev_cli_notm}} [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) command to quickly enable the cloud on an existing server-side app.

For any of the previous creation methods, the flow is similar. Select the project type, implementation language, and app pattern to use. You can also opt to add services to your app, such as authentication or persistence. Finally, you can configure continuous delivery for the app, which provides a complete toolchain of source control and team communications. Including a pipeline that is triggered on each commit to validate, build, and deploy your app to the {{site.data.keyword.cloud_notm}}.

![A create app flow that uses {{site.data.keyword.dev_cli_notm}} CLI](../images/create_flow.png "A create app flow that uses {{site.data.keyword.dev_cli_notm}} CLI"){: caption="Figure 1. A create app flow that uses {{site.data.keyword.dev_cli_notm}} CLI" caption-side="bottom"}

The {{site.data.keyword.dev_cli_notm}} CLI works closely together to provide a smooth experience during development. Projects that are created from the web consoles provide a **Download code** button to download the generated source code to your workstation for further development.

### Helpful CLI commands
{: #helpful}

The following `ibmcloud dev` CLI commands help in working with your project and the web consoles:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) Use to download an apps source code to your workstation.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Opens your browser to the current app's project page in {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) The command to create a new app.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) Used to delete the current app from the {{site.data.keyword.cloud_notm}} project area.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) The command to cloud-enable an existing server-side app.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) To get credentials that are required by the project to enable the use of bound services.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) To list all the apps that are created in the currently selected org and space, from either the CLI or the consoles.

### Exploring the app's project structure
{: #exploring-project}

Projects that are created or enabled for use with the developer tools come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` has default entries that are used by the `ibmcloud dev` commands that you can override with values that are passed through the command line.

### Reference Blogs and Videos
{: #ref1}

- Video: [Installing {{site.data.keyword.cloud_notm}} developer tools on Ubuntu Linux&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")
- Blog: [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/cloud-archive/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli//){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

## Code, build, and run
{: #code-build-run}

After you create your project, it's up to you to craft it into something useful. The general flow consists of editing the source code, then running [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) to compile the app within a local container specific to your app's language and configuration. Depending on your apps language and generator that is used, there are one or more containers that default to support building and running locally. Typically, there's a "tools" container for builds and local debugging. This container has extra tools and capabilities to aid you in development. There's also a "run" container that mimics the runtime environment of your app after deployment, either in Cloud Foundry or IBM's Kubernetes based container environment.

You're free to use whatever IDE or editor you prefer to code your app. {{site.data.keyword.IBM_notm}} offers an extension for the Microsoft&trade; Visual Studio Code (VSCode) editor that enables you to access all the IDE commands from directly within the editor.

When the project is built, run your app by using [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) or [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). The app is run within the proper container. Some apps' patterns support multiple containers external to your apps. The apps automatically start and configure during run or debug. There's also a [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) command that runs any test cases that are associated with the app.

### How local containers are used
{: #local-containers}

The {{site.data.keyword.dev_cli_long}} CLI uses two containers for building and testing your app. The first is the tools container, which contains the necessary utilities to build and test your app. The Dockerfile for this container is defined by the [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) parameter. You might think of it as a development container as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container. This container is of a form suitable to be deployed for use, for example, in {{site.data.keyword.cloud}}. As a result, an entry point is defined that starts your app. When you select to run your app through the {{site.data.keyword.dev_cli_short}} CLI, it uses this container. The Dockerfile for this container is defined by the [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) parameter.

### Helpful CLI commands
{: #helpful2}

The following CLI commands help you debug your project:
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) Build the project in a local container.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) Debug your application in a local container.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) Run your application in a local container.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) Open a shell into a local container.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) Check the status of the containers used by the {{site.data.keyword.dev_cli_notm}} CLI.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) Stop a container
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) Test your application in a local container.

### Debugging local apps
{: #ref2}

- [Debugging local apps](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Deploy
{: #cli-deploy}

Under a proper cloud-native environment, you use a fully functional DevOps pipeline to manage all deployments and a wealth of other capabilities. During the create flow, you can set up your app to use IBM Cloud's DevOps. If you aren't ready to use the built-in DevOps, then you can either manually run [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) to deploy your app, or use the `deploy` command within your own DevOps pipeline.

### Helpful CLI commands
{: #helpful3}

The following CLI commands help in working with your project during the deployment process:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Opens the {{site.data.keyword.cloud_notm}} console for a project.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) To deploy an application to {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) View the URL of your project.

### Reference Blogs and Videos
{: #idt-reference}

- Blog: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/cloud/blog/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")
- Blog: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/cloud-archive/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")
