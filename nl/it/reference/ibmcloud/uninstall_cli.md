---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Disinstalla la CLI {{site.data.keyword.Bluemix_notm}} 

Consulta le seguenti sezioni per le istruzioni su come disinstallare {{site.data.keyword.Bluemix_notm}} su piattaforme specifiche.

## Disinstalla su Windows

* Fai clic sul pulsante `Avvia` e seleziona `Pannello di controllo`
* Nella finestra a comparsa, fai clic su `Disinstalla un programma`
* Nell'elenco delle applicazioni a comparsa, individua `IBM Cloud Command Line Interface`
* Fai clic con il tasto destro su `IBM Cloud Command Line Interface` e seleziona `Disinstalla`
* Viene avviato il programma di disinstallazione. Segui le istruzioni per completare la disinstallazione.

## Disinstalla su Linux/macOS

### Prima della versione `0.9.0`

* Apri un terminale ed esegui i seguenti comandi
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* Ripulisci gli script di completamento automatico, se sono stati configurati. Per ulteriori dettagli, fai riferimento a [Abilita completamento automatico della CLI](enable_cli_autocompletion.html).

### Versione `0.9.0` e successive

* Apri un terminale ed esegui il seguente comando
  * `/usr/local/ibmcloud/uninstall`
* Ripulisci gli script di completamento automatico, se sono stati configurati. Per ulteriori dettagli, fai riferimento a [Abilita completamento automatico della CLI](enable_cli_autocompletion.html).
