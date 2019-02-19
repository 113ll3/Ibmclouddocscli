---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-14"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Developing and deploying your apps
{: #developing}

Developing Cloud Native apps by using the {{site.data.keyword.dev_cli_notm}} CLI follows a fairly simple flow:

1. [Create or Enable an app](#idt-create).
2. [Code, Build, and Run](#code-build-run) your app locally by using containers.
3. [Deploy](#cli-deploy) your app to the {{site.data.keyword.cloud_notm}}

## Create or Enable an App
{: #idt-create}

There are several ways that you can create a Cloud app.
- [App Services web console](https://cloud.ibm.com/developer/appservice/dashboard) for generic web apps and microservices
- [Watson Dashboard](https://cloud.ibm.com/developer/watson/dashboard) for creating Watson based capability enabled starter apps.
    - Other industry and technology-based dashboards are available from the "Hamburger" menu on the {{site.data.keyword.cloud_notm}} home page. All take a similar approach of using Starter Kits to create new apps.
- {{site.data.keyword.dev_cli_notm}} CLIs [`ibmcloud dev create`](/docs/cli/idt/commands.html#create) command to create a new app.
- {{site.data.keyword.dev_cli_notm}} CLIs [`ibmcloud dev enable`](/docs/cli/idt/commands.html#enable) command to quickly enable the cloud on an existing server-side app.

For any of the previous creation methods, the flow is similar. You can choose the project type, implementation language, and app pattern to use. You can also opt to add services to your app, such as authentication or persistence. Finally, you can choose to enable DevOps capability to the app that provides a complete toolchain of source control and team communications, and a pipeline that is triggered on each commit to validate, build, and deploy your app to the {{site.data.keyword.cloud_notm}}.

![Sample create flow using {{site.data.keyword.dev_cli_notm}} CLI](create_flow.png "Sample create flow using {{site.data.keyword.dev_cli_notm}} CLI") <br> Figure 2. Sample create flow using {{site.data.keyword.dev_cli_notm}} CLI

The {{site.data.keyword.dev_cli_notm}} CLI works closely together to provide a seamless experience during development. Projects that are created within any of the web consoles provide a **Download code** button to download the generated source code to your workstation for more development.

### Helpful CLI commands
{: #helpful}

The following CLI commands help in working with your project and the web consoles:
- [`code`](/docs/cli/idt/commands.html#code) to directly pull an apps generated source code to your workstation
- [`console`](/docs/cli/idt/commands.html#console) to open your browser to the current app's project page in the {{site.data.keyword.cloud_notm}}
- [`create`](/docs/cli/idt/commands.html#create) command to create a new app.
- [`delete`](/docs/cli/idt/commands.html#delete) to delete the current app from the {{site.data.keyword.cloud_notm}} project area.
- [`enable`](/docs/cli/idt/commands.html#enable) command to cloud-enable an existing server-side app.
- [`get-credentials`](/docs/cli/idt/commands.html#get-credentials) to get credentials that are required by the project to enable the use of bound services.
- [`list`](/docs/cli/idt//commands.html#list) to list all the apps that you've created in the currently selected org/space, from either the CLI or the consoles.

### Exploring the app's project structure
{: #exploring-project}

Projects that are created or enabled for use with the tool come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` has default entries that are used by the commands of the tool that can be overridden by values that are passed through the command line.

### Reference Blogs and Videos
{: #ref1}

- Video: [Installing {{site.data.keyword.cloud_notm}} developer tools on Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- Blog: [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

## Code, Build, and Run
{: #code-build-run}

Once your project is created, it's up to you to craft it into something useful. The general flow consists of editing the source code, then running [`ibmcloud dev build`](/docs/cli/idt/commands.html#build) to compile the app within a local container specific to your app's language and configuration. Depending on your apps language and generator that is used, there are one or more containers defaulted to support building and running locally. Typically, there's a "tools" container for builds and local debugging. This container has extra tools and capabilities to aid you in development. There's also a "run" container that closely mimics the actual runtime environment of your app when it's deployed to the cloud, either in Cloud Foundry or IBM's Kubernetes based container environment.

You're free to use whatever IDE or editor you prefer to code up your application. We offer an extension for the Microsoft Visual Studio Code (VSCode) editor that enables you to access all the IDE commands from directly within the editor.

When the project is built, run your app using [`ibmcloud dev run`](/docs/cli/idt/commands.html#run) or [`ibmcloud dev debug`](/docs/cli/iddt/commands.html#debug). This runs the app within the proper container. Some apps' patterns support multiple containers external to your apps. These automatically start and configure during run or debug. There's also a [`ibmcloud dev test`](/docs/cli/idt/commands.html#test) command that runs any test cases that are associated with the app.

### How local containers are used
{: #local-containers}

The {{site.data.keyword.dev_cli_long}} CLI uses two containers for building and testing your application. The first is the tools container, which contains the necessary utilities to build and test your application. The Dockerfile for this container is defined by the [`dockerfile-tools`](/docs/cli/idt/commands.html#command-parameters) parameter. You might think of it as a development container as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container. This container is of a form suitable to be deployed for use, for example, in {{site.data.keyword.cloud}}. As a result, an entry point is defined that starts your application. When you select to run your application through the {{site.data.keyword.dev_cli_short}} CLI, it uses this container. The Dockerfile for this container is defined by the [`dockerfile-run`](/docs/cli/idt/commands.html#run-parameters) parameter.

### Helpful CLI commands
{: #helpful2}

The following CLI commands help you work with your project during the code, build, and run cycles:
- [`build`](/docs/cli/idt/commands.html#build) Build the project in a local container.
- [`debug`](/docs/cli/idt/commands.html#debug) Debug your application in a local container.
- [`run`](/docs/cli/idt/commands.html#run) Run your application in a local container.
- [`shell`](/docs/cli/idt/commands.html#shell) Open a shell into a local container.
- [`status`](/docs/cli/idt/commands.html#status) Check the status of the containers used by the {{site.data.keyword.dev_cli_notm}} CLI.
- [`stop`](/docs/cli/idt/commands.html#stop) Stop a container
- [`test`](/docs/cli/idt/commands.html#test) Test your application in a local container.

### Reference Blogs and Videos
{: #ref2}

- [Debugging local apps](/docs/cli/idt/local_debug.html#local-debug)

## Deploy
{: #cli-deploy}

Under a proper cloud native environment, you use a fully functional DevOps pipeline to manage all deployments and a wealth of other capabilities. During the create flow, you can set up your app to use IBM Cloud's DevOps. If you aren't ready to use the built-in DevOps, then you either manually [`ibmcloud dev deploy`](/docs/cli/idt/commands.html#deploy) your app, or use the deploy command within your own DevOps pipeline.  

### Helpful CLI commands
{: #helpful3}

The following CLI commands help in working with your project during the deploy process:
- [`console`](/docs/cli/idt/commands.html#console) Opens the {{site.data.keyword.cloud_notm}} console for a project.
- [`deploy`](/docs/cli/idt/commands.html#deploy) Deploy an application to {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt/commands.html#view) View the URL of your project.

### Reference Blogs and Videos
{: #ref3}

- Blog: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- Blog: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
