---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}

# IAM-Zugriff, API-Schlüssel, Service-IDs und Zugriffsgruppen verwalten
{: #ibmcloud_commands_iam}

Verwenden Sie die folgenden Befehle, um API-Schlüssel, Service-IDs, Zugriffsgruppen sowie Berechtigungsrichtlinien für Benutzer, Services und Zugriffsgruppen zu verwalten.
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Alle Service-IDs auflisten:
```
ibmcloud iam service-ids [--uuid] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Nur UUID der Service-IDs anzeigen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

UUID aller Service-IDs des aktuellen Kontos auflisten:
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Details einer Service-ID anzeigen:
```
ibmcloud iam service-id (NAME|UUID) [--uuid] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>--uuid</dt>
  <dd>Die UUID der Service-ID anzeigen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Details der Service-ID `sample-test` anzeigen:
```
ibmcloud iam service-id sample-test
```
{: codeblock}

Details der Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` anzeigen:
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Service-ID erstellen:
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung der Service-ID</dd>
  <dt>--lock</dt>
  <dd>Die Service-ID bei der Erstellung sperren</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID mit dem Servicenamen `sample-test` und der Beschreibung `hello, world!` erstellen:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

Gesperrte Service-ID mit dem Servicenamen `sample-test` und der Beschreibung `hello, world!` erstellen:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

Service-ID aktualisieren:
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Service</dd>
  <dt>-d, --description</dt>
  <dd>Die neue Beschreibung des Service</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-test` ohne Bestätigung in `sample-test-2` umbenennen:
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

Beschreibung des Service `sample-test` aktualisieren:
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` mit neuer Beschreibung in `sample-test-3` umbenennen:
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Service-ID löschen:
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID in `sample-teset` ohne Bestätigung löschen:
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` löschen:
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Service-ID sperren:
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID in `sample-teset` ohne Bestätigung sperren:
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` sperren:
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Service-ID entsperren:
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID in `sample-teset` ohne Bestätigung entsperren:
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` entsperren:
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Alle API-Schlüssel der {{site.data.keyword.cloud_notm}}-Plattform auflisten:
```
ibmcloud iam api-keys [--output FORMAT]
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Einen API-Schlüssel für die {{site.data.keyword.cloud_notm}}-Plattform erstellen:
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock] [--output FORMAT]
```

Die Verwendung der {{site.data.keyword.cloud_notm}}-CLI-Anmeldung mit einem API-Schlüssel funktioniert nicht mit dem traditionellen SL-API-Schlüssel, der sich unter `control.softlayer.com` befindet. Für die Anmeldung bei der {{site.data.keyword.cloud_notm}}-CLI mit einem API-Schlüssel ist ein aktualisiertes {{site.data.keyword.cloud_notm}}-Konto erforderlich, bei dem die Infrastruktur über [cloud.ibm.com](https://cloud.ibm.com/registration){: new_window}![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") verwaltet wird.
{: note}

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu erstellenden API-Schlüssels.</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die Beschreibung des API-Schlüssels</dd>
<dt>--file <i>FILE</i></dt>
<dd>Informationen zu API-Schlüssel in der angegebenen Datei speichern.</dd>
<dt>--lock</dt>
<dd>API-Schlüssel bei seiner Erstellung sperren.</dd>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel erstellen und in einer Datei speichern:
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

Gesperrten API-Schlüssel mit dem Namen "test-key" erstellen:
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

API-Schlüssel der {{site.data.keyword.cloud_notm}}-Plattform aktualisieren:
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der alte Name des zu aktualisierenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu aktualisierenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-n <i>NAME</i> (optional)</dt>
<dd>Der neue Name des API-Schlüssels</dd>
<dt>-d <i>DESCRIPTION</i> (optional)</dt>
<dd>Die neue Beschreibung des API-Schlüssels</dd>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Beschreibung eines API-Schlüssels aktualisieren:
```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

API-Schlüssel der {{site.data.keyword.cloud_notm}}-Plattform löschen:
```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu löschenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu löschenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

Plattform-API-Schlüssel sperren:
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Sperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel "test-api-key" sperren:
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

API-Schlüssel mit der angegebenen UUID ohne Bestätigung sperren:
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}s

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Plattform-API-Schlüssel entsperren:
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Entsperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiele</strong>:

API-Schlüssel "test-api-key" entsperren:
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

API-Schlüssel mit der angegebenen UUID ohne Bestätigung entsperren:
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Alle API-Schlüssel eines Service auflisten:
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Die Service-API-Schlüssel ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Alle API-Schlüssel des Service `sample-service` auflisten
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Details eines Service-API-Schlüssels auflisten:
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>UUID des Service-API-Schlüssels anzeigen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Den Service-API-Schlüssel ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Details des Service-API-Schlüssels `sample-key` des Service `sample-service` anzeigen:
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Service-API-Schlüssel erstellen:
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [--output FORMAT] [-f, --force] [--lock]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID oder des neu erstellten Service-API-Schlüssels</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Die Beschreibung des API-Schlüssels</dd>
  <dt>--file</dt>
  <dd>Informationen zu API-Schlüssel in der angegebenen Datei speichern.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Erstellung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` für Service `sample-service` ohne Bestätigung erstellen:
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Service-API-Schlüssel aktualisieren:
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Der neue Name des Service-API-Schlüssels</dd>
  <dt>-d, --description</dt>
  <dd>Die neue Beschreibung des Service-API-Schlüssels</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` in `new-sample-key` umbenennen:
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Service-API-Schlüssel löschen:
```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` löschen:
```
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Service-API-Schlüssel sperren:
```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` sperren:
```
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Service-API-Schlüssel entsperren:
```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` entsperren:
```
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Richtlinien eines Benutzers auflisten.
```
ibmcloud iam user-policies USER_NAME [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Benutzername, zu dem die Richtlinien gehören</dd>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:
 
Richtlinien von Benutzer `name@example.com` auflisten:
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Details einer Benutzerrichtlinie anzeigen:
```
ibmcloud iam user-policy USER_NAME POLICY_ID [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Benutzername, zu dem die Richtlinie gehört</dd>
<dt>POLICY_ID (erforderlich)</dt>
<dd>Die ID der Richtlinie</dd>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `0bb730daa` des Benutzers `name@example.com` auflisten:
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Benutzerrichtlinie erstellen:
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dl>
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>Die GUID der Serviceinstanz der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Ressource der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit den Flags `--file`, `--resource` und `--resource-group-id`.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit den Flags `--file`, `--resource` und `--resource-group-name`.</dd>
<dt>--account-management (optional)</dt>
<dd>Zugriff auf alle Kontoverwaltungsservices erteilen.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie für Benutzer `name@example.com` aus Richtlinien-JSON-Datei `policy.json` erstellen:
```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

`name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuweisen:
```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

`name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuweisen:
```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuweisen:
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

`name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Benutzerrichtlinie aktualisieren:
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dt>USER_NAME (erforderlich)</dt>
<dd>Der Benutzername, zu dem die Richtlinie gehört</dd>
<dt>POLICY_ID (erforderlich)</dt>
<dd>Die ID der zu aktualisierenden Richtlinie</dd>
<dt>--file <i>FILE</i> (optional)</dt>
<dd>Die JSON-Datei der Richtliniendefinition</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (optional)</dt>
<dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (optional)</dt>
<dd>Der Servicename der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i> (optional)</dt>
<dd>Die GUID der Serviceinstanz der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--region <i>REGION</i> (optional)</dt>
<dd>Die Region der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (optional)</dt>
<dd>Der Ressourcentyp der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource <i>RESOURCE</i> (optional)</dt>
<dd>Die Ressource der Richtliniendefinition. Gegenseitig ausschließend mit dem Flag `--file`.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (optional)</dt>
<dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit den Flags `--file`, `--resource` und `--resource-group-id`.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (optional)</dt>
<dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit den Flags `--file`, `--resource` und `--resource-group-name`.</dd>
<dt>--account-management (optional)</dt>
<dd>Zugriff auf alle Kontoverwaltungsservices erteilen.</dd>
<dt>--output FORMAT (optional)</dt>
<dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Benutzerrichtlinie mit der Benutzerrichtlinie in der JSON-Datei aktualisieren
```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Administrator` für alle Ressourcen von `sample-service` zu erteilen
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Editor` für die Ressource `key123` der Beispielserviceinstanz mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuzuweisen:
```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuzuweisen:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Benutzerrichtlinie aktualisieren, um `name@example.com` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Benutzerrichtlinie löschen
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Zielkonto

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Benutzerrichtlinie ohne Bestätigung löschen</dd>
</dl>

<strong>Beispiele</strong>:

Die Richtlinie `user-policy-id` des Benutzers `name@example.com` löschen:
```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Richtlinie `user-policy-id` des Benutzers `name@example.com` ohne Bestätigung löschen:
```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Alle Servicerichtlinien des angegebenen Service auflisten:
```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat für Servicerichtlinien angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt</dd>
  <dt>-f, --force (optional)</dt>
  <dd>Die Servicerichtlinien ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinien des Service `test` auflisten:
```
ibmcloud iam service-policies test
```

Richtlinien des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` auflisten:
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Details einer Servicerichtlinie anzeigen:
```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat für Servicerichtlinie angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt</dd>
  <dt>-f, --force (optional)</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung anzeigen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `140798e2-8ea7db3` des Service `test` anzeigen:
```
ibmcloud iam service-policies test 140798e2-8ea7db3
```

Richtlinie `140798e2-8ea7db3` des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` anzeigen:
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Servicerichtlinie erstellen:
```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit den Flags `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `--resource-group-name` und `--resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>--service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>--resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>--resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-name`.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Zugriff auf alle Kontoverwaltungsservices erteilen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung erstellen</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie aus JSON-Datei für Service `test` erstellen:
```
ibmcloud iam service-policy-create test --file @policy.json
```

Servicerichtlinie aus JSON-Datei für Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` erstellen:
```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

Service `test` die Rolle `Administrator` für alle Kontoverwaltungsservices zuweisen:
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

Service `test` die Rolle `Viewer` für alle Ressourcen im Konto zuweisen:
```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Servicerichtlinie aktualisieren:
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit den Flags `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `resource-group-name` und `resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit dem Flag `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-name`.</dd>
  <dt>--account-management (optional)</dt>
  <dd>Zugriff auf alle Kontoverwaltungsservices erteilen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Die Servicerichtlinie ohne Bestätigung aktualisieren</dd>
</dl>

<strong>Beispiele</strong>:

Servicerichtlinie `140798e2-8ea7db3` aus JSON-Datei für Service `test` aktualisieren:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Servicerichtlinie `140798e2-8ea7db3` aus JSON-Datei für Service `test` aktualisieren:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Servicerichtlinie `140798e2-8ea7db3` aktualisieren, um dem Service `test` die Rolle `Administrator` für alle Kontoverwaltungsservices zuzuweisen:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

Servicerichtlinie `140798e2-8ea7db3` aktualisieren, um dem Service `test` die Rolle `Viewer` für alle Ressourcen im Konto zuzuweisen:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Servicerichtlinie löschen:
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SERVICE_ID (erforderlich)</dt>
  <dd>Der Name oder die UUID der Service-ID</dd>
  <dt>POLICY_ID (erforderlich)</dt>
  <dd>Die ID der Servicerichtlinie<dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `140798e2-8ea7db3` des Service `test` löschen:
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```

Richtlinie `140798e2-8ea7db3` des Service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` löschen:
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

OAuth-Tokens für die aktuelle Sitzung abrufen und anzeigen:
```
ibmcloud iam oauth-tokens [--output FORMAT]
```
{: codeblock}

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

OAuth-Tokens aktualisieren und anzeigen:
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

Plattformdefinierte und servicedefinierte Rollen auflisten:
```
ibmcloud iam roles [--service SERVICE_NAME] [--output FORMAT]
```
{: codeblock}

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--service SERVICE_NAME</dt>
  <dd>Der Name des Service. Wenn nicht angegeben, werden nur die plattformdefinierten Rollen definiert.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Plattformrollen auflisten
```
ibmcloud iam roles
```

Rollen für den Service `cloudantnosql` in JSON auflisten:
```
ibmcloud iam roles --service cloudantnosql --output JSON
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Öffentliche IBMid mit dedizierter Nicht-IBMid trennen:
```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Trennen ohne Bestätigung erzwingen</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Berechtigungsrichtlinie erstellen, um den Zugriff einer Serviceinstanz auf eine andere Serviceinstanz zu ermöglichen:

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-type RESOURCE_TYPE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME] [--target-resource-type RESOURCE_TYPE | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Quellenservice, der für den Zugriff autorisiert werden kann.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Zielservice, für dessen Zugriff der Quellenservice autorisiert werden kann.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Die Rollen, die Zugriff für den Quellenservice bereitstellen.</dd>  
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Der Name der Quellenserviceinstanz, die sich mit `--source-service-instance-id` gegenseitig ausschließt. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Quellenservice Zugriffsberechtigung.</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>Die ID der Quellenserviceinstanz, die sich mit `--source-service-instance-name` gegenseitig ausschließt. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Quellenservice Zugriffsberechtigung.</dd>
  <dt>--source-resource-type</dt>
  <dd>Der Ressourcentyp des Quellenservice.</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Der Name der Zielserviceinstanz, die sich mit `--target-service-instance-id` gegenseitig ausschließt. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Zielservice Zugriffsberechtigung.</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>Die ID der Zielserviceinstanz, die sich mit `--target-service-instance-name` gegenseitig ausschließt. Wenn keine Angabe gemacht wird, erhalten alle Instanzen des Zielservice Zugriffsberechtigung.</dd>
  <dt>--target-resource-type</dt>
  <dd>Der Ressourcentyp des Zielservice.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Berechtigungsrichtlinie löschen:
```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>Die ID der zu löschenden Berechtigungsrichtlinie.</dd>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Details zu einer Berechtigungsrichtlinie anzeigen:
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>Die ID der anzuzeigenden Berechtigungsrichtlinie.</dd>
  <dt>--output FORMAT (optional)</dt>
  <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl> 

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Berechtigungsrichtlinien unter dem aktuellen Konto auflisten:
```
ibmcloud iam authorization-policies [--output FORMAT]
```
{: codeblock}

<strong>Voraussetzungen</strong>: Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--output FORMAT (optional)</dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
   </dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Zugriffsgruppen unter dem aktuellen Konto auflisten:
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-u</dt>
  <dd>Listet die Zugriffsgruppen auf, zu denen der Benutzer gehört. Dieses Flag wird ausschließlich mit '-s' verwendet.</dd>
  <dt>-s</dt>
  <dd>Listet die Zugriffsgruppen auf, zu denen die Service-ID gehört. Dieses Flag wird ausschließlich mit '-u' verwendet.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Zugriffsgruppen auflisten:
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Details einer Zugriffsgruppe anzeigen:
```
ibmcloud iam access-group GROUP_NAME [--id] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-id</dt>
  <dd>Nur ID anzeigen</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Details der Zugriffsgruppe `example_group` anzeigen:
```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Zugriffsgruppe erstellen:
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Beschreibung der Zugriffsgruppe</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Eine Zugriffsgruppe namens `example_group` erstellen:
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Zugriffsgruppe aktualisieren:
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Name der neuen Zugriffsgruppe</dd>
  <dt>-d, --description</dt>
  <dd>Neue Beschreibung</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
  <dt>-f, --force</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppe `example_group` in `hello_world_group` umbenennen:
```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Zugriffsgruppe löschen

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
  <dt>-r, --recursive</dt>
  <dd>Zugriffsgruppe und deren Mitglieder löschen</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppe `example_group` löschen:
```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Mehrere Benutzer in einer Zugriffsgruppe auflisten:
```
ibmcloud iam access-group-users GROUP_NAME [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Benutzer in der Zugriffsgruppe `example_group` auflisten:
```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Benutzer zu einer Zugriffsgruppe hinzufügen:
```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` zur Zugriffsgruppe `example_group` hinzufügen:
```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Einen Benutzer aus einer Zugriffsgruppe entfernen:
```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` aus der Zugriffsgruppe `example_group` entfernen:
```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Einen Benutzer aus allen Zugriffsgruppen entfernen:
```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Benutzer `name@example.com` aus allen Zugriffsgruppen entfernen:
```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Service-IDs in einer Zugriffsgruppe auflisten:
```
ibmcloud iam access-group-service-ids GROUP_NAME [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Service-IDs in der Zugriffsgruppe `example_group` auflisten:
```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Service-ID zu einer Zugriffsgruppe hinzufügen:
```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` zur Zugriffsgruppe `example_group` hinzufügen:
```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Service-ID aus Zugriffsgruppe entfernen:
```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` aus der Zugriffsgruppe `example_group` entfernen:
```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Service-ID aus allen Zugriffsgruppen entfernen:
```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `example-service` aus allen Zugriffsgruppen entfernen:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Richtlinien einer Zugriffsgruppe auflisten:
```
ibmcloud iam access-group-policies GROUP_NAME [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Alle Richtlinien der Zugriffsgruppe `example_group` auflisten:
```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Details einer Zugriffsgruppenrichtlinie anzeigen:
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Details der Richtlinie `51b9717e-76b0-4f6a-bda7-b8132431f926` der Zugriffsgruppe `example_group` anzeigen:
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Zugriffsgruppenrichtlinie erstellen:
```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition</dd>
  <dt>-roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppenrichtlinie aus einer JSON-Datei erstellen:
```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

`example_group` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`example_group` die Rolle `Editor` für die Ressource `key123` der Instanz `sample-service` mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`example_group` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

`example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuweisen:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Zugriffsgruppenrichtlinie aktualisieren:
```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--file</dt>
  <dd>Die JSON-Datei der Richtliniendefinition</dd>
  <dt>--roles</dt>
  <dd>Die Rollennamen der Richtliniendefinition. Für unterstützte Rollen eines bestimmten Service führen Sie `ibmcloud iam roles --service SERVICE_NAME` aus. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Der Servicename der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Die GUID der Serviceinstanz der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-region</dt>
  <dd>Die Region der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Der Ressourcentyp der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource</dt>
  <dd>Die Ressource der Richtliniendefinition. Diese Option ist gegenseitig ausschließend mit `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Der Name der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>Die ID der Ressourcengruppe. `*` bedeutet 'alle Ressourcengruppen'. Diese Option ist gegenseitig ausschließend mit `--file` und `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Ausgabeformat angeben. Nur 'JSON' wird unterstützt.</dd>
</dl>

<strong>Beispiele</strong>:

Zugriffsgruppenrichtlinie mit der Richtlinie in der Richtlinien-JSON-Datei aktualisieren:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Administrator` für alle Ressourcen von `sample-service` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Editor` für die Ressource `key123` der Instanz `sample-service` mit der GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` in der Region `us-south` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Operator` für die Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Anzeigeberechtigter` für die Mitglieder der Ressourcengruppe `sample-resource-group` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Zugriffsgruppenrichtlinie aktualisieren, um `example_group` die Rolle `Anzeigeberechtigter` für Mitglieder der Ressourcengruppe mit der ID `dda27e49d2a1efca58083a01dfde18f6` zuzuweisen:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Zugriffsgruppenrichtlinie löschen:
```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Löschen ohne Bestätigung erzwingen</dd>
</dl>

<strong>Beispiele</strong>:

Richtlinie `51b9717e-76b0-4f6a-bda7-b8132431f926` der Zugriffsgruppe `example_group` löschen:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
