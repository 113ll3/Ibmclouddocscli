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

# 専用 ID とパブリック IBM ID との接続
{: #connect_dedicated_id}

パブリック IAM サービスが使用可能な専用クラウドにログインするために、{{site.data.keyword.Bluemix_notm}} CLI では専用 ID ではなくパブリック IBM ID でログインするよう要求されます。


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

専用 ID がパブリック IBM ID に既に接続されている場合、認証されてログインされます。

```
  Authenticating...
  OK

  Connected to dedicated user my_dedicated_id
```

しかし、専用 ID がパブリック IBM ID に接続されていない場合、パブリック IBM ID に手動で接続するようプロンプトが出されます。

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

専用 ID の資格情報を入力するオプションを選択します。認証に成功すると、専用 ID はパブリック IBM ID に接続されます。

## ローカル UAA サーバーへのログインの強制

専用 ID での UAA サーバーへのログインを強制するには、`bluemix login` コマンドに `--no-iam` オプションを指定します。

```
  $ bluemix login --no-iam
```

## 専用 ID のパブリック IBM ID からの切断 

`bluemix iam dedicated-id-disconnect` を使用して、パブリック IBM ID と接続された専用 ID を切断できます。

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

