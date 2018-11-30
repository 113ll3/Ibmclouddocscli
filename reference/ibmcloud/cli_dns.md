---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing domains with the DNS service

{{site.data.keyword.Bluemix}} Domain Name Service (DNS) provides customers with a central location to view and manage their domains through the basic DNS management interface and also gives users the option to manage reverse and secondary DNS in the same location for free of charge.

Use the following commands to manage the {{site.data.keyword.Bluemix_notm}} classic infrastructure DNS service.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} infrastructure DNS commands that have links that bring you to more info for the command">
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

## ibmcloud sl dns import
{: #sl_dns_import}

Import a zone based off a BIND zone file.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--dry-run</dt>
<dd>Don't actually create records.</dd>
</dl>

**Examples**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
This command imports zone and its resource records from file: ~/ibm.com.txt.

## ibmcloud sl dns record-add
{: #sl_dns_record_add}

Add resource record in a zone.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL(Time-To-Live)  in seconds, such as: 86400, default is: 7200.</dd>
</dl>

**Examples**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
This command adds an A record to zone: ibm.com, its host is "ftp", data is "127.0.0.1" and ttl is 86400 seconds.

## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Update resource records in a zone.
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--by-record</dt>
<dd>Edit by host record, such as www.</dd>
<dt>--by-id</dt>
<dd>Edit a single record by its ID.</dd>
<dt>--data</dt>
<dd>Record data, such as an IP address.</dd>
<dt>--ttl</dt>
<dd>TTL value in seconds, such as: 86400.</dd>
</dl>

**Examples**:
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
This command edits records under zone: ibm.com, whose ID is 12345678, and set its data to "127.0.0.2" and ttl to 3600.

## ibmcloud sl dns record-list
{: #sl_dns_record_list}

List all the resource records in a zone.
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--data</dt>
<dd>Filter by record data, such as an IP address.</dd>
<dt>--record</dt>
<dd>Filter by host record, such as www.</dd>
<dt>--ttl</dt>
<dd>Filter by TTL value in seconds, such as 86400.</dd>
<dt>--type</dt>
<dd>Filter by record type, such as A or CNAME.</dd>
</dl>

**Examples**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
This command lists all A records under zone: ibm.com,filtered by host is elasticsearch and ttl is 900 seconds.

## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Remove resource record from a zone.
```
ibmcloud sl dns record-remove RECORD_ID
```


**Examples**:
```
ibmcloud sl dns record-remove 12345678
```
This command removes resource record with ID 12345678.

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Create a zone.
```
ibmcloud sl dns zone-create ZONE
```


**Examples**:
```
ibmcloud sl dns zone-create ibm.com
```
This command creates a zone named ibm.com.

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Delete a zone.
```
ibmcloud sl dns zone-delete ZONE
```


**Examples**:
```
ibmcloud sl dns zone-delete ibm.com
```
This command deletes a zone named ibm.com.

## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

List all zones on your account.
```
ibmcloud sl dns zone-list
```


**Examples**:
```
ibmcloud sl dns zone-list
```
This command lists all zones under current account.

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Print zone and resource records in BIND format.
```
ibmcloud sl dns zone-print ZONE
```


**Examples**:
```
ibmcloud sl dns zone-print ibm.com
```
This command prints zone named ibm.com in BIND format.
