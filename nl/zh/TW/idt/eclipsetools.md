---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 部署應用程式
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} 提供可以安裝到現有 Eclipse 環境的外掛程式，以協助整合開發人員的整合開發環境 (IDE) 與 Bluemix®。工具容許您將 JavaScript、WAR（Web 保存檔）及 EAR（企業保存檔）檔案以及 Liberty Profile 包裝伺服器部署到 Cloud 伺服器－就從您的 Eclipse IDE 或 WebSphere® Application Server Developer Tools (WDT) 進行。這些工具還可讓您在部署時建立服務並將服務鏈結至應用程式，以及定義環境變數。

如果您已經使用 Websphere Application Developer Tools 搭配 Liberty Profile 讓應用程式在 Eclipse 執行，則可以在執行中程式之上安裝這些工具。您可以在工作台將應用程式新增至 Cloud 伺服器，以部署應用程式。由於 Liberty 建置套件的包裝伺服器支援獨特特性，您也可以選擇將整個 Liberty Profile 伺服器部署到 Cloud。您也可以將 Node.js JavaScript 應用程式部署至 Cloud。

## 安裝 Eclipse Tools

了解如何安裝 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}。需要 Java™ 1.7 或更新版本的執行環境。

有多種方法可以安裝 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}，包括：
* 從 Marketplace 安裝。
* 從 WASDev 安裝。
* 從 IBM WebSphere Application Server Developer Tools (WDT) 安裝程式下載。

### 從 Marketplace 安裝

安裝需要 [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) 或 [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers)。

接著，請遵循這裡的指示：[https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help)。

### 從 WASDev 安裝

1. 在 WASDev 中開啟[下載](https://developer.ibm.com/wasdev/downloads/)頁面。
2. 將 `Install` 圖示拖曳至 Eclipse 中的工具列。
3. 依預設，已經為您選取了特性。請按一下**確認**。
4. 接受授權合約，然後按一下**完成**。

### 從 IBM WebSphere Application Server Developer Tools (WDT) 安裝程式下載

1. 開啟**說明 > 安裝 WebSphere 軟體**。搜尋 Cloud
2. 選取 `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` 項目，然後按一下**安裝**。
3. 依預設，已經為您選取了特性。請按一下**確認**。
4. 接受授權合約，然後按一下**完成**。

## 包裝伺服器支援

使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}，有多種情境以便將 Liberty Server 或包裝伺服器推送至 Cloud 並確認部署。

* 建立 Cloud 伺服器。
* 使用 WAR 檔或 EAR 檔建立 Liberty Profile 伺服器。
* 停止伺服器。

使用包裝伺服器支援的 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}，有多種情境可以：

* 將 Liberty Server 推送至 Cloud。
* 將 Liberty 包裝伺服器推送至 Cloud。
* 利用測試，確認成功部署應用程式。

此外，您可以將包裝伺服器壓縮檔匯入到工作區中的任何專案。

### 情境 1 - 將已停止的 Liberty Server 新增至 Cloud 然後測試應用程式

1. 在「伺服器」視圖中，於 `Cloud` 伺服器上按一下滑鼠右鍵。
2. 選取**新增及移除**。
3. 在對話框中，會顯示 Liberty Server 實例。選取一個實例，然後按一下**新增**。
4. 按一下**完成**。
5. 在「應用程式」對話框中，預設名稱是衍生自 Liberty Server 實例。您可以變更此名稱，但名稱中不得包含空格或特殊字元。預設值如果不與 Cloud 伺服器中現有應用程式衝突，便可接受。
6. 按一下**完成**，然後等待應用程式發佈在 Cloud 上。
7. 在 Cloud 伺服器下已新增的 Liberty Server 模組按一下滑鼠右鍵。選取**開啟首頁**。即會在預設 Web 瀏覽器中開啟包裝伺服器根 URL。使用這個根 URL 作為建置 URL 的基礎，以在包裝的 WAR 及 EAR 應用程式內進行測試。

