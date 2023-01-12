---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, ibmcloud sl call-api, classic infrastructure, API endpoints

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Calling arbitrary classic infrastructure API endpoints (ibmcloud sl call-api)
{: #sl-all-api}

Use the following command from the {{site.data.keyword.cloud}} Command Line Interface to call the arbitrary classic infrastructure API endpoints.
{: shortdesc}

## ibmcloud sl call-api
{: #sl_call_api}

Call arbitrary API endpoints:
```bash
ibmcloud sl call-api SERVICE METHOD [OPTIONS]
```

**Command options**:

--init
:   Init parameter.

--mask
:   Object mask: use to limit fields returned.

--parameters
:   Append parameters to web call.

--limit
:   Result limit.

--offset
:   Result offset.

--filter
:   Object filters.


**Examples**:
```bash
ibmcloud sl call-api SoftLayer_Network_Storage editObject --init 57328245 --parameters '[{"notes":"Testing."}]'
```
{: codeblock}

This command edits volume notes.
