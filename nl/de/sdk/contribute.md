---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-26"

keywords: contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# SDK-Plug-in entwickeln
{: #contribute}

Befolgen Sie diese Richtlinien, um das SDK-Plug-in für die {{site.data.keyword.cloud}}-CLI zu entwickeln.

## Entwicklungsumgebung einrichten
{: #dev-env}

* Cloud Foundry-[CLI ](https://github.com/cloudfoundry/cli/releases){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Die Cloud Foundry-CLI ist nicht erforderlich, aber sie ist hilfreich für den Zugriff auf {{site.data.keyword.cloud_notm}} über das Terminal.

   Weitere Informationen zur Cloud Foundry-CLI finden Sie in der [Dokumentation](/docs/cli?topic=cloud-cli-cf#cf).

* {{site.data.keyword.cloud_notm}}-[CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Dieses Plug-in wird in der {{site.data.keyword.cloud_notm}}-CLI installiert. Die {{site.data.keyword.cloud_notm}}-CLI stellt außerdem nützliche Ressourcen für den Zugriff auf {{site.data.keyword.cloud_notm}} über das Terminal bereit.

* Go-[Entwicklungsumgebung ](https://golang.org/doc/code.html){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Go hat strenge Vorgaben für Paketpositionen, deshalb muss Ihre Quelle in der `$GOPATH`-Verzeichnisstruktur definiert sein. Stellen Sie sicher, dass Sie die Variablen `$GOPATH` und `$GOROOT` definieren und `$GOPATH/bin` in Ihre `$PATH`-Umgebungsvariable einschließen. Bearbeiten Sie dafür Ihre Konfigurationsdatei `~/.bash_profile` (unter Mac OS) entsprechend.

   ```
   ### SET GOPATH und GOROOT von Go
   export GOPATH=$HOME/Development/go
   export GOROOT=/usr/local/opt/go/libexec
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Abhängigkeitsmanager: [govendor ](https://github.com/kardianos/govendor){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Das Tool `govendor` erstellt und verwaltet die Go-Abhängigkeiten. Es wird nur benötigt, wenn Sie beabsichtigen, das Anbieterverzeichnis zu aktualisieren.

   * Installieren Sie das Tool mithilfe des folgenden Befehls.

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Initialisieren Sie `govendor` in Ihrem Projektverzeichnis mithilfe des folgenden Befehls.

      ```
      govendor init
      ```
      {: codeblock}

   * Fügen Sie Abhängigkeiten aus `$GOPATH` mithilfe des folgenden Befehls zum Anbieterverzeichnis hinzu.

      ```
      govendor add +local
      ```
      {: codeblock}

* BDD-Testframework: [Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

Das Testframework basiert auf Ginkgo, einem BDD-Testframework für Go. Es wird zusammen mit [Gomega](http://onsi.github.io/gomega/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link"), einer Abgleichs- und Zusicherungsbibliothek für Gingko, verwendet.

   * Installieren Sie `ginkgo` mithilfe des folgenden Befehls.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Installieren Sie `gomega` mithilfe des folgenden Befehls.

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Führen Sie mithilfe des folgenden Befehls Komponententests aus.

      ```
      ginkgo -r
      ```
      {: codeblock}

      * Hängen Sie für mehr Codeabdeckung `-cover` an den Befehl an.

   * Rufen Sie mithilfe des folgenden Befehls ein lesbares HTML-Formular der Codeabdeckung ab.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Wechseln Sie in das Verzeichnis, in dem sich die Datei `.coverprofile` befindet.

* Internationalisierung: [go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") und [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

Die Internationalisierung basiert auf `go-i18n`, einem Paket- und Befehlszeilentool, das Unterstützung für die Übersetzung einer Go-Anwendung in mehrere Sprachen bereitstellt. Übersetzungspakete werden von `go-bindata` vorverarbeitet. Dies ist ein Befehl, der alle Eingabedateien in verwaltbaren Go-Quellcode konvertiert.

   * Installieren Sie `go-i18n` mithilfe des folgenden Befehls.

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Installieren Sie `go-bindata` mithilfe des folgenden Befehls.

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Debugging: [delve ](https://github.com/derekparker/delve){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

Delve ist ein Debugger für die Go-Programmiersprache und wird von [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") verwendet.

   * Installieren Sie `delve` mithilfe des folgenden Befehls.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Befolgen Sie unter Mac OS die bereitgestellten [Anweisungen ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link"), um das erforderliche selbst signierte Zertifikat zu erstellen.


## Erforderliche Laufzeitbibliotheken
{: #runtime-libs}

Die erforderlichen Laufzeitbibliotheken werden im Verzeichnis `vendor` verwaltet und im Git-Repository festgeschrieben, um Stabilität sicherzustellen, da Go keinen leistungsfähigen Abhängigkeitsmanager umfasst.

### Laufzeitabhängigkeiten
{: #runtime-dependencies}

Verschachtelte Abhängigkeiten sind nicht aufgeführt.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Das SDK für {{site.data.keyword.cloud_notm}}-CLI-Plug-ins. das die Infrastruktur für die Entwicklung von {{site.data.keyword.cloud_notm}}-CLI-Plug-ins bereitstellt.

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Dieses Paket stellt die Infrastruktur zum Erstellen von Befehlszeilen-Apps in Go bereit. Das {{site.data.keyword.cloud_notm}}-CLI-Plug-in basiert auf einer älteren Version dieser Bibliothek (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Dieses Paket stellt eine Reihe von Überprüfungs- und Bereinigungskomponenten für Zeichenfolgen, Strukturen und Sammlungen bereit. Verwenden Sie dieses Paket, statt Ihre eigenen Überprüfungskomponenten zu implementieren.

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Dieses Paket implementiert einen vereinfachten HTTP-Client zur Unterstützung der Verarbeitung von HTTP-Anforderungen und -Antworten.

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Dieses Paket implementiert ein CLI-Drehfeld, um während langer Operationen wie der SDK-Generierung Benutzern Feedback zu geben.

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")

   Dieses Paket dient der Erkennung der aktuellen Sprache des Betriebssystems.

## Repository klonen
{: #clone-repo}

Das Repository muss in der Go-[Verzeichnisstruktur](https://golang.org/doc/code.html){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") geklont werden. Dies ist aufgrund der Funktionsweise von `govendor` erforderlich und entspricht den bei Go bewährten Verfahren.

* Importieren Sie interne Abhängigkeiten mittels eines vollständig qualifizierten Paketnamens.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Klonen Sie das Repository.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Plug-in erstellen, testen und installieren
{: #build-plug-in}

Erstellen Sie das Plug-in, indem Sie einen der folgenden Befehle auswählen.
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

Das Build-Script installiert das Plug-in auch in der {{site.data.keyword.Bluemix_notm}}-CLI.
{: note}

Testen Sie das Plug-in, indem Sie einen der folgenden Befehle ausführen.
```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Führen Sie Integrationstests in Form von Komponententests und Abdeckung aus.
```
sh bin/testAll.sh
```
{: codeblock}

Führen Sie das Plug-in als eigenständige CLI aus.
```
./main
```
{: codeblock}

Installieren und rufen Sie das Plug-in als {{site.data.keyword.cloud_notm}}-CLI auf, indem Sie einen der folgenden Befehle ausführen.
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
