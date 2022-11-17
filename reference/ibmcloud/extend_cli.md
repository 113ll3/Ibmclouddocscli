---

copyright:
  years: 2015, 2022
lastupdated: "2022-11-17"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Extending {{site.data.keyword.cloud_notm}} CLI with plug-ins
{: #plug-ins}

The {{site.data.keyword.cloud}} Command Line Interface supports a plug-in framework to extend its capability. You can install a plug-in from a repository, a web URL, or install a plug-in binary locally.

For more commands to manage plug-ins, run `ibmcloud plugin` to see the help messages. For more information, see also [Adding and removing IBM Cloud CLI plug-ins](/docs/cli?topic=cli-ibmcloud_commands_settings).
{: tip}

## Installing a plug-in from the {{site.data.keyword.cloud_notm}} CLI repository
{: #install-from-repo}

### Searching for a plug-in
{: #cli-search-plugin}

Use the `ibmcloud plugin repo-plugins -r REPO_NAME` command to look for a plug-in in the repository.

The {{site.data.keyword.cloud_notm}} CLI provides an official plug-in repository with the name 'IBM Cloud', which you can search as shown in the following example:
```bash
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```text
Status             Name                                        Versions                       Description   
Update Available   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Manage Cloud Functions 
...
```
{: screen}

### Installing the plug-in
{: #cli-install-plugin}

Use the `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` command to install the plug-in. For example, use the following command to install a plug-in from the official IBM plug-in repo 'IBM Cloud':
```bash
ibmcloud plugin install code-engine
```
{: codeblock}

```text
Looking up 'code-engine' from repository 'IBM Cloud'...
Plug-in 'code-engine 1.23.2' found in repository 'IBM Cloud'
Attempting to download the binary file...
 54.29 MiB / 54.29 MiB [============================================] 100.00% 10s
56929376  bytes downloaded
Installing binary...
OK
Plug-in 'code-engine 1.23.2' was successfully installed into /Users/username/.bluemix/plugins/code-engine. Use 'ibmcloud plugin show code-engine' to show its details.
```
{: screen}

## Installing a plug-in locally
{: #install-plugin-locally}

Use the `ibmcloud plugin install LOCAL_FILE_NAME` command to install a plug-in binary on your local computer. For example:
```bash
ibmcloud plugin install ./code-engine-darwin-amd64-1.23.2
```
{: codeblock}

```text
Installing plugin './code-engine-darwin-amd64-1.23.2'...
OK
Plug-in 'code-engine 1.23.2' was successfully installed into /Users/username/.bluemix/plugins/code-engine. Use 'ibmcloud plugin show code-engine' to show its details.
$
```
{: screen}

## Installing a plug-in from a web URL
{: #install-plugin-from-url}

Use the `ibmcloud plugin install URL` command to install a plug-in directly from a web URL. For example:
```bash
ibmcloud plugin install http://example.com/downloads/my-plugin
```
{: codeblock}
