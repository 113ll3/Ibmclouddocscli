---



copyright:

  years: 2015，2017

lastupdated: "2017-07-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Logging in with a federated ID
{: #federated_id}

As a federated user, you can log in to {{site.data.keyword.Bluemix}} from the command-line interface (CLI) by using either a one-time passcode or an API key. 
{: shortdesc}

## Using a one-time passcode
{:onetime_passcode}

When you use the one-time passcode option to log in with a federated ID, you specify the single-sign on (SSO) parameter to get a one-time passcode, which you then enter at login. 

Because a one-time passcode retrieves code from the {{site.data.keyword.Bluemix_notm}} console, it causes the use of a federated ID in your automation script to fail. Avoid trouble by using the API key option with an automated script. 
{: tip}

### From the {{site.data.keyword.Bluemix_notm}} CLI
1. Specify the `--sso` option with the `bluemix login` command.
2. Follow the URL in the prompt to get the one-time passcode.
3. Copy and paste the passcode value in the CLI as your input.
    
  ``` 
  bluemix login --sso
  API endpoint: https://api.ng.bluemix.net
      
  One Time Code (Get one at https://iam.ng.bluemix.net/oidc/passcode)> 
  Authenticating...
  OK
      
  ```
  
### From the Cloud Foundry CLI
1. Specify the `--sso` option with the `cf login` command. 
2. Follow the URL in the prompt to get the one-time passcode. 
3. Copy and paste the passcode value in the CLI as your input. 
    
  ```
  cf login --sso
  API endpoint: https://api.ng.bluemix.net
      
  One Time Code (Get one at https://login.ng.bluemix.net/UAALoginServerWAR/passcode)>
  Authenticating...
  OK
      
  ```

## Using an API key
{:api_key}

The required API key is the {{site.data.keyword.Bluemix_notm}} API key that's used to authenticate with the {{site.data.keyword.Bluemix_notm}} platform, not the Softlayer API key or {{site.data.keyword.Bluemix_notm}} service API key.

1. Create an API key with the [`bluemix iam api-key-create` command](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_api_key_create). Use the `-f` option to generate an API key file instead of showing the key in the command window:

   ```
   bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]
  
   ```

2. Log in with the API key. 

  You can use the API key with the {{site.data.keyword.Bluemix_notm}} CLI in any of the following ways:
    
    * Call the API key directly:
  
      ```
      bluemix login --apikey <api_key_string>
    
      ```
    
    * Call the API key with the key file: 
  
      ```
      bluemix login --apikey @key_file_name
    
      ```
    
    * Set an environment variable. Additionally, you can also set an environment variable on your system. For example, BLUEMIX_API_KEY=<api_key_string>, where `api_key_string` is the custom value of the API key. After the environment variable is set, you can simply specify `bluemix login` from the CLI. 
  
  To log in by using the Cloud Foundry CLI, specify `apikey` as the user name and the API key string as the password:

    ```
    cf login
    API endpoint: https://api.ng.bluemix.net
  
    Email> apikey
  
    Password>
    Authenticating...
    OK
  
    ```

