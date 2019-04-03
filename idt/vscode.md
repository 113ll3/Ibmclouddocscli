---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-03"

keywords: cli, ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

The IBM Cloud Developer Tools extension for Visual Studio Code provides access to capabilities from the IBM developer CLI directly within the Visual Studio Code editor’s command palette. You can quickly access a subset of `ibmcloud dev` commands for both Docker and Cloud Foundry workflows, including app deployment, starting/stopping/restarting apps on {{site.data.keyword.cloud}}, viewing remote app logs, and more – all without the need to leave the editor’s context.
{:shortdesc}

![Screen capture of the IBM Developer Tools extension download screen.](vscode.png "Extension download screen within Visual Studio Code")

## Dependencies
{: #vscode-dependencies}

To use the IBM Cloud Developer Tools extension for Visual Studio Code, you need the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) and the {{site.data.keyword.cloud_notm}} CLI plug-in that is installed on your system.

## Installation
{: #vscode-installation}

The simplest way to install the {{site.data.keyword.dev_cli_notm}} extension is to use Visual Studio Code’s 'quick open' command:

1. Open the 'quick open' command palette by using the following key combinations from within the editor:

  * **Mac:** `cmd + p`
  * **Windows / Linux:** `ctrl + p`

2. Enter the `ext install ibm-developer` command and press enter to install the {{site.data.keyword.dev_cli_notm}} extension inside the Visual Studio Code editor.

Or you can install the {{site.data.keyword.dev_cli_notm}} extension through the "Extensions" management window:

1. Open the **Extensions** sidebar in the Visual Studio Code editor, and then search by using the string `publisher:IBM Developer`. The {{site.data.keyword.dev_cli_notm}} extension is displayed in the search results.  
2. Click **Install** to begin the installation.

You can also access the [IBM Cloud Developer Tools extension directly within the Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon").

## Usage
{: #vscode-usage}

You start the extension commands by using Visual Studio Code’s command palette.

First, open the command palette by using the following key combination:

* **Mac:** `cmd + shift + p`
* **Windows / Linux:** `ctrl + shift + p`

Next, you enter or select the command that you want to start. You can type ‘ibmcloud’ within the command palette to see the list of all available commands.

### Using the IBM Developer Extension for Docker workflows (Docker containers)
{: #usage-docker}

You can get started with `ibmcloud dev` workflows in just a few steps:
* Create a project by using one of the two following methods:
  * Use the [{{site.data.keyword.cloud_notm}} web console](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") and download the generated code
  * Use the {{site.data.keyword.cloud_notm}} Developer Tools CLI Plug-in and generate a project by using the [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create) command.
* Open the project’s folder locally in the Visual Studio Code editor
* Use the `ibmcloud dev build` command to build the app into a Docker image
* Use the `ibmcloud dev debug` command to run the app in local Docker for development
> Note: To debug a Node.js application that is running inside the local Docker container, you need to [add a debug configuration for the local container](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon").
* Use the `ibmcloud dev run` command to run the app in local Docker in release mode
* Use the `ibmcloud dev deploy` command to deploy the application to a Cloud Foundry runtime on {{site.data.keyword.cloud_notm}}

### Using the IBM Developer Extension for Cloud Foundry workflows
{: #usage-cloud-foundry}

For users that are currently deploying apps to Cloud Foundry runtimes on {{site.data.keyword.cloud_notm}}, there's also support for the `cf` set of operations.

You can get started with Cloud Foundry workflows in just a few steps:
* Create a new Cloud Foundry application
  * Use the [{{site.data.keyword.cloud_notm}} web console](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") and download the starter code
  * Create a new Cloud Foundry application manually
* Open the project folder locally in the Visual Studio Code editor
* Use `ibmcloud cf apps` to list all of your applications
* Use `ibmcloud cf push` to push a build of your application to the Cloud Foundry runtime
* Use ibmcloud `cf <start/stop/restage/restart>` to change the status of your application
* Use `ibmcloud cf logs` to view the live log stream for your application
  * Use `ibmcloud cf logs` to stop the log stream
