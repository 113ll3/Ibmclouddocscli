---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Allgemeine CLI-Befehle (ibmcloud)
{: #ibmcloud_cli}

Von der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle (CLI) werden Befehle bereitgestellt, die nach Namensbereich für Benutzer zur Interaktion mit {{site.data.keyword.cloud_notm}} zusammengefasst sind.

Der {{site.data.keyword.cloud_notm}}-Befehlszeilenclient enthält im Installationspaket einen Cloud Foundry-Befehlszeilenclient. Wenn Sie eine eigene Cloud Foundry-Befehlszeilenschnittstelle installiert haben, dann verwenden Sie die Befehle der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle (CLI) vom Typ `ibmcloud [command]` und die Befehle der Cloud Foundry-CLI vom Typ `cf [command]` Ihrer eigenen Installation nicht in demselben Kontext. Verwenden Sie stattdessen  `ibmcloud cf [command]`, wenn Sie Cloud Foundry-Ressourcen mit der Cloud Foundry-Befehlszeilenschnittstelle (CF-CLI) im Kontext der {{site.data.keyword.cloud_notm}}-CLI verwalten wollen. Beachten Sie, dass `ibmcloud cf api/login/logout/target` nicht zulässig ist und Sie stattdessen `ibmcloud api/login/logout/target` verwenden müssen.

Ab Mai 2018 wird an Stelle der {{site.data.keyword.cloud_notm}}-CLI-Befehle `bluemix` und `bx` künftig der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch weiterhin verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

In der nachfolgenden Liste finden Sie detaillierte Angaben zu den von der {{site.data.keyword.cloud_notm}}-CLI unterstützten Befehlen mit zugehörigen Namen, Argumenten, Optionen, Voraussetzungen, Beschreibungen und Beispielen.
{: shortdesc}

Unter *Voraussetzungen* wird aufgelistet, welche Aktionen vor der Verwendung des Befehls ausgeführt werden müssen. Für Befehle, für die keine Voraussetzungen erfüllt sein müssen, ist **Keine** angegeben. Andernfalls kann mindestens eine der folgenden Aktionen eine Voraussetzung sein:

<dl>
<dt>Endpunkt</dt>
<dd>Vor der Verwendung des Befehls muss mittels <code>ibmcloud api</code> ein API-Endpunkt festgelegt werden.</dd>
<dt>Anmeldung</dt>
<dd>Vor der Verwendung dieses Befehls ist die Anmeldung über den Befehl <code>ibmcloud login</code> erforderlich.
Verwenden Sie beim Anmelden mit einer föderierten ID die Option '--sso' für die Anmeldung mit einmaligem Kenncode oder verwenden Sie die Option '--apikey' für die Authentifizierung mit einem API-Schlüssel.
</dd>
<dt>Ziel</dt>
<dd>Vor der Verwendung dieses Befehls muss der Befehl <code>ibmcloud target</code> zum Festlegen einer Organisation oder eines Bereichs verwendet werden.</dd>
<dt>Docker</dt>
<dd>Die Docker-CLI (docker) muss installiert werden, um diesen Befehl auszuführen.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Zeigt die erweiterte Hilfe für integrierte Befehle und unterstützte Namensbereiche der obersten Ebene in der {{site.data.keyword.cloud_notm}}-CLI oder die Hilfe für einen bestimmten integrierten Befehl oder Namensbereich an.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (optional)</dt>
   <dd>Der Befehl oder Namensbereich, für den die Hilfe angezeigt wird. Wenn nichts angegeben ist, wird die erweiterte Hilfe für die {{site.data.keyword.Bluemix_notm}}-CLI angezeigt.</dd>
   </dl>

<strong>Beispiele</strong>:

Erweiterte Hilfe für die {{site.data.keyword.cloud_notm}}-CLI anzeigen:
```
ibmcloud help
```
{: codeblock}

Hilfe für den Befehl `info` anzeigen:
```
ibmcloud help info
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

{{site.data.keyword.cloud_notm}}-API-Endpunkt festlegen oder anzeigen.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>API_ENDPOINT (optional)</dt>
   <dd>Der API-Endpunkt, der als Ziel verwendet wird, zum Beispiel `https://cloud.ibm.com`. Wenn weder die Option *API_ENDPOINT* noch die Option `--unset`  angegeben wird, wird der aktuelle API-Endpunkt angezeigt.</dd>
   <dt>--unset (optional)</dt>
   <dd>Entfernt die Einstellung für den API-Endpunkt.</dd>
   <dt>--skip-ssl-validation (optional)</dt>
   <dd>Umgeht die SSL-Validierung von HTTP-Anforderungen.</dd>
   </dl>
<strong>Beispiele</strong>:

Für den API-Endpunkt cloud.ibm.com festlegen:
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

Aktuellen API-Endpunkt anzeigen:
```
ibmcloud api
```
{: codeblock}

Definition für den API-Endpunkt rückgängig machen:
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Standardwerte in die Konfigurationsdatei schreiben.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Der Zeitlimitwert für HTTP-Anforderungen. Der Standardwert ist 60 Sekunden.</dd>
   <dt>--trace true|false|<i>Dateipfad</i></dt>
   <dd>Trace für HTTP-Anforderungen mit Ausgabe auf Terminal oder in angegebener Datei aktivieren.</dd>
   <dt>--color true|false</dt>
   <dd>Farbausgabe aktivieren oder inaktivieren. Die Farbausgabe ist standardmäßig aktiviert.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Eine Standardländereinstellung festlegen. Wenn LOCALE den Wert <i>CLEAR</i> hat, wird die vorherige Ländereinstellung gelöscht.</dd>
   <dt>--check-version true|false</dt>
   <dd>CLI-Versionsprüfung aktivieren oder inaktivieren.</dd>
   </dl>

Es kann jeweils nur eine dieser Optionen gleichzeitig angegeben werden.

<strong>Beispiele</strong>:

HTTP-Anforderungszeitlimit auf 30 Sekunden setzen:
```
ibmcloud config --http-timeout 30
```
{: codeblock}

Traceausgabe für HTTP-Anforderungen aktivieren:
```
ibmcloud config --trace true
```
{: codeblock}

Traceausgabe für HTTP-Anforderungen in eine angegebene Datei */home/usera/my_trace* schreiben:
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Farbausgabe inaktivieren:
```
ibmcloud config --color false
```
{: codeblock}

Ländereinstellung auf 'zh_Hans' setzen:
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

Ländereinstellungen löschen:
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

Der Befehl `ibmcloud info` ist ab der CLI-Version `0.14` nicht mehr verfügbar. Informationen zum Installieren der aktuellen CLI-Version finden Sie in [Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

Eingebettete CF-CLI aufrufen
```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Nachricht "Befehl cf wird aufgerufen..." inaktivieren</dd>
</dl>

<strong>Beispiele</strong>:

CF-Apps auflisten

```
ibmcloud cf apps
```

CF-Services ohne Nachricht "Befehl cf wird aufgerufen..." auflisten:
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Benutzer anmelden.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>Voraussetzungen</strong>: Keine

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Befehlsoptionen</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (optional)</dt>
  <dd> API-Endpunkt (z. B. cloud.ibm.com)</dd>
  <dt> --apikey <i>API_KEY oder @API_KEY_FILE_PATH</i>
  <dd> API-Schlüsselinhalt oder der Pfad einer API-Schlüsseldatei, der durch @ angegeben wird.</dd>
  <dt> --sso (optional) </dt>
  <dd> Verwenden Sie einen einmaligen Kenncode für die Anmeldung. </dd>
  <dt> -u <i>USERNAME</i> (optional)</dt>
  <dd> Der Benutzername.</dd>
  <dt> -p <i>PASSWORD</i> (optional)</dt>
  <dd> Das Kennwort.</dd>
  <dt> -c <i>ACCOUNT_ID</i> (optional) </dt>
  <dd> ID des Zielkontos. Diese Option ist gegenseitig ausschließend mit '--no-account'.</dd>
  <dt> --no-account (optional) </dt>
  <dd> Anmeldung ohne Konto erzwingen. Diese Option wird nicht empfohlen. Diese Option ist gegenseitig ausschließend mit '-c'.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional) </dt>
  <dd> Name der Zielressourcengruppe</dd>
  <dt> -r REGION</dt>
  <dd> Name der Region, z. B. 'us-south' oder 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> Anmeldung erzwingen, ohne eine Region als Ziel auszuwählen</dd>
  <dt> -o <i>ORG</i> (optional)</dt>
  <dd> Name der Zielorganisation (veraltet, 'ibmcloud target -o ORG' verwenden)</dd>
  <dt> -s <i>SPACE</i> (optional) </dt>
  <dd> Name des Zielbereichs (veraltet, 'ibmcloud target -s SPACE' verwenden)</dd>
  <dt> --no-iam </dt>
  <dd> Authentifizierung beim Anmeldeserver anstatt beim öffentlichen IAM erzwingen</dd>
  <dt> --skip-ssl-validation (optional) </dt>
  <dd> Umgeht die SSL-Validierung von HTTP-Anforderungen. Diese Option wird nicht empfohlen.</dd>
</dl>

<strong>Beispiele</strong>:

### Interaktive Anmeldung

```
ibmcloud login
```
{: codeblock}

Melden Sie sich mit dem Benutzernamen und dem Kennwort an und legen Sie Zielkonto, Organisation und Bereich fest:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Melden Sie sich mit einem einmaligen Kenncode an und legen Sie Zielkonto, Organisation und Bereich fest:
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### Cloud Foundry-Services verwenden

Zur Verwendung der Cloud Foundry-Services müssen Sie eine Cloud-Foundry-Organisation und einen Cloud Foundry-Bereich als Ziel festlegen. Sie können den folgenden Befehl ausführen, um die Organisation und den Bereich interaktiv auszuwählen:
```
ibmcloud target --cf
```
{: codeblock}

Optional können Sie die Ausgabe des vorigen Befehls verwenden, um Ihre Organisation und Ihren Bereich manuell mit dem folgenden Befehl festzulegen:
```
ibmcloud target -o <wert> -s <wert>
```
{: codeblock}

### API-Schlüssel hat zugeordnetes Konto

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### API-Schlüssel hat kein zugeordnetes Konto

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Hinweis:</strong> Wenn der API-Schlüssel ein zugeordnetes Konto hat, ist ein Wechsel zu einem anderen Konto nicht zulässig.

### Einmaligen Kenncode verwenden
```
ibmcloud login -u UserID --sso
```
{: codeblock}

Anschließend stellt die CLI einen URL-Link bereit und fordert den Kenncode an:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Öffnen Sie den Link im Browser, um einen Kenncode zu erhalten. Geben Sie den erhaltenen Kenncode in die Konsole ein und melden Sie sich an.

## ibmcloud logout
{: #ibmcloud_logout}

Benutzer abmelden.
```
ibmcloud logout
```
{: codeblock}

<strong>Voraussetzungen</strong>: Keine

## ibmcloud regions
{: #ibmcloud_regions}

Zeigt die Informationen für alle Regionen in {{site.data.keyword.Bluemix_notm}} an.
```
ibmcloud regions
```
{: codeblock}

<strong>Voraussetzungen</strong>: Endpunkt

## ibmcloud target
{: #ibmcloud_target}


Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen.
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
   <dt>-c <i>ACCOUNT_ID</i> (optional)</dt>
   <dd>Die ID des Zielkontos.</dd>
   <dt>-r <i>REGION_NAME</i> (optional)</dt>
   <dd>Der Name der Region, in die gewechselt werden soll, z. B. 'us-south' oder 'eu-gb'.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (optional)</dt>
   <dd>Der Name der Ressourcengruppe.</dd>
   <dt>--cf</dt>
   <dd>Interaktive Auswahl der Zielorganisation und des Zielbereichs</dd>
   <dt>--cf-api</dt>
   <dd>Cloud Foundry-API-Endpunkt</dd>
   <dt>-o <i>ORG_NAME</i> (optional)</dt>
   <dd>Der Name der Zielorganisation.</dd>
   <dt>-s <i>SPACE_NAME</i> (optional)</dt>
   <dd>Der Name des Zielbereichs.</dd>
   <dt>--unset-region</dt>
   <dd>Die Festlegung der Zielregion aufheben.</dd>
   <dt>--unset-resource-group</dt>
   <dd>Festlegung der ausgewählten Ressourcengruppe als Ziel aufheben</dd>
   <dt>--output <i>FORMAT</i></dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
</dl>
Wenn keine der Optionen angegeben wird, werden das aktuelle Konto, die aktuelle Region, die aktuelle Organisation und der aktuelle Bereich angezeigt.

<strong>Beispiele</strong>:

Aktuelles Konto, aktuelle Organisation und aktuellen Bereich festlegen:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Zu einer neuen Region wechseln:
```
ibmcloud target -r eu-gb
```
{: codeblock}

Aktuelles Konto, aktuelle Region, aktuelle Organisation und aktuellen Bereich anzeigen:
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Update auf die neueste Version der Befehlszeilenschnittstelle durchführen:
```
ibmcloud update [-f]
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen. Rootberechtigung ist erforderlich.</dd>
</dl>


## Allgemeine Servicebefehle der klassischen Infrastruktur
{: #softlayer_cli}

Verwenden Sie Befehle der klassischen Infrastruktur in der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle (CLI) zum Konfigurieren und Verwalten von Infrastrukturservices.

Den Befehl `ibmcloud sl` ausführen, um die Liste der verfügbaren Befehle anzuzeigen:
```
USAGE:
   ibmcloud sl command [argumente...] [optionen...]

COMMANDS:
   block           Gen1-Infrastruktur - Blockspeicher
   cdn             Gen1-Infrastruktur - Netz zur Bereitstellung von Inhalten
   file            Gen1-Infrastruktur - Dateispeicher
   dns             Gen1-Infrastruktur - Domin Name System
   globalip        Gen1-Infrastruktur - Globale IP-Adressen
   hardware        Gen1-Infrastruktur - Hardware-Server
   image           Gen1-Infrastruktur - Datenverarbeitungsimages
   ipsec           Gen1-Infrastruktur - IPSEC-VPN
   loadbal         Gen1-Infrastruktur - Lastausgleichsfunktionen
   security        Gen1-Infrastruktur - SSH-Schlüssel und SSL-Zertifikate
   securitygroup   Gen1-Infrastruktur - Netzsicherheitsgruppen
   subnet          Gen1-Infrastruktur - Netz-Teilnetze
   ticket          Gen1-Infrastruktur - Tickets verwalten
   vlan            Gen1-Infrastruktur - Netz-VLANs
   vs              Gen1-Infrastruktur - Virtuelle Server
   order           Gen1-Infrastruktur - Bestellungen
   user            Gen1-Infrastruktur - Benutzer verwalten
   call-api        Beliebige API-Endpunkte aufrufen
   help            Hinweis für Befehlsverwendung ausgeben
```
{: screen}

Gehen Sie wie folgt vor, um Hilfeinformationen zu einem Befehl anzuzeigen:
```
ibmcloud sl [command] -h
```

Der Befehl `ibmcloud sl init` ist ab der CLI-Version `0.14` nicht mehr verfügbar. Informationen zum Installieren der aktuellen CLI-Version finden Sie in [Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Hilfeinformationen für alle Befehle für den Betrieb der Umgebung der klassischen Infrastruktur anzeigen.
```
ibmcloud sl help
```
{: codeblock}

