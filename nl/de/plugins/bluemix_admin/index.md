---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}}-Administrator-CLI
{: #bluemixadmincli}

Sie können Ihre {{site.data.keyword.cloud_notm}} Local- oder {{site.data.keyword.cloud_notm}} Dedicated-Umgebung über die Cloud Foundry-Befehlszeilenschnittstelle (Command-Line Interface, CLI) mit dem {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in verwalten. Sie können Benutzer zum Beispiel aus einer LDAP-Registry hinzufügen.

Vor dem Beginn müssen Sie die Cloud Foundry-CLI installieren. Für das {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in ist
`cf` Version 6.11.2 oder höher erforderlich. [Cloud Foundry-Befehlszeilenschnittstelle herunterladen](https://github.com/cloudfoundry/cli/releases){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")

Die Cloud Foundry-CLI wird von Cygwin nicht unterstützt. Verwenden Sie die Cloud Foundry-CLI in einem anderen als dem Cygwin-Befehlszeilenfenster.

Die {{site.data.keyword.cloud_notm}}-Administrator-CLI wird nur für die Umgebungen {{site.data.keyword.cloud_notm}} Local und {{site.data.keyword.cloud_notm}} Dedicated verwendet. Von {{site.data.keyword.cloud_notm}} Public wird sie nicht unterstützt.
{: note}

## {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in hinzufügen
{: #add-admin-cli}

Nach der Installation der Cloud Foundry-CLI können Sie das {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in hinzufügen.

Wenn Sie das {{site.data.keyword.cloud_notm}}-Administrator-Plug-in zuvor installiert haben, müssen Sie möglicherweise das Plug-in deinstallieren, das Repositry löschen und anschließend erneut installieren, um die neuesten Aktualisierungen zu erhalten.
{: tip}

Führen Sie die folgenden Schritte aus, um das Repository hinzuzufügen und das Plug-in zu installieren:

1. Führen Sie den folgenden Befehl aus, um das {{site.data.keyword.cloud_notm}}-Administrator-Plug-in hinzuzufügen:
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  Denselben Befehl finden Sie mit dem tatsächlichen Endpunkt auf der CLI-Seite Ihrer Administrationskonsole: `https://<customer_console_endpoint>.bluemix.net/cli`.
  {: note}

2. Führen Sie den folgenden Befehl aus, um das {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in zu installieren:
  ```
  cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
```
  {: codeblock}

## {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in deinstallieren
{: #remove-admin-cli}

Führen Sie die folgenden Schritte aus, um das Plug-in zu deinstallieren. 

1. Deinstallieren Sie das Plug-in:
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. Entfernen Sie das Plug-in-Repository:
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

Anschließend können Sie das aktualisierte Repository hinzufügen und das neueste Plug-in installieren.

## {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in verwenden
{: #using-admin-cli}

Mit dem {{site.data.keyword.cloud_notm}}-Administrator-CLI-Plug-in können Sie Benutzer hinzufügen oder entfernen, Benutzer zu Organisationen zuordnen oder die Zuordnung aufheben und andere Management-Tasks ausführen.

Führen Sie den folgenden Befehl aus,
um eine Liste der Befehle anzuzeigen:
```
cf plugins
```
{: codeblock}

Wenn Sie weitere Hilfe zu einem Befehl benötigen, verwenden Sie die Option `-help`.

### Verbindung zu {{site.data.keyword.cloud_notm}} herstellen und anmelden
{: #connecting-ibm-cloud}

1. Führen Sie zum Herstellen einer Verbindung zum {{site.data.keyword.cloud_notm}}-API-Endpunkt den folgenden Befehl aus:
  ```
  cf api api.us-south.cf.cloud.ibm.com
  ```
  {: codeblock}
  
  Während die traditionellen Cloud Foundry-API-Endpunkte (`api.*.bluemix.net`) weiterhin verfügbar sind, können Sie Scripte und die Automatisierung der Infrastruktur aktualisieren, um die folgenden aktualisierten Cloud Foundry-API-Endpunkte für Ihre Region zu verwenden:

  * api.us-south.cf.cloud.ibm.com  (vormals api.ng.bluemix.net)
  * api.eu-gb.cf.cloud.ibm.com     (vormals api.eu-gb.bluemix.net)
  * api.us-east.cf.cloud.ibm.com   (vormals api.us-east.bluemix.net)
  * api.eu-de.cf.cloud.ibm.com     (vormals api.eu-de.bluemix.net)
  * api.au-syd.cf.cloud.ibm.com    (vormals api.au-syd.bluemix.net)

  Die korrekte URL können Sie auf der Seite für Ressourcen und Informationen der Administrationskonsole ermitteln. Die URL wird im Abschnitt 'API-Informationen' im Feld **API-URL** angezeigt.

2. Melden Sie sich bei {{site.data.keyword.cloud_notm}} durch Ausführen des folgenden Befehls an: 
  ```
  cf login
  ```
  {: codeblock}

## Benutzer verwalten
{: #admin_users}

### Benutzer hinzufügen
{: #admin_add_user}

Verwenden Sie den folgenden Befehl, um Ihrer {{site.data.keyword.cloud_notm}}-Umgebung einen Benutzer aus der Benutzerregistry Ihrer Umgebung hinzuzufügen:
```
cf ba add-user <user_name> <organization> <first_name> <last_name>
```
{: codeblock}

Zum Hinzufügen eines Benutzers zu einer bestimmten Organisation müssen Sie ein Administrator mit der Berechtigung 'users.write' (oder 'Superuser') sein. Wenn Sie ein Organisationsmanager sind, kann Ihnen auch die Funktion bereitgestellt werden, mit der Sie Ihrer Organisation Benutzer über einen Superuser hinzufügen können, der den Befehl **`enable-managers-add-users`** ausführt. Weitere Informationen finden Sie unter [Managern das Hinzufügen von Benutzern ermöglichen](#clius_emau).

| Option | Beschreibung | 
| -------| ------------|
| _userName_ | Der Name des Benutzers im LDAP-Registry. |
| _organization_ | Der Name oder die GUID der {{site.data.keyword.cloud_notm}}-Organisation, der der Benutzer hinzugefügt werden soll. |
| _firstName_ | Der Vorname des Benutzers, der der Organisation hinzugefügt werden soll. | 
| _lastName_ | Der Nachname des Benutzers, der der Organisation hinzugefügt werden soll. | 
{: caption="Tabelle 1. Optionen für den cf-Befehl 'ba add-user'" caption-side="top"}

Sie können auch **`ba au`** als Alias für den längeren Befehlsnamen **`ba add-user`** verwenden.
{: tip}

### Benutzer über {{site.data.keyword.Bluemix_dedicated_notm}} einladen
{: #admin_dedicated_invite_public}

Jede {{site.data.keyword.Bluemix_dedicated_notm}}-Umgebung verfügt in {{site.data.keyword.cloud_notm}} über einen öffentliches, kundeneigenes Firmenkonto. Benutzer können in der Dedicated-Umgebung nur Cluster mit dem {{site.data.keyword.containershort}} erstellen, wenn sie zuvor vom Administrator zu diesem öffentlichen Firmenkonto hinzugefügt wurden. Wenn die Benutzer zum öffentlichen Firmenkonto hinzugefügt wurden, sind die jeweiligen Dedicated-Konten und Public-Konten miteinander verknüpft. Benutzer können sich mit ihrer IBMid gleichzeitig bei Dedicated und Public anmelden und Sie können Ressourcen unter dem öffentlichen Konto von der Dedicated-Schnittstelle aus erstellen. Weitere Informationen finden Sie unter [IBM Cloud Container Service unter Dedicated einrichten](/docs/containers?topic=containers-dedicated#dedicated_setup). Laden Sie Dedicated-Benutzer wie folgt zum öffentlichen Konto ein:
```
cf ba invite-users-to-public -userid=<user_email> -organization=<dedicated_org_id> -apikey=<public_api_key> -public_org_id=<public_org_id>
```
{: pre}

Benutzer der Dedicated-Umgebung können Sie nur zu Ihrem öffentlichen {{site.data.keyword.cloud_notm}}-Konto hinzufügen, wenn Sie ein Administrator des Dedicated-Kontos sind. 

| Option | Beschreibung | 
| -------| ------------|
| -userid | Wenn Sie einen einzelnen Benutzer einladen, die E-Mail-Adresse dieses Benutzers. |
| -organization | Wenn alle Benutzer in einer Organisation des Dedicated-Kontos eingeladen werden sollen, die ID der Organisation des Dedicated-Kontos. |
| -apikey | Ein API-Schlüssel zum Einladen von Benutzern für das öffentliche Konto. Dieser Schlüssel muss vom Administrator des öffentlichen Kontos generiert werden.| 
| -public_org_id | Die ID der Organisation des öffentlichen Kontos, zu der Benutzer eingeladen werden. | 
{: caption="Tabelle 2. Optionen für den cf-Befehl 'ba invite-users-to-public'" caption-side="top"}

### Von {{site.data.keyword.Bluemix_dedicated_notm}} aus eingeladene Benutzer auflisten
{: #admin_dedicated_list}

Wenn Sie Benutzer einer Dedicated-Umgebung zu Ihrem {{site.data.keyword.Bluemix_notm}}-Konto mit dem Befehl [**`invite-users-to-public`**](#admin_dedicated_invite_public) eingeladen haben, können Sie die Benutzer in Ihrem Konto auflisten, um den zugehörigen Einladungsstatus anzuzeigen. Eingeladene Benutzer mit einer bestehenden IBMid haben den Status ACTIVE. Eingeladene Benutzer, die nicht über eine IBMid verfügen, haben den Status PENDING oder ACTIVE, abhängig davon, ob sie die Einladung zum Konto bereits angenommen haben. Listen Sie die Benutzer in Ihrem {{site.data.keyword.Bluemix_notm}}-Konto wie folgt auf:

```
cf ba invite-users-status -apikey=<public_api_key>
```
{: pre}

Benutzer der Dedicated-Umgebung können Sie nur zu Ihrem öffentlichen {{site.data.keyword.Bluemix_notm}}-Konto hinzufügen, wenn Sie ein Administrator des Dedicated-Kontos sind.

<dl class="parml">
<dt class="pt dlterm">&lt;public_api_key&gt;</dt>
<dd class="pd">Der API-Schlüssel, der für die Einladung der Benutzer zu dem Konto verwendet wurde. Dieser Schlüssel muss vom Administrator des öffentlichen Kontos generiert werden.</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### Nach einem Benutzer suchen
{: #admin_search_user}

Verwenden Sie den folgenden Befehl in Kombination mit den optionalen Suchfilterparametern (Name, Berechtigung, Organisation und Rolle), um nach einem Benutzer zu suchen:

```
cf ba search-users -name=<user_name_value> -permission=<permission_value> -organization=<organization_value> -role=<role_value>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| -name | Der Name des Benutzers. |
| -permission | Die dem Benutzer zugeordnete Berechtigung. Verfügbare Berechtigungen: 'admin' (oder 'superuser'), 'login' (oder 'basic'), 'catalog.read', 'catalog.write', 'reports.read', 'reports.write', 'users.read' oder 'users.write'. Dieser Parameter kann nicht in derselben Abfrage wie der Parameter 'organization' verwendet werden. |
| -organization | Der Name der Organisation, zu der der Benutzer gehört. Dieser Parameter kann nicht in derselben Abfrage wie der Parameter 'permission' verwendet werden. | 
| -role | Die dem Benutzer zugeordnete Organisationsrolle. Verfügbare Rollen: 'auditors', 'managers' und 'billing_managers'. Sie müssen mit diesem Parameter die Organisation angeben. | 
{: caption="Tabelle 3. Optionen für den cf-Befehl 'ba search-users'" caption-side="top"}

Sie können auch **`ba su`** als Alias für den längeren Befehlsnamen **`ba search-users`** verwenden.
{: tip}

### Berechtigungen für einen Benutzer festlegen
{: #admin_setperm_user}

Verwenden Sie den folgenden Befehl, um die Berechtigungen für einen angegebenen Benutzer festzulegen:
```
cf ba set-permissions <user_name> <permission> <access>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _userName_ | Der Name des Benutzers. |
| _permission_ | Die dem Benutzer zugeordnete Berechtigung festlegen. Verfügbare Berechtigungen: 'admin' (oder 'superuser'), 'login' (oder 'basic'), 'catalog.read', 'catalog.write', 'reports.read', 'reports.write', 'users.read' oder 'users.write'. Dieser Parameter kann nicht in derselben Abfrage wie der Parameter 'organization' verwendet werden. |
| _access_ | Für die Berechtigungen 'catalog', 'reports' oder 'user' müssen Sie außerdem die Zugriffsebene `read` oder `write` angeben. |  
{: caption="Tabelle 4. Optionen für den cf-Befehl 'ba set-permissions'" caption-side="top"}

Sie können jeweils nur eine Berechtigung gleichzeitig festlegen.

Sie können auch **`ba sp`** als Alias für den längeren Befehlsnamen **`ba set-permissions`** verwenden.
{: tip}

<!-- staging-only commands end -->

### Benutzer entfernen
{: #admin_remov_user}

Verwenden Sie den folgenden Befehl, um einen Benutzer aus Ihrer {{site.data.keyword.Bluemix_notm}}-Umgebung zu entfernen:

```
cf ba remove-user <user_name>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">Der Name des Benutzers in {{site.data.keyword.Bluemix_notm}}.</dd>

</dl>

Sie können auch **`ba ru`** als Alias für den längeren Befehlsnamen **`ba remove-user`** verwenden.
{: tip}

### Managern das Hinzufügen von Benutzern ermöglichen
{: #clius_emau}

Wenn Sie über die Berechtigung 'Superuser' für Ihre {{site.data.keyword.Bluemix_notm}}-Umgebung verfügen, können Sie  Organisationsmanagern die Möglichkeit geben, in den von ihnen verwalteten Organisationen Benutzer hinzuzufügen. Um Managern das Hinzufügen von Benutzern zu ermöglichen, verwenden Sie den folgenden Befehl:

```
cf ba enable-managers-add-users
```
{: codeblock}

Sie können auch **`ba emau`** als Alias für den längeren Befehlsnamen **`ba enable-managers-add-users`** verwenden.
{: tip}

### Das Hinzufügen von Benutzern für Manager inaktivieren
{: #clius_dmau}

Wenn Organisationsmanager autorisiert wurden, Benutzer zu den von ihnen verwalteten Organisationen in Ihrer {{site.data.keyword.Bluemix_notm}}-Umgebung mit dem Befehl **`enable-managers-add-users`** hinzuzufügen, können Sie diese Einstellung inaktivieren, sofern Sie die Berechtigung 'Superuser' besitzen. Um Managern die Möglichkeit zu nehmen, Benutzer hinzuzufügen, verwenden Sie den folgenden Befehl:

```
cf ba disable-managers-add-users
```
{: codeblock}

Sie können auch **`ba dmau`** als Alias für den längeren Befehlsnamen **`ba disable-managers-add-users`** verwenden.
{: tip}

## Organisationen verwalten
{: #admin_orgs}

### Organisation hinzufügen
{: #admin_add_org}

Verwenden Sie den folgenden Befehl, um eine Organisation hinzuzufügen:

```
cf ba create-org <organization> <manager>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ |Der Name oder die GUID der {{site.data.keyword.Bluemix_notm}}-Organisation, die hinzugefügt werden soll. |
| _manager_ | Der Benutzername des Managers der Organisation. |
{: caption="Tabelle 5. Optionen für den cf-Befehl 'ba create-org'" caption-side="top"}

Sie können auch **`ba co`** als Alias für den längeren Befehlsnamen **`ba create-org`** verwenden.
{: tip}

### Organisation löschen
{: #admin_delete_org}

Verwenden Sie den folgenden Befehl, um eine Organisation zu löschen:

```
cf ba delete-org <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">Der Name oder die GUID der zu löschenden {{site.data.keyword.cloud_notm}}-Organisation.</dd>
</dl>

Sie können auch **`ba do`** als Alias für den längeren Befehlsnamen **`ba delete-org`** verwenden.
{: tip}

### Benutzer einer Organisation zuweisen
{: #admin_ass_user_org}

Um einen Benutzer in Ihrer {{site.data.keyword.cloud_notm}}-Umgebung einer bestimmten Organisation zuzuweisen, verwenden Sie den folgenden Befehl:

```
cf ba set-org <user_name> <organization> [<role>]
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _userName_ | Der Name des Benutzers. |
| _organization_ | Der Name oder die GUID der {{site.data.keyword.cloud_notm}}-Organisation, der der Benutzer zugewiesen werden soll. |
| _role_ | Die Rolle des Benutzers. Gültige Werte: `OrgManager`, `BillingManager` und `OrgAuditor`. Beschreibungen der Rollen finden Sie im Abschnitt [Rollen](/docs/iam?topic=iam-userroles#userroles). |  
{: caption="Tabelle 6. Optionen für den cf-Befehl 'ba set-org'" caption-side="top"}

Sie können auch **`ba so`** als Alias für den längeren Befehlsnamen **`ba set-org`** verwenden.
{: tip}

### Zuweisung eines Benutzers zu einer Organisation aufheben
{: #admin_unass_user_org}

Um die Zuweisung eines Benutzers in Ihrer {{site.data.keyword.cloud_notm}}-Umgebung zu einer bestimmten Organisation aufzuheben, verwenden Sie den folgenden Befehl:

```
cf ba unset-org <user_name> <organization> [<role>]
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _userName_ | Der Name des Benutzers. |
| _organization_ | Der Name oder die GUID der {{site.data.keyword.cloud_notm}}-Organisation. |
| _role_ | Die Rolle des Benutzers. Gültige Werte: `OrgManager`, `BillingManager` und `OrgAuditor`. Beschreibungen der Rollen finden Sie im Abschnitt [Rollen](/docs/iam?topic=iam-userroles#userroles). |  
{: caption="Tabelle 7. Optionen für den cf-Befehl 'ba unset-org'" caption-side="top"}

Sie können auch **`ba uo`** als Alias für den längeren Befehlsnamen **`ba unset-org`** verwenden.
{: tip}

### Kontingent für eine Organisation festlegen
{: #admin_set_org_quota}

Verwenden Sie den folgenden Befehl, um für eine bestimmte Organisation ein Nutzungskontingent festzulegen:

```
cf ba set-quota <organization> <plan>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die GUID der {{site.data.keyword.cloud_notm}}-Organisation, für die das Kontingent festgelegt werden soll. |
| _plan_ | Der Kontingentplan für eine Organisation. |  
{: caption="Tabelle 8. Optionen für den cf-Befehl 'ba set-quota'" caption-side="top"}

Sie können auch **`ba sq`** als Alias für den längeren Befehlsnamen **`ba set-quota`** verwenden.
{: tip}


### Containerkontingente für eine Organisation ermitteln
{: #admin_find_containquotas}

Verwenden Sie den folgenden Befehl, um das Kontingent für Container einer Organisation zu ermitteln:

```
cf ibmcloud-admin containers-quota <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">Der Name oder die ID der Organisation in IBM Cloud. Dieser Parameter ist erforderlich.</dd>
</dl>

Sie können auch **`ba cq`** als Alias für den längeren Befehlsnamen **`ibmcloud-admin containers-quota`** verwenden.
{: tip}

### Containerkontingente für eine Organisation festlegen
{: #admin_set_containquotas}

Verwenden Sie den folgenden Befehl mit mindestens einer der Optionen, um das Kontingent für Container in einer Organisation festzulegen:

```
cf ibmcloud-admin set-containers-quota <organization> <options>
```
{: codeblock}

Sie können mehrere Optionen angeben. Es muss jedoch mindestens eine Option angegeben sein.
{: note}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die ID der {{site.data.keyword.cloud_notm}}-Organisation für die das Kontingent festgelegt werden soll. |
| _options_ | Die Auswahlmöglichkeiten sind **`floating-ips-max value`** (Kurzname **`fim`**), **`floating-ips-space-default value`** (Kurzname **`fisd`**), **`memory-max value`** (Kurzname **`mm`**), **`memory-space-default value`** (Kurzname **`msd`**) oder **`image-limit value`** (Kurzname **`il`**). Der Wert muss eine ganze Zahl sein.  |  
{: caption="Tabelle 9. Optionen für den cf-Befehl 'ibmcloud-admin set-containers-quota'" caption-side="top"}

Optional können Sie eine Datei angeben, die bestimmte Konfigurationsparameter in einem gültigen JSON-Objekt enthält. Falls Sie die Option **`-file`** verwenden, hat diese Option Vorrang und die anderen Optionen werden ignoriert. Verwenden Sie den folgenden Befehl, um eine Datei bereitzustellen, anstatt die Optionen festzulegen:

```
cf ibmcloud-admin set-containers-quota <organization> <-file path_to_JSON_file>
```
{: codeblock}

Das Format der JSON-Datei sollte dem folgenden Beispiel entsprechen:

```
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: codeblock}

Sie können auch **`ba scq`** als Alias für den längeren Befehlsnamen **`ibmcloud-admin set-containers-quota`** verwenden.
{: tip}

## Bereiche verwalten
{: #admin_spaces}

### Bereich in der Organisation hinzufügen

Verwenden Sie den folgenden Befehl, um einen Bereich in der Organisation hinzuzufügen:

```
cf ibmcloud-admin create-space <organization> <space_name>
```

{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die GUID der Organisation, zu der der Bereich hinzugefügt werden soll. |
| _spaceName_ | Der Name des Bereichs, den Sie der Organisation hinzufügen möchten. |  
{: caption="Tabelle 10. Optionen für den cf-Befehl 'ibmcloud-admin create-space'" caption-side="top"}

Sie können auch **`ba cs`** als Alias für den längeren Befehlsnamen **`ba create-space`** verwenden.
{: tip}

### Bereich aus der Organisation löschen

Verwenden Sie den folgenden Befehl, um einen Bereich aus der Organisation zu entfernen:

```
cf ibmcloud-admin delete-space <organization> <space_name>
```

{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die GUID der Organisation, aus der der Bereich entfernt werden soll. |
| _spaceName_ | Der Name des Bereichs, den Sie aus der Organisation entfernen möchten. |  
{: caption="Tabelle 11. Optionen für den cf-Befehl 'ibmcloud-admin delete-space'" caption-side="top"}

Sie können auch **`ba cs`** als Alias für den längeren Befehlsnamen **`ba delete-space`** verwenden.
{: tip}

### Benutzer einem Bereich mit einer Rolle hinzufügen

Verwenden Sie den folgenden Befehl, um einen Benutzer in einem Bereich mit einer angegebenen Rolle zu erstellen:

```
cf ibmcloud-admin set-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die GUID der Organisation, zu der der Benutzer hinzugefügt werden soll. |
| _spaceName_ | Der Name des Bereichs, zu dem der Benutzer hinzugefügt werden soll. |
| _userName_ | Der Name des Benutzers. |
| _role_ | Die Rolle des Benutzers. Gültige Werte sind `Manager`, `Developer` und `Auditor`. |  
{: caption="Tabelle 12. Optionen für den cf-Befehl 'ibmcloud-admin set-space'" caption-side="top"}

Sie können auch **`ba ss`** als Alias für den längeren Befehlsnamen **`ba set-space`** verwenden.
{: tip}


### Rolle eines Benutzers in einem Bereich entfernen

Verwenden Sie den folgenden Befehl, um die Rolle eines Benutzers in einem Bereich zu entfernen:

```
cf ibmcloud-admin unset-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _organization_ | Der Name oder die GUID der Organisation, zu der der Benutzer gehört. |
| _spaceName_ | Der Name des Bereichs, zu dem der Benutzer gehört. |
| _userName_ | Der Name des Benutzers. |
| _role_ | Die Rolle des Benutzers. Gültige Werte sind `Manager`, `Developer` und `Auditor`. |  
{: caption="Tabelle 13. Optionen für den cf-Befehl 'ibmcloud-admin unset-space'" caption-side="top"}

Sie können auch **`ba us`** als Alias für den längeren Befehlsnamen **`ba unset-space`** verwenden.
{: tip}

## Katalog verwalten
{: #admin_catalog}

### Services für alle Organisationen aktivieren
{: #admin_ena_service_org}

Verwenden Sie den folgenden Befehl, um die Sichtbarkeit eines Service im {{site.data.keyword.cloud_notm}}-Katalog für alle
Organisationen zu aktivieren:

```
cf ba enable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">Der Name oder die GUID des Serviceplans, der aktiviert werden soll. Wenn Sie einen nicht eindeutigen Serviceplannamen eingeben, wie zum Beispiel 'Standard' oder 'Basic', werden Sie dazu aufgefordert, eine Auswahl aus einer angezeigten Liste mit Serviceplänen zu treffen. Wählen Sie die Servicekategorie auf der Homepage aus, um einen Serviceplannamen anzugeben. Wählen Sie dann **Hinzufügen** aus, um die Services für diese Kategorie anzuzeigen. Klicken Sie auf den Servicenamen, um die Detailansicht zu öffnen; anschließend können Sie die Namen der für diesen Service verfügbaren Servicepläne anzeigen. </dd>
</dl>

Sie können auch **`ba esp`** als Alias für den längeren Befehlsnamen **`ba enable-service-plan`** verwenden.
{: tip}

### Services für alle Organisationen inaktivieren
{: #admin_dis_service_org}

Verwenden Sie den folgenden Befehl, um die Sichtbarkeit eines Service im
{{site.data.keyword.Bluemix_notm}}-Katalog für alle Organisationen zu inaktivieren:

```
cf ba disable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">Der Name oder die GUID des Serviceplans, der aktiviert werden soll. Wenn Sie einen nicht eindeutigen Serviceplannamen eingeben, wie zum Beispiel 'Standard' oder 'Basic', werden Sie dazu aufgefordert, eine Auswahl aus einer angezeigten Liste mit Serviceplänen zu treffen. Wählen Sie die Servicekategorie auf der Homepage aus, um einen Serviceplannamen anzugeben. Wählen Sie dann **Hinzufügen** aus, um die Services für diese Kategorie anzuzeigen. Klicken Sie auf den Servicenamen, um die Detailansicht zu öffnen; anschließend können Sie die Namen der für diesen Service verfügbaren Servicepläne anzeigen.</dd>
</dl>

Sie können auch **`ba dsp`** als Alias für den längeren Befehlsnamen **`ba disable-service-plan`** verwenden.
{: tip}

### Sichtbarkeit von Services für Organisationen hinzufügen
{: #admin_addvis_service_org}

Sie können eine Organisation aus der Liste der Organisationen, für die ein bestimmter Service im {{site.data.keyword.Bluemix_notm}}-Katalog sichtbar ist, hinzufügen. Verwenden
Sie den folgenden Befehl, um einer Organisation zu gestatten, einen bestimmten Service im Katalog anzuzeigen:

```
cf ba add-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _planIdentifier_ | Der Name oder die GUID des Serviceplans, der aktiviert werden soll. Wenn Sie einen nicht eindeutigen Serviceplannamen eingeben, wie zum Beispiel 'Standard' oder 'Basic', werden Sie dazu aufgefordert, eine Auswahl aus einer angezeigten Liste mit Serviceplänen zu treffen. Wählen Sie die Servicekategorie auf der Homepage aus, um einen Serviceplannamen anzugeben. Wählen Sie dann **Hinzufügen** aus, um die Services für diese Kategorie anzuzeigen. Klicken Sie auf den Servicenamen, um die Detailansicht zu öffnen; anschließend können Sie die Namen der für diesen Service verfügbaren Servicepläne anzeigen. |
| _organization_ | Der Name oder die GUID der Organisation, die der Sichtbarkeitsliste des Service hinzugefügt werden soll.|  
{: caption="Tabelle 14. Optionen für den cf-Befehl 'ba add-service-plan-visibility'" caption-side="top"}

Sie können auch **`ba aspv`** als Alias für den längeren Befehlsnamen **`ba add-service-plan-visibility`** verwenden.
{: tip}

### Sichtbarkeit von Services für Organisationen entfernen
{: #admin_remvis_service_org}

Sie können eine Organisation aus der Liste der Organisationen, für die ein bestimmter Service im
{{site.data.keyword.Bluemix_notm}}-Katalog sichtbar ist, entfernen. Verwenden Sie den folgenden Befehl, um für eine Organisation
die Sichtbarkeit eines Service im Katalog zu entfernen:

```
cf ba remove-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _planIdentifier_ | Der Name oder die GUID des Serviceplans, der aktiviert werden soll. Wenn Sie einen nicht eindeutigen Serviceplannamen eingeben, wie zum Beispiel 'Standard' oder 'Basic', werden Sie dazu aufgefordert, eine Auswahl aus einer angezeigten Liste mit Serviceplänen zu treffen. Wählen Sie die Servicekategorie auf der Homepage aus, um einen Serviceplannamen anzugeben. Wählen Sie dann **Hinzufügen** aus, um die Services für diese Kategorie anzuzeigen. Klicken Sie auf den Servicenamen, um die Detailansicht zu öffnen; anschließend können Sie die Namen der für diesen Service verfügbaren Servicepläne anzeigen. |
| _organization_ | Der Name oder die GUID der Organisation, die aus der Sichtbarkeitsliste des Service entfernt werden soll.|  
{: caption="Tabelle 15. Optionen für den cf-Befehl 'ba remove-service-plan-visibility'" caption-side="top"}

Sie können auch **`ba rspv`** als Alias für den längeren Befehlsnamen **`ba remove-service-plan-visibility`** verwenden.
{: tip}

### Sichtbarkeit von Services für Organisationen bearbeiten
{: #admin_editvis_service_org}

Sie können die Liste der Services, die für bestimmte Organisationen im {{site.data.keyword.Bluemix_notm}}-Katalog
sichtbar sind, bearbeiten und ersetzen. Verwenden Sie den folgenden Befehl, um alle vorhandenen sichtbaren Services für eine Organisation oder mehrere Organisationen zu ersetzen:

```
cf ba edit-service-plan-visibilities <plan_identifier> <organization_1> <optional_organization_2>
```
{: codeblock}

Dieser Befehl ersetzt vorhandene sichtbare Services für die angegebenen Organisationen durch den Service, den Sie im Befehl angeben.

| Option | Beschreibung | 
| -------| ------------|
| _planIdentifier_ | Der Name oder die GUID des Serviceplans, der aktiviert werden soll. Wenn Sie einen nicht eindeutigen Serviceplannamen eingeben, wie zum Beispiel 'Standard' oder 'Basic', werden Sie dazu aufgefordert, eine Auswahl aus einer angezeigten Liste mit Serviceplänen zu treffen. Wählen Sie die Servicekategorie auf der Homepage aus, um einen Serviceplannamen anzugeben. Wählen Sie dann **Hinzufügen** aus, um die Services für diese Kategorie anzuzeigen. Klicken Sie auf den Servicenamen, um die Detailansicht zu öffnen; anschließend können Sie die Namen der für diesen Service verfügbaren Servicepläne anzeigen. |
| _organization_ | Der Name oder die GUID der Organisation, für die Sichtbarkeit hinzugefügt werden soll. Sie können
die Sichtbarkeit des Service für mehrere Organisationen aktivieren, indem Sie zusätzliche Organisationsnamen oder GUIDs im Befehl angeben. |  
{: caption="Tabelle 16. Optionen für den cf-Befehl 'ba edit-service-plan-visibilities'" caption-side="top"}

Sie können auch **`ba espv`** als Alias für den längeren Befehlsnamen **`ba edit-service-plan-visibility`** verwenden.
{: tip}

## Berichte verwalten
{: #admin_add_report}

### Berichte hinzufügen
{: #admin_adding_report}

Verwenden Sie den folgenden Befehl, um einen Sicherheitsbericht hinzuzufügen:

```
cf ba add-report <category> <date> <PDF|TXT|LOG> <RTF>
```
{: codeblock}

Wenn Sie für die Berichtsberechtigung über Schreibzugriff verfügen, können Sie eine neue Kategorie erstellen und für die Benutzer einen Bericht in einem zulässigen Format hinzufügen. Geben Sie den neuen Kategorienamen für den Parameter **`category`** ein oder fügen Sie den neuen Bericht einer vorhandenen Kategorie hinzu.

| Option | Beschreibung | 
| -------| ------------|
| _category_ | Die Kategorie für den Bericht. Wenn der Name mindestens ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen.|
| _date_ | Das Berichtsdatum im Format JJJJMMTT. |  
| _filePath_ | Der Pfad für die PDF-Datei, Textdatei oder Protokolldatei des Berichts, die hochgeladen werden soll. |
| _RTF_ | Eine Option zum Einschluss einer RTF-Version (Rich Text Format) der PDF. Diese Option gilt nur, wenn Sie einen Pfad zur PDF-Datei für den Bericht angeben. Die RTF-Version wird zum Indexieren und Suchen verwendet. |
{: caption="Tabelle 17. Optionen für den cf-Befehl 'ba add-report'" caption-side="top"}

Sie können auch **`ba ar`** als Alias für den längeren Befehlsnamen **`ba add-report`** verwenden.
{: tip}

### Berichte löschen
{: #admin_del_report}

Verwenden Sie den folgenden Befehl, um einen Sicherheitsbericht zu löschen:

```
cf ba delete-report <category> <date> <name>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _category_ | Die Kategorie für den Bericht. Wenn der Name mindestens ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen.|
| _date_ | Das Berichtsdatum im Format JJJJMMTT. |  
| _name_ | Der Name des Berichts. |
{: caption="Tabelle 18. Optionen für den cf-Befehl 'ba delete-report'" caption-side="top"}

Sie können auch **`ba d`r** als Alias für den längeren Befehlsnamen **`ba delete-report`** verwenden.
{: tip}

### Berichte abrufen
{: #admin_retr_report}

Verwenden Sie den folgenden Befehl, um einen Sicherheitsbericht abzurufen:

```
cf ba retrieve-report <search>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;search&gt;</dt>
<dd class="pd">Der Dateiname des Berichts. Wenn ein Leerzeichen im Namen enthalten ist, setzen Sie den Namen in Anführungszeichen.</dd>
</dl>

Sie können auch **`ba rr`** als Alias für den längeren Befehlsnamen **`ba retrieve-report`** verwenden.
{: tip}

## Metrikinformationen zu Ressourcen anzeigen
{: #cliresourceusage}

Sie können Metrikinformationen zu Ressourcen anzeigen, beispielsweise Hauptspeicher- und Plattenbelegung oder CPU-Auslastung. Es wird eine Zusammenfassung der verfügbaren physischen und reservierten Ressourcen sowie der Nutzung dieser Ressourcen angezeigt. Zudem werden Nutzungsdaten zu Droplet Execution Agents (DEAs) und Diego-Zellen (Diego-Architektur) angezeigt. Verwenden Sie den folgenden Befehl, um die Metrikinformationen zu Ressourcen anzuzeigen:

```
cf ba resource-metrics
```

Sie können auch **`ba rsm`** als Alias für den längeren Befehlsnamen **`ba resource-metrics`** verwenden.
{: tip}

## Verlaufsprotokoll für Ressourcenmetriken anzeigen
{: #cliresourceusagehistory}

Sie können das Verlaufsprotokoll für Ressourcenmetriken für die Hauptspeicher- und Plattenspeichernutzung abrufen. Die zurückgegebenen Metriken umfassen die Menge der genutzten Ressourcen gegenüber der Gesamtmenge der verfügbaren Ressourcen sowohl für die physischen als auch für die reservierten Ressourcen. Protokolldaten für die Hauptspeicher- und Plattenspeichernutzung können in stündlichen, täglichen oder monatlichen Intervallen angezeigt werden. Zum Abrufen von Daten innerhalb eines bestimmten Datumsbereichs können Sie Anfangs- und Enddatumsangaben machen. Die Standardeinstellung für die Protokolldaten, wenn kein Datum angegeben wird, lautet: Hauptspeicherdaten in stündlichen Intervallen für die letzten 48 Stunden. Die Daten werden in absteigender Reihenfolge angezeigt, wobei die neuesten Datumsangaben am Anfang stehen. Verwenden Sie den folgenden Befehl, um die Verlaufsprotokolldaten zu Ressourcenmetriken anzuzeigen:

```
cf ba resource-metrics-history <hourly|daily|monthly>  <memory|disk >  <start|end>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| --hourly | View the historical data for the last 48 hours. This is the default value. |
| --daily | View the historical data daily average for the last 30 days. |  
| --monthly | View the historical data monthly average for the last 6 months. |
| --memory | View the used and total reserved and physical memory. |
| --disk | View the used and total reserved and physical disk. | 
| --start | Specify a start date for daily or monthly in the format of mm-dd-yyyy, or start date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
| --end | Specify an end date for daily or monthly in the format of mm-dd-yyyy, or end date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
{: caption="Tabelle 19. Optionen für den cf-Befehl 'ba resource-metrics-history'" caption-side="top"}

**Beispiele**

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

Sie können die obige Liste mit Befehlsparametern und Beispielen mit dem folgenden Befehl anzeigen:

```
cf ba resource-metrics-history -help
```

Sie können auch **`ba rsmh`** als Alias für den längeren Befehlsnamen **`ba resource-metrics-history`** verwenden.
{: tip}

## Service-Broker verwalten
{: #admin_servbro}

### Service-Broker auflisten
{: #clilistservbro}

Verwenden Sie den folgenden Befehl, um Service-Broker aufzulisten:

```
cf ba service-brokers <broker_name>
```
{: codeblock}

Geben Sie zum Auflisten aller Service-Broker den Befehl ohne den Parameter **`broker_name`** ein.

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">Der Name des angepassten Service-Brokers. Verwenden Sie diesen Parameter, wenn Sie Informationen zu einem bestimmten Service-Broker abrufen wollen. Optional.</dd>
</dl>

Sie können auch **`ba sb`** als Alias für den längeren Befehlsnamen **`ba service-brokers`** verwenden.
{: tip}

### Service-Broker hinzufügen
{: #cliaddservbro}

Verwenden Sie den folgenden Befehl, um einen Service-Broker hinzuzufügen, damit Sie einen angepassten Service zum {{site.data.keyword.Bluemix_notm}}-Katalog hinzufügen können:

```
cf ba add-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _brokerName_ | Der Name des angepassten Service-Brokers. |
| _userName_ | Der Benutzername für das Konto, das Zugriff auf den Service-Broker hat. |  
| _password_ | Das Kennwort für das Konto, das Zugriff auf den Service-Broker hat. |
| _brokerURL_ | Die URL für den Service-Broker. |
{: caption="Tabelle 20. Optionen für den cf-Befehl 'ba add-service-broker'" caption-side="top"}

Sie können auch **`ba asb`** als Alias für den längeren Befehlsnamen **`ba add-service-broker`** verwenden.
{: tip}

### Service-Broker löschen
{: #clidelservbro}

Verwenden Sie den folgenden Befel, um einen Service-Broker zu löschen und damit den angepassten Service aus dem
{{site.data.keyword.Bluemix_notm}}-Katalog zu entfernen:

```
cf ba delete-service-broker <service_broker>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;service_broker&gt;</dt>
<dd class="pd">Der Name oder die GUID des angepassten Service-Brokers.</dd>
</dl>

Sie können auch **`ba dsb`** als Alias für den längeren Befehlsnamen **`ba delete-service-broker`** verwenden.
{: tip}

### Service-Broker aktualisieren
{: #cliupdservbro}

Verwenden Sie den folgenden Befehl, um einen Service-Broker zu aktualisieren:

```
cf ba update-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _brokerName_ | Der Name des angepassten Service-Brokers. |
| _userName_ | Der Benutzername für das Konto, das Zugriff auf den Service-Broker hat. |  
| _password_ | Das Kennwort für das Konto, das Zugriff auf den Service-Broker hat. |
| _brokerURL_ | Die URL für den Service-Broker. |
{: caption="Tabelle 21. Optionen für den cf-Befehl 'ba update-service-broker'" caption-side="top"}

Sie können auch **`ba usb`** als Alias für den längeren Befehlsnamen **`ba update-service-broker`** verwenden.
{: tip}

## Anwendungssicherheitsgruppen verwalten
{: #admin_secgro}

Zum Arbeiten mit Anwendungssicherheitsgruppen (Application Security Groups, ASGs) müssen Sie ein Administrator mit voller Berechtigung für die lokale oder dedizierte Umgebung sein. Alle Benutzer in der Umgebung können die verfügbaren ASGs für die Organisation auflisten, die Ziel des Befehls ist. Zum Erstellen, Aktualisieren oder Binden von ASGs müssen Sie jedoch Administrator für die {{site.data.keyword.Bluemix_notm}}-Umgebung sein.

ASGs dienen als virtuelle Firewalls, die den abgehenden Datenverkehr aus den Apps in Ihre {{site.data.keyword.cloud_notm}}-Umgebung steuern. Jede ASG besteht aus einer Liste mit Regeln, die den Datenverkehr und die Kommunikation in das externe Netz oder aus diesem Netz definieren. Sie können eine oder mehrere ASGs an einen bestimmten Sicherheitsgruppensatz (z. B. an einen Gruppensatz, der für die Anwendung des globalen Zugriffs verwendet wird) oder an Bereiche innerhalb einer Organisation in der {{site.data.keyword.Bluemix_notm}}-Umgebung binden.

Bei der Erstinstallation von {{site.data.keyword.Bluemix_notm}} wird der gesamte Zugriff auf das externe Netz eingeschränkt. Zwei von IBM erstellte Sicherheitsgruppen (`public_networks` und `dns`) ermöglichen den globalen Zugriff auf das externe Netz, wenn Sie diese Gruppen an die Cloud Foundry-Standardsicherheitsgruppensätze binden. Die beiden Sicherheitsgruppensätze in Cloud Foundry zur Anwendung des globalen Zugriffs sind die Gruppensätze **Default Staging** und **Default Running**. Von diesen Gruppensätzen werden die Regeln für den Datenverkehr auf alle aktiven Apps bzw. alle Staging-Apps angewendet. Wenn Sie keine Bindung an diese beiden Sicherheitsgruppensätze herstellen möchten, können Sie die Bindung an die Cloud Foundry-Gruppensätze aufheben und die Sicherheitsgruppe anschließend an einen bestimmten Bereich binden. Weitere Informationen finden Sie in [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

Durch das Aufheben der Bindung für die Gruppensätze **Default Staging** oder **Default Running** an die beiden von IBM erstellten Sicherheitsgruppen `public_networks` und `dns` wird der globale Zugriff auf das externe Netz inaktiviert. Verwenden Sie das Aufheben der Bindung mit Vorsicht und berücksichtigen Sie dabei die potenziellen Auswirkungen auf die Ausführung und das Staging von Apps in Ihrer Umgebung.
{: important}

Die folgenden Befehle, die Ihnen die Arbeit mit Sicherheitsgruppen ermöglichen, basieren auf Cloud Foundry Version 1.6. Weitere Informationen einschließlich der Angaben zu erforderlichen und optionalen Feldern finden Sie in den Cloud Foundry-Informationen im Abschnitt [Creating Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

### Sicherheitsgruppen auflisten
{: #clilissecgro}

Verwenden Sie den folgenden Befehl, um alle Sicherheitsgruppen aufzulisten:

```
cf ba security-groups
```
{: codeblock}

Verwenden Sie den folgenden Befehl, um die Details einer bestimmten Sicherheitsgruppe anzuzeigen:

```
cf ba security-groups <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba sg`** als Alias für den längeren Befehlsnamen **`ba security-groups`** verwenden.
{: tip}

### Sicherheitsgruppe erstellen
{: #clicreasecgro}

Verwenden Sie den folgenden Befehl, um eine Sicherheitsgruppe zu erstellen:
```
cf ba create-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

Den Namen erstellter Sicherheitsgruppen wird das Präfix `adminconsole_` vorangestellt, um sie von den Sicherheitsgruppen zu unterscheiden, die von IBM erstellt werden.

| Option | Beschreibung | 
| -------| ------------|
| _groupName_ | Der Name der Sicherheitsgruppe. |
| _filePath_ |Der absolute oder relative Pfad zu einer Regeldatei. |  
{: caption="Tabelle 22. Optionen für den cf-Befehl 'ba create-security-group'" caption-side="top"}

Sie können auch **`ba csg`** als Alias für den längeren Befehlsnamen **`ba create-security-group`** verwenden.
{: tip}

Weitere Informationen zur Erstellung von Sicherheitsgruppen und Regeln, die den abgehenden Datenverkehr definieren, finden Sie in [Creating Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

### Sicherheitsgruppe aktualisieren
{: #cliupdsecgro}

Verwenden Sie den folgenden Befehl, um eine Sicherheitsgruppe zu aktualisieren:

```
cf ba update-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _groupName_ | Der Name der Sicherheitsgruppe. |
| _filePath_ |Der absolute oder relative Pfad zu einer Regeldatei. |  
{: caption="Tabelle 23. Optionen für den cf-Befehl 'ba update-security-group'" caption-side="top"}

Sie können auch **`ba usg`** als Alias für den längeren Befehlsnamen **`ba update-security-group`** verwenden.
{: tip}

### Sicherheitsgruppe löschen
{: #clidelsecgro}

Verwenden Sie den folgenden Befehl, um eine Sicherheitsgruppe zu löschen:
```
cf ba delete-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba dsg`** als Alias für den längeren Befehlsnamen **`ba delete-security-group`** verwenden.
{: tip}

### Sicherheitsgruppen binden
{: #clibindsecgro}

Verwenden Sie den folgenden Befehl, um eine Bindung zum Sicherheitsgruppensatz 'Default Staging' herzustellen:

```
cf ba bind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba bssg`** als Alias für den längeren Befehlsnamen **`ba bind-staging-security-group`** verwenden.
{: tip}

Verwenden Sie den folgenden Befehl, um eine Bindung zum Sicherheitsgruppensatz 'Default Running' herzustellen:

```
cf ba bind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba brsg`** als Alias für den längeren Befehlsnamen **`ba bind-running-security-group`** verwenden.
{: tip}

Verwenden Sie den folgenden Befehl, um eine Sicherheitsgruppe an einen Bereich zu binden:

```
cf ba bind-security-group <security-group> <org> <space>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _groupName_ | Der Name der Sicherheitsgruppe. |
| _org_ | Der Name der Organisation, an die die Sicherheitsgruppe gebunden wird. |
| _space_ | Der Name des Bereichs innerhalb der Organisation, an die die Sicherheitsgruppe gebunden wird.|
{: caption="Tabelle 24. Optionen für den cf-Befehl 'ba bind-security-group'" caption-side="top"}

Sie können auch **`ba bsg`** als Alias für den längeren Befehlsnamen **`ba bind-security-group`** verwenden.
{: tip}

Weitere Informationen zum Binden von Sicherheitsgruppen finden Sie in [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

### Bindung von Sicherheitsgruppen aufheben
{: #cliunbindsecgro}

Durch das Aufheben der Bindung des Gruppensatzes 'Default Staging' an die beiden von IBM erstellten Sicherheitsgruppen `public_networks` und `dns` wird der globale Zugriff auf das externe Netz inaktiviert. Verwenden Sie das Aufheben der Bindung mit Vorsicht und berücksichtigen Sie dabei die Auswirkungen auf das Staging von Apps in Ihrer Umgebung. Verwenden Sie den folgenden Befehl, um die Bindung zu einem Sicherheitsgruppensatz 'Default Staging' aufzuheben:

```
cf ba unbind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba ussg`** als Alias für den längeren Befehlsnamen **`ba unbind-staging-security-group`** verwenden.
{: tip}

Durch das Aufheben der Bindung des Gruppensatzes 'Default Running' an die beiden von IBM erstellten Sicherheitsgruppen `public_networks` und `dns` wird der globale Zugriff auf das externe Netz inaktiviert. Verwenden Sie das Aufheben der Bindung mit Vorsicht und berücksichtigen Sie dabei die Auswirkungen auf alle aktiven Apps in Ihrer Umgebung. Verwenden Sie den folgenden Befehl, um die Bindung zu einem Sicherheitsgruppensatz 'Default Running' aufzuheben:

```
cf ba unbind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;security-group&gt;</dt>
<dd class="pd">Der Name der Sicherheitsgruppe.</dd>
</dl>

Sie können auch **`ba brsg`** als Alias für den längeren Befehlsnamen **`ba unbind-running-security-group`** verwenden.
{: tip}

Verwenden Sie den folgenden Befehl, um die Bindung einer Sicherheitsgruppe zu einem Bereich aufzuheben:

```
cf ba unbind-security-group <security-group> <org> <space>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _groupName_ | Der Name der Sicherheitsgruppe. |
| _org_ | Der Name der Organisation, für die die Bindung an die Sicherheitsgruppe aufgehoben wird. |
| _space_ | Der Name des Bereichs innerhalb der Organisation, für die die Bindung an die Sicherheitsgruppe aufgehoben wird.|
{: caption="Tabelle 25. Optione für den cf-Befehl 'ba unbind-security-group'" caption-side="top"}

Sie können auch **`ba usg`** als Alias für den längeren Befehlsnamen **`ba unbind-security-group`** verwenden.
{: tip}

Weitere Informationen zum Aufheben der Bindung von Sicherheitsgruppen finden Sie in [Unbinding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

## Buildpacks verwalten
{: #admin_buildpack}

### Buildpacks auflisten
{: #clilistbuildpack}

Wenn Sie über eine Schreibberechtigung für den App-Katalog verfügen, können Sie Buildpacks auflisten. Verwenden Sie den folgenden Befehl, um alle Buildpacks aufzulisten oder ein  bestimmtes Buildpack anzuzeigen:

```
cf ba buildpacks <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">Ein optionaler Parameter zur Angabe eines bestimmten Buildpacks, das angezeigt werden soll.</dd>
</dl>

Sie können auch **`ba lb`** als Alias für den längeren Befehlsnamen **`ba buildpacks`** verwenden.
{: tip}

### Buildpack erstellen und hochladen
{: #clicreupbuildpack}

Wenn Sie über eine Schreibberechtigung für den App-Katalog verfügen, können Sie ein Buildpack erstellen und hochladen. Jede komprimierte Datei mit der Dateierweiterung `.zip` kann hochgeladen werden. Verwenden Sie den folgenden Befehl, um ein Buildpack hochzuladen:

```
cf ba create-buildpack <buildpack_name> <file_path> <position>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _name_ | Der Name des hochzuladenden Buildpacks. |
| _filePath_ | Der Pfad zur komprimierten Datei des Buildpacks. |
| _position_ | Die Reihenfolge, in der die Buildpacks während der automatischen Buildpackerkennung geprüft werden. |
{: caption="Tabelle 26. Optionen für den cf-Befehl 'ba create-buildpack'" caption-side="top"}

Sie können auch **`ba cb`** als Alias für den längeren Befehlsnamen **`ba create-buildpack`** verwenden.
{: tip}

### Buildpack aktualisieren
{: #cliupdabuildpack}

Wenn Sie über eine Schreibberechtigung für den App-Katalog verfügen, können Sie ein vorhandenes Buildpack aktualisieren. Verwenden Sie den folgenden Befehl, um ein Buildpack zu aktualisieren:
```
cf ba update-buildpack <buildpack_name> <position> <enabled> <locked>
```
{: codeblock}

| Option | Beschreibung | 
| -------| ------------|
| _name_ | Der Name des zu aktualisierenden Buildpacks. |
| _position_ | Die Reihenfolge, in der die Buildpacks während der automatischen Buildpackerkennung geprüft werden. |
| _enabled_ | Gibt an, ob das Buildpack für das Staging verwendet wird. |
| _locked_ | Gibt an, ob das Buildpack gesperrt ist, um Aktualisierungen zu verhindern. | 
{: caption="Tabelle 27. Optionen für den cf-Befehl 'ba update-buildpack'" caption-side="top"}

Sie können auch **`ba ub`** als Alias für den längeren Befehlsnamen **`ba update-buildpack`** verwenden.
{: tip}

### Buildpack löschen
{: #clidelbuildpack}

Wenn Sie über eine Schreibberechtigung für den App-Katalog verfügen, können Sie ein vorhandenes Buildpack löschen. Verwenden Sie den folgenden Befehl, um ein Buildpack zu löschen:
```
cf ba delete-buildpack <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">Der Name des zu löschenden Buildpacks.</dd>
</dl>

Sie können auch **`ba db`** als Alias für den längeren Befehlsnamen **`ba delete-buildpack`** verwenden.
{: tip}
