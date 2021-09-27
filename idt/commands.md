---

copyright:
   years: 2017, 2021
lastupdated: "2021-09-27"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer cli, dev commands, devtools, developer tools, dev tools, ic dev commands, ic dev deploy

subcollection: cli

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# {{site.data.keyword.dev_cli_notm}} commands (ibmcloud dev)
{: #idt-cli}

The {{site.data.keyword.cloud}} Command Line Interface includes the `ibmcloud dev` or `ic dev` {{site.data.keyword.dev_cli_short}} commands to create, manage, deploy, debug, and test applications.
{: shortdesc}

Run multiple commands in a single command-line statement by using [compound commands](#compound).
{: tip}

## build
{: #build}

If you're using Windows&trade;, you must be running Windows&trade; 10 Pro or later.

You can build your app by using the `build` command. The `test`, `debug`, and `run` commands expect to find a compiled app so you must run a `build` operation beforehand.

The `build-cmd-debug` configuration element is used to build the app for all uses except for `run`. You build your app for debugging by specifying the command-line option `--debug`. The `build-cmd-run` configuration element is used when you're building the app for use with the `run` command.

To build with multiple containers, your app must have a [Compose](https://docs.docker.com/compose/overview/){: external} file, which is specified in the `cli-config.yml`, or you can use the `dockerfile-tools` command parameter to provide one.

Run the following command in your current app directory to begin building:  
```
ibmcloud dev build [--debug]
```
{: codeblock}

### build command parameters
{: #build-parameters}

The following parameters can be used with the `build` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #build-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev build --config-file cli-config.yml`

#### `build-cmd-run`
{: #build-build-cmd-run}

* Parameter that is used to specify a command to build code for all use except DEBUG.
* Usage: `ibmcloud dev build --build-cmd-run [some.build.command]`

#### `container-name-tools`  
{: #build-container-name-tools1}

* Container name for the tools container.
* Usage: `ibmcloud dev build --container-name-tools [<appName>]`

#### `container-path-tools`
{: #build-container-path-tools}

* Location in the container to share for build, debug, test.
* Usage: `ibmcloud dev build --container-path-tools [/path/for/build]`

#### `container-mounts-run`
{: #build-container-mounts-run}

* Use this option to define mounts between the host system and the run container.
* The `host-path-run` and `container-path-run` values are inserted at the beginning of this list.
* As a best practice, and to prevent unexpected results, you can build and run by using the same mount settings.
* Usage: `ibmcloud dev build --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #build-container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you can build and debug by using the same mount settings.
* Usage: `ibmcloud dev build --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-port-map`
{: #build-container-port-map}

* Port mappings for the container. The first value is the port to use in the host OS, the second is the port in the container [`host-port:container-port`].
* Usage: `ibmcloud dev build --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #build-dockerfile-tools}

* Dockerfile for the tools container.
* Usage: `ibmcloud dev build --dockerfile-tools [path/to/dockerfile]`

#### `host-path-tools`
{: #build-host-path-tools}

* Location on the host to share for build, debug, test.
* Usage: `ibmcloud dev build --host-path-tools [/path/to/build/tools]`

#### `image-name-tools`
{: #build-image-name-tools}

* Image to create from `dockerfile-tools`.
* Usage: `ibmcloud dev build --image-name-tools [path/to/image-name]`

#### `trace`
{: #build-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev build --trace`

## code
{: #code}

Use the `code` command to download a previously created app with app template code and configuration files for the {{site.data.keyword.cloud_notm}}. You can use this command when you need to extract a second copy of an app.

Run the following command to download the code from a specified app.
```
ibmcloud dev code <appName>
```
{: codeblock}

### code command parameters
{: #code-parameters}

The following parameter can be used with the `code` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #code-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev code --trace`

## console
{: #console}

Use the `console` command to open a web browser to your app's web console on {{site.data.keyword.cloud_notm}}. You can run the `ibmcloud dev console` command from inside your app's folder. The CLI attempts to find a matching app on the {{site.data.keyword.cloud_notm}} that has the same app ID as the current directory. If the system isn't able to find a matching name, it opens the {{site.data.keyword.cloud_notm}} App Development console instead of the specific app.

You can provide an app name and the CLI skips matching based on the folder or app name. In this case, the CLI opens the named app's console in a web browser.  

Run the following command to open a web browser to your app's web console.
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

Create an app that prompts for all information, including resource group, app type, language, and starter kit. You are prompted to enter a name for your app, and you can select services to add to the app. You can also select DevOps toolchain options for automatic deployment, or you can select manual deployment. The app is created in the current directory. Only the deployment files that are relevant for your choice of deployment target are created. You can use the [**ibmcloud dev edit**](/docs/cli?topic=cli-idt-cli#edit) command from the app directory to add more deployment file types if you need them.

To create an app in the current directory and to associate services with it, run the following command:
```
ibmcloud dev create
```
{: codeblock}

For more information, see [Creating an app from a starter kit](/docs/apps?topic=apps-create-deploy-app-cli#create-app-cli).

### create command parameters
{: #create-parameters}

The following parameter can be used with the `create` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #create-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev create --trace`

## debug
{: #debug}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can debug your app through the `debug` command. A build must first be completed against the app by using the build command with the `--debug` argument. When you start the `debug` command, a container is started which provides a debug port or ports as defined by the `container-port-map-debug` value in the cli-config.yml or specified on the command line. Connect your favorite debugging tool to the port or ports, and you can debug your app as normal.

First, compile your app:
```
ibmcloud dev build --debug
```
{: codeblock}

To begin, run the following command in your current app directory to begin debugging:
```
ibmcloud dev debug
```
{: codeblock}

To debug, attach your debug tool to the specified port.

To exit the debug session, use `CTRL-C`.

### debug command parameters
{: #debug-parameters}

The following parameters can be used with the `debug` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #debug-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev debug --config-file cli-config.yml`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parameter that is used to build code for DEBUG.
* Usage: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `container-mounts-run`
{: #debug-container-mounts-run}

* Use this option to define mounts between the host system and the run container.
* The `host-path-run` and `container-path-run` values are inserted at the beginning of this list.
* As a best practice, and to prevent unexpected results, you can build and run by using the same mount settings.
* Usage: `ibmcloud dev debug --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #debug-container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you can build and debug by using the same mount settings.
* Usage: `ibmcloud dev debug --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-name-run`  
{: #debug-container-name-run1}

* Container name for the run container.
* Usage: `ibmcloud dev debug --container-name-run [<appName>]`

#### `container-name-tools`  
{: #debug-container-name-tools1}

* Container name for the tools container.
* Usage: `ibmcloud dev debug --container-name-tools [<appName>]`

#### `container-path-tools`
{: #debug-container-path-tools}

* Location in the container to share for build, debug, test.
* Usage: `ibmcloud dev debug --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #debug-container-port-map}

* Port mappings for the container. The first value is the port to use in the host OS, the second is the port in the container [`host-port:container-port`].
* Usage: `ibmcloud dev debug --container-port-map [8090:8090,9090:9090]`

#### `container-port-map-debug`
{: #port-map-debug}

* Port mappings for the debug port. The first value is the port to use in the host OS, the second is the port in the container [`host-port:container-port`].
* Usage: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `debug-cmd`
{: #debug-cmd}

* Parameter that is used to specify a command to start debug in the tools container. Use this parameter if the `build-cmd-debug` starts your app in debug.
* Usage: `ibmcloud dev debug --debug-cmd /the/debug/command`

#### `dockerfile-tools`
{: #debug-dockerfile-tools}

* Dockerfile for the tools container.
* Usage: `ibmcloud dev debug --dockerfile-tools [path/to/dockerfile]`

#### `host-path-tools`
{: #debug-host-path-tools}

* Location on the host to share for build, debug, test.
* Usage: `ibmcloud dev debug --host-path-tools [/path/to/build/tools]`

#### `image-name-tools`
{: #debug-image-name-tools}

* Image to create from `dockerfile-tools`.
* Usage: `ibmcloud dev debug --image-name-tools [path/to/image-name]`

#### `trace`
{: #debug-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev debug --trace`

## delete
{: #delete}

Use the `delete` command to remove apps from your {{site.data.keyword.cloud_notm}} space. You can run the command without parameters to list available apps and select the app from the numbered list to delete. App code and directories aren't removed from your local disk space.

Run the following command to delete your app from {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete [appName] [--force,-f]
```
{: codeblock}

{{site.data.keyword.cloud_notm}} services aren't removed.
{: note}

### delete command parameters
{: #delete-command-parameters}

The following parameters can be used with the `delete` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `force`
{: #delete-force}

* Parameter that is optionally used to skip the prompt confirmation for deleting an application
* Usage: `ibmcloud dev delete [appName] --force`

#### `trace`
{: #delete-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev delete --trace`

## deploy
{: #deploy}

You can deploy an app as a {{site.data.keyword.cloud_notm}} Foundry app or as a container.

Run the following command in your current app directory to build your app:  
```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current app directory to deploy your app:
```
ibmcloud dev deploy
```
{: codeblock}

Before you deploy a Cloud Foundry app to {{site.data.keyword.cloud_notm}}, a `manifest.yml` file must be present in your app's root directory.
{: tip}

For more information, see [Deploying your app](/docs/apps?topic=apps-create-deploy-app-cli).

### Deploying to {{site.data.keyword.containerlong_notm}}
{: #deploy-kubernetes}

Before you deploy an app as a container, you must locally install [Kubernetes](https://kubernetes.io/){: external} and [Helm](https://github.com/helm/helm){: external}. The Helm client version must not be newer than the Helm server version. You can find both by running `helm version`.

To deploy your app on Kubernetes, you must either specify the `deploy-target` as `container` in the `cli-config.yml` or use the parameter `-t container`.

Other parameters needed to configure Kubernetes deployment can also be specified in the `cli-config.yml` by using command-line arguments. If you don't define these parameters in the `cli-config.yml`, you must deploy with the parameter `-t container`. Then, you're prompted for all of the other values.

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<{{site.data.keyword.cloud_notm}} Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

In the `cli-config.yml`, you can define the location of a Helm chart in the `chart-path` property and configure the `deploy-image-target` as shown in the example. The `deploy-image-target` element in the `cli-config.yml` is used instead of the `repository` and `tag` elements in the `chart/values.yml` file. To deploy to {{site.data.keyword.cloud_notm}} specifically, set the configuration element `ibm-cluster` to the name of the Kubernetes cluster that you created in {{site.data.keyword.cloud_notm}}. If you don't specify the cluster name, are prompted to select it from a list of your available clusters.

### Deploying to Red Hat OpenShift on {{site.data.keyword.cloud_notm}}
{: #deploy-openshift-cli}

You can deploy your app to a {{site.data.keyword.openshiftlong}} container by using a DevOps toolchain or by using the `deploy` command.

#### Toolchain deployment to OpenShift
{: #deploy-openshift-toolchain}

[{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started) provides toolchain deployment support for [OpenShift](/docs/openshift?topic=openshift-getting-started) clusters. To use this feature, you need an OpenShift cluster. With this prerequisite met, an OpenShift deployment option is available for the `create` and `edit` capabilities of the {{site.data.keyword.dev_cli_notm}} commands.

By selecting the **OpenShift** option, you can create a toolchain that deploys to the OpenShift cluster that you specify through the dialog.

#### Manual deployment to OpenShift
{: #deploy-openshift-manual}

For manual deployment to an OpenShift container, the syntax is the same as for deploying your app to any other Helm-based Kubernetes cluster.

First, create or enable an app. You must have an OpenShift cluster. For more information about configuring your cluster, see [Creating OpenShift clusters](/docs/openshift?topic=openshift-clusters).

After those prerequisites are met, you can deploy the app by typing the following command from the app folder:

```
ibmcloud dev deploy -t container
```
{: codeblock}

The CLI prompts you through the deployment process.

### deploy command parameters
{: #deploy-parameters}

The following parameters can be used with the `deploy` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #deploy-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev deploy --config-file cli-config.yml`

#### `chart-path`
{: #chart-path}

* Parameter that is used for a container deployment to specify the location of the Helm chart used for the deployment.
* Usage: `ibmcloud dev deploy --chart-path [/the/path]`

#### `cluster-role`
{: #cluster-role}

* Cluster role that is used to enable manual deployment to {{site.data.keyword.containerlong_notm}}. For example, `cluster-admin`.
* Usage: `ibmcloud dev deploy -t container --cluster-role [role-name]`

#### `cluster-service-account`
{: #cluster-service-account}

* Cluster service account that is used to enable manual deployment to {{site.data.keyword.containerlong_notm}}. For example, `kube-system:default`.
* Usage: `ibmcloud dev deploy -t container --cluster-service-account [account-name]`

#### `deploy-image-target`
{: #deploy-image-target}

* Parameter that is used with a container deployment as the target image name for the deployment. The value must not include a version. For example, image-name:{version} because the version is automatically incremented and appended by `deploy`.
* Usage: `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `domain`
{: #domain}

* Parameter that is used to define the domain of the app when you deploy to {{site.data.keyword.cloud_notm}} Foundry.
* Usage: `ibmcloud dev deploy --domain [domain]`

#### `host`
{: #host}

* Parameter that is used to define the hostname of the app when you deploy to {{site.data.keyword.cloud_notm}} Foundry.
* Usage: `ibmcloud dev deploy --host [hostname]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parameter that is used to define the name of the Kubernetes cluster for a container deployment to {{site.data.keyword.cloud_notm}}.
* Usage: `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `image-name-run`
{: #deploy-image-name-run}

* Parameter that is used to identify the image so that `deploy` knows which image to push to the {{site.data.keyword.cloud_notm}} image registry for {{site.data.keyword.containerlong_notm}} deployments.
* Usage: `ibmcloud dev deploy --image-name-run [image-name]`

#### `target`
{: #deploy-target}

* Parameter that is used to indicate the type of deployment to be completed. The default deployment type is buildpack.
* Usage: `ibmcloud dev deploy -t|--target buildpack|container`

#### `trace`
{: #deploy-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev deploy --trace`

## diag
{: #diag}

The `diag` command is used as a diagnostic to display the version information of installed dependencies for the {{site.data.keyword.dev_cli_notm}} commands. Running `diag` is helpful to determine whether you're missing any dependencies or to help in debugging problems.

Run the following command to display the versions of your installed dependencies:
```
ibmcloud dev diag
```
{: codeblock}

### diag command parameters
{: #diag-parameters}

The following parameter can be used with the `diag` command.

#### `trace`
{: #diag-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev diag --trace`

## edit
{: #edit}

Edit your app with options such as connecting it with an existing {{site.data.keyword.cloud_notm}} app, managing {{site.data.keyword.cloud_notm}}, and its {{site.data.keyword.cloud_notm}} toolchain that deploys to {{site.data.keyword.containerlong_notm}}, or {{site.data.keyword.cloud_notm}} Foundry. With a local app that is connected to an app in {{site.data.keyword.cloud_notm}}, use `edit` to add new services, connect and disconnect existing services, or remove existing services from your account. Additionally, you can:
 * Create or view a DevOps toolchain for the app.
 * Select DevOps toolchain options for automatic deployment.
 * Select manual deployment. The deployment files that are relevant for your choice of deployment target are created.

Run the following command in the root of your app directory:
```
ibmcloud dev edit
```
{: codeblock}

If you have no existing services on your account, this command shows you a list of service groups from which you can select a service to connect to your app.

However, if you have any existing services on your account, this command shows you a list of those services and whether each service is connected to the app or not.

* A connected service gives you options to either disconnect the service from your app or delete the service from your account, which disconnects it from all apps.

* A disconnected service gives you options to either connect that service to your app or delete the service from your account. Connecting an existing service also downloads files, such as credentials or source code.

You can also add a service to your app, where you are guided through service selection prompts to download files such as credential files or source code.

### edit command parameters
{: #edit-parameters}

The following parameters can be used with the `edit` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #edit-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev edit --config-file cli-config.yml`

#### `trace`
{: #edit-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev edit --trace`

## enable
{: #enable}

Enable an existing app for {{site.data.keyword.cloud_notm}} deployment. The `enable` command attempts to automatically detect the language of an existing app and then prompt for necessary additional information. All deployment environments can be used through a manual `deploy` or by using a DevOps toolchain. Only the deployment files that are relevant for your choice of deployment target are created. You can use the [**ibmcloud dev edit**](/docs/cli?topic=cli-idt-cli#edit) command from the app directory to add more deployment file types if you need them.

While logged in to {{site.data.keyword.cloud_notm}}, you can connect this local app with an app that is already in {{site.data.keyword.cloud_notm}} or create a new {{site.data.keyword.cloud_notm}} app. To take advantage of {{site.data.keyword.cloud_notm}} features such as services and DevOps toolchains, an app in {{site.data.keyword.cloud_notm}} is necessary. When an {{site.data.keyword.cloud_notm}} app is created for an app that is cloned from a Git repository, the {{site.data.keyword.cloud_notm}} app includes this repository in its configuration. 

The `enable` command is a Beta feature. If you have trouble with the `enable` command, see [troubleshooting](/docs/cli?topic=cli-troubleshoot). In particular, `enable` isn't intended for mobile apps or frameworks. For complex apps that produce several deployable assets, each component of the app must be enabled individually. 

Run the following command to enable an existing app in the current directory:
```
ibmcloud dev enable
```
{: codeblock}

The presence of necessary files provides app language detection for a valid project structure.  

* The presence of a `package.json` file identifies a Node.js app.
* The presence of a `package.swift` file identifies a Swift app.
* The presence of either a `setup.py` or `requirements.txt` file identifies a Python app.
* The presence of either a `pom.xml` or `build.gradle` file identifies a Java&trade; app.
	* The presence of a `pom.xml` identifies a Maven app.
	* The presence of a `build.gradle` identifies a Gradle app.

You can also override the detected app language by using the `--language` argument. Only valid and complete apps are supported. The enable command doesn't modify your source code.

### enable language options
{: #enable-language-options}

Language options include:
* Go
* Java EE (interpreted as Java&trade; - Java&trade; EE)
* Java-mp (interpreted as Java&trade; - Java&trade; MicroProfile)
* Java-spring (interpreted as Java&trade; - Spring Framework)
* Node
* Python
* Swift

Files that are created by using the `ibmcloud dev enable` command are saved with a `.merge` file extension if name conflicts occur with existing files in the app folder.

### enable command parameters
{: #enable-parameters}

The following parameters can be used with the `enable` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`  
{: #config-file-enable}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev enable --config-file cli-config.yml`

#### `force`
{: #enable-force}

* Parameter that is used to force reenabling an already enabled app.
* Usage: `ibmcloud dev enable -f|--force`

#### `language`
{: #enable-language}

* Parameter that is used to specify the language of the app to be enabled.
* Usage: `ibmcloud dev enable -l|--language [language]`

#### `trace`
{: #trace-enable}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev enable --trace`

## get-credentials
{: #get-credentials}

Get credentials are required by the app to enable the use of connected services.

### get-credentials command parameters
{: #creds-parameters}

The following parameter can be used with the `enable` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #creds-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev get-credentials --trace`

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

You can list all {{site.data.keyword.cloud_notm}} apps in a resource group.

Run the following command to list your apps:
```
ibmcloud dev list
```
{: codeblock}

### list command parameters
{: #list-parameters}

The following parameter can be used with the `list` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #list-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev list --trace`

## pipeline-get
{: #pipeline-get}

View the details of a Classic pipeline.

```
ibmcloud dev pipeline-get [pipelineID] [--output JSON]
```
{: codeblock}

### pipeline-get command parameters
{: #pipeline-get-command-parameters}

#### `json`
{: #json-get}

* Parameter that is used to output the pipeline details in JSON format.
* Usage: `ibmcloud dev pipeline-get [pipelineID] --output JSON`

### pipeline-get command parameters
{: #pipeget-parameters}

The following parameter can be used with the `pipeline-get` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #pipeline-get-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-get [pipelineID] --trace`

## pipeline-run
{: #pipeline-run}

Run a Classic pipeline.
```
ibmcloud dev pipeline-run [pipelineID] [--stage-id stageID] [--output JSON] 
```
{: codeblock}

### pipeline-run command parameters
{: #pipeline-run-command-parameters}

The following parameters can be used with the `pipeline-run` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `stage-id`
{: #run-stage-id}

* Parameter optionally used to select a pipeline's stage to run
* Usage: `ibmcloud dev pipeline-run [pipelineID] --stage-id [stageID]`

#### `json`
{: #json-run}

* Parameter that is used to output the pipeline's invocation details in JSON format.
* Usage: `ibmcloud dev pipeline-run [pipelineID] --output JSON`

#### `trace`
{: #pipeline-run-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-run [pipelineID] --trace`

## pipeline-log
{: #pipeline-log}

View recent Classic pipeline logs by using the `pipeline-log` command.

* If the pipeline ID is specified as an argument, all logs for all jobs in all stages are printed for that pipeline.
* If the stage ID flag is populated, the logs are filtered by that stage in the pipeline. 
* If the job ID is specified with the stage ID, the logs are filtered to just the job in the stage. 
* If the job execution ID is specified along with the stage ID and job ID, a search is done among all available logs that match the job execution ID specified.

Usage:
```
ibmcloud dev pipeline-log [pipelineID] [--stage-id stageID] [--job-id jobID] [--job-exec-id jobExecutionID]
```
{: codeblock}

### pipeline-log command parameters
{: #pipeline-log-command-parameters}

The following parameters can be used with the `pipeline-log` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `job-id`
{: #job-id}

* Parameter that is used to filter the logs by the job ID.
* Requires the `stage-id` flag.
* Usage: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID]`

#### `job-exec-id`
{: #job-exec-id}

* Parameter that is used to filter the logs by the job execution ID.
* Requires the `stage-id` flag.
* Requires the `job-id` flag.
* Usage: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID] --job-exec-id [jobExecutionID]`

#### `stage-id`
{: #log-stage-id}

* Parameter that is used to filter the logs by the stage ID.
* Usage: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID]`

#### `trace`
{: #pipelog-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-log [pipelineID] --trace`

## pipeline-open
{: #pipeline-open}

View the URL for the Classic pipeline through the `pipeline-open` command. The `pipeline-open` command also opens the URL in your default browser.
```
ibmcloud dev pipeline-open [pipelineID]
```
{: codeblock}

### pipeline-open command parameters
{: #pipeopen-parameters}

The following parameter can be used with the `pipeline-open` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #pipeline-open-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev pipeline-open [pipelineID] --trace`

## run
{: #run}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can run your app through the `run` command. A build must first be completed against the app by using the `build` command. When you run the `run` command, the run container starts and exposes the ports as defined by the `container-port-map` parameter. The `run-cmd` parameter is used to start the app if the run container `Dockerfile` doesn't contain an entry point to complete this step.

To run with multiple containers, your app must contain a [Compose](https://docs.docker.com/compose/overview/){: external} file, which is specified in the `cli-config.yml`, or you can use the `dockerfile-run` command parameter to provide one.

First, compile your app:
```
ibmcloud dev build
```
{: codeblock}

Run the following command in your current app directory to start your app:
```
ibmcloud dev run
```
{: codeblock}

To exit the session use `CTRL-C`.

### run command parameters
{: #run-parameters}

The following parameters can be used with the `run` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #run-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev run --config-file cli-config.yml`

#### `build-cmd-run`
{: #run-build-cmd-run}

* Parameter that is used to specify a command to build code for all use except DEBUG.
* Usage: `ibmcloud dev run --build-cmd-run [some.build.command]`

#### `container-mounts-run`
{: #run-container-mounts-run}

* Use this option to define mounts between the host system and the run container.
* The `host-path-run` and `container-path-run` values are inserted at the beginning of this list.
* As a best practice, and to prevent unexpected results, you can build and run by using the same mount settings.
* Usage: `ibmcloud dev run --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #run-container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you can build and debug by using the same mount settings.
* Usage: `ibmcloud dev run --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-name-run`  
{: #run-container-name-run}

* Container name for the run container.
* Usage: `ibmcloud dev run --container-name-run [<appName>]`

#### `container-name-tools`  
{: #run-container-name-tools}

* Container name for the tools container.
* Usage: `ibmcloud dev run --container-name-tools [<appName>]`

#### `container-path-run`
{: #container-path-run}

* Location in the container to share on run.
* Usage: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `container-path-tools`
{: #run-container-path-tools}

* Location in the container to share for build, debug, test.
* Usage: `ibmcloud dev run --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #run-container-port-map}

* Port mappings for the container. The first value is the port to use in the host OS, the second is the port in the container [`host-port:container-port`].
* Usage: `ibmcloud dev run --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile for the run container.
* If you intend to run with several containers, use a Compose file.
* To use multiple compose files, surround a comma-delimited list of the file names with double quotation marks.
* Usage: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Usage: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `dockerfile-tools`
{: #run-dockerfile-tools}

* Dockerfile for the tools container.
* Usage: `ibmcloud dev run --dockerfile-tools [path/to/dockerfile]`

#### `host-path-run`
{: #host-path-run}

* Location on the host system to share in the container on run.
* Usage: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `host-path-tools`
{: #run-host-path-tools}

* Location on the host to share for build, debug, test.
* Usage: `ibmcloud dev run --host-path-tools [/path/to/build/tools]`

#### `image-name-run`
{: #run-image-name-run}

* Image to create from `dockerfile-run`.
* Usage: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `image-name-tools`
{: #run-image-name-tools}

* Image to create from `dockerfile-tools`.
* Usage: `ibmcloud dev run --image-name-tools [path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parameter that is used to run code in the run container. Use this parameter if your image starts your app.
* Usage: `ibmcloud dev run --run-cmd [/the/run/command]`

#### `trace`
{: #run-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev run --trace`

## shell
{: #shell}

If you're using Windows&trade;, you must be run Windows&trade; 10 Pro or later.

You can open the shell inside the run or tools container with the `shell` command.

By running the following command:
```
ibmcloud dev shell
```
{: codeblock}

This command opens an interactive shell into the app's docker container. The default target container for the `shell` command is defined by the `container-shell-target` value in the `cli-config.yml` file, where the valid values are `run` or `tools`. If this value is not defined or an invalid value is specified, then the `shell` command targets the `tools` container by default. The shell command opens the container to the directory specified by the `WORKDIR` instruction in the corresponding Dockerfile. If `WORKDIR` is not listed in the Dockerfile, the container root is used as the working directory. For more information, see [this reference](https://docs.docker.com/engine/reference/builder/#workdir){: external}.

Alternatively, you can decide to pass either `run` or `tools` as an argument to the command and that container is brought up and the shell is opened for that container. Similarly, you can use the `container-name` parameter to pass the name of the container into which you want to shell. However, this flag is reserved for when no containers are running. The `run` and `tools` arguments are more flexible so you can switch between containers when one is running. For example, if the tools container is running and you run `ibmcloud dev shell run`, the `tools` container is stopped and the `run` container starts, and vice versa.

If the target `run` or `tools` container is not already running when you run the `shell` command, then the target container is started. However, the default `Cmd` or `Entrypoint` in the Dockerfile is overridden to start directly into the shell instead of starting the server process. So you can start the `run` or `tools` container, and then manually start the server with your own arbitrary or custom commands.

You can also specify the shell that you want to open by using the `container-shell` parameter. By default, `/bin/sh` is used. If you'd prefer to use the bash shell, then specify the `container-shell` value to be `/bin/bash`; however, keep in mind that bash is not automatically available across all Linux&trade; variants.

Any additional arguments that you pass to the command beyond the flags are parsed as the command to be run when the shell is opened. If you provide a command, the shell inside the container exits upon running the command and returns you to your terminal.

For example, you can run the Linux&trade; `ls` command inside of the tools container shell by running `ibmcloud dev shell tools ls`. You can also specify flags to be passed into the shell command execution by wrapping the arguments in quotation marks, such as `ibmcloud dev shell "ls -la"`.

The `shell` command doesn't require an app to be compiled, which allows for shelling into the tools container directly to debug why an app is failing to compile.
{: tip}

### shell command parameters
{: #shell-parameters}

The following parameters can be used with the `shell` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #shell-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev edit --config-file cli-config.yml`

#### `container-name`
{: #container-name-shell}

* Name of the container into which you want to shell.
* Usage: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Specifies which shell to run inside the container (default is /bin/sh).
* Usage: `ibmcloud dev shell --container-shell [path/to/shell]`

#### `trace`
{: #shell-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev shell --trace`

#### `use-root-user-tools`
{: #shell-use-root-user-tools}

* Use this parameter to use the root user in the tools container.
* Usage: `ibmcloud dev shell --use-root-user-tools`

## status
{: #status}

If you are using Windows&trade;, you must be running Windows&trade; 10 Pro or later.

You can query the status of the containers that are used by the {{site.data.keyword.dev_cli_short}} commands as defined by `container-name-run` and `container-name-tools`.

Run the following command in your current app directory to check container status:
```
ibmcloud dev status
```
{: codeblock}

### status command parameters
{: #status-parameters}

The following parameters can be used with the `status` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #status-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev status --config-file cli-config.yml`

#### `container-name-run`
{: #status-container-name-run1}

* Container name for the run container.
* Usage: `ibmcloud dev status --container-name-run [<appName>]`

#### `container-name-tools`
{: #status-container-name-tools}

* Container name for the tools container.
* Usage: `ibmcloud dev status --container-name-tools [<appName>]`

#### `trace`
{: #status-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev status --trace`

## stop
{: #stop}

If you're using Windows&trade;, you must be run Windows&trade; 10 Pro or later.

You can stop your containers through the `stop` command.

To stop the tools and run containers as defined in your `cli-config.yml` file, run:
```
ibmcloud dev stop
```
{: codeblock}

To stop a container that isn't defined in the `cli-config.yml` file, you can specify an extra command-line parameter to override it. If no containers are specified in the `cli-config.yml` file or on the command line, the stop command simply returns.

### stop command parameters
{: #stop-parameters}

The following parameters can be used with the `stop` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #stop-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev stop --config-file cli-config.yml`

#### `container-name-run`  
{: #stop-container-name-run1}

* Container name for the run container.
* Usage: `ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`  
{: #stop-container-name-tools}

* Container name for the tools container.
* Usage: `ibmcloud dev stop --container-name-tools [<appName>]`

#### `trace`
{: #stop-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev stop --trace`

## tekton-info
{: #tekton-info}

View the details of a Tekton pipeline.

```
ibmcloud dev tekton-info [pipelineID] [--verbose][--output JSON]
```
{: codeblock}

### tekton-info command parameters
{: #tekton-info-command-parameters}

The following parameters can be used with the `tekton-info` command.

#### `verbose`
{: #tekton-info-verbose}

* Use this parameter to provide all details of a pipeline in JSON format.
* Usage: `ibmcloud dev tekton-info [pipelineID] --verbose`

#### `json`
{: #json-tekton-info}

* Parameter that is used to output the pipeline details in JSON format.
* Usage: `ibmcloud dev tekton-info [pipelineID] --output JSON`

#### `trace`
{: #tekton-info-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-info [pipelineID] --trace`

## tekton-logs
{: #tekton-logs}

View recent Tekton pipeline run logs by using the `tekton-logs` command.

* The pipeline run ID is a required argument.
* If the task name is specified as an argument, only the logs for this task are retrieved.

Usage:
```
ibmcloud dev tekton-logs [pipelineID] --run-id [pipelinerunID] [--task-name taskName] [--output JSON]
```
{: codeblock}

### tekton-logs command parameters
{: #tekton-logs-command-parameters}

The following parameters can be used with the `tekton-logs` command.

#### `run-id` (required)
{: #run-id}

* Parameter that identifies the pipeline run for the log retrieval.
* Usage: `ibmcloud dev tekton-logs [pipelineID]  --run-id [pipelinerunID]`

#### `task-name`
{: #task-name}

* Parameter that is used to filter the logs by the pipeline run task name.
* Usage: `ibmcloud dev tekton-logs [pipelineID]  --run-id [pipelinerunID] --task-name [taskName]`

#### `json`
{: #json-tekton-logs}

* Parameter that is used to output the log details in JSON format.
* Usage: `ibmcloud dev tekton-logs [pipelineID]  --run-id [pipelinerunID] --output JSON`

#### `trace`
{: #tekton-logs-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-logs [pipelineID]  --run-id [pipelinerunID] --trace`

## tekton-pipelinerun
{: #tekton-pipelinerun}

View the details of a Tekton pipeline run or use the `ls` parameter to list all pipeline runs for the pipeline.

Usage:
```
ibmcloud dev tekton-pipelinerun [pipelineID] --run-id [pipelinerunID] [--output JSON]
ibmcloud dev tekton-pipelinerun ls [pipelineID]
```
{: codeblock}

### tekton-pipelinerun command parameters
{: #tekton-pipelinerun-command-parameters}

The following parameters can be used with the `tekton-pipelinerun` command.

#### `run-id` (required)
{: #tekton-pipelinerun-run-id}

* Parameter that identifies the pipeline run to retrieve.
* Usage: `ibmcloud dev tekton-pipelinerun [pipelineID] --run-id [pipelinerunID]`

#### `json`
{: #json-tekton-pipelinerun}

* Parameter that is used to output the pipeline run details in JSON format.
* Usage: `ibmcloud dev tekton-pipelinerun [pipelineID] --run-id [pipelinerunID] --output JSON`

#### `trace`
{: #tekton-pipelinerun-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-pipelinerun [pipelineID] --run-id [pipelinerunID] --trace`

## tekton-pipelineruns
{: #tekton-pipelineruns}

View a list of pipeline runs for a Tekton pipeline.

Usage:
```
ibmcloud dev tekton-pipelineruns [pipelineID] [--output JSON]
```
{: codeblock}

### tekton-pipelineruns command parameters
{: #tekton-pipelineruns-command-parameters}

The following parameters can be used with the `tekton-pipelineruns` command.

#### `json`
{: #json-tekton-pipelineruns}

* Parameter that is used to output the pipeline runs in JSON format.
* Usage: `ibmcloud dev tekton-pipelineruns [pipelineID] --output JSON`

#### `trace`
{: #tekton-pipelineruns-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-pipelineruns [pipelineID] --trace`

## tekton-trigger
{: #tekton-trigger}

Run a Tekton pipeline.

Usage:
```
ibmcloud dev tekton-trigger [pipelineID] --trigger-name [triggerName] [--output JSON]
```
{: codeblock}

### tekton-trigger command parameters
{: #tekton-trigger-command-parameters}

The following parameters can be used with the `tekton-trigger` command.

#### `trigger-name` (required)
{: #tekton-trigger-name}

* Use this parameter to indicate the trigger to be run.
* Usage: `ibmcloud dev tekton-trigger [pipelineID] --trigger-name [triggerName]`

#### `json`
{: #json-tekton-trigger}

* Parameter that is used to output the trigger results in JSON format.
* Usage: `ibmcloud dev tekton-trigger [pipelineID] --trigger-name [triggerName] --output JSON`

#### `trace`
{: #tekton-trigger-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev tekton-trigger [pipelineID] --trigger-name [triggerName] --trace`

## test
{: #test}

If you're using Windows&trade;, you must run Windows&trade; 10 Pro or later.

You can test your app through the `test` command. A build must first be completed against the app by using the `build --debug` command. The tools container is then used to start the `test-cmd` for the app.

First, compile your app:
```
ibmcloud dev build --debug
```
{: codeblock}

Run the following command to test your app:
```
ibmcloud dev test
```
{: codeblock}

### test command parameters
{: #test-parameters}

The following parameters can be used with the `test` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #test-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev test --config-file cli-config.yml`

#### `container-mounts-run`
{: #test-container-mounts-run}

* Use this option to define mounts between the host system and the run container.
* The `host-path-run` and `container-path-run` values are inserted at the beginning of this list.
* As a best practice, and to prevent unexpected results, you can build and run by using the same mount settings.
* Usage: `ibmcloud dev test --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #test-container-mounts-tools}

* Use this option to define mounts between the host system and the tools container.
* The `host-path-tools` and `container-path-tools` values are inserted at the beginning this list.* As a best practice and to prevent unexpected results, you can build and debug by using the same mount settings.
* Usage: `ibmcloud dev test --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-name-tools`  
{: #test-container-name-tools1}

* Container name for the tools container.
* Usage: `ibmcloud dev test --container-name-tools [<appName>]`

#### `container-path-tools`
{: #test-container-path-tools}

* Location in the container to share for build, debug, test.
* Usage: `ibmcloud dev test --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #test-container-port-map}

* Port mappings for the container. The first value is the port to use in the host OS, the second is the port in the container [`host-port:container-port`].
* Usage: `ibmcloud dev test --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #test-dockerfile-tools}

* Dockerfile for the tools container.
* Usage: `ibmcloud dev test --dockerfile-tools [path/to/dockerfile]`

#### `host-path-tools`
{: #test-host-path-tools}

* Location on the host to share for build, debug, test.
* Usage: `ibmcloud dev test --host-path-tools [/path/to/build/tools]`

#### `image-name-tools`
{: #test-image-name-tools}

* Image to create from `dockerfile-tools`.
* Usage: `ibmcloud dev test --image-name-tools [path/to/image-name]`

#### `test-cmd`
{: #test-cmd}

* Parameter that is used to specify a command to test code in the tools container.
* Usage: `ibmcloud dev test --test-cmd /the/test/command`

#### `trace`
{: #test-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev test --trace`

## toolchain-delete
{: #toolchain-delete}

Delete a toolchain. If no toolchain name is provided, you can select one from a list. The list of toolchains depends on the currently targeted resource group and region.

The targeted Resource Group is found in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target).
```
ibmcloud dev toolchain-delete [toolchainName] [--force,-f]
```
{: codeblock}

### toolchain-delete command parameters
{: #toolchain-delete-command-parameters}

The following parameters can be used with the `toolchain-delete` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `force`
{: #toolchain-delete-force}

* Parameter that is used to skip the prompt confirmation for deleting a toolchain.
* Usage: `ibmcloud dev toolchain-delete [toolchainName] --force`

#### `trace`
{: #toolchain-delete-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-delete [toolchainName] --trace`

## toolchain-get
{: #toolchain-get}

View the details of a toolchain. If no toolchain name is provided, you can select one from a list. 

Uses the targeted resource group in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target). Some Cloud Foundry-based toolchains might not be compatible with this command.
```
ibmcloud dev toolchain-get [toolchainName] [--output JSON]
```
{: codeblock}

### toolchain-get command parameters
{: #toolchain-get-command-parameters}

The following parameters can be used with the `toolchain-get` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `json`
{: #json-toolchain-get}

* Parameter that is used to output the toolchain details in JSON format.
* Usage: `ibmcloud dev toolchain-get [toolchainName] --output JSON`

#### `trace`
{: #toolchain-get-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-get [toolchainName] --trace`

## toolchain-open
{: #toolchain-open}

View the URL for the toolchain through the `toolchain-open` command. The `toolchain-open` command also opens the URL in your default browser. If no toolchain name is provided, a list of toolchains is provided to select from.
```
ibmcloud dev toolchain-open [toolchainName]
```
{: codeblock}

### toolchain-open command parameters
{: #toolchain-open-parameters}

The following parameter can be used with the `toolchain-open` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `trace`
{: #toolchain-open-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchain-open [toolchainName] --trace`

## toolchains
{: #toolchains}

View a list of toolchains in the current resource group. 

Uses the targeted Resource Group in the `IBMCLOUD API Key`. For more information, see [Set or View the target Account, Region or Resource Group](/docs/cli/reference/ibmcloud?topic=cli-ibmcloud_cli#ibmcloud_target). Some Cloud Foundry-based toolchains might not be compatible with this command.
```
ibmcloud dev toolchains [--output JSON]
```
{: codeblock}

### toolchains command parameters
{: #toolchains-command-parameters}

The following parameters can be used with the `toolchains` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `json`
{: #json-toolchains}

* Parameter that is used to output the toolchains in JSON format.
* Usage: `ibmcloud dev toolchains --output JSON`

#### `trace`
{: #toolchains-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev toolchains --trace`

## view
{: #view}

You can view the URL to which your app is deployed through the `view` command. Run this command in the root directory of the app you want to view. The `view` command also opens the URL in your default browser.

For apps that are deployed to {{site.data.keyword.cloud_notm}} Foundry, the URL consists of the app's hostname and the app's domain.

For apps that are deployed to {{site.data.keyword.containerlong_notm}}, the URL consists of the IP address of the node it is deployed to, and the public port. If the command determines that the app was deployed to Kubernetes, the CLI tool prompts for confirmation. If you specify that the app wasn't deployed to Kubernetes, then the {{site.data.keyword.cloud_notm}} Foundry URL is shown. If you expected the command to show the URL for a Kubernetes-deployed app, ensure that the `cli-config.yml` contains an entry for `chart-path` or supply it through command line as shown [here](#chart-path).

Run the following command from the app directory to view your app:
```
ibmcloud dev view
```
{: codeblock}

### view command parameters
{: #view-parameters}

The following parameters can be used with the `view` command or by updating the app's `cli-config.yml` file directly.

Command parameters that are entered on the command line take precedence over the `cli-config.yml` configuration.
{: note}

#### `config-file`
{: #view-config-file}

* Specify a `cli-config.yml` file to use for a command.
* Usage: `ibmcloud dev view --config-file cli-config.yml`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parameter that is used to define the name of the Kubernetes cluster when you target a container deployment.
* Usage: `ibmcloud dev view --ibm-cluster [cluster-name]`

#### `no-open`
{: #no-open}

* Parameter that is used to specify not to open the browser.
* Usage: `ibmcloud dev view --no-open`

#### `target`
{: #commands-deploy-target}

* Parameter that is used to indicate the type of deployment to bypass the prompt.
* Usage: `ibmcloud dev view -t|--target buildpack|container`

#### `trace`
{: #view-trace}

* Use this parameter to provide verbose output.
* Usage: `ibmcloud dev view --trace`

#### `web-app-root`
{: #web-app-root}

* Root of the project to append to the Cloud Foundry and Kubernetes app URL.
* Usage: `ibmcloud dev view --web-app-root [root]`

## compound commands
{: #compound}

You are able to run several commands in one command-line statement by separating the {{site.data.keyword.dev_cli_notm}} commands with the `/` delimiter. More command-line flags can be used after you specify the compound commands. The following commands are examples of how you can use compound commands:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

All flags must trail the final command and be applied to all commands to which that flag is associated. Using `ibmcloud dev build/deploy/view -t container --trace` as an example, the `--trace` flag is applied to all three commands, but the `-t` is only applicable to the final two commands, and is not applied to the `build` command.

The following commands can be used with this feature:
`build, debug, deploy, get-credentials, run, stop, test, view`

If one command fails for any reason, the subsequent commands are not run.

If any commands follow `debug` or `run`, execution continues if `debug` or `run` is terminated by means other than killing the process from the current terminal window. Enter `CTRL+C` to kill the process and not run the subsequent commands. For example, you can run `ibmcloud dev stop` from another terminal window to stop the running container and continue execution to the next command.
