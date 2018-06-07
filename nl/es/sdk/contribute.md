---

copyright:
  years: 2017
lastupdated: "2018-05-23"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Contribución al plugin SDK
{: #contribute}

Siga estas directrices para contribuir al plugin {{site.data.keyword.Bluemix}} CLI SDK.

## Configuración del entorno de desarrollo
{: #dev-env}

* Cloud Foundry [CLI ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/cloudfoundry/cli/releases)

   Cloud Foundry CLI no es necesario, pero permite acceder a {{site.data.keyword.Bluemix_notm}} desde el terminal.

   Para obtener más información sobre Cloud Foundry CLI, consulte la [documentación ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](/docs/cli/reference/cfcommands/index.html){: new_window}.

* {{site.data.keyword.Bluemix_notm}} [CLI ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://clis.{DomainName}/ui/home.html)

   Este plugin se instala en {{site.data.keyword.Bluemix_notm}} CLI. {{site.data.keyword.Bluemix_notm}} CLI también proporciona recursos útiles para acceder a {{site.data.keyword.Bluemix_notm}} desde el terminal.

   Para obtener más información sobre {{site.data.keyword.Bluemix_notm}} CLI, consulte la [documentación ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](/docs/cli/reference/bluemix_cli/index.html){: new_window}.

* [Entorno de desarrollo ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://golang.org/doc/code.html) de Go

   Go es un lenguaje estricto con relación a ubicaciones de paquetes, por ello, el código fuente se debe definir dentro de la estructura de directorios `$GOPATH`. Asegúrese de definir las variables `$GOPATH` y `$GOROOT` y de incluir `$GOPATH/bin` en su variable de entorno `$PATH`. Si es necesario, edite su archivo de configuración `~/.bash_profile` (en Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestor de dependencias: [govendor ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/kardianos/govendor)

   La herramienta `govendor` crea y gestiona las dependencias de Go. No es necesario a no ser que piense actualizar el directorio de proveedor.

   * Instálelo con el siguiente mandato.

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Inicialice `govendor` en el directorio del proyecto utilizando el mandato siguiente.

      ```
      govendor init
      ```
      {: codeblock}

   * Añada dependencias desde `$GOPATH` al directorio de proveedor utilizando el siguiente mandato.

      ```
      govendor add +local
      ```
      {: codeblock}

* Infraestructura de prueba BDD: [Ginkgo ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://onsi.github.io/ginkgo/)

La infraestructura de prueba se basa en Ginkgo, una infraestructura de pruebas BDD para Go. Se utiliza con [Gomega ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://onsi.github.io/gomega/), una biblioteca de aserciones y coincidencias para Ginko.

   * Instale `gingko` utilizando el mandato siguiente.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Instale `gingko` utilizando el mandato siguiente.

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Ejecute pruebas de unidad mediante el mandato siguiente.

      ```
      ginkgo -r
      ```
      {: codeblock}

      * Para añadir cobertura de código, añada `-cover` al mandato.

   * Utilice el siguiente mandato para obtener HTML preparado para la cobertura de código.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Irá al directorio en el que se encuentra ubicado el archivo `.coverprofile`.

* Internacionalización: [go-i18n ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/nicksnyder/go-i18n) y [go-bindata ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/jteeuwen/go-bindata)

La internacionalización se basa en go-i18n, un paquete y una herramienta de línea de mandatos que proporciona soporte para traducir una aplicación Go en distintos lenguajes. Los paquetes de traducción están procesados de forma previa por go-bindata, un mandato que convierte cualquier archivo de entrada en un código fuente Go gestionable.

   * Instale `go-i18n` utilizando el siguiente mandato.

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Instale `go-bindata` utilizando el siguiente mandato.

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Depuración: [delve ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/derekparker/delve)

Delve es un depurador para el lenguaje de programación Go que [Visual Studio Code ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://code.visualstudio.com/) utiliza.

   * Instale `delve` utilizando el siguiente mandato.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Para Mac OS, sigas las [instrucciones ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) para crear el certificado autofirmado necesario.


## Bibliotecas de tiempo de ejecución necesarias
{: #runtime-libs}

Las bibliotecas de tiempo de ejecución necesarias están gestionadas bajo el directorio `vendor` y están confirmadas en el repositorio Git para asegurar estabilidad, puesto que Go no proporciona un gestor robusto de dependencias.

### Dependencias de tiempo de ejecución
{: #runtime-dependencies}

Las dependencias anidadas no están listadas.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   El plugin {{site.data.keyword.Bluemix_notm}} CLI SDK, que proporciona la infraestructura para desarrollar plugins de {{site.data.keyword.Bluemix_notm}} CLI.

* [github.com/urfave/cli ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/urfave/cli)

   Este paquete proporciona una infraestructura para compilar apps de línea de mandatos en Go. El plugin {{site.data.keyword.Bluemix_notm}} CLI se basa en una versión antigua de esta biblioteca (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/asaskevich/govalidator)

   Este paquete proporciona una serie de validadores y sanitizantes para series, estructuras y colecciones. Utilice este paquete en lugar de aplicar nuestros propios validadores.

* [github.com/parnurzeal/gorequest ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/parnurzeal/gorequest)

   Este paquete implementa un cliente HTTP simplificado para ayudar a manejar las solicitudes y respuestas HTTP.

* [github.com/briandowns/spinner ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/briandowns/spinner)

   Este paquete implementa un control spinner de CLI para proporcionar comentarios de usuario mientras se están procesando operaciones extensas, como las de generación de SDK.

* [github.com/cloudfoundry-attic/jibber_jabber ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/cloudfoundry-attic/jibber_jabber)

   Este paquete se utiliza para detectar el idioma actual del sistema operativo.


## Clonación de repositorios
{: #clone-repo}

Este [repositorio ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) se debe clonar en la [estructura de directorios ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://golang.org/doc/code.html) de Go debido a la forma en la que `govendor` funciona, que también sigue las prácticas recomendadas de Go.

* Importe dependencias internas mediante un nombre de paquete totalmente calificado.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Clone el repositorio.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Compilación, pruebas e instalación del plugin
{: #build-plug-in}

Compile el plugin eligiendo uno de los mandatos siguientes.

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

**Nota**: El script de compilación también instala el plugin para {{site.data.keyword.Bluemix_notm}} CLI.

Pruebe el plugin eligiendo uno de los mandatos siguientes.

```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Ejecute pruebas de integración con cobertura y pruebas de unidad.

```
sh bin/testAll.sh
```
{: codeblock}

Ejecute el plugin como un CLI autónomo.

```
./main
```
{: codeblock}

Instale e invoque el plugin como un {{site.data.keyword.Bluemix_notm}} CLI eligiendo alguno de los siguientes mandatos.

```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