### 情境 2 - 將已停止的 Liberty Server 拖放至 Cloud

情境 1 說明如何新增及移除 Liberty Server 模組。此作業可以使用拖放功能予以簡化。

1. 如果從情境 1 繼續，請從 Cloud 伺服器移除 Liberty Server 模組。
2. 選取並拖曳已停止的 Liberty Server 實例，將它放入「伺服器」視圖中的 Cloud 伺服器。即會出現「應用程式」對話視窗。
3. 遵循情境 1 中的步驟 5-10。

### 情境 3 - 執行包裝伺服器至 Cloud

Liberty Profile 服務實例的快速功能表包含一個「包裝伺服器」動作。此動作會將伺服器包裝至保存檔。在 Cloud 中，已新增一個新動作，將伺服器包裝成壓縮檔，然後將它部署至 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}。

1. 如果從情境 1 或 2 繼續，請從 Cloud 伺服器移除 Liberty Server 模組。
2. 在「伺服器」視圖中，於 Liberty Profile 伺服器實例上按一下滑鼠右鍵。
3. 在「公用程式」功能表下，選取**包裝伺服器至 {{site.data.keyword.Bluemix_notm}}**。
4. 在對話框中，選擇您要部署應用程式的 Cloud 伺服器。
5. 按一下**確定**。即會出現「應用程式」對話視窗。
6. 遵循情境 1 中的步驟 5-10。
7. 如果出現進度對話視窗，請選擇**在背景中執行**，然後等到應用程式部署完成。

### 情境 4 - 使用包裝伺服器壓縮檔 - 在伺服器中執行

先前的情境說明如何在「伺服器」視圖中使用現有的 Liberty Server 實例，以及如何將它們部署至 Cloud。您也可以將現有的包裝伺服器壓縮檔部署至 Cloud。

1. 建立或取得包裝伺服器壓縮檔。
2. 將壓縮檔匯入至工作區中的任何專案。
3. 在壓縮檔按一下滑鼠右鍵，然後選取**執行身分 > 在伺服器中執行**。即會出現「在伺服器中執行」對話視窗。
4. 選取 Cloud 伺服器。
5. 按一下**完成**。即會出現「應用程式」對話視窗。
6. 遵循情境 1 中的步驟 5-10。模組名稱是衍生自壓縮檔。

### 情境 5 - 使用包裝伺服器壓縮檔 - 拖放

1. 選取並拖曳包裝伺服器壓縮檔，然後將它放入「伺服器」視圖中的 Cloud 伺服器。即會出現「應用程式」對話視窗。
2. 遵循情境 1 中的步驟 5-10。模組名稱是衍生自壓縮檔的名稱。

## 推送 EAR 檔

使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 將 EAR 推送至 Cloud。

定義新的伺服器。

1. 若要建立新的 Cloud 伺服器，請選取**檔案 > 新建 > 其他**
2. 從「伺服器」種類選取**伺服器**，然後按**下一步**。
3. 在 IBM 下尋找 Cloud。
4. 按**下一步**。
5. 輸入您的 Cloud 帳戶資訊。如果沒有帳戶，請按一下**註冊**。
6. 按**下一步**。
7. 選擇您的組織及空間。預設值是 `dev`。
8. 按**下一步**。
9. 按一下**完成**。

匯入 EAR 檔

1. 按一下滑鼠右鍵選取**匯入**。
2. 搜尋 EAR 檔。
3. 瀏覽並找出您想要匯入的 EAR 檔。
4. 確定目標運行環境已設為 {{site.data.keyword.Bluemix_notm}} 運行環境。

部署應用程式。

