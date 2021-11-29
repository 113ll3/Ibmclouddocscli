---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-03"

keywords: cli, ibmcloud sl call-api, classic infrastructure, API endpoints

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

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
<dl>
<dt>--init</dt>
<dd>Init parameter.</dd>
<dt>--mask</dt>
<dd>Object mask: use to limit fields returned.</dd>
<dt>--parameters</dt>
<dd>Append parameters to web call.</dd>
<dt>--limit</dt>
<dd>Result limit.</dd>
<dt>--offset</dt>
<dd>Result offset.</dd>
<dt>--filter</dt>
<dd>Object filters.</dd>
</dl>

**Examples**:
```bash
ibmcloud sl call-api SoftLayer_Network_Storage editObject --init 57328245 --parameters '[{"notes":"Testing."}]'
```
{: codeblock}

This command edits volume notes.
