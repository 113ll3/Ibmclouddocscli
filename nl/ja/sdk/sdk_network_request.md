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

# ネットワーク要求を行う
{: #sdk-network-request}

`BMSCore` SDK を使用して、任意のリソースにネットワーク要求を行うこともできます。

## Android
{: #request-android}

1. Android アプリケーションに [Client SDK をインポートして初期化](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-android)しておくようにしてください。

2. ネットワーク要求を行います。

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

`Request` クラスは、HTTP 要求を発行し、要求が完了した後に応答を取得するための簡単な方法です。 大きなファイルまたは大量のデータをダウンロードまたはアップロードする場合は、`Request` `download` または `upload` のメソッドを使用できます。 ダウンロードまたはアップロードの進行をモニターするには、カスタムの `ProgressListener` を作成して、`download` または `upload` のメソッドに渡します。

使用法の完全な例については、`BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。


## iOS
{: #request-ios}

1. iOS アプリに [Client SDK をインポートして初期化](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-ios)しておくようにしてください。

2. ネットワーク要求を作成します。

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

`Request` クラスは、HTTP 要求を発行し、要求が完了した後に応答を取得するための簡単な方法です。 `Request` クラスよりも柔軟に、細かく管理する必要がある場合は、`BMSURLSession` クラスを使用できます。 `BMSURLSession` クラスには、アップロードの進行のモニタリング、要求の一時停止またはキャンセルなどの機能があります。 応答の取得には、完了ハンドラーまたはデリゲートのいずれかを選択することができます。

`BMSURLSession` クラスは、iOS のみで使用可能です。

使用法の完全な例については、`BMSCore` GitHub [README ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

## Cordova
{: #request-cordova}

1. Cordova アプリに [Client SDK をインポートして初期化](/docs/cli/sdk?topic=cloud-cli-sdk_BMSClient#init-BMSClient-cordova)しておくようにしてください。

2. ネットワーク要求を作成します。

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