1. 在已啟動的 Cloud 伺服器按一下滑鼠右鍵。選擇**新增及移除**。
2. 選擇 EAR，然後按一下**新增**。
3. 按一下**完成**。即會開啟「應用程式詳細資料」視窗。
4. 命名該應用程式，然後按**下一步**。有效名稱可包含 A-Z、0-9、- 及 _。但不得包含空格或其他特殊字元。依預設，會設定「啟動部署」資訊。
5. 按**下一步**。
6. 必要的話，請選取服務。按**下一步**。
7. 必要的話，請新增變數。按一下**完成**。
8. 推送應用程式之後，在專案上按一下滑鼠右鍵，然後選擇**開啟首頁**。
9. 將 Web 模組名稱及應用程式名稱新增至 URL。
10. 若要儲存您指定的設定及變數，請選取「應用程式詳細資料」視窗中的**儲存至資訊清單檔**勾選框。

## 部署 Node.js 應用程式
使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 部署現有或新的 Node.js 專案至 Cloud、設定應用程式部署詳細資料，然後在瀏覽器中驗證結果。

如果您還沒有現有的 Node.js 應用程式，請從步驟 1 開始。如果您已有現有的 Node.js 應用程式，請從步驟 7 開始。

1. 選取**檔案 > 新建 > 專案**。
2. 從 JavaScript 種類選取 **JavaScript 專案**。
3. 按**下一步**。
4. 命名專案。
5. 按一下**完成**。

定義新的伺服器。

1. 若要建立新的 Cloud 伺服器，請選取**檔案 > 新建 > 其他**
2. 從「伺服器」種類選取**伺服器**，然後按**下一步**。
3. 在 IBM 下尋找 Cloud。
4. 按**下一步**。
5. 輸入您的 Cloud 帳戶資訊。如果沒有帳戶，請按一下**註冊**。
6. 按**下一步**。
7. 選擇您的組織及空間。預設值是 `dev`。
8. 按**下一步**。
9. 按一下**完成**。

啟用應用程式以便發佈至 Cloud

1. 在專案瀏覽器中，在專案按一下滑鼠右鍵，然後選擇**內容 > 專案資料類型**。
2. 按一下**轉換成資料類型表單**。
3. 在「專案資料類型」下，選取 **Node.js 應用程式**。
4. 按一下**確定**。

部署應用程式。

1. 在已啟動的 Cloud 伺服器按一下滑鼠右鍵。選擇**新增及移除**。
2. 選擇專案，然後按一下**新增**。
3. 按一下**完成**。即會開啟「應用程式詳細資料」視窗。
4. 若要將部署配置儲存到應用程式的資訊清單檔，請選取「應用程式詳細資料」視窗中的**儲存至資訊清單檔**勾選框。
5. 命名該應用程式，然後按**下一步**。有效名稱可包含 A-Z、0-9、- 及 _。但不得包含空格或其他特殊字元。
6. 在「啟動部署」資訊畫面上接受預設值。
7. 按**下一步**。
8. 必要的話，請選取服務。按**下一步**。
9. 必要的話，請新增變數。按一下**完成**。
10. 推送應用程式之後，在專案上按一下滑鼠右鍵，然後選擇**開啟首頁**。

## 漸進式發佈

您可以漸進式地更新應用程式檔案，而不必重新推送整個應用程式。漸進式發佈讓您不必針對每項變更執行完整的重新部署，節省整個開發過程的時間。


這個特性支援 Web 應用程式（WAR 及 EAR）和包裝伺服器。


若要使用漸進式發佈，必須啟用應用程式或包裝伺服器的[開發模式](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html)。

1. 將應用程式或包裝伺服器新增至 Cloud，除非已存在。**附註：**如果應用程式部署名稱有底線，便無法啟用此功能。

2. 藉由在應用程式或包裝伺服器上按一下滑鼠右鍵，然後選取**啟用開發模式**，來啟用開發模式。

啟用開發模式之後，請使用漸進式發佈功能：

1. 視需要修改應用程式。**附註：**對於包裝伺服器，不支援修改配置。

2. 儲存變更。

