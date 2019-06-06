---

copyright:
  years: 2017, 2019
lastupdated: "2019-06-06"

keywords: cli, contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Contributing to the SDK plug-in
{: #contribute}

Follow these guidelines to contribute to the {{site.data.keyword.cloud}} CLI SDK plug-in.

## Setting up your development environment
{: #dev-env}

* Cloud Foundry [CLI](https://github.com/cloudfoundry/cli/releases){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon").

   The Cloud Foundry CLI isn't required, but it helps to access {{site.data.keyword.cloud_notm}} from a terminal.

   For more information about the Cloud Foundry CLI, see the [documentation](/docs/cli?topic=cloud-cli-cf#cf).

* {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   This plug-in is added to the {{site.data.keyword.cloud_notm}} CLI and provides useful resources to access {{site.data.keyword.cloud_notm}} from the command line.

* Go's [development environment](https://golang.org/doc/code.html){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   Go is strict with package locations, so your source must be defined within the `$GOPATH` directory structure. You must define your `$GOPATH` and `$GOROOT` variables, and include `$GOPATH/bin` in your `$PATH` environment variable. You can edit the `~/.bash_profile` configuration file (on Mac) to make these changes.

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Dependency manager: [`govendor`](https://github.com/kardianos/govendor){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   The `govendor` tool creates and manages the Go dependencies. You don't need it unless you plan to update the vendor directory.

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

* BDD test framework: [Ginkgo](http://onsi.github.io/ginkgo/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

The test framework is based on Ginkgo, a BDD testing framework for Go, and is used with [`gomega`](http://onsi.github.io/gomega/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon"), which is a matcher and assertion library for Ginkgo.

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

   * To obtain a friendly HTML form of the code coverage, use the following command.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * You are taken to the directory where the `.coverprofile` file is located.

* Globalization: [go-i18n](https://github.com/nicksnyder/go-i18n){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") and [go-bindata](https://github.com/jteeuwen/go-bindata){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

Globalization is based on `go-i18n`, which is a package and command line tool that provides support to translate a Go application into multiple languages. Translation bundles are pre-processed by the `go-bindata` command that converts any input file into manageable Go source code.

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

* Debugging: [delve](https://github.com/go-delve/delve){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

Delve is a debugger for the Go programming language, and is used by [Visual Studio Code](https://code.visualstudio.com/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon").

   * Install `delve` by using the following command.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * For Mac OS, follow the [instructions](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") to create the required self-signed certificate.


## Required runtime libraries
{: #runtime-libs}

The required runtime libraries are managed under the `vendor` directory and are committed to the Git repository to ensure stability, as Go doesn't provide a robust dependency manager.

### Runtime dependencies
{: #runtime-dependencies}

Nested dependencies aren't listed.

* [github.com/IBM-Cloud/ibm-cloud-cli-sdk](https://github.com/IBM-Cloud/ibm-cloud-cli-sdk){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   The {{site.data.keyword.cloud_notm}} CLI plug-in SDK, which provides infrastructure to develop {{site.data.keyword.cloud_notm}} CLI plug-ins.

* [github.com/urfave/cli](https://github.com/urfave/cli){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   This package provides infrastructure to build command line apps in Go. The {{site.data.keyword.cloud_notm}} CLI plug-in relies on an older version of this library (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator](https://github.com/asaskevich/govalidator){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   This package provides a number of validators and sanitizers for strings, structs, and collections. Use this package instead of implementing your own validators.

* [github.com/parnurzeal/gorequest](https://github.com/parnurzeal/gorequest){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   This package implements a simplified HTTP client to help handle HTTP requests and responses.

* [github.com/briandowns/spinner](https://github.com/briandowns/spinner){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   This package implements a CLI spinner to provide user feedback while long operations, such as SDK generation, are being processed.

* [github.com/cloudfoundry-attic/jibber_jabber](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon")

   This package is used to detect the current language of the operating system.

## Cloning the repository
{: #clone-repo}

The repository must be cloned into Go's [directory structure](https://golang.org/doc/code.html){: new_window} ![External link icon](../../icons/launch-glyph.svg "External link icon") because of how `govendor` works, which also follows Go's best practices.

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

Install and invoke the plug-in as a {{site.data.keyword.cloud_notm}} CLI by choosing either of the following commands.
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
