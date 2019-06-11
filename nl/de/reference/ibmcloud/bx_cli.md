---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

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

Die Befehlszeilenschnittstelle (Command-Line Interface, CLI) von {{site.data.keyword.cloud_notm}} stellt eine nach Namensbereich geordnete Gruppe von Befehlen für Benutzerinteraktionen mit {{site.data.keyword.cloud_notm}} bereit.
{: shortdesc}

Der {{site.data.keyword.cloud_notm}}-Befehlszeilenclient enthält im Installationspaket einen Cloud Foundry-Befehlszeilenclient. Wenn Sie eine eigene Cloud Foundry-CLI installiert haben, verwenden Sie die Befehle der {{site.data.keyword.cloud_notm}}-CLI und die Befehle der Cloud Foundry-CLI Ihrer eigenen Installation nicht im selben Kontext. Verwenden Sie stattdessen **`ibmcloud cf [command]`**, wenn Sie Cloud Foundry-Ressourcen mit der Cloud Foundry-CLI im Kontext der {{site.data.keyword.cloud_notm}}-CLI verwalten möchten. Beachten Sie, dass **`ibmcloud cf api/login/logout/target`** nicht zulässig ist und Sie stattdessen **`ibmcloud api/login/logout/target`** verwenden müssen.

Ab Mai 2018 wird an Stelle der {{site.data.keyword.cloud_notm}}-CLI-Befehle **`bluemix`** und **`bx`** künftig der Befehl **`ibmcloud`** verwendet. Sie können die CLI-Befehle **`bluemix`** und **`bx`** jedoch weiterhin verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

In der nachfolgenden Liste finden Sie detaillierte Angaben zu den von der {{site.data.keyword.cloud_notm}}-CLI unterstützten Befehlen mit zugehörigen Namen, Argumenten, Optionen, Voraussetzungen, Beschreibungen und Beispielen.

In den Voraussetzungen wird aufgelistet, welche Aktionen vor der Verwendung des Befehls ausgeführt werden müssen. Dazu können eine oder mehrere der folgenden Aktionen gehören:

<dl>
<dt>Docker</dt>
<dd>Installieren Sie die Docker-CLI.</dd>
<dt>Endpunkt</dt>
<dd>Legen Sie mit dem Befehl **`ibmcloud api`** einen API-Endpunkt fest.</dd>
<dt>Anmeldung</dt>
<dd>Melden Sie sich mit dem Befehl **`ibmcloud login`** an. Wenn Sie sich mit einer föderierten ID anmelden, verwenden Sie die Option **`-- sso`** , um sich mit einem einmaligen Kenncode zu authentifizieren, oder verwenden Sie die Option **`-- apikey`** , um sich mit einem API-Schlüssel zu authentifizieren.</dd>
<dt>Ziel</dt>
<dd>Legen Sie mit dem Befehl **`ibmcloud target`** eine Organisation und einen Bereich fest.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Zeigt die erweiterte Hilfe für integrierte Befehle und unterstützte Namensbereiche der obersten Ebene in der {{site.data.keyword.cloud_notm}}-CLI oder die Hilfe für einen bestimmten integrierten Befehl oder Namensbereich an. 

```
ibmcloud help [COMMAND|NAMESPACE]
```

