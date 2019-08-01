---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Unternehmen, Kontogruppen und Konten verwalten
{: #ibmcloud_enterprise}

Verwenden Sie die folgenden Befehle, um Unternehmen, Kontogruppen und Konten zu verwalten.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Ein Unternehmen erstellen. 
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>NAME (erforderlich)</dt>
<dd>Unternehmensname.</dd>
<dt>-d, --domain DOMAIN_NAME (optional)</dt>
<dd>Domänenname.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)</dt>
<dd>Benutzer-ID der primären Kontaktperson des Unternehmens.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Unternehmensinformationen aktualisieren.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>-f, --force (optional)</dt>
<dd>Aktualisierung ohne Bestätigung.</dd>
<dt>-n, --name NEW_NAME (required)</dt>
<dd>Neuer Name des Unternehmens.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Details des Unternehmens anzeigen.
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Eine Kontogruppe erstellen.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>NAME (erforderlich)</dt>
<dd>Kontogruppenname.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name der übergeordneten Kontogruppe. Bei Auslassung wird das aktuelle Unternehmen verwendet.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (optional)</dt>
<dd>Benutzer-ID der primären Kontaktperson der Kontogruppe.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Eine Kontogruppe aktualisieren.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--id ID (erforderlich)</dt>
<dd>ID der Zielkontogruppe. Diese Option ist gegenseitig ausschließend mit `-n, --name`.</dd>
<dt>-n, --name NAME (erforderlich)</dt>
<dd>Name der Zielkontogruppe. Diese Option ist gegenseitig ausschließend mit `--id`.</dd>
<dt>--new-name NEW_NAME (erforderlich)</dt>
<dd>Neuer Name der Zielkontogruppe. </dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Details zur Kontogruppe anzeigen.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--id ID (erforderlich)</dt>
<dd>ID der Kontogruppe. Diese Option ist gegenseitig ausschließend mit `-n, --name`.</dd>
<dt>-n, --name NAME (erforderlich)</dt>
<dd>Name der Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--id`.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

Kontogruppen auflisten.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group`.</dd>
<dt>--recursive (optional)</dt>
<dd>Untergeordnete Kontogruppen anzeigen.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Ein Konto erstellen.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>NAME (erforderlich)</dt>
<dd>Kontogruppenname.</dd>
<dt>--owner USER_ID (optional)</dt>
<dd>Benutzer-ID der Kontogruppe. </dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional).</dt>
<dd>Name der übergeordneten Kontogruppe. Bei Auslassung wird das aktuelle Unternehmen verwendet.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Ein Konto in ein anderes übergeordnetes Element verschieben.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--id ID (erforderlich)</dt>
<dd>ID des Zielkontos.Diese Option ist gegenseitig ausschließend mit `-n, --name`.</dd>
<dt>-n, --name NAME (erforderlich)</dt>
<dd>Name des Zielkontos. Diese Option ist gegenseitig ausschließend mit `--id`.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (erforderlich)</dt>
<dd>Name der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group-id` und `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (erforderlich)</dt>
<dd>ID der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group` und `--parent-enterprise`.</dd>
<dt>--parent-enterprise (erforderlich)</dt>
<dd>Das Unternehmen als übergeordnetes Element festlegen. Diese Option ist gegenseitig ausschließend mit `--parent-account-group` und `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Details des Kontos anzeigen.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--id ID (erforderlich)</dt>
<dd>ID des Kontos. Diese Option ist gegenseitig ausschließend mit `-n, --name`.</dd>
<dt>-n, --name NAME (erforderlich)</dt>
<dd>Name des Kontos. Diese Option ist gegenseitig ausschließend mit `--id`.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

Konten auflisten.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (optional)</dt>
<dd>Name der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group`.</dd>
<dt>--recursive (optional)</dt>
<dd>Untergeordnete Konten anzeigen.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Ein eigenständiges Konto importieren.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
<dt>--account-id</dt>
<dd>ID des Quellenkontos. </dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (optional)</dt>
<dd>Name der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (optional)</dt>
<dd>ID der übergeordneten Kontogruppe. Diese Option ist gegenseitig ausschließend mit `--parent-account-group`.</dd>
</dl>
