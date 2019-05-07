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

# Contributo al plugin SDK
{: #contribute}

Segui queste linee guida per contribuire al plugin SDK della CLI {{site.data.keyword.cloud}}.

## Impostazione dell'ambiente di sviluppo
{: #dev-env}

* [CLI Cloud Foundry ](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").

   La CLI Cloud Foundry non è obbligatoria, ma aiuta ad accedere a {{site.data.keyword.cloud_notm}} da un terminale.

   Per ulteriori informazioni sulla CLI Cloud Foundry, consulta la [documentazione](/docs/cli?topic=cloud-cli-cf#cf).

* {{site.data.keyword.cloud_notm}}CLI [](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Questo plug-in viene aggiunto alla CLI {{site.data.keyword.cloud_notm}} e fornisce delle risorse utili per accedere a {{site.data.keyword.cloud_notm}} dalla riga di comando.

* Ambiente di sviluppo di [Go ](https://golang.org/doc/code.html){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Go è rigoroso riguardo le ubicazioni del pacchetto, per cui la tua origine deve essere definita all'interno della struttura di directory `$GOPATH`. Devi definire le tue variabili `$GOPATH` e `$GOROOT` e includere `$GOPATH/bin` nella tua variabile di ambiente `$PATH`. Puoi modificare il file di configurazione `~/.bash_profile` (su Mac) per apportare queste modifiche.

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestore dipendenza: [`govendor `](https://github.com/kardianos/govendor){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

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

* Framework di test BDD: [Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

Il framework di test si basa su Ginkgo, un framework di test BDD per Go e viene utilizzato con [`gomega`](http://onsi.github.io/gomega/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno"), che è una libreria di confronto e asserzione per Ginkgo.

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

   * Per ottenere un modulo HTML facile da utilizzare della copertura del codice, utilizza il seguente comando.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Vieni indirizzato alla directory in cui si trova il file `.coverprofile`.

* Globalizzazione: [go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") e [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

La globalizzazione si basa su `go-i18n`, che è un pacchetto e uno strumento della riga di comando che fornisce il supporto per tradurre un'applicazione Go in più linguaggi. I bundle di traduzione sono pre-elaborati dal comando `go-bindata` che converte tutti i file di input in codice sorgente Go gestibile.

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

* Debug: [delve ](https://github.com/go-delve/delve){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

Delve è un programma di debug per il linguaggio di programmazione Go e viene utilizzato da [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").

   * Installa `delve` utilizzando il seguente comando.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Per Mac OS, segui le [istruzioni ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") per creare il certificato autofirmato obbligatorio.


## Librerie di runtime obbligatorie
{: #runtime-libs}

Le librerie di runtime obbligatorie sono gestite nella directory `vendor` e ne viene eseguito il commit al repository Git per garantire la stabilità, poiché Go non fornisce un gestore delle dipendenze affidabile.

### Dipendenze di runtime
{: #runtime-dependencies}

Le dipendenze nidificate non sono elencate.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   SDK plugin CLI {{site.data.keyword.cloud_notm}}, che fornisce l'infrastruttura per sviluppare i plugin CLI {{site.data.keyword.cloud_notm}}.

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Questo pacchetto fornisce l'infrastruttura per creare applicazioni della riga di comando in Go. Il plug-in CLI {{site.data.keyword.cloud_notm}} si basa su una precedente versione di questa libreria (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Questo pacchetto fornisce vari validatori e strumenti di pulizia per le stringhe, strutture e raccolte. Utilizza questo pacchetto invece di implementare i tuoi validatori.

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Questo pacchetto implementa un client HTTP semplificato per aiutare a gestire le richieste e le risposte HTTP.

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Questo pacchetto implementa una casella di selezione della CLI per fornire un feedback utente mentre vengono elaborate le operazioni di lunga durata, come la generazione SDK.

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

   Questo pacchetto viene utilizzato per rilevare il linguaggio corrente del sistema operativo.

## Clonazione del repository
{: #clone-repo}

Questo repository deve essere clonato nella [struttura di directory di Go ](https://golang.org/doc/code.html){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") a causa della modalità di funzionamento di `govendor`, che segue anch'essa le prassi ottimali di Go.

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

Lo script di build installa anche il plug-in nella CLI {{site.data.keyword.Bluemix_notm}}.
{: note}

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

Installa e richiama il plug-in come una CLI {{site.data.keyword.cloud_notm}} scegliendo uno dei seguenti comandi.
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
