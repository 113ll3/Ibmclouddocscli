---

copyright:
  years: 2016, 2019
lastupdated: "2019-04-10"

keywords: cli, cf commands, cloud foundry commands, cloud foundry cli, cf apps, cf help, cf logs, cf api

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:note: .note}

# Mit cf-Befehlen arbeiten
{: #cf}

Die Befehlszeilenschnittstelle (CLI) von Cloud Foundry (CF) stellt Befehle bereit, mit denen Sie Ihre Apps verwalten können. In der nachfolgenden Liste sind die für die App-Verwaltung am häufigsten verwendeten cf-Befehle mit Namen, Optionen, Nutzungen, Voraussetzungen, Beschreibungen und Beispielen aufgeführt. Um alle cf-Befehle und die zugehörigen Hilfeinformationen aufzulisten, verwenden Sie `cf help`. Mit dem Befehl `cf command_name -h` können Sie detaillierte Hilfeinformationen zu einem bestimmten Befehl anzeigen.
{: shortdesc}

Weitere Informationen zum Einstieg in die Cloud Foundry-CLI finden Sie in [Getting Started](https://github.com/cloudfoundry/cli#getting-started){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

Eine detailliertere Liste von `cf CLI`-Befehlen finden Sie in der Community im [Cloud Foundry CLI Reference Guide](https://docs.cloudfoundry.org/cf-cli/cf-help.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

Wenn sich in Ihrem Netz zwischen dem Host, auf dem die cf-Befehle ausgeführt werden, und dem Cloud Foundry-API-Endpunkt ein HTTP-Proxy-Server befindet, müssen Sie den Hostnamen oder die IP-Adresse des Proxy-Servers durch Festlegung der Umgebungsvariablen `HTTP_PROXY` angeben. Details finden Sie in [Using the cf CLI with a Proxy Server](https://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").
{: note}

## Index für Befehle der Cloud Foundry-CLI
{: #CLIname_commands_index}

Verwenden Sie den Index in der folgenden Tabelle als Referenz für die häufig verwendeten Cloud Foundry-Befehle:

<table summary="Allgemeine Cloud Foundry-Befehle in alphabetischer Reihenfolge mit Links zu näheren Befehlsinformationen">
<caption>Tabelle 1. Allgemeine Cloud Foundry-Befehle</caption>
 <thead>
 <th colspan="6">Allgemeine Cloud Foundry-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[api](#cf_api)</td>
 <td>[help](#cf_help)</td>
 <td>[login](#cf_login)</td>
 <td>[stacks](#cf_stacks)</td>
 <td>[target](#cf_target)</td>
 <td>[-v ](#cf_v)</td>
 </tr>
   </tbody>
 </table>

<table summary="Befehle zur Verwaltung von Apps, Bereichen und Services in alphabetischer Reihenfolge. Jeder Befehl verfügt über einen Link, der Ihnen weitere Informationen zu dem Befehl gibt.">
<caption>Tabelle 2. Befehle zur Verwaltung von Apps, Bereichen und Services</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von Apps, Bereichen und Services</th>
 </thead>
 <tbody>
 <tr>
 <td>[apps](#cf_apps)</td>
 <td>[bind-service](#cf_bind-service)</td>
 <td>[create-service](#cf_create-service)</td>
 <td>[create-space](#cf_create-space)</td>
 <td>[delete](#cf_delete)</td>
  </tr>
 <tr>
 <td>[delete-space](#cf_delete-space)</td>
 <td>[events](#cf_events)</td>
 <td>[Protokolle](#cf_logs)</td>
 <td>[marketplace](#cf_marketplace)</td>
 <td>[Push-Operation](#cf_push)</td>
  </tr>
 <tr>
 <td>[scale](#cf_scale)</td>
 <td>[services](#cf_services)
 <td>[set-env](#cf_set-env)</td>
 <td>[ssh](#cf_ssh)</td>
 <td>[stop](#cf_stop)</td>
 </tr>
 </tbody>
 </table>

## cf api
{: #cf_api}

Verwenden Sie diesen Befehl, um die URL des API-Endpunkts von {{site.data.keyword.cloud}} anzuzeigen oder anzugeben.
```
cf api [URL] [--skip-ssl-validation] [--unset]
```

<strong>Voraussetzungen</strong>: keine.

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>URL (optional)</dt>
   <dd>Die URL des {{site.data.keyword.cloud_notm}}-API-Endpunkts, die Sie für das Herstellen einer Verbindung zu {{site.data.keyword.cloud_notm}} angeben müssen. In der Regel ist diese URL `https://api.<REGION>.cf.{DomainName}`.
   Wenn Sie die URL des API-Endpunkts anzeigen möchten, den Sie zurzeit verwenden, müssen Sie diesen Parameter für den Befehl 'cf api' nicht angeben.</dd>
   <dt>* --skip-ssl-validation</dt>
   <dd>Inaktiviert den Prozess der SSL-Validierung. Die Verwendung dieses Parameters kann zu Sicherheitsproblemen führen.</dd>
   <dt>* --unset</dt>
   <dd>Entfernt Verbindungsinformationen für alle API-Endpunkte.</dd>
   </dl>

<strong>Beispiele</strong>:

Aktuellen API-Endpunkt anzeigen:
```
cf api
```
{: codeblock}

Verbindung zu allen API-Endpunkten für api.us-south.cf.cloud.ibm.com entfernen:
```
cf api api.us-south.cf.cloud.ibm.com --unset
```
{: codeblock}

SSL-Validierungsprozess für api.us-south.cf.cloud.ibm.com inaktivieren:
```
cf api api.us-south.cf.cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

## cf apps
{: #cf_apps}

Listet alle Anwendungen auf, die Sie im aktuellen Bereich bereitgestellt haben. Der Status der einzelnen Anwendungen wird auch angezeigt.

Nehmen Sie an, dass Sie über eine einzige Instanz für eine App verfügen und in der Instanzenspalte der Antwort auf den Befehl 'cf apps' 1/1 angezeigt wird, falls die App aktiv ist und 0/1, wenn die App inaktiv ist. Wenn der Status der App-Instanz ?/1 (unbekannt) ist, können Sie die App-URL in Ihren Browser kopieren und prüfen, ob die App antwortet, oder Sie können das Protokoll zurate ziehen; verwenden Sie hierfür den Befehl `cf logs appname`, um zu sehen, ob die App Protokollinhalt generiert.

```
cf apps
```
{: codeblock}

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

## cf bind-service
{: #cf_bind-service}

Bindet eine vorhandene Serviceinstanz an Ihre Anwendung.

```
cf bind-service appname service_instance
```
{: codeblock}

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>appname (erforderlich)</dt>
   <dd>Der Name der Anwendung.</dd>
   <dt>service_instance (erforderlich)</dt>
   <dd>Der Name der vorhandenen Serviceinstanz.</dd>
    </dl>

<strong>Beispiele</strong>:

Binden einer Serviceinstanz mit dem Namen `my_dataworks` an eine App mit dem Namen `my_app`.
```
cf bind-service my_app my_dataworks
```
{: codeblock}


## cf create-service
{: #cf_create-service}

Erstellen einer Serviceinstanz.

```
cf create-service service_name service_plan service_instance
```
{: codeblock}

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>service_name (erforderlich)</dt>
   <dd>Der Name des Service.</dd>
   <dt>service_plan (erforderlich)</dt>
   <dd>Der Name des Serviceplans.</dd>
   <dt>service_instance (erforderlich)</dt>
   <dd>Der Name, den Sie für die neue von Ihnen erstellte Serviceinstanz verwenden möchten.</dd>
    </dl>

<strong>Beispiele</strong>:

Erstellen einer Instanz des {{site.data.keyword.dataworks_short}}-Service mit einem `kostenfreien` Plan.
```
cf create-service DataWorks free my_dataworks
```
{: codeblock}


## cf create-space
{: #cf_create-space}

Erstellt einen Bereich.

```
cf create-space space_name [-o] [-q]
```

<strong>Voraussetzungen</strong>: `cf api`, `cf login`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>space_name (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   <dt>*-o* (optional)</dt>
   <dd>Der Name der Organisation, in der Sie einen Bereich erstellen möchten.</dd>
   <dt>*-q* (optional)</dt>
   <dd>Das Kontingent, das dem neue erstellten Bereich zugeordnet werden soll. Wenn keine Angabe festgelegt wird, wird automatisch ein Standardkontingent zugeordnet.</dd>
    </dl>

<strong>Beispiele</strong>:

Erstellen eines Bereichs mit dem Namen new_space
```
cf create-space new_space
```
{: codeblock}


## cf delete
{: #cf_delete}

Löscht eine vorhandene Anwendung.

```
cf delete appname [-f] [-r]
```

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>appname (erforderlich)</dt>
   <dd>Der Name der Anwendung.</dd>
   <dt>*-f* (optional)</dt>
   <dd>Erzwingt die Löschung der Anwendung ohne Bestätigung.</dd>
   <dt>*-r* (optional)</dt>
   <dd>Löscht alle Domänennamen, die der Anwendung zugeordnet sind. </dd>
    </dl>

<strong>Beispiele</strong>:

Löscht eine Anwendung mit dem Namen `my_app` (erfordert eine Bestätigung).
```
cf delete my_app
```
{: codeblock}

Löschen einer Anwendung mit dem Namen `my_app` ohne erforderliche Bestätigung.
```
cf delete my_app -f
```
{: codeblock}

Löschen einer Anwendung mit dem Namen `my_app` und aller Domänennamen, die `my_app` zugeordnet sind.
```
cf delete my_app -r
```
{: codeblock}

Löschen einer Anwendung mit dem Namen `my_app` und aller Domänennamen, die `my_app` zugeordnet sind, ohne erforderliche Bestätigung.
```
cf delete my_app -f -r
```
{: codeblock}


## cf delete-space
{: #cf_delete-space}

Löscht einen Bereich.
```
cf delete-space space_name [-f]
```

<strong>Voraussetzungen</strong>: `cf api`, `cf login`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>space_name (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   <dt>*-f* (optional)</dt>
   <dd>Erzwingt die Löschung des Bereichs ohne Bestätigung.</dd>
   *Hinweis:* Das Löschen eines Bereichs ist eine Operation, die nicht rückgängig gemacht werden kann.
   </dl>

<strong>Beispiele</strong>:

Löscht eine Anwendung mit dem Namen `my_app` (erfordert eine Bestätigung).
```
cf delete my_app
```
{: codeblock}

Löschen einer Anwendung mit dem Namen `my_app` ohne erforderliche Bestätigung.
```
cf delete my_app -f
```
{: codeblock}

Löschen einer Anwendung mit dem Namen `my_app` und aller Domänennamen, die `my_app` zugeordnet sind.
```
cf delete my_app -r
```
{: codeblock}

Löscht eine Anwendung mit dem Namen `my_app` und alle Domänen, die `my_app` zugeordnet sind, ohne erforderliche Bestätigung.
```
cf delete my_app -f -r
```
{: codeblock}


## cf events
{: #cf_events}

Zeigt Laufzeitereignisse an, die sich auf eine Anwendung beziehen.

```
cf events [appname]
```
{: codeblock}

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>appname</dt>
   <dd>Der Name der Anwendung.</dd>
   </dl>

<strong>Beispiele</strong>:

Anzeigen der Ereignisse für eine Anwendung mit dem Namen `my_app`.
```
cf events my_app
```
{: codeblock}


## cf help
{: #cf_help}

Anzeigen von Hilfeinformationen für alle cf-Befehle oder für einen bestimmten cf-Befehl.

```
cf help [command_name]
```
{: codeblock}

<strong>Voraussetzungen</strong>: keine.

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>command_name (optional)</dt>
   <dd>Der Name eines Befehls.</dd>
    </dl>

<strong>Beispiele</strong>:

Anzeigen von Hilfeinformationen für alle cf-Befehle.
```
cf help
```
{: codeblock}

Anzeigen der Hilfeinformationen für den Befehl 'events'.
```
cf help events
```
{: codeblock}


## cf login
{: #cf_login}

Hiermit melden Sie sich bei {{site.data.keyword.cloud_notm}} an. Wenn Sie sich mit einer föderierten ID anmelden, müssen Sie den SSO-Parameter (SSO - Single Sign-on) zum Anmelden verwenden.

Sie können für die Anmeldung auch einen API-Schlüssel für die {{site.data.keyword.cloud_notm}}-Plattform verwenden. Verwenden Sie den Benutzernamen `apikey` und Ihren API-Schlüsselwert als Kennwort. Weitere Informationen zum Erstellen eines API-Schlüssels finden Sie im Abschnitt mit [Informationen zu API-Schlüsseln](/docs/iam?topic=iam-manapikey#manapikey).
{: note}

```
cf login [-a url] [-u user_name] [-p password] [-sso] [-o organization_name] [-s space_name] [--skip-ssl-validation]
```

<strong>Voraussetzungen</strong>: keine.

<strong>Befehlsoptionen</strong>:

<dl>
<dt>*-a* https://api.<REGION>.cf.{DomainName} (optional)</dt>
<dd>Die URL des API-Endpunkts von {{site.data.keyword.cloud_notm}}.</dd>
<dt>*-u* user_name (optional)</dt>
<dd>Ihr Benutzername.</dd>
<dt>*-p* password (optional)</dt>
<dd>Ihr Kennwort.</dd>
<dd>*Wichtig* Wenn Sie Ihr Kennwort mithilfe des Parameters *-p* in der Befehlszeilenschnittstelle angeben, wird es möglicherweise im Befehlszeilenprotokoll aufgezeichnet. Sie sollten aus Sicherheitsgründen das Kennwort nicht mithilfe des Parameters -p angeben. Geben Sie stattdessen das Kennwort ein, wenn Sie in der Befehlszeilenschnittstelle dazu aufgefordert werden.</dd>
<dt>*-sso*</dt>
<dd>Sie müssen die SSO-Option (SSO - Single Sign-on) verwenden, wenn Sie sich mit einer föderierten ID anmelden. Dies ist nicht erforderlich, wenn Sie sich mit einer IBMid anmelden. Wenn Sie versuchen, sich mit einer föderierten ID anzumelden und dabei keinen SSO-Parameter angeben, werden Sie aufgefordert, den Parameter anzugeben. Bei Verwendung des SSO-Parameters werden Sie aufgefordert, beim Anmelden den einmaligen Kenncode einzugeben.</dd>
<dt>*-o* organization_name</dt>
<dd>Der Name der Organisation, bei der Sie sich anmelden möchten.</dd>
<dt>*-s* space_name</dt>
<dd>Der Name des Bereichs, bei dem Sie sich anmelden möchten.</dd>
<dt>*--skip-ssl-validation* (optional)</dt>
<dd>Inaktiviert den Prozess der SSL-Validierung. Die Verwendung dieses Parameters kann zu Sicherheitsproblemen führen.</dd>
</dl>

*Hinweis:* Wenn Sie im Parameter *-p* dieses Befehls Ihr Kennwort angeben, wird Ihr Kennwort möglicherweise in der Protokolldatei des Shellbefehls aufgezeichnet und kann für andere Benutzer des lokalen Betriebssystem sichtbar sein.

<strong>Beispiele</strong>:

Melden Sie sich bei {{site.data.keyword.cloud_notm}} an.
```
cf login
```
{: codeblock}

Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit dem definierten Endpunkt `https://api.us-south.cf.cloud.ibm.com` an.
```
cf login -a https://api.us-south.cf.cloud.ibm.com
```
{: codeblock}

Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit dem definierten Endpunkt `https://api.us-south.cf.cloud.ibm.com`, dem Benutzernamen `user_name` und aus Sicherheitsgründen ohne Angabe eines Kennworts an.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u user_name
```
{: codeblock}

Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit dem definierten Endpunkt `https://api.us-south.cf.cloud.ibm.com`, dem Benutzernamen `user_name` (aus Sicherheitsgründen ohne Angabe des Kennworts), dem Organisationsnamen `org_name` und dem Bereichsnamen `space_name` an.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u user_name -o org_name -s space_name
```
{: codeblock}

Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit dem definierten Endpunkt `https://api.us-south.cf.cloud.ibm.com` unter Verwendung eines API-Schlüssels an. Verwenden Sie `apikey` als Benutzernamen und den tatsächlichen API-Schlüssel als Kennwort.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u apikey -p ThisValueIsYourAPIKey
```
{: codeblock}

Sie können sich an den folgenden regionalen Cloud Foundry-API-Endpunkten anmelden:
* api.us-south.cf.cloud.ibm.com  (vorher api.ng.bluemix.net)
* api.eu-gb.cf.cloud.ibm.com     (vorher api.eu-gb.bluemix.net)
* api.us-east.cf.cloud.ibm.com   (vorher api.us-east.bluemix.net)
* api.eu-de.cf.cloud.ibm.com     (vorher api.eu-de.bluemix.net)
* api.au-syd.cf.cloud.ibm.com    (vorher api.au-syd.bluemix.net)

Die traditionellen "api.<REGION>.bluemix.net" Cloud Foundry-API-Endpunkte sind noch gültig, werden aber demnächst nicht mehr unterstützt.
{: note}

## cf logs
{: #cf_logs}

Zeigt die Protokolldatenströme STDOUT und STDERR einer Anwendung an.

```
cf logs appname [--recent]
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname</dt>
<dd>Der Name der Anwendung.</dd>
<dt>*--recent* (optional)</dt>
<dd>Ruft letzte Protokolle ab.</dd>
</dl>

<strong>Beispiele</strong>:

Anzeigen der Protokolldatenströme für eine Anwendung mit dem Namen `my_app`.
```
cf logs my_app
```
{: codeblock}

Anzeigen der letzten Protokolldatenströme für eine Anwendung mit dem Namen `my_app`.
```
cf logs my_app --recent
```
{: codeblock}


## cf marketplace
{: #cf_marketplace}

Listet alle Services auf, die im Marktplatz verfügbar sind. Die von diesem Befehl aufgeführten Services werden auch im {{site.data.keyword.cloud_notm}}-Katalog angezeigt.

```
cf marketplace
```
<strong>Voraussetzungen</strong>: `cf api`

<strong>Befehlsoptionen</strong>: keine.

<strong>Beispiele</strong>:

Auflisten aller Services im Marktplatz
```
cf marketplace
```
{: codeblock}


## cf push
{: #cf_push}

Bereitstellen einer neuen Anwendung in {{site.data.keyword.cloud_notm}} oder Aktualisieren einer vorhandenen Anwendung in {{site.data.keyword.cloud_notm}}.

```
cf push appname [-b buildpack_name] [-c start_command] [-f manifest_path] [-i instance_number] [-k disk_limit] [-m memory_limit] [-n host_name] [-p app_path] [-s stack_name] [-t timeout_length] [--no-hostname] [--no-manifest] [--no-route] [--no-start] [--random-route]
```

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname (erforderlich)</dt>
<dd>Der Name der Anwendung.</dd>
<dt>*-b* buildpack_name (optional)</dt>
<dd>Der Name des Buildpacks. Der Name des Buildpacks (buildpack_name) kann der Name eines benutzerdefinierten Buildpacks (z. B. liberty-for-java) oder eine Git-URL (z. B. https://github.com/cloudfoundry/java-buildpack) oder eine Git-URL mit einem Zweig oder Tag sein (z. B. https://github.com/cloudfoundry/java-buildpack#v3.3.0 für den V3.3.0-Tag).</dd>
<dt>*-c* start_command (optional)</dt>
<dd>Der Startbefehl Ihrer Anwendung. Geben Sie für die Verwendung des standardmäßigen Startbefehls für diese Option den Wert null an. </dd>
<dt>*-f* manifest_path (optional)</dt>
<dd>Der Pfad zur Manifestdatei. Die Standardmanifestdatei lautet 'manifest.yml'. Sie befindet sich im Stammverzeichnis der Anwendung.</dd>
<dt>*-i* instance_number (optional)</dt>
<dd>Die Anzahl der Instanzen.</dd>
<dt>*-k* disk_limit (optional)</dt>
<dd>Der Plattengrenzwert für die Anwendung. Mögliche Werte: *256M*, *1024M* oder *1G*.</dd>
<dt>*-m* memory_limit (optional)</dt>
<dd>Die Speicherbegrenzung für die Anwendung. Mögliche Werte: *256M*, *1024M* oder *1G*.</dd>
<dt>*-n* host_name (optional)</dt>
<dd>Der Hostname für die Anwendung, zum Beispiel *my-subdomain*.</dd>
<dt>*-p* app_path (optional)</dt>
<dd>Der Pfad zum Anwendungsverzeichnis oder zur Archivdatei des Anwendungsverzeichnisses.</dd>
<dt>*-s* stack_name (optional)</dt>
<dd>Der Stack zum Ausführen der Apps. Ein Stack ist ein vorgefertigtes Dateisystem einschließlich Betriebssystem. Mit `cf stacks` können Sie die in {{site.data.keyword.Bluemix_notm}} verfügbaren Stacks anzeigen.</dd>
<dt>*-t* timeout (optional)</dt>
<dd>Die maximale Zeit für den Start der Anwendung in Sekunden. Möglicherweise wird dieser Wert durch andere serverseitige Zeitlimits überschrieben.</dd>
<dt>*--no-hostname* (optional)</dt>
<dd>Ordnet dieser Anwendung die {{site.data.keyword.cloud_notm}}-Systemdomäne zu.</dd>
<dt>*--no-manifest* (optional)</dt>
<dd>Führt dazu, dass die Standardmanifestdatei ignoriert wird.</dd>
<dt>*--no-route* (optional)</dt>
<dd>Keine Route zu dieser Anwendung zuordnen.</dd>
<dt>*--no-start* (optional)</dt>
<dd>Verhindert, dass die Anwendung nach der Bereitstellung gestartet wird.</dd>
<dt>*--random-route* (optional)</dt>
<dd>Erstellt eine zufällige Route für die Anwendung.</dd>
</dl>

<strong>Beispiele</strong>:

Starten einer Anwendung mit dem Namen `my_app` mit dem Standard-Startbefehl.
```
cf push `my_app` -c null
```
{: codeblock}

Starten einer Anwendung mit dem Namen `my_app` und der Option, eine Scriptdatei mit dem Namen `run.sh` auszuführen.
```
cf push `my_app` -c "bash ./<run.sh>"
```
{: codeblock}



## cf scale
{: #cf_scale}

Zeigt die Anzahl der Instanzen, die Platten- und die Speicherbegrenzung für eine Anwendung an bzw. ändert die entsprechenden Werte.

```
cf scale appname [-i instance_number] [-k disk_limit] [-m memory_limit] [-f]
```

<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname (erforderlich)</dt>
<dd>Der Name der Anwendung.</dd>
<dt>*-i* instance_number (optional)</dt>
<dd>Die Anzahl der Instanzen.</dd>
<dt>*-k* disk_limit (optional)</dt>
<dd>Die Plattenbegrenzung für die Anwendung; mögliche Werte sind `256M`, `1024M` oder `1G`.</dd>
<dt>*-m* memory_limit (optional)</dt>
<dd>Die Speicherbegrenzung für die Anwendung, mögliche Werte sind `256M`, `1024M` oder `1G`.</dd>
<dt>*-f* (optional)</dt>
<dd>Erzwingt den Neustart der Anwendung ohne Eingabeaufforderung.</dd>
</dl>

<strong>Beispiele</strong>:

Anzeigen der Anzahl der Instanzen, der Platten- und der Speicherbegrenzung für eine Anwendung mit dem Namen `my_app`.
```
cf scale my_app
```
{: codeblock}

Ändern der Anzahl der Instanzen zu `1234`, der Plattenspeicherbegrenzung zu `1G` und der Speicherbegrenzung zu `1G` für eine App mit dem Namen `my_app`.
```
cf scale appname -i 1234 -k 1G -m 1G
```
{: codeblock}


## cf services
{: #cf_services}

Listet alle Services auf, die im aktuellen Bereich verfügbar sind.

```
cf services
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>: keine.

<strong>Beispiele</strong>:

Auflisten aller Services im aktuellen Bereich.
```
cf services
```
{: codeblock}


## cf set-env
{: #cf_set-env}

Festlegen einer Umgebungsvariablen für eine Anwendung.

```
cf set-env appname var_name var_value
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname (erforderlich)</dt>
<dd>Der Name der Anwendung.</dd>
<dt>var_name (erforderlich)</dt>
<dd>Der Name der Umgebungsvariable.</dd>
<dt>var_value (erforderlich)</dt>
<dd>Der Wert der Umgebungsvariable.</dd>
</dl>

<strong>Beispiele</strong>:

Festlegen einer Umgebungsvariablen mit dem Namen `variable_a` und dem Wert `123` für die Anwendung mit dem Namen `my_app`.
```
cf set-env my_app variable_a 123
```
{: codeblock}


## cf ssh
{: #cf_ssh}

Greifen Sie sicher auf den Anwendungscontainer zu. Der Befehl `cf ssh` kann verwendet werden, um eine interaktive SSH-Sitzung einzurichten, Fernbefehle auszuführen, Dateien zu übertragen und die Portweiterleitung mit einer bestimmten Anwendungscontainerinstanz einzurichten.

```
cf ssh
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

Standardmäßig ist SSH-Zugriff für Diego-Anwendungen aktiviert. Sie können den Befehl `cf ssh-enabled` verwenden, um zu überprüfen, ob der SSH-Zugriff für den Befehl `cf enable-ssh` aktiviert ist, oder Sie können diesen Zugriff aktivieren, falls er inaktiviert wurde.

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname</dt>
<dd>Der Name der Anwendung.</dd>
<dt>-c</dt>
<dd>Gibt einen auszuführenden Fernbefehl an.</dd>
<dt>-i</dt>
<dd>Gibt eine bestimmte Instanz einer Anwendung als Ziel an. Bei keiner Angabe wird die erste Instanz der Anwendung verwendet (eine Instanz mit dem Index 0).</dd>
<dt>-L</dt>
<dd>Aktiviert die Weiterleitung für den lokalen Port, die einen Ausgabeport auf Ihrer Maschine an einen Eingabeport auf der Anwendungs-VM bindet.</dd>
<dt>-N</dt>
<dd>Gibt an, dass kein ferner Befehl ausgeführt werden soll.</dd>
<dt>-t, -tt oder -T</dt>
<dd>Ermöglicht Ihnen die Ausführung einer SSH-Sitzung im Pseudo-TTY-Modus, statt eine Zeilenausgabe am Terminal zu generieren.<dd>
</dl>

<strong>Beispiele</strong>:

Mit diesem Befehl wird eine interaktive SSH-Sitzung gestartet, bei der die Containerinstanz die Anwendung `my_app` ausführt.
```
$ cf ssh my_app
```
{: codeblock}

Nachstehend wird ein einzelner Befehl für die Containerinstanz der Anwendung `my_app` ausgeführt.
```
$ cf ssh my_app -c "ls -l"
```

Mit diesem Befehl wird eine einzelne Datei aus der Containerinstanz der Anwendung `my_app` übertragen.
```
$ cf ssh my_app -c "/bin/cat logs/messages.log" > messages.log
```

Mit diesem Befehl wird die Portweiterleitung von Port 7777 auf der lokalen Maschine an Port 8888 auf der Containerinstanz der Anwendung `my_app` eingerichtet.
```
$ cf ssh -N -T -L 7777:localhost:8888 my_app

```

## cf stacks
{: #cf_stacks}

Mit diesem Befehl werden alle Stacks aufgeführt. Ein Stack ist ein vordefiniertes Dateisystem einschließlich eines Betriebssystems, das Apps ausführen kann.

```
cf stacks
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`

<strong>Befehlsoptionen</strong>: keine.

<strong>Beispiele</strong>:

Auflisten aller Stacks.
```
cf stacks
```
{: codeblock}


## cf stop
{: #cf_stop}

Stoppen einer Anwendung

```
cf stop appname
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`, `cf target`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>appname (erforderlich)</dt>
<dd>Der Name der Anwendung.</dd>
</dl>

<strong>Beispiele</strong>:

Stoppen der Anwendung mit dem Namen `my_app`.
```
cf stop my_app
```
{: codeblock}


## cf target
{: #cf_target}

Festlegen oder Anzeigen der Zielorganisation oder des Zielbereichs.

```
cf target [-o org_name] [-s space_name]
```
<strong>Voraussetzungen</strong>: `cf api`, `cf login`

<strong>Befehlsoptionen</strong>:

<dl>
<dt>-o *org_name* (optional)</dt>
<dd>Der Name der Organisation, in der sich der Bereich befindet.</dd>
<dt>-s *space_name* (optional)</dt>
<dd>Der Name des Bereichs.</dd>
</dl>

<strong>Beispiele</strong>:

Festlegen des Ziels auf die Organisation mit dem Namen "my_org" und den Bereich mit dem Namen "my_space".
```
cf target -o my_org -s my_space
```
{: codeblock}


## cf -v
{: #cf_v}

Anzeigen der Version der Cloud Foundry-Befehlszeilenschnittstelle.

```
cf -v
```
<strong>Voraussetzungen</strong>: keine.

<strong>Befehlsoptionen</strong>: keine.

<strong>Beispiele</strong>:

Anzeigen der Version der Cloud Foundry-Befehlszeilenschnittstelle.
```
cf -v
```
{: codeblock}


## Zugehörige Links
{: #cf-related}

* [Cloud Foundry-CLI herunterladen](https://github.com/cloudfoundry/cli/releases){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
* [Referenzkarte - cf-Befehle](ftp://public.dhe.ibm.com/cloud/bluemix/cf_cli_refcard.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")
