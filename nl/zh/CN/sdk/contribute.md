---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-03"

keywords: cli, contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# 帮助改进 SDK 插件
{: #contribute}

请遵循以下准则来帮助改进 {{site.data.keyword.cloud}} CLI SDK 插件。

## 设置开发环境
{: #dev-env}

* Cloud Foundry [CLI ](https://github.com/cloudfoundry/cli/releases){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

   Cloud Foundry CLI 不是必需的，但它可帮助您通过终端访问 {{site.data.keyword.cloud_notm}}。

   有关 Cloud Foundry CLI 的更多信息，请参阅[文档](/docs/cli?topic=cloud-cli-cf#cf)。

* {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。

   此插件会安装到 {{site.data.keyword.cloud_notm}} CLI 中。{{site.data.keyword.cloud_notm}} CLI 还提供了用于通过终端访问 {{site.data.keyword.cloud_notm}} 的有用资源。

* Go 的[开发环境 ](https://golang.org/doc/code.html){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   Go 对软件包位置有严格限制，因此必须在 `$GOPATH` 目录结构内定义源。确保定义 `$GOPATH` 和 `$GOROOT` 变量，并确保在 `$PATH` 环境变量中包含 `$GOPATH/bin`，这可通过编辑 `~/.bash_profile` 配置文件（在 Mac OS 上）来完成。

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* 依赖关系管理器：[govendor ](https://github.com/kardianos/govendor){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   `govendor` 工具用于创建和管理 Go 依赖关系。除非您计划更新供应商目录，否则无需此工具。

   * 使用以下命令安装 govendor。

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * 使用以下命令对项目目录上的 `govendor` 进行初始化。

      ```
      govendor init
      ```
      {: codeblock}

   * 使用以下命令将 `$GOPATH` 中的依赖关系添加到供应商目录。

      ```
      govendor add +local
      ```
      {: codeblock}

* BDD 测试框架：[Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

测试框架基于 Ginkgo，这是用于 Go 的 BDD 测试框架。它与 [Gomega ](http://onsi.github.io/gomega/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 配合使用，Gomega 是 Ginkgo 的匹配器和断言库。

   * 使用以下命令安装 `ginkgo`。

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * 使用以下命令安装 `gomega`。

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * 使用以下命令运行单元测试。

      ```
      ginkgo -r
      ```
      {: codeblock}

      * 要添加代码覆盖范围，请在命令后面附加 `-cover`。

   * 要获取易用 HTML 形式的代码覆盖范围，请使用以下命令。

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * 您将转至 `.coverprofile` 文件所在的目录。

* 国际化：[go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 和 [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

国际化基于 `go-i18n`，这是一个软件包和命令行工具，支持将 Go 应用程序翻译成多种语言。翻译捆绑软件由 `go-bindata` 进行预处理，这是用于将任何输入文件转换为可管理 Go 源代码的命令。

   * 使用以下命令安装 `go-i18n`。

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * 使用以下命令安装 `go-bindata`。

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* 调试：[delve ](https://github.com/go-delve/delve){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

Delve 是用于 Go 编程语言的调试器，并由 [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 使用。

   * 使用以下命令安装 `delve`。

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * 对于 Mac OS，请遵循[指示信息 ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 来创建必需的自签名证书。


## 必需的运行时库
{: #runtime-libs}

必需的运行时库在 `vendor` 目录下进行管理，并已落实到 Git 存储库以确保稳定性，因为 Go 未提供稳健的依赖关系管理器。

### 运行时依赖关系
{: #runtime-dependencies}

未列出嵌套依赖关系。

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   {{site.data.keyword.cloud_notm}} CLI 插件 SDK，提供用于开发 {{site.data.keyword.cloud_notm}} CLI 插件的基础架构。

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   此软件包提供用于使用 Go 构建命令行应用程序的基础架构。{{site.data.keyword.cloud_notm}} CLI 插件依赖于此库的较旧版本 (github.com/codegangsta/cli)。

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   此软件包提供了用于字符串、结构和集合的多个验证器和杀毒器。请使用此软件包，而不要实现自己的验证器。

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   此软件包实现简化的 HTTP 客户机，以帮助处理 HTTP 请求和响应。

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   此软件包实现 CLI 微调器，用于在处理长时间操作（如 SDK 生成）时提供用户反馈。

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")

   此软件包用于检测操作系统的当前语言。

## 克隆存储库
{: #clone-repo}

由于 `govendor` 的工作方式（同样遵循 Go 的最佳实践），此存储库必须克隆到 Go 的[目录结构 ](https://golang.org/doc/code.html){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

* 通过标准软件包名称导入内部依赖关系。

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* 克隆存储库。

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## 构建、测试和安装插件
{: #build-plug-in}

通过选择以下任一命令来构建插件。
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

构建脚本还会将插件安装到 {{site.data.keyword.Bluemix_notm}} CLI。
{: note}

通过选择以下任一命令来测试插件。
```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

使用单元测试和覆盖范围来运行集成测试。
```
sh bin/testAll.sh
```
{: codeblock}

将插件作为独立 CLI 运行。
```
./main
```
{: codeblock}

通过选择以下任一命令来安装插件并将其作为 {{site.data.keyword.cloud_notm}} CLI 进行调用。
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
