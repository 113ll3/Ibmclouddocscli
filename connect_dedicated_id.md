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

# Connecting a dedicated ID to your public IBMid
{: #connect_dedicated_id}

To log in to a dedicated cloud where public IAM service is available, {{site.data.keyword.Bluemix_notm}} CLI asks you to log in with your public IBMid instead of the dedicated ID.


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API endpoint: https://api.{dedicated_env}.bluemix.net

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

If your dedicated ID has already been connected to the public IBMid, it will authenticate and log in:

```
  Authenticating...
  OK

  Connected to dedicated user my_dedicated_id
```

However, if your dedicated ID has not been connected to the public IBMid, you will be prompted to manually connect to the public IBMid:

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

Select an option to input the credentials for the dedicated ID. After successful authentication, your dedicated ID will be connected to your public IBMid.

## Force logging in to local UAA server

To force logging in to the UAA server with a dedicated ID, specify the `--no-iam` option in `bluemix login` command:

```
  $ bluemix login --no-iam
```

## Disconnect your dedicated ID from the public IBMid 

You can use `bluemix iam dedicated-id-disconnect` to disconnect public IBMid with connected dedicated ID.

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

