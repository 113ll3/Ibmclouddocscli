---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-28"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Troubleshooting for the {{site.data.keyword.Bluemix_notm}} Developer Tools CLI plug-in
{: #troubleshoot}

General problems with using the {{site.data.keyword.dev_cli_short}} command-line interface (CLI) to create apps might include deployment failures or code that can't be retrieved. In many cases, you can recover from these problems by following a few easy steps.
{:shortdesc}

## Why do I get a host name error when I create an app with a non-mobile pattern?
{: #hostname-error}
{: troubleshoot}

The following error might be displayed if you use the {{site.data.keyword.dev_cli_short}} CLI to deploy an app to Cloud Foundry. If you enter a unique host name, you might still see this message.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

This error is caused by an expired login token.
{: tsCauses}

Log in again by running the following command:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Why do I get general command failures?
{: #general}
{: troubleshoot}

The following error might be displayed if you use the `create`, `delete`, `list`, or `code` commands:

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

This error is caused by an expired login token.
{: tsCauses}

Log in again by running the following command:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Why is the image for my new app not recognized?
{: #nosuchimage}
{: troubleshoot}

When you try to run an app without building it first, the following error might be displayed.

```
$ ibmcloud dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: tsSymptoms}

You must build an app before you run it. Run the following command in your current app directory:
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Run the following command in your current app directory to start your app:
```
ibmcloud dev run
```
{: tsResolve}

## Why do I get a service broker error when I add the {{site.data.keyword.objectstorageshort}} capability?
{: #os}
{: troubleshoot}

The following error might be displayed if you use the CLI to create two apps with the {{site.data.keyword.objectstorageshort}} capability:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

This error is due to the {{site.data.keyword.objectstorageshort}} service, which provides only one instance of the free {{site.data.keyword.objectstorageshort}} plan.
{: tsCauses}

Select a different plan.
{: tsResolve}

## Why isn't my code retrieved when I create an app?
{: #code}
{: troubleshoot}

The following error might be displayed when you use the CLI to create an app:

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

This error is due to an internal timeout.
{: tsCauses}

Use one of the following ways to get the code:

* Run the following command:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Replace `<your-app-name>` with the app name that you specified during app creation.

* Use the {{site.data.keyword.dev_console}}.

	1. Select your [app ![External link icon](../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/developer/appservice/apps) in the {{site.data.keyword.dev_console}}.

	2. Click **Download Code**.
{: tsResolve}

## Why can't I run the `ibmcloud dev run` commande for Node.js apps?
{: #node}
{: troubleshoot}

The following error might be displayed if you run the `ibmcloud dev run` command for Node.js web or BFF apps:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}
{: tsSymptoms}

This error occurs when the `appmetrics` module is installed on a different architecture. Native npm modules that are installed on one architecture do not work on another. The included Docker images are based on the Linux kernel.
{: tsCauses}

Delete the `node_modules` folder and run the `ibmcloud dev run` command again.
{: tsResolve}

## Why can't I deploy to {{site.data.keyword.Bluemix_notm}}?
{: troubleshoot}

A failure occurs when you try to deploy to {{site.data.keyword.Bluemix_notm}}, but there is no error displayed.
{: tsSymptoms}

You might not be logged in to your account.
{: tsCauses}

Run the following command to log in and try again.
```
ibmcloud login
```
{: tsResolve}

## Why can't I deploy to Kubernetes on {{site.data.keyword.Bluemix_notm}}?
{: troubleshoot}

The following failure might be displayed after you're prompted for your cluster name:
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

This is most likely due to a cluster name that's not valid. You can confirm the cause by running the same command with `--trace`, and the following details might be included in the error output:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Be sure that you are using the correct cluster and that you have configured your cluster for deployment by running:
```
ibmcloud cs cluster-config <cluster-name>
```
{: tsResolve}

## Why can't I deploy an image target?
{: troubleshoot}

The following failure might be displayed after you're prompted for the deploy image target:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

This is most likely due to a deploy image target that's not valid. More specifically, the namespace, which is the middle value in the deploy image target, might not be valid.
{: tsCauses}

Be sure that the namespace in the deploy image target matches one of the namespaces displayed when you run the following command:
```
ibmcloud cr namespaces
```
{: tsResolve}

## Why can't the language for my app be determined?
{: troubleshoot}

The following failure might be displayed when trying to start your app:
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: tsSymptoms}

This error might be due to one of the following causes:
- Running the [enable](/docs/cli/idt/commands.html#enable) command from a directory that is not the source directory of your application.
- Running the [enable](/docs/cli/idt/commands.html#enable) command for an app of a language that is not recognized at this time.
{: tsCauses}

Be sure that you run the command rom the app directory that contains source code for the app. If this does not solve the problem and the language is one of the [supported languages](/docs/cli/idt/commands.html#enable-language-options), use the `--language` parameter to specify the language.
{: tsResolve}

## Why can't I build or run an app that has been enabled for cloud deployment?
{: troubleshoot}

You might encounter various failures attempting to [build](/docs/cli/idt/commands.html#build) or [run](/docs/cli/idt/commands.html#run) an app that has been enabled.
{: tsSymptoms}


The many different possible causes can be found in each of the following links.
{: tsCauses}

- For more information about resolving such problems with a Spring app, see [Enabling existing Spring Boot applications for cloud deployment](/docs/java-spring/enable_existing.html#enable_existing).
- For more information about resolving such problems with a `Node.js` app, see [Enabling existing Node.js applications for cloud deployment](/docs/node/enable_existing.html#enable_existing).
{: tsResolve}

## How do I install the {{site.data.keyword.Bluemix_notm}} developer tools manually?
{: #appendix}
All prerequisites install for most users by using the platform installers. If you need to manually install any components, here are the instructions for each.
To install the dev plug-in, you must first install the [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use).
To use the dev plug-in itself, you must install it by running the following command: 
```
ibmcloud plugin install dev
```
{: codeblock}
 
For running and debugging apps locally, you must also install [Docker](https://www.docker.com/get-docker).
 
For deploying an app as a container, you must also install Kubernetes, Helm, and the following IBM Cloud CLI plug-ins.
 
### To install Kubernetes:
Mac users:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Linux users:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Windows users:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### To install Helm:
Mac and Linux users:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Windows users:
Download and install the [binary](https://github.com/kubernetes/helm/releases/tag/v2.7.2).

### To install the container-registry plug-in:
```
ibmcloud plugin install container-registry
```
{: codeblock}

### To install the container-service plug-in:
```
ibmcloud plugin install container-service
```
{: codeblock}


 
 
 
