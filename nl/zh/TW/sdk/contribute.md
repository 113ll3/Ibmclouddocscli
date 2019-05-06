---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-29"

keywords: cli, contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# 提出至 SDK 外掛程式
{: #contribute}

請遵循下列準則來提出至 {{site.data.keyword.cloud}} CLI SDK 外掛程式。

## 設定開發環境
{: #dev-env}

* Cloud Foundry [CLI ](https://github.com/cloudfoundry/cli/releases){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。

   Cloud Foundry CLI 不是必要項目，但它有助於從終端機存取 {{site.data.keyword.cloud_notm}}。

   如需 Cloud Foundry CLI 的相關資訊，請參閱[文件](/docs/cli?topic=cloud-cli-cf#cf)。

* {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   此外掛程式會新增至 {{site.data.keyword.cloud_notm}} CLI，並提供有用的資源，以從終端機存取 {{site.data.keyword.cloud_notm}}。

* Go 的[開發環境 ](https://golang.org/doc/code.html){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   Go 嚴格遵守套件位置，因此您的原始碼必須定義在 `$GOPATH` 目錄結構內。您必須定義 `$GOPATH` 及 `$GOROOT` 變數，並將 `$GOPATH/bin` 包含在 `$PATH` 環境變數中。您可以編輯 `~/.bash_profile` 配置檔（在 Mac 上），以進行這些變更。

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* 相依關係管理員：[`govendor `](https://github.com/kardianos/govendor){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

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

* BDD 測試架構：[Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

測試架構是以 Ginkgo 為基礎（Go 的 BDD 測試架構），並與 [`gomega`](http://onsi.github.io/gomega/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 搭配使用，gomega 是 Ginkgo 的配對器及主張程式庫。

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

   * 若要取得程式碼涵蓋面的易記 HTML 表單，請使用下列指令。

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * 您會被帶至 `.coverprofile` 檔案所在的目錄。

* 全球化：[go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 及 [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

全球是以 `go-i18n` 為基礎，它是一個套件及指令行工具，支援將 Go 應用程式翻譯為多種語言。翻譯軟體組是由 `go-bindata` 指令預先處理，此指令會將任何輸入檔轉換成可管理的 Go 原始碼。

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

* 除錯：[delve ](https://github.com/go-delve/delve){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

Delve 是 Go 程式設計語言的除錯器，並供 [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 使用。

   * 使用下列指令，安裝 `delve`。

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * 若為 Mac OS，請遵循[指示 ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 來建立所需的自簽憑證。


## 必要運行環境程式庫
{: #runtime-libs}

必要運行環境程式庫是在 `vendor` 目錄下進行管理，並確定至 Git 儲存庫以確保穩定性，因為 Go 未提供強健的相依關係管理員。

### 運行環境相依關係
{: #runtime-dependencies}

未列出巢狀相依關係。

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   {{site.data.keyword.cloud_notm}} CLI 外掛程式 SDK，提供開發 {{site.data.keyword.cloud_notm}} CLI 外掛程式的基礎架構。

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   此套件提供在 Go 中建置指令行應用程式的基礎架構。{{site.data.keyword.cloud_notm}} CLI 外掛程式依賴此程式庫的較舊版本 (github.com/codegangsta/cli)。

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   此套件提供一些用於字串、結構及集合的驗證器和消毒器。請使用此套件，而不要實作您自己的驗證器。

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   此套件實作簡化的 HTTP 用戶端，以協助處理 HTTP 要求及回應。

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   此套件實作 CLI 微調按鈕，以在處理 SDK 產生這類長時間作業時提供使用者意見。

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")

   此套件用來偵測作業系統的現行語言。

## 複製儲存庫
{: #clone-repo}

基於 `govendor` 的運作方式（這也遵循 Go 的最佳作法），必須將儲存庫複製到 Go 的[目錄結構 ](https://golang.org/doc/code.html){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。

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

建置 Script 也會將外掛程式安裝至 {{site.data.keyword.Bluemix_notm}} CLI。
{: note}

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

請選擇下列一個指令，以安裝及呼叫外掛程式作為 {{site.data.keyword.cloud_notm}} CLI。
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
