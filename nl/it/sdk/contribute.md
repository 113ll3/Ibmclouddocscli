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

# Contributo al plugin SDK
{: #contribute}

Segui queste linee guida per contribuire al plugin SDK della CLI {{site.data.keyword.Bluemix}}.

## Impostazione dell'ambiente di sviluppo
{: #dev-env}

* CLI [Cloud Foundry ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/cloudfoundry/cli/releases)

   La CLI Cloud Foundry non è obbligatoria, ma aiuta ad accedere a {{site.data.keyword.Bluemix_notm}} dal terminale.

   Per ulteriori informazioni sulla CLI Cloud Foundry, consulta la [documentazione ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/cli/reference/cfcommands/index.html){: new_window}.

* {{site.data.keyword.Bluemix_notm}} [CLI ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://clis.{DomainName}/ui/home.html)

   Questo plugin installa la CLI {{site.data.keyword.Bluemix_notm}}. La CLI {{site.data.keyword.Bluemix_notm}} fornisce anche risorse utili per accedere a {{site.data.keyword.Bluemix_notm}} dal terminale.

   Per ulteriori informazioni sulla CLI {{site.data.keyword.Bluemix_notm}}, consulta la [documentazione ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/cli/reference/bluemix_cli/index.html){: new_window}.

* Ambiente di sviluppo di [Go ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://golang.org/doc/code.html)

   Go è rigoroso riguardo le ubicazioni del pacchetto, per cui la tua origine deve essere definita all'interno della struttura di directory `$GOPATH`. Assicurati di definire le tue variabili `$GOPATH` e `$GOROOT` per includere `$GOPATH/bin` nella tua variabile di ambiente `$PATH`, il che può essere effettuato modificando il tuo file di configurazione `~/.bash_profile` (su Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestore dipendenza: [govendor ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/kardianos/govendor)

   Lo strumento `govendor` crea e gestisce le dipendenze Go. Non ti serve a meno che non intendi aggiornare la directory del fornitore.

   * Installo utilizzando il seguente comando.

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Inizializza `govendor` nella tua directory del progetto utilizzando il seguente comando.

      ```
      govendor init
      ```
      {: codeblock}

   * Aggiungi le dipendenze da `$GOPATH` alla directory del fornitore utilizzando il seguente comando.

      ```
      govendor add +local
      ```
      {: codeblock}

* Framework di test BDD: [Ginkgo ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://onsi.github.io/ginkgo/)

Il framework di test si basa su Ginkgo, un framework di test BDD per Go. Viene utilizzato con [Gomega ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://onsi.github.io/gomega/), che è una libreria di confronto e asserzione per Ginkgo.

   * Installa `ginkgo` utilizzando il seguente comando.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Installa `gomega` utilizzando il seguente comando.

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Esegui i test di unità utilizzando il seguente comando.

      ```
      ginkgo -r
      ```
      {: codeblock}

      * Per aggiungere la copertura del codice, accoda `-cover` al comando.

   * Ottieni un modulo HTML facile da utilizzare della copertura del codice, utilizzando il seguente comando.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Passerai alla directory in cui è ubicato il file `.coverprofile`.

* Internazionalizzazione: [go-i18n ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/nicksnyder/go-i18n) e [go-bindata ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/jteeuwen/go-bindata)

L'internazionalizzazione si basa su go-i18n, che è un pacchetto e uno strumento della riga di comando che fornisce il supporto per tradurre un'applicazione Go in più linguaggi. I bundle di traduzione sono rielaborati da go-bindata, che è un comando che converte tutti i file di input in codice sorgente Go gestibile.

   * Installa `go-i18n` utilizzando il seguente comando.

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Installa `go-bindata` utilizzando il seguente comando.

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Debug: [delve ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/derekparker/delve)

Delve è un programma di debug per il linguaggio di programmazione Go e viene utilizzato da [Visual Studio Code ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://code.visualstudio.com/).

   * Installa `delve` utilizzando il seguente comando.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Per Mac OS, segui le [istruzioni ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) per creare il certificato autofirmato obbligatorio.


## Librerie di runtime obbligatorie
{: #runtime-libs}

Le librerie di runtime obbligatorie sono gestite nella directory `vendor` e ne viene eseguito il commit al repository Git per garantire la stabilità, poiché Go non fornisce un gestore delle dipendenze affidabile.

### Dipendenze di runtime
{: #runtime-dependencies}

Le dipendenze nidificate non sono elencate.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   SDK plugin CLI {{site.data.keyword.Bluemix_notm}}, che fornisce l'infrastruttura per sviluppare i plugin CLI {{site.data.keyword.Bluemix_notm}}.

* [github.com/urfave/cli ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/urfave/cli)

   Questo pacchetto fornisce l'infrastruttura per creare applicazioni della riga di comando in Go. Il plugin CLI {{site.data.keyword.Bluemix_notm}} si basa su una precedente versione di questa libreria (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/asaskevich/govalidator)

   Questo pacchetto fornisce vari validatori e strumenti di pulizia per le stringhe, strutture e raccolte. Utilizza questo pacchetto invece di implementare i nostri validatori.

* [github.com/parnurzeal/gorequest ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/parnurzeal/gorequest)

   Questo pacchetto implementa un client HTTP semplificato per aiutare a gestire le richieste e le risposte HTTP.

* [github.com/briandowns/spinner ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/briandowns/spinner)

   Questo pacchetto implementa una casella di selezione della CLI per fornire un feedback utente mentre vengono elaborate le operazioni di lunga durata, come la generazione SDK.

* [github.com/cloudfoundry-attic/jibber_jabber ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/cloudfoundry-attic/jibber_jabber)

   Questo pacchetto viene utilizzato per rilevare il linguaggio corrente del sistema operativo.


## Clonazione del repository
{: #clone-repo}

Questo [repository ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) deve essere clonato nella [struttura della directory di Go ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://golang.org/doc/code.html) in modo che `govendor` funzioni, che segue inoltre le procedure consigliate di Go.

* Importa le dipendenze interne tramite un nome pacchetto completo.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Clona il repository.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Creazione, verifica e installazione del plug-in
{: #build-plug-in}

Crea il plug-in scegliendo uno dei seguenti comandi.

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

**Nota**: lo script di build installa anche il plugin nella CLI {{site.data.keyword.Bluemix_notm}}.

Verifica il plug-in scegliendo uno dei seguenti comandi.

```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Esegui i test di integrazione con i test di unità e la copertura.

```
sh bin/testAll.sh
```
{: codeblock}

Esegui il plug-in come una CLI autonoma.

```
./main
```
{: codeblock}

Installa e richiama il plug-in come una CLI {{site.data.keyword.Bluemix_notm}} scegliendo uno dei seguenti comandi.

```
bluemix plugin install main
bluemix help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
