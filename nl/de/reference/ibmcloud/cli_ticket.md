---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Tickets der klassischen Infrastruktur verwalten
{: #manage-sl-tickets}

Verwenden Sie die folgenden Befehle, um die Tickets der klassischen {{site.data.keyword.cloud}}-Infrastruktur zu verwalten.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

Einheiten einem Ticket zuordnen:
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hardware</dt>
<dd>ID eines Hardwaremediums, das zugeordnet werden soll.</dd>
<dt>--virtual</dt>
<dd>ID eines virtuellen Servers, der zugeordnet werden soll.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

Support-Ticket erstellen:
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--attachment</dt>
<dd>Erste Objekt-ID-Nummer für die Zuordnung zum Ticket.</dd>
<dt>--rootpwd</dt>
<dd>Rootkennwort, das der zugeordneten Einheiten-ID zugehörig ist.</dd>
<dt>--subject-id</dt>
<dd>Erforderlich. Subjekt-ID für das Ticket; 'ibmcloudsl ticket subjects' eingeben, um die Liste abzurufen.</dd>
<dt>--title</dt>
<dd>Erforderlich. Titel des Tickets.</dd>
<dt>--body</dt>
<dd>Tickethauptteil.</dd>
<dt>--priority</dt>
<dd>Ticketpriorität [1|2|3|4], von 1 (Kritisch) bis 4 (Minimale Auswirkung). Nur bei Advanced- und Premium-Support festlegbar. Informationen unter https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Geben Sie den Typ des zuzuordnenden Hardware- oder virtuellen Mediums an. Der Standardwert ist "hardware".</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

Zuordnung einer Einheit zu einem Ticket aufheben:
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hardware</dt>
<dd>ID eines Hardwaremediums, dessen Zuordnung aufgehoben werden soll.</dd>
<dt>--virtual</dt>
<dd>ID eines virtuellen Servers, für den die Zuordnung aufgehoben werden soll.</dd>
</dl>

**Beispiele**:
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

Ticketdetails anzeigen:
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--count</dt>
<dd>Anzahl der Aktualisierungen.</dd>
</dl>

**Beispiele**:
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

Tickets auflisten:
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--open</dt>
<dd>Nur offene Tickets anzeigen.</dd>
<dt>--closed</dt>
<dd>Nur geschlossene Tickets anzeigen.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

Subjekt-IDs für die Ticketerstellung auflisten:
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

Zusammenfassende Informationen über Tickets anzeigen:
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

Aktualisierung zu einem vorhandenen Ticket hinzufügen:
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Beispiele**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

Zuordnung für ein vorhandenes Ticket hinzufügen:
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--name</dt>
<dd>Der Name der Zuordnung, die im Ticket angezeigt wird.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

