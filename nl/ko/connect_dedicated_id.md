---



copyright:

  years: 2015，2017

lastupdated: "2017-12-08"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 공용 IBM ID에 데디케이티드 ID 연결
{: #connect_dedicated_id}

공용 IAM 서비스가 사용 가능한 데디케이티드 클라우드에 로그인할 수 있도록 {{site.data.keyword.Bluemix_notm}} CLI에서는 데디케이티드 ID 대신 공용 IBM ID로 로그인하도록 요구합니다.


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

데디케이티드 ID가 공용 IBM ID에 이미 연결되어 있는 경우 다음과 같이 인증되고 로그인됩니다.

```
Authenticating...
  OK
      
  Connected to dedicated user my_dedicated_id
```

하지만 데디케이티드 ID가 공용 IBM ID에 연결되지 않은 경우 다음과 같이 공용 IBM ID에 수동으로 연결하도록 프롬프트가 표시됩니다.

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

데디케이티드 ID의 신임 정보를 입력하는 옵션을 선택하십시오. 인증 성공 후 데디케이티드 ID가 공용 IBM ID에 연결됩니다.

## 로컬 UAA 서버에 강제 로그인

데디케이티드 ID로 UAA 서버에 강제로 로그인하려면 `bluemix login` 명령에 `--no-iam` 옵션을 지정하십시오.

```
  $ bluemix login --no-iam
```

## 공용 IBM ID에서 데디케이티드 ID 연결 끊기 

`bluemix iam dedicated-id-disconnect`를 사용하여 데디케이티드 ID와 공용 IBM ID의 연결을 끊으십시오.

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

