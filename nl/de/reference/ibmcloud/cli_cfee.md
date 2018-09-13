---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry Enterprise Environments (CFEE) (Beta)
{: #ibmcloud_commands_cfee}

Verwenden Sie die folgenden Befehle, um CFEE-Organisationen, -Bereiche, -Benutzer und -Rollen zu verwalten.
{: shortdesc}

<table summary="Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE-Umgebungen auflisten

```
ibmcloud cfee environments
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Details einer CFEE-Umgebung anzeigen

```
ibmcloud cfee environment NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>NAME (erforderlich)</dt>
   <dd>Der Name der Umgebung, die angezeigt werden soll.</dd>
   <dt>--id</dt>
   <dd>Nur ID anzeigen</dd>
  </dl>

<strong>Beispiele</strong>:

Details der CFEE-Umgebung `env_example` anzeigen:

```
ibmcloud cfee environment env_example
```

ID der CFEE-Umgebung `env_example` anzeigen:

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Alle Organisationen auflisten

```
ibmcloud cfee orgs [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Alle Organisationen auflisten:

```
ibmcloud cfee orgs
```

Alle Organisationen der CFEE-Umgebung `env_example` auflisten:

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Details einer Organisation anzeigen

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--guid</dt>
   <dd>Nur GUID der Organisation anzeigen, alle anderen Ausgaben für die Organisation werden unterdrückt</dd>
  </dl>

<strong>Beispiele</strong>:

Details der CFEE-Organisation `org_example` anzeigen:

```
ibmcloud cfee org org_example
```

Details der CFEE-Organisation `org_example` der CFEE-Umgebung `env_example` anzeigen:

```
ibmcloud cfee org org_example --env env_example
```

GUID der CFEE-Organisation `org_example` anzeigen:

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Eine Organisation erstellen

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, die erstellt wird.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>Kontingent, das der neu erstellten Organisation zugewiesen werden soll (Standardkontingent verwenden, wenn keine Angabe gemacht wird)</dd>
  </dl>

<strong>Beispiele</strong>:

CFEE-Organisation `org_example` erstellen:

```
ibmcloud cfee org-create org_example
```

CFEE-Organisation `org_example` der CFEE-Umgebung `env_example` erstellen:

```
ibmcloud cfee org-create org_example --env env_example
```

CFEE-Organisation `org_example` mit Kontingent `quote_example` erstellen:

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Eine Organisation löschen

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, die gelöscht wird.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-f, --force</dt>
   <dd>Löschen ohne Bestätigung erzwingen</dd>
  </dl>

<strong>Beispiele</strong>:

CFEE-Organisation `org_example` löschen:

```
ibmcloud cfee org-delete org_example
```

CFEE-Organisation `org_example` der CFEE-Umgebung `env_example` löschen:

```
ibmcloud cfee org-delete org_example --env env_example
```

CFEE-Organisation `org_example` ohne Bestätigung löschen:

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Benutzer in der angegebenen Organisation nach Rolle anzeigen

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>-a, --all</dt>
   <dd>Alle Benutzer in der angegebenen Organisation auflisten</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Benutzer in CFEE-Organisation `org_example` anzeigen:

```
ibmcloud cfee org-users org_example
```

Benutzer in CFEE-Organisation `org_example` der CFEE-Umgebung `env_example` anzeigen:

```
ibmcloud cfee org-users org_example --env env_example
```

Alle Benutzer in CFEE-Organisation `org_example` auflisten:

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Organisationsrolle einem Benutzer zuweisen (Organisationsmanager erforderlich)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der zugewiesen wird.</dd>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugeordnet wird.</dd>
   <dt>ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, der dieser Benutzer zugeordnet wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Rolle `BillingManager` dem Benutzer `test@exmaple.com` in der Organisation `org_example` zuweisen:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

Rolle `BillingManager` dem Benutzer `test@exmaple.com` in der Organisation `org_example` der CFEE-Umgebung `env_example` zuweisen:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Organisationsrolle eines Benutzers entfernen (nur Organisationsmanager oder Benutzer selbst)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der entfernt wird.</dd>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>ROLE (erforderlich)</dt>
   <dd>Der Name der Organisationsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>OrgManager: Diese Rolle kann Benutzer einladen und verwalten, Pläne auswählen und ändern sowie Ausgabenlimits festlegen.</li>
   <li>BillingManager: Diese Rolle kann die Abrechnungskonto- und Zahlungsinformationen erstellen und verwalten.</li>
   <li>OrgAuditor: Diese Rolle verfügt über Lesezugriff auf die Organisationsinformationen und -berichte.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Rolle `BillingManager` des Benutzers `test@exmaple.com` aus Organisation `org_example` entfernen:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

Rolle `BillingManager` des Benutzers `test@exmaple.com` aus der Organisation `org_example` der CFEE-Umgebung `env_example` entfernen:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Alle Bereiche auflisten

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Alle Bereiche auflisten

```
ibmcloud cfee spaces
```

Alle Bereiche der Organisation `org_example` und der CFEE-Umgebung `env_example` auflisten

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Informationen des angegebenen Bereichs anzeigen

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs, der angezeigt werden soll.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--guid</dt>
   <dd>GUID eines angegebenen Bereichs abrufen und anzeigen. Alle anderen Ausgaben für den Bereich werden unterdrückt.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>--security-group-rules</dt>
   <dd>Regeln für alle Sicherheitsgruppen abrufen, die dem Bereich zugeordnet sind.</dd>
  </dl>

<strong>Beispiele</strong>:

Informationen zum Bereich `space_example` anzeigen:

```
ibmcloud cfee space space_example
```

GUID zum Bereich `space_example` abrufen und anzeigen:

```
ibmcloud cfee space space_example --guid
```

Regeln für alle Sicherheitsgruppen, die dem Bereich `space_example` zugeordnet sind, anzeigen:

```
ibmcloud cfee space space_example --security-group-rules
```

Informationen zum Bereich `space_example` der Organisation `org_example` und der CFEE-Umgebung `env_example` anzeigen:

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Einen neuen Bereich erstellen

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs, der erstellt wird.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Neuen Bereich `space_example` erstellen:

```
ibmcloud cfee space-create space_example
```

Neuen Bereich `space_example` unter der Organisation `org_example` und der CFEE-Umgebung `env_example` erstellen:

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Bereich umbenennen

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>OLD_NAME (erforderlich)</dt>
   <dd>Der bisherige Name des Bereichs, der umbenannt werden soll.</dd>
   <dt>NEW_NAME (erforderlich)</dt>
   <dd>Der neue Name des Bereichs, der umbenannt werden soll.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Bereich `space_example` in `new_pace_example` umbenennen:

```
ibmcloud cfee space-rename space_example new_pace_example
```

Umbenennung des Bereichs `space_example` in `new_pace_example` unter der Organisation `org_example` und der CFEE-Umgebung `env_example` durchführen:

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Bereich löschen

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs, der gelöscht werden soll.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
   <dt>-f, --force</dt>
   <dd>Löschung ohne Bestätigung erzwingen.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organisationsname. Standardmäßig wird die aktuelle Organisation verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Bereich `space_example` löschen:

```
ibmcloud cfee space-delete space_example
```

Bereich `space_example` unter der Organisation `org_example` und der CFEE-Umgebung `env_example` ohne Bestätigung löschen:

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Bereichsrolle einem Benutzer zuordnen

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der zugewiesen wird.</dd>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, der dieser Benutzer zugewiesen wird.</dd>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs, dem dieser Benutzer zugewiesen wird.</dd>
   <dt>ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, der dieser Benutzer zugewiesen wird. Beispiel:
   <ul>
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Benutzer `test@exmaple.com` der Organisation `org_example` und dem Bereich `space_example` mit der Rolle `SpaceManager` zuweisen:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Benutzer `test@exmaple.com` der Organisation `org_example` und dem Bereich `space_example` mit der Rolle `SpaceManager` unter der Umgebung `env_example` zuweisen:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Bereichsrolle eines Benutzers entfernen

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>USER_EMAIL (erforderlich)</dt>
   <dd>Die E-Mail-Adresse des Benutzers, der entfernt wird.</dd>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation, aus der dieser Benutzer entfernt wird.</dd>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs, aus dem dieser Benutzer entfernt wird.</dd>
   <dt>ROLE (erforderlich)</dt>
   <dd>Der Name der Bereichsrolle, aus der dieser Benutzer entfernt wird. Beispiel:
   <ul>
   <li>SpaceManager: Diese Rolle kann Benutzer einladen und verwalten sowie Funktionen für einen angegebenen Bereich aktivieren.</li>
   <li>SpaceDeveloper: Diese Rolle kann Apps und Services erstellen und verwalten sowie Protokolle und Berichte anzeigen.</li>
   <li>SpaceAuditor: Diese Rolle kann Protokolle, Berichte und Einstellungen für den Bereich anzeigen.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Benutzer `test@exmaple.com` aus der Organisation `org_example` und dem Bereich `space_example` mit der Rolle `SpaceManager` entfernen:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Benutzer `test@exmaple.com` aus der Organisation `org_example` und dem Bereich `space_example` mit der Rolle `SpaceManager` unter der Umgebung `env_example` entfernen:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Alle Bereichsrollen des aktuellen Benutzers unter einer bestimmten Organisation abrufen

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Alle Bereichsrollen des aktuellen Benutzers unter der Organisation `org_example` abrufen:

```
ibmcloud cfee space-roles org_example
```

Alle Bereichsrollen des aktuellen Benutzers unter der Organisation `org_example` und der Umgebung `env_example` abrufen:

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Benutzer im angegebenen Bereich nach Rolle anzeigen

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
  <dl>
   <dt>ORG (erforderlich)</dt>
   <dd>Der Name der Organisation.</dd>
   <dt>SPACE (erforderlich)</dt>
   <dd>Der Name des Bereichs.</dd>
   <dt>--env ENV</dt>
   <dd>Der Name der CFEE-Umgebung. Standardmäßig wird die aktuelle CFEE-Umgebung verwendet, wenn keine Angabe gemacht wurde.</dd>
  </dl>

<strong>Beispiele</strong>:

Alle Benutzer im Bereich `space_example` und der Organisation `org_example` anzeigen:

```
ibmcloud cfee space-users org_example space_example
```

Alle Benutzer im Bereich `space_example` und der Organisation `org_example` und der Umgebung `env_example` anzeigen:

```
ibmcloud cfee space-users org_example space_example --env env_example
```
