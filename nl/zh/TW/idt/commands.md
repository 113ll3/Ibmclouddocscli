---

copyright:
   years: 2017, 2019
lastupdated: "2019-06-10"

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

# {{site.data.keyword.dev_cli_notm}} CLI 外掛程式 (ibmcloud dev) 指令
{: #idt-cli}

版本：2.1.18
發行日期：2019 年 3 月 28 日

自 2018 年 5 月開始，{{site.data.keyword.cloud}} CLI 指令 `bluemix` 及 `bx` 現在是 `ibmcloud`。不過，您仍然可以使用 `bluemix` 及 `bx` CLI 指令，直到未來移除它們為止。
{: tip}

請使用 {{site.data.keyword.dev_cli_notm}} CLI (`ibmcloud dev`) 指令來建立、管理、部署、除錯及測試應用程式。

使用[複合指令](#compound)，在單一指令行陳述式中執行多個指令。
{: tip}

## build
{: #build}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以使用 `build` 指令來建置應用程式。`test`、`debug` 及 `run` 指令預期會發現已編譯的應用程式，因此您必須先執行 `build` 作業。

`build-cmd-debug` 配置元素用於為除了 `run` 之外的所有使用情形而建置應用程式。建置應用程式以便進行除錯的方法是指定指令行選項 `--debug`。`build-cmd-run` 配置元素用於建置應用程式以搭配使用 `run` 指令。

若要使用多個容器來建置，您的應用程式必須有 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 檔案（指定於 `cli-config.yml` 中），或者您可以使用 `dockerfile-tools` 指令參數來提供檔案。

在現行應用程式目錄中執行下列指令，以開始建置：  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

使用 `code` 指令以下載先前建立的應用程式，其中包含應用程式範本程式碼以及 {{site.data.keyword.cloud_notm}} 的配置檔。當您需要擷取應用程式的第二個副本時，可以使用這個指令。

執行下列指令，以從指定的應用程式下載程式碼。
```
ibmcloud dev code <appName>
```
{: codeblock}

## console
{: #console}

使用 `console` 指令，以在 {{site.data.keyword.cloud_notm}} 上將 Web 瀏覽器開啟到應用程式的 Web 主控台。您可以從應用程式資料夾內執行 `ibmcloud dev console` 指令。CLI 會嘗試在 {{site.data.keyword.cloud_notm}} 上尋找應用程式 ID 與現行目錄相同的相符應用程式。如果系統找不到相符名稱，則會在 {{site.data.keyword.cloud_notm}} 上開啟 **Web 及行動**儀表板，而非特定應用程式。

您可以提供應用程式名稱，CLI 即會跳過根據資料夾或應用程式名稱進行比對。在此情況下，CLI 會在 Web 瀏覽器中開啟具名應用程式的主控台。  

執行下列指令，將 Web 瀏覽器開啟到應用程式的 Web 主控台。
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

建立應用程式，以提示您輸入所有資訊，包括資源類型、語言、入門範本套件及 DevOps 工具鏈選項。這些選項包括 IBM Cloud Foundry 或 Cloud Foundry Enterprise Environment，以及 Kubernetes。應用程式會在現行目錄中建立。

若要在現行目錄中建立應用程式，並讓服務與其相關聯，請執行下列指令：
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以透過 `debug` 指令，對您的應用程式進行除錯。必須先搭配使用 build 指令與 `--debug` 引數，針對應用程式完成建置。當您啟動 `debug` 指令時，會啟動容器，以提供 cli-config.yml 中 `container-port-map-debug` 值所定義或指令行上所指定的一個以上除錯埠。將您的最愛除錯工具連接至一個以上的埠，就可以正常地對應用程式進行除錯。

首先，請編譯您的應用程式：
```
ibmcloud dev build --debug
```
{: codeblock}

若要開始，請在現行應用程式目錄中執行下列指令，以開始除錯：
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

* 除錯埠的埠對映。第一個值是要在主機 OS 中使用的埠，第二個值是容器中的埠 [`host-port:container-port`]。
* 用法：`ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* 用來建置 DEBUG 程式碼的參數。
* 用法：`ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* 用來指定指令以在 tools 容器中開始除錯的參數。如果 `build-cmd-debug` 以除錯模式啟動應用程式，請使用此參數。
* 用法：`ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

使用 `delete` 指令，以移除 {{site.data.keyword.cloud_notm}} 空間中的應用程式。您可以執行沒有參數的指令來列出可用的應用程式，然後從編號清單中選取要刪除的應用程式。不會從本端磁碟空間移除應用程式碼及目錄。

執行下列指令，以從 {{site.data.keyword.cloud_notm}} 刪除應用程式：
```
ibmcloud dev delete <appName>
```
{: codeblock}

未移除 {{site.data.keyword.cloud_notm}} 服務。
{: note}

## deploy
{: #deploy}

您可以將應用程式部署為 Cloud Foundry 應用程式或容器。

在您將 Cloud Foundry 應用程式部署至 {{site.data.keyword.cloud_notm}} 之前，`manifest.yml` 檔案必須存在於應用程式的根目錄中。

在您將應用程式部署為容器之前，必須在本端安裝 [Kubernetes](https://kubernetes.io/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 及 [Helm](https://github.com/helm/helm){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。Helm 用戶端版本不得比 Helm 伺服器版本還要新。您可以執行 `helm version` 來尋找這兩者。建議使用 2.4.2 版作為用戶端版本。

若要在 Kubernetes 上部署應用程式，您必須在 `cli-config.yml` 中指定 `deploy-target` 作為 `container`，或使用參數 `-t container`。

使用指令行引數，也可以將配置 Kubernetes 部署所需的其他參數指定於 `cli-config.yml` 中。如果您未在 `cli-config.yml` 中定義這些參數，則必須使用 `-t container` 參數進行部署。然後，系統會提示您輸入所有其他值。

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

在 `cli-config.yml` 中，您可以在 `chart-path` 內容中定義 Helm 圖表位置，並配置 `deploy-image-target`（如範例中所示）。使用 `cli-config.yml` 中的 `deploy-image-target` 元素，而不是 `chart/values.yml` 檔案中的 `repository` 及 `tag` 元素。若要特別部署至 {{site.data.keyword.cloud_notm}}，請將配置元素 `ibm-cluster` 設為您在 {{site.data.keyword.cloud_notm}} 中建立的 Kubernetes 叢集名稱。

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

### 部署至 {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

您可以部署至 {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment。若要這樣做，請使用 `ibmcloud target --cf` 來配置此環境的本端環境，然後從該清單中選取正確的環境。您接著可以使用也用於 {{site.data.keyword.cloud_notm}} Public Cloud Foundry 的 `deploy` 指令。

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

* 這是與容器部署搭配使用的參數，用來指定部署的目標映像檔名稱。此值不得包括版本。例如：image-name:{version}，因為版本會自動遞增並附加 `deploy`。
* 用法：`ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* 這是對 {{site.data.keyword.cloud_notm}} 進行容器部署時選擇性使用之參數，用來定義 Kubernetes 叢集名稱
* 用法：`ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* 部署至 Cloud Foundry 時，選擇性地用來定義應用程式主機名稱的參數。
* 用法：`ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* 部署至 Cloud Foundry 時，選擇性地用來定義應用程式網域的參數。
* 用法：`ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

`diag` 指令用來作為診斷，以顯示 {{site.data.keyword.dev_cli_notm}} CLI 之已安裝相依關係的版本資訊。這有助於判斷您是否遺漏任何相依關係，或是協助進行問題除錯。

執行下列指令，以顯示已安裝相依關係的版本：
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

使用選項來編輯應用程式，例如將它與已在 {{site.data.keyword.cloud_notm}} 中的應用程式連接、管理應用程式的 {{site.data.keyword.cloud_notm}} 服務，以及使用其部署至 IBM Cloud Kubernetes、Cloud Foundry 或 Cloud Foundry Enterprise Environment 的 {{site.data.keyword.cloud_notm}} 工具鏈。如果本端應用程式已連接至 {{site.data.keyword.cloud_notm}} 中的應用程式，請使用 `edit` 來新增服務、連接及中斷連接現有的服務，或是移除您帳戶中的現有服務。此外，您還可以建立或檢視應用程式的 {{site.data.keyword.cloud_notm}} 工具鏈。請在應用程式目錄的根目錄中執行下列指令：
```
ibmcloud dev edit
```
{: codeblock}

如果您在帳戶上沒有任何現有服務，這個指令會顯示服務群組的清單，供您選取要連接至應用程式的服務。

不過，如果您在帳戶上有任何現有服務，這個指令會顯示那些服務的清單，以及每個服務是否連接至應用程式。

* 已連接的服務可讓您選擇是要中斷服務與應用程式的連線，還是從帳戶刪除服務，這樣會中斷它與所有應用程式的連線。

* 已中斷連線的服務可讓您選擇是要將該服務連接至應用程式，還是從帳戶刪除服務。連接現有的服務也會下載認證或原始碼這類檔案。

您也可以將新的服務新增至應用程式，在其中，會引導您完成選取服務提示，並下載認證檔或原始碼這類檔案。

## enable
{: #enable}

啟用現有應用程式以進行 {{site.data.keyword.cloud_notm}} 部署。`enable` 指令會嘗試自動偵測現有應用程式的語言，然後提示您輸入必要的其他資訊。這會產生檔案，以便用於本端 Docker 容器、Cloud Foundry 部署、Cloud Foundry Enterprise Environment 部署或「Kubernetes 容器」部署。您可以透過手動 `deploy` 或使用 DevOps 工具鏈，來利用所有部署環境。

登入 {{site.data.keyword.cloud_notm}} 後，您可以將這個本端應用程式與已在 {{site.data.keyword.cloud_notm}} 中的應用程式連接，或是建立新的 {{site.data.keyword.cloud_notm}} 應用程式。若要充分運用服務及 DevOps 工具鏈這類 {{site.data.keyword.cloud_notm}} 特性，就需要位於 {{site.data.keyword.cloud_notm}} 中的應用程式。針對從 Git 儲存庫複製的應用程式建立 {{site.data.keyword.cloud_notm}} 應用程式時，{{site.data.keyword.cloud_notm}} 應用程式會將這個儲存庫內含在其配置中。 

`enable` 是測試版特性。如果您在啟用應用程式的雲端功能時遇到問題，請參閱[疑難排解](/docs/cli?topic=cloud-cli-troubleshoot)。具體而言，`enable` 不適用於行動應用程式或架構。對於會產生數個可部署資產的複雜應用程式，必須個別啟用應用程式的每個元件。 

執行下列指令，以在現行目錄中啟用現有應用程式：
```
ibmcloud dev enable
```
{: codeblock}

如有必要檔案存在，便會提供對有效專案結構的應用程式語言偵測。  

* `package.json` 檔的存在會識別 Node.js 應用程式。
* `package.swift` 檔的存在會識別 Swift 應用程式。
* `setup.py` 或 `requirements.txt` 檔的存在會識別 Python 應用程式。
* `pom.xml` 或 `build.gradle` 檔的存在會識別 Java&trade; 應用程式。
	* `pom.xml` 檔的存在會識別 Maven 應用程式。
	* `build.gradle` 檔的存在會識別 Gradle 應用程式。

您也可以地使用 `--language` 引數來置換偵測到的應用程式語言。只支援有效且完整的應用程式。enable 指令不會修改原始碼。

### enable language 選項
{: #enable-language-options}

語言選項包括：
* node
* swift
* python
* java-ee（解譯為 Java&trade; - Java&trade; EE）
* java-mp（解譯為 Java&trade; - Java&trade; MicroProfile）
* java-spring（解譯為 Java&trade; - Spring Framework）

如果使用 `ibmcloud dev enable` 指令所建立檔案與應用程式資料夾中的現有檔案發生名稱衝突，則會儲存為 `.merge` 副檔名。  

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

#### `no-create`
{: #enable-no-create}

* 用來防止在 {{site.data.keyword.cloud_notm}} 建立應用程式的參數，且會在本端建立啟用檔案。
* 用法：`ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

取得應用程式所需的認證，以啟用連接的服務。

## help
{: #help}

依預設，如果未傳入任何動作或引數，或如果提供 'help' 動作，則這個指令會顯示一般「說明」文字。顯示的一般說明包括基本引數的說明，以及可用動作的清單。  

執行下列指令，以顯示一般說明資訊：
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

您可以列出資源群組中的所有 {{site.data.keyword.cloud_notm}} 應用程式。

執行下列指令，以列出您的應用程式：
```
ibmcloud dev list
```
{: codeblock}

## run
{: #run}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以透過 `run` 指令來執行您的應用程式。必須先使用 `build` 指令，針對應用程式完成建置。當您執行 `run` 指令時，run 容器會啟動，並公開 `container-port-map` 參數所定義的埠。如果 run 容器 `Dockerfile` 未包含進入點以完成此步驟，則會使用 `run-cmd` 參數來呼叫應用程式。

若要使用多個容器來執行，您的應用程式必須包含 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 檔案（指定於 `cli-config.yml` 中），或者您可以使用 `dockerfile-run` 指令參數來提供檔案。

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

下列參數專用於 `run` 指令，並且可協助您在 run 容器內管理您的應用程式。還有[參數](#command-parameters)與其他指令共用。

#### `container-name-run`
{: #container-name-run2}

* run 容器的容器名稱。
* 用法：`ibmcloud dev run --container-name-run [<appName>]`

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
* 如果您打算使用數個容器來執行，請使用 Compose 檔案。
* 若要使用多個 Compose 檔案，請用雙引號括住以逗點區隔的檔名清單。
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

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以使用 `shell` 指令，在 run 或 tools 容器內開啟 Shell。

執行下列指令：
```
ibmcloud dev shell
```
{: codeblock}

{{site.data.keyword.dev_cli_short}} CLI 會將互動式 Shell 開啟至應用程式的 Docker 容器。Shell 指令的預設目標容器是由 `cli-config.yml` 檔案中的 `container-shell-target` 值所定義，而有效值是 `run` 或 `tools`。如果未定義此值，或指定無效值，則依預設 `shell` 指令會以 `tools` 容器為目標。shell 指令會將容器開啟到對應 Dockerfile 中 `WORKDIR` 指示所指定的目錄。如果 Dockerfile 中未列出 `WORKDIR`，則會使用容器根目錄作為工作目錄。如需相關資訊，請參閱[此參考資料](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。

或者，您可以決定要傳遞 `run` 或 `tools` 作為指令的引數，以便啟動該容器和開啟 Shell 來連接該容器。同樣地，您可以使用 `container-name` 參數，傳遞您要以 Shell 方式連接的容器名稱。不過，此旗標保留用於沒有容器在執行中的情況。`run` 和 `tools` 引數更有彈性，而且可讓您在執行中的容器之間切換。例如，如果 tools 容器正在執行，且您執行 `ibmcloud dev shell run`，則會停止 `tools` 容器，並啟動 `run` 容器，反之亦然。

如果在您執行 `shell` 指令時，目標 `run` 或 `tools` 容器尚未執行，則會啟動目標容器。不過，會置換 Dockerfile 中的預設 `Cmd` 或 `Entrypoint` 以直接啟動到 Shell，而不是啟動伺服器處理程序。這可讓您啟動 `run` 或 `tools` 容器，並使用您自己的任意或自訂指令手動啟動伺服器。

您也可以使用 `container-shell` 參數，來指定您要開啟的 Shell 執行檔。依預設，會使用 `/bin/sh`。如果您偏好使用 Bash Shell，請將 `container-shell` 值指定為 `/bin/bash`；不過，請記住，不會在所有 Linux&trade; 變式中自動提供 Bash。

您在旗標後面傳遞給指令的任何其他引數都會剖析為要在開啟 Shell 時執行的指令。如果您提供指令，則容器內的 Shell 會在執行指令時結束，並回到您的終端機。

例如，您可以呼叫 &trade; `ibmcloud dev shell tools ls`，以在 tools 容器 Shell 內執行 Linux `ls` 指令。您也可以使用引號括住引數（例如 `ibmcloud dev shell "ls -la"`），來指定要傳入 Shell 指令執行的旗標。

### shell 指令參數
{: #shell-parameters}

#### `container-name`
{: #container-name}

* 您要以 Shell 方式連接的容器名稱。
* 用法：`ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* 指定要在容器內執行的 Shell（預設值是 /bin/sh）。
* 用法：`ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以查詢 `container-name-run` 及 `container-name-tools` 所定義之 {{site.data.keyword.dev_cli_short}} CLI 所使用容器的狀態。

在現行應用程式目錄中執行下列指令，以檢查容器狀態：
```
ibmcloud dev status
```
{: codeblock}

[Status 指令參數](#command-parameters)

## stop
{: #stop}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以透過 `stop` 指令來停止您的容器。

若要停止您 `cli-config.yml` 檔案定義的 tools 和 run 容器，請執行：
```
ibmcloud dev stop
```
{: codeblock}

若要停止未在 `cli-config.yml` 檔案中定義的容器，您可以指定額外的指令行參數來置換它。如果在 `cli-config.yml` 檔或指令行中未指定任何容器，則 stop 指令會直接傳回。

### stop 指令參數
{: #stop-parameters}

下列參數用於 `stop` 指令。還有[參數](#command-parameters)與其他指令共用。

#### `container-name-run`
{: #container-name-run}

* run 容器的容器名稱。
* 用法：`ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`
{: #container-name-tools}

* tools 容器的容器名稱。
* 用法：`ibmcloud dev stop --container-name-tools [<appName>]`

## test
{: #test}

如果您使用 Windows&trade;，則必須執行 Windows&trade; 10 Pro 或更新版本。

您可以透過 `test` 指令來測試您的應用程式。必須先使用 `build --debug` 指令，針對應用程式完成建置。然後，會使用 tools 容器來為應用程式啟動 `test-cmd`。

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

下列參數專屬於 `test` 指令。還有[參數](#command-parameters)與其他指令共用。

#### `test-cmd`
{: #test-cmd}

* 用來指定指令以在 tools 容器中測試程式碼的參數。
* 用法：`ibmcloud dev test --test-cmd /the/test/command`

## view
{: #view}

您可以透過 `view` 指令，來檢視應用程式所部署到的 URL。請在您要檢視的應用程式的根目錄中執行這個指令。`view` 指令也會在預設瀏覽器中開啟 URL。

對於部署至 Cloud Foundry 的應用程式，URL 包含應用程式的主機名稱及應用程式的網域。

對於部署至 Kubernetes 的應用程式，URL 包含其部署所在之節點的 IP 位址，以及公用埠。如果指令判定應用程式已部署至 Kubernetes，則 CLI 工具會提示進行確認。如果您指定應用程式未部署至 Kubernetes，則會顯示 Cloud Foundry URL。如果您預期指令顯示 Kubernetes 已部署應用程式的 URL，則請確定 `cli-config.yml` 包含 `chart-path` 的項目，或透過指令行提供它（如[這裡](#chart-path)所示）。

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

* 要附加至 Cloud Foundry 及 Kubernetes 應用程式 URL 的專案根目錄。
* 用法：`ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* 以容器部署為目標時，選擇性地用來定義 Kubernetes 叢集名稱的參數。
* 用法：`ibmcloud dev view --ibm-cluster [cluster-name]`

## 複合指令
{: #compound}

您可以在一個指令行陳述式中執行數個指令，方法是使用 `/` 定界字元來區隔 {{site.data.keyword.cloud_notm}} Developer Tools 指令。在您指定複合指令之後，可以使用其他指令行旗標。下列指令是如何使用複合指令的範例：
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

所有旗標都必須追蹤最終指令，並套用至與該旗標相關聯的所有指令。使用 `ibmcloud dev build/deploy/view -t container --trace` 作為範例，`--trace` 旗標會套用至全部三個指令，但 `-t` 只適用於最後兩個指令，因此不會套用至 `build` 指令。

下列指令可以與此特性搭配使用：
`build、debug、deploy、get-credentials、run、stop、test、view`

如果有一個指令因任何原因而失敗，則不會執行後續指令。

如果 `debug` 或 `run` 後面有任何指令，則會在透過從現行終端機視窗結束處理程序以外的方式終止 `debug` 或 `run` 時繼續執行。輸入 `CTRL+C` 即會結束處理程序，而不會執行後續指令。例如，您可以從另一個終端機視窗執行 `ibmcloud dev stop`，以停止執行中容器並繼續執行到下一個指令。

## build、debug、run 及 test 的參數
{: #command-parameters}

下列參數可以與 `build|debug|run|test` 指令搭配使用，或直接更新應用程式的 `cli-config.yml` 檔案予以使用。額外參數適用於 [`debug`](#debug-parameters) 及 [`run`](#run-parameters) 指令。

在指令行上輸入的指令參數，其優先順序高於 `cli-config.yml` 配置。
{: note}

#### `config-file`  
{: #config-file}

* 指定要用於指令的 cli-config.yml 檔案。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* run 容器的容器名稱。
* 用法：`ibmcloud dev <run|status|stop> --container-name-run [<appName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* tools 容器的容器名稱。
* 用法：`ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<appName>]`

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
* 作為最佳作法並防止非預期的結果，您可以使用相同的裝載設定來建置並執行。
* 用法：`ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* 使用此選項來定義主機系統與 tools 容器之間的裝載。
* `host-path-tools` 及 `container-path-tools` 值會插入至此清單的開頭。
* 作為最佳作法並防止非預期的結果，您可以使用相同的裝載設定來建置並除錯。
* 用法：`ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* 用來指定指令以建置所有用法的程式碼（但 DEBUG 除外）的參數。
* 用法：`ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* 使用此參數來提供詳細輸出。
* 用法：`ibmcloud dev <build|debug|run|test> --trace`
