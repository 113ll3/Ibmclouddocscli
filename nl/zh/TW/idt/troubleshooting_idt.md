---
copyright:
  years: 2017, 2018
lastupdated: "2018-11-30"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# IBM Cloud Developer Tools 的疑難排解
{: #ts}

記錄了 {{site.data.keyword.dev_cli_notm}} 的一些已知問題及其暫行解決方法。
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## 已知問題
{: #knownissues}

下列各節說明已知問題和可能的解決方案。


### 使用非行動模式建立專案時發生主機名稱已使用的錯誤
{: #hostname}

如果您使用 {{site.data.keyword.dev_cli_short}} 從「Web 應用程式」、BFF 或「微服務」模式建立專案，則可能會看到下列錯誤：

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### 原因
{: #hostname-cause}

此錯誤是過期登入記號所造成。


#### 解決方法
{: #hostname-resolution}

請重新登入。

```
ibmcloud login
```
{: codeblock}


### 啟用指令在辨識應用程式的語言時發生問題
{: #enable-unknown-language}

```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
#### 原因
{: #enable-unknown-language-cause}

此錯誤的原因可能是：
1. 從不是應用程式來源目錄的目錄中執行 [enable](commands.md#enable) 指令。
2. 針對目前無法辨識其語言的應用程式執行 [enable](commands.md#enable) 指令。


#### 解決方法
{: #enable-unknown-language-resolution}

請確定是從包含應用程式原始碼的應用程式目錄中執行這個指令。如果這麼做無法解決此狀況，且語言是其中一種[支援的語言](commands.md#enable-language-options)，請使用 `--language` 參數來指定語言。


### 建置或執行已啟用的應用程式時發生問題
{: #enable-build-run-failures}

您在嘗試 [build](commands.md#build)（建置）或 [run](commands.md#run)（執行）已啟用的應用程式時，可能會遇到各種失敗狀況。


#### 解決方法
{: #enable-build-run-failures-resolution}

如需解決 Spring 應用程式這類問題的相關指引，請參閱這篇[文章](/docs/java-spring/enable_existing.html#enable_existing)。

如需解決 Node.js 應用程式這類問題的相關指引，請參閱這篇[文章](/docs/node/enable_existing.html#enable_existing)。

### {{site.data.keyword.dev_cli_short}} 的一般失敗
{: #general}

如果您使用 {{site.data.keyword.dev_cli_short}} create、delete、list 或 code 指令，則可能會看到下列錯誤：

```
Failed to <command> project.
```
{: codeblock}


#### 原因
{: #general-cause}

此錯誤是過期登入記號所造成。


#### 解決方法
{: #general-resolution}

請重新登入。

```
ibmcloud login
```
{: codeblock}


### 錯誤：當您執行新的應用程式時，沒有這類映像檔
{: #nosuchimage}

當您執行專案而未先進行建置時，可能會看到下列錯誤。

```
$ ibmcloud dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```


#### 原因
{: #nosuchimage-cause}

您必須先建置專案，才能執行它。



#### 解決方法
{: #nosuchimage-resolution}

在現行專案目錄中執行下列指令，以建置您的應用程式：

```
ibmcloud dev build
```
{: codeblock}

在現行專案目錄中執行下列指令，以啟動您的應用程式：

```
ibmcloud dev run
```


### 新增 {{site.data.keyword.objectstorageshort}} 功能時發生服務分配管理系統錯誤
{: #os}

如果您使用 {{site.data.keyword.dev_cli_short}} 建立兩個具有 {{site.data.keyword.objectstorageshort}} 功能的專案，則可能會看到下列錯誤：

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### 原因
{: #os-cause}

此錯誤是 {{site.data.keyword.objectstorageshort}} 服務所造成，而此服務只提供免費 {{site.data.keyword.objectstorageshort}} 方案的一個實例。


#### 解決方法
{: #os-resolution}

系統會提示您選擇不同的方案來避免此錯誤。



### 建立應用程式期間無法取得程式碼
{: #code}

如果您使用 {{site.data.keyword.dev_cli_short}} 建立專案，則可能會看到下列錯誤：

```
FAILED
Project created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### 原因
{: #code-cause}

此錯誤是內部逾時所造成。



#### 解決方法
{: #code-resolution}

您可以使用下列其中一種方式來取得程式碼：

* 使用 CLI 執行下列指令：

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   請將 `<your-project-name>` 取代為您在專案建立期間指定的專案名稱。

* 使用 {{site.data.keyword.dev_console}}。

	1. 在 {{site.data.keyword.dev_console}} 中選取[專案 ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/developer/projects)，然後按一下**取得程式碼**。

	2. 按一下**產生程式碼**。

	3. 產生程式碼之後，請按一下**下載程式碼**。



### 針對 Node.js 專案執行 `ibmcloud dev run` 時發生錯誤
{: #node}

如果您是搭配執行 `ibmcloud dev run` 與適用於 Node.js Web 或 BFF 專案的 {{site.data.keyword.dev_cli_short}}，則可能會看到下列錯誤：

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### 原因
{: #node-cause}

`appmetrics` 模組安裝在不同的架構上時，會發生此錯誤。安裝在某個架構上的原生 mpm 模組無法在另一個架構上運作。所包括的 Docker 映像檔是以 Linux Kernel 為基礎。



#### 解決方法
{: #node-resolution}

刪除 `node_modules` 資料夾，並重新執行 `ibmcloud dev run`。


### 無法部署至 {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

您可能會嘗試使用 {{site.data.keyword.dev_cli_short}} 部署至 {{site.data.keyword.Bluemix_notm}}，您看到它未部署至 {{site.data.keyword.Bluemix_notm}}，但沒有發生錯誤。


#### 原因
{: #cause1}

這可能是您未登入您的帳戶。

#### 解決方法
{: #resolution1}

請登入，然後再試一次。

```
ibmcloud login
```


### 無法部署至 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes
{: #failuretodeploytokube}

在叢集名稱的起始提示之後，您可能會看到此失敗：

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### 原因
{: #cause2}

這最有可能是因為叢集名稱無效，且可以利用 `--trace` 來執行相同指令來確認，您可能會在錯誤輸出中看到此內容：

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### 解決方法
{: #resolution2}

請確定您使用的是正確叢集，而且您已透過執行下列指令來配置要進行部署的叢集：

```
ibmcloud cs cluster-config <cluster-name>
```


### 無法部署至 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes

在部署映像檔目標的提示之後，您可能會看到此失敗：

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### 原因
{: #cause3}

最有可能是因為部署映像檔目標無效。更具體來說，可能是名稱空間（即部署映像檔目標中的中間值）無效。


#### 解決方法
{: #resolution3}

請確定部署映像檔目標中的名稱空間符合執行下列指令所找到的其中一個名稱空間：

```
ibmcloud cr namespaces
```



## 附錄
{: #appendix}

全部必要條件會使用本頁面頂端的平台安裝程式，為大部分使用者安裝。如果您需要手動安裝任何元件，以下是其指示：

若要安裝 dev 外掛程式，必須先安裝 [IBM Cloud CLI](../reference/bluemix_cli/get_started.md#getting-started)。

若要使用 dev 外掛程式本身，您必須執行下列指令來安裝它：`ibmcloud plugin install dev -r Bluemix`。

若要在本端執行和除錯應用程式，您也必須安裝 [Docker ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://www.docker.com/get-docker)。

若要將應用程式部署為容器，您還必須安裝 Kubernetes、Helm 及下列 IBM Cloud CLI 外掛程式：

若要安裝 Kubernetes：
* Mac 使用者：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux 使用者：
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows 使用者：
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

若要安裝 Helm：
* Mac 及 Linux 使用者：
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows 使用者：
在 https://github.com/kubernetes/helm/releases/tag/v2.6.0 下載並安裝二進位檔

若要安裝 container-registry 外掛程式：
`ibmcloud plugin install container-registry`

若要安裝 container-service 外掛程式：
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## 取得協助及支援
{: #gettinghelp}

如果您對 {{site.data.keyword.Bluemix_notm}}{{site.data.keyword.dev_console}} 或 {{site.data.keyword.dev_cli_notm}} 有問題或疑問，請搜尋資訊或透過討論區提問來取得協助。您也可以開啟支援案例。

在討論區中張貼時，您可以標記您的問題，以通知 {{site.data.keyword.Bluemix_notm}} 開發團隊。

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

如果您在使用 {{site.data.keyword.dev_console}} 或 {{site.data.keyword.dev_cli_notm}} 開發或部署應用程式時有技術方面的問題：

* 將問題張貼在 [Stack Overflow ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix)，並使用 `bluemix-dev-services` 和 `ibm-bluemix` 來標記問題。
* 將問題張貼在 [Slack ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](http://ibm-cloud-tech.slack.com/) 的 `bluemix-dev-services` 頻道。馬上[註冊 ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](http://ibm.biz/IBMCloudNativeSlack)。


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

如需使用討論區的詳細資料，請參閱[取得協助 ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](/docs/support/index.html#getting-help)。

如需開啟 {{site.data.keyword.IBM}} 支援案例的相關資訊，或支援層次及案例嚴重性的相關資訊，請參閱[與支援中心聯絡 ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](/docs/support/index.html#contacting-support)。

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
