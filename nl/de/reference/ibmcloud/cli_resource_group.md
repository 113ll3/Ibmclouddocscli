---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Ressourcengruppen und Ressourcen
{: #ibmcloud_commands_resource}

Verwenden Sie die folgenden Befehle, um {{site.data.keyword.Bluemix_notm}}-Ressourcengruppen und -Ressourcen zu verwalten.
{: shortdesc}

<table summary="ibmcloud-Befehle zur Verwaltung von Ressourcengruppen und Ressourcen.">
  <thead>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Ressourcengruppen auflisten.

```
ibmcloud resource groups [--default]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--default</dt>
  <dd>Standardgruppe des aktuellen Kontos abrufen.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Ressourcengruppen unter aktuellem Zielkonto auflisten:

```
ibmcloud resource groups
```

Standardgruppe unter aktuellem Zielkonto auflisten:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Details einer Ressourcengruppe anzeigen

```
ibmcloud resource group NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Ressourcengruppe</dd>
  <dt>--id</dt>
  <dd>Nur ID anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` anzeigen:

```
ibmcloud resource group example-group
```

Nur ID der Ressourcengruppe `example-group` anzeigen:

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Ressourcengruppe erstellen

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

<strong>Beispiele</strong>:

Ressourcengruppe `example-group` mit Kontingent `free` erstellen:

```
ibmcloud resource group-create example-group free
```

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

Kontingent der Ressourcengruppe `example-group` in `free` ändern:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Alle Kontingentdefinitionen auflisten

```
ibmcloud resource quotas
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Alle Kontingentdefinitionen auflisten:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Details einer Kontingentdefinition anzeigen

```
ibmcloud resource quota NAME
```

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
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Der Name des zugehörigen Service</dd>
  <dt>--location</dt>
  <dd>Nach Position filtern</dd>
  <dt>--long</dt>
  <dd>Weitere Felder in Ausgabe anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Serviceinstanzen des Service `test-service` auflisten:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Details einer Serviceinstanz anzeigen

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
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
</dl>

<strong>Beispiele</strong>:

Details der Serviceinstanz `my-service-instance` anzeigen:

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Serviceinstanz erstellen

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Serviceinstanz</dd>
  <dt>SERVICE_NAME oder SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Service</dd>
  <dt>SERVICE_PLAN_NAME oder SERVICE_PLAN_ID (erforderlich)</dt>
  <dd>Der Name oder die ID des Serviceplans</dd>
  <dt>LOCATION</dt>
  <dd>Zielposition oder -umgebung zum Erstellen der Serviceinstanz</dd>
  <dt>-t, --tags</dt>
  <dd>Tags</dd>
  <dt>-p, --parameters</dt>
  <dd>Die JSON-Datei oder JSON-Zeichenfolge von Parametern zum Erstellen einer Serviceinstanz</dd>
  <dt>-d, --deployment</dt>
  <dd>Name der Bereitstellung</dd>
</dl>

<strong>Beispiele</strong>:
Eine Serviceinstanz mit dem Namen `my-service-instance` mithilfe des Serviceplans `test-service-plan` des Service `test-service` in der Region `eu-gb` erstellen:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Serviceinstanz aktualisieren

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>Name (erforderlich)</dt>
  <dd>Name der Serviceinstanz, gegenseitig ausschließend mit ID</dd>
  <dt>ID (erforderlich)</dt>
  <dd>ID der Serviceinstanz, gegenseitig ausschließend mit NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name der Serviceinstanz</dd>
  <dt>-t, --tags</dt>
  <dd>Neue Tags</dd>
  <dt>--service-plan-id</dt>
  <dd>Die neue ID des Serviceplans</dd>
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

Serviceinstanz löschen

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
Serviceinstanz `my-service-instance` der Ressource löschen:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Bindungen an Servicealias anzeigen

```
ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
</dl>

<strong>Beispiele</strong>:
Ressourcenbindungen an Servicealiasnamen `my-service-alias` anzeigen:

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Details einer Servicebindung anzeigen

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>--id</dt>
  <dd>Nur die ID anzeigen. Alle anderen Ausgaben für diese Servicebindung werden unterdrückt.</dd>
</dl>

<strong>Beispiele</strong>:
Details der Servicebindung zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` anzeigen:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Servicebindung erstellen

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (erforderlich)</dt>
  <dd>Der Servicealiasname</dd>
  <dt>APP_NAME</dt>
  <dd>Der Cloud Foundry-Anwendungsname</dd>
  <dt>ROLE_NAME</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--service-id</dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameter</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Servicebindungen zwischen dem Servicealiasnamen `my-service-alias` und der App `my-app` mit der Rolle `Administrator` erstellen:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Servicebindung löschen

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

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Serviceschlüssel der Serviceinstanz oder des Servicealias auflisten

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel der Serviceinstanz `my-service-instance` auflisten:

```
ibmcloud resource service-keys --instance-name my-service-instance
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Details eines Serviceschlüssels anzeigen

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>--id</dt>
  <dd>ID des Serviceschlüssels anzeigen</dd>
</dl>

<strong>Beispiele</strong>:
Details der Serviceschlüssel `my-service-key` anzeigen:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Serviceschlüssel erstellen

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME</dt>
  <dd>Der Name des Schlüssels</dd>
  <dt>ROLE_NAME</dt>
  <dd>Der Name der Benutzerrolle</dd>
  <dt>--instance-id</dt>
  <dd>Die Serviceinstanz-ID</dd>
  <dt>--instance-name</dt>
  <dd>Der Serviceinstanzname</dd>
  <dt>--alias-id</dt>
  <dd>Die Servicealias-ID</dd>
  <dt>--alias-name</dt>
  <dd>Der Servicealiasname</dd>
  <dt>--service-id</dt>
  <dd>Der Name oder die UUID der Service-ID, zu der die Rolle gehört</dd>
  <dt>-p, --parameters</dt>
  <dd>JSON-Datei oder JSON-Zeichenfolge als Parameter</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:
Serviceschlüssel mit dem Namen `my-service-key` mit der Rolle `Administrator` für die Serviceinstanz `my-service-instance` erstellen:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Serviceschlüssel löschen

```
ibmcloud resource service-key-delete KEY_NAME [-f, --forece]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Der Name des Schlüssels</dd>
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

Aliasnamen für eine Serviceinstanz auflisten

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>Die ID der zugehörigen Serviceinstanz.</dd>
  <dt>--instance-name</dt>
  <dd>Der Name der zugehörigen Serviceinstanz.</dd>
</dl>

<strong>Beispiele</strong>:
Servicealiasnamen für Serviceinstanz `my-service-instance` auflisten:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Details eines Servicealias anzeigen

```
ibmcloud resource service-alias ALIAS_NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>ALIAS_NAME (erforderlich)</dt>
  <dd>Der Name des Servicealias</dd>
  <dt>--id</dt>
  <dd>Nur die ID des angegebenen Servicealias anzeigen. Alle anderen Ausgaben für diesen Alias werden unterdrückt.</dd>
</dl>

<strong>Beispiele</strong>:
Details des Servicealias `my-service-alias` anzeigen:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Alias einer Serviceinstanz erstellen

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

Servicealias aktualisieren

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
Servicealias `my-service-alias` aktualisieren und seinen Namen in `new-service-alias` ändern:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Servicealias löschen

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
Mit der Lucene-Abfragesyntax nach Ressourcen suchen

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)]
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
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Nach einer Ressource mit dem angegebenen Tag suchen:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Alle Tags auflisten

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Tagtyp (unterstützte Werte: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>Anfangspositionsnummer der Ressource (Standardwert: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Anzahl zurückzugebender Ressourcen (maximal 10000) (Standardwert: 10000)</dd>
</dl>

<strong>Beispiele</strong>:

Alle Tags auflisten

```
ibmcloud resource tags
```

Alle eingeschränkten Tags auflisten

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Details eines Tags anzeigen

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
</dl>

<strong>Beispiele</strong>:

Details des Tags "Ray Brown" anzeigen

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Tag erstellen

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname</dd>
  <dt>--tag-type</dt>
  <dd>Tagtyp (unterstützte Werte: user, restricted; Standardwert: user)</dd>
</dl>

<strong>Beispiele</strong>:

Benutzertag mit dem Namen "think:2018" erstellen

```
ibmcloud resource tag-create --tag-name think:2018
```

Eingeschränkten Tag mit dem Namen "department:marketing" erstellen

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Benutzertag mit dem Namen "Ray Brown" erstellen

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Eingeschränkten Tag mit dem Namen "environment:My Development" erstellen

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Tag löschen

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" löschen

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Tag zu einer Ressource hinzufügen

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--resource-crn (erforderlich)</dt>
  <dd>Ressourcen-CRN</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" zur Ressource mit dem CRN "resource_example_crn" hinzufügen

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Tag von einer Ressource entfernen

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--resource-crn (erforderlich)</dt>
  <dd>Ressourcen-CRN</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" von der Ressource mit dem CRN "resource_example_crn" entfernen

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Benutzertag in eingeschränkten Tag ändern und umgekehrt

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--tag-name (erforderlich)</dt>
  <dd>Tagname, gegenseitig ausschließend mit --tag-crn</dd>
  <dt>--tag-crn (erforderlich)</dt>
  <dd>Tag-CRN, gegenseitig ausschließend mit --tag-name</dd>
  <dt>--tag-type (erforderlich)</dt>
  <dd>Tagtyp</dd>
</dl>

<strong>Beispiele</strong>:

Tag "Ray Brown" in eingeschränkten Tag ändern

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
