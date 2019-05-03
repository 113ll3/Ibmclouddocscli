---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, security cli, ssh keys cli, ssl cli, ibmcloud sl security, certificate cli, ibmcloud sl, sshkey-add, manage security cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# SSH-Sicherheitsschlüssel und SSL-Zertifikate verwalten
{: #sl-manage-security-keys}

SSH-Schlüssel ermöglichen den Zugriff auf ein Gerät ohne Verwendung eines Kennworts der entsprechenden Clients für jeden öffentlichen Schlüssel, der auf dem Gerät bereitgestellt wird. Durch das Hinzufügen eines SSH-Schlüssels zu einer Einheit greift die Einheit, der der SSH-Schlüssel bereitgestellt wird, auf die Einheit für den entsprechenden Schlüssel ohne Verwendung eines Kennworts zu.

SSL-Zertifikate werden von Websites als Sicherheitsmaßnahme zum Schutz des Benutzers aktiviert. Sie werden in der Regel verwendet, wenn Sie vertrauliche Informationen an eine Website übertragen müssen.

Verwenden Sie die folgenden Befehle, um SSH-Schlüssel und Zertifikate der klassischen {{site.data.keyword.cloud}}-Infrastruktur zu verwalten.
{: shortdesc}

## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Neuen SSH-Schlüssel hinzufügen.
```
ibmcloud sl security sshkey-add LABEL [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>Die für diesen Schlüssel zu importierende Datei 'id_rsa.pub'.</dd>
<dt>-k, --key</dt>
<dd>Der tatsächliche SSH-Schlüssel.</dd>
<dt>--note</dt>
<dd>Zusätzliche Anmerkung, die dem Schlüssel zugeordnet wird.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
{: codeblock}

Dieser Befehl fügt einen SSH-Schlüssel aus der Datei ~/.ssh/id_rsa.pub mit der Anmerkung "mykey" hinzu.

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH-Schlüssel bearbeiten.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--label</dt>
<dd>Der neue Bezeichnung für den Schlüssel.</dd>
<dt>--note</dt>
<dd>Neue Anmerkungen für den Schlüssel.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security sshkey-edit 12345678 --label ibmcloud --note testing
```
{: codeblock}

Dieser Befehl aktualisiert den SSH-Schlüssel mit der ID `12345678` und legt die Bezeichnung auf `ibmcloud` und die Anmerkung auf `testing` fest.

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

SSH-Schlüssel für eigenes Konto auflisten.
```
ibmcloud sl security sshkey-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,label,fingerprint,notes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security sshkey-list --sortby label
```
{: codeblock}

Dieser Befehl listet alle SSH-Schlüssel für das aktuelle Konto auf und sortiert sie nach Bezeichnung.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Gibt einen SSH-Schlüssel am Bildschirm aus.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>Der öffentliche SSH-Schlüssel wird in diese Datei geschrieben.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
{: codeblock}

Dieser Befehl zeigt die ID, die Bezeichnung und die Anmerkungen des SSH-Schlüssels mit der ID 12345678 an und schreibt den öffentlichen Schlüssel in die Datei ~/mykey.pub.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Entfernt einen SSH-Schlüssel permanent.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
{: codeblock}

Dieser Befehl entfernt den SSH-Schlüssel mit der ID `12345678`, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

Details zum SSL-Zertifikat hinzufügen und hochladen.
```
ibmcloud sl security cert-add [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--crt</dt>
<dd>Zertifikatsdatei.</dd>
<dt>--csr</dt>
<dd>Zertifikatssignieranforderungsdatei.</dd>
<dt>--icc</dt>
<dd>Zwischenzertifikatsdatei.</dd>
<dt>--key</dt>
<dd>Datei mit privatem Schlüssel.</dd>
<dt>--notes</dt>
<dd>Zusätzliche Anmerkungen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
Dieser Befehl fügt die Zertifikatsdatei ~/ibm.com.cert und die Datei mit privatem Schlüssel ~/ibm.com.key für die Domäne ibm.com hinzu.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

SSL-Zertifikat bearbeiten.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--crt</dt>
<dd>Zertifikatsdatei.</dd>
<dt>--csr</dt>
<dd>Zertifikatssignieranforderungsdatei.</dd>
<dt>--icc</dt>
<dd>Zwischenzertifikatsdatei.</dd>
<dt>--key</dt>
<dd>Datei mit privatem Schlüssel.</dd>
<dt>--notes</dt>
<dd>Zusätzliche Anmerkungen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
Dieser Befehl bearbeitet das Zertifikat mit der ID 12345678 und aktualisiert den zugehörigen privaten Schlüssel mit der Datei: ~/ibm.com.key.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

SSL-Zertifikat und Schlüsseldateien herunterladen.
```
ibmcloud sl security cert-download IDENTIFIER
```


**Beispiele**:
```
ibmcloud sl security cert-download 12345678
```
Dieser Befehl lädt 4 Dateien in das aktuelle Verzeichnis für das Zertifikat mit der ID 12345678 herunter. Diese 4 Dateien sind die Zertifikatsdatei, die Zertifikatssignieranforderungsdatei, die Zwischenzertifikatsdatei und die Datei mit privatem Schlüssel.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

SSL-Zertifikate für eigenes Konto auflisten.
```
ibmcloud sl security cert-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--status</dt>
<dd>Zertifikate mit diesem Status anzeigen; Standard: 'all'; Optionen: all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,common_name,days_until_expire,notes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Dieser Befehl listet alle gültigen Zertifikate für das aktuelle Konto auf und sortiert sie nach Gültigkeitstagen.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

SSL-Zertifikat entfernen.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl security cert-remove 12345678
```
Dieser Befehl entfernt das Zertifikat mit der ID 12345678.
