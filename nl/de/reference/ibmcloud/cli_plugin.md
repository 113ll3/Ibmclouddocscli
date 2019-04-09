---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: add cli plug-in, remove cli plug-in, cli plug-in, ibmcloud plugin, repo-add, repo-remove, plugin uninstall, plugin update

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# CLI-Plug-ins in {{site.data.keyword.cloud_notm}} hinzufügen und entfernen
{: #ibmcloud_commands_settings}

{{site.data.keyword.cloud}} unterstützt ein Plug-in-Framework zur Erweiterung der verfügbaren Funktionalität. Verwenden Sie die folgenden Befehle, um die Plug-ins der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle zu verwalten.
{: shortdesc}

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Alle Plug-in-Repositorys auflisten, die in der Befehlszeilenschnittstelle von {{site.data.keyword.cloud_notm}} registriert sind.
```
ibmcloud plugin repos
```
{: codeblock}

<strong>Voraussetzungen</strong>: Keine

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Neues Plug-in-Repository zur Befehlszeilenschnittstelle von {{site.data.keyword.cloud_notm}} hinzufügen.
```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das hinzugefügt werden soll. Sie können einen eigenen Namen für jedes Repository definieren.</dd>
   <dt>REPO_URL (erforderlich)</dt>
   <dd>Die URL des Repositorys, das hinzugefügt werden soll. Die URL des Repositorys muss das Protokoll (zum Beispiel 'http://plugins.ng.bluemix.net' anstatt 'plugins.ng.bluemix.net') enthalten. http://plugins.ng.bluemix.net ist das offizielle Plug-in-Repository der {{site.data.keyword.cloud_notm}}-CLI.</dd>
    </dl>


<strong>Beispiele</strong>:

Offizielles Plug-in-Repository der {{site.data.keyword.Bluemix_notm}}-CLI als `bluemix-repo` hinzufügen:
```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```
{: codeblock}

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Plug-in-Repository aus der {{site.data.keyword.cloud_notm}}-CLI entfernen.
```
ibmcloud plugin repo-remove REPO_NAME
```
{: codeblock}

<strong>Voraussetzungen</strong>: Keine

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>REPO_NAME (erforderlich)</dt>
   <dd>Der Name des Repositorys, das entfernt werden soll.</dd>
   </dl>

<strong>Beispiele</strong>:

Repository `bluemix-repo` aus der Befehlszeilenschnittstelle von {{site.data.keyword.cloud_notm}} entfernen:
```
ibmcloud plugin repo-remove bluemix-repo
```
{: codeblock}

## ibmcloud plugin repo-plugins
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

## ibmcloud plugin repo-plugin
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

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Alle installierten Plug-ins in der {{site.data.keyword.Bluemix_notm}}-CLI auflisten.
```
ibmcloud plugin list
```
{: codeblock}

<strong>Voraussetzungen</strong>: Keine

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Details eines installierten Plug-ins anzeigen.
```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Voraussetzungen</strong>: Keine

## ibmcloud plugin install
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

## ibmcloud plugin update
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

## ibmcloud plugin uninstall
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
