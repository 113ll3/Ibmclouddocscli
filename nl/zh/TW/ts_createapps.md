---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-05"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# {{site.data.keyword.Bluemix_notm}} Developer Tools CLI 外掛程式的疑難排解
{: #troubleshoot}

使用 {{site.data.keyword.dev_cli_short}} 指令行介面 (CLI) 建立應用程式的一般問題可能包括部署失敗或無法擷取程式碼。在許多情況下，您可以遵照一些簡單的步驟，從這些問題回復。
{:shortdesc}

## 當我使用非行動模式建立應用程式時，為何會收到主機名稱錯誤？
{: #hostname-error}
{: troubleshoot}

如果您使用 {{site.data.keyword.dev_cli_short}} CLI 將應用程式部署至 Cloud Foundry，可能會顯示下列錯誤。如果您輸入唯一的主機名稱，仍可能會看到此訊息。

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

此錯誤是過期登入記號所造成。
{: tsCauses}

執行下列指令以再次登入：
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 為何會收到一般指令失敗？
{: #general}
{: troubleshoot}

如果您使用 `create`、`delete`、`list` 或 `code` 指令，則可能會顯示下列錯誤：

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

此錯誤是過期登入記號所造成。
{: tsCauses}

執行下列指令以再次登入：
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 為何無法辨識新應用程式的映像檔？
{: #nosuchimage}
{: troubleshoot}

當您嘗試執行應用程式而未先進行建置時，可能會顯示下列錯誤。

```
$ ibmcloud dev run
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
{: tsSymptoms}

您必須先建置應用程式，才能執行它。
在現行應用程式目錄中執行下列指令：
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

在現行應用程式目錄中執行下列指令，以啟動您的應用程式：
```
ibmcloud dev run
```
{: tsResolve}

## 為何在新增 {{site.data.keyword.objectstorageshort}} 功能時收到服務分配管理系統錯誤？
{: #os}
{: troubleshoot}

如果您使用 CLI 來建立兩個具有 {{site.data.keyword.objectstorageshort}} 功能的應用程式，則可能會顯示下列錯誤：

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

此錯誤是 {{site.data.keyword.objectstorageshort}} 服務所造成，而此服務只提供免費 {{site.data.keyword.objectstorageshort}} 方案的一個實例。
{: tsCauses}

選取不同的方案。
{: tsResolve}

## 為何在建立應用程式時未擷取我的程式碼？
{: #code}
{: troubleshoot}

如果您使用 CLI 來建立應用程式，則可能會顯示下列錯誤：

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

此錯誤是內部逾時所造成。
{: tsCauses}

請使用下列其中一種方法來取得程式碼：

* 請執行下列指令：

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   請將 `<your-app-name>` 取代為您在應用程式建立期間指定的應用程式名稱。

* 使用 {{site.data.keyword.dev_console}}。

	1. 在 {{site.data.keyword.dev_console}} 中選取[應用程式 ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://console.bluemix.net/developer/appservice/apps)。

	2. 按一下**下載程式碼**。
{: tsResolve}

## 為何無法對 Node.js 應用程式執行 `ibmcloud dev run` 指令？
{: #node}
{: troubleshoot}

如果您對 Node.js Web 或 BFF 應用程式執行 `ibmcloud dev run` 指令，則可能會顯示下列錯誤：

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
{: tsSymptoms}

`appmetrics` 模組安裝在不同的架構上時，會發生此錯誤。安裝在某個架構上的原生 mpm 模組無法在另一個架構上運作。所包括的 Docker 映像檔是以 Linux Kernel 為基礎。
{: tsCauses}

刪除 `node_modules` 資料夾，並重新執行 `ibmcloud dev run` 指令。
{: tsResolve}

## 為何無法部署至 {{site.data.keyword.Bluemix_notm}}？
{: troubleshoot}

當您嘗試部署至 {{site.data.keyword.Bluemix_notm}} 時失敗，但未顯示任何錯誤。
{: tsSymptoms}

您可能未登入您的帳戶。
{: tsCauses}

執行下列指令，以登入並再試一次。
```
ibmcloud login
```
{: tsResolve}

## 為何無法部署至 {{site.data.keyword.Bluemix_notm}} 上的 Kubernetes？
{: troubleshoot}

系統提示您輸入叢集名稱之後，可能會顯示下列失敗：
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

這最可能是叢集名稱無效所造成。您可以執行與 `--trace` 相同的指令來確認原因，而錯誤輸出中可能會包含下列詳細資料：
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

請確定您使用的是正確叢集，而且您已透過執行下列指令來配置要進行部署的叢集：
```
ibmcloud cs cluster-config <cluster-name>
```
{: tsResolve}

## 為何無法部署映像檔目標？
{: troubleshoot}

系統提示您輸入部署映像檔目標之後，可能會顯示下列失敗：
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

這最可能是部署映像檔目標無效所造成。更具體來說，名稱空間（即部署映像檔目標中的中間值）可能無效。
{: tsCauses}

請確定部署映像檔目標中的名稱空間符合執行下列指令時所顯示的其中一個名稱空間：
```
ibmcloud cr namespaces
```
{: tsResolve}

## 為何無法判定應用程式的語言？
{: troubleshoot}

系統嘗試啟動您的應用程式之後，可能會顯示下列失敗：
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: tsSymptoms}

此錯誤可能是由下列其中一個原因所造成：
- 從不是應用程式來源目錄的目錄中執行 [enable](/docs/cli/idt/commands.html#enable) 指令。
- 針對目前無法辨識其語言的應用程式執行 [enable](/docs/cli/idt/commands.html#enable) 指令。
{: tsCauses}

請務必從包含應用程式原始碼的應用程式目錄中執行此指令。如果這無法解決問題，且語言是其中一種[支援的語言](/docs/cli/idt/commands.html#enable-language-options)，請使用 `--language` 參數來指定語言。
{: tsResolve}

## 為何無法建置或執行已針對雲端部署啟用的應用程式？
{: troubleshoot}

您在嘗試 [build](/docs/cli/idt/commands.html#build)（建置）或 [run](/docs/cli/idt/commands.html#run)（執行）已啟用的應用程式時，可能會遇到各種失敗問題。
{: tsSymptoms}


您可以在下列每個鏈結中找到許多不同的原因。
{: tsCauses}

- 如需解決 Spring 應用程式這類問題的相關資訊，請參閱[啟用現有的 Spring Boot 應用程式以進行雲端部署](/docs/java-spring/enable_existing.html#enable_existing)。
- 如需解決 `Node.js` 應用程式這類問題的相關資訊，請參閱[啟用現有的 Node.js 應用程式以進行雲端部署](/docs/node/enable_existing.html#enable_existing)。
{: tsResolve}
