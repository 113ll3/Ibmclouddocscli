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

# 提出網路要求
{: #sdk-network-request}

您也可以使用 `BMSCore` SDK，對任何資源提出網路要求。

## Android
{: #request-android}

1. 確定您已在 Android 應用程式中[匯入並起始設定用戶端 SDK](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-android)。

2. 提出網路要求。

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

`Request` 類別是提出 HTTP 要求並在要求完成後取得回應的簡單方法。如果您要下載或上傳大型檔案或大型資料主體，則可以使用 `Request` `download` 或 `upload` 方法。若要監視下載或上傳進度，請建立自訂 `ProgressListener`，並將它傳遞給 `download` 或 `upload` 方法。

如需完整的用法範例，請參閱 `BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。


## iOS
{: #request-ios}

1. 確定您已在 iOS 應用程式中[匯入並起始設定用戶端 SDK](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-ios)。

2. 建立網路要求。

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

`Request` 類別是提出 HTTP 要求並在要求完成後取得回應的簡單方法。如果您想要得到比 `Request` 類別更多的彈性與控制，可以使用 `BMSURLSession` 類別。`BMSURLSession` 類別部分特性包括監視上傳的進度，以及暫停或取消要求。若要取得回應，您可以選擇完成處理程式或委派。

`BMSURLSession` 類別僅適用於 iOS。

如需完整的用法範例，請參閱 `BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")。

## Cordova
{: #request-cordova}

1. 確定您已在 Cordova 應用程式中[匯入並起始設定用戶端 SDK](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-cordova)。

2. 建立網路要求。

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
