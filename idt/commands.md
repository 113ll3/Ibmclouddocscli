---

copyright:

   years: 2017, 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}  

# {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) commands
{: #idt-cli}

Version: 1.2.0
Released: Mar 8, 2018

As of May 2018 the {{site.data.keyword.Bluemix_notm}} CLI commands have changed from `bluemix` and `bx` to `ibmcloud`. However you can still use the `bluemix` and `bx` CLI commands until they are deprecated at a later date.
{: tip}

Use the following {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) commands to create a project, deploy, debug, and test it.

- [build](#build): Build the project in a local container
- [code](#code): Download the code from a project
- [console](#console): Opens the IBM Cloud console for a project
- [create](#create): Creates a new project and gives you the option to add services
- [debug](#debug): Debug your application in a local container
- [delete](#delete): Deletes a project from your space
- [deploy](#deploy): Deploy an application to IBM Cloud
- [enable](#enable): Add IBM Cloud files to an existing project
- [get-credentials](#get-credentials): Gets credentials that are required by the project to enable use of bound services
- [help](#help): Help on IDT syntax and arguments
- [list](#list): List all IBM Cloud projects in a space
- [run](#run): Run your application in a local container
- [shell](#shell): Open a shell into a local container
- [status](#status): Check the status of the containers that are used by the CLI
- [stop](#stop): Stop a container
- [test](#test): Test your application in a local container
- [view](#view): View the apps deployed URL for testing and viewing
- [compound commands](#compound): Run multiple commands in one command line statement



## build
{: #build}

You can build your application by using the `build` command. The `test`, `debug`, and `run` commands expect to find a compiled project so you must first run a `build` operation beforehand.  

The `build-cmd-debug` configuration element is used to build the application for all uses except for `run`. You build your application for debugging by specifying the command line option `--debug`.  The `build-cmd-run` configuration element is used when you are building the application for use with the `run` command.

To build with multiple containers, either your project must contain a [Compose](https://docs.docker.com/compose/overview/) file, which is specified in the `cli-config.yml`, or you can use the `dockerfile-tools` command parameter to provide one. See the [Compose File](/docs/apps/projects/compose_file.html) for more information.

Run the following command in your current project directory to build your application:  

```
ibmcloud dev build [--debug]
```
{: codeblock}


[Build command parameters](#command-parameters)


## code
{: #code}

Use the `code` command to download a previously created project with application template code and configuration files for the {{site.data.keyword.Bluemix_notm}}.  This is useful when you need to extract a second copy of a project that you have created.

Run the following command to download the code from a specified project.

```
ibmcloud dev code <projectName>
```
{: codeblock}


## console
{: #console}

Use the `console` command to open a web browser to your application's web console on IBM Cloud.  You can run the `ibmcloud dev console` command from inside your project's folder, and the CLI attempts to find a matching project on the IBM Cloud that has the same project ID as the current directory. If the system is not able to find a matching name, it opens the Web and Mobile dashboard on IBM Cloud instead of the specific project.

You can provide a project name and the CLI skips matching based on folder/application name. In this case, the CLI opens the named project's console in a web browser.  

Run the following command to open a web browser to your application's web console.

```
ibmcloud dev console [projectName]
```
{: codeblock}


## create
{: #create}

Create a project, prompting for all information, including resource type, language, starter kit, and DevOps Toolchain options. The project is created in the current directory.

To create a project in the current directory and to associate services with it, run the following command:

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

You can debug your application through the `debug` command. A build must first be completed against the project by using the build command with the `--debug` argument. When you start the `debug` command, a container is started which provides a debug port or ports as defined by the `container-port-map-debug` value in the cli-config.yml or specified on the command line. Connect your favorite debugging tool to the port or ports, and you can debug your application as normal.

First, compile your project:

```
ibmcloud dev build --debug
```
{: codeblock}

To begin, run the following command in your current project directory to debug your application:

```
ibmcloud dev debug
```
{: codeblock}

To debug, attach your debug tool to the specified port.

To exit the debug session, use `CTRL-C`.


### debug command parameters
{: #debug-parameters}

The following parameters are exclusive to the `debug` command and assist with debugging an application. There are [additional parameters](#command-parameters) shared with other commands.

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

* Parameter that is used to specify a command to invoke debug in the tools container. Use this parameter if the `build-cmd-debug` starts your application in debug.
* Usage: `ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Use the `delete` command to remove projects from your {{site.data.keyword.Bluemix}} space. You can run the command without parameters to list available projects and select the project from the numbered list to delete. Project code and directories are not removed from your local disk space.

Run the following command to delete your project from {{site.data.keyword.Bluemix}}:

```
ibmcloud dev delete <projectName>
```
{: codeblock}


**Note:** {{site.data.keyword.Bluemix}} services are **not** removed.


## deploy
{: #deploy}

You can deploy an application as a Cloud Foundry application or as a container.

To deploy as a Cloud Foundry application to {{site.data.keyword.Bluemix}}, a `manifest.yml` file must be present in your project's root directory.

To deploy an application as a container, you must locally install [Kubernetes](https://kubernetes.io/) and [Helm](https://github.com/kubernetes/helm). Be sure that the Helm client version is not newer than the Helm server version. You can find both of these by running `helm version`. We recommend using v2.4.2 for the client version.

In the `cli-config.yml`, you can choose to define the location of a Helm chart in the `chart-path` property, set the `deploy-target` element to `container`, and configure the `deploy-image-target` as shown in the example. The `deploy-image-target` element in the `cli-config.yml` is used instead of the `repository` and `tag` elements in the `chart/values.yml` file. To deploy to {{site.data.keyword.Bluemix}} specifically, set the configuration element `ibm-cluster` to the name of the Kubernetes cluster you have created in {{site.data.keyword.Bluemix}} as described in the [Tutorial: Creating clusters](/docs/containers/cs_tutorials.html#cs_cluster_tutorial).

For more information on provisioning, configuring, and deploying to a Kubernetes cluster, see the [Deploy a scalable web application on Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes) tutorial.

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

If you do not define these in the cli-config.yml, you then must deploy with the parameter `-t container` and you will be prompted for all of the other values.

Run the following command in your current project directory to build your application:  

```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current project directory to deploy your project:

```
ibmcloud dev deploy
```
{: codeblock}


### deploy command parameters
{: #deploy-parameters}

The following parameters can be used with the `deploy` command or by updating the project's `cli-config.yml` file directly. There are [additional parameters](#command-parameters) shared with other commands.

#### `chart-path`
{: #chart-path}

* Parameter used for a container deployment to specify the location of the Helm chart used for the deployment.
* Usage `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Parameter optionally used to indicate the type of deployment to be completed.  The default deployment type is buildpack.
* Usage `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter used with a container deployment as the target image name for the deployment (e.g. to tag to a Docker registry).  The value must not include a version, for example: image-name:{version} because the version is automatically incremented and appended by `deploy`.
* Usage `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parameter optionally used to define the name of the Kubernetes cluster for a container deployment to {{site.data.keyword.Bluemix}}
* Usage `ibmcloud dev deploy --ibm-cluster [cluster-name]`


## enable
{: #enable}

Enable an existing project for {{site.data.keyword.Bluemix_notm}} deployment. The `enable` command attempts to automatically detect the language of an existing project and then prompt for necessary additional information. This generates and adds files that can be used for local Docker containers, CloudFoundry deployment, or Kubernetes/Container Deployment.

Run the following command to enable an existing project in the current directory for {{site.data.keyword.Bluemix_notm}} deployment:

```
ibmcloud dev enable
```
{: codeblock}

The presence of necessary files provides project language detection for a valid project structure.  

* The presence of a `package.json` file identifies a Node.js project.
* The presence of a `package.swift` file identifies a Swift project.
* The presence of either a `setup.py` or `requirements.txt` file identifies a Python project.
* The presence of either a `pom.xml` or `build.gradle` file identifies a Java project.
	* The presence of a `pom.xml` identifies a Maven project.
	* The presence of a `build.gradle` identifies a Gradle project.

Optionally, you can also override the detected project language using the `--language` argument.  However, only valid and complete projects are supported. The enable command does not modify your source code.

Language options include:
* node
* swift
* python
* java-ee (interpreted as Java - Java EE)
* java-mp (interpreted as Java - Java MicroProfile)
* java-spring (interpreted as Java - Spring Framework)

Files created using the `ibmcloud dev enable` command that have naming conflicts with existing files in the project folder are saved with a `.merge` file extension.  

### enable command parameters
{: #enable-parameters}

The following parameters can be used with the `enable` command or by updating the project's `cli-config.yml` file directly. There are [additional parameters](#command-parameters) shared with other commands.

#### `language`
{: #enable-language}

* Parameter used to specify the language of the project to be enabled.
* Usage `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parameter used to force re-enabling an already enabled project.
* Usage `ibmcloud dev enable -f|--force`


## get-credentials
{: #get-credentials}

Gets credentials required by the project to enable the use of bound services.


## help
{: #help}

By default, if no action or arguments are passed in, or if the 'help' action is provided, this command shows a general "Help" text. General help displayed includes a description of the base arguments as well as a listing of the available actions.  

Run the following command to display General help information:

```
ibmcloud dev help
```
{: codeblock}


## list
{: #list}

You can list all {{site.data.keyword.Bluemix_notm}} projects in a space.

Run the following command to list your projects:

```
ibmcloud dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
ibmcloud dev edit
```
{: codeblock}
-->


## run
{: #run}

You can run your application through the `run` command. A build must first be completed against the project by using the `build` command. When you invoke the `run` command, the run container is started and exposes the ports as defined by the `container-port-map` parameter. The `run-cmd` parameter can be used to invoke the application if the run container Dockerfile does not contain an entry point to complete this step.

In order to run with multiple containers, either your project should contain a [Compose](https://docs.docker.com/compose/overview/) file, specified in the `cli-config.yml`, or you can use the `dockerfile-run` command parameter to provide one. See the [Compose File](/docs/apps/projects/compose_file.html) for more information.

First, compile your project:

```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current project directory to start your application:

```
ibmcloud dev run
```
{: codeblock}

To exit the session use `CTRL-C`.


### run command parameters
{: #run-parameters}

The following parameters are exclusive to the `run` command and
assist with managing your application within the run container.
There are [additional parameters](#command-parameters) shared with other commands.

#### `container-name-run`
{: #container-name-run2}

* Container name for the run container.
* Usage: `ibmcloud dev run --container-name-run [<projectName>]`

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
* If you intend to run with multiple containers, this should be a Compose file.
* To use multiple compose files, surround a comma-delimited list of the file names with double quotes.
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

You can open the shell inside the run or tools container with the `shell` command.

By simply running this command

```
ibmcloud dev shell
```

the {{site.data.keyword.dev_cli_short}} CLI will open an interactive shell into the application's docker container. The default target container for the shell command is defined by the `container-shell-target` value in the `cli-config.yml` file, where the valid values are `run` or `tools`. If this value is not defined or an invalid value is specified, then the `shell` command will target the `tools` container by default. The shell command opens the container to the directory specified by the `WORKDIR` instruction in the corresponding Dockerfile. If `WORKDIR` is not listed in the Dockerfile, the container root is used as the working directory. See [this reference](https://docs.docker.com/engine/reference/builder/#workdir) for more information.

Alternatively, you can decide to pass either `run` or `tools` as an argument to the command and that container will be brought up and the shell will be opened for that container. Similarly, you can use the `container-name` parameter to pass the name of the container into which you wish to shell. However, this flag should be reserved for when no containers are running. The `run` and `tools` arguments are more flexible and allow you to switch between containers when one is currently running. For example, if the tools container is running and you execute `ibmcloud dev shell run`, the `tools` container will be stopped and the `run` container will be started, and vice versa.

If the target `run` or `tools` container is not already running when you execute the `shell` command, then the target container will be started. However, the default `Cmd` or `Entrypoint` in the Dockerfile will be overridden to launch directly into the shell instead of starting the server process. This allows you to start the `run` or `tools` container, and manually start the server with your own arbitrary or custom commands.


You can also specify the shell executable you wish to open by using the `container-shell` parameter. By default, `/bin/sh` is used. If you'd prefer to use the bash shell, then specify the `container-shell` value to be `/bin/bash`; however, keep in mind that bash is not automatically available across all Linux variants.

Any additional arguments you pass to the command beyond the flags will be parsed as the command to be run when the shell is opened. If you provide a command to be run, the shell inside the container will exit upon running the command and return to your terminal.

For example, you can run the Linux `ls` command inside of the tools container shell by invoking `ibmcloud dev shell tools ls`.   You can also specify additional flags to be passed into the shell command execution by wrapping the arguments in quotes, such as `ibmcloud dev shell "ls -la"`.

### shell command parameters
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Name of the container into which you wish to shell.
* Usage: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Specifies which shell to run inside the container (default is /bin/sh)
* Usage: `ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

You can query the status of the containers that are used by the {{site.data.keyword.dev_cli_short}} CLI as defined by `container-name-run` and `container-name-tools`.

Run the following command in your current project directory to check container status:

```
ibmcloud dev status
```
{: codeblock}


[Status command parameters](#command-parameters)


## stop
{: #stop}

You can stop your containers through the `stop` command.

To stop the tools and run containers as defined in your `cli-config.yml` file, run:

```
ibmcloud dev stop
```
{: codeblock}

To stop a container that is not defined in the `cli-config.yml` file, you can specify an extra command line parameter to override it.  If no containers are specified in the `cli-config.yml` file or on the command line, the stop command simply returns.

### stop command parameters
{: #stop-parameters}

The following parameters are used for the `stop` command. There are [additional parameters](#command-parameters) shared with other commands.

#### `container-name-run`
{: #container-name-run}

* Container name for the run container.
* Usage: `ibmcloud dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* Container name for the tools container.
* Usage: `ibmcloud dev stop --container-name-tools [<projectName>]`



## test
{: #test}

You can test your application through the `test` command. A build must first be completed against the project by using the `build --debug` command. The tools container is then used to invoke the `test-cmd` for the application.

First, compile your project:

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

The following parameter is exclusive to the `test` command.  There are [additional parameters](#command-parameters) shared with other commands.

#### `test-cmd`
{: #test-cmd}

* Parameter that is used to specify a command to test code in the tools container.
* Usage: `ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

You can view the URL to which your application is deployed through the `view` command. Run this command in the root directory of the application you wish to view. The `view` command will also open the URL in your default browser.

For applications deployed to Cloud Foundry, the URL consists of the application's hostname and the application's domain.

For applications deployed to Kubernetes, the URL consists of the IP address of the node to which it is deployed and the public port. If the command determines that the app was deployed to Kubernetes, the CLI tool will prompt for confirmation. If you specify that the application was not actually deployed to Kubernetes, then the Cloud Foundry URL is shown. If you expected the command to show the URL for a Kubernetes-deployed application and it did not, then either ensure that the `cli-config.yml` contains an entry for `chart-path` or supply it via command line as shown [here](#chart-path).

Run the following command to view your application:

```
ibmcloud dev view
```
{: codeblock}

### view command parameters
{: #view-parameters}

The following parameters are exclusive to the `view` command.

#### `deploy-target`

* Parameter optionally used to indicate the type of deployment to bypass the prompt
* Usage `ibmcloud dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Parameter that is used to specify not to open the browser.
* Usage: `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Root of the project to append to the Kubernetes app URL
* Usage: `ibmcloud dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* Parameter optionally used to define the name of the Kubernetes cluster when targeting a container deployment
* Usage `ibmcloud dev view --ibm-cluster [cluster-name]`


## compound commands
{: #compound}

You can run multiple commands in one command line statement by separating the IDT commands with the `/` delimeter. Additional command line flags can be specified after you specify the compound commands.  The following commands are examples of how you can use compound commands:

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

All flags must trail the final command and will be applied to all commands to which that flag is associated. In the example above, the `--trace` flag is applicable to all 3 commands, but the `-t` is only applicable to the final 2 commands, and so will not be applied to the `build` command.

These are the commands that may be used with this feature:
`build, debug, deploy, get-credentials, run, stop, test, view`

If one command fails for any reason, the subsequent commands will not be executed. If any commands follow `debug` or `run`, execution will only continue if `debug` or `run` is terminated by means other than killing the process from the current terminal window. `CTRL+C` will kill the process and not run the subsequent commands. For example, you can execute `ibmcloud dev stop` from another terminal window to stop the running container and continue execution to the next command.


## Parameters for build, debug, run, and test
{: #command-parameters}

The following parameters can be used with the `build|debug|run|test` commands or by updating the project's `cli-config.yml` file directly. Extra parameters are available for the [`debug`](#debug-parameters) and [`run`](#run-parameters) commands.

**Note**: Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.

#### `config-file`  
{: #config-file}

* Specify a cli-config.yml file to use for a command.
* Usage: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Container name for the run container.
* Usage: `ibmcloud dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Container name for the tools container.
* Usage: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

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
* As a best practice and to prevent unexpected results, you should build and run using the same mount settings.
* Usage: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you should build and debug using the same mount settings.
* Usage: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parameter that is used to specify a command to build code for all use but DEBUG.
* Usage: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev <build|debug|run|test> --trace`
