---

copyright:
  years: 2016, 2018
lastupdated: "2018-06-21"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock: .codeblock}

# 네트워크 요청 작성
{: #sdk-network-request}

`BMSCore` SDK를 사용하여 모든 리소스에 대한 네트워크 요청을 작성할 수도 있습니다.

## Android
{: #request-android}

1. Android 애플리케이션에서 [클라이언트 SDK를 가져와서 초기화](sdk_BMSClient.html#init-BMSClient-android)했는지 확인하십시오.

2. 네트워크 요청을 작성하십시오.

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

`Request` 클래스는 요청을 작성하고 요청이 완료된 후에 응답을 가져오는 간단한 방법입니다. 대량 파일 또는 대량 볼륨의 데이터를 다운로드하거나 업로드하는 경우 `Request` `download` 또는 `upload` 메소드를 사용할 수 있습니다. 다운로드 또는 업로드 진행상태를 모니터하려면 사용자 정의 `ProgressListener`를 작성하고 이를 `download` 또는 `upload` 메소드로 전달하십시오.

<!--For complete usage examples, see the `BMSCore` GitHub [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core).-->


## iOS
{: #request-ios}

1. iOS 애플리케이션에서 [클라이언트 SDK를 가져와서 초기화](sdk_BMSClient.html#init-BMSClient-ios)했는지 확인하십시오.

2. 네트워크 요청을 작성하십시오.

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

`Request` 클래스는 요청을 작성하고 요청이 완료된 후에 응답을 가져오는 간단한 방법입니다. `Request` 클래스보다 더 많은 유연성과 제어 기능을 원하는 경우, `BMSURLSession` 클래스를 사용할 수 있습니다. `BMSURLSession` 클래스의 일부 기능으로는 업로드 프로세스 모니터링과 요청 일시정지 또는 취소가 있습니다. 응답을 가져오는 옵션으로 완료 핸들러 또는 위임 중 하나를 선택할 수 있습니다.

`BMSURLSession` 클래스는 iOS용으로만 사용 가능합니다.

완전한 사용 예제는 `BMSCore` GitHub [README](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core)를 참조하십시오.


## Cordova
{: #request-cordova}

1. Cordova 애플리케이션에서 [클라이언트 SDK를 가져와서 초기화](sdk_BMSClient.html#init-BMSClient-cordova)했는지 확인하십시오.

2. 네트워크 요청을 작성하십시오.

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
