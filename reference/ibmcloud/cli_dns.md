---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, domain management, dns service, ibmcloud sl dns, classic infrastructure, management interface, dns, dns cli, manage dns cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Managing domains with the DNS service (ibmcloud sl dns)
{: #sl-manage-domains}

{{site.data.keyword.cloud}} Domain Name Service (DNS) provides customers with a central location to view and manage their domains through the basic DNS management interface. Users can manage reverse and secondary DNS in the same location free of charge.

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage the {{site.data.keyword.cloud_notm}} classic infrastructure DNS service.
{: shortdesc}

## ibmcloud sl dns import
{: #sl_dns_import}

Import a zone based off a BIND zone file:
```bash
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

**Command options**:

--dry-run
:   Don't actually create records.

**Examples**:
```bash
ibmcloud sl dns import ~/ibm.com.txt
```
{: codeblock}

This command imports zone and its resource records from file: `~/ibm.com.txt`.

## ibmcloud sl dns record-add
{: #sl_dns_record_add}

Add resource record in a zone:
```bash
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

**Command options**:

--ttl
:   TTL(Time-To-Live) in seconds, such as: 86400. The default is: 7200.

**Examples**:
```bash
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
{: codeblock}

This command adds an A record to zone: ibm.com, its host is "ftp", data is "127.0.0.1" and ttl is 86400 seconds.

## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Update resource records in a zone:
```bash
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

**Command options**:

--by-record
:   Edit by host record, such as www.

--by-id
:   Edit a single record by its ID.

--data
:   Record data, such as an IP address.

--ttl
:   TTL(Time-To-Live) in seconds, such as: 86400.

**Examples**:
```bash
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
{: codeblock}

This command edits records under the zone: ibm.com, whose ID is `12345678`, and sets its data to "127.0.0.2" and ttl to 3600.

## ibmcloud sl dns record-list
{: #sl_dns_record_list}

List all the resource records in a zone:
```bash
ibmcloud sl dns record-list ZONE [OPTIONS]
```

**Command options**:

--data
:   Filter by record data, such as an IP address.

--record
:   Filter by host record, such as www.

--ttl
:   Filter by TTL (Time-To-Live) in seconds, such as 86400.

--type
:   Filter by record type, such as A or CNAME.

**Examples**:
```bash
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
{: codeblock}

This command lists all A records under the zone: ibm.com, and filters by host, elasticsearch, and ttl is 900 seconds.

## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Remove resource record from a zone:
```bash
ibmcloud sl dns record-remove RECORD_ID
```

**Examples**:
```bash
ibmcloud sl dns record-remove 12345678
```
{: codeblock}

This command removes resource record with ID `12345678`.

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Create a zone:
```bash
ibmcloud sl dns zone-create ZONE 
```

**Examples**:
```bash
ibmcloud sl dns zone-create ibm.com
```
{: codeblock}

This command creates a zone that is named `ibm.com`.

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Delete a zone:
```bash
ibmcloud sl dns zone-delete ZONE
```

**Examples**:
```bash
ibmcloud sl dns zone-delete ibm.com
```
{: codeblock}

This command deletes a zone that is named `ibm.com`.

## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

List all zones on your account:
```bash
ibmcloud sl dns zone-list 
```

**Examples**:
```bash
ibmcloud sl dns zone-list
```
{: codeblock}

This command lists all zones under current account.

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Print zone and resource records in BIND format:
```bash
ibmcloud sl dns zone-print ZONE
```

**Examples**:
```bash
ibmcloud sl dns zone-print ibm.com
```
{: codeblock}

This command prints zone that is named `ibm.com`, and in BIND format.

