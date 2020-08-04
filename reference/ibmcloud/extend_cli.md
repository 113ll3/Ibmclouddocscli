---

copyright:
  years: 2015, 2020
lastupdated: "2020-08-03"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:external: target="_blank" .external}

# Extending {{site.data.keyword.cloud_notm}} CLI with plug-ins
{: #plug-ins}

The {{site.data.keyword.cloud}} Command Line Interface supports a plug-in framework to extend its capability. You can install a plug-in from a repository, a web URL, or install a plug-in binary locally.

For more commands to manage plug-ins, run `ibmcloud plugin` to see the help messages.
{: tip}

## Installing a plug-in from the {{site.data.keyword.cloud_notm}} CLI repository
{: #install-from-repo}

### Searching for a plug-in
{: #cli-search-plugin}

Use the `ibmcloud plugin repo-plugins -r REPO_NAME` command to look for a plug-in in the repository.

The {{site.data.keyword.cloud_notm}} CLI provides an official plug-in repository with the name 'IBM Cloud', which you can search as shown in the following example:
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                        Versions                       Description   
Update Available   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Manage Cloud Functions 
...
```
{: screen}

### Installing the plug-in
{: #cli-install-plugin}

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

## Installing a plug-in locally
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

## Installing a plug-in from a web URL
{: #install-plugin-from-url}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a web URL. For example:
```
ibmcloud plugin install http://example.com/downloads/my-plugin
```
{: codeblock}
