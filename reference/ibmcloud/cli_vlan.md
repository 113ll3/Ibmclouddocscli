---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, classic infrastructure cli, vlan cli, classic vlan cli, ibmcloud sl vlan, manage virtual network cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing classic infrastructure VLANs (ibmcloud sl vlan)
{: #manage-classic-vlans}

Virtual local area networks (VLANs) are used by {{site.data.keyword.cloud}} to isolate broadcast traffic on the public and private networks. VLANs are assigned as needed to fulfill other offerings.

Use the following commands from the {{site.data.keyword.cloud_notm}} Command Line Interface to manage classic infrastructure VLANs.
{: shortdesc}

## ibmcloud sl vlan create
{: #sl_vlan_create}

Create a new VLAN:
```bash
ibmcloud sl vlan create [OPTIONS]
```

**Command options**:

-t, --vlan-type
:   The type of the VLAN, either public or private.

-r, --router
:   The host name of the router.

-d, --datacenter
:   The short name of the datacenter.

-n, --name
:   The name of the VLAN.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vlan create -t public -d dal09 -n myvlan
```
{: codeblock}

This command creates a public VLAN that is located in datacenter `dal09` and name is `myvlan`.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Cancel a VLAN:
```bash
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vlan cancel 12345678 -f
```
{: codeblock}

This command cancels VLAN with ID `12345678` without asking for confirmation.

## ibmcloud sl vlan detail
{: #sl_vlan_detail}

Get details about a VLAN:
```bash
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

**Command options**:

--no-vs
:   Hide virtual server listing.

--no-hardware
:   Hide hardware listing.

**Examples**:
```bash
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
{: codeblock}

This command shows details of VLAN with ID `12345678`, and not list virtual server or hardware server.

## ibmcloud sl vlan edit
{: #sl_vlan_edit}

Edit the details about a VLAN:
```bash
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

**Command options**:

-n, --name
:   The name of the VLAN.

**Examples**:
```bash
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
{: codeblock}

This command updates vlan with ID `12345678` and gives it a new name `myvlan-rename`.

## ibmcloud sl vlan list
{: #sl_vlan_list}

List all the VLANs on your account:
```bash
ibmcloud sl vlan list [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.

-d, --datacenter
:   Filter by datacenter shortname.

-n, --number
:   Filter by VLAN number.

--name
:   Filter by VLAN name.

--order
:   Filter by ID of the order that purchased the VLAN.

**Examples**:
```bash
ibmcloud sl vlan list -d dal09 --sortby number
```
{: codeblock}

This commands lists all VLANs on current account, and filtering by datacenter that equals to `dal09`, and sorts them by VLAN number.

## ibmcloud sl vlan options
{: #sl_vlan_options}

List all the options for creating VLAN:
```bash
ibmcloud sl vlan options
```

**Examples**:
```bash
ibmcloud sl vlan options
```
{: codeblock}

This command lists all options for creating a VLAN, eg. VLAN type, datacenters, subnet size, routers, etc.

