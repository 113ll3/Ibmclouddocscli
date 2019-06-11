---

copyright:
  years: 2016, 2019
lastupdated: "2019-05-21"

keywords: cli, bmscore, bmscore sdk, network request, ios network cli, android network cli, cordova network cli, mobile network request, mobile cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Netzanforderung stellen
{: #sdk-network-request}

Sie können das `BMSCore`-SDK auch verwenden, um Netzanforderungen an Ressourcen auszugeben.

## Android
{: #request-android}

1. Stellen Sie sicher, dass Sie in Ihrer Android-Anwendung das [Client-SDK importiert und initialisiert](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-android) haben.

2. Geben Sie eine Netzanforderung aus.

	```Java
	String customResourceURL = "<Ihre Ressourcen-URL>";
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

Die Klasse `Request` ist ein einfacher Weg, eine HTTP-Anforderung auszugeben und die Antwort zu erhalten, nachdem die Anforderung abgeschlossen wurde. Wenn Sie große Dateien oder umfangreiche Datensammlungen herunterladen oder hochladen, können Sie die `Request`-Methoden `download` oder `upload` verwenden. Um den Fortschritt des Downloads oder Uploads zu überwachen, erstellen Sie einen angepassten `ProgressListener` und übergeben ihn an die Methoden `download` oder `upload`.

Vollständige Verwendungsbeispiele finden Sie in der GitHub-[README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") zu `BMSCore`.


## iOS
{: #request-ios}

1. Stellen Sie sicher, dass Sie in Ihrer iOS-App das [Client-SDK importiert und initialisiert](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-ios) haben.

2. Erstellen Sie eine neue Netzanforderung.

	### Swift 3.0
	{: #ios-swift3 notoc}

	```Swift
	let customResourceURL = "<Ihre Ressourcen-URL>"
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
	let customResourceURL = "<Ihre Ressourcen-URL>"
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

Die Klasse `Request` ist ein einfacher Weg, eine HTTP-Anforderung auszugeben und die Antwort zu erhalten, nachdem die Anforderung abgeschlossen wurde. Wenn Sie mehr Flexibilität und Kontrolle wünschen als die Klasse `Request` bereitstellt, können Sie stattdessen die Klasse `BMSURLSession` verwenden. Manche Funktionen der Klasse `BMSURLSession` umfassen das Überwachen des Fortschritts von Uploads sowie das Anhalten oder Abbrechen von Anforderungen. Um die Antworten zu erhalten, können Sie zwischen Completion-Handlern oder Delegierten wählen.

Die Klasse `BMSURLSession` ist nur für iOS verfügbar.

Vollständige Verwendungsbeispiele finden Sie in der GitHub-[README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") zu `BMSCore`.

## Cordova
{: #request-cordova}

1. Stellen Sie sicher, dass Sie in Ihrer Cordova-App das [Client-SDK importiert und initialisiert](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-cordova) haben.

2. Erstellen Sie eine neue Netzanforderung.

	```Javascript
	var success = function(data) {
		console.log("success", data);
	}
	var failure = function(error)
		{console.log("failure", error);
	}
	var request = new BMSRequest("<Ihre Anwendungsroute>", BMSRequest.GET);
	request.send(success, failure);
	```
	{: codeblock}
