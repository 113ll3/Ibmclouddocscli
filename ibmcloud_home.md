---

copyright:
  years: 2021
lastupdated: "2021-02-09"

keywords: IBM Cloud CLI, IBMCLOUD_HOME, ibmcloud cli, ibmcloud

subcollection: cli

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:external: target="_blank" .external}

# Working with multiple accounts or sessions with the {{site.data.keyword.cloud_notm}} CLI
{: #ibmcloud-home}

You can use the IBMCLOUD_HOME environment variable to work with multiple accounts or multiple sessions at the same time in the {{site.data.keyword.cloud}} CLI.
{: shortdesc}

With the IBMCLOUD_HOME environment variable, you can set a path for the local account metadata. You can specify a different directory for each account, and that's helpful when you want to create different {{site.data.keyword.cloud_notm}} CLI sessions for every call or API call.

## Before you begin
{: #ibmcloud-home-prereq}

* Set up your [{{site.data.keyword.cloud}} account](https://{DomainName}/registration){: external}. For more information, see [Setting up your {{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started).
* [Install the {{site.data.keyword.cloud_notm}} CLI](https://cloud.ibm.com/docs/cli?topic=cli-getting-started).

## Setting the IBMCLOUD_HOME environment variable
{: #ibmcloud-home-usage}

To run multiple {{site.data.keyword.cloud_notm}} CLI sessions in parallel, use different environments per session. You need to set up a different configuration directory for each session.

For your first environment, enter the following command:

```
  export IBMCLOUD_HOME=/home/myuser/.ibmcloudenv1
  ibmcloud login
```
{: codeblock}

For your second environment, enter the following command:

```
export IBMCLOUD_HOME=/home/myuser/.ibmcloudenv2
ibmcloud login
```
{: codeblock}

For more information about environment variables for the {{site.data.keyword.cloud_notm}} CLI, see [Tips and Tricks for Using the {{site.data.keyword.cloud_notm}} CLI](https://www.ibm.com/cloud/blog/tips-and-tricks-for-using-the-ibm-cloud-cli){: external}.
