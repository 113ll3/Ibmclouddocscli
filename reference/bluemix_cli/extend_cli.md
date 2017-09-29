---

copyright:

  years: 2015, 2017
lastupdated: "2017-08-20"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Extending {{site.data.keyword.Bluemix_notm}} CLI with plug-ins
{: #plug-ins}

{{site.data.keyword.Bluemix_notm}} CLI supports a plug-in framework to extend its capability. You can install a plug-in from a repository, a web URL, or install a plug-in binary locally. 

[{{site.data.keyword.Bluemix_notm}} CLI plug-ins repository](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![External link icon](../../../icons/launch-glyph.svg)is the official repository to host the plugins.

## Install a plugin from repository

* Look for the plug-in

  Use command 'bluemix plugin repo-plugins -r REPO_NAME' to look for a plugins in the repository.
  
  {{site.data.keyword.Bluemix_notm}} CLI has the official repository with name `Bluemix` configured by default. You can list the plug-ins in the official `Bluemix` repository as below.

  ```
  $ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   Bluemix CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            Bluemix Network Security Group plugin          0.1.1

  ```

* Install the plug-in

  Use 'bx plugin install PLUGIN_NAME -r REPO_NAME' to install the plugin, for example:

  ```
  $ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Install a plug-in locally

  Use command `bluemix plugin install LOCAL_FILE_NAME` to install a plugin-in binary in your local machine, for example

  ```
  $ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Install from a web URL

  Use command `bluemix plugin install URL` to install a plugin directly from a web URL, for example

  ```
  ~$ bluemix plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


For more commands to manage plug-ins, run `bluemix plugin` to see the help messages.