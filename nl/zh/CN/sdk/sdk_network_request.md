---

copyright:
  years: 2016, 2018
lastupdated: "2018-11-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 发出网络请求
{: #sdk-network-request}

您还可以使用 `BMSCore` SDK 向任何资源发出网络请求。

## Android
{: #request-android}

1. 确保已在 Android 应用程序中[导入客户机 SDK 并对其进行初始化](sdk_BMSClient.html#init-BMSClient-android)。

2. 发出网络请求。

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

`Request` 类是发出 HTTP 请求并在请求完成后获取响应的简单方法。如果要下载或上传大型文件或大量数据，那么可以使用 `Request` `download` 或 `upload` 方法。要监视下载或上传的进度，请创建定制 `ProgressListener`，并将其传递给 `download` 或 `upload` 方法。

<!--For complete usage examples, see the `BMSCore` GitHub [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core).-->


## iOS
{: #request-ios}

1. 确保已在 iOS 应用程序中[导入客户机 SDK 并对其进行初始化](sdk_BMSClient.html#init-BMSClient-ios)。

2. 创建网络请求。

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

`Request` 类是发出 HTTP 请求并在请求完成后获取响应的简单方法。如果需要比 `Request` 类中所提供的级别更高的灵活性和控制权，可以使用 `BMSURLSession` 类。`BMSURLSession` 类的某些功能包括监视上传进度以及暂停或取消请求。要获取响应，可以选择完成处理程序或代理。

`BMSURLSession` 类仅可用于 iOS。

有关完整用法示例，请参阅 `BMSCore` GitHub [README ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window}。


## Cordova
{: #request-cordova}

1. 确保已在 Cordova 应用程序中[导入客户机 SDK 并对其进行初始化](sdk_BMSClient.html#init-BMSClient-cordova)。

2. 创建网络请求。

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
