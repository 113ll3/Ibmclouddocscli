---
copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Troubleshooting IBM Cloud Developer Tools
{: #ts}

Some known issues with the {{site.data.keyword.dev_cli_notm}} are documented, along with their workarounds.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Known issues
{: #knownissues}

The following sections describe known issues and possible resolutions.


### Hostname is taken error when you create a project with a non-mobile pattern
{: #hostname}

You might see the following error if you use the {{site.data.keyword.dev_cli_short}} to create a project from the Web App, BFF, or Microservice patterns:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Cause
{: #hostname-cause}

This error is due to an expired login token.


#### Resolution
{: #hostname-resolution}

Log in again.

```
ibmcloud login
```
{: codeblock}


### General failures with the {{site.data.keyword.dev_cli_short}}
{: #general}

You might see the following error if you use the {{site.data.keyword.dev_cli_short}} create, delete, list, or code commands:

```
Failed to <command> project.
```
{: codeblock}


#### Cause
{: #general-cause}

This error is due to an expired login token.


#### Resolution
{: #general-resolution}

Log in again.

```
ibmcloud login
```
{: codeblock}


### Error: No such image when you run a new project
{: #nosuchimage}

You might see the following error when you run a project without building it first.

```
$ ibmcloud dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### Cause
{: #nosuchimage-cause}

You must build a project before you run it.


#### Resolution
{: #nosuchimage-resolution}

Run the following command in your current project directory to build your application:

```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current project directory to start your application:

```
ibmcloud dev run
```


### Service broker error when you add the {{site.data.keyword.objectstorageshort}} capability
{: #os}

You might see the following error if you use the {{site.data.keyword.dev_cli_short}} to create two projects with the {{site.data.keyword.objectstorageshort}} capability:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Cause
{: #os-cause}

This error is due to the {{site.data.keyword.objectstorageshort}} service, which provides only one instance of the Free {{site.data.keyword.objectstorageshort}} plan.


#### Resolution
{: #os-resolution}

You are prompted to choose a different plan to avoid this error.


### Failure getting the code during project creation
{: #code}

You might see the following error if you use the {{site.data.keyword.dev_cli_short}} to create a project:

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### Cause
{: #code-cause}

This error is due to an internal timeout.


#### Resolution
{: #code-resolution}

You can get the code either of the following ways:

* Run the following command by using the CLI:

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   Replace `<your-project-name>` with the project name that you specified during project creation.

* Use the {{site.data.keyword.dev_console}}.

	1. Select your [project ![External link icon](../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/developer/projects) in the {{site.data.keyword.dev_console}} and click **Get the Code**.

	2. Click **Generate Code**.

	3. After the code is generated, click **Download Code**.


### Error running `ibmcloud dev run` for Node.js projects
{: #node}

You might see the following error if you are running `ibmcloud dev run` with the {{site.data.keyword.dev_cli_short}} for Node.js Web or BFF projects:

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


#### Cause
{: #node-cause}

This error occurs when the `appmetrics` module is installed on a different architecture. Native npm modules that are installed on one architecture do not work on another. The included Docker images are based on the Linux kernel.


#### Resolution
{: #node-resolution}

Delete `node_modules` folder and run `ibmcloud dev run` again.


### Failure to deploy to {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

You might attempt to deploy to {{site.data.keyword.Bluemix_notm}} with the {{site.data.keyword.dev_cli_short}} and you see that it does not deploy to {{site.data.keyword.Bluemix_notm}} but there is no error.


#### Cause
{: #cause1}

This could be that you are not logged in to your account.

#### Resolution
{: #resolution1}

Log in and try again.

```
ibmcloud login
```


### Failure to deploy to Kubernetes on {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploytokube}

You might see this failure after the initial prompt for your cluster name:

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### Cause
{: #cause2}

Most likely this is due to an invalid cluster name and can be confirmed by running the same command with `--trace` and you might see this in the error output:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Resolution
{: #resolution2}

Be sure that you are using the correct cluster and that you have configured your cluster for deployment by running

```
ibmcloud cs cluster-config <cluster-name>
```


### Failure to deploy to Kubernetes on {{site.data.keyword.Bluemix_notm}}

You might see this failure after the prompt for the deploy image target:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### Cause
{: #cause3}

Most likely, this is due to an invalid deploy image target. More specifically, it could be an invalid namespace, the middle value in the deploy image target


#### Resolution
{: #resolution3}

Be sure that the namespace in the deploy image target matches one of the namespaces that is found from running

```
ibmcloud cr namespaces
```



## APPENDIX
{: #appendix}

All prerequisites are installed for most users that are using the platform installers. If you need to manually install any components, here are the instructions:

To install the dev plug-in, the [IBM Cloud CLI](../reference/bluemix_cli/get_started.md#getting-started) must first be installed.

To use the dev plug-in itself, you must install it by running the following command: `ibmcloud plugin install dev -r Bluemix`

For running and debugging applications locally, you must also install [Docker ![External link icon](../icons/launch-glyph.svg "External link icon")](https://www.docker.com/get-docker).

For deploying an application as a container, you must also install `Kubernetes`, `Helm`, and the following IBM Cloud CLI plug-ins:

To install Kubernetes:
* Mac users:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux users:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows users:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

To install Helm:
* Mac and Linux users:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows users:
Download and install the binary at https://github.com/kubernetes/helm/releases/tag/v2.6.0

To install the container-registry plug-in:
`ibmcloud plugin install container-registry`

To install the container-service plug-in:
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Getting help and support
{: #gettinghelp}

If you have problems or questions about the {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} or the {{site.data.keyword.dev_cli_notm}}, get help by searching for information or by asking questions through a forum. You can also open a support ticket.

When you post in the forums, you can tag your questions so that the {{site.data.keyword.Bluemix_notm}} development teams are notified.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

If you have technical questions about developing or deploying an app with the {{site.data.keyword.dev_console}} or the {{site.data.keyword.dev_cli_notm}}:

* Post your question on [Stack Overflow ![External link icon](../icons/launch-glyph.svg "External link icon")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) and tag your question with `bluemix-dev-services` and `ibm-bluemix`.
* Post your question on [Slack ![External link icon](../icons/launch-glyph.svg "External link icon")](http://ibm-cloud-tech.slack.com/) in the `bluemix-dev-services` channel. [Sign up ![External link icon](../icons/launch-glyph.svg "External link icon")](http://ibm.biz/IBMCloudNativeSlack) today.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

See [Getting help ![External link icon](../icons/launch-glyph.svg "External link icon")](/docs/support/index.html#getting-help) for more details about using the forums.

For information about opening an {{site.data.keyword.IBM}} support ticket, or about support levels and ticket severities, see [Contacting support ![External link icon](../icons/launch-glyph.svg "External link icon")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
