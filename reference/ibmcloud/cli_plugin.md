---

copyright:
  years: 2018, 2021
lastupdated: "2021-12-29"

keywords: cli, add cli plug-in, remove cli plug-in, cli plug-in, ibmcloud plugin, repo-add, repo-remove, plugin uninstall, plugin update, cli private endpoints

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Adding and removing {{site.data.keyword.cloud_notm}} CLI plug-ins (ibmcloud plugin)
{: #ibmcloud_commands_settings}

{{site.data.keyword.cloud}} supports a plug-in framework to extend its capability. Use the following commands to manage the {{site.data.keyword.cloud_notm}} Command Line Interface plug-ins.
{: shortdesc}

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

List all plug-in repositories that are registered in {{site.data.keyword.cloud_notm}} CLI.

```bash
ibmcloud plugin repos
```
{: codeblock}

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Add a new plug-in repository to {{site.data.keyword.cloud_notm}} CLI.

```bash
ibmcloud plugin repo-add REPO_NAME REPO_URL
```
{: codeblock}

**Command options**:

REPO_NAME (required)
:   The name of the repository to be added. You can define your own name for each repository.

REPO_URL (required)
:   The URL of the repository to be added. The repository URL must contain the protocol (for example, `https://plugins.cloud.ibm.com` instead of `plugins.cloud.ibm.com`). https://plugins.cloud.ibm.com is the official plug-in repository of {{site.data.keyword.cloud_notm}} CLI.

**Examples**:

Add the official plug-in repository of {{site.data.keyword.cloud_notm}} CLI as `ibmcloud-repo`:

```bash
ibmcloud plugin repo-add ibmcloud-repo https://plugins.cloud.ibm.com
```
{: codeblock}

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Remove a plug-in repository from {{site.data.keyword.cloud_notm}} CLI.

```bash
ibmcloud plugin repo-remove REPO_NAME
```
{: codeblock}

**Command options**:

REPO_NAME (required)
:   The name of the repository to be removed.

**Examples**:

Remove `ibmcloud-repo` repository from {{site.data.keyword.cloud_notm}} CLI:

```bash
ibmcloud plugin repo-remove ibmcloud-repo
```
{: codeblock}

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

List all available plug-ins in all added repositories or a specific repository.

```bash
ibmcloud plugin repo-plugins [-r REPO_NAME]
```
{: codeblock}

**Command options**:

-r REPO_NAME (optional)
:   List only the plug-ins in the specified repository.

**Examples**:

List all plug-ins in all added repositories:

```bash
ibmcloud plugin repo-plugins
```
{: codeblock}

List all plug-ins in the `ibmcloud-repo` repository:

```bash
ibmcloud plugin repo-plugins -r ibmcloud-repo
```
{: codeblock}

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Show the details of a plug-in in the repository.

```bash
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```
{: codeblock}

**Command options**:

-r REPO_NAME (optional)
:   The name of the repository. If no repository is specified, the command uses the default plug-in repository.å

**Examples**:

List details of plug-in "IBM-Containers" in repository "sample-repo":

```bash
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```
{: codeblock}

List details of plug-in "IBM-Containers" in default repository

```bash
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```
{: codeblock}

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

List all installed plug-ins in {{site.data.keyword.cloud_notm}} CLI. Each plug-in returns the current version installed, whether there is a more recent version available for update, and if the version of the plug-in installed supports private endpoint use.

```bash
ibmcloud plugin list
```
{: codeblock}

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Show details of an installed plug-in.

```bash
ibmcloud plugin show PLUGIN-NAME
```
{: codeblock}

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Install a specific version of a plug-in to {{site.data.keyword.cloud_notm}} CLI from the specified path or repository, or all latest available plug-ins in the repository.

```bash
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION] [-f]
```
{: codeblock}

```bash
ibmcloud plugin install [-a, --all] [-r REPO_NAME] [-f]
```
{: codeblock}

```bash
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```
{: codeblock}

If no repository is specified, the command uses the default plug-in repository `IBM Cloud`. If you are installing a single plug-in, and no version is specified, the command selects the latest available version to install. If the '-a, --all' flag is specified, the command installs all latest available plug-ins in the repository.

**Command options**:

PLUGIN_PATH|PLUGIN_NAME
:   If -r REPO_NAME is not specified, the plug-in is installed from the specified local path or remote URL.

-a, --all (optional)
:   Install all latest available plug-ins in the repository.

-r REPO_NAME (optional)
:   The name of the repository where the plug-in binary is located. If no repository is specified, the command uses the default plug-in repository `IBM Cloud`.

-v VERSION (optional)
:   Version of the plug-in to be installed. Accepts specific semantic version or constraint.

-f 
:   Force installs the plug-in without confirmation.

The {{site.data.keyword.cloud_notm}} CLI has the official repository name of `IBM Cloud`.

**Examples**:

Install a plug-in from the local file:

```bash
ibmcloud plugin install /downloads/new_plugin
```
{: codeblock}

Install a plug-in from the remote URL:

```bash
ibmcloud plugin install http://example.com/downloads/my-plugin
```
{: codeblock}

Install the `container-service` plug-in of the latest version from the `IBM Cloud` repository:

```bash
ibmcloud plugin install container-service -r "IBM Cloud"
```
{: codeblock}

or you can run:

```bash
ibmcloud plugin install container-service
```
{: codeblock}

Install the `container-service` plug-in with the version `0.1.425` from the official plug-in repository:

```bash
ibmcloud plugin install container-service -v 0.1.425
```
{: codeblock}

Install all latest available plug-ins from the official plug-in repository:

```bash
ibmcloud plugin install --all
```
{: codeblock}

Install all latest available plug-ins from the official plug-in repository without confirmation:

```bash
ibmcloud plugin install --all -f
```
{: codeblock}

## ibmcloud plugin download
{: #ibmcloud_plugin_download}

Download a specific version of a plug-in to {{site.data.keyword.cloud_notm}} CLI from the specified repository, or all latest available plug-ins in the repository.

```bash
ibmcloud plugin download PLUGIN_NAME [-r REPO_NAME] [-v VERSION] [-d, --dest DOWNLOAD_DIRECTORY] [-f]
```
{: codeblock}

```bash
ibmcloud plugin download [-a, --all] [-r REPO_NAME] [-f]
```
{: codeblock}

```bash
ibmcloud plugin download URL [-f] [-d DOWNLOAD_DIRECTORY]
```
{: codeblock}

If no repository is specified, the command uses the default plug-in repository `IBM Cloud`. If you are downloading a single plug-in, and no version is specified, the command selects the latest available version to download. If the '-a, --all' flag is specified, the command downloads all latest available plug-ins in the repository.

**Command options**:

-a, --all (optional)
:   Downloads all latest available plug-ins in the repository.

-r REPO_NAME (optional)
:   The name of the repository where the plug-in binary is located. If no repository is specified, the command uses the default plug-in repository `IBM Cloud`.

-v VERSION (optional)
:   Version of the plug-in to be downloaded. Accepts specific semantic version or constraint.

-d, --dest DOWNLOAD_DIRECTORY (optional)
:   The destination directory for the downloaded plug-in. If not specified, this is the working directory.

-f 
:   Force downloads the plug-in without confirmation.

The {{site.data.keyword.cloud_notm}} CLI has the official repository name of `IBM Cloud`.

**Examples**:

Download a plug-in from the remote URL:

```bash
ibmcloud plugin download http://example.com/downloads/my-plugin
```
{: codeblock}

Download the `container-service` plug-in of the latest version from the `IBM Cloud` repository:

```bash
ibmcloud plugin download container-service -r "IBM Cloud"
```
{: codeblock}

Or you can run:

```bash
ibmcloud plugin download container-service
```
{: codeblock}

Download the `container-service` plug-in with the version `0.1.425` from the official plug-in repository:

```bash
ibmcloud plugin download container-service -v 0.1.425
```
{: codeblock}

Download the `container-service` plug-in with the version `0.1.425` from the official plug-in repository, into the `~/my_downloads` directory:

```bash
ibmcloud plugin download container-service -v 0.1.425 -d ~/my_downloads
```
{: codeblock}

Download all latest available plug-ins from the official plug-in repository:

```bash
ibmcloud plugin download --all
```
{: codeblock}

Download all latest available plug-ins from the official plug-in repository without confirmation:

```bash
ibmcloud plugin download --all -f
```
{: codeblock}

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Upgrade the plug-in from a repository.

```bash
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```
{: codeblock}

If no repository is specified, the command uses the default plug-in repository `IBM Cloud`. If no version is specified, the command selects the latest available version to install.

**Command options**:

PLUGIN NAME
:   Name of the plug-in to update. If not specified, the command checks upgrades for all plug-ins installed.

-r REPO_NAME
:   The name of the repository where the plug-in binary is located. If not specified, the command uses the default plug-in repository `IBM Cloud`.

-v VERSION (optional)
:   The version of the plug-in to be updated to. If not provided, update the plug-in to the most recent version.

--all
:   Update all available plug-ins.

**Examples**:

Check for all available upgrades in the official plug-in repository `IBM Cloud`:

```bash
ibmcloud plugin update -r "IBM Cloud"
```
{: codeblock}

or you can run:

```bash
ibmcloud plugin update
```
{: codeblock}

Upgrade the plug-in `container-service` in the official plug-in repository to the most recent:

```bash
ibmcloud plugin update container-service
```
{: codeblock}

Update the plug-in `container-service` in the official plug-in repository to version '0.1.440':

```bash
ibmcloud plugin update container-service -v 0.1.440
```
{: codeblock}

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Uninstall the specified plug-in from {{site.data.keyword.cloud_notm}} CLI.

```bash
ibmcloud plugin uninstall PLUGIN_NAME
```
{: codeblock}

**Command options**:

PLUGIN_NAME (required)
:   The name of the plug-in to be uninstalled.

**Examples**:

Uninstall the 'container-service' plug-in that was previously installed:

```bash
ibmcloud plugin uninstall container-service
```
{: codeblock}
