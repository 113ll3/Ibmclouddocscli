---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-03"

keywords: cli, docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

{:external: target="_blank" .external}

# Using {{site.data.keyword.dev_cli_notm}} from a Docker Container
{: #using-idt-from-docker}

With the {{site.data.keyword.dev_cli_long}} Docker Container, you get the {{site.data.keyword.cloud}} Command Line Interface, plus the following tools:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} plug-in
* {{site.data.keyword.registrylong_notm}} plug-in
* {{site.data.keyword.containerlong_notm}} plug-in

## Before you begin
{: #idt-docker-prereq}

You need an [{{site.data.keyword.cloud_notm}} account](https://{DomainName}/login){: external} and you must install the most recent stable Docker version.

## Step 1. Pull the Docker Image from the Docker hub
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Step 2. Start the Docker Container
{: #step2-start-docker}

Use the following command to start the {{site.data.keyword.dev_cli_notm}} Docker Container.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Step 3. Log in to {{site.data.keyword.cloud_notm}} with your IBMid
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

If your credentials are rejected, you might be using a federated ID. See [Logging in with a federated ID](/docs/account?topic=account-federated_id) for more details.
{: tip}

The {{site.data.keyword.dev_cli_notm}} commands use two containers to facilitate building and testing your application. The first is the tools container, which contains the necessary utilities to build and test your app. The `Dockerfile` for this container is defined by the [`dockerfile-tools`](/docs/cli?topic=cli-idt-cli#build-dockerfile-tools) parameter. You might think of it as a development container, as it contains the tools that are normally used for development of a particular runtime.

The second container is the run container, which closely mimics the actual runtime environment of your app. This container is in a form that is suitable to be deployed for use, for example, in {{site.data.keyword.cloud_notm}}. As a result, an entry point is defined that starts your app. When you choose to run your app through the {{site.data.keyword.cloud_notm}} CLI, it uses this container. The `Dockerfile` for this container is defined by the [`dockerfile-run`](/docs/cli?topic=cli-idt-cli#run-parameters) parameter.

Now you're ready to use the {{site.data.keyword.dev_cli_notm}} commands to manage {{site.data.keyword.cloud_notm}} resources and develop and deploy your apps.
