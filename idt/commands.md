---

copyright:
   years: 2017, 2019
lastupdated: "2019-04-15"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer plugin cli, dev plugin commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# {{site.data.keyword.dev_cli_notm}} CLI plug-in (ibmcloud dev) commands
{: #idt-cli}

Version: 2.1.18
Released: 28 March 2019

As of May 2018, the {{site.data.keyword.cloud}} CLI commands `bluemix` and `bx` are now `ibmcloud`. However, you can still use the `bluemix` and `bx` CLI commands until they're removed later.
{: tip}

Use the following {{site.data.keyword.dev_cli_notm}} CLI (`ibmcloud dev`) commands to create an application, manage, deploy, debug, and test it.

- [build](#build): Build the application in a local container.
- [code](#code): Download the code for an application.
- [console](#console): Opens the {{site.data.keyword.cloud_notm}} console for an application.
- [create](#create): Creates a new application and gives you the option to add services.
- [debug](#debug): Debug your application in a local container.
- [delete](#delete): Deletes an application from your space.
- [deploy](#deploy): Deploy an application to {{site.data.keyword.cloud_notm}}.
- [diag](#diag): Displays version information about installed dependencies.
- [edit](#edit): Add or remove services from an existing application.
- [enable](#enable): Update an existing application for use with {{site.data.keyword.cloud_notm}} Developer Tools.
- [get-credentials](#get-credentials): Gets credentials that are required by the application. to enable use of connected {{site.data.keyword.cloud_notm}} services.
- [help](#help): Help on the CLI syntax and arguments.
- [list](#list): List all {{site.data.keyword.cloud_notm}} applications in a resource group.
- [run](#run): Run your application in a local container.
- [shell](#shell): Open a shell into a local container.
- [status](#status): Check the status of the containers that are used by the CLI.
- [stop](#stop): Stop a container.
- [test](#test): Test your application in a local container.
- [view](#view): View the deployed URL of the application for testing and viewing.
- [compound commands](#compound): Run multiple commands in a single command line statement.

## build
{: #build}

If you're using Windows&trade;, you must be running Windows&trade; 10 Pro or later.

You can build your application by using the `build` command. The `test`, `debug`, and `run` commands expect to find a compiled application so you must run a `build` operation beforehand.

The `build-cmd-debug` configuration element is used to build the application for all uses except for `run`. You build your application for debugging by specifying the command line option `--debug`. The `build-cmd-run` configuration element is used when you're building the application for use with the `run` command.

To build with multiple containers, your application must have a [Compose](https://docs.docker.com/compose/overview/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") file, which is specified in the `cli-config.yml`, or you can use the `dockerfile-tools` command parameter to provide one.

Run the following command in your current application directory to build your application:  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

Use the `code` command to download a previously created application with application template code and configuration files for the {{site.data.keyword.cloud_notm}}. You can use this command when you need to extract a second copy of an application.

Run the following command to download the code from a specified application.
```
ibmcloud dev code <applicationName>
```
{: codeblock}

## console
{: #console}

Use the `console` command to open a web browser to your application's web console on {{site.data.keyword.cloud_notm}}. You can run the `ibmcloud dev console` command from inside your application's folder. The CLI attempts to find a matching application on the {{site.data.keyword.cloud_notm}} that has the same application ID as the current directory. If the system isn't able to find a matching name, it opens the Web and Mobile dashboard on {{site.data.keyword.cloud_notm}} instead of the specific application.

You can provide an application name and the CLI skips matching based on the folder or application name. In this case, the CLI opens the named application's console in a web browser.  

Run the following command to open a web browser to your application's web console.
```
ibmcloud dev console [applicationName]
```
{: codeblock}

## create
{: #create}

Create an application, prompting for all information, including resource type, language, starter kit, and DevOps Toolchain options including IBM Cloud Foundry or Cloud Foundry Enterprise Environment, and Kubernetes. The application is created in the current directory.

To create an application in the current directory and to associate services with it, run the following command:
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can debug your application through the `debug` command. A build must first be completed against the application by using the build command with the `--debug` argument. When you start the `debug` command, a container is started which provides a debug port or ports as defined by the `container-port-map-debug` value in the cli-config.yml or specified on the command line. Connect your favorite debugging tool to the port or ports, and you can debug your application as normal.

First, compile your application:
```
ibmcloud dev build --debug
```
{: codeblock}

To begin, run the following command in your current application directory to debug your application:
```
ibmcloud dev debug
```
{: codeblock}

To debug, attach your debug tool to the specified port.

To exit the debug session, use `CTRL-C`.

### debug command parameters
{: #debug-parameters}

The following parameters are exclusive to the `debug` command and assist with debugging an application. There are [additional parameters](#command-parameters) that are shared with other commands.

#### `container-port-map-debug`
{: #port-map-debug}

* Port mappings for the debug port. The first value is the port to use in the host OS, the second is the port in the container [host-port:container-port].
* Usage: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parameter that is used to build code for DEBUG.
* Usage: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parameter that is used to specify a command to start debug in the tools container. Use this parameter if the `build-cmd-debug` starts your application in debug.
* Usage: `ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

Use the `delete` command to remove applications from your {{site.data.keyword.cloud_notm}} space. You can run the command without parameters to list available applications and select the application from the numbered list to delete. Application code and directories aren't removed from your local disk space.

Run the following command to delete your application from {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete <applicationName>
```
{: codeblock}

{{site.data.keyword.cloud_notm}} services aren't removed.
{: note}

## deploy
{: #deploy}

You can deploy an application as a Cloud Foundry application or as a container.

Before you deploy a Cloud Foundry application to {{site.data.keyword.cloud_notm}}, a `manifest.yml` file must be present in your application's root directory.

Before you deploy an application as a container, you must locally install [Kubernetes](https://kubernetes.io/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") and [Helm](https://github.com/helm/helm){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon"). The Helm client version must not be newer than the Helm server version. You can find both by running `helm version`. It is recommended to use v2.4.2 for the client version.

To deploy your application on Kubernetes, you must either specify the `deploy-target` as `container` in the `cli-config.yml` or use the parameter `-t container`.

Other parameters needed to configure Kubernetes deployment can also be specified in the `cli-config.yml` by using command line arguments. If you don't define these parameters in the `cli-config.yml`, you must deploy with the parameter `-t container`. Then, you're prompted for all of the other values.

```yaml
chart-path: "chart/myapplication"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

In the `cli-config.yml`, you can choose to define the location of a Helm chart in the `chart-path` property and configure the `deploy-image-target` as shown in the example. The `deploy-image-target` element in the `cli-config.yml` is used instead of the `repository` and `tag` elements in the `chart/values.yml` file. To deploy to {{site.data.keyword.cloud_notm}} specifically, set the configuration element `ibm-cluster` to the name of the Kubernetes cluster that you created in {{site.data.keyword.cloud_notm}}.

Run the following command in your current application directory to build your application:  
```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current application directory to deploy your application:
```
ibmcloud dev deploy
```
{: codeblock}

### deploy to {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

You can deploy to an {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment. To do so, configure your local environment for this environment by using `ibmcloud target --cf`, and then choose the correct environment from that list. You can then use the `deploy` command as you would for {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### deploy command parameters
{: #deploy-parameters}

The following parameters can be used with the `deploy` command or by updating the application's `cli-config.yml` file directly. There are [additional parameters](#command-parameters) that are shared with other commands.

#### `chart-path`
{: #chart-path}

* Parameter used for a container deployment to specify the location of the Helm chart used for the deployment.
* Usage `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Parameter optionally used to indicate the type of deployment to be completed. The default deployment type is buildpack.
* Usage `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter that is used with a container deployment as the target image name for the deployment. The value must not include a version. For example: image-name:{version} because the version is automatically incremented and appended by `deploy`.
* Usage `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parameter optionally used to define the name of the Kubernetes cluster for a container deployment to {{site.data.keyword.cloud_notm}}
* Usage `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Parameter optionally used to define the host name of the application when you deploy to Cloud Foundry.
* Usage `ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* Parameter optionally used to define the domain of the application when you deploy to Cloud Foundry.
* Usage `ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

This command is used as a diagnostic to display the version information of installed dependencies for the {{site.data.keyword.dev_cli_notm}} CLI. This is helpful to determine whether you're missing any dependencies or to help in debugging problems.

Run the following command to display the versions of your installed dependencies:
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

Edit your application with options such as connecting it with an application already in {{site.data.keyword.cloud_notm}}, managing the {{site.data.keyword.cloud_notm}} services of the application, and its {{site.data.keyword.cloud_notm}} Toolchain that deploys to IBM Cloud Kubernetes, Cloud Foundry, or Cloud Foundry Enterprise Environment. With a local application that is connected to an application in {{site.data.keyword.cloud_notm}}, use `edit` to add new services, connect and disconnect existing services, or remove existing services from your account. Additionally, you can create or view an {{site.data.keyword.cloud_notm}} Toolchain for the application. Run the following command in the root of your application directory:
```
ibmcloud dev edit
```
{: codeblock}

If you have no existing services on your account, this command shows you a list of service groups from which you can select a service to connect to your application.

However, if you have any existing services on your account, this command shows you a list of those services and whether each service is connected to the application or not.

* A connected service gives you options to either disconnect the service from your application or delete the service from your account, disconnecting it from all applications to which it's connected.

* A disconnected service gives you options to either connect that service to your application or delete the service from your account. Connecting an existing service also downloads files, such as credentials or source code to begin using that service.

You can also add a new service to your application, where you are guided through service selection prompts and download additional files such as credential files or source code to begin using the new service.

## enable
{: #enable}

Enable an existing application for {{site.data.keyword.cloud_notm}} deployment. The `enable` command attempts to automatically detect the language of an existing application and then prompt for necessary additional information. This generates and adds files that can be used for local Docker containers, Cloud Foundry deployment, Cloud Foundry Enterprise Environment deployment, or Kubernetes Container deployment. All deployment environments can be utilized through a manual `deploy` or by using a DevOps Toolchain.

When logged in to {{site.data.keyword.cloud_notm}}, you can choose to connect this local application with an application that is already in {{site.data.keyword.cloud_notm}} or create a new {{site.data.keyword.cloud_notm}} application. To take advantage of {{site.data.keyword.cloud_notm}} features such as services and DevOps Toolchains, an application in {{site.data.keyword.cloud_notm}} is necessary. When an {{site.data.keyword.cloud_notm}} app is created for an app that is cloned from a Git repository, the {{site.data.keyword.cloud_notm}} app includes this repository in its configuration. 

`Enable` is a Beta feature. If you have trouble enabling your application, our [troubleshooting page](/docs/cli/ts_createapps.html#troubleshoot) has help for you. In particular, `enable` isn't intended for mobile applications or frameworks. For complex applications that produce several deployable assets, each component of the application must be enabled individually. 

Run the following command to enable an existing application in the current directory:
```
ibmcloud dev enable
```
{: codeblock}

The presence of necessary files provides application language detection for a valid project structure.  

* The presence of a `package.json` file identifies a Node.js application.
* The presence of a `package.swift` file identifies a Swift application.
* The presence of either a `setup.py` or `requirements.txt` file identifies a Python application.
* The presence of either a `pom.xml` or `build.gradle` file identifies a Java application.
	* The presence of a `pom.xml` identifies a Maven application.
	* The presence of a `build.gradle` identifies a Gradle application.

Optionally, you can also override the detected application language by using the `--language` argument. Only valid and complete applications are supported. The enable command doesn't modify your source code.

### enable language options
{: #enable-language-options}

Language options include:
* node
* swift
* python
* java-ee (interpreted as Java&trade; - Java&trade; EE)
* java-mp (interpreted as Java&trade; - Java&trade; MicroProfile)
* java-spring (interpreted as Java&trade; - Spring Framework)

Files that are created by using the `ibmcloud dev enable` command, and have naming conflicts with existing files in the application folder, are saved with a `.merge` file extension.  

### enable command parameters
{: #enable-parameters}

The following parameters can be used with the `enable` command or by updating the application's `cli-config.yml` file directly. There are [additional parameters](#command-parameters) that are shared with other commands.

#### `language`
{: #enable-language}

* Parameter used to specify the language of the application to be enabled.
* Usage `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parameter used to force reenabling an already enabled application.
* Usage `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Parameter to prevent creating an app in {{site.data.keyword.cloud_notm}} while creating the enablement files locally.
* Usage `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

Get credentials are required by the application to enable the use of connected services.

## help
{: #help}

By default, if no action or arguments are passed in, or if the 'help' action is provided, this command shows a general "Help" text. General help displayed includes a description of the base arguments and a listing of the available actions.  

Run the following command to display General help information:
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

You can list all {{site.data.keyword.cloud_notm}} applications in a resource group.

Run the following command to list your applications:
```
ibmcloud dev list
```
{: codeblock}

## run
{: #run}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can run your application through the `run` command. A build must first be completed against the application by using the `build` command. When you run the `run` command, the run container starts and exposes the ports as defined by the `container-port-map` parameter. The `run-cmd` parameter is used to invoke the application if the run container `Dockerfile` doesn't contain an entry point to complete this step.

In order to run with multiple containers, either your application must contain a [Compose](https://docs.docker.com/compose/overview/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") file, which is specified in the `cli-config.yml`, or you can use the `dockerfile-run` command parameter to provide one.

First, compile your application:
```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current application directory to start your application:
```
ibmcloud dev run
```
{: codeblock}

To exit the session use `CTRL-C`.

### run command parameters
{: #run-parameters}

The following parameters are exclusive to the `run` command and
assist with managing your application within the run container.
There are [additional parameters](#command-parameters) that are shared with other commands.

#### `container-name-run`
{: #container-name-run2}

* Container name for the run container.
* Usage: `ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* Location in the container to share on run.
* Usage: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Location on the host system to share in the container on run.
* Usage: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile for the run container.
* If you intend to run with several containers, this should be a Compose file.
* To use multiple compose files, surround a comma-delimited list of the file names with double quotation marks.
* Usage: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Usage: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Image to create from `dockerfile-run`.
* Usage: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parameter that is used to run code in the run container. Use this parameter if your image starts your application.
* Usage: `ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

If you're using Windows&trade;, you must be run Windows&trade; 10 Pro or later.

You can open the shell inside the run or tools container with the `shell` command.

By running the following command:
```
ibmcloud dev shell
```
{: codeblock}

The {{site.data.keyword.dev_cli_short}} CLI opens an interactive shell into the application's docker container. The default target container for the shell command is defined by the `container-shell-target` value in the `cli-config.yml` file, where the valid values are `run` or `tools`. If this value is not defined or an invalid value is specified, then the `shell` command targets the `tools` container by default. The shell command opens the container to the directory specified by the `WORKDIR` instruction in the corresponding Dockerfile. If `WORKDIR` is not listed in the Dockerfile, the container root is used as the working directory. See [this reference](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") for more information.

Alternatively, you can decide to pass either `run` or `tools` as an argument to the command and that container is brought up and the shell is opened for that container. Similarly, you can use the `container-name` parameter to pass the name of the container into which you want to shell. However, this flag should be reserved for when no containers are running. The `run` and `tools` arguments are more flexible and let you switch between containers when one is running. For example, if the tools container is running and you execute `ibmcloud dev shell run`, the `tools` container is stopped and the `run` container starts, and vice versa.

If the target `run` or `tools` container is not already running when you execute the `shell` command, then the target container is started. However, the default `Cmd` or `Entrypoint` in the Dockerfile is overridden to start directly into the shell instead of starting the server process. This allows you to start the `run` or `tools` container, and manually start the server with your own arbitrary or custom commands.

You can also specify the shell executable that you want to open by using the `container-shell` parameter. By default, `/bin/sh` is used. If you'd prefer to use the bash shell, then specify the `container-shell` value to be `/bin/bash`; however, keep in mind that bash is not automatically available across all Linux&trade; variants.

Any additional arguments that you pass to the command beyond the flags are parsed as the command to be run when the shell is opened. If you provide a command, the shell inside the container exits upon running the command and returns you to your terminal.

For example, you can run the Linux&trade; `ls` command inside of the tools container shell by invoking `ibmcloud dev shell tools ls`. You can also specify additional flags to be passed into the shell command execution by wrapping the arguments in quotation marks, such as `ibmcloud dev shell "ls -la"`.

### shell command parameters
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Name of the container into which you want to shell.
* Usage: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Specifies which shell to run inside the container (default is /bin/sh).
* Usage: `ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

If you are using Windows&trade;, you must be running Windows&trade; 10 Pro or later.

You can query the status of the containers that are used by the {{site.data.keyword.dev_cli_short}} CLI as defined by `container-name-run` and `container-name-tools`.

Run the following command in your current application directory to check container status:
```
ibmcloud dev status
```
{: codeblock}

[Status command parameters](#command-parameters)

## stop
{: #stop}

If you're using Windows&trade;, you must be run Windows&trade; 10 Pro or later.

You can stop your containers through the `stop` command.

To stop the tools and run containers as defined in your `cli-config.yml` file, run:
```
ibmcloud dev stop
```
{: codeblock}

To stop a container that isn't defined in the `cli-config.yml` file, you can specify an extra command line parameter to override it. If no containers are specified in the `cli-config.yml` file or on the command line, the stop command simply returns.

### stop command parameters
{: #stop-parameters}

The following parameters are used for the `stop` command. There are [additional parameters](#command-parameters) that are shared with other commands.

#### `container-name-run`
{: #container-name-run}

* Container name for the run container.
* Usage: `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* Container name for the tools container.
* Usage: `ibmcloud dev stop --container-name-tools [<applicationName>]`

## test
{: #test}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can test your application through the `test` command. A build must first be completed against the application by using the `build --debug` command. The tools container is then used to start the `test-cmd` for the application.

First, compile your application:
```
ibmcloud dev build --debug
```
{: codeblock}

Run the following command to test your application:
```
ibmcloud dev test
```
{: codeblock}

### test command parameters
{: #test-parameters}

The following parameter is exclusive to the `test` command. There are [additional parameters](#command-parameters) that are shared with other commands.

#### `test-cmd`
{: #test-cmd}

* Parameter that is used to specify a command to test code in the tools container.
* Usage: `ibmcloud dev test --test-cmd /the/test/command`

## view
{: #view}

You can view the URL to which your application is deployed through the `view` command. Run this command in the root directory of the application you want to view. The `view` command also opens the URL in your default browser.

For applications deployed to Cloud Foundry, the URL consists of the application's host name and the application's domain.

For applications deployed to Kubernetes, the URL consists of the IP address of the node to which it's deployed, and the public port. If the command determines that the application was deployed to Kubernetes, the CLI tool prompts for confirmation. If you specify that the application wasn't deployed to Kubernetes, then the Cloud Foundry URL is shown. If you expected the command to show the URL for a Kubernetes deployed application, ensure that the `cli-config.yml` contains an entry for `chart-path` or supply it through command line as shown [here](#chart-path).

Run the following command to view your application:
```
ibmcloud dev view
```
{: codeblock}

### view command parameters
{: #view-parameters}

The following parameters are exclusive to the `view` command.

#### `deploy-target`

* Parameter optionally used to indicate the type of deployment to bypass the prompt.
* Usage `ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* Parameter that is used to specify not to open the browser.
* Usage: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Root of the project to append to the Cloud Foundry and Kubernetes application URL.
* Usage: `ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parameter optionally used to define the name of the Kubernetes cluster when you target a container deployment.
* Usage `ibmcloud dev view --ibm-cluster [cluster-name]`

## compound commands
{: #compound}

You are able to run several commands in one command line statement by separating the {{site.data.keyword.cloud_notm}} developer tools commands with the `/` delimiter. Additional command line flags can be used after you specify the compound commands. The following commands are examples of how you can use compound commands:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

All flags must trail the final command and be applied to all commands to which that flag is associated. Using `ibmcloud dev build/deploy/view -t container --trace` as an example, the `--trace` flag is applied to all three commands, but the `-t` is only applicable to the final two commands, and won't be applied to the `build` command.

The following commands can be used with this feature:
`build, debug, deploy, get-credentials, run, stop, test, view`

If one command fails for any reason, the subsequent commands are not run.

If any commands follow `debug` or `run`, execution continues if `debug` or `run` is terminated by means other than killing the process from the current terminal window. `CTRL+C` kills the process and not run the subsequent commands. For example, you can run `ibmcloud dev stop` from another terminal window to stop the running container and continue execution to the next command.

## Parameters for build, debug, run, and test
{: #command-parameters}

The following parameters can be used with the `build|debug|run|test` commands or by updating the application's `cli-config.yml` file directly. Extra parameters are available for the [`debug`](#debug-parameters) and [`run`](#run-parameters) commands.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`  
{: #config-file}

* Specify a cli-config.yml file to use for a command.
* Usage: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Container name for the run container.
* Usage: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Container name for the tools container.
* Usage: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* Location on the host to share for build, debug, test.
* Usage: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Location in the container to share for build, debug, test.
* Usage: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Port mappings for the container. The first value is the port to use in the host OS, the second is the port in the container [host-port:container-port].
* Usage: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile for the tools container.
* Usage: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Image to create from `dockerfile-tools`.
* Usage: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Use this option to define mounts between the host system and the run container.
* The `host-path-run` and `container-path-run` values are inserted at the beginning of this list.
* As a best practice, and to prevent unexpected results, you can build and run by using the same mount settings.
* Usage: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you can build and debug by using the same mount settings.
* Usage: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parameter that is used to specify a command to build code for all use but DEBUG.
* Usage: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev <build|debug|run|test> --trace`
