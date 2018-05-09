---

copyright:
  years: 2016, 2018
lastupdated: "2018-04-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Cómo realizar una solicitud de red
{: #sdk-network-request}

También puede utilizar el SDK `BMSCore` para realizar solicitudes de red a cualquier recurso.

## Android
{: #request-android}

1. Asegúrese de que ha [importado el SDK de cliente y lo ha inicializado](sdk_BMSClient.html#init-BMSClient-android) en su aplicación Android.

2. Realice una solicitud de red.

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

La clase `Request` ofrece un método sencillo para realizar una solicitud HTTP y obtener la respuesta una vez completada la solicitud. Si va a descargar o a cargar archivos grandes o grandes cantidades de datos, puede utilizar los métodos `Request` `download` o `upload`. Para supervisar el progreso de la descarga o de la carga, cree un `ProgressListener` personalizado y páselo a los métodos `download` o `upload`.

<!--For complete usage examples, see the `BMSCore` GitHub [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core).-->


## iOS
{: #request-ios}

1. Asegúrese de que ha [importado el SDK de cliente y lo ha inicializado](sdk_BMSClient.html#init-BMSClient-ios) en su aplicación iOS.

2. Cree una solicitud de red.

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

La clase `Request` ofrece un método sencillo para realizar una solicitud HTTP y obtener la respuesta una vez completada la solicitud. Si desea más flexibilidad y control del que puede obtener de la clase `Request`, puede utilizar la clase `BMSURLSession`. Algunas de las características de la clase `BMSURLSession` incluyen el progreso de supervisión de las cargas y la colocación en pausa o cancelación de solicitudes. Para obtener las respuestas, puede elegir manejadores de terminación o delegados.

La clase `BMSURLSession` solo está disponible para iOS.

Para ver ejemplos de uso completos, consulte archivo [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core) de `BMSCore` GitHub.


## Cordova
{: #request-cordova}

1. Asegúrese de haber [importado e inicializado el SDK del cliente](sdk_BMSClient.html#init-BMSClient-cordova) en la aplicación Cordova.

2. Cree una solicitud de red.

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

