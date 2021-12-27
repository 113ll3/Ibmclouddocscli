---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, placement group management, ibmcloud sl placement-group, classic infrastructure, placement group, placement group cli, manage placement group cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Managing classic infrastructure placement groups (ibmcloud sl placement-group)
{: #sl-manage-placement-group}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage the {{site.data.keyword.cloud_notm}} classic infrastructure placement group.
{: shortdesc}

## ibmcloud sl placement-group create
{: #sl_placement_group_create}

Create a placement group:
```bash
ibmcloud sl placement-group create (--name NAME) (-b, --backend-router-id BACKENDROUTER) (-r, --rule-id RULE)
```

**Command options**:

-n, --name
:   Required. Name for this new placement group.

-b, --backend-router-id
:   Required. Backend router ID.

-r, --rule-id
:   Required. The ID of the rule to govern this placement group.

## ibmcloud sl placement-group create-options
{: #sl_placement_group_create_options}

List options for creating a placement group:
```bash
ibmcloud sl placement-group create-options
```

## ibmcloud sl placement-group delete
{: #sl_placement_group_delete}

Delete a placement group:
```bash
ibmcloud sl placement-group delete (--id PLACEMENTGROUP_ID) [-f, --force]
```

**Command options**:

--id
:   Required. ID for the placement group.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl placement-group detail
{: #sl_placement_group_detail}

View details of a placement group:
```bash
ibmcloud sl placement-group detail (--id PLACEMENTGROUP_ID)
```

**Command options**:

--id
:   Required. ID for the placement group.

## ibmcloud sl placement-group list
{: #sl_placement_group_list}

List placement groups:
```bash
ibmcloud sl placement-group list
```