### Voraussetzungen
{: #help-prereqs}

Keine.

### Befehlsoptionen
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>Der Befehl oder Namensbereich, für den die Hilfe angezeigt wird. Wenn nichts angegeben ist, wird die erweiterte Hilfe für die {{site.data.keyword.Bluemix_notm}}-CLI angezeigt. Optional.</dd>
</dl>

### Beispiele
{: #help-examples}

Erweiterte Hilfe für die {{site.data.keyword.cloud_notm}}-CLI anzeigen:
```
ibmcloud help
```
{: codeblock}

Hilfe für den Befehl **`dev`** anzeigen:
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

{{site.data.keyword.cloud_notm}}-API-Endpunkt festlegen oder anzeigen.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### Voraussetzungen
{: #api-prereqs}

Keine.

### Befehlsoptionen
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>Der API-Endpunkt, der als Ziel verwendet wird, zum Beispiel `https://cloud.ibm.com`. Wenn weder die Option **`API_ENDPOINT`** noch die Option **`--unset`** angegeben ist, wird der aktuelle API-Endpunkt angezeigt. Optional.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Umgeht die SSL-Validierung von HTTP-Anforderungen. Optional.</dd>
<dt>--unset</dt>
<dd>Entfernt die Einstellung für den API-Endpunkt.</dd>
</dl>

### Beispiele
{: #api-examples}

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

API-Endpunkt entfernen:
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Schreibt Standardwerte in die Konfigurationsdatei.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Voraussetzungen
{: #config-prereqs}

Keine.

### Befehlsoptionen
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>CLI-Versionsprüfung aktivieren oder inaktivieren. Gültige Werte: `true` oder `false`.</dd>
<dt>--color</dt>
<dd>Farbausgabe aktivieren oder inaktivieren. Diese Option ist standardmäßig inaktiviert. Gültige Werte: `true` oder `false`.</dd>
<dt>--http-timeout</dt>
<dd>Der Zeitlimitwert für HTTP-Anforderungen in Sekunden. Der Standardwert ist 60 Sekunden.</dd>
<dt>--locale</dt>
<dd>Eine Standardländereinstellung festlegen. Wenn kein Wert angegeben ist, wird die vorherige Ländereinstellung gelöscht.</dd>
<dt>--trace </dt>
<dd>Trace für HTTP-Anforderungen mit Ausgabe auf Terminal oder in angegebener Datei aktivieren. Gültige Werte: `true` oder `false`.</dd>
</dl>

Sie können jeweils nur eine der Optionen auf einmal angeben.
{: tip}

### Beispiele
{: #config-examples}

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

Trace für HTTP-Anforderungen mit Ausgabe in die Datei `/home/usera/my_trace`:
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

Der Befehl **`ibmcloud info`** ist ab der CLI-Version 0.14 nicht mehr verfügbar. Informationen zum Installieren der aktuellen CLI-Version finden Sie in [Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).

## ibmcloud cf
{: #ibmcloud_cf}

Eingebettete Cloud Foundry-CLI aufrufen.
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### Voraussetzungen
{: #info-prereqs}

Keine.

### Befehlsoptionen
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>Aufrufende Nachricht nicht anzeigen.</dd>
</dl>

### Beispiele
{: #info-examples}

Cloud Foundry-Anwendungen auflisten:
```
ibmcloud cf apps
```
{: codeblock}

Cloud Foundry-Services auflisten, ohne die Nachricht `Befehl cf wird aufgerufen...` anzuzeigen:
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

Eine Cloud Foundry-CLI für die IBM Cloud-CLI installieren
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### Voraussetzungen
{: #cfinstall-prereqs}

Keine.

### Befehlsoptionen
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>Zu installierende Version der Cloud Foundry-CLI angeben</dd>
  <dt>--restore</dt>
  <dd>Cloud Foundry-CLI-Version vor dem Bundle wiederherstellen</dd>
  <dt>-f, --force</dt>
  <dd>Installation ohne Bestätigung erzwingen</dd>
</dl>

### Beispiele
{: #cfinstall-examples}

Cloud Foundry-CLI Version `6.44.1` installieren:

```
ibmcloud cf install -v 6.44.1
```

Neueste Version der Cloud Foundry-CLI ohne Bestätigung installieren:

```
ibmcloud cf install -f
```

Standardmäßige Bundle-Version der Cloud Foundry-CLI wiederherstellen:

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

Bei der {{site.data.keyword.cloud_notm}}-CLI anmelden

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### Voraussetzungen
{: #login-prereqs}

Keine.

### Befehlsoptionen
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>Der API-Endpunkt, z. B. `cloud.ibm.com`. </dd>
<dt>--apikey API_KEY oder @API_KEY_FILE_PATH</dt>
<dd>Der Inhalt des API-Schlüssels oder der Pfad einer API-Schlüsseldatei, der durch das Symbol @ angegeben wird.</dd>
<dt>-u USER_NAME</dt>
<dd>Der Benutzername. Optional.</dd>
<dt>-p PASS_WORD</dt>
<dd>Das Benutzerkennwort. Optional.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Die ID des Zielkontos. Diese Option ist gegenseitig ausschließend mit der Option **`--no account`**.</dd>
<dt>--no-account</dt>
<dd>Erzwungene Anmeldung ohne das Konto. Diese Option wird nicht empfohlen und sie ist gegenseitig ausschließend mit der Option **`-c`**.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Der Name der Zielressourcengruppe. Optional.</dd>
<dt>-r REGION</dt>
<dd>Der Name der Zielregion, z. B. us-south oder eu-gb.</dd>
<dt>--no-region</dt>
<dd>Erzwungene Anmeldung, ohne eine Region als Ziel auszuwählen.</dd>
<dt>-o ORG</dt>
<dd>Der Name der Zielorganisation. Diese Option wird nicht mehr verwendet. Verwenden Sie stattdessen **`ibmcloud target -o org_name`**. Optional.</dd>
<dt>-s SPACE</dt>
<dd>Der Name des Zielbereichs. Diese Option wird nicht mehr verwendet. Verwenden Sie stattdessen **`ibmcloud target -s space_name`**. Optional.</dd>
<dt>--no-iam</dt>
<dd>Authentifizierung beim Anmeldeserver anstatt beim öffentlichen IAM erzwingen.</dd>
<dt>--skip-ssl-validation</dt>
<dd>SSL-Validierung der HTTP-Anforderungen umgehen. Diese Option wird nicht empfohlen.</dd>
</dl>

### Beispiele
{: #login-examples}

Im Dialogbetrieb anmelden

```
ibmcloud login
```
{: codeblock}

Mit Benutzername und Kennwort anmelden und Zielkonto, -organisation und -bereich festlegen:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Mit einmaligem Kenncode anmelden und Zielkonto, -organisation und -bereich festlegen:
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Legen Sie Cloud Foundry-Organisation und -Bereich fest. Sie können den folgenden Befehl ausführen, um die Organisation und den Bereich interaktiv anzugeben:

```
ibmcloud target --cf
```
{: codeblock}

Wenn Sie wissen, zu welcher Organisation und zu welchem Bereich der Service gehört, können Sie alternativ auch den folgenden Befehl verwenden:

```
ibmcloud target -o <wert> -s <wert>
```
{: codeblock}

API-Schlüssel mit zugeordnetem Konto verwenden:

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

API-Schlüssel ohne zugeordnetes Konto verwenden:

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

Wenn dem API-Schlüssel ein Konto zugeordnet ist, wird der Wechsel zu einem anderen Konto nicht unterstützt.
{ :note}

Einmaligen Kenncode verwenden:

```
ibmcloud login -u UserID --sso
```
{: codeblock}

Anschließend stellt die CLI einen URL-Link bereit und fordert zur Eingabe des Kenncodes auf:

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Öffnen Sie den Link in einem Browser, um einen Kenncode zu erhalten. Geben Sie den angegebenen Kenncode in der Konsole ein, um sich anzumelden.

## ibmcloud logout
{: #ibmcloud_logout}

Melden Sie sich von der CLI ab.

```
ibmcloud logout
```
{: codeblock}

### Voraussetzungen
{: #logout-prereqs}

Keine.

## ibmcloud regions
{: #ibmcloud_regions}

Zeigt die Informationen für alle Regionen in {{site.data.keyword.Bluemix_notm}} an.

```
ibmcloud regions
```
{: codeblock}

### Voraussetzungen
{: #regions-prereqs}

Legen Sie mit dem Befehl **`ibmcloud api`** einen API-Endpunkt fest.

## ibmcloud target
{: #ibmcloud_target}

Zielkonto, Region, Organisation oder Bereich festlegen oder anzeigen.

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### Voraussetzungen
{: #target-prereqs}

* Legen Sie mit dem Befehl **`ibmcloud api`** einen API-Endpunkt fest.
* Melden Sie sich mit dem Befehl **`ibmcloud login`** an. Wenn Sie sich mit einer föderierten ID anmelden, verwenden Sie die Option **`-- sso`** , um sich mit einem einmaligen Kenncode zu authentifizieren, oder verwenden Sie die Option **`-- apikey`** , um sich mit einem API-Schlüssel zu authentifizieren.

### Befehlsoptionen
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>Die ID des Zielkontos. Optional.</dd>
<dt>-r REGION</dt>
<dd>Der Name der Zielregion, z. B. us-south oder eu-gb. Optional.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Der Name der Zielressourcengruppe. Optional.</dd>
<dt>--cf</dt>
<dd>Die Zielorganisation und den Bereich im Dialogbetrieb angeben.</dd>
<dt>--cf-api</dt>
<dd>Der Cloud Foundry-API-Endpunkt.</dd>
<dt>-o ORG</dt>
<dd>Der Name der Zielorganisation. Optional.</dd>
<dt>-s SPACE</dt>
<dd>Der Name des Zielbereichs. Optional.</dd>
<dt>--unset-region</dt>
<dd>Die Zielregion abwählen.</dd>
<dt>--unset-resource-group</dt>
<dd>Die Zielressourcengruppe abwählen.</dd>
<dt>--output FORMAT</dt>
<dd>Das angegebene Ausgabeformat. JSON wird derzeit als einziges Format unterstützt.</dd>
</dl>

Wenn keine der Optionen angegeben wird, werden das aktuelle Konto, die aktuelle Region, die aktuelle Organisation und der aktuelle Bereich angezeigt.
{: note}

### Beispiele
{: #target-examples}

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
### Voraussetzungen
{: #update-prereqs}

### Befehlsoptionen
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>Aktualisierung ohne Bestätigung erzwingen. Rootberechtigung ist erforderlich.</dd>
</dl>

## Allgemeine Servicebefehle der klassischen Infrastruktur
{: #softlayer_cli}

Verwenden Sie Befehle der klassischen Infrastruktur in der {{site.data.keyword.cloud_notm}}-CLI zum Konfigurieren und Verwalten von Infrastrukturservices.

Den Befehl **`ibmcloud sl`** ausführen, um die Liste der verfügbaren Befehle anzuzeigen:
```
USAGE:
   ibmcloud sl command [argumente...] [optionen...]

COMMANDS:
   block           Gen1-Infrastruktur - Blockspeicher
   cdn             Gen1-Infrastruktur - Netz zur Bereitstellung von Inhalten
   file            Gen1-Infrastruktur - Dateispeicher
   dns             Gen1-Infrastruktur - Domain Name System
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

Führen Sie den folgenden Befehl aus, um Hilfeinformationen zu einem Befehl anzuzeigen:
```
ibmcloud sl [command] -h
```

Der Befehl **`ibmcloud sl init`** ist ab der CLI-Version `0.14` nicht mehr verfügbar. Informationen zum Installieren der aktuellen CLI-Version finden Sie in [Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Hilfeinformationen für alle Befehle für den Betrieb der Umgebung der klassischen Infrastruktur anzeigen.
```
ibmcloud sl help
```
{: codeblock}

