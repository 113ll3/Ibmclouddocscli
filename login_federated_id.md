---



copyright:

  years: 2015，2017

lastupdated: "2017-06-30"


---

{:shortdesc: .shortdesc}

# Log in to Bluemix with a Federated ID using the Command-Line Interface
{: #federated_id}

An initial attempt to log in to Bluemix with a federated ID and password from the command-line interface will be rejected. To successfully log in, you will need to use a one-time passcode or Bluemix API key. Because a One-time passcode retrieves code from the Bluemix Console, it will cause the use of a federated ID in your automation script, to fail; you must use the  Bluemix API key with an automated script.

**Note**: The required API key is Bluemix API key for authentication with Bluemix platform, not the Softlayer API key or Bluemix service API key.

## Log in with a one-time passcode
{:onetime_passcode}


From the Bluemix CLI, log in with `--sso`. Follow the url in the prompt to get the one-time passcode, copy the value, and paste it into the CLI as your input:

```
bluemix login --sso
API endpoint: https://api.ng.bluemix.net

One Time Code (Get one at https://iam.ng.bluemix.net/oidc/passcode)> 
Authenticating...
OK

```


If you are using CF CLI, use use the `--sso` option:

```
cf login --sso
API endpoint: https://api.ng.bluemix.net

One Time Code (Get one at https://login.ng.bluemix.net/UAALoginServerWAR/passcode)> 
Authenticating...
OK

```


## Log in with a Bluemix API key
{:api_key}

### Create a Bluemix API key

For more info on creating an API key from the Bluemix Console, see: [Managing API keys](/docs/iam/apikeys.html#manapikey).

You can also use the {{site.data.keyword.Bluemix_notm}} CLI to manage your API keys by listing your keys, creating keys, updating keys, or deleting keys. See the [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam) command section for more information. Use the `-f` option to generate an API key file instead of showing the key in the command window:

```
bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]
```

### log in with an API key using the Bluemix CLI

After you generate the API key, there are a few ways you can use the key with the Bluemix CLI:

1. Call the API key directly:

  ```
  bluemix login --apikey <api_key_string>
  ```

2. Call the API key with the key file. Alternatively, you can call the generated key file using the `-f` option when you create the API key:

  ```
  bluemix login --apikey @key_file_name
  ```

3. Set an environment variable. Additionally, you can also set an environment variable on your system. For example: BLUEMIX_API_KEY=<api_key_string>, where `api_key_string` is the custom value of the API key. After the environment variavle is set, you can simply specify `bluemix login` from the CLI. 


### login with API key using CF CLI

If you want to log in using the CF CLI instead of the Bluemix CLI, just use `apikey` as the username and the API key string as the password:

```
cf login     
API endpoint: https://api.ng.bluemix.net

Email> apikey    

Password>
Authenticating...
OK
```
