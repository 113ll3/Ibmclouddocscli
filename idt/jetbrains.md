---

copyright:

  years: 2018

lastupdated: "2018-07-12"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Jetbrains IDEs
{: #ibm-dev-tools-for-jetbrains}

The IBM Cloud Developer Tools extension for Jetbrains IDEs, which include `IntelliJ`, `WebStorm`, `Android Studio`, and more, provides new menu entries to directly access IDT CLI commands from within the IDE. It enables you to quickly access a subset of `ibmcloud dev` commands for both Docker and CloudFoundry workflows, including app deployment, starting/stopping/restarting apps on {{site.data.keyword.Bluemix_notm}}, viewing remote app logs, and more – all without the need to leave the editor’s context.
{:shortdesc}

![Screen capture of the IBM Cloud Developer Tools running within WebStorm IDE.](jetbrains.png "IDT menu example running within WebStorm IDE")

## Dependencies
{: #dependencies}

To utilize the IBM Cloud Developer Tools extension for Jetbrains-based IDEs, you will also need the [IBM Cloud Developer Tools CLI](index.html) installed on your system.

## Installation
{: #installation}

The simplest way to install the IBM Cloud Developer Tools extension for Jetbrains IDE, is to go to the [IDT Github repo's jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) page, and follow the instructions.

## Usage
{: #usage}

You can either start with an existing server-side app, and Enable it for the {{site.data.keyword.Bluemix_notm}}, or use the IDT CLI to Create a new app from a StarterKit (ibmcloud dev create). Once you have your app's project, open it in your JetBrains IDE.

If you have a generic server-side app, select Tools > IBM Cloud Developer Tools > Enable app for IBM Cloud. This will check for all the required files and add any that are missing which will then enable you to build the app locally, as well as deploy it to {{site.data.keyword.Bluemix_notm}} using a Cloud Foundry app, or within a Kubernetes cluster.

Develop your cloud native app by using the basic build/run/deploy actions from the IDT menu. If you need to perform actions that are not in the menu, simply open the Terminal tab and enter the desired commands manually.
