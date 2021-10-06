---

copyright:
  years: 2015, 2021
lastupdated: "2021-10-06"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, command line, command-line, developer tools troubleshoot

subcollection: cli

content-type: troubleshoot

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:external: target="_blank" .external}
{:support: data-reuse='support'}

# Troubleshooting for the {{site.data.keyword.cloud_notm}} CLI and {{site.data.keyword.dev_cli_short}}
{: #troubleshoot}

See solutions to common problems with using the {{site.data.keyword.cloud}} Command Line Interface. In many cases, you can recover from these problems by following a few easy steps.
{: shortdesc}

## Why do I get a failure when updating the CLI, updating a plug-in, or installing a plug-in?
{: #ts-cli-version-1-failure}
{: troubleshoot}
{: support}

If you are attempting to update the {{site.data.keyword.cloud_notm}} CLI, or update or install a plug-in with a CLI version lower than 2.0.0, you see an error similar to the following message.
{: tsSymptoms}

```text
An error occurred when fetching latest CLI info:
invalid character '<' looking for beginning of value
```
{: screen}

This error is caused by the older CLI version attempting to reach the deprecated CLI repo infrastructure.
{: tsCauses}

Download and install or replace the older CLI with the latest CLI version by using these [instructions](/docs/cli?topic=cli-install-ibmcloud-cli).
{: tsResolve}

## Why do I get a host name error when I create an application with a non-mobile pattern?
{: #ts-cli-hostname-error}
{: troubleshoot}
{: support}

The following error might be displayed if you use the {{site.data.keyword.cloud_notm}} CLI to deploy an application to Cloud Foundry. If you enter a unique host name, you might still see this message.
{: tsSymptoms}

```text
The hostname <myHostname> is taken.
```
{: screen}


This error is caused by an expired login token.
{: tsCauses}

Log in again by running the following command:
{: tsResolve}

```text
ibmcloud login
```
{: codeblock}


## Why do I get general command failures?
{: #ts-cli-general-failures}
{: troubleshoot}
{: support}

The following error might be displayed if you use the `create`, `delete`, `list`, or `code` commands:
```text
Failed to <command> app.
```
{: screen}
{: tsSymptoms}

This error is caused by an expired login token.
{: tsCauses}

Log in again by running the following command:
```text
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Why is the image for a new app not recognized?
{: #ts-cli-nosuchimage}
{: troubleshoot}

When you try to `ibmcloud dev run` an app without building it first, the following error might be displayed.
```text
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
{: screen}
{: tsSymptoms}

You must build an app before you run it. Run the following command in your current app directory:
```text
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Run the following command in your current app directory to start your app:
```text
ibmcloud dev run
```
{: tsResolve}

## Why do I get a service broker error when I add the {{site.data.keyword.objectstorageshort}} capability?
{: #ts-cli-object-storage}
{: troubleshoot}

The following error might be displayed if you use the CLI to create two apps with the {{site.data.keyword.objectstorageshort}} capability:

```text
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

This error is due to the {{site.data.keyword.objectstorageshort}} service, which provides only one instance of the free {{site.data.keyword.objectstorageshort}} plan.
{: tsCauses}

Select a different plan.
{: tsResolve}

## Why isn't code retrieved when I create an app?
{: #retrieve-code-error}
{: troubleshoot}

The following error might be displayed when you use the CLI to create an app:
```text
FAILED                            
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

This error is due to an internal timeout.
{: tsCauses}

Use one of the following ways to get the code:

* Run the following command:

   ```text
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Replace `<your-app-name>` with the app name that you specified during app creation.

* Use the {{site.data.keyword.dev_console}}.

	1. Select your [app](https://cloud.ibm.com/resources){: external} in the {{site.data.keyword.dev_console}}.

	2. Click **Download Code**.
{: tsResolve}

## Why can't I run the `ibmcloud dev run` command for Node.js apps?
{: #ts-cli-node}
{: troubleshoot}

The following error might be displayed if you run the `ibmcloud dev run` command for Node.js web or BFF apps:

```text
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
{: screen}
{: tsSymptoms}

This error occurs when the `appmetrics` module is installed on a different architecture. Native `npm` modules that are installed on one architecture do not work on another. The included Docker images are based on the Linux&trade; kernel.
{: tsCauses}

Delete the `node_modules` folder and run the `ibmcloud dev run` command again.
{: tsResolve}

## Why can't I deploy to {{site.data.keyword.cloud_notm}}?
{: #ts-cli-deploy-issues}
{: troubleshoot}
{: support}

A failure occurs when you try to deploy to {{site.data.keyword.cloud_notm}}, but no error is displayed.
{: tsSymptoms}

You might not be logged in to your account.
{: tsCauses}

Run the following command to log in and try again.
```text
ibmcloud login
```
{: tsResolve}

## Why can't I deploy to Kubernetes on {{site.data.keyword.cloud_notm}}?
{: #ts-cli-kube-deploy}
{: troubleshoot}
{: support}

The following failure might be displayed after you're prompted for your cluster name:
```text
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

The problem is most likely due to a cluster name that's not valid. You can confirm the cause by running the same command with `--trace`, and the following details might be included in the error output:
```text
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Be sure that you are using the correct cluster and that it is configured for deployment by running:
```text
ibmcloud ks cluster config <cluster-name>
```
{: codeblock}
{: tsResolve}

## Why can't I deploy an image target?
{: #ts-deploy-image-target}
{: troubleshoot}

The following failure might be displayed after you're prompted for the deployment image target:
```text
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

The problem is most likely due to a deployment image target that's not valid. More specifically, the namespace, which is the middle value in the deployment image target, might not be valid.
{: tsCauses}

Be sure that the namespace in the deployment image target matches one of the namespaces that are displayed when you run the following command:
```text
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Why can't the app language be determined?
{: #ts-cli-determine-language}
{: troubleshoot}

The following failure might be displayed when you start your app:
```text
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

This error might be due to one of the following causes:
- Running the [enable](/docs/cli?topic=cli-idt-cli#enable) command from a directory that is not the source directory of your app.
- Running the [enable](/docs/cli?topic=cli-idt-cli#enable) command for an app of a language that is not recognized.
{: tsCauses}

Be sure that you run the command from the app directory that contains source code for the app. If the issue is not resolved, and the language is one of the [supported languages](/docs/cli?topic=cli-idt-cli#enable-language-options), use the `--language` parameter to specify the language.
{: tsResolve}

## Why can't I build or run a Node.js app that is enabled for cloud deployment?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

You might encounter various failures to [build](/docs/cli?topic=cli-idt-cli#build) or [run](/docs/cli?topic=cli-idt-cli#run) an app that is enabled for cloud deployment.
{: tsSymptoms}

These failures have many possible causes. For more information about resolving such problems with a `Node.js` app, see [Enabling existing Node.js apps for cloud deployment](/docs/node?topic=node-enable_existing#enable_existing).
{: tsResolve}

## Why can't I build the Docker image?
{: #ts-cli-docker}
{: troubleshoot}

If you see the following the error: 
```text
FAILED
An error exit status 1 was encountered while building the Docker 
image.
```
{: screen}

This error might be due to one of the following causes:
- Docker is not installed.
- The Docker daemon is not running.
{: tsCauses}

Be sure that Docker is installed and running:
- To install or start [Docker for Mac](https://docs.docker.com/docker-for-mac/install/){: external}
- To install or start [Docker for Windows&trade;](https://docs.docker.com/docker-for-windows/install/){: external}
- To install or start [Docker for Linux&trade;](https://docs.docker.com/v17.12/install/){: external}
{: tsResolve}

## Why is my Helm upgrade failing with errors?
{: #ts-cli-helm-rbac}
{: troubleshoot}

You can run into the following error due to role-based access control (RBAC) issues:
```text
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED: 
configmaps is forbidden: User "system:serviceaccount:kube-system:default" 
cannot list resource "configmaps" in API group "" in the namespace 
"kube-system"
```
{: screen}

To resolve the issue, run the following command:
{: tsResolve}

```text
kubectl create clusterrolebinding tiller --clusterrole=cluster-admin --serviceaccount=kube-system:default -n kube-system
```
{: codeblock}

## How do I resolve incompatible Helm versions?
{: #ts-cli-helm}
{: troubleshoot}

If the client and server Helm versions are not in sync, you might see the following errors:
```text
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

To resolve the issue, set the client's version to the same as the cluster's version. For example, to install the 2.8.1 Helm version, run the following commands:
{: tsResolve}

* For Mac and Linux&trade;, run the following commands:
   ```text
   export DESIRED_VERSION=v2.8.1
 
   curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
 
   export HELM_HOME=~/.helm
   ```

* For Windows&trade;: As an administrator, download and install the `helm` binary from [https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: external}.
  
   From the PowerShell terminal, use the following commands:
   ```text
   Set-Location Env:
   Set-Item HELM_HOME C:\.helm\
   ```
   {: codeblock}

## Why does the Helm init command fail during app deployment to my Kubernetes cluster?
{: #ts-cli-helm-error}
{: troubleshoot}
{: support}

When I try to deploy my app to a Kubernetes cluster by using the `ic dev deploy -t container` command, the following error occurs:
{: tsSymptoms}

```text
Executing helm init
$HELM_HOME has been configured at /Users/username/.helm.
FAILED
The 'helm init' command failed to complete due to: exit status 1
```
{: screen}

Some specifications are deprecated with new Kubernetes V1.16 clusters.
{: tsCauses}

Update Helm to 2.16.0 or later.
{: tsResolve}

## Why is `ibmcloud dev build` failing with a user name that includes "@"?
{: #ts-cli-username}
{: troubleshoot}

During the image build process, your user name is used for the user in the Docker tools image. If the user name contains any special characters like '@' or '-', then the Docker image build process fails with the following error:
```text
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Dumping output from the command:
```
{: screen}

To resolve the issue, change your user name to not include any special characters, or specify the following flag to use the root user instead:
```text
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}

## Why is `ibmcloud dev build` failing with "exit status 100"?
{: #ts-cli-build-error}
{: troubleshoot}

Running the `ibmcloud dev build` command displays the following error:
```text
FAILED
An error exit status 100 was encountered while building the Docker image.
```
{: screen}
{: tsSymptoms}

There is a problem with mapping the OS user into the container due to a UID conflict.
{: tsCauses}

Resolve the OS user's UID conflict. To work around the issue, you can run the following command:
{: tsResolve}

```text
ibmcloud dev build --use-root-user-tools
```
{: codeblock}

## Why does the 'ibmcloud catalog search' command fail?
{: #ts-cli-catalog-search-error}
{: troubleshoot}

Running the `ibmcloud catalog search` command displays the following error:
```text
FAILED
'search' is not a registered command. See 'C:\Program Files\IBM\Cloud\bin\ibmcloud.exe catalog help'.
```
{: screen}
{: tsSymptoms}

The `ibmcloud catalog search` command was moved to a separate plug-in in v1.0.0.
{: tsCauses}

To use this command, you must install the catalogs-management plug-in. For more information, see [Catalogs management CLI plug-in](/docs/cli?topic=cli-manage-catalogs-plugin).
{: tsResolve}
