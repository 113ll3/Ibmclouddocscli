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

# Contribución al plugin de SDK
{: #contribute}

Siga estas directrices para contribuir al plugin de SDK de CLI de {{site.data.keyword.cloud}}.

## Configuración del entorno de desarrollo
{: #dev-env}

* [CLI](https://github.com/cloudfoundry/cli/releases){: new_window} de Cloud Foundry
![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

   La CLI de Cloud Foundry no es necesaria, pero permite acceder a {{site.data.keyword.cloud_notm}} desde un terminal.

   Para obtener más información sobre la CLI de Cloud Foundry, consulte la [documentación](/docs/cli?topic=cloud-cli-cf#cf).

* [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) de {{site.data.keyword.cloud_notm}}.

   El plugin se añade a la CLI de {{site.data.keyword.cloud_notm}} y proporciona recursos útiles para acceder a {{site.data.keyword.cloud_notm}} desde la línea de mandatos.

* [Entorno de desarrollo](https://golang.org/doc/code.html){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") de Go

   Go es un lenguaje estricto con ubicaciones de paquetes, por ello, el código fuente se debe definir dentro de la estructura de directorios `$GOPATH`. Debe definir las variables `$GOPATH` y `$GOROOT` e incluir `$GOPATH/bin` en la variable de entorno `$PATH`. Edite el archivo de configuración `~/.bash_profile` para realizar estos cambios.

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestor de dependencias: [`govendor`](https://github.com/kardianos/govendor){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   La herramienta `govendor` crea y gestiona las dependencias de Go. No es necesaria a no ser que piense actualizar el directorio de proveedor.

   * Instálela con el siguiente mandato.

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

* Infraestructura de prueba BDD: [Ginkgo](http://onsi.github.io/ginkgo/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

La infraestructura de prueba se basa en Ginkgo, una infraestructura de pruebas BDD para Go, y se utiliza con [`gomega`](http://onsi.github.io/gomega/){: new_window}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo"), que es una biblioteca de buscador y de aserciones para Ginkgo.

   * Instale `gingko` utilizando el mandato siguiente.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Instale `gomega` utilizando el mandato siguiente.

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

   * Utilice el siguiente mandato para obtener un formato HTML preparado para la cobertura de código.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Irá al directorio en el que se encuentra el archivo `.coverprofile`.

* Globalización: [go-i18n](https://github.com/nicksnyder/go-i18n){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") y [go-bindata](https://github.com/jteeuwen/go-bindata){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

La globalización se basa en `go-i18n`, un paquete y una herramienta de línea de mandatos que proporciona soporte para traducir una aplicación Go en distintos lenguajes. Los paquetes de traducción están procesados de forma previa mediante el mandato `go-bindata`, que convierte cualquier archivo de entrada en un código fuente Go gestionable.

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

* Depuración: [delve](https://github.com/go-delve/delve){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

Delve es un depurador para el lenguaje de programación Go que [Visual Studio Code](https://code.visualstudio.com/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") utiliza.

   * Instale `delve` utilizando el siguiente mandato.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Para Mac OS, sigas las [instrucciones](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") para crear el certificado autofirmado necesario.


## Bibliotecas de tiempo de ejecución necesarias
{: #runtime-libs}

Las bibliotecas de tiempo de ejecución necesarias están gestionadas bajo el directorio `vendor` y están confirmadas en el repositorio Git para asegurar estabilidad, puesto que Go no proporciona un gestor robusto de dependencias.

### Dependencias de tiempo de ejecución
{: #runtime-dependencies}

Las dependencias anidadas no están listadas.

* [github.ibm.com/Bluemix/bluemix-cli-sdk](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   El plugin de SDK de CLI de {{site.data.keyword.cloud_notm}}, que proporciona la infraestructura para desarrollar plugins de CLI de {{site.data.keyword.cloud_notm}}.

* [github.com/urfave/cli](https://github.com/urfave/cli){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   Este paquete proporciona una infraestructura para compilar apps de línea de mandatos en Go. El plugin de CLI de {{site.data.keyword.cloud_notm}} se basa en una versión antigua de esta biblioteca (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator](https://github.com/asaskevich/govalidator){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   Este paquete proporciona una serie de validadores y sanitizantes para series, estructuras y colecciones. Utilice este paquete en lugar de aplicar sus propios validadores.

* [github.com/parnurzeal/gorequest](https://github.com/parnurzeal/gorequest){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   Este paquete implementa un cliente HTTP simplificado para ayudar a manejar las solicitudes y respuestas HTTP.

* [github.com/briandowns/spinner](https://github.com/briandowns/spinner){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   Este paquete implementa un control spinner de CLI para proporcionar comentarios de usuario mientras se están procesando operaciones extensas, como las de generación de SDK.

* [github.com/cloudfoundry-attic/jibber_jabber](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

   Este paquete se utiliza para detectar el idioma actual del sistema operativo.

## Clonación de repositorios
{: #clone-repo}

El repositorio se debe clonar en [la estructura de directorios](https://golang.org/doc/code.html){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") de Go debido al modo en que funciona `govendor`, que también sigue las prácticas recomendadas de Go.

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


## Creación, prueba e instalación del plugin
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

El script de compilación también instala el plugin en la CLI de {{site.data.keyword.Bluemix_notm}}.
{: note}

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

Ejecute el plugin como una CLI autónoma.
```
./main
```
{: codeblock}

Instale e invoque el plugin como una CLI de {{site.data.keyword.cloud_notm}} eligiendo alguno de los siguientes mandatos.
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
