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

# {{site.data.keyword.dev_cli_notm}} CLI 插件 (ibmcloud dev) 命令
{: #idt-cli}

版本：2.1.18
发布时间：2019 年 3 月 28 日

从 2018 年 5 月起，{{site.data.keyword.cloud}} CLI 命令 `bluemix` 和 `bx` 都变为 `ibmcloud`。但是，您仍然可以使用 `bluemix` 和 `bx` CLI 命令，直到稍后这些命令被除去为止。
{: tip}

使用以下 {{site.data.keyword.dev_cli_notm}} CLI (`ibmcloud dev`) 命令，可创建、管理、部署、调试和测试应用程序。

- [build](#build)：在本地容器中构建应用程序。
- [code](#code)：下载应用程序的代码。
- [console](#console)：打开应用程序的 {{site.data.keyword.cloud_notm}} 控制台。
- [create](#create)：创建新应用程序并提供用于添加服务的选项。
- [debug](#debug)：在本地容器中调试应用程序。
- [delete](#delete)：从空间中删除应用程序。
- [deploy](#deploy)：将应用程序部署到 {{site.data.keyword.cloud_notm}}。
- [diag](#diag)：显示有关已安装依赖项的版本信息。
- [edit](#edit)：在现有应用程序中添加或除去服务。
- [enable](#enable)：更新现有应用程序以用于 {{site.data.keyword.cloud_notm}} Developer Tools。
- [get-credentials](#get-credentials)：获取所需的凭证，以便在应用程序中可以使用连接的 {{site.data.keyword.cloud_notm}} 服务。
- [help](#help)：有关 CLI 语法和自变量的帮助。
- [list](#list)：列出资源组中的所有 {{site.data.keyword.cloud_notm}} 应用程序。
- [run](#run)：在本地容器中运行应用程序。
- [shell](#shell)：将 shell 打开到本地容器中。
- [status](#status)：检查 CLI 使用的容器的状态。
- [stop](#stop)：停止容器。
- [test](#test)：在本地容器中测试应用程序。
- [view](#view)：查看应用程序的已部署 URL 以进行测试和查看。
- [compound commands](#compound)：在一个命令行语句中运行多个命令。

## build
{: #build}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以使用 `build` 命令来构建应用程序。`test`、`debug` 和 `run` 命令需要查找已编译的应用程序，因此必须先运行 `build` 操作。

`build-cmd-debug` 配置元素用于构建应用程序以用于除 `run` 之外的所有用途。通过指定命令行选项 `--debug` 来构建应用程序以进行调试。在构建应用程序以用于 `run` 命令时，会使用 `build-cmd-run` 配置元素。

要使用多个容器进行构建，应用程序必须包含 `cli-config.yml` 中指定的 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 文件，您也可以使用 `dockerfile-tools` 命令参数提供该文件。

在当前应用程序目录中运行以下命令来构建应用程序：  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

使用 `code` 命令可下载先前为 {{site.data.keyword.cloud_notm}} 创建的包含应用程序模板代码和配置文件的应用程序。您可以在需要抽取应用程序的第二个副本时使用此命令。

运行以下命令从指定应用程序下载代码。
```
ibmcloud dev code <applicationName>
```
{: codeblock}

## console
{: #console}

使用 `console` 命令可打开 Web 浏览器并转至 {{site.data.keyword.cloud_notm}} 上的应用程序 Web 控制台。可以从应用程序的文件夹内运行 `ibmcloud dev console` 命令。CLI 会尝试在 {{site.data.keyword.cloud_notm}} 上查找与当前目录具有相同应用程序标识的匹配应用程序。如果系统找不到匹配的名称，将会在 {{site.data.keyword.cloud_notm}} 上打开“Web 和移动”仪表板，而不是打开特定的应用程序。

您可以提供应用程序名称，这样 CLI 会跳过基于文件夹或应用程序名称进行匹配。在这种情况下，CLI 会在 Web 浏览器中打开指定应用程序的控制台。  

运行以下命令来打开 Web 浏览器并转至应用程序的 Web 控制台。
```
ibmcloud dev console [applicationName]
```
{: codeblock}

## create
{: #create}

创建应用程序，并根据提示输入所有信息，包括资源类型、语言、入门模板工具包和 DevOps 工具链选项，包括 IBM Cloud Foundry 或 Cloud Foundry Enterprise Environment，以及 Kubernetes。这将在当前目录中创建应用程序。

要在当前目录中创建应用程序并使服务与其相关联，请运行以下命令：
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以通过 `debug` 命令来调试应用程序。在此之前，必须先使用带 `--debug` 自变量的 build 命令对应用程序完成构建。启动 `debug` 命令时，会启动一个容器，用于提供如 cli-config.yml 中的 `container-port-map-debug` 值所定义或如命令行上所指定的一个或多个调试端口。将您喜欢的调试工具连接到相应端口，然后可以如常调试应用程序。

首先编译应用程序：
```
ibmcloud dev build --debug
```
{: codeblock}

首先，在当前应用程序目录中运行以下命令来调试应用程序：
```
ibmcloud dev debug
```
{: codeblock}

要进行调试，请将调试工具连接到指定的端口。

要退出调试会话，请使用 `CTRL-C`。

### debug 命令参数
{: #debug-parameters}

以下参数是 `debug` 命令独有的，可帮助调试应用程序。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `container-port-map-debug`
{: #port-map-debug}

* 调试端口的端口映射。第一个值是要在主机操作系统中使用的端口，第二个值是容器中的端口：[host-port:container-port]。
* 用法：`ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* 该参数用于针对 DEBUG 用途构建代码。
* 用法：`ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* 该参数用于指定命令以在 tools 容器中启动调试。如果 `build-cmd-debug` 以调试方式启动应用程序，请使用此参数。
* 用法：`ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

使用 `delete` 命令可从 {{site.data.keyword.cloud_notm}} 空间中除去应用程序。您可以运行不带参数的命令来列出可用的应用程序，然后从编号列表中选择要删除的应用程序。应用程序代码和目录不会从本地磁盘空间中除去。

运行以下命令从 {{site.data.keyword.cloud_notm}} 中删除应用程序：
```
ibmcloud dev delete <applicationName>
```
{: codeblock}

{{site.data.keyword.cloud_notm}} 服务不会被除去。
{: note}

## deploy
{: #deploy}

可以将应用程序部署为 Cloud Foundry 应用程序或容器。

在将 Cloud Foundry 应用程序部署到 {{site.data.keyword.cloud_notm}} 之前，`manifest.yml` 文件必须存在于应用程序的根目录中。

在将应用程序部署为容器之前，必须在本地安装 [Kubernetes](https://kubernetes.io/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 和 [Helm](https://github.com/helm/helm){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。Helm 客户机版本不得高于 Helm 服务器版本。可以运行 `helm version` 来查看这两个版本。建议使用客户机版本 V2.4.2。

要在 Kubernetes 上部署应用程序，必须在 `cli-config.yml` 中将 `deploy-target` 指定为 `container`，或者使用 `-t container` 参数。

此外，还可以使用命令行自变量在 `cli-config.yml` 中指定配置 Kubernetes 部署所需的其他参数。如果未在 `cli-config.yml` 中定义这些参数，那么必须使用 `-t container` 参数进行部署。然后，系统会提示您输入所有其他值。

```yaml
chart-path: "chart/myapplication"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

在 `cli-config.yml` 中，可以选择在 `chart-path` 属性中定义 Helm chart 的位置，然后配置 `deploy-image-target`，如示例所示。这将使用 `cli-config.yml` 中的 `deploy-image-target` 元素，而不是 `chart/values.yml` 文件中的 `repository` 和 `tag` 元素。具体来说，要部署到 {{site.data.keyword.cloud_notm}}，请将配置元素 `ibm-cluster` 设置为您在 {{site.data.keyword.cloud_notm}} 中创建的 Kubernetes 集群的名称。

在当前应用程序目录中运行以下命令来构建应用程序：  
```
ibmcloud dev build
```
{: codeblock}

在当前应用程序目录中运行以下命令来部署应用程序：
```
ibmcloud dev deploy
```
{: codeblock}

### 部署到 {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

您可以部署到 {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment。要执行此操作，请使用 `ibmcloudtarget --cf` 为此环境配置您的本地环境，然后从该列表中选择正确的环境。然后，可以使用 `deploy` 命令，方法与 {{site.data.keyword.cloud_notm}} Public Cloud Foundry 的情况相同。

### deploy 命令参数
{: #deploy-parameters}

以下参数可以与 `deploy` 命令配合使用，也可以通过直接更新应用程序的 `cli-config.yml` 文件来使用。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `chart-path`
{: #chart-path}

* 用于容器部署的参数，可指定用于部署的 Helm chart 的位置。
* 用法：`ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* 参数（可选），用于指示要完成的部署类型。缺省部署类型为 buildpack。
* 用法：`ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* 作为部署的目标映像名称用于容器部署的参数。该值不得包含版本。例如：image-name:{version}，因为版本由 `deploy` 自动进行递增并附加到末尾。
* 用法：`ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* 参数（可选），用于定义将容器部署到 {{site.data.keyword.cloud_notm}} 的 Kubernetes 集群的名称
* 用法：`ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `主机 (host)`
{: #host}

* 参数（可选），用于定义部署到 Cloud Foundry 时应用程序的主机名。
* 用法：`ibmcloud dev deploy --host [hostname]`

#### `域 (domain)`
{: #domain}

* 参数（可选），用于定义部署到 Cloud Foundry 时应用程序的域。
* 用法：`ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

此命令用作诊断功能，以显示 {{site.data.keyword.dev_cli_notm}} CLI 的已安装依赖项的版本信息。此命令对于确定是否缺少任何依赖项或帮助调试问题很有帮助。

运行以下命令以显示已安装依赖项的版本：
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

使用选项来编辑应用程序，例如将应用程序与 {{site.data.keyword.cloud_notm}} 中已有的应用程序相连接，以及管理应用程序的 {{site.data.keyword.cloud_notm}} 服务及其 {{site.data.keyword.cloud_notm}} 工具链以部署到 IBM Cloud Kubernetes、Cloud Foundry 或 Cloud Foundry Enterprise Environment。对于与 {{site.data.keyword.cloud_notm}} 中的应用程序连接的本地应用程序，使用 `edit` 来添加新服务，将现有服务连接和断开连接，或者从帐户中除去现有服务。此外，可以创建或查看应用程序的 {{site.data.keyword.cloud_notm}} 工具链。在应用程序目录的根目录中运行以下命令：
```
ibmcloud dev edit
```
{: codeblock}

如果您的帐户上没有现有服务，此命令将显示服务组列表，您可以从中选择要连接到应用程序的服务。

但是，如果您的帐户上有任何现有服务，此命令将显示这些服务的列表以及每个服务是否已连接到应用程序。

* 对于连接的服务，您可以选择断开该服务与应用程序的连接，也可以将该服务从帐户中删除，从而使其与所连接的所有应用程序断开连接。

* 对于断开连接的服务，您可以选择将该服务连接到应用程序，也可以将该服务从帐户中删除。连接现有服务还会下载文件（如凭证或源代码）以便开始使用该服务。

您还可以向应用程序添加新服务，系统会提示您选择服务并下载其他文件（如凭证文件或源代码）以便开始使用新服务。

## enable
{: #enable}

允许现有应用程序进行 {{site.data.keyword.cloud_notm}} 部署。`enable` 命令尝试自动检测现有应用程序的语言，然后提示您输入其他必要信息。这将生成并添加可用于本地 Docker 容器、Cloud Foundry 部署、Cloud Foundry Enterprise Environment 部署或 Kubernetes 容器部署的文件。您可以手动运行 `deploy` 或使用 DevOps 工具链来利用所有部署环境。

登录到 {{site.data.keyword.cloud_notm}} 后，您可以选择将此本地应用程序与 {{site.data.keyword.cloud_notm}} 中已有的应用程序相连接，或创建新的 {{site.data.keyword.cloud_notm}} 应用程序。要利用 {{site.data.keyword.cloud_notm}} 功能（例如，各种服务和 DevOps 工具链），需要 {{site.data.keyword.cloud_notm}} 中的应用程序。为从 Git 存储库克隆的应用程序创建 {{site.data.keyword.cloud_notm}} 应用程序时，该 {{site.data.keyword.cloud_notm}} 应用程序会在其配置中包含此存储库。 

`enable` 是 Beta 功能。如果在启用应用程序时遇到困难，可查看我们的[故障诊断页面](/docs/cli/ts_createapps.html#troubleshoot)来获取帮助。特别是，`enable` 不适用于移动应用程序或框架。对于生成多个可部署资产的复杂应用程序，必须分别启用应用程序的每个组件。 

运行以下命令来启用当前目录中的现有应用程序：
```
ibmcloud dev enable
```
{: codeblock}

存在必要文件可提供应用程序语言检测，以确定项目结构是否有效。  

* 存在 `package.json` 文件可识别 Node.js 应用程序。
* 存在 `package.swift` 文件可识别 Swift 应用程序。
* 存在 `setup.py` 或 `requirements.txt` 文件可识别 Python 应用程序。
* 存在 `pom.xml` 或 `build.gradle` 文件可识别 Java 应用程序。
	* 存在 `pom.xml` 可识别 Maven 应用程序。
	* 存在 `build.gradle` 可识别 Gradle 应用程序。

（可选）您还可以使用 `--language` 自变量来覆盖检测到的应用程序语言。仅支持有效且完整的应用程序。enable 命令不会修改源代码。

### 启用语言选项
{: #enable-language-options}

语言选项包括：
* node
* swift
* python
* java-ee（解释为 Java&trade; - Java&trade; EE）
* java-mp（解释为 Java&trade; - Java&trade; MicroProfile）
* java-spring（解释为 Java&trade; - Spring Framework）

如果使用 `ibmcloud dev enable` 命令创建的文件与应用程序文件夹中的现有文件存在命名冲突，这些文件将使用 `.merge` 文件扩展名进行保存。  

### enable 命令参数
{: #enable-parameters}

以下参数可以与 `enable` 命令配合使用，也可以通过直接更新应用程序的 `cli-config.yml` 文件来使用。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `language`
{: #enable-language}

* 该参数用于指定要启用的应用程序语言。
* 用法：`ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* 该参数用于强制重新启用已启用的应用程序。
* 用法：`ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* 用于阻止在本地创建启用文件时在 {{site.data.keyword.cloud_notm}} 中创建应用程序的参数。
* 用法：`ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

获取所需的凭证，以便在应用程序中可以使用连接的服务。

## help
{: #help}

缺省情况下，如果未传入操作或自变量，或者如果提供了“help”操作，那么此命令会显示一般“帮助”文本。显示的一般帮助包括基本自变量的描述以及可用操作的列表。  

运行以下命令来显示一般帮助信息：
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

可以列出资源组中的所有 {{site.data.keyword.cloud_notm}} 应用程序。

运行以下命令来列出应用程序：
```
ibmcloud dev list
```
{: codeblock}

## run
{: #run}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以通过 `run` 命令来运行应用程序。在此之前，必须先使用 `build` 命令对应用程序完成构建。运行 `run` 命令时，将启动 run 容器，并按 `container-port-map` 参数所定义的方式公开端口。如果 run 容器 `Dockerfile` 不包含用于完成此步骤的入口点，那么会使用 `run-cmd` 参数来调用应用程序。

要使用多个容器来运行，应用程序必须包含 `cli-config.yml` 中指定的 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 文件，您也可以使用 `dockerfile-run` 命令参数来提供该文件。

首先编译应用程序：
```
ibmcloud dev build
```
{: codeblock}

在当前应用程序目录中运行以下命令来启动应用程序：
```
ibmcloud dev run
```
{: codeblock}

要退出会话，请使用 `CTRL-C`。

### run 命令参数
{: #run-parameters}

以下参数是 `run` 命令独有的，可帮助管理 run 容器内的应用程序。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `container-name-run`
{: #container-name-run2}

* run 容器的容器名称。
* 用法：`ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* 容器中要在运行时共享的位置。
* 用法：`ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* 主机系统上要在运行时在容器中共享的位置。
* 用法：`ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* run 容器的 Dockerfile。
* 如果打算使用多个容器来运行，那么此项应为 Compose 文件。
* 要使用多个 Compose 文件，请将文件名的逗号分隔列表括在双引号内。
* 用法：`ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* 用法：`ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* 要基于 `dockerfile-run` 创建的映像。
* 用法：`ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* 该参数用于在 run 容器中运行代码。如果映像要启动应用程序，请使用此参数。
* 用法：`ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以使用 `shell` 命令在 run 或 tools 容器内打开 shell。

方法是运行以下命令：
```
ibmcloud dev shell
```
{: codeblock}

{{site.data.keyword.dev_cli_short}} CLI 会将交互式 shell 打开到应用程序的 Docker 容器中。shell 命令的缺省目标容器由 `cli-config.yml` 文件中的 `container-shell-target` 值定义，其中有效值为 `run` 或 `tools`。如果未定义此值或指定了无效的值，那么缺省情况下 `shell` 命令会将 `tools` 容器设置为目标容器。shell 命令会将容器打开到相应 Dockerfile 中 `WORKDIR` 指令所指定的目录。如果 Dockerfile 中未列出 `WORKDIR`，那么会将容器根目录用作工作目录。有关更多信息，请参阅[此参考](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

或者，您可以决定将 `run` 或 `tools` 作为自变量传递给命令，这会启动该容器，并为该容器打开 shell。与此类似，可以使用 `container-name` 参数来传递要将 shell 打开到其中的容器的名称。但是，应该保留此标志用于没有容器在运行的情况。`run` 和 `tools` 自变量更灵活，并支持在当前有一个容器正在运行的情况下切换容器。例如，如果 tools 容器正在运行，而您执行了 `ibmcloud dev shell run`，那么 `tools` 容器会停止，而 `run` 容器会启动，反之亦然。

如果在执行 `shell` 命令时目标 `run` 或 `tools` 容器尚未运行，那么会启动目标容器。但是，会覆盖 Dockerfile 中的缺省 `Cmd` 或 `Entrypoint`，以直接启动到 shell 中，而不是启动服务器进程。这允许您启动 `run` 或 `tools` 容器，并使用自己的任意命令或定制命令来手动启动服务器。

您还可以使用 `container-shell` 参数指定要打开的 shell 可执行文件。缺省情况下，会使用 `/bin/sh`。如果您倾向于使用 bash shell，请将 `container-shell` 值指定为 `/bin/bash`；但是，请记住，bash 并非在所有 Linux&trade; 变体中都自动可用。

除了标志以外，传递给命令的其他任何自变量都会解析为打开 shell 时要运行的命令。如果提供了命令，那么容器内的 shell 会在运行该命令后退出并返回到终端。

例如，可以通过调用 `ibmcloud dev shell tools ls` 在 tools 容器 shell 内运行 Linux&trade; `ls` 命令。还可以通过将自变量括在引号内来指定要传递到 shell 命令执行中的其他标志，例如 `ibmcloud dev shell "ls -la"`。

### shell 命令参数
{: #shell-parameters}

#### `container-name`
{: #container-name}

* 要将 shell 打开到其中的容器的名称。
* 用法：`ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* 指定要在容器内运行的 shell（缺省值为 /bin/sh）。
* 用法：`ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以查询 {{site.data.keyword.dev_cli_short}} CLI 使用的容器（如 `container-name-run` 和 `container-name-tools` 所定义）的状态。

在当前应用程序目录中运行以下命令来检查容器状态：
```
ibmcloud dev status
```
{: codeblock}

[Status 命令参数](#command-parameters)

## stop
{: #stop}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以通过 `stop` 命令来停止容器。

要停止 `cli-config.yml` 文件中定义的 tools 和 run 容器，请运行：
```
ibmcloud dev stop
```
{: codeblock}

要停止 `cli-config.yml` 文件中未定义的容器，可以指定额外的命令行参数将其覆盖。如果在 `cli-config.yml` 文件或命令行中未指定任何容器，那么 stop 命令将直接返回。

### stop 命令参数
{: #stop-parameters}

以下参数用于 `stop` 命令。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `container-name-run`
{: #container-name-run}

* run 容器的容器名称。
* 用法：`ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* tools 容器的容器名称。
* 用法：`ibmcloud dev stop --container-name-tools [<applicationName>]`

## test
{: #test}

如果使用 Windows&trade;，那么必须运行 Windows&trade; 10 专业版或更高版本。

可以通过 `test` 命令来测试应用程序。在此之前，必须先使用 `build --debug` 命令对应用程序完成构建。然后，tools 容器用于对应用程序启动 `test-cmd`。

首先编译应用程序：
```
ibmcloud dev build --debug
```
{: codeblock}

运行以下命令来测试应用程序：
```
ibmcloud dev test
```
{: codeblock}

### test 命令参数
{: #test-parameters}

以下参数是 `test` 命令独有的。有一些[其他参数](#command-parameters)是与其他命令共享的。

#### `test-cmd`
{: #test-cmd}

* 该参数用于指定命令以在 tools 容器中测试代码。
* 用法：`ibmcloud dev test --test-cmd /the/test/command`

## view
{: #view}

可以通过 `view` 命令来查看应用程序部署到的 URL。在要查看的应用程序的根目录中运行此命令。`view` 命令还会在缺省浏览器中打开相应 URL。

对于部署到 Cloud Foundry 的应用程序，URL 由应用程序的主机名和应用程序的域组成。

对于部署到 Kubernetes 的应用程序，URL 由其部署到的节点的 IP 地址和公共端口组成。如果该命令确定应用程序已部署到 Kubernetes，那么 CLI 工具会提示进行确认。如果您指定应用程序未部署到 Kubernetes，那么将显示 Cloud Foundry URL。如果您预期该命令显示部署到 Kubernetes 的应用程序的 URL，请确保 `cli-config.yml` 包含 `chart-path` 的条目，或者通过命令行提供该条目，如[此处](#chart-path)所示。

运行以下命令来查看应用程序：
```
ibmcloud dev view
```
{: codeblock}

### view 命令参数
{: #view-parameters}

以下参数是 `view` 命令独有的。

#### `deploy-target`

* 参数（可选），用于指示要绕过提示的部署类型。
* 用法：`ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* 该参数用于指定不打开浏览器。
* 用法：`ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* 要附加到 Cloud Foundry 和 Kubernetes 应用程序 URL 的项目根目录。
* 用法：`ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* 参数（可选），用于在设置目标容器部署时定义 Kubernetes 集群的名称。
* 用法：`ibmcloud dev view --ibm-cluster [cluster-name]`

## compound 命令
{: #compound}

可以通过使用 `/` 定界符来分隔 {{site.data.keyword.cloud_notm}} Developer Tools 命令，从而在一个命令行语句中运行多个命令。在指定 compound 命令后，可以使用其他命令行标志。以下命令是可以如何使用 compound 命令的示例：
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

所有标志都必须尾随最后一个命令，并应用于与该标志相关联的所有命令。以 `ibmcloud dev build/deploy/view -t container --trace` 为例，`--trace` 标志会应用于所有三个命令，但 `-t` 仅会应用于最后两个命令，而不会应用于 `build` 命令。

以下命令可用于此功能：
`build、debug、deploy、get-credentials、run、stop、test 和 view`

如果某个命令出于任何原因而失败，那么不会执行后续命令。

如果 `debug` 或 `run` 后跟任何命令，那么仅当 `debug` 或 `run` 以不同于在当前终端窗口中终止进程的方式终止时，执行才会继续。`CTRL+C` 会终止进程，而不会运行后续命令。例如，可以在其他终端窗口中运行 `ibmcloud dev stop` 来停止正在运行的容器，然后继续执行到下一个命令。

## 用于 build、debug、run 和 test 的参数
{: #command-parameters}

以下参数可以与 `build|debug|run|test` 命令配合使用，也可以通过直接更新应用程序的 `cli-config.yml` 文件来使用。还有额外的参数可用于 [`debug`](#debug-parameters) 和 [`run`](#run-parameters) 命令。

在命令行上输入的命令参数优先于 `cli-config.yml` 配置。
{: note}

#### `config-file`  
{: #config-file}

* 指定要用于命令的 cli-config.yml 文件。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* run 容器的容器名称。
* 用法：`ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* tools 容器的容器名称。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* 主机上要共享用于构建、调试和测试的位置。
* 用法：`ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* 容器中要共享用于构建、调试和测试的位置。
* 用法：`ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* 容器的端口映射。第一个值是要在主机操作系统中使用的端口，第二个值是容器中的端口：[host-port:container-port]。
* 用法：`ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* tools 容器的 Dockerfile。
* 用法：`ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* 要基于 `dockerfile-tools` 创建的映像。
* 用法：`ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* 使用此选项可定义主机系统和 run 容器之间的安装。
* `host-path-run` 和 `container-path-run` 值会插入到此列表的开头。
* 作为最佳实践并且为了防止意外结果，可以使用相同的安装设置来构建和运行。
* 用法：`ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* 使用此选项可定义主机系统和 tools 容器之间的安装。
* `host-path-tools` 和 `container-path-tools` 值会插入到此列表的开头。* 作为最佳实践并且为了防止意外结果，可以使用相同的安装设置来构建和调试。
* 用法：`ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* 该参数用于指定命令以针对除 DEBUG 之外的所有用途构建代码。
* 用法：`ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* 使用此参数可提供详细输出。
* 用法：`ibmcloud dev <build|debug|run|test> --trace`