3. 在 Cloud 伺服器上按一下滑鼠右鍵，然後選取**發佈**。

快取模式：重新啟動工作台之後，如果應用程式處於開發模式或除錯模式，您會看到進度視窗指出「正在擷取開發及除錯狀態」。進度完成之後，開發模式及除錯模式會相應地重新整理。

## 遠端除錯

對 Liberty 或 Node.js 應用程式執行遠端除錯。

必須啟用[開發模式](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html)才能執行除錯。此模式會在選取「啟用應用程式除錯」時自動執行。

### 啟用企業保存檔 (EAR)、Web 保存檔 (WAR) 或 Liberty Server 的除錯

目前，會隨機產生免費的本端埠，但如果用戶端防火牆封鎖它，除錯情境便會失敗。要略過此點，請啟動開發模式、找到 bluemixcache.xml 檔，然後新增 port="#"，其中 # 是本端機器的埠號。

1. 在 Cloud 伺服器下，在您要除錯的應用程式按一下滑鼠右鍵。

   **附註：**如果應用程式部署名稱有底線，便無法啟用此功能。請先變更名稱再啟用遠端除錯。

2. 按一下**啟用應用程式除錯**。

   「進度視圖」會顯示 `Establishing debug session for <AppName>` 的狀態。

   應用程式顯示它正在 `Developing, Debugging <AppName>`。

   除錯器正在執行，且可以使用。

### 停用 EAR、WAR 或 Liberty Server 的除錯

您可以停用除錯程序，並維持啟用開發模式。

1. 在應用程式按一下滑鼠右鍵。
2. 按一下**停用應用程式除錯**。
3. 會有對話框詢問您是否也要停用開發模式。按一下**是**或**否**。

如果開發模式維持啟用，應用程式會顯示它正在 `Developing <AppName>`。

 如果兩者都已停用，應用程式會顯示它 `Deployed as <AppName>`。

### 啟用 Node.js 應用程式的除錯

**附註：**在完成下列步驟之前，請確定您有部署至 Cloud 的現有 JavaScript 應用程式。請參閱先前的步驟，以取得部署 JavaScript 應用程式的相關資訊。

1. 在「伺服器」視圖中，在 Node.js 應用程式按一下滑鼠右鍵，然後選取**開啟** JavaScript Debugger。會出現對話框並詢問您是否要增加應用程式的記憶體限制。
2. 按一下「是」。啟用 JavaScript 除錯會增加應用程式記憶體需求，而應用程式會因為更新的記憶體限制加快重新啟動的速度。
3. 選取瀏覽器安裝以用於除錯。Google Chrome 是唯一受支援的瀏覽器。如果 Google Chrome 不是可用的選項，請選取**管理...** 鏈結，並新增本端 Google Chrome 安裝的鏈結。
4. 按一下**確定**。會出現一個進度顯示器，指出正在更新（您的應用程式）至除錯模式。啟用除錯之後，Google Chrome 會開啟到正確的網站。
5. 使用您的登入名稱及密碼在 Google Chrome 中進行鑑別。成功鑑別之後，會開啟除錯主控台。您現在可以進行應用程式的除錯。

快取模式：重新啟動工作台之後，如果應用程式處於開發模式或除錯模式，您會看到進度視窗指出「正在擷取開發及除錯狀態」。進度完成之後，開發模式及除錯模式會重新整理。

## 連接至遠端 Liberty Server

了解如何使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 連接至遠端 Liberty Server。您可以連接至以服務形式執行 WebSphere Application Server 的遠端 Liberty Server。

若要連接至遠端 Liberty Server，必須安裝 Liberty Tools。您也必須在 Cloud 上建立 WebSphere Application Server 服務。

1. 在您的 Cloud 伺服器按一下滑鼠右鍵，然後選取**配置遠端伺服器...**。

   這個選項只適用於已安裝 Liberty Tools 的情況。

