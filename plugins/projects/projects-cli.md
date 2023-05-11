---

copyright:
  years: 2023
lastupdated: "2023-05-11"

subcollection: cli

keywords: project CLI, project command line , project terminal, project shell

---

{{site.data.keyword.attribute-definition-list}}

# Project CLI reference
{: #projects-cli}

The {{site.data.keyword.cloud}} command-line interface (CLI) provides extra capabilities for service offerings. You can use the {{site.data.keyword.cloud_notm}} CLI to manage projects you have access to.
{: shortdesc}

## Before you begin
{: #projects-cli-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the Project CLI by running the following command:

   ```sh
   ibmcloud plugin install project
   ```
   {: pre}

You're notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running `ibmcloud plugin list`.
{: tip}

{{site.data.keyword.cloud_notm}} CLI requires Java&trade; 1.8.0.
{: note}

## `ibmcloud project create`
{: #project-cli-create-command}

Create a new project and asynchronously setup the tools to manage it. Add a deployable architecture by customizing the configuration. After the changes are validated and approved, deploy the resources that the project configures.

```sh
ibmcloud project create --name NAME [--description DESCRIPTION] [--configs CONFIGS] [--resource-group RESOURCE-GROUP] [--location LOCATION]
```

### Command options
{: #project-create-cli-options}

`--name` (string)
:   The project name. Required.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--description` (string)
:   A project's descriptive text.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--configs` ([`ProjectConfigPrototype[]`](#cli-project-config-prototype-example-schema))
:   The project configurations.

    The maximum length is `10000` items. The minimum length is `0` items.

`--resource-group` (string)
:   The resource group in which project data and tools are provisioned.

    The default value is `Default`. The maximum length is `40` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]*$/`.

`--location` (string)
:   The data center location where project resources are deployed.

    The default value is `us-south`. The maximum length is `12` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(us-south|us-east|eu-gb|eu-de)$/`.

### Example
{: #project-create-examples}

```sh
ibmcloud project create \
    --name=acme-microservice \
    --description='A microservice to deploy on top of ACME infrastructure.' \
    --configs='[{"id": "exampleString", "name": "common-variables", "labels": ["exampleString"], "description": "exampleString", "locator_id": "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global", "input": [{"name": "exampleString"}], "setting": [{"name": "exampleString", "value": "exampleString"}]}]' \
    --resource-group=Default \
    --location=us-south
```
{: pre}


### Example output
{: #project-create-cli-output}

Sample response for creating a project

```json
{
  "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
  "name" : "acme-microservice",
  "description" : "A microservice to deploy on top of ACME infrastructure.",
  "configs" : [ {
    "id" : "673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "name" : "common-variables",
    "type" : "terraform_template",
    "external_resources_account" : "e5ed08b9203bad3e4b6f57f0d1675a88",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "output" : [ {
      "name" : "tags",
      "value" : [ "project:ghost", "type:infrastructure" ]
    } ]
  }, {
    "id" : "4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "name" : "account-stage",
    "description" : "Stage account configuration. The stage account hosts test environments prestage, performance, stage. This configuration configures services common to all these environments and regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "input" : [ {
      "name" : "account_id",
      "value" : "id of the stage account",
      "type" : "string"
    }, {
      "name" : "resource_group",
      "value" : "cross-environments",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "account:stage" ],
      "type" : "string"
    }, {
      "name" : "cis_name",
      "value" : "name of the CIS service to create",
      "type" : "string"
    }, {
      "name" : "cm_name",
      "value" : "name of the Certiticate Manager serice to create",
      "type" : "string"
    }, {
      "name" : "sm_name",
      "value" : "name of the Secrets Manager serice to create",
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "resource_group_id"
    }, {
      "name" : "cis_id"
    }, {
      "name" : "cm_id"
    }, {
      "name" : "sm_id"
    } ]
  }, {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group",
      "value" : "stage",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "env:stage" ],
      "type" : "string"
    }, {
      "name" : "logdna_name",
      "value" : "name of the LogDNA stage service instance",
      "type" : "string"
    }, {
      "name" : "sysdig_name",
      "value" : "name of the SysDig stage service instance",
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "resource_group_id"
    }, {
      "name" : "logdna_id"
    }, {
      "name" : "sysdig_id"
    } ]
  }, {
    "id" : "596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "name" : "region-us-south-stage",
    "description" : "Stage us-south configuration. There must be a blueprint configuring the VPC + ROKS stage us-south. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "schematics_blueprint",
    "labels" : [ "env:stage", "region:us-south", "governance:test", "build:0" ],
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group_id",
      "value" : "$configs[].name["env-stage"].output.resource_group_id",
      "type" : "string"
    }, {
      "name" : "logdna_id",
      "value" : "$configs[].name["env-stage"].output.logdna_id",
      "type" : "string"
    }, {
      "name" : "sysdig_id",
      "value" : "$configs[].name["env-stage"].output.sysdig_id",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "region:us-south" ],
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "vpc_id"
    }, {
      "name" : "roks_cluster_id"
    } ]
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "name" : "region-eu-de-stage",
    "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "schematics_blueprint",
    "labels" : [ "env:stage", "region:eu-de", "governance:test", "build:0" ],
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group_id",
      "value" : "$configs[].name["env-stage"].output.resource_group_id",
      "type" : "string"
    }, {
      "name" : "logdna_id",
      "value" : "$configs[].name["env-stage"].output.logdna_id",
      "type" : "string"
    }, {
      "name" : "sysdig_id",
      "value" : "$configs[].name["env-stage"].output.sysdig_id",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "region:eu-de" ],
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "vpc_id"
    }, {
      "name" : "roks_cluster_id"
    } ]
  } ]
}
```
{: screen}

## `ibmcloud project list`
{: #project-cli-list-command}

List existing projects. Projects are sorted by ID.
Note: If the `--all-pages` option is not set, the command only retrieves a single page of the collection.

```sh
ibmcloud project list [--start START] [--limit LIMIT] [--complete COMPLETE]
```


### Command options
{: #project-list-cli-options}

`--start` (string)
:   The pagination token determines which resource to start from on the next page. If not specified, the logical first page is returned.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/^\\S+$/`.

`--limit` (int64)
:   Determine the maximum number of resources to return. The number of resources that are returned is the same, with exception of the last page.

    The maximum value is `100`. The minimum value is `1`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for list.

### Example
{: #project-list-examples}

```sh
ibmcloud project list \
    --start=exampleString \
    --limit=10 \
    --complete=false
```
{: pre}

### Example output
{: #project-list-cli-output}

A projects list results example

```json
{
  "limit" : 10,
  "total_count" : 25,
  "first" : {
    "href" : "https://projects.test.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "start" : "start-here-for-next-page-dude"
  },
  "last" : {
    "href" : "https://projects.test.cloud.ibm.com/v1/projects/99999050-1234-ac97-0000-ba5a12fe0945"
  },
  "next" : {
    "href" : "https://projects.test.cloud.ibm.com/v1/projects/12349050-1234-ac97-0000-ba5a12fe9087"
  },
  "previous" : {
    "href" : "https://projects.test.cloud.ibm.com/v1/projects/12349000-6756-abcd-0000-ba5a12fe9087"
  },
  "projects" : [ {
    "description" : "a project example",
    "name" : "iaas-infra-prestage-env",
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "metadata" : {
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "location" : "us-south",
      "resource_group" : "Default",
      "state" : "READY",
      "cumulative_needs_attention_view" : [ {
        "event" : "project.instance.update"
      }, {
        "event_id" : "489f0090-6d7c-4af5-8f20-9106543e4974"
      }, {
        "config_id" : "069ab83e-5016-4bf2-bd50-cc95cf678293"
      }, {
        "config_version" : 1
      } ]
    }
  }, {
    "name" : "iaas-infra-stage-env",
    "id" : "1123ed42-4356-efa1-1101-235900fe9087",
    "metadata" : {
      "crn" : "crn:v1:staging:public:project:eu-de:a/06580d923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "location" : "eu-gb",
      "resource_group" : "Default",
      "state" : "UPDATING",
      "cumulative_needs_attention_view" : [ ]
    }
  } ]
}
```
{: screen}

## `ibmcloud project get`
{: #project-cli-get-command}

Retrieve a project by the ID.

```sh
ibmcloud project get --id ID [--exclude-configs EXCLUDE-CONFIGS] [--complete COMPLETE]
```


### Command options
{: #project-get-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--exclude-configs` (bool)
:   When the `exclude-configs` query parameter is set to `true` only active configurations are returned. No draft configurations are returned.

    The default value is `false`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

### Example
{: #project-get-examples}

```sh
ibmcloud project get \
    --id=exampleString \
    --exclude-configs=false \
    --complete=false
```
{: pre}

### Example output
{: #project-get-cli-output}

Sample response for retrieving a project.

```json
{
  "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
  "name" : "acme-microservice",
  "description" : "A microservice to deploy on top of ACME infrastructure.",
  "configs" : [ {
    "id" : "673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "name" : "common-variables",
    "type" : "terraform_template",
    "external_resources_account" : "e5ed08b9203bad3e4b6f57f0d1675a88",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "output" : [ {
      "name" : "tags",
      "value" : [ "project:ghost", "type:infrastructure" ]
    } ]
  }, {
    "id" : "4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "name" : "account-stage",
    "description" : "Stage account configuration. The stage account hosts test environments prestage, performance, stage. This configuration configures services common to all these environments and regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "input" : [ {
      "name" : "account_id",
      "value" : "ID of the stage account",
      "type" : "string"
    }, {
      "name" : "resource_group",
      "value" : "cross-environments",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "account:stage" ],
      "type" : "string"
    }, {
      "name" : "cis_name",
      "value" : "name of the CIS service to create",
      "type" : "string"
    }, {
      "name" : "cm_name",
      "value" : "name of the Certiticate Manager service to create",
      "type" : "string"
    }, {
      "name" : "sm_name",
      "value" : "name of the Secrets Manager service to create",
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "resource_group_id"
    }, {
      "name" : "cis_id"
    }, {
      "name" : "cm_id"
    }, {
      "name" : "sm_id"
    } ]
  }, {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group",
      "value" : "stage",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "env:stage" ],
      "type" : "string"
    }, {
      "name" : "logdna_name",
      "value" : "name of the LogDNA stage service instance",
      "type" : "string"
    }, {
      "name" : "sysdig_name",
      "value" : "name of the SysDig stage service instance",
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "resource_group_id"
    }, {
      "name" : "logdna_id"
    }, {
      "name" : "sysdig_id"
    } ]
  }, {
    "id" : "596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "name" : "region-us-south-stage",
    "description" : "Stage us-south configuration. There must be a blueprint configuring the VPC + ROKS stage us-south. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by Schematics Blueprint.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "schematics_blueprint",
    "labels" : [ "env:stage", "region:us-south", "governance:test", "build:0" ],
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group_id",
      "value" : "$configs[].name["env-stage"].output.resource_group_id",
      "type" : "string"
    }, {
      "name" : "logdna_id",
      "value" : "$configs[].name["env-stage"].output.logdna_id",
      "type" : "string"
    }, {
      "name" : "sysdig_id",
      "value" : "$configs[].name["env-stage"].output.sysdig_id",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "region:us-south" ],
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "vpc_id"
    }, {
      "name" : "roks_cluster_id"
    } ]
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "name" : "region-eu-de-stage",
    "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "schematics_blueprint",
    "labels" : [ "env:stage", "region:eu-de", "governance:test", "build:0" ],
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group_id",
      "value" : "$configs[].name["env-stage"].output.resource_group_id",
      "type" : "string"
    }, {
      "name" : "logdna_id",
      "value" : "$configs[].name["env-stage"].output.logdna_id",
      "type" : "string"
    }, {
      "name" : "sysdig_id",
      "value" : "$configs[].name["env-stage"].output.sysdig_id",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "region:eu-de" ],
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "vpc_id"
    }, {
      "name" : "roks_cluster_id"
    } ]
  } ],
  "metadata" : {
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "location" : "us-south",
    "resource_group" : "Default",
    "state" : "READY",
    "cumulative_needs_attention_view" : [ {
      "event" : "project.instance.update"
    }, {
      "event_id" : "489f0090-6d7c-4af5-8f20-9106543e4974"
    }, {
      "config_id" : "069ab83e-5016-4bf2-bd50-cc95cf678293"
    }, {
      "config_version" : 1
    } ],
    "event_notifications_crn" : "crn:v1:staging:public:event-notifications:us-south:a/06580c923e40314421d3b6cb40c01c68:instance-id::"
  }
}
```
{: screen}

## `ibmcloud project delete`
{: #project-cli-delete-command}

Delete a project by the ID.

```sh
ibmcloud project delete --id ID [--destroy DESTROY]
```


### Command options
{: #project-delete-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--destroy` (bool)
:   When the `destroy` parameter is set to `true`, the resources that were created by configurations within the project are destroyed.

    The default value is `false`.

### Example
{: #project-delete-examples}

```sh
ibmcloud project delete \
    --id=exampleString \
    --destroy=false
```
{: pre}

## `ibmcloud project config-create`
{: #project-cli-config-create-command}

Add a new configuration to a project.

```sh
ibmcloud project config-create --id ID --new-name NEW-NAME --new-locator-id NEW-LOCATOR-ID [--new-id NEW-ID] [--new-labels NEW-LABELS] [--new-description NEW-DESCRIPTION] [--new-input NEW-INPUT] [--new-setting NEW-SETTING]
```


### Command options
{: #project-config-create-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--name` (string)
:   The configuration name. Required.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--locator-id` (string)
:   The location ID of a project configuration manual property. Required.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[\\.0-9a-z-A-Z_-]+$/`.

`--labels` ([]string)
:   A collection of configuration labels.

    The list items must match regular expression `/^[_\\-a-z0-9:\/=]+$/`. The maximum length is `10000` items. The minimum length is `0` items.


`--description` (string)
:   A description for the new configuration.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--input` ([`InputVariableInput[]`](#cli-input-variable-input-example-schema))
:   The inputs of a Schematics template property.

    The maximum length is `10000` items. The minimum length is `0` items.

`--setting`
:   An optional setting object that is passed to the cart API.

    The maximum length is `10000` items. The minimum length is `0` items.

### Example
{: #project-config-create-examples}

```sh
ibmcloud project config-create \
    --id=exampleString \
    --new-name=env-stage \
    --new-locator-id=1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global \
    --new-id=exampleString \
    --new-labels=env:stage,governance:test,build:0 \
    --new-description='Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.' \
    --new-input='[{"name": "account_id"}]' \
    --new-setting='[{"name": "IBMCLOUD_TOOLCHAIN_ENDPOINT", "value": "https://api.us-south.devops.dev.cloud.ibm.com"}]'
```
{: pre}

### Example output
{: #project-config-create-cli-output}

Sample response for a project configuration

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project configs`
{: #project-cli-configs-command}


Lists all of the configurations within a specific project.

```sh
ibmcloud project configs --id ID [--version VERSION] [--complete COMPLETE]
```


### Command options
{: #project-configs-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--version` (string)
:   The version of configuration to return.

    The default value is `active`. Allowable values are: `active`, `draft`, `mixed`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

### Example
{: #project-configs-examples}

```sh
ibmcloud project configs \
    --id=exampleString \
    --version=active \
    --complete=false
```
{: pre}

### Example output
{: #project-configs-cli-output}

Sample response for get project configs

```json
{
  "configs" : [ {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group",
      "value" : "stage",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "env:stage" ],
      "type" : "string"
    }, {
      "name" : "logdna_name",
      "value" : "Name of the LogDNA stage service instance",
      "type" : "string"
    }, {
      "name" : "sysdig_name",
      "value" : "Name of the SysDig stage service instance",
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "resource_group_id"
    }, {
      "name" : "logdna_id"
    }, {
      "name" : "sysdig_id"
    } ]
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "name" : "region-eu-de-stage",
    "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint.",
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "schematics_blueprint",
    "labels" : [ "env:stage", "region:eu-de", "governance:test", "build:0" ],
    "input" : [ {
      "name" : "account_id",
      "value" : "$configs[].name["account-stage"].input.account_id",
      "type" : "string"
    }, {
      "name" : "resource_group_id",
      "value" : "$configs[].name["env-stage"].output.resource_group_id",
      "type" : "string"
    }, {
      "name" : "logdna_id",
      "value" : "$configs[].name["env-stage"].output.logdna_id",
      "type" : "string"
    }, {
      "name" : "sysdig_id",
      "value" : "$configs[].name["env-stage"].output.sysdig_id",
      "type" : "string"
    }, {
      "name" : "access_tags",
      "value" : [ "region:eu-de" ],
      "type" : "string"
    } ],
    "output" : [ {
      "name" : "vpc_id"
    }, {
      "name" : "roks_cluster_id"
    } ]
  } ]
}
```
{: screen}

## `ibmcloud project config-get`
{: #project-cli-config-get-command}

Returns a specific configuration within a project.

```sh
ibmcloud project config-get --id ID --config-id CONFIG-ID [--version VERSION] [--complete COMPLETE]
```


### Command options
{: #project-config-get-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--version` (string)
:   The version of the configuration to return.

    The default value is `active`. The maximum length is `10` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(active|draft|\\d+)$/`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

### Example
{: #project-config-get-examples}

```sh
ibmcloud project config-get \
    --id=exampleString \
    --config-id=exampleString \
    --version=active \
    --complete=false
```
{: pre}

### Example output
{: #project-config-get-cli-output}

Sample response for a project configuration

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project config-update`
{: #project-cli-config-update-command}

Update a configuration in a project by the ID.

```sh
ibmcloud project config-update --id ID --config-id CONFIG-ID --project-config PROJECT-CONFIG [--complete COMPLETE]
```


### Command options
{: #project-config-update-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--project-config` ([`JSONPatchOperation[]`](#cli-json-patch-operation-example-schema))
:   The change delta of the project configuration to update. Required.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

### Example
{: #project-config-update-examples}

```sh
ibmcloud project config-update \
    --id=exampleString \
    --config-id=exampleString \
    --project-config='[{"op": "add", "path": "exampleString", "from": "exampleString", "value": "exampleString"}]' \
    --complete=false
```
{: pre}

### Example output
{: #project-config-update-cli-output}

Sample response for a project configuration

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project config-delete`
{: #project-cli-config-delete-command}


Delete a configuration in a project.

```sh
ibmcloud project config-delete --id ID --config-id CONFIG-ID [--draft-only DRAFT-ONLY] [--destroy DESTROY]
```


### Command options
{: #project-config-delete-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--draft-only` (bool)
:   When `draft-only` is set to `true`, only the draft versions of a configuration are deleted.

    The default value is `false`.

`--destroy` (bool)
:   When the `destroy` parameter is set to `true`, the resources that were created by the configuration are destroyed.

    The default value is `false`.

### Example
{: #project-config-delete-examples}

```sh
ibmcloud project config-delete \
    --id=exampleString \
    --config-id=exampleString \
    --draft-only=false \
    --destroy=false
```
{: pre}

### Example output
{: #project-config-delete-cli-output}

An example of the delete configuration response.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage"
}
```
{: screen}

## `ibmcloud project config-check`
{: #project-cli-config-check-command}

Validates a configuration in a project. The validation includes creating or updating the associated schematics workspace with a plan job, running the Code Risk Analyzer scans, and cost estimatation.

```sh
ibmcloud project config-check --id ID --config-id CONFIG-ID [--x-auth-refresh-token X-AUTH-REFRESH-TOKEN] [--version VERSION] [--complete COMPLETE]
```


### Command options
{: #project-config-check-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration to validate. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--x-auth-refresh-token` (string)
:   The IAM refresh token.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--version` (string)
:   The version of the configuration to validate.

    The default value is `active`. The maximum length is `10` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(active|draft)$/`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.


### Example
{: #project-config-check-examples}

```sh
ibmcloud project config-check \
    --id=exampleString \
    --config-id=exampleString \
    --x-auth-refresh-token=exampleString \
    --version=active \
    --complete=false
```
{: pre}


### Example output
{: #project-config-check-cli-output}

Sample response for a project configuration

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project config-install`
{: #project-cli-config-install-command}

Deploy a configuration. It is an asynchronous operation that can be tracked using the project status API.

```sh
ibmcloud project config-install --id ID --config-id CONFIG-ID [--complete COMPLETE]
```


### Command options
{: #project-config-install-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration to install. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

### Example
{: #project-config-install-examples}

```sh
ibmcloud project config-install \
    --id=exampleString \
    --config-id=exampleString \
    --complete=false
```
{: pre}

### Example output
{: #project-config-install-cli-output}

Sample response for a project configuration

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project config-uninstall`
{: #project-cli-config-uninstall-command}


Destroy all of the resources that were created by a configuration. You can track it by using the project status API.

```sh
ibmcloud project config-uninstall --id ID --config-id CONFIG-ID
```


### Command options
{: #project-config-uninstall-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration to destroy configuration resources. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-uninstall-examples}

```sh
ibmcloud project config-uninstall \
    --id=exampleString \
    --config-id=exampleString
```
{: pre}

## `ibmcloud project config-merge`
{: #project-cli-config-merge-approve-command}

Approve changes to a draft configuration.

```sh
ibmcloud project config-merge --id ID --config-id CONFIG-ID [--complete COMPLETE]
```

### Command options
{: #project-config-merge-approve-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration to install. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--complete` (bool)
:   When the `complete` query parameter is set to `true`, the full metadata is returned.

    The default value is `false`.

`--comment` (string)
:   Add a comment to the approved changes. Required.

### Example
{: #project-config-merge-approve-examples}

```sh
ibmcloud project config-merge \
    --id=exampleString \
    --config-id=exampleString \
    --comment=`Approving the changes` \
    --complete=false
```
{: pre}

### Example output
{: #project-config-merge-approve-cli-output}

Sample response for a project configuration merge

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage",
  "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
  "labels" : [ "env:stage", "governance:test", "build:0" ],
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "type" : "terraform_template",
  "input" : [ {
    "name" : "account_id",
    "value" : "$configs[].name["account-stage"].input.account_id",
    "type" : "string"
  }, {
    "name" : "resource_group",
    "value" : "stage",
    "type" : "string"
  }, {
    "name" : "access_tags",
    "value" : [ "env:stage" ],
    "type" : "string"
  }, {
    "name" : "logdna_name",
    "value" : "name of the LogDNA stage service instance",
    "type" : "string"
  }, {
    "name" : "sysdig_name",
    "value" : "name of the SysDig stage service instance",
    "type" : "string"
  } ],
  "output" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ]
}
```
{: screen}

## `ibmcloud project config-discard`
{: #project-cli-config-discard-changes-command}


Discard changes to a configuration.

```sh
ibmcloud project config-discard --id ID --config-id CONFIG-ID [--complete COMPLETE]
```

### Command options
{: #project-config-discard-changes-cli-options}

`--id` (string)
:   The ID of the project, which uniquely identifies it. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The ID of the configuration to install. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-discard-changes-examples}

```sh
ibmcloud project config-discard \
    --id=exampleString \
    --config-id=exampleString
```
{: pre}

### Example output
{: #project-config-discard-changes-cli-output}

Sample response for a project configuration discard

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "name" : "env-stage"
}
```
{: screen}


## Other relevant commands for {{site.data.keyword.cloud_notm}} projects
{: #project-relevant-commands-other}

The following commands are not a part of the projects CLI plug-in, but you can use them to complete project-related tasks, such as attaching tags to a project. This list is not exhaustive of all of the relevant commands that are available to use with projects. Rather, this list is a starting point for you to explore other commands that you can use with projects.

Some of the following commands might require the installation of their specific plug-ins before you can run them.
{: important}

Run [`ibmcloud resource tag-attach`](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_tag_attach) to attach tags to a project:

```sh
ibmcloud resource tag-attach --tag-names TAG --resource-id PROJECT-CRN
```

Run [`ibmcloud resource search`](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_search) to retrieve all of the resources in an account created by configurations in a project: {: #ibmcloud-resource-tag-search}

```sh
ibmcloud resource search "service_tags:\"schematics::project_id:PROJECT_ID\""
```

Run [`ibmcloud schematics logs`](/docs/cli?topic=cli-schematics-cli-reference#schematics-logs) to retrieve the log files for a {{site.data.keyword.bpshort}} workspace:

```sh
ibmcloud schematics logs --id WORKSPACE_ID [--act-id ACTION_ID]
```

## Schema examples
{: #project-schema-examples}

The following schema examples represent the data that you need to specify for a command option. These examples model the data structure and include placeholder values for the expected value type. When you run a command, replace these values with the values that apply to your environment.

### ProjectConfigInputVariable[]
{: #cli-project-config-input-variable-example-schema}

The following example shows the format of the `InputVariableInput[]` object.

```json

[ {
  "name" : "account_id"
} ]
```
{: codeblock}


### JSONPatchOperation[]
{: #cli-json-patch-operation-example-schema}

The following example shows the format of the `JSONPatchOperation[]` object.

```json

[ {
  "op" : "add",
  "path" : "exampleString",
  "from" : "exampleString",
  "value" : "exampleString"
} ]
```
{: codeblock}

### ProjectConfigInput[]
{: #cli-project-config-input-example-schema}

The following example shows the format of the `ProjectConfigInput[]` object.

```json

[ {
  "id" : "exampleString",
  "name" : "common-variables",
  "labels" : [ "exampleString" ],
  "description" : "exampleString",
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "input" : [ {
    "name" : "exampleString"
  } ],
  "setting" : [ {
    "name" : "exampleString",
    "value" : "exampleString"
  } ]
} ]
```
{: codeblock}

### ProjectConfigSettingCollection[]
{: #cli-project-config-setting-collection-example-schema}

The following example shows the format of the ProjectConfigSettingCollection[] object.

```json

[ {
  "name" : "IBMCLOUD_TOOLCHAIN_ENDPOINT",
  "value" : "https://api.us-south.devops.dev.cloud.ibm.com"
} ]
```
{: codeblock}
