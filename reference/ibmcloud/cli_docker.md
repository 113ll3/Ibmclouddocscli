---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-12"

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

Now you're ready to use the {{site.data.keyword.dev_cli_notm}} commands to manage {{site.data.keyword.cloud_notm}} resources and develop and deploy your apps.
