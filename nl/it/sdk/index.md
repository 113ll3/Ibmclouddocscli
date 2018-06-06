---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-23"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK Generator
{: #sdk-cli}

Il plugin {{site.data.keyword.IBM}} SDK Generator può essere installato nella [CLI {{site.data.keyword.Bluemix_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/cli/reference/bluemix_cli/all_versions.html).

Come sviluppatore in {{site.data.keyword.Bluemix_notm}}, puoi utilizzare questo plugin per generare gli SDK dalla tua definizione API REST conforme con la [Open API Specification ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.openapis.org/). Quando modifichi la tua definizione API REST, puoi utilizzare questo plugin per rigenerare solo il SDK anziché rigenerare l'intero progetto.

Puoi anche vedere se le tue applicazioni Cloud Foundry in uno spazio specifico hanno definizioni API REST che sono valide per la generazione SDK. Infine, puoi utilizzare il plugin {{site.data.keyword.IBM_notm}} SDK Generator per convalidare qualsiasi definizione API REST per assicurarti che siano conformi ai requisiti del generatore SDK.

Questo plugin {{site.data.keyword.IBM_notm}} SDK Generator ti consente di integrare facilmente i tuoi servizi di backend nella tua applicazione con un SDK generato. Quando si verifica una modifica a un'API REST, puoi rigenerare il SDK e sostituire la versione precedente per un upgrade del SDK. Puoi anche integrare la CLI in una pipeline DevOps e garantire che il SDK sia sempre conforme alla specifica API ogni volta che l'applicazione viene creata.

La definizione API REST deve essere valida e ospitata su un endpoint del server live o su un file locale nel tuo sistema. Se la definizione API REST è ospitata, l'URL relativo deve essere definito nella variabile di ambiente `OPENAPI_SPEC`.


## Requisiti
{: #prereqs}

Assicurati di soddisfare i seguenti requisiti.

* Avere un account [{{site.data.keyword.Bluemix_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://bluemix.net)
* Una definizione API valida conforme alla specifica [Open API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.openapis.org/)


## Installazione
{: #installation}

1. [Installa la CLI {{site.data.keyword.Bluemix}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://clis.ng.bluemix.net/ui/home.html).

2. [Installa il plugin ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/cli/reference/bluemix_cli/all_versions.html#install_plug-in).

	```
	ibmcloud plugin install sdk-gen
	```
	{: codeblock}


## Comandi
{: #commands}

Utilizza i seguenti comandi per generare un SDK, convalidare i file di definizione Open API o per elencare le applicazioni Cloud Foundry.


### Generazione di un SDK
{: #gen}

Utilizza `ibmcloud sdk generate [arguments...] [command options]`.


#### Argomenti
{: #gen-args}

* `APP_NAME` - il nome dell'applicazione Cloud Foundry nel tuo spazio corrente
* `OPENAPI_DOC_LOCATION` - un URL o percorso file relativo al JSON o Yaml della definizione API REST non elaborata
* `GENERATED_SDK_NAME` (facoltativo) - il nome del SDK generato


#### Opzioni
{: #gen-options}

* `PLATFORM` (obbligatorio)
   * `--android` - genera un SDK Android
   * `--ios` - genera un SDK Swift iOS
   * `--swift` - genera un SDK server Swift
   * `--js` - genera un SDK JavaScript
* `LOCATION` (obbligatorio) - specifica il tipo per `OPENAPI_DOC_LOCATION`
   * `-r` - URL remoto
   * `-f` - file
   * `-a` - applicazione eseguita su {{site.data.keyword.Bluemix_notm}}
   * `-l` - URL host locale
* `--output "YOUR_RELATIVE_PATH"` (facoltativo) - inserisce l'SDK generato nella directory specificata da `YOUR_RELATIVE_PATH` (sovrascrive l'SDK esistente, se presente)
* `--unzip` (facoltativo) - estrae l'SDK generato (sovrascrive le risorse SDK esistenti, se presenti)


#### Utilizzo
{: #gen-usage}

Per generare un SDK da un'applicazione Cloud Foundry in esecuzione in {{site.data.keyword.Bluemix_notm}}, puoi utilizzare il nome dell'applicazione come parametro nella CLI. Il seguente comando utilizza il nome dell'applicazione come `SDK_Name`.

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

Per generare un SDK da un URL di un file di definizione Open API o un file JSON o Yaml locale, utilizza il seguente comando.

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Convalida delle definizioni Open API
{: #validating}

Utilizza `ibmcloud sdk validate [argument]`.


#### Argomenti
{: #val-args}

* `APP_NAME` - il nome dell'applicazione Cloud Foundry nel tuo spazio corrente
* `OPENAPI_DOC_LOCATION` - un URL o percorso file relativo al JSON o Yaml della definizione API REST non elaborata


#### Utilizzo
{: #val-usage}

Per convalidare la specifica API di un'applicazione Cloud Foundry in esecuzione in {{site.data.keyword.Bluemix_notm}}, puoi utilizzare il nome dell'applicazione come parametro nella CLI.

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

Per convalidare un SDK dall'URL di un documento di specifiche API o un file JSON o Yaml locale, utilizza il seguente comando.

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### Elenca applicazioni (Cloud Foundry)
{: #list-apps}

Utilizza `ibmcloud sdk list [argument] [option]` per elencare le applicazioni e convalidare le specifiche API. Devi impostare la variabile di ambiente `OPENAPI_SPEC` sul percorso URL relativo che ospita la tua specifica.


#### Argomenti
{: #list-args}

* `SPACE_NAME` (facoltativo) - il nome dello spazio Cloud Foundry all'interno della tua organizzazione in cui ricercare le applicazioni. Se non viene fornito, la ricerca avviene nello spazio corrente.


#### Opzioni
{: #list-options}

* `--url` (facoltativo) - visualizza un URL completamente formato della definizione Open API per ogni applicazione nell'elenco


#### Utilizzo
{: #list-usage}

Per elencare le applicazioni nello spazio corrente, utilizza il seguente comando.

```
ibmcloud sdk list
```
{: codeblock}

Per elencare le applicazioni nello spazio corrente e visualizzare l'URL della specifica API, utilizza il seguente comando.

```
ibmcloud sdk list --url
```
{: codeblock}

Per elencare le applicazioni in uno specifico spazio, utilizza il seguente comando.

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

Per elencare le applicazioni in uno specifico spazio e visualizzare l'URL della specifica API, utilizza il seguente comando.

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
