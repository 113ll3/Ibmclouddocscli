---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-22"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Mit Ressourcen und Ressourcengruppen arbeiten
{: #ibmcloud_commands_resource}

Eine Ressourcengruppe bietet Ihnen die Möglichkeit, Ihre Kontoressourcen in anpassbaren Gruppierungen zu organisieren. Verwenden Sie die folgenden Befehle, um {{site.data.keyword.cloud}}-Ressourcen und Ressourcen in einer Ressourcengruppe zu verwalten.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Ressourcengruppen auflisten.
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--default</dt>
  <dd>Standardgruppe des aktuellen Kontos abrufen.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Ressourcengruppen unter aktuellem Zielkonto auflisten:
```
ibmcloud resource groups
```
{: codeblock}

Standardgruppe unter aktuellem Zielkonto auflisten:
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

Details einer Ressourcengruppe anzeigen
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Ressourcengruppe</dd>
  <dt>--id</dt>
  <dd>Nur ID anzeigen</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` anzeigen:
```
ibmcloud resource group example-group
```
{: codeblock}

Nur ID der Ressourcengruppe `example-group` anzeigen:
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Ressourcengruppe erstellen:
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Ressourcengruppe</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` erstellen:
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Vorhandene Ressourcengruppe aktualisieren
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Zielressourcengruppe</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name der Ressourcengruppe</dd>
  <dt>-q, --quota</dt>
  <dd>Name der neuen Kontingentdefinition</dd>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` in `trial-group` umbenennen:
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

Kontingent der Ressourcengruppe `example-group` in `free` ändern:
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Alle Kontingentdefinitionen auflisten:
```
ibmcloud resource quotas
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Kontingentdefinitionen auflisten:
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Details einer Kontingentdefinition anzeigen
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Kontingents</dd>
</dl>

<strong>Beispiele</strong>:

Details des Kontingents `free` anzeigen:
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Cloud Foundry-Serviceinstanz in eine Ressourcengruppe migrieren
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME oder SERVICE_INSTANCE_ID (erforderlich)</dt>
  <dd>Der Name oder die ID der Serviceinstanz</dd>
  <dt>--resource-group-name</dt>
  <dd>Der Name der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit dem Flag '--resource-group-id'. Wenn keine der beiden Optionen angegeben wird, wird standardmäßig die aktuell als Ziel angegebene Ressourcengruppe verwendet.</dd>
  <dt>--resource-group-id</dt>
  <dd>Die ID der Ressourcengruppe. Diese Option ist gegenseitig ausschließend mit dem Flag '--resource-group-name'. Wenn keine der beiden Optionen angegeben wird, wird standardmäßig die aktuell als Ziel angegebene Ressourcengruppe verwendet.</dd>
  <dt>-f, --force</dt>
  <dd>Migrieren ohne Bestätigung</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Serviceinstanzen auflisten
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>Der Name des zugehörigen Service</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>Nach Position filtern</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>Instanztypen. Der Typ `service_instance` wird verwendet, wenn keine Angabe gemacht wird; mit 'all' können alle Instanztypen aufgelistet werden.</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--long</dt>
  <dd>Weitere Felder in Ausgabe anzeigen</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. </dd>
</dl>

<strong>Beispiele</strong>:

Serviceinstanzen des Service `test-service` auflisten:
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Details einer Serviceinstanz anzeigen

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich), gegenseitig ausschließend mit ID</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>ID (erforderlich), gegenseitig ausschließend mit NAME</dt>
  <dd>ID der Serviceinstanz</dd>
  <dt>--location</dt>
  <dd>Nach Position filtern</dd>
  <dt>--id</dt>
  <dd>ID der Serviceinstanz anzeigen</dd>
  <dt>--output</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
</dl>

<strong>Beispiele</strong>:

