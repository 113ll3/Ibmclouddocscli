---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Using {{site.data.keyword.dev_cli_notm}} from a Docker Container

With the {{site.data.keyword.dev_cli_notm}} Docker Container, you get the {{site.data.keyword.Bluemix}} CLI, plus the following tools:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} plug-in
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} plug-in
* {{site.data.keyword.registrylong_notm}} plug-in
* {{site.data.keyword.containerlong_notm}} plug-in
* `sdk-gen` plug-in

## Before you begin
{: #prereq}

You need an [{{site.data.keyword.Bluemix_notm}} account](https://console.bluemix.net/){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") and you must install the latest stable Docker version before taking the following steps.

## Step 1. Pull the Docker Image from the Docker hub.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Step 2. Start the Docker Container.
{: #step2}

Use the following command to start the {{site.data.keyword.dev_cli_notm}} Docker Container.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Step 3. Log in to {{site.data.keyword.Bluemix_notm}} with your IBMid.
{: #step3}

```
ibmcloud login
```
{: codeblock}


If your credentials are rejected, you might be using a federated ID. See [Logging in with a federated ID](/docs/iam/login_fedid.html#federated_id) for more details.
{: tip}

Now you are ready to use the {{site.data.keyword.dev_cli_notm}} to manage {{site.data.keyword.Bluemix_notm}} resources and  develop and deploy your applications.
