---



copyright:

  years: 2015，2018

lastupdated: "2017-12-08"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 将专用标识连接到公共 IBM 标识
{: #connect_dedicated_id}

要登录到提供公共 IAM 服务的专用云，{{site.data.keyword.Bluemix_notm}} CLI 会要求您使用公共 IBM 标识（而不是专用标识）登录。


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

如果您的专用标识已经连接到公共 IBM 标识，那么它将进行认证并登录：

```
Authenticating...
  OK
      
  Connected to dedicated user my_dedicated_id
```

但是，如果您的专用标识尚未连接到公共 IBM 标识，那么将提示您手动连接到公共 IBM 标识：

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

选择其中一个选项以输入专用标识的凭证。成功认证后，您的专用标识将连接到公共 IBM 标识。

## 强制登录到本地 UAA 服务器

要强制使用专用标识登录到 UAA 服务器，请在 `bluemix login` 命令中指定 `--no-iam` 选项：

```
  $ bluemix login --no-iam
```

## 断开专用标识与公共 IBM 标识的连接 

可以使用 `bluemix iam dedicated-id-disconnect` 来断开公共 IBM 标识与所连接专用标识的连接。

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

