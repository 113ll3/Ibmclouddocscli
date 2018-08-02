---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Uninstall {{site.data.keyword.Bluemix_notm}} CLI

Please see the following sections for instructions on how to uninstall {{site.data.keyword.Bluemix_notm}} on specific platforms.

## Uninstall on Windows

* Click `Start` button, and then select `Control Panel`
* In the pop-up window, click `Uninstall a program`
* In the pop-up application list, locate `IBM Cloud Command Line Interface`
* Right click `IBM Cloud Command Line Interface`, and select `Uninstall`
* The uninstaller will be launched. Follow the instructions to finish the uninstallation.

## Uninstall on Linux/macOS

### Prior to version `0.9.0`

* Open a terminal, and execute the following commands
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* Clean up autocompletion scripts, if you've configured them. For more details, refer to [Enable CLI Autocompletion](enable_cli_autocompletion.html).

### Version `0.9.0` and later

* Open a terminal, and execute the following command
  * `/usr/local/ibmcloud/uninstall`
* Clean up autocompletion scripts, if you've configured them. For more details, refer to [Enable CLI Autocompletion](enable_cli_autocompletion.html).
