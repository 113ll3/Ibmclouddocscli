---

copyright:

  years: 2018


lastupdated: "2018-07-26"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Befehle zur Verwaltung von Einstellungen für Kataloge, Plug-ins und Abrechnungen
{: #ibmcloud_commands_settings}

<table summary="ibmcloud-Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit.">
<caption>Tabelle 1. Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung der {{site.data.keyword.Bluemix_notm}}-Einstellungen für Kataloge, Plug-ins, Abrechnungen und Sicherheit</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ### ibmcloud catalog search
{: #ibmcloud_catalog_search}

Katalogeinträge durchsuchen

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Die geografische Region angeben, in der gesucht werden soll. Momentan werden nur "us-south" und "united-kingdom" unterstützt</dd>
  <dt>-k, --kind</dt>
  <dd>Nach Art der Ressourcen filtern. Momentan werden nur "service-cf", "iaas", "runtime", "template" und "dashboard" unterstützt</dd>
  <dt>-p, --price</dt>
  <dd>Nach Preis filtern. Momentan werden nur "free", "paygo" und "bluemix-subscription" unterstützt</dd>
  <dt>-t, --tag</dt>
  <dd>Nach Tag filtern.</dd>
  <dt>--sort-by</dt>
  <dd>Für Sortierung zu verwendende Eigenschaft</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Momentan "group", "provider" und "tags".</dd>
  <dt>--reverse</dt>
  <dd>Gibt an, ob die Sortierreihenfolge umgekehrt werden soll</dd>
  <dt>--json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
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

### ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Katalogeintrag abrufen

```
ibmcloud catalog entry ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--children</dt>
  <dd>Alle untergeordneten Elemente für Katalogeintrag abrufen</dd>
  <dt>--json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>--global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Eintrag mit ID `a0ef1-d3b4j0` abrufen:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

### ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Neuen Katalogeintrag erstellen (nur Katalogadministrator eines Kontos)

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

### ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Vorhandenen Katalogeintrag aktualisieren (nur Katalogadministrator oder Editor eines Kontos)

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

### ibmcloud catalog entry-delete
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
ibmcloud catalog delete 'j402-dnf1i'
```

### ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Sichtbarkeit eines Katalogeintrags abrufen (nur Katalogadministrator eines Kontos)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-json</dt>
  <dd>Ursprüngliche JSON-Antwort ausgeben</dd>
  <dt>-global</dt>
  <dd>Im globalen Bereich arbeiten</dd>
</dl>

<strong>Beispiele</strong>:

Sichtbarkeit der Ressource `j402-dnf1i` im globalen Bereich abrufen:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

### ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Sichtbarkeit eines vorhandenen Katalogeintrags aktualisieren (nur Katalogadministrator eines Kontos)

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

### ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Serviceangebote im Marktplatz auflisten

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

### ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Boilerplate-Vorlagen in {{site.data.keyword.Bluemix_notm}} anzeigen

```
ibmcloud catalog templates [-d]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>-d (optional)</dt>
   <dd>Wenn die Option <i>-d</i> angegeben wird, wird auch die Beschreibung jeder Vorlage angezeigt. Andernfalls werden nur die ID und der Name jeder Vorlage angezeigt.</dd>
   </dl>

### ibmcloud catalog template
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

### ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Erstellt eine cf-Anwendung, die auf der angegebenen Vorlage mit der angegebenen URL und Beschreibung basiert. Die neue App wird standardmäßig automatisch gestartet.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>TEMPLATE_ID (erforderlich)</dt>
   <dd>Die Vorlage, auf der die Anwendung bei ihrer Erstellung basiert. Verwenden Sie <i>ibmcloud templates</i>, um die IDs aller Vorlagen anzuzeigen.</dd>
   <dt>CF_APP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung, die erstellt werden soll.</dd>
   <dt>-u <i>URL</i> (optional)</dt>
   <dd>Die Route der Anwendung. Wenn sie nicht angegeben ist, wird die Route von {{site.data.keyword.Bluemix_notm}} automatisch auf der Grundlage des App-Namens und der Standarddomäne festgelegt.</dd>
   <dt>-d <i>DESCRIPTION</i> (optional)</dt>
   <dd>Die Beschreibung für die Anwendung.</dd>
   <dt>--no-start (optional)</dt>
   <dd>Startet die Anwendung nach ihrer Erstellung nicht automatisch. Wenn diese Option nicht angegeben wird, wird die Anwendung nach ihrer Erstellung automatisch gestartet.</dd>
   </dl>


<strong>Beispiele</strong>:

cf-Anwendung `my-app` auf der Basis der Vorlage `javaHelloWorld` erstellen:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Anwendung `my-ruby-app` auf der Basis der Vorlage `rubyHelloWorld` mit der Route `myrubyapp.chinabluemix.net` und der Beschreibung `My first ruby app on {{site.data.keyword.Bluemix_notm}}.` erstellen:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Anwendung `my-python-app` auf Basis der Vorlage `pythonHelloWorld` ohne automatischen Start erstellen:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

### ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ausgewähltes Subset von Regionen in von Ihnen ausgewähltem Format abrufen.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Geografie nach ID angeben.</dd>
  <dt>-k, --kind</dt>
  <dd>Liste mit Einträgen für die angegebene Art abrufen.</dd>
  <dt>--col</dt>
  <dd>Zusätzliche Spalten für die Tabelle angeben. Momentan "group", "provider" und "tags".</dd>
  <dt>--json</dt>
  <dd>Ausgabe der ursprünglichen JSON-Antwort.</dd>
  <dt>--global</dt>
  <dd>In globalem Bereich arbeiten.</dd>
  <dt>--csv</dt>
  <dd>CSV-Ausgabedatei</dd>
</dl>

### ibmcloud catalog runtime
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

### ibmcloud catalog runtimes
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

### ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Monatliche Nutzungsinformationen des aktuellen Kontos anzeigen (nur Kontoadministrator)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

<strong>Beispiele</strong>:

Nutzungs- und Kostenbericht des aktuellen Kontos für 06/2016 anzeigen:

```
ibmcloud billing account-usage -d 2016-06
```

### ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Monatliche Nutzungsinformationen für eine Organisation anzeigen (nur Kontoadministrator oder Abrechnungsmanager der Organisation)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>ORG_NAME (erforderlich)</dt>
  <dd>Name der Organisation.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

### ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Monatliche Nutzungsinformationen für eine Ressourcengruppe anzeigen (nur Kontoadministrator oder Ressourcengruppenadministrator)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

<dl>
  <dt>GROUP_NAME (erforderlich)</dt>
  <dd>Name der Ressourcengruppe.</dd>
  <dt>-d MONTH_DATE (optional)</dt>
  <dd>Daten für den angegebenen Monat und das angegebene Datum unter Verwendung des Formats JJJJ-MM anzeigen. Wird keine Angabe gemacht, wird die Nutzung des aktuellen Monats angezeigt.</dd>
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

### ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Monatliche Nutzung für Ressourceninstanzen unter dem aktuellen Konto anzeigen.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
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
  <dt>--json (optional)</dt>
  <dd>Nutzungsergebnis im JSON-Format anzeigen.</dd>
</dl>

### ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Alle Plug-in-Repositorys auflisten, die in der Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} registriert sind.

```
ibmcloud plugin repos
```

<strong>Voraussetzungen</strong>: Keine

### ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Neues Plug-in-Repository zur Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} hinzufügen.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das hinzugefügt werden soll. Sie können einen eigenen Namen für jedes Repository definieren.</dd>
   <dt>REPO_URL (erforderlich)</dt>
   <dd>Die URL des Repositorys, das hinzugefügt werden soll. Die URL des Repositorys muss das Protokoll (zum Beispiel 'http://plugins.ng.bluemix.net' anstatt 'plugins.ng.bluemix.net') enthalten. http://plugins.ng.bluemix.net ist das offizielle Plug-in-Repository der {{site.data.keyword.Bluemix_notm}}-CLI.</dd>
    </dl>


<strong>Beispiele</strong>:

Offizielles Plug-in-Repository der {{site.data.keyword.Bluemix_notm}}-CLI als `bluemix-repo` hinzufügen:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

### ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Plug-in-Repository aus der {{site.data.keyword.Bluemix_notm}}-CLI entfernen.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das entfernt werden soll.</dd>
   </dl>

<strong>Beispiele</strong>:

Repository `bluemix-repo` aus der Befehlszeilenschnittstelle von {{site.data.keyword.Bluemix_notm}} entfernen:

```
ibmcloud plugin repo-remove bluemix-repo
```

### ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Alle verfügbaren Plug-ins in allen hinzufügten Repositorys oder einem bestimmten Repository auflisten.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Nur die Plug-ins im angegebenen Repository auflisten.</dd>
   </dl>

<strong>Beispiele</strong>:

Alle Plug-ins in allen hinzugefügten Repositorys auflisten:

```
ibmcloud plugin repo-plugins
```

Alle Plug-ins im Repository `bluemix-repo` auflisten:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

### ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Details eines Plug-ins im Repository anzeigen.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Der Name des Repositorys. Wird kein Repository angegeben, verwendet der Befehl das Standardrepository des Plug-ins.</dd>
   </dl>

<strong>Beispiele</strong>:

Details des Plug-ins "IBM-Containers" im Repository "sample-repo" auflisten:

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Details des Plug-ins "IBM-Containers" im Standardrepository auflisten

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

### ibmcloud plugin list
{: #ibmcloud_plugin_list}

Alle installierten Plug-ins in der {{site.data.keyword.Bluemix_notm}}-CLI auflisten.

```
ibmcloud plugin list
```

<strong>Voraussetzungen</strong>: Keine

### ibmcloud plugin show
{: #ibmcloud_plugin_show}

Details eines installierten Plug-ins anzeigen.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Voraussetzungen</strong>: Keine

### ibmcloud plugin install
{: #ibmcloud_plugin_install}

Angegebene Version des Plug-ins aus dem angegebenen Pfad oder Repository in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle installieren.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.
Wenn keine Version angegeben wird, wählt der Befehl die neueste verfügbare Version zur Installation aus.

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (erforderlich)</dt>
   <dd>Wenn -r <i>REPO_NAME</i> nicht angegeben wird, wird das Plug-in vom angegebenen lokalen Pfad oder der Remote URL installiert.</dd>
   <dt>-r <i>REPO_NAME</i> (optional)</dt>
   <dd>Der Name des Repositorys, in dem sich die Plug-in-Binärdatei befindet. Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.</dd>
   <dt>-v <i>VERSION</i> (optional)</dt>
   <dd>Die Version des Plug-ins, die installiert werden soll. Wird keine Angabe gemacht, wird die neueste Version des Plug-ins installiert. Diese Option ist nur gültig, wenn Sie das Plug-in aus dem Repository installieren.</dd>
   <dt>-f </dt>
   <dd>Installieren des Plug-ins ohne Bestätigung erzwingen.</dd>
    </dl>


Die {{site.data.keyword.Bluemix_notm}}-CLI trägt den offiziellen Repository-Namen `Bluemix`.

<strong>Beispiele</strong>:

Plug-in von der lokalen Datei installieren:

```
ibmcloud plugin install /downloads/new_plugin
```

Plug-in von der Remote URL installieren:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Plug-in 'container-service' der neuesten Version aus dem Repository 'Bluemix' installieren:

```
ibmcloud plugin install container-service -r Bluemix
```

oder einfach:

```
ibmcloud plugin install container-service
```

Plug-in 'container-service' mit der Version '0.1.425' aus dem offiziellen Plug-in-Repository installieren:

```
ibmcloud plugin install container-service -v 0.1.425
```

### ibmcloud plugin update
{: #ibmcloud_plugin_update}

Upgrade des Plug-ins aus einem Repository durchführen.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Wird kein Repository angegeben, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.
Wenn keine Version angegeben wird, wählt der Befehl die neueste verfügbare Version zur Installation aus.

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Name des zu aktualisierenden Plug-ins. Wenn keine Angabe erfolgt, prüft der Befehl Upgrades für alle installierten Befehle.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Der Name des Repositorys, in dem sich die Plug-in-Binärdatei befindet. Wenn keine Angabe gemacht wird, verwendet der Befehl das Standardrepository 'Bluemix' des Plug-ins.</dd>
 <dt>-v <i>VERSION</i> (optional)</dt>
 <dd>Die Version des Plug-ins, auf die aktualisiert werden soll. Wenn keine Version angegeben wird, wird das Plug-in auf die neueste verfügbare Version aktualisiert.</dd>
 <dt>--all</dt>
 <dd>Alle verfügbaren Plug-ins aktualisieren</dd>
</dl>

<strong>Beispiele</strong>:

Offizielles Plug-in-Repository 'Bluemix' auf alle verfügbaren Upgrades prüfen:

```
ibmcloud plugin update -r Bluemix
```

oder einfach:

```
ibmcloud plugin update
```

Upgrade des Plug-ins 'container-service' im offiziellen Plug-in-Repository auf die neueste Version durchführen:

```
ibmcloud plugin update container-service
```

Plug-in 'container-service' im offiziellen Plug-in-Repository auf Version '0.1.440' aktualisieren:

```
ibmcloud plugin update container-service -v 0.1.440
```

### ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Angegebenes Plug-in in der {{site.data.keyword.Bluemix_notm}}-CLI deinstallieren.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>PLUGIN_NAME (erforderlich)</dt>
   <dd>Der Name des Plug-ins, das deinstalliert werden soll.</dd>
    </dl>

<strong>Beispiele</strong>:

Plug-in 'container-service' deinstallieren, das zuvor installiert wurde:

```
ibmcloud plugin uninstall container-service
```
