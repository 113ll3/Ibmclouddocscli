---
copyright:

  years: 2018

lastupdated: "2018-06-27"

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

1. [Create or Enable an app](#create)
2. [Code, Build, and Run](#build) your app locally by using containers
3. [Deploy](#deploy) your app to the {{site.data.keyword.Bluemix_notm}}

## Create or Enable an App
{: #create}

There are several ways that you can create a Cloud app.
- [App Services web console](https://console.bluemix.net/developer/appservice) for generic web apps and microservices
- [Watson Dashboard](https://console.bluemix.net/dashboard/watson) for creating Watson based capability enabled starter apps.
    - Other industry and technology-based dashboards are available from the "Hamburger" menu on the {{site.data.keyword.Bluemix_notm}} home page. All take a similar approach of using Starter Kits to create new apps.
- {{site.data.keyword.dev_cli_notm}} CLIs [`ibmcloud dev create`](./commands.html#create) command to create a new app.
- {{site.data.keyword.dev_cli_notm}} CLIs [`ibmcloud dev enable`](./commands.html#enable) command to quickly enable the cloud on an existing server-side app.

For any of the previous creation methods, the flow is similar. You can choose the project type, implementation language, and app pattern to use. You can also opt to add services with an added value to your app, such as authentication or persistence. Finally, you can choose to enable DevOps capability to the app that provides a complete toolchain of source control and team communications, and a pipeline that is triggered on each commit to validate, build, and deploy your app to the IBM Cloud.

![Sample create flow using IDT CLI](create_flow.png "Sample create flow using IDT CLI") <br> Figure 2. Sample create flow using IDT CLI

The {{site.data.keyword.dev_cli_notm}} CLI works closely together to provide a seamless experience during development. Projects that are created within any of the web consoles provide a "Download code" button to download the generated source code to your workstation for more development.

### Helpful CLI commands
{: #helpful}

The following CLI commands help in working with your project and the web consoles:
- [`code`](./commands.html#code) to directly pull an apps generated source code to your workstation
- [`console`](./commands.html#console) to open your browser to the current app's project page in the {{site.data.keyword.Bluemix_notm}}
- [`create`](./commands.html#create) command to create a new app.
- [`delete`](./commands.html#delete) to delete the current app from the {{site.data.keyword.Bluemix_notm}} project area.
- [`enable`](./commands.html#enable) command to cloud-enable an existing server-side app.
- [`get-credentials`](./commands.html#get-credentials) to get credentials that are required by the project to enable the use of bound services.
- [`list`](./commands.html#list) to list all the apps that you have created in the currently selected org/space, from either the CLI or the consoles.


### Exploring the app's project structure
{: #exploring-project}

Projects that are created or enabled for use with the tool come with pre-configured settings encapsulated in the `cli-config.yml` file. The `cli-config.yml` contains default entries that are used by the commands of the tool that can be overridden by values that are passed through the command line.

More details on project structures can be found here:
- [Java projects](/docs/apps/projects/java_project_contents.html)
- [NodeJS projects](/docs/apps/projects/node_project_contents.html)
- [Python projects](/docs/apps/projects/python_project_contents.html)
- [Swift projects](/docs/apps/projects/swift_project_contents.html)


### Reference Blogs and Videos
{: #ref1}

- Video: [Installing IDT on Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- Blog: [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## Code, Build, and Run
{: #build}


Once your project has been created, it's now up to you to craft it into something useful. The general flow consists of editing the source code, then running a [`ibmcloud dev build`](commands.html#build) to compile the app within a local container specific to your app's language and configuration. Depending on your apps language and generator that is used, there are one or more containers defaulted to support building and running locally.  Typically, there will be a "tools" container for builds and local debugging. This container will usually have extra tools and capabilities to aid you in development. There is also a "run" container that closely mimics the actual runtime environment of your app once deployed to the cloud, either in Cloud Foundry or IBM's Kubernetes based container environment.


You are free to use whatever IDE or editor you prefer to code up your application. We offer an extension for the Microsoft VisualStudio Code (VSCode) editor that enables you to access all the IDE commands from directly within the editor.

Once the project has been built, you'll next want to run your app using the [`ibmcloud dev run`](commands.html#run) or [`ibmcloud dev debug`](commands.html#debug), depending on your apps generator configuration. This will run the app within the proper container. Some apps patterns support multiple containers external to your apps such as persistence or other capabilities. These will automatically be started and configured during run or debug. There is also a [`ibmcloud dev test`](commands.html#test) command that will execute any test cases associated with the app.


### How local containers are used
{: #local-containers}

The {{site.data.keyword.dev_cli_long}} CLI uses two containers to facilitate building and testing your application. The first is the tools container, which contains the necessary utilities to build and test your application. The Dockerfile for this container is defined by the [`dockerfile-tools`](commands.html#command-parameters) parameter. You might think of it as a development container as it contains the tools normally used for development of a particular runtime.

The second container is the run container. This container is of a form suitable to be deployed for use, for example, in {{site.data.keyword.Bluemix}}. As a result, an entry point is defined that starts your application. When you select to run your application through the {{site.data.keyword.dev_cli_short}} CLI, it uses this container. The Dockerfile for this container is defined by the [`dockerfile-run`](commands.html#run-parameters) parameter.


### Helpful CLI commands
{: #helpful2}

The following CLI commands assist in working with your project during the code, build, and run cycles:
- [`build`](./commands.html#build) Build the project in a local container
- [`debug`](./commands.html#debug) Debug your application in a local container
- [`run`](./commands.html#run) Run your application in a local container
- [`shell`](./commands.html#shell) Open a shell into a local container
- [`status`](./commands.html#status) Check the status of the containers used by the CLI
- [`stop`](./commands.html#stop) Stop a container
- [`test`](./commands.html#test) Test your application in a local container

### Reference Blogs and Videos
{: #ref2}

- [Debugging local apps](local_debug.html)





## Deploy
{: #deploy}

Under a proper cloud native environment, you will want to utilize a fully functional DevOps pipeline to manage all deployments, as well as a wealth of other capabilities. During the create flow, you can set up your app to use IBM Cloud's DevOps. If you are not ready to use the built-in DevOps, then you can either manually [`ibmcloud dev deploy`](./commands.html#deploy) your app, or use the deploy command within your own DevOps pipeline.  



### Helpful CLI commands
{: #helpful3}

The following CLI commands help in working with your project during the deploy process:
- [`console`](./commands.html#console) Opens the IBM Cloud console for a project
- [`deploy`](./commands.html#deploy) Deploy an application to IBM Cloud
- [`view`](./commands.html#view) View the URL of your project


### Reference Blogs and Videos
{: #ref3}

- Blog: [Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- Blog: [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
