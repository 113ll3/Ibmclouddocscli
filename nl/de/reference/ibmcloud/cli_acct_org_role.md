---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Konten, Benutzer und Organisationen
 {: #ibmcloud_commands_account}

 Verwenden Sie die folgenden Befehle, um Konten, Benutzer in einem Konto und die Organisationen, Bereiche, Rollen und Domänenzertifikate von Cloud Foundry-Services zu verwalten.
  {: shortdesc}

  <table summary="ibmcloud-Befehle zur Verwaltung von Konten, Organisationen, Bereichen und Rollen.">
   <thead>
   </thead>
   <tbody>
   <tr>
   <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
   <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
   <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
   <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
   <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
   </tr>
   <tr>
   <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
   <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
   <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
   <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
   <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
   </tr>
   <tr>
   <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
   <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
   <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
   <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
   <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
   </tr>
   <tr>
   <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
   <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
   <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
   <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
   <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
  </tr>
   <td>[ibmcloud account list](cli_acct_org_role.html#ibmcloud_account_list)</td>
   <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
   <td>[ibmcloud account users](cli_acct_org_role.html#ibmcloud_account_users)</td>
   <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
   <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
   </tr>
   <tr>
    <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
   </tr>
   </tbody>
   </table>

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
   <dd>Ausgabeformat angeben, zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
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

Die Informationen für die angegebene Organisation anzeigen.

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
   <dd>Ausgabeformat angeben, zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
   </dl>

<strong>Beispiele</strong>:

Informationen für die Organisation `IBM` mit der GUID anzeigen

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

Alle Bereiche auflisten

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
   <dd>Ausgabeformat angeben, zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. </dd>
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

Informationen des angegebenen Bereichs anzeigen

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
   <dd>Ausgabeformat angeben, zum gegenwärtigen Zeitpunkt wird nur JSON unterstützt. Alle anderen Ausgaben für den Bereich werden unterdrückt. Diese Option ist gegenseitig ausschließend mit '--guid'.</dd>
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

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-space ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Benutzer in der angegebenen Organisation nach Rolle anzeigen

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>ORG_NAME (erforderlich)</dt>
<dd>Der Name der Organisation.</dd>
<dt>-a (optional)</dt>
<dd>Alle Benutzer in der angegebenen Organisation auflisten (nicht nach Rolle gruppiert).</dd>
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

Alle Organisationsrollen des aktuellen Benutzers abrufen

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
**Hinweis:** Sie können die Organisations-/Bereichsrolle mithilfe der CLI festlegen; zum Festlegen der übrigen Berechtigungen müssen Sie jedoch die Benutzerschnittstelle verwenden. Weitere Informationen finden Sie in [Benutzerzugriff zuweisen](/docs/iam/assignaccess.html#assignaccess).
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

## ibmcloud account users
{: #ibmcloud_account_users}

Dem Konto zugeordnete Benutzer anzeigen. Diese Operation kann nur vom Kontoeigner ausgeführt werden.

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
   <dd>Organisationsrolle. Gültige Eingabe: OrgManager, BillingManager, OrgAuditor und OrgUser. Wenn keine Angabe erfolgt, wird die Organisationsbenutzerrolle festgelegt.</dd>
   <dt>-s SPACE</dt>
   <dd>Bereich, in den der Benutzer eingeladen werden soll</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Bereichsrolle. Gültige Eingabe: SpaceManager, SpaceDeveloper und SpaceAuditor.</dd>
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
