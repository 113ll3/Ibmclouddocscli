---

copyright:
  years: 2021, 2022
lastupdated: "2022-02-22"

keywords: IBM Cloud CLI, IBMCLOUD_HOME, ibmcloud cli, ibmcloud

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Working with multiple sessions with the {{site.data.keyword.cloud_notm}} CLI
{: #ibmcloud-home}

You can use the IBMCLOUD_HOME environment variable to work with multiple sessions at the same time in the {{site.data.keyword.cloud}} CLI.
{: shortdesc}

With the IBMCLOUD_HOME environment variable, you can set a path for the session metadata. You can specify a different directory for each session, and that's helpful when you want to run multiple {{site.data.keyword.cloud_notm}} CLI sessions simultaneously.

## Before you begin
{: #ibmcloud-home-prereq}

* Set up your [{{site.data.keyword.cloud}} account](/registration){: external}. For more information, see [Setting up your {{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started).
* [Install the {{site.data.keyword.cloud_notm}} CLI](https://cloud.ibm.com/docs/cli?topic=cli-getting-started).

## Setting the IBMCLOUD_HOME environment variable
{: #ibmcloud-home-usage}

To run multiple {{site.data.keyword.cloud_notm}} CLI sessions in parallel, use different environments per session. You need to set up a different configuration directory for each session.

For your first environment, enter the following command:

```bash
  export IBMCLOUD_HOME=/home/myuser/.ibmcloudenv1
  ibmcloud login
```
{: codeblock}

For your second environment, enter the following command:

```bash
export IBMCLOUD_HOME=/home/myuser/.ibmcloudenv2
ibmcloud login
```
{: codeblock}

For more information about environment variables for the {{site.data.keyword.cloud_notm}} CLI, see [Tips and Tricks for Using the {{site.data.keyword.cloud_notm}} CLI](https://www.ibm.com/cloud/blog/tips-and-tricks-for-using-the-ibm-cloud-cli){: external} and [{{site.data.keyword.cloud_notm}} CLI (ibmcloud) environment variables](/docs/cli?topic=cli-ibmcloud_env_var).
