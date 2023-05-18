---

copyright:
  years: 2015, 2023
lastupdated: "2023-05-17"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, cli, command line, command-line, developer tools, plugin install

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Extending {{site.data.keyword.cloud_notm}} CLI with plug-ins
{: #plug-ins}

The {{site.data.keyword.cloud}} Command Line Interface supports a plug-in framework to extend its capability. Install a plug-in from a repository, a URL, or install a plug-in binary locally.
{: shortdesc}

For more commands to manage plug-ins, run `ibmcloud plugin` to see the help messages. For more information, see [Adding and removing {{site.data.keyword.cloud_notm}} CLI plug-ins](/docs/cli?topic=cli-ibmcloud_commands_settings).
{: tip}

## Before you begin
{: #cli-before-you-begin}

Install the stand-alone [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-install-ibmcloud-cli#install-ibmcloud-cli) so that you can install CLI plug-ins for {{site.data.keyword.cloud_notm}}.

## Searching for a plug-in
{: #cli-search-plugin}

Use the `ibmcloud plugin repo-plugins` command to discover all the available plug-ins in the repository.

```bash
ibmcloud plugin repo-plugins
```
{: codeblock}

```text
Status             Name                                        Versions                       Description   
Update Available   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Manage Cloud Functions 
...
```
{: screen}

## Installing a plug-in from the {{site.data.keyword.cloud_notm}} CLI repository
{: #install-from-repo}

### Installing a specific plug-in
{: #cli-install-plugin}

Use the `ibmcloud plugin install PLUGIN_NAME` command to install a specific plug-in. For example, use the following command to install the {{site.data.keyword.cloud_notm}} Code Engine CLI plug-in:

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

### Installing all plug-ins
{: #cli-install-all}

Use the `plugin install -a` command to install all the latest available plug-ins that are in the repository:

```bash
ibmcloud plugin install -a
```

### Installing multiple plug-ins
{: #cli-install-multiple}

Use the `plugin install PLUGIN_NAME@VERSION` command to install multiple plug-ins at the same time. For example, use the following command to install the container-service@1.0.506 and the secrets-manager@0.1.25 plug-ins:

```bash
ibmcloud plugin install container-service@1.0.506 secrets-manager@0.1.25
```

For more information, see [`ibmcloud plugin install`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_install).

## Confirming installed plug-ins
{: #cli-install-view}

Use the `plugin list` command to confirm that all required plug-ins are installed in {{site.data.keyword.cloud_notm}} CLI. The `plugin list` command returns the following information for each plugin that is installed:

* The plug-in name.
* The current version of the plug-in.
* Whether a more recent version of the plugin is available.
* Whether the plug-in version supports private endpoint use.

```bash
ibmcloud plugin list
```

## Related information
{: #cli-install-relinfo}

You can also install a plug-in from a URL, download a plug-in, or install a plug-in binary locally:

* To install a plug-in from a URL, see [`ibmcloud plugin install`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_install).
* To download a plug-in, see [How do I download a plug-in?](/docs/cli?topic=cli-ibm-cli-faq#cli-install-download-local)
* To install a plug-in locally, see [`ibmcloud plugin install`](/docs/cli?topic=cli-ibmcloud_commands_settings#ibmcloud_plugin_install).

