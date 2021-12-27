---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cli

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing classic infrastructure support tickets (ibmcloud sl ticket)
{: #manage-sl-tickets}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure tickets.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach}

Attach devices to a ticket:
```bash
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

**Command options**:

--hardware
:   The identifier for hardware to attach.

--virtual
:   The identifier for a virtual server to attach.

**Examples**:
```bash
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create}

Create a support ticket:
```bash
ibmcloud sl ticket create [OPTIONS]
```

**Command options**:

--attachment
:   Initial object ID number to attach to ticket.

--rootpwd
:   Root password that is associated with the attached device ID.

--subject-id
:   Required. The subject ID to use for the ticket, issue `ibmcloud sl ticket subjects` to get the list.

--title
:   Required. The title of the ticket.

--body
:   The ticket body.

--priority
:   Ticket priority [1|2|3|4], from 1 (Critical) to 4 (Minimal Impact). Only settable with Advanced and Premium support. See https://www.ibm.com/cloud/support.

--attachment-type
:   Specify the type of attachment，hardware or virtual. The default is hardware.

**Examples**:
```bash
ibmcloud sl ticket create --title "Example title" --subject-id 1522 --body "This is an example ticket. Please disregard."
```
{: codeblock}

## ibmcloud sl ticket detach
{: #sl_ticket_detach}

Detach devices from a ticket:
```bash
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

**Command options**:

--hardware
:   The identifier for hardware to detach.

--virtual
:   The identifier for a virtual server to detach.

**Examples**:
```bash
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```bash
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail
{: #sl_ticket_detail}

Get details for a ticket:
```bash
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

**Command options**:

--count
:   Number of updates.

**Examples**:
```bash
ibmcloud sl ticket detail 767676
```
{: codeblock}

```bash
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list
{: #sl_ticket_list}

List tickets:
```bash
ibmcloud sl ticket list [OPTIONS]
```

**Command options**:

--open
:   Display only open tickets.

--closed
:   Display only closed tickets.

## ibmcloud sl ticket subjects
{: #sl_ticket_subjects}

List Subject IDs for ticket creation:
```bash
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary
{: #sl_ticket_summary}

View the summary information about tickets:
```bash
ibmcloud sl ticket summary
```

## ibmcloud sl ticket update
{: #sl_ticket_update}

Adds an update to an existing ticket:
```bash
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Examples**:
```bash
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload
{: #sl_ticket_upload}

Adds an attachment to an existing ticket:
```bash
ibmcloud sl ticket upload TICKETID FILEPATH
```

**Command options**:

--name
:   The name of the attachment shown in the ticket.

**Examples**:
```bash
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

