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
{:note: .note}

# Contributing to the SDK plug-in
{: #contribute}

Follow these guidelines to contribute to the {{site.data.keyword.Bluemix}} CLI SDK plug-in.

## Setting up your development environment
{: #dev-env}

* Cloud Foundry [CLI ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/cloudfoundry/cli/releases).

   The Cloud Foundry CLI is not required, but it helps to access {{site.data.keyword.Bluemix_notm}} from the Terminal.

   For more information about the Cloud Foundry CLI, see the [documentation](/docs/cli/reference/cfcommands/index.html).

* {{site.data.keyword.Bluemix_notm}} [CLI](/docs/cli/index.html#overview).

   This plug-in installs into the {{site.data.keyword.Bluemix_notm}} CLI. The {{site.data.keyword.Bluemix_notm}} CLI also provides useful resources to access {{site.data.keyword.Bluemix_notm}} from the Terminal.

* Go's [development environment ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://golang.org/doc/code.html)

   Go is strict with regards to package locations, so your source must be defined within the `$GOPATH` directory structure. Ensure that you define your `$GOPATH` and `$GOROOT` variables and that you include `$GOPATH/bin` in your `$PATH` environment variable, which can be done by editing your `~/.bash_profile` configuration file (on Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Dependency manager: [govendor ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/kardianos/govendor)

   The `govendor` tool creates and manages the Go dependencies. You do not need it unless you plan to update the vendor directory.

   * Install it by using the following command.

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Initialize `govendor` on your project directory by using the following command.

      ```
      govendor init
      ```
      {: codeblock}

   * Add dependencies from `$GOPATH` to the vendor directory by using the following command.

      ```
      govendor add +local
      ```
      {: codeblock}

* BDD test framework: [Ginkgo ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://onsi.github.io/ginkgo/)

The test framework is based on Ginkgo, a BDD testing framework for Go. It is used with [Gomega ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://onsi.github.io/gomega/), which is a matcher and assertion library for Ginkgo.

   * Install `ginkgo` by using the following command.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Install `gomega` by using the following command.

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Run unit tests by using the following command.

      ```
      ginkgo -r
      ```
      {: codeblock}

      * To add code coverage, append `-cover` to the command.

   * Obtain a friendly HTML form of the code coverage, use the following command.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * You will go to the directory where the `.coverprofile` file is located.

* Internationalization: [go-i18n ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/nicksnyder/go-i18n) and [go-bindata ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/jteeuwen/go-bindata)

Internationalization is based on go-i18n, which is a package and command-line tool that provides support to translate a Go application into multiple languages. Translation bundles are pre-processed by go-bindata, which is a command that converts any input file into manageable Go source code.

   * Install `go-i18n` by using the following command.

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Install `go-bindata` by using the following command.

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Debugging: [delve ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/derekparker/delve)

Delve is a debugger for the Go programming language, and is used by [Visual Studio Code ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://code.visualstudio.com/).

   * Install `delve` by using the following command.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * For Mac OS, follow the [instructions ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) to create the required self-signed certificate.


## Required runtime libraries
{: #runtime-libs}

The required runtime libraries are managed under the `vendor` directory and are committed to the Git repository to ensure stability, as Go does not provide a robust dependency manager.

### Runtime dependencies
{: #runtime-dependencies}

Nested dependencies are not listed.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   The {{site.data.keyword.Bluemix_notm}} CLI plug-in SDK, which provides infrastructure to develop {{site.data.keyword.Bluemix_notm}} CLI plug-ins.

* [github.com/urfave/cli ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/urfave/cli)

   This package provides infrastructure to build command-line apps in Go. The {{site.data.keyword.Bluemix_notm}} CLI plugin relies on an older version of this library (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/asaskevich/govalidator)

   This package provides a number of validators and sanitizers for strings, structs, and collections. Use this package instead of implementing our own validators.

* [github.com/parnurzeal/gorequest ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/parnurzeal/gorequest)

   This package implements a simplified HTTP client to help handle HTTP requests and responses.

* [github.com/briandowns/spinner ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/briandowns/spinner)

   This package implements a CLI spinner to provide user feedback while long operations, such as SDK generation, are being processed.

* [github.com/cloudfoundry-attic/jibber_jabber ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/cloudfoundry-attic/jibber_jabber)

   This package is used to detect the current language of the operating system.

## Cloning the repository
{: #clone-repo}

The repository must be cloned into Go's [directory structure ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://golang.org/doc/code.html) because of how `govendor` works, which also follows Go's best practices.

* Import internal dependencies through a fully qualified package name.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Clone the repository.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Building, testing, and installing the plug-in
{: #build-plug-in}

Build the plug-in by choosing either of the following commands.

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

The build script also installs the plug-in to the {{site.data.keyword.Bluemix_notm}} CLI.
{: note}

Test the plug-in by choosing either of the following commands.

```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Run integration tests with unit tests and coverage.

```
sh bin/testAll.sh
```
{: codeblock}

Run the plug-in as a stand-alone CLI.

```
./main
```
{: codeblock}

Install and invoke the plug-in as a {{site.data.keyword.Bluemix_notm}} CLI by choosing either of the following commands.

```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
