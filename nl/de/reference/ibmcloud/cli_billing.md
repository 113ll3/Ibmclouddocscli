---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Nutzungsinformationen für Konten, Organisationen, Ressourcengruppen und Ressourcen anzeigen 
{: #ibmcloud_billing}

Verwenden Sie die folgenden Befehle, um Ressourcennutzungs- und Abrechnungsdaten abzurufen.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Monatliche Nutzungsinformationen des aktuellen Kontos anzeigen (nur Kontoadministrator): 
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Nutzungs- und Kostenbericht des aktuellen Kontos für 06/2016 anzeigen:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Monatliche Nutzungsinformationen für eine Organisation anzeigen (nur Kontoadministrator oder Abrechnungsmanager der Organisation): 
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>ORG_NAME (erforderlich)</dt>
  <dd>Name der Organisation.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Monatliche Nutzungsinformationen für eine Ressourcengruppe anzeigen (nur Kontoadministrator oder Ressourcengruppenadministrator):
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>GROUP_NAME (erforderlich)</dt>
  <dd>Name der Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Monatliche Nutzungsinformationen für Ressourceninstanzen des aktuellen Kontos anzeigen: 
```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-o ORG_NAME (optional)</dt>
  <dd>Filterinstanzen nach Organisation.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filterinstanzen nach Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für Monat und Datum durch Angeben des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>