Details der Serviceinstanz `my-service-instance` anzeigen:
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Serviceinstanz erstellen
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>SERVICE_NAME oder SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Service. Verwenden Sie zum Auflisten von Serviceangeboten den Befehl `ibmcloud catalog service-marketplace`[](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace).</dd>
  <dt>SERVICE_PLAN_NAME oder SERVICE_PLAN_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Serviceplans</dd>
  <dt>LOCATION (erforderlich)</dt>
  <dd>Zielposition oder -umgebung zum Erstellen der Serviceinstanz</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>Name der Bereitstellung</dd>
  <dt>-p, --parameters <i>@JSONFILE or JSON_STRING</i></dt>
  <dd>Die JSON-Datei oder JSON-Zeichenfolge von Parametern zum Erstellen einer Serviceinstanz</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Typen der Serviceendpunkte</dd>
</dl>

<strong>Beispiele</strong>:

Serviceinstanz mit dem Namen `my-service-instance` unter Verwendung des Serviceplans `test-service-plan` des Service `test-service` in der Region `eu-gb` erstellen:
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Serviceinstanz aktualisieren:
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>Name (erforderlich)</dt>
  <dd>Name der Serviceinstanz, gegenseitig ausschließend mit ID</dd>
  <dt>ID (erforderlich)</dt>
  <dd>ID der Serviceinstanz, gegenseitig ausschließend mit NAME</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>Der neue Name der Serviceinstanz</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>Die neue ID des Serviceplans</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>Die JSON-Datei oder JSON-Zeichenfolge von Parametern zum Erstellen einer Serviceinstanz</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Typen der Serviceendpunkte</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceinstanz `my-service-instance` aktualisieren und ihren Namen in `new-service-instance` ändern:
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Serviceinstanz löschen:
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>Name (erforderlich)</dt>
  <dd>Name der Serviceinstanz, gegenseitig ausschließend mit ID</dd>
  <dt>ID (erforderlich)</dt>
  <dd>ID der Serviceinstanz, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
  <dt>--recursive</dt>
  <dd>Alle zugehörigen Ressourcen löschen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcenserviceinstanz `my-service-instance` löschen:
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Bindungen an Servicealias anzeigen:
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcenbindungen an Servicealias `my-service-alias` anzeigen:
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Details einer Servicebindung anzeigen:
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>--id</dt>
  <dd>Nur die ID anzeigen. Alle anderen Ausgaben für diese Servicebindung werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
</dl>

<strong>Beispiele</strong>:

Details der Servicebindung zwischen dem Servicealias `my-service-alias` und der App `my-app` anzeigen:
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Servicebindung erstellen:
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME (erforderlich)</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>ROLE_NAME (erforderlich)</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Typ des Serviceendpunkts</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Servicebindung  zwischen dem Servicealias `my-service-alias` und der App `my-app` mit der Rolle `Administrator` erstellen:
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Servicebindung löschen:
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicebindung zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` löschen:
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Serviceschlüssel der Serviceinstanz oder des Servicealias auflisten:
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Die Serviceinstanz-ID</dd>
  <dt>--instance-name</dt>
  <dd>Der Serviceinstanzname</dd>
  <dt>--alias-id</dt>
  <dd>Die Servicealias-ID</dd>
  <dt>--alias-name</dt>
  <dd>Der Servicealiasname</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Serviceschlüssel der Serviceinstanz `my-service-instance` auflisten:
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Zeigt die Details jeder beliebigen Anzahl an Serviceschlüsseln an; dabei stimmen die ersten *n* Zeichen des Serviceschlüsselnamens mit dem bereitgestellten Schlüsselnamen (KEY_NAME) überein.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>ID</dt>
  <dd>ID des Schlüssels</dd>
  <dt>-g</dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--id</dt>
  <dd>ID des Serviceschlüssels anzeigen. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
</dl>

<strong>Beispiele</strong>:

Details des Serviceschlüssels `my-service-key` anzeigen:
```
ibmcloud resource service-key my-service-key
```
<strong>Beispiele</strong>:
Details des Serviceschlüssels mit der ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79` anzeigen:

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Serviceschlüssel erstellen:
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>ROLE_NAME (erforderlich)</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>Die Serviceinstanz-ID</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>Der Serviceinstanzname</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>Die Servicealias-ID</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>Der Servicealiasname</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Name der Ressourcengruppe</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Typ des Serviceendpunkts</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceschlüssel mit dem Namen `my-service-key` und der Rolle `Administrator` für die Serviceinstanz `my-service-instance` erstellen:
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Serviceschlüssel aktualisieren:
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>Der Name oder die ID des Schlüssels</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>Der neue Name des Schlüssels</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Die ID der Ressourcengruppe, zu der der Schlüssel gehört</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceschlüssel mit dem Namen `my-service-key` aktualisieren und den neuen Namen `my-service-key-2` zuweisen:
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Serviceschlüssel löschen:
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>Name des Schlüssels oder ID des Schlüssels</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceschlüssel `my-service-key` löschen:
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Aliasnamen für eine Serviceinstanz auflisten:
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Die ID der zugehörigen Serviceinstanz.</dd>
  <dt>--instance-name</dt>
  <dd>Der Name der zugehörigen Serviceinstanz.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Servicealiasnamen für Serviceinstanz `my-service-instance` auflisten:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Details eines Servicealias anzeigen:
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>--id</dt>
  <dd>Nur die ID des angegebenen Servicealias anzeigen. Alle anderen Ausgaben für diesen Alias werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>--output value  Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--id'.</dd>
