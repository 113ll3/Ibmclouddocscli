---

copyright:
  years: 2023
lastupdated: "2023-11-20"

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
ibmcloud project create [--definition DEFINITION] --location LOCATION --resource-group RESOURCE-GROUP [--configs CONFIGS]
```

### Command options
{: #project-create-cli-options}

`--definition` ([`ProjectPrototypeDefinition`](#cli-project-prototype-definition-example-schema))
:   The definition of the project. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--location` (string)
:   The IBM Cloud location where a resource is deployed. Required.

    The maximum length is `12` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(us-south|us-east|eu-gb|eu-de)$/`.

`--resource-group` (string)
:   The resource group name where the project's data and tools are created. Required.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]*$/`.

`--configs` ([`ProjectConfigPrototype[]`](#cli-project-config-prototype-example-schema))
:   The project configurations. These configurations are only included in the response of creating a project if a configs array is specified in the request payload.

    The default value is `[]`. The maximum length is `100` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--configs=@path/to/file.json`.

`--definition-name` (string)
:   The name of the project. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--definition-description` (string)
:   A brief explanation of the project's use in the configuration of a deployable architecture. It is possible to create a project without providing a description. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-destroy-on-delete` (bool)
:   The policy that indicates whether the resources are destroyed or not when a project is deleted. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The default value is `true`.

### Example
{: #project-create-examples}

```sh
ibmcloud project create \
    --definition '{"name": "acme-microservice", "description": "A microservice to deploy on top of ACME infrastructure.", "destroy_on_delete": true}' \
    --location us-south \
    --resource-group Default \
    --configs '[{"definition": {"name": "exampleString", "description": "exampleString", "environment": "exampleString", "authorizations": {"trusted_profile_id": "exampleString", "method": "api_key", "api_key": "exampleString"}, "compliance_profile": {"id": "exampleString", "instance_id": "exampleString", "instance_location": "exampleString", "attachment_id": "exampleString", "profile_name": "exampleString"}, "locator_id": "exampleString", "inputs": {}, "settings": {}}, "schematics": {"workspace_crn": "exampleString"}}]'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project create \
    --location us-south \
    --resource-group Default \
    --configs projectConfigPrototype \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-destroy-on-delete true
```
{: pre}

## `ibmcloud project list`
{: #project-cli-list-command}

List existing projects. Projects are sorted by ID.
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud project list [--start START] [--limit LIMIT]
```

### Command options
{: #project-list-cli-options}

`--start` (string)
:   Marks the last entry that is returned on the page. The server uses this parameter to determine the first entry that is returned on the next page. If this parameter is not specified, the logical first page is returned.

    The default value is ``. The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^\\S*$/`.

`--limit` (int64)
:   Determine the maximum number of resources to return. The number of resources that are returned is the same, with the exception of the last page.

    The default value is `10`. The maximum value is `100`. The minimum value is `1`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for list.

### Example
{: #project-list-examples}

```sh
ibmcloud project list \
    --start=exampleString \
    --limit=10
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
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "start" : "start-here-for-next-page-dude"
  },
  "last" : {
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/99999050-1234-ac97-0000-ba5a12fe0945"
  },
  "next" : {
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/12349050-1234-ac97-0000-ba5a12fe9087"
  },
  "previous" : {
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/12349000-6756-abcd-0000-ba5a12fe9087"
  },
  "projects" : [ {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "description" : "a project example",
      "name" : "iaas-infra-prestage-env",
      "destroy_on_delete" : false
    },
    "location" : "us-south",
    "state" : "ready",
    "resource_group" : "Default",
    "resource_group_id" : "f37d2637ea814cfd9a1742683a713d24",
    "cumulative_needs_attention_view" : [ {
      "event" : "project.instance.update"
    }, {
      "event_id" : "489f0090-6d7c-4af5-8f20-9106543e4974"
    }, {
      "config_id" : "069ab83e-5016-4bf2-bd50-cc95cf678293"
    }, {
      "config_version" : 1
    } ]
  }, {
    "id" : "1123ed42-4356-efa1-1101-235900fe9087",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "description" : "a project example",
      "name" : "iaas-infra-stage-env",
      "destroy_on_delete" : false
    },
    "crn" : "crn:v1:staging:public:project:eu-de:a/06580d923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "location" : "eu-gb",
    "state" : "ready",
    "resource_group" : "Default",
    "resource_group_id" : "f37d2637ea814cfd9a1742683a713d24",
    "cumulative_needs_attention_view" : [ ]
  } ]
}
```
{: screen}

## `ibmcloud project get`
{: #project-cli-get-command}

Get information about a project.

```sh
ibmcloud project get --id ID
```

### Command options
{: #project-get-cli-options}

`--id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-get-examples}

```sh
ibmcloud project get \
    --id=exampleString
```
{: pre}

### Example output
{: #project-get-cli-output}

Sample response for retrieving a project.

```json
{
  "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z",
  "definition" : {
    "name" : "acme-microservice",
    "description" : "A microservice to deploy on top of ACME infrastructure.",
    "destroy_on_delete" : true
  },
  "configs" : [ {
    "id" : "673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "common-variables"
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "update_available" : false,
    "version" : 1
  }, {
    "id" : "4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "account-stage",
      "description" : "Stage account configuration. The stage account hosts test environments prestage, performance, stage. This configuration configures services common to all these environments and regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "env-stage",
      "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/293c3c36-a094-4115-a12b-de0a9ca39be5",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "region-us-south-stage",
      "description" : "Stage us-south configuration. There must be a blueprint configuring the VPC + ROKS stage us-south. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by Schematics Blueprint."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "region-eu-de-stage",
      "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  } ],
  "environments" : [ {
    "id" : "b0c44146-1ef6-40c2-82ba-74d51149770a",
    "definition" : {
      "name" : "dev-environment",
      "description" : "Dev environment"
    },
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "created_at" : "2023-02-10T10:05:35.787Z",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/environments/b0c44146-1ef6-40c2-82ba-74d51149770a"
  } ],
  "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
  "cumulative_needs_attention_view" : [ {
    "event" : "project.instance.update"
  }, {
    "event_id" : "489f0090-6d7c-4af5-8f20-9106543e4974"
  }, {
    "config_id" : "069ab83e-5016-4bf2-bd50-cc95cf678293"
  }, {
    "config_version" : 1
  } ],
  "event_notifications_crn" : "crn:v1:staging:public:event-notifications:us-south:a/06580c923e40314421d3b6cb40c01c68:instance-id::",
  "location" : "us-south",
  "resource_group" : "Default",
  "state" : "ready"
}
```
{: screen}

## `ibmcloud project update`
{: #project-cli-update-command}

Update a project by the ID.

```sh
ibmcloud project update --id ID [--definition DEFINITION]
```

### Command options
{: #project-update-cli-options}

`--id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition` ([`ProjectPatchDefinitionBlock`](#cli-project-patch-definition-block-example-schema))
:   The definition of the project. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--definition-name` (string)
:   The name of the project. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--definition-description` (string)
:   A brief explanation of the project's use in the configuration of a deployable architecture. It is possible to create a project without providing a description. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-destroy-on-delete` (bool)
:   The policy that indicates whether the resources are destroyed or not when a project is deleted. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

### Examples
{: #project-update-examples}

```sh
ibmcloud project update \
    --id exampleString \
    --definition '{"name": "acme-microservice", "description": "A microservice to deploy on top of ACME infrastructure.", "destroy_on_delete": true}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project update \
    --id exampleString \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-destroy-on-delete true
```
{: pre}

### Example output
{: #project-update-cli-output}

Sample response for retrieving a project with configurations.

```json
{
  "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z",
  "definition" : {
    "name" : "acme-microservice",
    "description" : "A microservice to deploy on top of ACME infrastructure.",
    "destroy_on_delete" : true
  },
  "configs" : [ {
    "id" : "673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "common-variables"
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/673d79e4-52bf-4184-b8e9-d3ca3c110f96",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "update_available" : false,
    "version" : 1
  }, {
    "id" : "4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "account-stage",
      "description" : "Stage account configuration. The stage account hosts test environments prestage, performance, stage. This configuration configures services common to all these environments and regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/4a1d4ba2-54ba-43a7-975a-d82b5a7612d1",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "env-stage",
      "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/293c3c36-a094-4115-a12b-de0a9ca39be5",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "region-us-south-stage",
      "description" : "Stage us-south configuration. There must be a blueprint configuring the VPC + ROKS stage us-south. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by Schematics Blueprint."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/596e8656-9d4b-41a5-8340-b0cbe8bd374a",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "definition" : {
      "name" : "region-eu-de-stage",
      "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint."
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "is_draft" : true,
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "state" : "draft",
    "update_available" : false,
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "version" : 1
  } ],
  "environments" : [ {
    "id" : "b0c44146-1ef6-40c2-82ba-74d51149770a",
    "definition" : {
      "name" : "dev-environment",
      "description" : "Dev environment"
    },
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "created_at" : "2023-02-10T10:05:35.787Z",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a/environments/b0c44146-1ef6-40c2-82ba-74d51149770a"
  } ],
  "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
  "cumulative_needs_attention_view" : [ {
    "event" : "project.instance.update"
  }, {
    "event_id" : "489f0090-6d7c-4af5-8f20-9106543e4974"
  }, {
    "config_id" : "069ab83e-5016-4bf2-bd50-cc95cf678293"
  }, {
    "config_version" : 1
  } ],
  "event_notifications_crn" : "crn:v1:staging:public:event-notifications:us-south:a/06580c923e40314421d3b6cb40c01c68:instance-id::",
  "location" : "us-south",
  "resource_group" : "Default",
  "resource_group_id" : "f37d2637ea814cfd9a1742683a713d24",
  "state" : "ready"
}
```
{: screen}

## `ibmcloud project delete`
{: #project-cli-delete-command}

Delete a project document by the ID. A project can only be deleted after deleting all of its resources.

```sh
ibmcloud project delete --id ID
```

### Command options
{: #project-delete-cli-options}

`--id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-delete-examples}

```sh
ibmcloud project delete \
    --id=exampleString
```
{: pre}

## `ibmcloud project environment-create`
{: #project-cli-environment-create-command}

Create an environment.

```sh
ibmcloud project environment-create --project-id PROJECT-ID [--definition DEFINITION]
```

### Command options
{: #project-environment-create-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition` ([`EnvironmentDefinitionRequiredProperties`](#cli-environment-definition-required-properties-example-schema))
:   The environment definition. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--definition-name` (string)
:   The name of the environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--definition-description` (string)
:   The description of the environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-authorizations` ([`ProjectConfigAuth`](#cli-project-config-auth-example-schema))
:   The authorization details. You can authorize by using a trusted profile or an API key in Secrets Manager. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-authorizations=@path/to/file.json`.

`--definition-inputs` ([`InputVariable`](#cli-input-variable-example-schema))
:   The input variables for configuration definition and environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-inputs=@path/to/file.json`.

`--definition-compliance-profile` ([`ProjectComplianceProfile`](#cli-project-compliance-profile-example-schema))
:   The profile required for compliance. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-compliance-profile=@path/to/file.json`.

### Examples
{: #project-environment-create-examples}

```sh
ibmcloud project environment-create \
    --project-id exampleString \
    --definition '{"name": "development", "description": "The environment \'development\'", "authorizations": {"trusted_profile_id": "exampleString", "method": "api_key", "api_key": "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"}, "inputs": {}, "compliance_profile": {"id": "some-profile-id", "instance_id": "some-instance-id", "instance_location": "us-south", "attachment_id": "some-attachment-id", "profile_name": "some-profile-name"}}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project environment-create \
    --project-id exampleString \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-authorizations projectConfigAuth \
    --definition-inputs inputVariable \
    --definition-compliance-profile projectComplianceProfile
```
{: pre}

### Example output
{: #project-environment-create-cli-output}

Sample environment response.

```json
{
  "id" : "env123",
  "definition" : {
    "name" : "development",
    "description" : "The environment 'development'",
    "authorizations" : {
      "method" : "api_key",
      "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
    },
    "inputs" : {
      "resource_group" : "stage",
      "region" : "us-south"
    },
    "compliance_profile" : {
      "id" : "some-profile-id",
      "instance_id" : "some-instance-id",
      "instance_location" : "us-south",
      "profile_name" : "some-profile-name",
      "attachment_id" : "some-attachment-id"
    }
  },
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "created_at" : "2023-06-29T03:28:14.709Z",
  "modified_at" : "2023-06-29T03:28:14.709Z"
}
```
{: screen}

## `ibmcloud project environments`
{: #project-cli-environments-command}

Returns all environments.

```sh
ibmcloud project environments --project-id PROJECT-ID
```

### Command options
{: #project-environments-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-project-environments-examples}

```sh
ibmcloud project environments \
    --project-id exampleString
```
{: pre}

### Example output
{: #project-environments-cli-output}

Sample environment response for a list.

```json
{
  "environments" : [ {
    "id" : "env123",
    "definition" : {
      "name" : "development",
      "description" : "The environment 'development'",
      "authorizations" : {
        "method" : "api_key",
        "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
      },
      "inputs" : {
        "resource_group" : "stage",
        "region" : "us-south"
      },
      "compliance_profile" : {
        "id" : "some-profile-id",
        "instance_id" : "some-instance-id",
        "instance_location" : "us-south",
        "profile_name" : "some-profile-name",
        "attachment_id" : "some-attachment-id"
      }
    },
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "created_at" : "2023-06-29T03:28:14.709Z",
    "modified_at" : "2023-06-29T03:28:14.709Z"
  } ]
}
```
{: screen}

## `ibmcloud project environment`
{: #project-cli-project-environment-command}

Returns an environment.

```sh
ibmcloud project environment --project-id PROJECT-ID --id ID
```


### Command options
{: #project-environment-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The environment ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$).+$/`.

### Example
{: #project-project-environment-examples}

```sh
ibmcloud project environment \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-environment-cli-output}

Sample environment response.

```json
{
  "id" : "env123",
  "definition" : {
    "name" : "development",
    "description" : "The environment 'development'",
    "authorizations" : {
      "method" : "api_key",
      "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
    },
    "inputs" : {
      "resource_group" : "stage",
      "region" : "us-south"
    },
    "compliance_profile" : {
      "id" : "some-profile-id",
      "instance_id" : "some-instance-id",
      "instance_location" : "us-south",
      "profile_name" : "some-profile-name",
      "attachment_id" : "some-attachment-id"
    }
  },
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "created_at" : "2023-06-29T03:28:14.709Z",
  "modified_at" : "2023-06-29T03:28:14.709Z"
}
```
{: screen}

## `ibmcloud project environment-update`
{: #project-cli-environment-update-command}

Update an environment by the ID.

```sh
ibmcloud project environment-update --project-id PROJECT-ID --id ID [--definition DEFINITION]
```

### Command options
{: #project-environment-update-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The environment ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$).+$/`.

`--definition` ([`EnvironmentDefinitionProperties`](#cli-environment-definition-properties-example-schema))
:   The environment definition used for updates. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--definition-name` (string)
:   The name of the environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[^'"`<>{}\\x00-\\x1F]+$/`.

`--definition-description` (string)
:   The description of the environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-authorizations` ([`ProjectConfigAuth`](#cli-project-config-auth-example-schema))
:   The authorization details. You can authorize by using a trusted profile or an API key in Secrets Manager. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-authorizations=@path/to/file.json`.

`--definition-inputs` ([`InputVariable`](#cli-input-variable-example-schema))
:   The input variables for configuration definition and environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-inputs=@path/to/file.json`.

`--definition-compliance-profile` ([`ProjectComplianceProfile`](#cli-project-compliance-profile-example-schema))
:   The profile required for compliance. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-compliance-profile=@path/to/file.json`.

### Examples
{: #project-environment-update-examples}

```sh
ibmcloud project environment-update \
    --project-id exampleString \
    --id exampleString \
    --definition '{"name": "development", "description": "The environment \'development\'", "authorizations": {"trusted_profile_id": "exampleString", "method": "api_key", "api_key": "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"}, "inputs": {}, "compliance_profile": {"id": "some-profile-id", "instance_id": "some-instance-id", "instance_location": "us-south", "attachment_id": "some-attachment-id", "profile_name": "some-profile-name"}}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project environment-update \
    --project-id exampleString \
    --id exampleString \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-authorizations projectConfigAuth \
    --definition-inputs inputVariable \
    --definition-compliance-profile projectComplianceProfile
```
{: pre}

### Example output
{: #project-environment-update-cli-output}

Sample environment response.

```json
{
  "id" : "env123",
  "definition" : {
    "name" : "development",
    "description" : "The environment 'development'",
    "authorizations" : {
      "method" : "api_key",
      "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
    },
    "inputs" : {
      "resource_group" : "stage",
      "region" : "us-south"
    },
    "compliance_profile" : {
      "id" : "some-profile-id",
      "instance_id" : "some-instance-id",
      "instance_location" : "us-south",
      "profile_name" : "some-profile-name",
      "attachment_id" : "some-attachment-id"
    }
  },
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "created_at" : "2023-06-29T03:28:14.709Z",
  "modified_at" : "2023-06-29T03:28:14.709Z"
}
```
{: screen}

## `ibmcloud project environment-delete`
{: #project-cli-environment-delete-command}

Delete an environment in a project by ID.

```sh
ibmcloud project environment-delete --project-id PROJECT-ID --id ID
```

### Command options
{: #project-environment-delete-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The environment ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$).+$/`.

### Example
{: #project-environment-delete-examples}

```sh
ibmcloud project environment-delete \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-environment-delete-cli-output}

Sample environment delete response.

```json
{
  "id" : "env123"
}
```
{: screen}


## `ibmcloud project config-create`
{: #project-cli-config-create-command}

Add a new configuration to a project.

```sh
ibmcloud project config-create --project-id PROJECT-ID [--definition DEFINITION] [--schematics SCHEMATICS]
```

### Command options
{: #project-config-create-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition` ([`ProjectConfigPrototypeDefinitionBlock`](#cli-project-config-prototype-definition-block-example-schema))
:   The name and description of a project configuration. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--schematics` ([`SchematicsWorkspace`](#cli-schematics-workspace-example-schema))
:   A schematics workspace associated to a project configuration. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--schematics=@path/to/file.json`.

`--definition-name` (string)
:   The configuration name. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9][a-zA-Z0-9-_ ]*$/`.

`--definition-description` (string)
:   A project configuration description. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-environment` (string)
:   The ID of the project environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition-authorizations` ([`ProjectConfigAuth`](#cli-project-config-auth-example-schema))
:   The authorization details. You can authorize by using a trusted profile or an API key in Secrets Manager. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-authorizations=@path/to/file.json`.

`--definition-compliance-profile` ([`ProjectComplianceProfile`](#cli-project-compliance-profile-example-schema))
:   The profile required for compliance. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-compliance-profile=@path/to/file.json`.

`--definition-locator-id` (string)
:   A dotted value of catalogID.versionID. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[\\.0-9a-z-A-Z_-]+$/`.

`--definition-inputs` ([`InputVariable`](#cli-input-variable-example-schema))
:   The input variables for configuration definition and environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-inputs=@path/to/file.json`.

`--definition-settings` ([`ProjectConfigSetting`](#cli-project-config-setting-example-schema))
:   Schematics environment variables to use to deploy the configuration.
Settings are only available if they were specified when the configuration was initially created. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-settings=@path/to/file.json`.

`--schematics-workspace-crn` (string)
:   An existing schematics workspace CRN. This option provides a value for a sub-field of the JSON option 'schematics'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `4` characters. The value must match regular expression `/^crn:v[0-9](:([A-Za-z0-9\\-._~!$&'()*+,;=@\/]|%[0-9A-Z]{2})*){8}$/`.

### Example
{: #project-config-create-examples}

```sh
ibmcloud project config-create \
    --project-id exampleString \
    --definition '{"name": "env-stage", "description": "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.", "environment": "exampleString", "authorizations": {"trusted_profile_id": "exampleString", "method": "api_key", "api_key": "exampleString"}, "compliance_profile": {"id": "exampleString", "instance_id": "exampleString", "instance_location": "exampleString", "attachment_id": "exampleString", "profile_name": "exampleString"}, "locator_id": "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global", "inputs": {}, "settings": {}}' \
    --schematics '{"workspace_crn": "exampleString"}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project config-create \
    --project-id exampleString \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-environment exampleString \
    --definition-authorizations projectConfigAuth \
    --definition-compliance-profile projectComplianceProfile \
    --definition-locator-id exampleString \
    --definition-inputs inputVariable \
    --definition-settings projectConfigSetting \
    --schematics-workspace-crn exampleString
```
{: pre}

### Example output
{: #project-config-create-cli-output}

Sample response for a project configuration draft.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project configs`
{: #project-cli-configs-command}

The collection of configurations that are returned.

```sh
ibmcloud project configs --project-id PROJECT-ID
```

### Command options
{: #project-configs-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-configs-examples}

```sh
ibmcloud project configs \
    --project-id=exampleString
```
{: pre}

### Example output
{: #project-configs-cli-output}

Sample response for get project configurations.

```json
{
  "configs" : [ {
    "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
    "definition" : {
      "name" : "env-stage",
      "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace."
    },
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "version" : 1,
    "state" : "validated",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/293c3c36-a094-4115-a12b-de0a9ca39be5"
  }, {
    "id" : "9c7afed6-17fb-4c56-a13d-440a78f936bd",
    "definition" : {
      "name" : "region-eu-de-stage",
      "description" : "Stage eu-de configuration. There must be a blueprint configuring the VPC + ROKS stage eu-de. It is a schematics_blueprint type of configuration that points to a Github repo hosting a Schematics Blueprint that can be deployed by a Schematics Blueprint."
    },
    "approved_version" : {
      "version" : 1,
      "state" : "approved",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd/versions/1"
    },
    "project" : {
      "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
      "definition" : {
        "name" : "iaas-infra-prestage-env"
      },
      "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
      "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
    },
    "version" : 2,
    "state" : "draft",
    "created_at" : "2023-02-22T19:51:23.253Z",
    "modified_at" : "2023-02-22T19:51:23.253Z",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd"
  } ]
}
```
{: screen}

## `ibmcloud project config`
{: #project-cli-config-command}

Returns the specified project configuration in a specific project.

```sh
ibmcloud project config --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-examples}

```sh
ibmcloud project config \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-cli-output}

Sample response for a project configuration.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of config that points to a github repo hosting the terraform modules that can be deployed via Schematics Workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "approved_version" : {
    "version" : 1,
    "needs_attention_state" : [ {
      "event" : "check.pipeline.failed",
      "severity" : "ERROR",
      "event_id" : "baa1e163-4323-4982-866f-6afdfc7ff17d",
      "action_url" : "https://action/url",
      "timestamp" : "2023-07-26T17:21:15.231Z"
    } ],
    "state" : "approved",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd/versions/1"
  },
  "deployed_version" : {
    "version" : 1,
    "needs_attention_state" : [ {
      "event" : "check.pipeline.failed",
      "severity" : "ERROR",
      "event_id" : "baa1e163-4323-4982-866f-6afdfc7ff17d",
      "action_url" : "https://action/url",
      "timestamp" : "2023-07-26T17:21:15.231Z"
    } ],
    "state" : "deployed",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/9c7afed6-17fb-4c56-a13d-440a78f936bd/versions/1"
  },
  "last_validated" : {
    "cost_estimate" : { },
    "cra_logs" : { },
    "job" : {
      "id" : "ba98208b61efa490153b72adfd672251",
      "summary" : {
        "plan_summary" : { },
        "apply_summary" : { },
        "destroy_summary" : { },
        "message_summary" : { },
        "plan_messages" : { },
        "apply_messages" : { },
        "destroy_messages" : { }
      }
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/606bdec6-3b18-4c5e-9cf5-64ff228ab4f6/configs/ac0f34f7-1efc-408c-8a7f-eaa2c9d2bb64/versions/1/last_validated",
    "result" : "passed"
  },
  "last_deployed" : {
    "job" : {
      "id" : "c646f6bd5921e5a56656818cc4a22bea",
      "summary" : {
        "plan_summary" : { },
        "apply_summary" : { },
        "destroy_summary" : { },
        "message_summary" : { },
        "plan_messages" : { },
        "apply_messages" : { },
        "destroy_messages" : { }
      }
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/606bdec6-3b18-4c5e-9cf5-64ff228ab4f6/configs/ac0f34f7-1efc-408c-8a7f-eaa2c9d2bb64/versions/1/last_deployed",
    "result" : "passed"
  },
  "last_undeployed" : {
    "job" : {
      "id" : "55ced596251e5fcfe86814d189da035e",
      "summary" : {
        "plan_summary" : { },
        "apply_summary" : { },
        "destroy_summary" : { },
        "message_summary" : { },
        "plan_messages" : { },
        "apply_messages" : { },
        "destroy_messages" : { }
      }
    },
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/606bdec6-3b18-4c5e-9cf5-64ff228ab4f6/configs/ac0f34f7-1efc-408c-8a7f-eaa2c9d2bb64/versions/1/last_undeployed",
    "result" : "failed"
  },
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "version" : 2,
  "is_draft" : true,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "draft",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-update`
{: #project-cli-config-update-command}

Update a configuration in a project by the ID.

```sh
ibmcloud project config-update --project-id PROJECT-ID --id ID [--definition DEFINITION]
```

### Command options
{: #project-config-update-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition` ([`ProjectConfigPatchDefinitionBlock`](#cli-project-config-patch-definition-block-example-schema))
:   The name and description of a project configuration. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition=@path/to/file.json`.

`--definition-name` (string)
:   The configuration name. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9][a-zA-Z0-9-_ ]*$/`.

`--definition-description` (string)
:   A project configuration description. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/^$|^(?!\\s).*\\S$/`.

`--definition-environment` (string)
:   The ID of the project environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--definition-authorizations` ([`ProjectConfigAuth`](#cli-project-config-auth-example-schema))
:   The authorization details. You can authorize by using a trusted profile or an API key in Secrets Manager. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-authorizations=@path/to/file.json`.

`--definition-compliance-profile` ([`ProjectComplianceProfile`](#cli-project-compliance-profile-example-schema))
:   The profile required for compliance. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-compliance-profile=@path/to/file.json`.

`--definition-locator-id` (string)
:   A dotted value of catalogID.versionID. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(?!.*\\s$)[\\.0-9a-z-A-Z_-]+$/`.

`--definition-inputs` ([`InputVariable`](#cli-input-variable-example-schema))
:   The input variables for configuration definition and environment. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-inputs=@path/to/file.json`.

`--definition-settings` ([`ProjectConfigSetting`](#cli-project-config-setting-example-schema))
:   Schematics environment variables to use to deploy the configuration.
Settings are only available if they were specified when the configuration was initially created. This option provides a value for a sub-field of the JSON option 'definition'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--definition-settings=@path/to/file.json`.

### Example
{: #project-config-update-examples}

```sh
ibmcloud project config-update \
    --project-id exampleString \
    --id exampleString \
    --definition '{"name": "exampleString", "description": "exampleString", "environment": "exampleString", "authorizations": {"trusted_profile_id": "exampleString", "method": "api_key", "api_key": "exampleString"}, "compliance_profile": {"id": "exampleString", "instance_id": "exampleString", "instance_location": "exampleString", "attachment_id": "exampleString", "profile_name": "exampleString"}, "locator_id": "exampleString", "inputs": {}, "settings": {}}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project config-update \
    --project-id exampleString \
    --id exampleString \
    --definition-name exampleString \
    --definition-description exampleString \
    --definition-environment exampleString \
    --definition-authorizations projectConfigAuth \
    --definition-compliance-profile projectComplianceProfile \
    --definition-locator-id exampleString \
    --definition-inputs inputVariable \
    --definition-settings projectConfigSetting
```
{: pre}

### Example output
{: #project-config-update-cli-output}

Sample response for a project configuration draft.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-delete`
{: #project-cli-config-delete-command}

Delete a configuration in a project. Deleting the configuration will also destroy all the resources deployed by the configuration if the query parameter `destroy` is specified.

```sh
ibmcloud project config-delete --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-delete-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-delete-examples}

```sh
ibmcloud project config-delete \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-delete-cli-output}

An example of the delete configuration response.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5"
}
```
{: screen}

## `ibmcloud project config-force-approve`
{: #project-cli-config-force-approve-command}

Force approve configuration edits to the main configuration with an approving comment.

```sh
ibmcloud project config-force-approve --project-id PROJECT-ID --id ID [--comment COMMENT]
```

### Command options
{: #project-config-force-approve-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--comment` (string)
:   Notes on the project draft action. If this is a forced approve on the draft configuration, a non-empty comment is required.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(.|\\n|\\r)+\\S+$/`.

### Example
{: #project-config-force-approve-examples}

```sh
ibmcloud project config-force-approve \
    --project-id exampleString \
    --id exampleString \
    --comment 'Approving the changes'
```
{: pre}

### Example output
{: #project-config-force-approve-cli-output}

Sample response for a project configuration draft.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-approve`
{: #project-cli-config-approve-command}

Approve and merge configuration edits to the main configuration.

```sh
ibmcloud project config-approve --project-id PROJECT-ID --id ID [--comment COMMENT]
```

### Command options
{: #project-config-approve-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--comment` (string)
:   Notes on the project draft action. If this is a forced approve on the draft configuration, a non-empty comment is required.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^(?!\\s)(.|\\n|\\r)+\\S+$/`.

### Example
{: #project-config-approve-examples}

```sh
ibmcloud project config-approve \
    --project-id exampleString \
    --id exampleString \
    --comment 'Approving the changes'
```
{: pre}

### Example output
{: #project-config-approve-cli-output}

Sample response for a project configuration.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-validate`
{: #project-cli-config-validate-command}

Run a validation check on a given configuration in project. The check includes creating or updating the associated schematics workspace with a plan job, running the CRA scans, and cost estimatation.

```sh
ibmcloud project config-validate --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-validate-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-validate-examples}

```sh
ibmcloud project config-validate \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-validate-cli-output}

Sample response for a project configuration.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-deploy`
{: #project-cli-config-deploy-command}

Deploy a project's configuration. It's an asynchronous operation that can be tracked using the get project configuration API with full metadata.

```sh
ibmcloud project config-deploy --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-deploy-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-deploy-examples}

```sh
ibmcloud project config-deploy \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-deplou-cli-output}

Sample response for a project configuration draft.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-undeploy`
{: #project-cli-config-undeploy-command}

Destroy a project's configuration resources. The operation destroys all the resources that are deployed with the specific configuration. You can track it by using the get project configuration API with full metadata.

```sh
ibmcloud project config-undeploy --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-undeploy-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-undeploy-examples}

```sh
ibmcloud project config-undeploy \
    --project-id exampleString \
    --id exampleString
```
{: pre}

## `ibmcloud project config-sync`
{: #project-cli-config-sync-command}

Sync a project configuration by analyzing the associated pipeline runs and schematics workspace logs to get the configuration back to a working state.

```sh
ibmcloud project config-sync --project-id PROJECT-ID --id ID [--schematics SCHEMATICS]
```

### Command options
{: #project-config-sync-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--schematics` ([`SchematicsWorkspace`](#cli-schematics-workspace-example-schema))
:   A schematics workspace associated to a project configuration. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--schematics=@path/to/file.json`.

`--schematics-workspace-crn` (string)
:   An existing schematics workspace CRN. This option provides a value for a sub-field of the JSON option 'schematics'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `4` characters. The value must match regular expression `/^crn:v[0-9](:([A-Za-z0-9\\-._~!$&'()*+,;=@\/]|%[0-9A-Z]{2})*){8}$/`.

### Examples
{: #project-config-sync-examples}

```sh
ibmcloud project config-sync \
    --project-id exampleString \
    --id exampleString \
    --schematics '{"workspace_crn": "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"}'
```
{: pre}

Alternatively, granular options are available for the sub-fields of JSON string options:
```sh
ibmcloud project config-sync \
    --project-id exampleString \
    --id exampleString \
    --schematics-workspace-crn exampleString
```
{: pre}

## `ibmcloud project config-resources`
{: #project-cli-config-resources-command}

A list of resources deployed by a configuraton.

```sh
ibmcloud project config-resources --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-resources-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-resources-examples}

```sh
ibmcloud project config-resources \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-resources-cli-output}

Sample response for get project configuration resources.

```json
{
  "resources" : [ {
    "resource_crn" : "crn:v1:staging:public:toolchain:us-south:a/4e1c48fcf8ac33c0a2441e4139f189ae:bf40ad13-b107-446a-8286-c6d576183bb1::",
    "resource_name" : "toolchain_instance",
    "resource_type" : "ibm_cd_toolchain",
    "resource_tainted" : false,
    "resource_group_name" : ""
  }, {
    "resource_crn" : "crn:v1:staging:public:cloud-object-storage:global:a/4e1c48fcf8ac33c0a2441e4139f189ae:bf40ad13-b107-446a-8286-c6d576183bb1::",
    "resource_name" : "cos_bucket_instance",
    "resource_type" : "ibm_cos_bucket",
    "resource_tainted" : false,
    "resource_group_name" : ""
  } ],
  "resources_count" : 2
}
```
{: screen}

## `ibmcloud project config-versions`
{: #project-cli-config-versions-command}

Returns a list of previous and current versions of a project configuration in a specific project.

```sh
ibmcloud project config-versions --project-id PROJECT-ID --id ID
```

### Command options
{: #project-config-versions-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

### Example
{: #project-config-versions-examples}

```sh
ibmcloud project config-versions \
    --project-id exampleString \
    --id exampleString
```
{: pre}

### Example output
{: #project-config-versions-cli-output}

Sample response for list project configuration drafts.

```json
{
  "versions" : [ {
    "version" : 1,
    "state" : "approved",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/293c3c36-a094-4115-a12b-de0a9ca39be5/versions/1"
  }, {
    "version" : 2,
    "state" : "validated",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/db268db0-160b-4911-8f93-89659000a927/configs/293c3c36-a094-4115-a12b-de0a9ca39be5/versions/2"
  } ]
}
```
{: screen}

## `ibmcloud project config-version`
{: #project-cli-config-version-command}

Returns a specific version of a project configuration in a specific project.

```sh
ibmcloud project config-version --project-id PROJECT-ID --id ID --version VERSION
```

### Command options
{: #project-config-version-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--config-id` (string)
:   The unique configuration ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--version` (int64)
:   The configuration version. Required.

### Example
{: #project-config-version-examples}

```sh
ibmcloud project config-version \
    --project-id exampleString \
    --id exampleString \
    --version 38
```
{: pre}

### Example output
{: #project-config-version-cli-output}

Sample response for a project configuration draft.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5",
  "definition" : {
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a `terraform_template` type of configuration that points to a GitHub repo hosting the Terraform modules that can be deployed by a Schematics workspace.",
    "labels" : [ "env:stage", "governance:test", "build:0" ],
    "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
    "type" : "terraform_template",
    "inputs" : {
      "account_id" : "$configs[].name["account-stage"].inputs.account_id",
      "resource_group" : "stage",
      "access_tags" : [ "env:stage" ],
      "logdna_name" : "name of the LogDNA stage service instance",
      "sysdig_name" : "name of the SysDig stage service instance"
    }
  },
  "is_draft" : true,
  "version" : 2,
  "outputs" : [ {
    "name" : "resource_group_id"
  }, {
    "name" : "logdna_id"
  }, {
    "name" : "sysdig_id"
  } ],
  "project" : {
    "id" : "cfbf9050-ab8e-ac97-b01b-ab5af830be8a",
    "definition" : {
      "name" : "iaas-infra-prestage-env"
    },
    "crn" : "crn:v1:staging:public:project:us-south:a/06580c923e40314421d3b6cb40c01c68:cfbf9050-ab8e-ac97-b01b-ab5af830be8a::",
    "href" : "https://projects.api.cloud.ibm.com/v1/projects/cfbf9050-ab8e-ac97-b01b-ab5af830be8a"
  },
  "schematics" : {
    "workspace_crn" : "crn:v1:staging:public:schematics:us-south:a/38acaf4469814090a4e675dc0c317a0d:95ad49de-ab96-4e7d-a08c-45c38aa448e6:workspace:us-south.workspace.service.e0106139"
  },
  "state" : "validated",
  "update_available" : true,
  "created_at" : "2023-02-22T19:51:23.253Z",
  "modified_at" : "2023-02-22T19:51:23.253Z"
}
```
{: screen}

## `ibmcloud project config-version-delete`
{: #project-cli-config-version-delete-command}

Delete a configuration in a project. Deleting the configuration will also destroy all the resources deployed by the configuration if the query parameter `destroy` is specified.

```sh
ibmcloud project config-version-delete --project-id PROJECT-ID --id ID --version VERSION
```

### Command options
{: #project-config-version-delete-cli-options}

`--project-id` (string)
:   The unique project ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--id` (string)
:   The unique config ID. Required.

    The maximum length is `128` characters. The value must match regular expression `/^[\\.\\-0-9a-zA-Z]+$/`.

`--version` (int64)
:   The configuration version. Required.

### Example
{: #project-config-version-delete-examples}

```sh
ibmcloud project config-version-delete \
    --project-id exampleString \
    --id exampleString \
    --version 38
```
{: pre}

### Example output
{: #project-config-version-delete-cli-output}

An example of the delete configuration response.

```json
{
  "id" : "293c3c36-a094-4115-a12b-de0a9ca39be5"
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

The following schema examples represent the data that you need to specify for a command option. These examples model the data structure and include placeholder values for the expected value type. When you run a command, replace these values with the values that apply to your environment as appropriate.

### EnvironmentDefinitionProperties
{: #cli-environment-definition-properties-example-schema}

The following example shows the format of the EnvironmentDefinitionProperties object.

```json

{
  "name" : "development",
  "description" : "The environment 'development'",
  "authorizations" : {
    "trusted_profile_id" : "exampleString",
    "method" : "api_key",
    "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
  },
  "inputs" : { },
  "compliance_profile" : {
    "id" : "some-profile-id",
    "instance_id" : "some-instance-id",
    "instance_location" : "us-south",
    "attachment_id" : "some-attachment-id",
    "profile_name" : "some-profile-name"
  }
}
```
{: codeblock}

### EnvironmentDefinitionRequiredProperties
{: #cli-environment-definition-required-properties-example-schema}

The following example shows the format of the EnvironmentDefinitionRequiredProperties object.

```json

{
  "name" : "development",
  "description" : "The environment 'development'",
  "authorizations" : {
    "trusted_profile_id" : "exampleString",
    "method" : "api_key",
    "api_key" : "TbcdlprpFODhkpns9e0daOWnAwd2tXwSYtPn8rpEd8d9"
  },
  "inputs" : { },
  "compliance_profile" : {
    "id" : "some-profile-id",
    "instance_id" : "some-instance-id",
    "instance_location" : "us-south",
    "attachment_id" : "some-attachment-id",
    "profile_name" : "some-profile-name"
  }
}
```
{: codeblock}

### ProjectConfigPatchDefinitionBlock
{: #cli-project-config-patch-definition-block-example-schema}

The following example shows the format of the ProjectConfigPatchDefinitionBlock object.

```json

{
  "name" : "exampleString",
  "description" : "exampleString",
  "environment" : "exampleString",
  "authorizations" : {
    "trusted_profile_id" : "exampleString",
    "method" : "api_key",
    "api_key" : "exampleString"
  },
  "compliance_profile" : {
    "id" : "exampleString",
    "instance_id" : "exampleString",
    "instance_location" : "exampleString",
    "attachment_id" : "exampleString",
    "profile_name" : "exampleString"
  },
  "locator_id" : "exampleString",
  "inputs" : { },
  "settings" : { }
}
```
{: codeblock}

### ProjectConfigPrototypeDefinitionBlock
{: #cli-project-config-prototype-definition-block-example-schema}

The following example shows the format of the ProjectConfigPrototypeDefinitionBlock object.

```json

{
    "name" : "env-stage",
    "description" : "Stage environment configuration, which includes services common to all the environment regions. There must be a blueprint configuring all the services common to the stage regions. It is a terraform_template type of configuration that points to a Github repo hosting the terraform modules that can be deployed by a Schematics Workspace.",
  "environment" : "exampleString",
  "authorizations" : {
    "trusted_profile_id" : "exampleString",
    "method" : "api_key",
    "api_key" : "exampleString"
  },
  "compliance_profile" : {
    "id" : "exampleString",
    "instance_id" : "exampleString",
    "instance_location" : "exampleString",
    "attachment_id" : "exampleString",
    "profile_name" : "exampleString"
  },
  "locator_id" : "1082e7d2-5e2f-0a11-a3bc-f88a8e1931fc.018edf04-e772-4ca2-9785-03e8e03bef72-global",
  "inputs" : { },
  "settings" : { }
}
```
{: codeblock}

### ProjectConfigPrototype[]
{: #cli-project-config-prototype-example-schema}

The following example shows the format of the ProjectConfigPrototype[] object.

```json

[ {
  "definition" : {
    "name" : "exampleString",
    "description" : "exampleString",
    "environment" : "exampleString",
    "authorizations" : {
      "trusted_profile_id" : "exampleString",
      "method" : "api_key",
      "api_key" : "exampleString"
    },
    "compliance_profile" : {
      "id" : "exampleString",
      "instance_id" : "exampleString",
      "instance_location" : "exampleString",
      "attachment_id" : "exampleString",
      "profile_name" : "exampleString"
    },
    "locator_id" : "exampleString",
    "inputs" : { },
    "settings" : { }
  },
  "schematics" : {
    "workspace_crn" : "exampleString"
  }
} ]
```
{: codeblock}

### ProjectPatchDefinitionBlock
{: #cli-project-patch-definition-block-example-schema}

The following example shows the format of the ProjectPatchDefinition object.

```json

{
  "name" : "acme-microservice",
  "description" : "A microservice to deploy on top of ACME infrastructure.",
  "destroy_on_delete" : true
}
```
{: codeblock}

### ProjectPrototypeDefinitionBlock
{: #cli-project-prototype-definition-block-example-schema}

The following example shows the format of the ProjectPrototypeDefinitionBlock object.

```json

{
  "name" : "acme-microservice",
  "description" : "A microservice to deploy on top of ACME infrastructure.",
  "destroy_on_delete" : true
}
```
{: codeblock}

### SchematicsWorkspace
{: #cli-schematics-workspace-example-schema}

The following example shows the format of the SchematicsWorkspace object.

```json

{
  "workspace_crn" : "exampleString"
}
```
{: codeblock}
