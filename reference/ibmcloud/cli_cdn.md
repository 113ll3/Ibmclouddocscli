---

copyright:
  years: 2018, 2019
lastupdated: "2019-09-09"

keywords: cli, content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Working with the Content Delivery Network (CDN) service
{: #sl-cdn-service}

The Content Delivery Network (CDN) service distributes content where its needed. A CDN is a system of distributed servers that deliver web content based on the geographic locations of the user, the origin of the webpage, and the content delivery server.

Use the following commands to manage the {{site.data.keyword.cloud_notm}} classic infrastructure CDN service.
{: shortdesc}

## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Cancel a CDN account.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

Detail a CDN Account.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

List all CDN accounts.
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filter by order ID.</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

Cache one or more files on all edge nodes.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

Order a CDN account.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN bandwidth. Pay as You Go price is used if not specified.</dd>
<dt>-s, --storage</dt>
<dd>CDN storage. Pay as You Go price is used if not specified.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Show bandwidth and storage options for ordering CDN account:
```
ibmcloud sl cdn options
```
{: codeblock}

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Create an origin pull mapping.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-t, --type</dt>
<dd>The media type for this mapping (http, flash, wm, ...), default is: http.</dd>
<dt>-c, --cname</dt>
<dd>An optional CNAME to attach to the mapping.</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

List origin pull mappings:
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Remove an origin pull mapping:
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

Purge cached files from all edge nodes:
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>
