---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing classic infrastructure tickets
{: #manage-sl-tickets}

Use the following commands to manage {{site.data.keyword.cloud}} classic infrastructure tickets.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach}

Attach devices to a ticket:
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--hardware</dt>
<dd>The identifier for hardware to attach.</dd>
<dt>--virtual</dt>
<dd>The identifier for a virtual server to attach.</dd>
</dl>

**Examples**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create}

Create a support ticket:
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--attachment</dt>
<dd>Initial object ID number to attach to ticket.</dd>
<dt>--rootpwd</dt>
<dd>Root password that is associated with the attached device ID.</dd>
<dt>--subject-id</dt>
<dd>Required. The subject ID to use for the ticket, issue `ibmcloud sl ticket subjects` to get the list.</dd>
<dt>--title</dt>
<dd>Required. The title of the ticket.</dd>
<dt>--body</dt>
<dd>The ticket body.</dd>
<dt>--priority</dt>
<dd>Ticket priority [1|2|3|4], from 1 (Critical) to 4 (Minimal Impact). Only settable with Advanced and Premium support. See https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Specify the type of attachment，hardware or virtual. The default is hardware.</dd>
</dl>

**Examples**:
```
ibmcloud sl ticket create --title "Example title" --subject-id 1522 --body "This is an example ticket. Please disregard."
```
{: codeblock}

## ibmcloud sl ticket detach
{: #sl_ticket_detach}

Detach devices from a ticket:
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--hardware</dt>
<dd>The identifier for hardware to detach.</dd>
<dt>--virtual</dt>
<dd>The identifier for a virtual server to detach.</dd>
</dl>

**Examples**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail
{: #sl_ticket_detail}

Get details for a ticket:
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--count</dt>
<dd>Number of updates.</dd>
</dl>

**Examples**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list
{: #sl_ticket_list}

List tickets:
```
ibmcloud sl ticket list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--open</dt>
<dd>Display only open tickets.</dd>
<dt>--closed</dt>
<dd>Display only closed tickets.</dd>
</dl>

## ibmcloud sl ticket subjects
{: #sl_ticket_subjects}

List Subject IDs for ticket creation:
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary
{: #sl_ticket_summary}

View the summary information about tickets:
```
ibmcloud sl ticket summary
```

## ibmcloud sl ticket update
{: #sl_ticket_update}

Adds an update to an existing ticket:
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Examples**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload
{: #sl_ticket_upload}

Adds an attachment to an existing ticket:
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>Command options</strong>:
<dl>
<dt>--name</dt>
<dd>The name of the attachment shown in the ticket.</dd>
</dl>

**Examples**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

