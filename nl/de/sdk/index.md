---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK Generator
{: #sdk-cli}

Das {{site.data.keyword.IBM}} SDK Generator-Plug-in kann in der [{{site.data.keyword.Bluemix_notm}}-CLI ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](/docs/cli/reference/bluemix_cli/all_versions.html) installiert werden. 

Als Entwickler können Sie dieses Plug-in in {{site.data.keyword.Bluemix_notm}} verwenden, um SDKs aus Ihrer mit der [Open API-Spezifikation ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.openapis.org/) kompatiblen REST-API-Definition zu generieren. Wenn Sie Änderungen an Ihrer REST-API-Definition vornehmen, können Sie dieses Plug-in verwenden, um nur das SDK und nicht das gesamte Projekt neu zu erstellen. 

Sie können auch prüfen, ob Ihre Cloud Foundry-Apps in einem bestimmten Bereich REST-API-Definitionen aufweisen, die für die SDK-Generierung gültig sind. Schließlich können Sie das {{site.data.keyword.IBM_notm}} SDK Generator-Plug-in verwenden, um alle REST-API-Definitionen zu prüfen und sicherzustellen, dass sie den SDK Generator-Definitionen entsprechen. 

Dieses {{site.data.keyword.IBM_notm}} SDK Generator-Plug-in ermöglicht Ihnen, Ihre Back-End-Services mit einem generierten SDK einfach in Ihre App zu integrieren. Wenn eine Änderung an einer REST-API auftritt, können Sie das SDK neu generieren und das alte nahtlos durch ein SDK-Upgrade ersetzen. Sie können auch die CLI in eine 'devops'-Pipeline integrieren und sicherstellen, dass das SDK immer mit den API-Spezifikationen übereinstimmt, wenn die App erstellt wird. 

Die REST-API-Definition muss gültig sein und entweder an einem Live-Serverendpunkt oder in einer lokalen Datei auf Ihrem System gehostet sein. Wenn die REST-API-Definition gehostet wird, muss die relative URL in der Umgebungsvariablen `OPENAPI_SPEC` definiert sein. 


## Anforderungen
{: #prereqs}

Stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen. 

* Sie verfügen über ein [{{site.data.keyword.Bluemix_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://bluemix.net). 
* Eine gültige API-Definition, die der [Open API-![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.openapis.org/)-Spezifikation entspricht. 


## Installation
{: #installation}

1. [Installieren Sie die {{site.data.keyword.Bluemix}}-CLI ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://clis.ng.bluemix.net/ui/home.html). 

2. [Installieren Sie das Plug-in ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](/docs/cli/reference/bluemix_cli/all_versions.html#install_plug-in). 

	```
	bx plugin install sdk-gen
	```
	{: codeblock}


## Befehle
{: #commands}

Verwenden Sie die folgenden Befehle, um ein SDK zu generieren, Open API-Definitionsdateien zu prüfen oder Cloud Foundry-Apps aufzulisten. 


### SDK generieren
{: #gen}

Verwenden Sie `bx sdk generate [arguments...] [command options]`. 


#### Argumente
{: #gen-args}

* `APP_NAME` - der Name der Cloud Foundry-App in Ihrem aktuellen Bereich
* `OPENAPI_DOC_LOCATION` - eine URL oder ein relativer Dateipfad zur unformatierten JSON- oder Yaml-Datei mit der REST-API-Definition
* `GENERATED_SDK_NAME` (optional) - der Name des generierten SDK


#### Optionen
{: #gen-options}

* `PLATFORM` (erforderlich)
   * `--android` - generiert ein Android-SDK
   * `--ios` - generiert ein iOS Swift-SDK
   * `--swift` - generiert ein Swift-Server-SDK
   * `--js` - generiert ein JavaScript-SDK
* `LOCATION` (erforderlich) - gibt den Typ für `OPENAPI_DOC_LOCATION` an
   * `-r` - ferne URL
   * `-f` - Datei
   * `-a` - App, die unter {{site.data.keyword.Bluemix_notm}} ausgeführt wird
   * `-l` - URL des lokalen Host
* `--output "YOUR_RELATIVE_PATH"` (optional) - platziert das generierte SDK in dem Verzeichnis, das durch `YOUR_RELATIVE_PATH` angegeben ist (überschreibt das gegebenenfalls vorhandene SDK) 
* `--unzip` (optional) - extrahiert das generierte SDK (überschreibt gegebenenfalls vorhandene SDK-Artefakte) 


#### Verwendung
{: #gen-usage}

Um ein SDK aus einer Cloud Foundry-App zu extrahieren, das in {{site.data.keyword.Bluemix_notm}} ausgeführt wird, können Sie den Namen der App als Parameter für die CLI verwenden. Der folgende Befehl verwendet den Namen der App als `SDK_Name`. 

```
bx sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

Führen Sie den folgenden Befehl aus, um ein SDK aus einer URL in einer Open API-Definitionsdatei oder einer lokalen JSON- bzw. Yaml-Datei zu generieren. 

```
bx sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Open API-Definitionen prüfen
{: #validating}

Verwenden Sie `bx sdk validate [argument]`. 


#### Argumente
{: #val-args}

* `APP_NAME` - der Name der Cloud Foundry-App in Ihrem aktuellen Bereich
* `OPENAPI_DOC_LOCATION` - eine URL oder ein relativer Dateipfad zur unformatierten JSON- oder Yaml-Datei mit der REST-API-Definition


#### Verwendung
{: #val-usage}

Um eine API-Spezifikation einer Cloud Foundry-App zu prüfen, die in {{site.data.keyword.Bluemix_notm}} ausgeführt wird, können Sie den Namen der App als Parameter für die CLI verwenden. 

```
bx sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

Führen Sie den folgenden Befehl aus, um ein SDK aus der URL für ein API-Spezifikationsdokument oder eine lokale JSON- oder Yaml-Datei zu prüfen. 

```
bx sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### Apps auflisten (Cloud Foundry)
{: #list-apps}

Verwenden Sie `bx sdk list [argument] [option]` zum Auflisten von Apps und Prüfen von API-Spezifikationen. Sie müssen die Umgebungsvariable `OPENAPI_SPEC` auf einen relativen URL-Pfad festlegen, in dem Ihre Spezifikationen gehostet sind. 


#### Argumente
{: #list-args}

* `SPACE_NAME` (optional) - der Name des Cloud Foundry-Bereichs in Ihrer aktuellen Organisation, in dem Sie nach Apps suchen möchten. Wenn keine Angabe erfolgt, wird im aktuellen Bereich gesucht. 


#### Optionen
{: #list-options}

* `--url` (optional) - zur Anzeige einer vollständigen URL der Open API-Definition für jede App in der Liste. 


#### Verwendung
{: #list-usage}

Verwenden Sie den folgenden Befehl, um alle Apps im aktuellen Bereich aufzulisten. 

```
bx sdk list
```
{: codeblock}

Verwenden Sie den folgenden Befehl, um Apps im aktuellen Bereich aufzulisten und die URL der API-Spezifikation anzuzeigen. 

```
bx sdk list --url
```
{: codeblock}

Verwenden Sie den folgenden Befehl, um Apps in einem bestimmten Bereich aufzulisten. 

```
bx sdk list [SPACE_NAME]
```
{: codeblock}

Verwenden Sie den folgenden Befehl, um Apps in einem bestimmten Bereich aufzulisten und die URL der API-Spezifikation anzuzeigen. 

```
bx sdk list [SPACE_NAME] --url
```
{: codeblock}
