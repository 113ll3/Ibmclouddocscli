---

copyright:

   years: 2017, 2018

lastupdated: "2018-08-28"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# {{site.data.keyword.dev_cli_notm}} CLI 外掛程式 (ibmcloud dev) 指令
{: #idt-cli}

版本：1.2.0
發表日期：2018 年 3 月 8 日

到 2018 年五月為止，{{site.data.keyword.Bluemix_notm}} CLI 指令已從 `bluemix` 和 `bx` 變更為 `ibmcloud`。不過，您仍然可以使用 `bluemix` 和 `bx` CLI 指令，直到未來移除它們為止。
{: tip}

請使用下列 {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) 指令來建立應用程式、管理、部署、除錯及測試它。

- [build](#build)：在本端容器中建置應用程式
- [code](#code)：下載應用程式的程式碼
- [console](#console)：開啟應用程式的 IBM Cloud 主控台
- [create](#create)：建立新的應用程式，並讓您選擇新增服務
- [debug](#debug)：在本端容器中針對您的應用程式進行除錯
- [delete](#delete)：從您的空間刪除應用程式
- [deploy](#deploy)：將應用程式部署至 IBM Cloud
- [diag](#diag)：顯示已安裝之相依關係的版本資訊
- [edit](#edit)：在現有應用程式裡新增或移除服務
- [enable](#enable)：更新現有應用程式以便搭配 IBM Cloud Developer Tools 使用
- [get-credentials](#get-credentials)：取得應用程式所需的認證，以啟用連接之 IBM Cloud 服務的使用
- [help](#help)：CLI 語法和引數的說明
- [list](#list)：列出資源群組中的所有 IBM Cloud 應用程式
- [run](#run)：在本端容器中執行應用程式
- [shell](#shell)：開啟 Shell 以連接至本端容器
- [status](#status)：檢查 CLI 所使用容器的狀態
- [stop](#stop)：停止容器
- [test](#test)：在本端容器中測試應用程式
- [view](#view)：檢視應用程式的部署 URL，以便測試和檢視
- [複合指令](#compound)：在單一指令行陳述式中執行多個指令



## build
{: #build}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以使用 `build` 指令來建置應用程式。`test`、`debug` 和 `run` 指令預期會發現已編譯的應用程式，因此您必須先執行 `build` 作業。  

`build-cmd-debug` 配置元素用於為除了 `run` 之外的所有使用情形而建置應用程式。建置應用程式以便進行除錯的方法是指定指令行選項 `--debug`。`build-cmd-run` 配置元素用於建置應用程式以便搭配 `run` 指令使用之時。

若要使用多個容器建置，您的應用程式必須包含 [Compose](https://docs.docker.com/compose/overview/) 檔案（指定於 `cli-config.yml` 中），或是您可以使用 `dockerfile-tools` 指令參數來提供檔案。如需相關資訊，請參閱 [Compose 檔案](/docs/apps/projects/compose_file.html)。

在現行應用程式目錄中執行下列指令，以建置您的應用程式：  

```
ibmcloud dev build [--debug]
```
{: codeblock}



## code
{: #code}

使用 `code` 指令以下載先前建立的應用程式，其中包含應用程式範本程式碼以及 {{site.data.keyword.Bluemix_notm}} 的配置檔。當您需要擷取已建立應用程式的第二個副本時，這十分有用。

執行下列指令，以從指定的應用程式下載程式碼。

```
ibmcloud dev code <applicationName>
```
{: codeblock}


## console
{: #console}

使用 `console` 指令，以在 IBM Cloud 上將 Web 瀏覽器開啟到應用程式的 Web 主控台。您可以從應用程式資料夾內執行 `ibmcloud dev console` 指令，而 CLI 會嘗試在 IBM Cloud 上尋找應用程式 ID 與現行目錄相同的相符應用程式。如果系統找不到相符名稱，則會在 IBM Cloud 上開啟 Web 及「行動」儀表板，而非特定應用程式。

您可以提供應用程式名稱，CLI 便會跳過根據資料夾/應用程式名稱進行比對。在此情況下，CLI 會在 Web 瀏覽器中開啟具名應用程式的主控台。  

執行下列指令，以將 Web 瀏覽器開啟到應用程式的 Web 主控台。

```
ibmcloud dev console [applicationName]
```
{: codeblock}


## create
{: #create}

建立應用程式，並提示輸入所有資訊，包括資源類型、語言、入門範本套件及「DevOps 工具鏈」選項。應用程式會在現行目錄中建立。

若要在現行目錄中建立應用程式，並讓服務與其相關聯，請執行下列指令：

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以透過 `debug` 指令，對您的應用程式進行除錯。必須先搭配使用 build 指令與 `--debug` 引數，針對應用程式完成建置。當您啟動 `debug` 指令時，會啟動容器，以提供 cli-config.yml 中 `container-port-map-debug` 值所定義或指令行上所指定的一個以上除錯埠。將您的最愛除錯工具連接至一個以上的埠，而且可以正常地對應用程式進行除錯。

首先，請編譯您的應用程式：

```
ibmcloud dev build --debug
```
{: codeblock}

若要開始，請在現行應用程式目錄中執行下列指令，以對應用程式進行除錯：

```
ibmcloud dev debug
```
{: codeblock}

若要除錯，請將除錯工具連接至指定的埠。

若要結束除錯階段作業，請使用 `CTRL-C`。


### debug 指令參數
{: #debug-parameters}

下列參數專用於 `debug` 指令，並且可協助您對應用程式進行除錯。還有[其他參數](#command-parameters)與其他指令共用。

#### `container-port-map-debug`
{: #port-map-debug}

* 除錯埠的埠對映。第一個值是要在主機 OS 中使用的埠，第二個值是容器中的埠 [host-port:container-port]。
* 用法：`ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* 用來建置 DEBUG 程式碼的參數。
* 用法：`ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* 用來指定指令以在 tools 容器中呼叫除錯的參數。如果 `build-cmd-debug` 以除錯模式啟動應用程式，請使用此參數。
* 用法：`ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

使用 `delete` 指令，以移除 {{site.data.keyword.Bluemix}} 空間中的應用程式。您可以執行沒有參數的指令來列出可用的應用程式，然後從編號清單中選取要刪除的應用程式。應用程式碼及目錄不會從本端磁碟空間移除。

執行下列指令，以從 {{site.data.keyword.Bluemix}} 刪除應用程式：

```
ibmcloud dev delete <applicationName>
```
{: codeblock}


**附註：****未**移除 {{site.data.keyword.Bluemix}} 服務。


## deploy
{: #deploy}

您可以將應用程式部署為 Cloud Foundry 應用程式或容器。

在當成 Cloud Foundry 應用程式部署至 {{site.data.keyword.Bluemix}} 之前，`manifest.yml` 檔案必須存在於應用程式的根目錄中。

將應用程式部署為容器之前，您必須在本端安裝 [Kubernetes](https://kubernetes.io/) 及 [Helm](https://github.com/kubernetes/helm)。請確定 Helm 用戶端版本未比 Helm 伺服器版本還要新。您可以執行 `helm version` 來尋找這兩項。建議使用 2.4.2 版作為用戶端版本。

若要在 Kubernetes 上部署應用程式，您必須在 `cli-config.yml` 中指定 `deploy-target` 作為 `container`，或使用參數 `-t container`。

配置 Kubernetes 部署所需的其他參數也可以指定於 `cli-config.yml`，如下所示，或是使用指令行引數。如果您未在 `cli-config.yml` 中定義這些參數，則必須使用 `-t container` 參數進行部署，而且系統會提示您輸入所有其他值。

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

在 `cli-config.yml` 中，您可以選擇在 `chart-path` 內容中定義 Helm 圖表位置，並配置 `deploy-image-target`（如範例中所示）。使用 `cli-config.yml` 中的 `deploy-image-target` 元素，而不是 `chart/values.yml` 檔案中的 `repository` 及 `tag` 元素。若要特別部署至 {{site.data.keyword.Bluemix}}，請將配置元素 `ibm-cluster` 設為您在 {{site.data.keyword.Bluemix}} 中建立的 Kubernetes 叢集名稱（如[指導教學：建立叢集](/docs/containers/cs_tutorials.html#cs_cluster_tutorial)中所述）。

如需佈建、配置及部署至 Kubernetes 叢集的相關資訊，請參閱[在 Kubernetes 上部署可擴充 Web 應用程式](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes)指導教學。

在現行應用程式目錄中執行下列指令，以建置您的應用程式：  

```
ibmcloud dev build
```
{: codeblock}

在現行應用程式目錄中執行下列指令，以部署您的應用程式：

```
ibmcloud dev deploy
```
{: codeblock}


### deploy 指令參數
{: #deploy-parameters}

下列參數可以與 `deploy` 指令搭配使用，或直接更新應用程式的 `cli-config.yml` 檔案予以使用。還有[其他參數](#command-parameters)與其他指令共用。

#### `chart-path`
{: #chart-path}

* 這是用於容器部署的參數，用來指定部署所用的 Helm 圖表位置。
* 用法：`ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* 選擇性地用來指出要完成之部署類型的參數。預設部署類型是 buildpack。
* 用法：`ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* 這是用於容器部署的參數，用來指定部署的目標映像名稱（例如標記至 Docker 登錄）。值不得包括版本（例如：image-name:{version}），因為版本會自動遞增並附加 `deploy`。
* 用法：`ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* 這是對 {{site.data.keyword.Bluemix}} 進行容器部署時選擇性使用之參數，用來定義 Kubernetes 叢集名稱
* 用法：`ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* 部署至 Cloud Foundry 時，選擇性地用來定義應用程式主機名稱的參數
* 用法：`ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* 部署至 Cloud Foundry 時，選擇性地用來定義應用程式網域的參數
* 用法：`ibmcloud dev deploy --domain [domain]`


## diag
{: #diag}

這個指令用來作為診斷，以顯示 {{site.data.keyword.dev_cli_notm}} CLI 之已安裝相依關係的版本資訊。這尤其有助於判斷您是否遺漏任何相依關係，或是協助進行問題除錯。

執行下列指令，以顯示已安裝相依關係的版本：

```
ibmcloud dev diag
```
{: codeblock}


## edit
{: #edit}

藉由新增服務、連接現有服務和將其中斷連線，或移除現有服務，來編輯您的應用程式。請在應用程式目錄的根目錄執行下列指令：

```
ibmcloud dev edit
```
{: codeblock}

如果您在帳戶上沒有任何現有服務，這個指令將顯示服務群組的清單，供您選取要連接至應用程式的服務。

不過，如果您在帳戶上有任何現有服務，這個指令將顯示那些服務的清單，以及每個服務是否連接至應用程式。

選取已連接的服務會讓您選擇是要從應用程式將服務中斷連線，還是從帳戶刪除服務，因而將它從已連接的所有應用程式中斷連線。

選取已中斷連線的服務會讓您選擇是要將該服務連接至應用程式，還是從帳戶刪除服務。連接現有的服務也將下載例如認證檔或原始碼等檔案，以便開始使用該服務。

您也可以選取新增服務至應用程式的選項。這會引導您完成選取服務的提示，並且將下載其他檔案，例如認證檔或原始碼，以便開始使用新服務。



## enable
{: #enable}

啟用現有應用程式以進行 {{site.data.keyword.Bluemix_notm}} 部署。`enable` 指令會嘗試自動偵測現有應用程式的語言，然後提示您輸入必要的其他資訊。這會產生及新增可用於本端 Docker 容器、CloudFoundry 部署或「Kubernetes/容器部署」的檔案。

執行下列指令，以在現行目錄中啟用現有應用程式進行 {{site.data.keyword.Bluemix_notm}} 部署：

```
ibmcloud dev enable
```
{: codeblock}

如有必要檔案存在，便會提供對有效專案結構的應用程式語言偵測。  

* `package.json` 檔的存在會識別 Node.js 應用程式。
* `package.swift` 檔的存在會識別 Swift 應用程式。
* `setup.py` 或 `requirements.txt` 檔的存在會識別 Python 應用程式。
* `pom.xml` 或 `build.gradle` 檔的存在會識別 Java 應用程式。
	* `pom.xml` 檔的存在會識別 Maven 應用程式。
	* `build.gradle` 檔的存在會識別 Gradle 應用程式。

您也可以選擇性地使用 `--language` 引數來置換偵測到的應用程式語言。不過，只支援有效且完整的應用程式。enable 指令不會修改原始碼。

語言選項包括：
* node
* swift
* python
* java-ee（解譯為 Java - Java EE）
* java-mp（解譯為 Java - Java MicroProfile）
* java-spring（解譯為 Java - Spring Framework）

如果使用 `ibmcloud dev enable` 指令所建立檔案的名稱與應用程式資料夾中的現有檔案衝突，則會儲存為 `.merge` 副檔名。  

### enable 指令參數
{: #enable-parameters}

下列參數可以與 `enable` 指令搭配使用，或直接更新應用程式的 `cli-config.yml` 檔案予以使用。還有[其他參數](#command-parameters)與其他指令共用。

#### `language`
{: #enable-language}

* 用來指定要啟用之應用程式語言的參數。
* 用法：`ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* 用來強制重新啟用已啟用應用程式的參數。
* 用法：`ibmcloud dev enable -f|--force`


## get-credentials
{: #get-credentials}

取得應用程式所需的認證，以啟用連接服務的使用。


## help
{: #help}

依預設，如果未傳入任何動作或引數，或如果提供 'help' 動作，則此指令會顯示一般「說明」文字。顯示的一般說明包括基本引數的說明，以及可用動作的清單。  

執行下列指令，以顯示一般說明資訊：

```
ibmcloud dev help
```
{: codeblock}


## list
{: #list}

您可以列出資源群組中的所有 {{site.data.keyword.Bluemix_notm}} 應用程式。

執行下列指令，以列出您的應用程式：

```
ibmcloud dev list
```
{: codeblock}


## run
{: #run}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以透過 `run` 指令來執行您的應用程式。必須先使用 `build` 指令，針對應用程式完成建置。當您呼叫 `run` 指令時，會啟動 run 容器，並公開 `container-port-map` 參數所定義的埠。如果 run 容器 Dockerfile 未包含進入點以完成此步驟，則 `run-cmd` 參數可用來呼叫應用程式。

若要使用多個容器執行，您的應用程式應該包含 [Compose](https://docs.docker.com/compose/overview/) 檔案（指定於 `cli-config.yml` 中），也可以使用 `dockerfile-run` 指令參數來提供檔案。如需相關資訊，請參閱 [Compose 檔案](/docs/apps/projects/compose_file.html)。

首先，請編譯您的應用程式：

```
ibmcloud dev build
```
{: codeblock}

在現行應用程式目錄中執行下列指令，以啟動您的應用程式：

```
ibmcloud dev run
```
{: codeblock}

若要結束階段作業，請使用 `CTRL-C`。


### run 指令參數
{: #run-parameters}

下列參數專用於 `run` 指令，並且可協助您在 run 容器內管理您的應用程式。還有[其他參數](#command-parameters)與其他指令共用。

#### `container-name-run`
{: #container-name-run2}

* run 容器的容器名稱。
* 用法：`ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* 執行時，容器中要共用的位置。
* 用法：`ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* 執行時，主機系統上要在容器中共用的位置。
* 用法：`ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* run 容器的 Dockerfile。
* 如果您打算使用多個容器來執行，這應該是 Compose 檔。
* 若要使用多個 Compose 檔，請用雙引號括住以逗點區隔的檔名清單。
* 用法：`ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* 用法：`ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* 要從 `dockerfile-run` 建立的映像檔。
* 用法：`ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* 用來在 run 容器中執行程式碼的參數。如果您的映像檔會啟動應用程式，請使用此參數。
* 用法：`ibmcloud dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以使用 `shell` 指令，在 run 或 tools 容器內開啟 Shell。

只要執行下列指令：

```
ibmcloud dev shell
```

{{site.data.keyword.dev_cli_short}} CLI 會開啟互動式 Shell，以連接至應用程式的 Docker 容器。Shell 指令的預設目標容器是由 `cli-config.yml` 檔案中的 `container-shell-target` 值所定義，而有效值是 `run` 或 `tools`。如果未定義此值，或指定無效值，則依預設 `shell` 指令會以 `tools` 容器為目標。shell 指令會將容器開啟到對應 Dockerfile 中 `WORKDIR` 指示所指定的目錄。如果 Dockerfile 中未列出 `WORKDIR`，則會使用容器根目錄作為工作目錄。如需相關資訊，請參閱[此參照](https://docs.docker.com/engine/reference/builder/#workdir)。

或者，您可以決定傳遞 `run` 或 `tools` 作為指令的引數，那麼便會啟動該容器，且會開啟 Shell 以連接該容器。同樣地，您可以使用 `container-name` 參數，傳遞您想要以 Shell 方式連接的容器名稱。不過，此旗標應該保留用於沒有容器在執行中的情況。`run` 和 `tools` 引數更有彈性，而且可讓您在目前執行中的容器之間切換。例如，如果 tools 容器在執行中，且您執行 `ibmcloud dev shell run`，則會停止 `tools` 容器，並啟動 `run` 容器，反之亦然。

如果在您執行 `shell` 指令時，目標 `run` 或 `tools` 容器尚未執行，則會啟動目標容器。不過，Dockerfile 中的預設 `Cmd` 或 `Entrypoint` 會置換成直接啟動到 Shell，而不是啟動伺服器處理程序。這可讓您啟動 `run` 或 `tools` 容器，並使用您自己的任意或自訂指令手動啟動伺服器。


您也可以使用 `container-shell` 參數，來指定您要開啟的 Shell 執行檔。依預設，會使用 `/bin/sh`。如果您偏好使用 Bash Shell，請將 `container-shell` 值指定為 `/bin/bash`；不過，請記住，不會在所有 Linux 變式中自動提供 Bash。

您在旗標後面傳遞給指令的任何其他引數都會剖析為要在開啟 Shell 時執行的指令。如果您提供要執行的指令，則容器內的 Shell 會在執行指令時結束並回到您的終端機。

例如，您可以呼叫 `ibmcloud dev shell tools ls`，以在 tools 容器 Shell 內執行 Linux `ls` 指令。您也可以使用引號括住引數（例如 `ibmcloud dev shell "ls -la"`），來指定要傳入 Shell 指令執行的其他旗標。

### shell 指令參數
{: #shell-parameters}

#### `container-name`
{: #container-name}

* 您想要以 Shell 方式連接的容器名稱。
* 用法：`ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* 指定要在容器內執行的 Shell（預設值是 /bin/sh）
* 用法：`ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以查詢 `container-name-run` 及 `container-name-tools` 所定義之 {{site.data.keyword.dev_cli_short}} CLI 所使用容器的狀態。

在現行應用程式目錄中執行下列指令，以檢查容器狀態：

```
ibmcloud dev status
```
{: codeblock}


[Status 指令參數](#command-parameters)


## stop
{: #stop}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以透過 `stop` 指令來停止您的容器。

若要停止您 `cli-config.yml` 檔案定義的 tools 和 run 容器，請執行：

```
ibmcloud dev stop
```
{: codeblock}

若要停止未在 `cli-config.yml` 檔中定義的容器，您可以指定額外的指令行參數來置換它。如果在 `cli-config.yml` 檔或指令行中未指定任何容器，則 stop 指令會直接傳回。

### stop 指令參數
{: #stop-parameters}

下列參數用於 `stop` 指令。還有[其他參數](#command-parameters)與其他指令共用。

#### `container-name-run`
{: #container-name-run}

* run 容器的容器名稱。
* 用法：`ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* tools 容器的容器名稱。
* 用法：`ibmcloud dev stop --container-name-tools [<applicationName>]`



## test
{: #test}

如果您是使用 Windows&trade;，則必須執行 Windows 10 Pro 或更新版本。

您可以透過 `test` 指令來測試您的應用程式。必須先使用 `build --debug` 指令，針對應用程式完成建置。然後，會使用 tools 容器來為應用程式呼叫 `test-cmd`。

首先，請編譯您的應用程式：

```
ibmcloud dev build --debug
```
{: codeblock}

執行下列指令，以測試您的應用程式：

```
ibmcloud dev test
```
{: codeblock}


### test 指令參數
{: #test-parameters}

下列參數專屬於 `test` 指令。還有[其他參數](#command-parameters)與其他指令共用。

#### `test-cmd`
{: #test-cmd}

* 用來指定指令以在 tools 容器中測試程式碼的參數。
* 用法：`ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

您可以透過 `view` 指令，來檢視應用程式所部署到的 URL。請在您要檢視的應用程式的根目錄中執行此指令。`view` 指令也會在預設瀏覽器中開啟 URL。

對於部署至 Cloud Foundry 的應用程式，URL 會包含應用程式的主機名稱及應用程式的網域。

對於部署至 Kubernetes 的應用程式，URL 包含部署它的節點 IP 位址及公用埠。如果指令判定應用程式已部署至 Kubernetes，則 CLI 工具會提示進行確認。如果您指定應用程式實際上未部署至 Kubernetes，則會顯示 Cloud Foundry URL。如果您預期指令顯示 Kubernetes 已部署應用程式的 URL，但未顯示，則請確定 `cli-config.yml` 包含 `chart-path` 的項目，或透過指令行提供它（如[這裡](#chart-path)所示）。

執行下列指令，以檢視您的應用程式：

```
ibmcloud dev view
```
{: codeblock}

### view 指令參數
{: #view-parameters}

下列參數專屬於 `view` 指令。

#### `deploy-target`

* 選擇性地用來指出要略過提示之部署類型的參數。
* 用法：`ibmcloud dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* 用來指定不要開啟瀏覽器的參數。
* 用法：`ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* 要附加至 Cloud Foundry 及 Kubernetes 應用程式 URL 的專案根目錄
* 用法：`ibmcloud dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* 以容器部署為目標時，選擇性地用來定義 Kubernetes 叢集名稱的參數
* 用法：`ibmcloud dev view --ibm-cluster [cluster-name]`


## 複合指令
{: #compound}

您可以在一個指令行陳述式中執行多個指令，方法是使用 `/` 定界字元來區隔 {{site.data.keyword.Bluemix_notm}} Developer Tools 指令。在您指定複合指令之後，可以指定其他指令行旗標。下列指令是如何使用複合指令的範例：

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

所有旗標都必須追蹤最終指令，並會套用至與該旗標相關聯的所有指令。在上面的最終範例中，`--trace` 旗標適用於所有 3 個指令，但 `-t` 只適用於最後 2 個指令，因此不會套用至 `build` 指令。

這些指令可以與此特性搭配使用：`build、debug、deploy、get-credentials、run、stop、test、view`

如果有一個指令因任何原因而失敗，則不會執行後續指令。

如果 `debug` 或 `run` 後面有任何指令，則只有在透過從現行終端機視窗結束處理程序以外的方式終止 `debug` 或 `run` 時，才會繼續執行。`CTRL+C` 將會結束處理程序，而不會執行後續指令。例如，您可以從另一個終端機視窗執行 `ibmcloud dev stop`，以停止執行中容器並繼續執行到下一個指令。


## build、debug、run 及 test 的參數
{: #command-parameters}

下列參數可以與 `build|debug|run|test` 指令搭配使用，或直接更新應用程式的 `cli-config.yml` 檔案予以使用。額外參數適用於 [`debug`](#debug-parameters) 及 [`run`](#run-parameters) 指令。

**附註**：指令行上所輸入指令參數的優先順序高於 `cli-config.yml` 配置。

#### `config-file`  
{: #config-file}

* 指定要用於指令的 cli-config.yml 檔案。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* run 容器的容器名稱。
* 用法：`ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* tools 容器的容器名稱。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* 主機上要共用以進行建置、除錯、測試的位置。
* 用法：`ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* 容器中要共用以進行建置、除錯、測試的位置。
* 用法：`ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* 容器的埠對映。第一個值是要在主機 OS 中使用的埠，第二個值是容器中的埠 [host-port:container-port]。
* 用法：`ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* tools 容器的 Dockerfile。
* 用法：`ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* 要從 `dockerfile-tools` 建立的映像檔。
* 用法：`ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* 使用此選項來定義主機系統與 run 容器之間的裝載。
* 在此清單的開頭插入 `host-path-run` 及 `container-path-run` 值。
* 作為最佳作法並防止非預期的結果，您應該使用相同的裝載設定來建置並執行。
* 用法：`ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* 使用此選項來定義主機系統與 tools 容器之間的裝載。
* `host-path-tools` 及 `container-path-tools` 值會插入至此清單的開頭。
* 作為最佳作法並防止非預期的結果，您應該使用相同的裝載設定來建置並除錯。
* 用法：`ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* 用來指定指令以建置所有用法的程式碼（但 DEBUG 除外）的參數。
* 用法：`ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* 使用此參數來提供詳細輸出。
* 用法：`ibmcloud dev <build|debug|run|test> --trace`
