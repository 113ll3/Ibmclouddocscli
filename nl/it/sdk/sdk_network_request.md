---

copyright:
  years: 2016, 2019
lastupdated: "2019-06-03"

keywords: cli, bmscore, bmscore sdk, network request, ios network cli, android network cli, cordova network cli, mobile network request, mobile cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Effettuazione di una richiesta di rete
{: #sdk-network-request}

Puoi utilizzare l'SDK `BMSCore` per effettuare richieste di rete a qualsiasi risorsa.

## Android
{: #request-android}

1. Assicurati di avere [importato l'SDK client e di averlo inizializzato](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-android) nella tua applicazione Android.

2. Effettua una richiesta di rete.

	```Java
	String customResourceURL = "<your resource URL>";
	Request request = new Request(customResourceURL, "GET");

	ResponseListener listener = new ResponseListener() {
		@Override
		public void onSuccess(Response response) {
			Log.i("MyApp", "Response: " + response.getResponseText());
		}

		@Override
		public void onFailure(Response response, Throwable t, JSONObject extendedInfo) {
			Log.i("MyApp", "Request failed. Response: " + response.getResponseText() + ". Error: " + t.getLocalizedMessage());
		}
	};

	request.send(getApplicationContext(), listener);
	```
	{: codeblock}

La classe `Request` rappresenta un metodo semplice per effettuare una richiesta HTTP e ottenere la risposta al completamento della richiesta. Se stai scaricando o caricando dei file o dei corpi di dati di grandi dimensioni, puoi utilizzare i metodi `Request` `download` o `upload`. Per monitorare l'avanzamento dello scaricamento o del caricamento, crea un `ProgressListener` personalizzato e trasmettilo ai metodi `download` o `upload`.

Per degli esempi di utilizzo completi, vedi il `BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").


## iOS
{: #request-ios}

1. Assicurati di aver [importato e inizializzato l'SDK Client](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-ios) nella tua applicazione iOS.

2. Crea una richiesta di rete.

	### Swift 3.0
	{: #ios-swift3 notoc}

	```Swift
	let customResourceURL = "<your resource URL>"
	let request = Request(url: customResourceURL, method: HttpMethod.GET)

	let callBack:BMSCompletionHandler = {(response: Response?, error: Error?) in
		if error == nil {
			print ("Response: \(response?.responseText), no error")
		} else {
			print ("Error: \(error)")
		}
	}
	request.send(completionHandler: callBack)
	```
	{: codeblock}

	### Swift 2.2
	{: #ios-swift22 notoc}

	```Swift
	let customResourceURL = "<your resource URL>"
	let request = Request(url: customResourceURL, method: HttpMethod.GET)

	let callBack:BMSCompletionHandler = {(response: Response?, error: NSError?) in
		if error == nil {
			print ("Response: \(response?.responseText), no error")
		} else {
			print ("Error: \(error)")
		}
	}
	request.send(completionHandler: callBack)
	```
	{: codeblock}

La classe `Request` rappresenta un metodo semplice per effettuare una richiesta HTTP e ottenere la risposta al completamento della richiesta. Se vuoi più flessibilità e controllo rispetto a quello ottenuto con `Request`, puoi utilizzare la classe `BMSURLSession`. Alcune funzioni della classe `BMSURLSession` comprendono il monitoraggio dell'avanzamento dei caricamenti e la messa in pausa o l'annullamento delle richieste. Per ottenere le risposte, puoi selezionare i gestori o i delegati di completamento.

La classe `BMSURLSession` è disponibile solo per iOS.

Per degli esempi di utilizzo completi, vedi il `BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").

## Cordova
{: #request-cordova}

1. Assicurati di aver [importato e inizializzato l'SDK Client](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-cordova) nella tua applicazione Cordova.

2. Crea una richiesta di rete.

	```Javascript
	var success = function(data) {
		console.log("success", data);
	}
	var failure = function(error)
		{console.log("failure", error);
	}
	var request = new BMSRequest("<your application route>", BMSRequest.GET);
	request.send(success, failure);
	```
	{: codeblock}
