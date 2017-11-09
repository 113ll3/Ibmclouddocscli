---



copyright:

  years: 2015，2017

lastupdated: "2017-01-12"



---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# (Deprecated) Development mode CLI
{: #devmodecli}


**This CLI has been deprecated:** Instead of using the Development mode (dev_mode) CLI, use IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}  or DevOps Web IDE. You can continue to use the dev_mode CLI until 30 June 2016.

With {{site.data.keyword.Bluemix_notm}} development mode command line interface (dev_mode CLI), you can update your apps while your apps are running in the cloud. dev_mode CLI is built as a cf CLI plug-in and supports both Liberty and IBM Node.js apps.
{: shortdesc}


You can do the following tasks with the dev_mode CLI:
- Switch your app between dev mode and normal mode.
- Update application files incrementally without a new push.
- Start, stop, or restart your app in the existing container.

## Installing the dev_mode plug-in
**Prerequisite:** Before you begin, install the Cloud Foundry CLI. See [Start coding with Cloud Foundry command line interface](https://github.com/cloudfoundry/cli) for details.


Use one of the following methods to install the dev_mode command line tool:
- Install locally.
  1. Download the dev_mode plug-in for your platform from [{{site.data.keyword.Bluemix_notm}}  CLI Plugin Repository ![External link icon](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net){: new_window}.
  2. Go to the folder that the dev_mode plug-in is saved, and install the dev_mode plug-in by using the cf install-plugin command. For example:

        ```
        cf install-plugin dev_mode-linux64
        ```

- Install from the {{site.data.keyword.Bluemix_notm}}  CLI repository.
  1. Add the bluemix-repo repository into the Cloud Foundry CLI repositories by using the following command:

        ```
        cf add-plugin-repo bluemix-repo http://plugins.ng.bluemix.net
        ```

  2. Type cf repo-plugins. The dev_mode plug-in appears in the bluemix-repo repository.

		```
        cf repo-plugins
        ```

  3. Install the dev_mode plug-in into the Cloud Foundry CLI plug-ins by using the following command:

        ```
        cf install-plugin dev_mode -r bluemix-repo
        ```

## Viewing dev_mo {{site.data.keyword.Bluemix_notm}}  

To display all dev_mode CLI commands, use the following command:

```
cf plugins
```

## dev_mode CLI commands index
{: #dev_mode_cmds_index}

Use the index in the following table to refer to the frequently used dev_mode CLI commands:

<table summary="dev_mode commands index">
<caption>Table 1. dev_mode commands</caption>
 <thead>
 <th colspan="4">dev_mode commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[help](#help)</td>
 <td>[mode](#mode)</td>
 <td>[status](#status)</td>
 <td>[update-file](#update_file)</td>
 </tr>
 <tr>
 <td>[delete-file](#delete_file)</td>
 <td>[start-inplace](#start_inplace)</td>
 <td>[stop-inplace](#stop_inplace)</td>
 <td>[restart-inplace](#restart_inplace)</td>
 </tr>
  </tbody>
 </table>


## help
{: #help}

Display help about a command.

```
cf help <commandName>
```


## mode
{: #mode}

Change the app mode.

```
cf mode <appName> <dev|normal>
```
<strong>Command options</strong>:

   <dl>
   <dt>dev</dt>
   <dd>Development mode.</dd>
   <dt>normal</dt>
   <dd>Production mode.</dd>
   </dl>


## status
{: #status}

Show the app mode and runtime status.
```
cf status <appName>
```



## update-file
{: #update_file}

Update application files in the cloud.

```
cf update-file <remotePath> <localPath> [command_options]
```


<strong>Command options</strong>:

   <dl>
   <dt>expand</dt>
   <dd>Indicate whether the uploaded files must be extracted from the zip file.</dd>
   <dt>restart</dt>
   <dd>Restart the app runtime after the files are updated.</dd>
   </dl>



## delete-file
{: #delete_file}

Delete application files in the cloud.

```
cf delete-file <remotePath> [command_options]
```


<strong>Command options</strong>:
 <dl>
   <dt>restart</dt>
   <dd>Restart the app runtime after the files are updated.</dd>
  </dl>


## start-inplace
{: #start_inplace}
Start the app in the existing container.

```
cf start-inplace <appName>
```



## stop-inplace
{: #stop_inplace}
Stop the app in the existing container.

```
cf stop-inplace <appName>
```



## restart-inplace
{: #restart_inplace}

Restart the app in the existing container.

```
cf restart-inplace <appName>
```



# Related Links
{: #rellinks}

## Related Links
{: #general}
* [Development mode CLI ![External link icon](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/repository.html#cf-plugins){:new_window}
* [DevOps Web IDE ![External link icon](../../../icons/launch-glyph.svg)](https://hub.jazz.net/docs/deploy/){:new_window}
