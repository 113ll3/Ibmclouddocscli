---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-14"

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

[{{site.data.keyword.cloud_notm}} CLI plug-ins repository](https://tools.ng.bluemix.net){: new_window} ![External link icon](../../../icons/launch-glyph.svg) is the official repository where plug-ins are hosted.

For more commands to manage plug-ins, run `ibmcloud plugin` to see the help messages.
{: tip}

## Install a plug-in from the {{site.data.keyword.cloud_notm}} CLI repository
{: #install-from-repo}

### Step 1: Search for the plug-in
{: #step1-search-plugin}

1. Use the `ibmcloud plugin repo-plugins -r REPO_NAME` command to look for a plug-in in the repository.
2. The {{site.data.keyword.cloud_notm}} CLI has the official repository with name 'IBM Cloud', you can search the official plug-ins as shown in the following example:

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Step 2: Install the plug-in
{: step2-install-plugin}

Use the `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` command to install the plug-in. For example, use the following command to install a plug-in from the official IBM plug-in repo 'IBM Cloud':

  ```
  $ ibmcloud plugin install auto-scaling 
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Install a plug-in locally
{: #install-plugin-locally}

Use the `ibmcloud plugin install LOCAL_FILE_NAME` command to install a plug-in binary on your local machine. For example:

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Install a plug-in from a web URL
{: install-plugin-from-url}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a web URL. For example

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
