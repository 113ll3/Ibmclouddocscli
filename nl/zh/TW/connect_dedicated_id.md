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

# 將專用 ID 連接至公用 IBM ID
{: #connect_dedicated_id}

若要登入有公用 IAM 服務可用的專用雲端，{{site.data.keyword.Bluemix_notm}} CLI 會要求您使用公用 IBM ID 來登入，而非專用 ID。


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

如果您的專用 ID 已連接至公用 IBM ID，則會進行鑑別並登入：

```
Authenticating...
  OK
      
  Connected to dedicated user my_dedicated_id
```

不過，如果您的專用 ID 尚未連接至公用 IBM ID，則系統會提示您手動連接至公用 IBM ID：

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

選取可輸入專用 ID 認證的選項。成功鑑別之後，專用 ID 就會連接至公用 IBM ID。

## 強制登入本端 UAA 伺服器

若要使用專用 ID 強制登入 UAA 伺服器，請在 `bluemix login` 指令中指定 `--no-iam` 選項：

```
  $ bluemix login --no-iam
```

## 中斷專用 ID 與公用 IBM ID 的連線 

您可以使用 `bluemix iam dedicated-id-disconnect` 來中斷公用 IBM ID 與已連接之專用 ID 的連線。

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

