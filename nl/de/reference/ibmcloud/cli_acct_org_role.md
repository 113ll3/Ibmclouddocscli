---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# Konten, Benutzer und Cloud-Foundry-Organisationen verwalten
{: #ibmcloud_commands_account}

Verwenden Sie die folgenden Befehle, um Konten, Benutzer in einem Konto und die Organisationen, Bereiche und Rollen von öffentlichen Cloud Foundry-Umgebungen zu verwalten.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Alle Organisationen auflisten

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Regionsname. Die Organisationen in der angegebenen Region auflisten. Standardmäßig wird die aktuelle Region verwendet, wenn keine Angabe gemacht wurde. Wenn 'all' angegeben ist, werden die Organisationen in allen Regionen aufgelistet.</dd>
   <dt>--guid</dt>
   <dd>GUID der Organisationen anzeigen. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>Konto-ID. Organisationen unter dem angegebenen Konto auflisten. Standardmäßig aktuelles Konto verwenden, falls keine Angabe gemacht wird. Wenn 'all' angegeben ist, werden die Organisationen unter allen Konten aufgelistet. Diese Option ist gegenseitig ausschließend mit '-u'.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Name des Kontoeigners. Organisationen unter den Konten auflisten, deren Eigner der angegebene Benutzer ist. Standardmäßig aktuelles Konto verwenden, falls keine Angabe gemacht wird. Wenn 'all' angegeben ist, werden die Organisationen unter allen Konten aufgelistet. Diese Option ist gegenseitig ausschließend mit '-c'.</dd>
   </dl>

<strong>Beispiele</strong>:

Alle Organisationen in der Region: `us-south` auflisten und GUID anzeigen

```
ibmcloud account orgs -r us-south --guid
```

Alle Organisationen im JSON-Format auflisten

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Informationen der angegebenen Organisation anzeigen

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>-r REGION</dt>
   <dd>Regionsname. Wenn nicht angegeben, wird standardmäßig die aktuelle Region verwendet. Bei Angabe von 'all' werden Organisationen mit dem angegebenen Namen in allen Regionen aufgelistet.</dd>
   <dt>--guid</dt>
   <dd>GUID einer angegebenen Organisation abrufen und anzeigen. Alle anderen Ausgaben für die Organisation werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
   <dt>--output REGION</dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
   </dl>

<strong>Beispiele</strong>:

Informationen der Organisation `IBM` mit der GUID anzeigen

```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Eine neue Organisation erstellen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, die erstellt wird.</dd>
   <dt>-f</dt>
   <dd>Erstellung ohne Bestätigung erzwingen.</dd>
   </dl>

<strong>Beispiele</strong>:

Organisation mit dem Namen `IBM` erstellen:

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Repliziert eine Organisation aus der aktuellen Region in eine andere Region.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der vorhandenen Organisation, die repliziert werden soll.</dd>
   <dt>REGION_NAME (erforderlich)</dt>
   <dd>Der Name der Region, die die replizierte Organisation hostet.</dd>
   </dl>

<strong>Beispiele</strong>:

Die Organisation `myorg` in die Region `eu-gb` replizieren:

```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Eine Organisation umbenennen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>OLD_ORG_NAME (erforderlich)</dt>
   <dd>Der bisherige Name der Organisation, die umbenannt werden soll.</dd>
   <dt>NEW_ORG_NAME (erforderlich)</dt>
   <dd>Der neue Name für die Organisation, die umbenannt werden soll.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Alle Kontobereiche auflisten

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>Organisationsname. Die Bereiche unter der angegebenen Organisation auflisten. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-r REGION-NAM</dt>
   <dd>Regionsname. Die Bereiche unter der angegebenen Region auflisten. Standardmäßig wird die aktuelle Region verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--output FORMAT</dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt.</dd>
   </dl>

<strong>Beispiele</strong>:

Alle Bereiche auflisten:

```
ibmcloud account spaces
```

Alle Bereiche der Organisation `org_example` im JSON-Format auflisten:

```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

Informationen zu einem bestimmten Bereich anzeigen

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs, der angezeigt werden soll.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--guid</dt>
   <dd>GUID eines angegebenen Bereichs abrufen und anzeigen. Alle anderen Ausgaben für den Bereich werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Ausgabeformat angeben. Zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Alle anderen Ausgaben für den Bereich werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
   <dt>--security-group-rules</dt>
   <dd>Regeln für alle Sicherheitsgruppen abrufen, die dem Bereich zugeordnet sind.</dd>
   </dl>

<strong>Beispiele</strong>:

Informationen zum Bereich `space_example` anzeigen:

```
ibmcloud account space space_example
```

GUID zum Bereich `space_example` anzeigen:

```
ibmcloud account space space_example --guid
```

Informationen zum Bereich `space_example` im JSON-Format anzeigen:

```
ibmcloud account space space_example --output JSON
```

Sicherheitsgruppenregeln zum Bereich `space_example` anzeigen:

```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-space](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-space](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-space](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Benutzer in der angegebenen Organisation nach Rolle anzeigen

```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>ORG_NAME (erforderlich)</dt>
<dd>Der Name der Organisation.</dd>
<dt>-a, -all (optional)</dt>
<dd>Alle Benutzer in der angegebenen Organisation auflisten (nicht nach Rolle gruppiert).</dd>
<dt>-r, --region REGION (optional)</dt>
<dd>Regionsname. Standardmäßig wird die aktuelle Region verwendet, wenn keine Angabe gemacht wurde.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Benutzer zur Organisation hinzufügen (Organisationsmanager erforderlich).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Benutzer aus der Organisation entfernen (Organisationsmanager oder nur Benutzer selbst)

```
ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Löschung ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Alle Organisationsrollen eines Benutzers unter dem aktuellen Konto abrufen

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>-u</dt>
   <dd>Benutzer-ID. Wenn keine Angabe erfolgt, wird standardmäßig der aktuelle Benutzer verwendet.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Einem Benutzer eine Organisationsrolle zuweisen. Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der zugeordnet wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugeordnet wird.</dd>
   <dt>ORG_ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, der dieser Benutzer zugeordnet wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
  </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` der Organisation `IBM` mit der Rolle `OrgManager` zuweisen:

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
Sie können Organisations-/Bereichsrollen mithilfe der CLI festlegen. Zum Festlegen der übrigen Berechtigungen müssen Sie jedoch die Benutzerschnittstelle verwenden. Weitere Informationen finden Sie unter [Zugriff auf Ressourcen verwalten](/docs/iam/mngiam.html#iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Eine Organisationsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Organisationsmanager ausgeführt werden.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der entfernt wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>ORG_ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
    </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` aus der Organisation `IBM` und der Rolle `OrgManager` entfernen:

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Benutzer in dem angegebenen Bereich nach Rolle anzeigen

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Einem Benutzer eine Bereichsrolle zuweisen. Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der zugeordnet wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugeordnet wird.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs, dem dieser Benutzer zugeordnet wird.</dd>
   <dt>SPACE_ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, der dieser Benutzer zugeordnet wird. Beispiel:
   <ul>
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
    </dl>

<strong>Beispiele</strong>:

Die Benutzerin `Mary` der Organisation `IBM` und dem Bereich `Cloud` mit der Rolle `SpaceManager` zuweisen:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Eine Bereichsrolle für einen Benutzer entfernen (widerrufen). Diese Operation kann nur von einem Bereichsmanager ausgeführt werden.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>USER_NAME (erforderlich)</dt>
   <dd>Der Name des Benutzers, der entfernt wird.</dd>
   <dt>ORG_NAME (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>SPACE_NAME (erforderlich)</dt>
   <dd>Der Name des Bereichs, aus dem dieser Benutzer entfernt wird.</dd>
   <dt>SPACE_ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
    </dl>


<strong>Beispiele</strong>:

Die Benutzerin `Mary` aus der Organisation `IBM` und dem Bereich `Cloud` mit der Rolle `SpaceManager` entfernen:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Alle Konten des aktuellen Benutzers auflisten

```
ibmcloud account list
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Das Konto der angegebenen Organisation anzeigen (Organisationsbenutzer erforderlich)

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--guid (optional)</dt>
  <dd>Nur die Konto-ID anzeigen</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Kontodetails anzeigen

```
ibmcloud account show
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
</dl>

<strong>Beispiele</strong>:

Details des aktuellen Zielkontos anzeigen:

```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

Bestimmtes Konto aktualisieren

```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Konnektivität des Serviceendpunkts für SoftLayer-Konto aktivieren oder inaktivieren</dd>
</dl>

<strong>Beispiele</strong>:

Konnektivität des Serviceendpunkts für aktuelles Konto aktivieren:

```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Auditprotokolle des Softlayer-Kontos auflisten

```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>Aktion. Auditprotokolle mit der angegebenen Aktion auflisten.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>Enddatum. Auditprotokolle vor dem Enddatum auflisten. Unterstützte Formate: jjjj-MM-ttTHH:mm:ss.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>Objekt. Auditprotokolle mit dem angegebenen Objekt auflisten.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>Objekttyp. Auditprotokolle mit dem angegebenen Objekttyp auflisten.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>Startdatum. Auditprotokolle nach dem Startdatum auflisten. Unterstützte Formate: jjjj-MM-ttTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>Benutzername. Auditprotokolle mit dem angegebenen Benutzernamen auflisten.</dd>
</dl>

<strong>Beispiele</strong>:

Auditprotokolle auflisten

```
ibmcloud account audit-logs
```

## ibmcloud account users
{: #ibmcloud_account_users}

Zeigt die Benutzer an, die dem Konto zugeordnet sind. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Benutzer von einem Konto entfernen (nur Kontoeigner)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>USER_ID (erforderlich)</dt>
<dd>Benutzer-ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>Konto-ID. Wenn keine Angabe erfolgt, wird standardmäßig das aktuelle Konto verwendet.</dd>
<dt>-f, --force</dt>
<dd>Entfernen ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Benutzer für das Konto einladen

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der eingeladen wird.</dd>
   <dt>-o ORG</dt>
   <dd>Organisation, in die der Benutzer eingeladen werden soll</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Organisationsrolle. Gültige Eingabe: OrgManager, BillingManager, OrgAuditor und OrgUser. Bei Auslassung wird die Organisationsbenutzerrolle (OrgUser) festgelegt.</dd>
   <dt>-s SPACE</dt>
   <dd>Bereich, in den der Benutzer eingeladen werden soll</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Bereichsrolle. Gültige Eingaben sind SpaceManager, SpaceDeveloper und SpaceAuditor.</dd>
</dl>

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Einladung erneut an einen Benutzer senden (Kontoadministrator)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der erneut eingeladen wird.</dd>
</dl>

## ibmcloud app domain-cert
{: #accounts-list-domain-cert}

Die Zertifikatsinformationen für eine Domäne auflisten

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>DOMAIN_NAME (erforderlich)</dt>
<dd>Die Domäne, in der das Zertifikat gehostet wird.</dd>
</dl>


<strong>Beispiele</strong>:

Die Zertifikatsinformationen für die Domäne `ibmcxo-eventconnect.com` anzeigen:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #accounts-add-domain-cert}

Der angegebenen Domäne in der aktuellen Organisation ein Zertifikat hinzufügen.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, der das Zertifikat hinzugefügt wird.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Datei mit dem privaten Schlüssel.</dd>
   <dt>-c <i>CERT_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Zertifikatsdatei.</dd>
   <dt>-p <i>PASSWORD</i> (optional)</dt>
   <dd>Das Kennwort für das Zertifikat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (optional)</dt>
   <dd>Der Pfad für die Zwischenzertifikatsdatei.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (optional)</dt>
   <dd>Die Truststore-Datei.</dd>
   </dl>


<strong>Beispiele</strong>:

Zertifikat der Domäne `ibmcxo-eventconnect.com` hinzufügen:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #accounts-remove-domain-cert}

Zertifikat aus der angegebenen Domäne in der aktuellen Organisation entfernen.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, aus der das Zertifikat entfernt werden soll.</dd>
   <dt>-f  (optional)</dt>
   <dd>Löschung ohne Bestätigung erzwingen.</dd>
   </dl>
