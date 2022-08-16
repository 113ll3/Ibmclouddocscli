---

copyright:
  years: 2022
lastupdated: "2022-08-04"

keywords: cli, context-based restrictions plugin

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Context-based restrictions CLI plug-in
{: #cbr-plugin}

The {{site.data.keyword.cloud}} context-based restrictions command-line interface (CLI) provides extra capabilities for context-based restrictions. You can use this CLI plug-in to manage access restrictions for {{site.data.keyword.cloud}} resources based on the network location of access requests.
{: shortdesc}

## Before you begin
{: #prereqs-cbr-plugin}

* Install the {{site.data.keyword.cloud_notm}} CLI. For more information, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started). The prefix for running commands by using the {{site.data.keyword.cloud_notm}} CLI is `ibmcloud`.
* Before you run commands, log in to {{site.data.keyword.cloud_notm}} with the `ibmcloud login` command to generate an access token and authenticate your session.


## Installing the context-based restrictions plug-in
{: #install-cbr-plugin}

To install the context-based restrictions plug-in, run the following command:

```bash
ibmcloud plugin install cbr
```
{: codeblock}

In the command line, you are notified when updates to the `ibmcloud` CLI and `cbr` CLI plug-in are available. Ensure that you keep your CLI up to date so that you can use all the available commands and flags.

If you want to view the current version of your `cbr` CLI plug-in, run `ibmcloud plugin list`.

## Zones
{: #cbr-zones-cli}

Operations on network zones.

### ibmcloud cbr zone-create
{: #cbr-cli-zone-create-command}

This operation creates a network zone for the specified account.

```sh
ibmcloud cbr zone-create [--name NAME] [--description DESCRIPTION] [--addresses ADDRESSES] [--excluded EXCLUDED] [--vpc VPC] [--service-ref SERVICE-REF] [--file FILE]
```
{: codeblock}

#### Example
{: #cbr-cli-zone-create-example}

```sh
ibmcloud cbr zone-create --name example-zone --description "Example zone description" --addresses 192.0.2.1,192.2.3.5-192.2.3.10
ibmcloud cbr zone-create --name example-zone-with-service-ref --service-ref service_name=kms
ibmcloud cbr zone-create --name example-zone-with-vpc --vpc crn:v1:staging:public:is:us-south:a/12ab34cd56ef78ab90cd12ef34ab56cd::vpc:r123-abc456de-f789-abc1-23de-f456abc789ab
```
{: codeblock}

#### Command options
{: #cbr-zone-create-cli-options}

--name (string)
:   The name of the zone.

--description (string)
:   The description of the zone.

--addresses (string)
:   The list of addresses in the zone. Only addresses of type `ipAddress`, `ipRange`, and `subnet` are allowed in a comma delimited format.

--excluded (string)
:   The list of excluded addresses in the zone. Only addresses of type `ipAddress`, `ipRange`, and `subnet` are allowed in a comma delimited format.

--service-ref (string)
:   The service refs in the zone. Input in the form `service_name=VALUE,service_name=VALUE,...`.
:   To find a list of available service refs, run the `ibmcloud cbr service-ref-targets` [command](#cbr-cli-service-ref-targets-command).

--vpc (string)
:   The VPCs allowed in the zone. Input in the form `value,value,...`.

--file (string)
:   The supplied file is used to create the zone. This flag is unique and cannot be used with other flags. The file needs to follow the JSON schema for the zone create API. For more information, see the [Context-based restrictions API](/apidocs/context-based-restrictions#create-zone-request){: external}.


### ibmcloud cbr zones
{: #cbr-cli-zones-command}

This operation lists network zones in the specified account.

```sh
ibmcloud cbr zones [--name NAME] [--sort SORT]
```
{: codeblock}

#### Example
{: #cbr-cli-zones-example}

```sh
ibmcloud cbr zones
```
{: codeblock}

#### Command options
{: #cbr-zones-cli-options}

--name (string)
:   The name of the zone.

--sort (string)
:   Sorts results by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).


### ibmcloud cbr zone
{: #cbr-cli-zone-command}

This operation retrieves the network zone that is identified by the specified zone ID.

```sh
ibmcloud cbr zone ZONE-ID
```
{: codeblock}

#### Example
{: #cbr-cli-zone-example}

```sh
ibmcloud cbr zone 65810ac762004f22ac19f8f8edf70a34
```
{: codeblock}

### ibmcloud cbr zone-update
{: #cbr-cli-zone-update-command}

This operation replaces the network zone that is identified by the specified zone ID. Partial updates are not supported and the entire network zone object is replaced.

```sh
ibmcloud cbr zone-update ZONE-ID [--name NAME] [--description DESCRIPTION] [--addresses ADDRESSES] [--excluded EXCLUDED] [--vpc VPC] [--service-ref SERVICE-REF] [--file FILE]
```
{: codeblock}

#### Example
{: #cbr-zone-update-example}

```shell
ibmcloud cbr zone-update 65810ac762004f22ac19f8f8edf70a34 --name 'Example Zone Name' --addresses 166.22.23.0-166.22.23.108 --excluded 166.22.23.100
ibmcloud cbr zone-update 65810ac762004f22ac19f8f8edf70a34 --name example-zone-with-service-ref --service-ref service_name=kms
ibmcloud cbr zone-update 65810ac762004f22ac19f8f8edf70a34 --name example-zone-with-vpc --vpc crn:v1:staging:public:is:us-south:a/12ab34cd56ef78ab90cd12ef34ab56cd::vpc:r123-abc456de-f789-abc1-23de-f456abc789ab
```
{: codeblock}

#### Command options
{: #cbr-zone-update-cli-options}

--name (string)
:   The name of the zone.

--description (string)
:   The description of the zone.

--addresses (string)
:   The list of addresses in the zone. Only addresses of type `ipAddress`, `ipRange`, and `subnet` are allowed in a comma delimited format.

--excluded (string)
:   The list of excluded addresses in the zone. Only addresses of type `ipAddress`, `ipRange`, and `subnet` are allowed in a comma delimited format.

--service-ref (string)
:   The service refs in the zone. Input in the form `name=value,name=value,...`.

--vpc (string)
:   The VPCs allowed in the zone. Input in the form `value,value,...`.

--file (string)
:   The supplied file is used to update the zone. This flag is unique and cannot be used with other flags. The file needs to follow the JSON schema for the zone update API. For more information, see the [Context-based restrictions API](/apidocs/context-based-restrictions#replace-zone-request){: external}.


### ibmcloud cbr zone-delete
{: #cbr-cli-zone-delete-command}

This operation deletes the network zone that is identified by the specified zone ID.

```sh
ibmcloud cbr zone-delete ZONE-ID
```
{: codeblock}

#### Example
{: #cbr-cli-zone-delete-example}

```sh
ibmcloud cbr zone-delete 65810ac762004f22ac19f8f8edf70a34
```
{: codeblock}

### ibmcloud cbr service-ref-targets
{: #cbr-cli-service-ref-targets-command}

This operation lists all of the available service reference targets.

```sh
ibmcloud cbr service-ref-targets [--type TYPE]
```
{: codeblock}

#### Example
{: #cbr-cli-service-ref-targets-example}

```sh
ibmcloud cbr service-ref-targets
```
{: codeblock}

#### Command options
{: #cbr-service-ref-targets-cli-options}

--type (string)
:   Specifies the types of services to retrieve. The default value is `all`. Allowable values are: `all`, `platform_service`.


## Rules
{: #cbr-rules-cli}

Operations on context-based restriction rules.

### ibmcloud cbr rule-create
{: #cbr-cli-rule-create-command}

This operation creates a rule for the specified account.

```sh
ibmcloud cbr rule-create [--description DESCRIPTION] [--context-attributes CONTEXT-ATTRIBUTES] [--resource-attributes RESOURCE-ATTRIBUTES] [--region REGION] [--resource RESOURCE] [--resource-group-id RESOURCE-GROUP-ID] [--resource-type RESOURCE-TYPE] [--service-instance SERVICE-INSTANCE] [--service-name SERVICE-NAME] [--zone-id ZONE-ID] [--tags TAGS] [--enforcement-mode ENFORCEMENT-MODE] [--file FILE]
```
{: codeblock}

#### Example
{: #cbr-cli-rule-create-example}

```sh
ibmcloud cbr rule-create --description 'Example Rule Description' --service-name kms --context-attributes endpointType=private --zone-id 93de8d3f588ab2c457ff576c364d1145
```
{: codeblock}

#### Command options
{: #cbr-rule-create-cli-options}

--description (string)
:   The description of the rule.

--context-attributes (string)
:   The context-attributes this rule applies to in the form of `name=value,name=value,...`.

--resource-attributes (string)
:   The resource-attributes this rule applies to in the form of `name=value,name=value,...`.

--region (string)
:   Shorthand for creating IBM Cloud resource attribute `region`. For supported regions, run `ibmcloud regions`.

--resource (string)
:   Shorthand for creating IBM Cloud resource attribute `resource`.

--resource-group-id (string)
:   Shorthand for creating IBM Cloud resource attribute `resourceGroupId`.

--resource-type (string)
:   Shorthand for creating IBM Cloud resource attribute `resourceType`.

--service-instance (string)
:   Shorthand for creating IBM Cloud resource attribute `serviceInstance`.

--service-name (string)
:   Shorthand for creating IBM Cloud resource attribute `serviceName`.

--zone-id (string)
:   Shorthand for adding context attribute `networkZoneId` to the first context.

--tags (string)
:   The access tags of the resource in the form of `name:value,name:value,...`.

--enforcement-mode (string)
:   How the rule is enforced. The CLI accepts the values `enabled` (default), `disabled`, and `report`. For more informaiton about enforcement, see [Rule enforcement](/docs/account?topic=account-context-restrictions-whatis#rule-enforcement).

--file (string)
:   The supplied file is used to create the rule. This flag is unique and cannot be used with other flags. The file needs to follow the JSON schema for the rule create API. For more information, see the [Context-based restrictions API](/apidocs/context-based-restrictions#create-rule-request){: external}.


### ibmcloud cbr rules
{: #cbr-cli-rules-command}

This operation lists rules in the specified account.

```sh
ibmcloud cbr rules [--enforcement-mode ENFORCEMENT-MODE] [--region REGION] [--resource RESOURCE] [--resource-type RESOURCE-TYPE] [--service-instance SERVICE-INSTANCE] [--service-name SERVICE-NAME] [--zone-id ZONE-ID] [--sort SORT]
```
{: codeblock}

#### Example
{: #cbr-cli-rules-example}

```sh
ibmcloud cbr rules
```
{: codeblock}

#### Command options
{: #cbr-rules-cli-options}

--enforcement-mode (string)
:   How the rule is enforced. The CLI accepts the values `enabled` (default), `disabled`, and `report`. For more informaiton about enforcement, see [Rule enforcement](/docs/account?topic=account-context-restrictions-whatis#rule-enforcement).

--region (string)
:   The `region` resource attribute.

--resource (string)
:   The `resource` resource attribute.

--resource-type (string)
:   The `resourceType` resource attribute.

--service-instance (string)
:   The `serviceInstance` resource attribute.

--service-name (string)
:   The `serviceName` resource attribute.

--zone-id (string)
:   The globally unique ID of the zone.

--sort (string)
:   Sorts results by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).


### ibmcloud cbr rule
{: #cbr-cli-rule-command}

This operation retrieves the rule that is identified by the specified rule ID.

```sh
ibmcloud cbr rule RULE-ID
```
{: codeblock}

#### Example
{: #cbr-cli-rule-example}

```sh
ibmcloud cbr rule 30fd58c9b75f40e854b89c432318b4a2
```
{: codeblock}

### ibmcloud cbr rule-update
{: #cbr-cli-rule-update-command}

This operation replaces the rule that is identified by the specified rule ID. Partial updates are not supported and the entire rule object is replaced.

```sh
ibmcloud cbr rule-update RULE-ID [--description DESCRIPTION] [--context-attributes CONTEXT-ATTRIBUTES] [--resource-attributes RESOURCE-ATTRIBUTES] [--region REGION] [--resource RESOURCE] [--resource-group-id RESOURCE-GROUP-ID] [--resource-type RESOURCE-TYPE] [--service-instance SERVICE-INSTANCE] [--service-name SERVICE-NAME] [--zone-id ZONE-ID] [--tags TAGS] [--enforcement-mode ENFORCEMENT-MODE] [--file FILE]
```
{: codeblock}

#### Example
{: #cbr-cli-rule-update-example}

```sh
ibmcloud cbr rule-update 30fd58c9b75f40e854b89c432318b4a2 --description 'Example rule description' --service-name kms --context-attributes endpointType=private --zone-id 93de8d3f588ab2c457ff576c364d1145
```
{: codeblock}

#### Command options
{: #cbr-rule-update-cli-options}

--description (string)
:   The description of the rule.

--context-attributes (string)
:   The context-attributes this rule applies to in the form of `name=value,name=value,...`.

--resource-attributes (string)
:   The resource-attributes this rule applies to in the form of `name=value,name=value,...`.

--region (string)
:   Shorthand for creating IBM Cloud resource attribute `region`. For supported regions, run `ibmcloud regions`.

--resource (string)
:   Shorthand for creating IBM Cloud resource attribute `resource`.

--resource-group-id (string)
:   Shorthand for creating IBM Cloud resource attribute `resourceGroupId`.

--resource-type (string)
:   Shorthand for creating IBM Cloud resource attribute `resourceType`.

--service-instance (string)
:   Shorthand for creating IBM Cloud resource attribute `serviceInstance`.

--service-name (string)
:   Shorthand for creating IBM Cloud resource attribute `serviceName`.

--zone-id (string)
:   Shorthand for adding context attribute `networkZoneId` to the first context.

--tags (string)
:   The access tags of the resource in the form of `name:value,name:value,...`.

--enforcement-mode (string)
:   How the rule is enforced. The CLI accepts the values `enabled` (default), `disabled`, and `report`. For more informaiton about enforcement, see [Rule enforcement](/docs/account?topic=account-context-restrictions-whatis#rule-enforcement).

--file (string)
:   The supplied file is used to update the rule. This flag is unique and cannot be used with other flags. The file needs to follow the JSON schema for the rule update API. For more information, see the [Context-based restrictions API](/apidocs/context-based-restrictions#replace-rule-request){: external}.


### ibmcloud cbr rule-delete
{: #cbr-cli-rule-delete-command}

This operation deletes the rule that is identified by the specified rule ID.

```sh
ibmcloud cbr rule-delete RULE-ID
```
{: codeblock}

#### Example
{: #cbr-cli-rule-delete-example}

```sh
ibmcloud cbr rule-delete 30fd58c9b75f40e854b89c432318b4a2
```
{: codeblock}
