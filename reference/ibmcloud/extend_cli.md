---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Extending {{site.data.keyword.cloud_notm}} CLI with plug-ins
{: #plug-ins}

{{site.data.keyword.cloud}} CLI supports a plug-in framework to extend its capability. You can install a plug-in from a repository, a web URL, or install a plug-in binary locally.

[{{site.data.keyword.cloud_notm}} CLI plug-ins repository](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![External link icon](../../../icons/launch-glyph.svg) is the official repository where plug-ins are hosted.

For more commands to manage plug-ins, run `ibmcloud plugin` to see the help messages.
{: tip}

## Install a plug-in from the {{site.data.keyword.cloud_notm}} CLI repository
{: #install-from-repo}

### Step 1: Search for the plug-in
{: #step1-search-plugin}

1. Use the `ibmcloud plugin repo-plugins -r REPO_NAME` command to look for a plug-in in the repository.
2. The {{site.data.keyword.cloud_notm}} CLI has the official repository with name 'IBM Cloud', you can search the official plug-ins as shown in the following example:
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                   Versions                       Description   
Update Available   container-service/kubernetes-service   0.2.99, 0.2.95, 0.2.80...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                        1.0.30, 1.0.29, 1.0.28...      IBM Cloud CLI plug-in for IBM Cloud Functions   
...
```
{: screen}

### Step 2: Install the plug-in
{: step2-install-plugin}

Use the `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` command to install the plug-in. For example, use the following command to install a plug-in from the official IBM plug-in repo 'IBM Cloud':

```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
Looking up 'auto-scaling' from repository 'IBM Cloud'...
Plug-in 'auto-scaling 0.2.7' found in repository 'IBM Cloud'
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
```
{: screen}

## Install a plug-in locally
{: #install-plugin-locally}

Use the `ibmcloud plugin install LOCAL_FILE_NAME` command to install a plug-in binary on your local machine. For example:

```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}

## Install a plug-in from a web URL
{: install-plugin-from-url}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a web URL. For example:
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

Output:
```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}
