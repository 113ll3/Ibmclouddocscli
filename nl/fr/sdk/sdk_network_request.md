---

copyright:
  years: 2016, 2019
lastupdated: "2019-02-21"

keywords: bmscore, bmscore sdk, network request, ios, android, cordova

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Elaboration d'une demande de réseau
{: #sdk-network-request}

Vous pouvez également utiliser le SDK `BMSCore` pour effectuer des demandes de réseau sur n'importe quelle ressource.

## Android
{: #request-android}

1. Vérifiez que vous avez bien [importé et initialisé le kit SDK client](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-android) dans votre application Android.

2. Faites une demande de réseau.

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

La classe `Request` est un moyen simple d'effectuer une demande HTTP et d'obtenir une réponse une fois la demande effectuée. Si vous envoyez ou recevez par téléchargement des fichiers volumineux ou de grands ensembles de données, vous pouvez utiliser la méthode `Request` `download` ou `upload`. Pour surveiller la progression de l'envoi ou de la réception par téléchargement, créez un élément `ProgressListener` personnalisé et transmettez-le à la méthode `download` ou `upload`.

<!--For complete usage examples, see the `BMSCore` GitHub [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core).-->


## iOS
{: #request-ios}

1. Vérifiez que vous avez bien [importé et initialisé le kit SDK client](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-ios) dans votre application iOS.

2. Créez une demande de réseau.

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

La classe `Request` est un moyen simple d'effectuer une demande HTTP et d'obtenir une réponse une fois la demande effectuée. Si vous avez
besoin de plus de souplesse et de contrôle que ceux offerts par la classe `Request`, vous pouvez utiliser la classe `BMSURLSession`. Parmi
les fonctionnalités de la classe `BMSURLSession`, on dénote le suivi de la progression des téléchargements et la mise en pause ou l'annulation des
demandes. Pour obtenir les réponses, vous pouvez choisir des gestionnaires d'exécution ou des délégués.

La classe `BMSURLSession` n'est disponible que pour iOS.

Pour accéder à des exemples d'utilisation complets, consultez le fichier [README `BMSCore` GitHub ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").


## Cordova
{: #request-cordova}

1. Vérifiez que vous avez bien [importé et initialisé le kit SDK client](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-cordova) dans votre application Cordova.

2. Créez une demande de réseau.

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
