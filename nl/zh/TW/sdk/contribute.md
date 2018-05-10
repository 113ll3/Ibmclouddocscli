---

copyright:
  years: 2017
lastupdated: "2018-03-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 提出至 SDK 外掛程式
{: #contribute}

請遵循下列準則來提出至 {{site.data.keyword.Bluemix}} CLI SDK 外掛程式。

## 設定開發環境
{: #dev-env}

* Cloud Foundry [CLI ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/cloudfoundry/cli/releases)

   Cloud Foundry CLI 不是必要項目，但它有助於從「終端機」存取 {{site.data.keyword.Bluemix_notm}}。

   如需 Cloud Foundry CLI 的相關資訊，請參閱[文件 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/cli/reference/cfcommands/index.html){: new_window}。

* {{site.data.keyword.Bluemix_notm}} [CLI ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://clis.{DomainName}/ui/home.html)

   此外掛程式會安裝至 {{site.data.keyword.Bluemix_notm}} CLI。{{site.data.keyword.Bluemix_notm}} CLI 也會提供有用的資源，以從「終端機」存取 {{site.data.keyword.Bluemix_notm}}。

   如需 {{site.data.keyword.Bluemix_notm}} CLI 的相關資訊，請參閱[文件 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/cli/reference/bluemix_cli/index.html){: new_window}。

* Go 的[開發環境 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://golang.org/doc/code.html)

   Go 嚴格遵守包裝位置，因此您的來源必須定義在 `$GOPATH` 目錄結構內。請確定已定義 `$GOPATH` 及 `$GOROOT` 變數，而且您在 `$PATH` 環境變數中包含 `$GOPATH/bin`，這只要編輯 `~/.bash_profile` 配置檔就能做到（在 Mac OS 上）。

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* 相依關係管理員：[govendor ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/kardianos/govendor)

   `govendor` 工具會建立及管理 Go 相依關係。除非您計劃更新供應商目錄，否則不需要它。

   * 使用下列指令進行安裝。

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * 使用下列指令，起始設定專案目錄上的 `govendor`。

      ```
      govendor init
      ```
      {: codeblock}

   * 使用下列指令，將相依關係從 `$GOPATH` 新增至供應商目錄。

      ```
      govendor add +local
      ```
      {: codeblock}

* BDD 測試架構：[Ginkgo ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://onsi.github.io/ginkgo/)

測試架構是以 Ginkgo 為基礎（Go 的 BDD 測試架構）。它是與 [Gomega ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://onsi.github.io/gomega/) 搭配使用，後者是 Ginkgo 的配對器及主張程式庫。

   * 使用下列指令，安裝 `ginkgo`。

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * 使用下列指令，安裝 `gomega`。

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * 使用下列指令，執行單元測試。

      ```
      ginkgo -r
      ```
      {: codeblock}

      * 若要新增程式碼涵蓋面，請將 `-cover` 附加至指令。

   * 使用下列指令，取得程式碼涵蓋面的易記 HTML 表單。

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * 您將移至 `.coverprofile` 檔案所在的目錄。

* 國際化：[go-i18n ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/nicksnyder/go-i18n) 及 [go-bindata ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/jteeuwen/go-bindata)

國際化是以 go-i18n 為基礎，它是一個套件及指令行工具，支援將 Go 應用程式翻譯為多種語言。翻譯軟體組是由 go-bindata 預先處理，它是將任何輸入檔轉換成可管理 Go 原始碼的指令。

   * 使用下列指令，安裝 `go-i18n`。

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * 使用下列指令，安裝 `go-bindata`。

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* 除錯：[delve ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/derekparker/delve)

Delve 是 Go 程式設計語言的除錯器，並供 [Visual Studio Code ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://code.visualstudio.com/) 使用。

   * 使用下列指令，安裝 `delve`。

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * 若為 Mac OS，請遵循[指示 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) 來建立所需的自簽憑證。


## 必要運行環境程式庫
{: #runtime-libs}

必要運行環境程式庫是在 `vendor` 目錄下進行管理，並確定至 Git 儲存庫以確保穩定性，因為 Go 未提供強健的相依關係管理員。

### 運行環境相依關係
{: #runtime-dependencies}

未列出巢狀相依關係。

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   {{site.data.keyword.Bluemix_notm}} CLI 外掛程式 SDK，提供開發 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式的基礎架構。

* [github.com/urfave/cli ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/urfave/cli)

   此套件提供在 Go 中建置指令行應用程式的基礎架構。{{site.data.keyword.Bluemix_notm}} CLI 外掛程式依賴此程式庫的較舊版本 (github.com/codegangsta/cli)。

* [github.com/asaskevich/govalidator ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/asaskevich/govalidator)

   此套件提供一些用於字串、結構及集合的驗證器和消毒器。請使用此套件，而不要實作我們自己的驗證器。

* [github.com/parnurzeal/gorequest ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/parnurzeal/gorequest)

   此套件實作簡化的 HTTP 用戶端，以協助處理 HTTP 要求及回應。

* [github.com/briandowns/spinner ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/briandowns/spinner)

   此套件實作 CLI 微調按鈕，以在處理 SDK 產生這類長時間作業時提供使用者意見。

* [github.com/cloudfoundry-attic/jibber_jabber ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/cloudfoundry-attic/jibber_jabber)

   此套件用來偵測作業系統的現行語言。


## 複製儲存庫
{: #clone-repo}

此[儲存庫 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) 必須複製至 Go 的[目錄結構 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://golang.org/doc/code.html)，因為 `govendor` 的運作方式，這也遵循 Go 的最佳作法。

* 透過完整的套件名稱匯入內部相依關係。

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* 複製儲存庫。

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## 建置、測試及安裝外掛程式
{: #build-plug-in}

請選擇下列一個指令，以建置外掛程式。

```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
go build main.go
```
{: codeblock}

```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
sh bin/build.sh
```
{: codeblock}

**附註**：建置 Script 也會將外掛程式安裝至 {{site.data.keyword.Bluemix_notm}} CLI。

請選擇下列一個指令，以測試外掛程式。

```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

使用單元測試及涵蓋面來執行整合測試。

```
sh bin/testAll.sh
```
{: codeblock}

將外掛程式當成獨立式 CLI 來執行。

```
./main
```
{: codeblock}

請選擇下列一個指令，以安裝及呼叫外掛程式作為 {{site.data.keyword.Bluemix_notm}} CLI。

```
bluemix plugin install main
bluemix help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