2. 選取 WebSphere Application Server 服務。

   如果您沒有 WebSphere Application Server 服務，可能會收到錯誤訊息。您必須先在 Cloud 上建立 WebSphere Application Server 服務，才能完成此設定。

3. 若要定義運行環境，請選取**配置運行環境...**。

   **附註：**如果您先前已建立運行環境，則可以跳過此步驟。

4. 按**下一步**。

5. 輸入伺服器連線資訊。

6. 按一下**完成**。

您已使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 連接至遠端 Liberty Server。

## 在 Cloud 應用程式上啟用 Cloud Foundry Diego

從 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 內啟用 Diego 架構功能。若要啟用 Diego，您需要在「伺服器」視圖中已定義的 Cloud 伺服器。

Diego 是新的 Cloud Foundry 架構，Cloud Foundry 實例使用它來管理執行中的應用程式容器。Diego 架構取代了 Cloud Foundry 先前使用的 Droplet Execution Agent (DEA) 架構。Cloud Foundry 安裝即將移至 Diego，使用者應用程式會自動且透通地切換至新的架構。

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 支援 Diego 及 DEA。您可以發佈應用程式、啟用漸進式應用程式發佈，以及進行應用程式的除錯。Diego 也容許 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 建立安全 Shell (SSH) 通道，連至已部署的 Cloud 應用程式，如此一來便容許在除錯時有更快速且更可靠的 Cloud 應用程式連線。您也可以啟用 SSH，以便自行建立通道來存取應用程式資源。

請完成下列步驟，以在 Cloud 切換至依預設使用 Diego 部署之前，針對應用程式使用 Diego 架構：

1. 在「伺服器」視圖中，於已部署的應用程式上按一下滑鼠右鍵。
2. 如果在 Cloud 伺服器上已支援 Diego，而您的應用程式尚未使用 Diego 部署，請從功能表選取**啟用 Diego**。
3. 如果伺服器支援 SSH 通道作業，程式會詢問您是否要為應用程式啟用 SSH。SSH 通道對於與應用程式通訊而言是更可靠的機制。不過，如果您選取**否**，則 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 中的功能會繼續使用不需要 SSH 通道作業的機制運作。

然後應用程式會使用 Diego 架構重新部署。

## 使用 Cloud Enterprise Federation 建立伺服器

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 支援 Cloud Enterprise Federation，這是一個單一登入服務，能讓使用者安全地存取雲端服務。使用 Cloud Enterprise Federation，您可以啟用由自已組織所提供的自訂協力廠商鑑別，而不使用標準登入鑑別，讓其他使用者安全地存取應用程式。

Cloud Enterprise Federation 會鑑別一組使用者，以便存取雲端服務。在您啟用 Cloud Enterprise Federation 之後，您的使用者會透過單一登入選項收到已啟用雲端功能之應用程式的鑑別。使用者必須選取單一登入選項，以在 Eclipse 工作台裡建立伺服器，並使用組織登入及密碼進行登入。啟用 Cloud Enterprise Federation 之後，不再使用 Eclipse Tools 中的傳統 Cloud 使用者 ID和密碼來鑑別使用者。

1. 在 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 中，選取**檔案 > 新建 > 其他...**。
2. 選取**伺服器 > 伺服器 > 下一步**。
3. 從樹狀結構選取 **IBM > {{site.data.keyword.Bluemix_notm}} > 下一步**。
4. 選取**使用一次性密碼登入 (SSO)** 勾選框。
5. 超鏈結會出現在登入對話框中。請按一下超鏈結來開啟 Cloud 鑑別頁面。
6. 輸入您的電子郵件位址和想要的密碼。
7. 成功登入之後，會提供您一次性密碼。將這個密碼複製到 Eclipse Tools for Cloud「新建伺服器」對話框的「密碼：」欄位。
8. 按一下**完成**。

Cloud 伺服器項目會列在「伺服器」視圖中，並且「伺服器狀態」為「已連接」。
