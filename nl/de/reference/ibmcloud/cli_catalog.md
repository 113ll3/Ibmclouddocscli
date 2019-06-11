---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Katalogangebote durchsuchen und verwalten
{: #ibmcloud_catalog}

Verwenden Sie die folgenden Befehle, um die {{site.data.keyword.cloud}}-Katalogeinträge, -Abfragevorlagen, -Laufzeiten und -Geoortungen in Rechenzentren zu verwalten.
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Katalogeinträge durchsuchen:
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Die geografische Region angeben, in der gesucht werden soll. Derzeit werden nur 'us-south' und 'united-kingdom' unterstützt.</dd>
  <dt>-k, --kind</dt>
  <dd>Nach Ressourcentyp filtern. Derzeit werden nur 'service-cf', 'iaas', 'runtime', 'template' und 'dashboard' unterstützt.</dd>
  <dt>-p, --price</dt>
  <dd>Nach Preis filtern. Derzeit werden nur 'free', 'paygo' und 'ibmcloud-subscription' unterstützt.</dd>
  <dt>-t, --tag</dt>
  <dd>Nach Tag filtern.</dd>
  <dt>--sort-by</dt>
  <dd>Für Sortierung zu verwendende Eigenschaft</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Derzeit werden 'group', 'provider' und 'tags' unterstützt.</dd>
  <dt>--reverse</dt>
  <dd>Gibt an, ob die Sortierreihenfolge umgekehrt werden soll</dd>
  <dt>--output TYPE (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
  <dt>--csv</dt>
  <dd>CSV-Ausgabedatei</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Service `Automation test` suchen:
```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Katalogeintrag abrufen:
```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--children</dt>
  <dd>Alle untergeordneten Elemente für Katalogeintrag abrufen</dd>
  <dt>--output TYPE (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Eintrag mit ID `a0ef1-d3b4j0` abrufen:
```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}

Neuen Katalogeintrag erstellen (nur Katalogadministrator eines Kontos):
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>Die übergeordnete ID des Objekts</dd>
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource aus JSON-Datei mit der übergeordneten ID `a0ef1-d3b4j0` erstellen:
```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}

Vorhandenen Katalogeintrag aktualisieren (nur Katalogadministrator oder Editor eines Kontos):
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource `j402-dnf1i` aus JSON-Datei aktualisieren:
```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Katalogeintrag löschen (nur Katalogadministrator eines Kontos)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Ressource `j402-dnf1i` löschen:
```
ibmcloud catalog delete `j402-dnf1i`
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Sichtbarkeit eines Katalogeintrags abrufen (nur Katalogadministrator eines Kontos)
```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>--output TYPE (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
  <dt>-global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Sichtbarkeit der Ressource `j402-dnf1i` im globalen Bereich abrufen:
```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}

Sichtbarkeit eines vorhandenen Katalogeintrags aktualisieren (nur Katalogadministrator eines Kontos):
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) zur Einschlussliste hinzufügen und für den Eintrag Sichtbarkeit erteilen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--includes-remove</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) aus der Einschlussliste entfernen und für den Eintrag die Sichtbarkeit widerrufen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>  
  <dt>--excludes-add</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) zur Ausschlussliste hinzufügen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--excludes-remove</dt>
  <dd>Ein Konto (oder eine Liste mit durch Kommas getrennten Konten) aus der Ausschlussliste entfernen und für den Eintrag die Sichtbarkeit widerrufen. Wenn das Konto von globalen Administratoren eingerichtet wurde, dann können die Kontoadministratoren das Konto nicht löschen. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--owner</dt>
  <dd>Den Eigner eines Objekts ändern. E-Mail- oder Konto-GUIDs sind zulässig.</dd>
  <dt>--restrict</dt>
  <dd>Die Einschränkung des Sichtbarkeitsobjekts in 'Privat' ändern.</dd>
  <dt>--unrestrict</dt>
  <dd>Die Einschränkung des Sichtbarkeitsobjekts in 'Öffentlich' ändern.</dd>  
  <dt>-c</dt>
  <dd>Das gültige JSON-Objekt, das die katalogspezifischen Konfigurationsparameter enthält, die entweder zeilenintern (inline) oder in einer Datei angegeben werden. Eine Liste der unterstützten Konfigurationsparameter finden Sie in der Dokumentation für den jeweiligen Katalogeintrag.</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Sichtbarkeit der Ressource `j402-dnf1i` aus JSON-Datei festlegen:
