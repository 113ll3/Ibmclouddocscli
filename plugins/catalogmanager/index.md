---



copyright:

  years: 2015, 2017

lastupdated: "2017-01-12"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Catalog Manager CLI
{: #ctlogmgrcli}

*Version:* 0.2.1

Catalog Manager (catalog-manager) is a {{site.data.keyword.Bluemix_notm}} CLI plug-in for catalog management including template and service broker management.
{: shortdesc}

**Note:** *Prerequisites* list which actions are required before using the command. Commands that have no prerequisite actions list **None**. Otherwise, prerequisites might include one or more of the following actions:
<dl>
<dt>**Endpoint**</dt>
<dd>An API endpoint must be set through the `bluemix api` before using the command. For example:
<pre><code>bluemix api https://api.xxx.bluemix.net</code></pre>
</dd>
<dt>**Login**</dt>
<dd>Login by using the `bluemix login` command is required before using this command. For example:
<pre><code>bluemix login</code></pre>
</dd>
<dt>**Target**</dt>
<dd>The `bluemix target` command must be used to set an org and space before using this command. For example:
<pre><code>bluemix target -o MyOrg -s MySpace</code></pre>
</dd>
</dl>


## bluemix catalog template-registry
View Bluemix template registry.

```
bluemix catalog template-registry
```

**Prerequisites**:  Endpoint


## bluemix catalog template-register
Register a new template on Bluemix template registry.

```
bluemix catalog template-register TEMPLATE_ID TEMPLATE_URL
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*TEMPLATE_ID* (required):  The ID of new registered template.

*TEMPLATE_URL*  (required):  TEMPLATE_URL points to a URL which hosts the metadata of new template.

**Examples**:

Create a new template with name `javaHelloWorld`:

```
bluemix catalog template-register javaHelloWorld http://javaHelloWorld.ng.bluemix.net/info
```


## bluemix catalog template-deregister
Deregister an existing boilerplate template.

```
bluemix catalog template-deregister TEMPLATE_ID [-f]
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*TEMPLATE_ID* (required):  You can use `bluemix catalog templates` to view all of the template IDs.

-f  (optional):  Force deregistration without confirmation.

**Examples**:

Deregister template `javaHelloWorld` without confirmation:

```
bluemix catalog template-deregister javaHelloWorld -f
```


## bluemix catalog service-broker
View the specified service broker info.

```
bluemix catalog service-broker SERVICE_BROKER_NAME
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*SERVICE_BROKER_NAME* (required):  The name of the service broker to be visited.


## bluemix catalog service-broker-create
Create a new service broker.

```
bluemix catalog service-broker-create SERVICE_BROKER_JSON_TEXT|SERVICE_BROKER_JSON_FILE [--no-billing]
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*SERVICE_BROKER_JSON_TEXT*|*SERVICE_BROKER_JSON_FILE* (required):  The JSON which describes the new service broker to be created. It can be either the JSON file name or JSON text directly.

--no-billing  (optional):  No billing for this service broker if specified.

**Examples**:

Create a new service broker with JSON file:

```
bluemix catalog service-broker-create ./broker.json
```

Create a new service broker with JSON text and without billing:

```
bluemix catalog service-broker-create '{"name":"test_broker", ...}' --no-billing
```

The following is an example for service broker JSON with all required fields:

```
{
    "name": "my_broker",  // the name of service broker
    "broker_url": "http://my_broker.ng.bluemix.net"  // the URL that points to the metadata of service broker
    "auth_username": "username",
    "auth_password": "password",  // The user name and password to visit the service broker url. User name and password should be sent with HTTP basic authorization.
    "visibilities": [
        {"organization_name": "OE_Runtimes_Scaling"}
    ]
}
```


## bluemix catalog service-broker-update
Update an existing service broker.

```
bluemix catalog service-broker-update ORIGINAL_BROKER_NAME SERVICE_BROKER_JSON_TEXT|SERVICE_BROKER_JSON_FILE [--allow-rename] [--no-syndication]
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*ORIGINAL_BROKER_NAME* (required):  The name of service broker to be updated.

*SERVICE_BROKER_JSON_TEXT*|*SERVICE_BROKER_JSON_FILE* (required):  The new JSON that describes the service broker. It can be either the JSON file name or JSON text directly.

--allow-rename (Optional): If set, specifies to use a new service broker name, which is set through 'name' property in the JSON file.

--no-syndication (Optional): If set, specifies to disable syndication when the service broker is updated.

**Examples**:

Update existing service broker `auto-scaling`:

```
bluemix catalog service-broker-update auto-scaling ./auto-scaling.json --allow-rename --no-syndication
```

See `bluemix catalog service-broker-create` for more details on service broker JSON format.


## bluemix catalog service-broker-delete
Delete the specified service broker.

```
bluemix catalog service-broker-delete SERVICE_BROKER_NAME [-f]
```

**Prerequisites**:  Endpoint, Login

**Command options**:

*SERVICE_BROKER_NAME* (required):  The name of service broker to be deleted.

-f  (optional):  Force deletion without confirmation.

**Examples**:

Delete service broker `auto-scaling` without confirmation:

```
bluemix catalog service-broker-delete auto-scaling -f
```
# rellinks
{: rellinks}
## general
{: general}
* [{{site.data.keyword.Bluemix_notm}} CLI ![External link icon](../../../icons/launch-glyph.svg)](http://plugins.{DomainName}/ui/home.html){: new_window}
* [Catalog Manager CLI ![External link icon](../../../icons/launch-glyph.svg)](http://plugins.{DomainName}/ui/repository.html#bluemix-plugins){: new_window}
