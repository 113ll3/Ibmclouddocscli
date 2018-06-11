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

# SDK-Plug-in entwickeln
{: #contribute}

Befolgen Sie diese Richtlinien, um das SDK-Plug-in für die {{site.data.keyword.Bluemix}}-CLI zu entwickeln.

## Entwicklungsumgebung einrichten
{: #dev-env}

* Cloud Foundry-[CLI ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/cloudfoundry/cli/releases)

   Die Cloud Foundry-CLI ist nicht erforderlich, aber sie vereinfacht den Zugriff auf {{site.data.keyword.Bluemix_notm}} über das Terminal.

   Weitere Informationen zur Cloud Foundry-CLI finden Sie in der [Dokumentation ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](/docs/cli/reference/cfcommands/index.html){: new_window}.

* {{site.data.keyword.Bluemix_notm}}-[CLI ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://clis.{DomainName}/ui/home.html)

   Dieses Plug-in wird in der {{site.data.keyword.Bluemix_notm}}-CLI installiert. Die {{site.data.keyword.Bluemix_notm}}-CLI stellt außerdem nützliche Ressourcen für den Zugriff auf {{site.data.keyword.Bluemix_notm}} über das Terminal bereit.

   Weitere Informationen zur {{site.data.keyword.Bluemix_notm}}-CLI finden Sie in der [Dokumentation ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](/docs/cli/reference/bluemix_cli/index.html){: new_window}.

* Go-[Entwicklungsumgebung ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://golang.org/doc/code.html)

   Go hat strenge Vorgaben für Paketpositionen, deshalb muss Ihre Quelle in der `$GOPATH`-Verzeichnisstruktur definiert sein. Stellen Sie sicher, dass Sie die Variablen `$GOPATH` und `$GOROOT` definieren und `$GOPATH/bin` in Ihre `$PATH`-Umgebungsvariable einschließen. Bearbeiten Sie dafür Ihre Konfigurationsdatei `~/.bash_profile` (unter Mac OS) entsprechend.

   ```
   ### SET GOPATH und GOROOT von Go
   export GOPATH=$HOME/Development/go
   export GOROOT=/usr/local/opt/go/libexec
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Abhängigkeitsmanager: [govendor ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/kardianos/govendor)

   Das Tool `govendor` erstellt und verwaltet die Go-Abhängigkeiten. Sie brauchen es nur, wenn Sie das Anbieterverzeichnis aktualisieren möchten.

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

* BDD-Testframework: [Ginkgo ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://onsi.github.io/ginkgo/)

Das Testframework basiert auf Ginkgo, einem BDD-Testframework für Go. Es wird mit [Gomega ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://onsi.github.io/gomega/) verwendet, einer Abgleichs- und Zusicherungsbibliothek für Ginkgo.

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

      * Sie werden zu dem Verzeichnis geleitet, in dem sich die Datei `.coverprofile` befindet.

* Internationalisierung: [go-i18n ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/nicksnyder/go-i18n) und [go-bindata ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/jteeuwen/go-bindata)

Internationalisierung basiert auf go-i18n, einem Paket- und Befehlszeilentool, das Unterstützung für die Übersetzung einer Go-Anwendung in mehrere Sprachen bereitstellt. Übersetzungspakete werden von 'go-bindata' vorverarbeitet. Dies ist ein Befehl, der alle Eingabedateien in verwaltbaren Go-Quellcode konvertiert.

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

* Debugging: [delve ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/derekparker/delve)

Delve ist ein Debugger für die Go-Programmiersprache und wird von [Visual Studio Code ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://code.visualstudio.com/) verwendet.

   * Installieren Sie `delve` mithilfe des folgenden Befehls.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Befolgen Sie unter Mac OS die bereitgestellten [Anweisungen ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://blog.ralch.com/tutorial/golang-debug-with-delve/), um das erforderliche selbst signierte Zertifikat zu erstellen.


## Erforderliche Laufzeitbibliotheken
{: #runtime-libs}

Die erforderlichen Laufzeitbibliotheken werden im Verzeichnis `vendor` verwaltet und im Git-Repository festgeschrieben, um Stabilität sicherzustellen, da Go keinen leistungsfähigen Abhängigkeitsmanager umfasst.

### Laufzeitabhängigkeiten
{: #runtime-dependencies}

Verschachtelte Abhängigkeiten sind nicht aufgeführt.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   Das SDK für {{site.data.keyword.Bluemix_notm}}-CLI-Plug-ins. das die Infrastruktur für die Entwicklung von {{site.data.keyword.Bluemix_notm}}-CLI-Plug-ins bereitstellt.

* [github.com/urfave/cli ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/urfave/cli)

   Dieses Paket stellt die Infrastruktur zum Erstellen von Befehlszeilen-Apps in Go bereit. Das {{site.data.keyword.Bluemix_notm}}-CLI-Plug-in basiert auf einer älteren Version dieser Bibliothek (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/asaskevich/govalidator)

   Dieses Paket stellt eine Reihe von Überprüfungs- und Bereinigungskomponenten für Zeichenfolgen, Strukturen und Sammlungen bereit. Verwenden Sie dieses Paket, statt Ihre eigenen Überprüfungskomponenten zu implementieren.

* [github.com/parnurzeal/gorequest ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/parnurzeal/gorequest)

   Dieses Paket implementiert einen vereinfachten HTTP-Client zur Unterstützung der Verarbeitung von HTTP-Anforderungen und -Antworten.

* [github.com/briandowns/spinner ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/briandowns/spinner)

   Dieses Paket implementiert ein CLI-Drehfeld, um während langer Operationen wie der SDK-Generierung Benutzern Feedback zu geben.

* [github.com/cloudfoundry-attic/jibber_jabber ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/cloudfoundry-attic/jibber_jabber)

   Dieses Paket dient der Erkennung der aktuellen Sprache des Betriebssystems.


## Repository klonen
{: #clone-repo}

Dieses [Repository ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) muss in der Go-[Verzeichnisstruktur ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://golang.org/doc/code.html) aufgrund der Funktionsweise von `govendor` geklont werden. Dies zählt auch zu den Best Practices von Go.

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

**Hinweis**: Das Build-Script installiert das Plug-in auch in der {{site.data.keyword.Bluemix_notm}}-CLI.

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

Installieren und rufen Sie Sie das Plug-in als {{site.data.keyword.Bluemix_notm}}-CLI auf, indem Sie einen der folgenden Befehle ausführen.

```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