```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}

Serviceangebote im Marktplatz auflisten:
```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Nur Cloud Foundry-Services anzeigen</dd>
  <dt>--rc</dt>
  <dd>Nur RC-kompatible Services anzeigen</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Serviceangebote im globalen Bereich anzeigen:
```
ibmcloud catalog service-marketplace --global
```
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Boilerplate-Vorlagen in {{site.data.keyword.cloud_notm}} anzeigen
```
ibmcloud catalog templates [-d]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>-d (optional)</dt>
   <dd>Wenn die Option <i>-d</i> angegeben wird, wird auch die Beschreibung jeder Vorlage angezeigt. Andernfalls werden nur die ID und der Name jeder Vorlage angezeigt.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Zeigt die detaillierten Informationen einer angegebenen Boilerplate-Vorlage an.
```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die ID der Boilerplate-Vorlage. Verwenden Sie <i>ibmcloud templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   </dl>


<strong>Beispiele</strong>:

Details der Vorlage `mobileBackendStarter` anzeigen:
```
ibmcloud catalog template mobileBackendStarter
```
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Erstellt eine cf-Anwendung, die auf der angegebenen Vorlage mit der angegebenen URL und Beschreibung basiert. Die neue App wird standardmäßig automatisch gestartet.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die Vorlage, auf der die Anwendung basiert, wenn sie erstellt wird. Verwenden Sie <i>ibmcloud templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   <dt>CF_APP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung, die erstellt werden soll.</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>Der Hostname der CF-Anwendung. Wenn sie nicht angegeben ist, wird die Route von {{site.data.keyword.cloud_notm}} automatisch auf der Grundlage des App-Namens und der Standarddomäne festgelegt.</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>Die Domäne der CF-Anwendung. Wenn sie nicht angegeben ist, wird die Route von {{site.data.keyword.cloud_notm}} automatisch auf der Grundlage des App-Namens und der Standarddomäne festgelegt.</dd>
   <dt>--desc <i>DESCRIPTION</i> (optional)</dt>
   <dd>Die Beschreibung für die Anwendung.</dd>
   <dt>--no-start (optional)</dt>
   <dd>Nach der Erstellung wird die Anwendung nicht automatisch gestartet: Wenn diese Option nicht angegeben ist, wird die Anwendung nach ihrer Erstellung automatisch gestartet.</dd>
   </dl>


<strong>Beispiele</strong>:

Erstellen Sie eine `cf`-App mit dem Namen `my-app`, die auf der Vorlage `javaHelloWorld` basiert:
```
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

Erstellen Sie eine App `my-ruby-app` auf Basis der Vorlage `rubyHelloWorld` mit einer Beschreibung:
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

Erstellen Sie eine App `my-python-app` auf Basis der Vorlage `pythonHelloWorld` ohne automatischen Start:
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ausgewähltes Subset von Regionen in von Ihnen ausgewähltem Format abrufen.
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Geografie nach ID angeben.</dd>
  <dt>-k, --kind</dt>
  <dd>Liste mit Einträgen für die angegebene Art abrufen.</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Momentan "group", "provider" und "tags".</dd>
  <dt>--output TYPE (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
  <dt>--global</dt>
  <dd>In globalem Bereich arbeiten.</dd>
  <dt>--csv</dt>
  <dd>CSV-Ausgabedatei</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Details einer Laufzeit anzeigen. Dieser Befehl steht nur für die öffentliche Cloud zur Verfügung.
```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Beispiele</strong>:

Details der Laufzeit "nodejsHelloWorld" anzeigen:
```
catalog runtime nodejsHelloWorld
```
{: codeblock}

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Alle Laufzeiten auflisten. Dieser Befehl steht nur für die öffentliche Cloud zur Verfügung.
```
ibmcloud catalog runtimes [-d]
```

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-d</dt>
  <dd>Beschreibung der einzelnen Laufzeiten anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Alle Laufzeiten und deren Beschreibung auflisten:
```
ibmcloud catalog runtimes -d
```
{: codeblock}
