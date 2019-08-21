---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Benutzer der klassischen Infrastruktur verwalten
{: #manage-sl-users}

Verwenden Sie die folgenden Befehle, um die Benutzer der klassischen {{site.data.keyword.cloud}}-Infrastruktur zu verwalten.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

Benutzer erstellen:
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--email</dt>
<dd>Die E-Mail-Adresse dieses Benutzers. Für die Erstellung erforderlich.</dd>
<dt>--password</dt>
<dd>Kennwort, das für diesen Benutzer festzulegen ist. Wenn kein Kennwort angegeben wird, erhält der Benutzer eine E-Mail, um ein Kennwort zu generieren, das nach 24 Stunden abläuft. Geben Sie die Option '-p generate' an, um ein Kennwort für Sie zu generieren. Kennwörter müssen aus mindestens 8 Zeichen bestehen, darunter Groß- und Kleinbuchstaben, eine Ziffer und ein Sonderzeichen.</dd>
<dt>--from-user</dt>
<dd>Basisbenutzer, der als Vorlage für die Erstellung dieses Benutzers verwendet werden soll. Der Standardwert ist der Benutzer, der diesen Befehl ausführt. Die in "in --template" angegebenen Informationen setzen diese Vorlage außer Kraft.</dd>
<dt>--template</dt>
<dd>Eine JSON-Zeichenfolge, die https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ beschreibt.</dd>
<dt>--api-key</dt>
<dd>API-Schlüssel für diesen Benutzer erstellen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Setzt den Status eines Benutzers auf `CANCEL_PENDING`, wodurch das Konto sofort inaktiviert und später durch einen automatisierten internen Prozess aus dem Konto entfernt wird.
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

Benutzerdetails anzeigen:
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--keys</dt>
<dd>API-Schlüssel des Benutzers anzeigen.</dd>
<dt>--permissions</dt>
<dd>Berechtigungen anzeigen, die diesem Benutzer zugewiesen sind. Für Masterbenutzer werden keine Berechtigungen angezeigt.</dd>
<dt>--hardware</dt>
<dd>Hardware anzeigen, auf die dieser Benutzer Zugriff hat.</dd>
<dt>--virtual</dt>
<dd>Virtuelle Gäste anzeigen, auf die dieser Benutzer Zugriff hat.</dd>
<dt>--logins</dt>
<dd>Anmeldeverlauf dieses Benutzers während der letzten 30 Tage anzeigen.</dd>
<dt>--events</dt>
<dd>Auditprotokoll für diesen Benutzer anzeigen.</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

Benutzerdetails bearbeiten:
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--template</dt>
<dd>Eine JSON-Zeichenfolge, die https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ beschreibt.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

Bestimmte Benutzerberechtigungen aktivieren oder inaktivieren:
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--enable</dt>
<dd>Ausgewählte Berechtigungen aktivieren oder inaktivieren. Akzeptierte Eingaben sind `true` und `false`. Der Standardwert ist `true`.</dd>
<dt>--permission</dt>
<dd>Festzulegende Berechtigung `keyName`; mehrere Instanzen zulässig. Schlüsselwort ALL verwenden, um alle Berechtigungen auszuwählen.</dd>
<dt>--from-user</dt>
<dd>Berechtigungen festlegen, die mit den Berechtigungen dieses Benutzers übereinstimmen. Entsprechende Berechtigungen werden hinzugefügt bzw. entfernt.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

Benutzer auflisten:
```
ibmcloud sl user list [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--column</dt>
<dd>Anzuzeigende Spalte. [Optionen: id,username,email,displayName,status,hardwareCount,virtualGuestCount][default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

Benutzerberechtigungen anzeigen:
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