</dl>

<strong>Beispiele</strong>:

Details des Servicealias `my-service-alias` anzeigen:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Alias einer Serviceinstanz erstellen:
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>--instance-id</dt>
  <dd>Die ID der zugehörigen Serviceinstanz.</dd>
  <dt>--instance-name</dt>
  <dd>Der Name der zugehörigen Serviceinstanz.</dd>
  <dt>-s</dt>
  <dd>Der Name des Bereichs, in dem der Alias erstellt wird. Der Standardwert ist der aktuelle Bereich.</dd>
  <dt>-t, --tags</dt>
  <dd>Tagaufzählung</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
</dl>

<strong>Beispiele</strong>:

Servicealias mit dem Namen `my-service-alias` der Serviceinstanz `my-service-instance` erstellen:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Servicealias aktualisieren:
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Servicealias</dd>
  <dt>-t, --tags</dt>
  <dd>Tagaufzählung</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung durch Benutzer erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Servicealias `my-service-alias` aktualisieren und den Namen in `new-service-alias` ändern:
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Servicealias löschen:
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Servicealias `my-service-alias` löschen:
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

Mit der Lucene-Abfragesyntax nach Ressourcen suchen:
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Anfangspositionsnummer der Ressource</dd>
  <dt>-l, -limit</dt>
  <dd>Anzahl zurückzugebender Ressourcen (maximal 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Für Sortierung zu verwendende Eigenschaft. Folgende Eingaben werden akzeptiert: `name`, `family`, `region`, `type`, `crn`.</dd>
  <dt>-p, --provider</dt>
  <dd>Ressourcen der klassischen Infrastruktur anzeigen (nur der Wert 'classic-infrastructure' ist zulässig)</dd>
</dl>

<strong>Durchsuchbare Attribute</strong>:
Sie können nach den folgenden Attributen suchen:

<dl>
  <dt>name</dt>
  <dd>Der benutzerdefinierte Name der Ressource.</dd>
  <dt>region</dt>
  <dd>Der geographische Bereich, in dem die Ressource bereitgestellt wird. Beispiele: us-south, us-east, au-syd, eu-gb, eu-de und jp-tok.</dd>
  <dt>service_name</dt>
  <dd>Der Name des Service, wie er in der Spalte 'Name' in der Ausgabe zu 'ibmcloud catalog service-marketplace' erscheint.</dd>
  <dt>family</dt>
  <dd>Die Cloudkomponente, zu der Ihre Ressource gehört. Zulässige Werte sind 'cloud_foundry', 'containers', 'resource_controller', 'vmware' oder 'ims'.</dd>
  <dt>organization_id</dt>
  <dd>Die GUID der Cloud Foundry-Organisation.</dd>
  <dt>doc.space_id</dt>
  <dd>Die GUID des Cloud Foundry-Bereichs.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>Die ID der Ressourcengruppe.</dd>
  <dt>type</dt>
  <dd>Der Ressourcentyp. Zulässige Werte sind 'k8-cluster', 'cf-service-instance', 'cf-user-provided-service-instance', 'cf-organization', 'cf-service-binding', 'cf-space', 'cf-application', 'resource-instance', 'resource-alias', 'resource-binding', 'resource-group', 'vmware-solutions', 'cloud-objects-storage-infrastructure', 'block-storage', 'file-storage', 'cloud-backup'.</dd>
  <dt>creation_date</dt>
  <dd>Das Erstellungsdatum der Ressource.</dd>
  <dt>modification_date</dt>
  <dd>Das Datum, an dem die Ressource zuletzt geändert wurde. Das Datumsformat ist 'jjjj-mm-ttThh:mm:ssZ </dd>
  <dt>_objectType</dt>
  <dd>Der Typ der klassischen Infrastrukturressource. Zulässige Werte sind 'SoftLayer_Virtual_DedicatedHost', 'SoftLayer_Hardware', 'SoftLayer_Network_Application_Delivery_Controller', 'SoftLayer_Network_Subnet_IpAddress', 'SoftLayer_Network_Vlan', 'SoftLayer_Network_Vlan_Firewall' und 'SoftLayer_Virtual_Guest'. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>Der an eine Ressource angehängte Tag. Verwenden Sie 'tagReferences.tag.name' zum Suchen nach Tags, die an klassische Inftrastrukturressourcen angehängt sind. </dd> 
</dl>

<strong>Beispiele</strong>:

Nach Cloud Foundry-Anwendungen suchen, deren Name mit einem angegebenen Text beginnt:
```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Nach Cloud Foundry-Serviceinstanzen des angegebenen Servicenamens suchen:
```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Nach Cloud Foundry-Servicebindungen in der Organisation mit der angegebenen ID suchen:
```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Nach Cloud Foundry-Bereichen mit dem angegebenen Namen in einer der zwei angegebenen Regionen suchen:
```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Nach Ressourcen, deren Name die Zeichenfolge dev enthält, im Cloud Foundry-Bereich mit der angegebenen ID suchen:
```
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Nach Resource Controller-Ressourcen an der angegebenen Position suchen (d. h. in der Region Vereinigte Staaten (Süden)):
```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Nach Ressourcen oder Aliasnamen in der Ressourcengruppe mit der angegebenen ID suchen:
```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Nach Ressourcengruppen mit dem Namen 'default' suchen:
```
ibmcloud resource search 'name:default AND type:resource-group'
```

Nach Ressourcenbindungen für den angegebenen Servicenamen suchen:
```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Nach einer Ressource mit dem angegebenen CRN (Cloud Resource Name) suchen:
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Nach einer Ressource mit dem angegebenen Tag suchen:
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

Nach einer klassischen Infrastrukturressource des Typs 'Virtual_Guest' mit der angegebenen ID suchen (nur mit '-p classic-infrastructure'):
```
ibmcloud resource search 'id:12345678 _objectType:SoftLayer_Virtual_Guest'
```
{: codeblock}

Nach einer klassischen Infrastrukturressources des Typs 'Hardware' mit dem angegebenen Tagnamen suchen (nur mit '-p classic-infrastructure'):
```
ibmcloud resource search 'tagReferences.tag.name:name _objectType:SoftLayer_Hardware'
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Alle Tags in Ihrem Abrechnungskonto auflisten:

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Anfangspositionsnummer des Tags</dd>
  <dt>-l, -limit</dt>
  <dd>Anzahl zurückzugebender Tags (maximal 1000, standardmäßig 100)</dd>
  <dt>-p; --provider</dt> 
  <dd>'classic-infrastructure' angeben, um nach Tags für die klassische Infrastruktur zu suchen</dd>
  <dt>-d, --details</dt>
  <dd>Anzahl der mit Tags versehenen Ressourcen anzeigen</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Mindestens einen Tag einer Ressource zuordnen:
```
ibmcloud resource tag-attach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```
<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-names (erforderlich)</dt>
  <dd>Durch Kommas getrennte Liste der Tagnamen</dd>
  <dt>--resource-id</dt>
  <dd>Die CRN der Ressource, der die Tags zugeordnet werden sollen; bei Ressourcen der klassischen Infrastruktur die ID der Ressource. Sie können die CRN oder die ID der Ressource mit dem Befehl 'ibmcloud resource search' abrufen.</dd>
  <dt>--resource-type</dt>
  <dd>Der Ressourcentyp der klassischen Infrastrukturressource, der die Tags zugeordnet werden sollen. Dieser Parameter ist erforderlich, wenn ein Tag für eine klassische Infrastrukturressource zugeordnet wird. Mögliche Werte für '--resource-type' sind 'SoftLayer_Virtual_DedicatedHost', 'SoftLayer_Hardware', 'SoftLayer_Network_Application_Delivery_Controller', 'SoftLayer_Network_Subnet_IpAddress', 'SoftLayer_Network_Vlan', 'SoftLayer_Network_Vlan_Firewall' und 'SoftLayer_Virtual_Guest'. </dd>
</dl>

<strong>Beispiele</strong>:

* Wenn Sie den Tag `MyTag` an einen Kubernetes-Cluster mit dem Namen `MyCluster` anhängen möchten, suchen Sie zuerst nach der CRN des Clusters, den Sie mit Tags versehen möchten:
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  Notieren Sie die CRN, bei der es sich um eine Zeichenfolge ähnlich diesem Beispiel handelt: 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  Führen Sie den folgenden Befehl aus, um den Tag zuzuordnen:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* Wenn Sie den Tag `MyTag` an eine virtuelle Gastmaschine der klassischen Infrastruktur mit dem Namen `MyVM` anhängen möchten, suchen Sie zuerst nach der ID der virtuellen Gastmaschine, die Sie mit Tags versehen möchten:
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  Notieren Sie die ID, bei der es sich um eine Zeichenfolge ähnlich `48373549` handelt.

  Führen Sie den folgenden Befehl aus, um den Tag zuzuordnen:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Für mindestens einen Tag die Zuordnung zu einer Ressource aufheben:
```
ibmcloud resource tag-detach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-names (erforderlich)</dt>
  <dd>Durch Kommas getrennte Liste der Tagnamen</dd>
  <dt>--resource-id</dt>
  <dd>Die CRN der Ressource, für die die Tagzuordnung aufgehoben werden soll; bei Ressourcen der klassischen Infrastruktur die ID der Ressource. Sie können die CRN oder die ID der Ressource mit dem Befehl 'ibmcloud resource search' abrufen.</dd>
  <dt>--resource-type</dt>
  <dd>Der Typ der klassischen Infrastrukturressource, für die die Tagzuordnung aufgehoben werden soll. Dieser Parameter ist erforderlich, wenn ein Tag für eine klassische Infrastrukturressource zugeordnet wird. Mögliche Werte für '--resource-type' sind 'SoftLayer_Virtual_DedicatedHost', 'SoftLayer_Hardware', 'SoftLayer_Network_Application_Delivery_Controller', 'SoftLayer_Network_Subnet_IpAddress', 'SoftLayer_Network_Vlan', 'SoftLayer_Network_Vlan_Firewall' und 'SoftLayer_Virtual_Guest'. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Tag löschen:
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Der Name des zu löschenden Tags.</dd>
  <dt>-p; --provider</dt> 
  <dd>'classic-infrastructure' angeben, um einen Tag für die klassische Infrastruktur zu löschen.</dd>
</dl>

Ein Tag kann nur gelöscht werden, wenn er keiner Ressource zugeordnet ist.
