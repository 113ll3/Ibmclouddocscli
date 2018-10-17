---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN

The Content Delivery Network (CDN) service distributes content where it is needed. The first time content is requested, it’s pulled from the host server to the network and stays there for other users to access it.

Use the following commands to manage the {{site.data.keyword.Bluemix_notm}} infrastructure CDN service.
{: shortdesc}

<table summary="Alphabetically ordered {{site.data.keyword.Bluemix_notm}} infrastructure CDN commands that have links that bring you to more info for the command">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

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
<dd>CDN bandwidth, 'Pay as You Go' price will be used if not specified.</dd>
<dt>-s, --storage</dt>
<dd>CDN storage, 'Pay as You Go' price will be used if not specified.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Bandwidth and storage options for ordering CDN account.
```
ibmcloud sl cdn options
```

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

List origin pull mappings.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Remove an origin pull mapping.
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

Purge cached files from all edge nodes.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>
