---

copyright:
  years: 2019
lastupdated: "2019-08-15"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Uninstalling the stand-alone {{site.data.keyword.cloud_notm}} CLI
{: #uninstall-ibmcloud-cli}

Use the following steps to uninstall the stand-alone {{site.data.keyword.cloud_notm}} CLI on specific platforms.
{: shortdesc}

## Uninstalling on Windows
{: #uninstall-cli-windows}

1. Click the **Start** button, and then select **Control Panel**.
2. In the pop-up window, click **Uninstall a program**.
3. In the pop-up application list, locate **IBM Cloud Command Line Interface**.
4. Right-click **IBM Cloud Command Line Interface**, and select **Uninstall**.
5. The uninstaller is started. Follow the instructions to finish the uninstallation.

## Uninstalling on Linux and macOS
{: #uninstall-cli-linux-macos}

The uninstallation steps are different depending on the version of the CLI that is installed.

To determine your {{site.data.keyword.cloud_notm}} CLI version, run:
```
ibmcloud -v
```
{: codeblock}

To uninstall versions earlier than `0.9.0`, run the following commands:
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Clean up the autocompletion scripts, if you configured them. For more information, see [Enabling shell autocompletion](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

To uninstall versions `0.9.0` and later, run the following command:
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Clean up any custom autocompletion scripts, if you configured them. For more information, see [Enabling shell autocompletion](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
