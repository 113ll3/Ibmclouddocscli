---

copyright:

  years: 2016,2017

lastupdated: "2017-06-07"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.BluSoftlayer_notm}}-Befehle (bluemix sl)
{: #softlayer_cli}

Das {{site.data.keyword.BluSoftlayer}}-Plug-in wurde in die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle integriert. Sie müssen das Plug-in nicht mehr installieren. 

Verwenden Sie die {{site.data.keyword.BluSoftlayer_notm}}-Befehle in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI), um SoftLayer-Services zu konfigurieren und zu verwalten. 


Zu Beginn installieren Sie die IBM {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle. Details hierzu finden Sie unter
[Bluemix-Befehlszeilenschnittstelle ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}. 

Eine vollständige Liste der {{site.data.keyword.Bluemix_notm}}-Befehle finden Sie unter [{{site.data.keyword.Bluemix_notm}}-Befehle (bx)](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli).


## Allgemeine {{site.data.keyword.BluSoftlayer_notm}}-Befehle

Folgende Befehle werden unterstützt. Verwenden Sie den Befehl `bluemix sl`, um die Liste der verfügbaren Befehle anzuzeigen: 

<table summary="Allgemeine Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Allgemeine SoftLayer-Befehle</caption>
 <thead>
 <th colspan="6">Allgemeine SoftLayer-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## {{site.data.keyword.BluSoftlayer_notm}}-Blockspeicherbefehle

 <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 2. Softlayer - Blockspeicher</caption>
 <thead>
 <th colspan="6">Softlayer - Blockspeicher</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[bluemix sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[bluemix sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[bluemix sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[bluemix sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[bluemix sl block replica-order](/docs/cli/reference/softlayer/index.html#sl_block_replica_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_cancel)</td>
 <td>[bluemix sl block snapshot-create](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_create)</td>
 <td>[bluemix sl block snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_disable)</td>
 <td>[bluemix sl block snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_enable)</td>
 <td>[bluemix sl block snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_delete)</td>
 <td>[bluemix sl block snapshot-list](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_list)</td>
  </tr>
 <tr>
 <td>[bluemix sl block snapshot-order](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_order)</td>
  <td>[bluemix sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[bluemix sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[bluemix sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
  <td>[bluemix sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
  <td>[bluemix sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}}-dns-Befehle

<table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 3. Softlayer - dns-Befehle</caption>
 <thead>
 <th colspan="6">Softlayer - dns-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[bluemix sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
 <td>[bluemix sl dns record-edit](/docs/cli/reference/softlayer/index.html#sl_dns_record_edit)</td>
 <td>[bluemix sl dns record-list](/docs/cli/reference/softlayer/index.html#sl_dns_record_list)</td>
 <td>[bluemix sl dns record-remove](/docs/cli/reference/softlayer/index.html#sl_dns_record_remove)</td>
  <td>[bluemix sl dns zone-create](/docs/cli/reference/softlayer/index.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[bluemix sl dns zone-delete](/docs/cli/reference/softlayer/index.html#sl_dns_zone_delete)</td>
   <td>[bluemix sl dns zone-list](/docs/cli/reference/softlayer/index.html#sl_dns_zone_list)</td>
   <td>[bluemix sl dns zone-print](/docs/cli/reference/softlayer/index.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

<table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 4. Softlayer - globale IP-Adressen</caption>
 <thead>
 <th colspan="6">Softlayer - globale IP-Adressen</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[bluemix sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[bluemix sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[bluemix sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[bluemix sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}}-image-Befehle

 <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 5. Softlayer - image-Befehle</caption>
 <thead>
 <th colspan="6">Softlayer - image-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl image delete](/docs/cli/reference/softlayer/index.html#sl_image_delete)</td>
 <td>[bluemix sl image detail](/docs/cli/reference/softlayer/index.html#sl_image_detail)</td>
 <td>[bluemix sl image edit](/docs/cli/reference/softlayer/index.html#sl_image_edit)</td>
 <td>[bluemix sl image list](/docs/cli/reference/softlayer/index.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}}-ISCSI-Speicherbefehle (traditionell)

  <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 6. Softlayer - ISCSI-Speicherbefehle (traditionell)</caption>
 <thead>
 <th colspan="6">Softlayer - ISCSI-Speicherbefehle (traditionell)</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl iscsi cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_cancel)</td>
 <td>[bluemix sl iscsi create](/docs/cli/reference/softlayer/index.html#sl_iscsi_create)</td>
 <td>[bluemix sl iscsi detail](/docs/cli/reference/softlayer/index.html#sl_iscsi_detail)</td>
 <td>[bluemix sl iscsi list](/docs/cli/reference/softlayer/index.html#sl_iscsi_list)</td>
 <td>[bluemix sl iscsi snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_cancel)</td>
 <td>[bluemix sl iscsi snapshot-create](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create)</td>
 </tr>
 <tr>
 <td>[bluemix sl iscsi snapshot-create-space](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create-space)</td>
 <td>[bluemix sl iscsi snapshot-list](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_list)</td>
 <td>[bluemix sl iscsi snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_restore)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}}-security-Befehle

 <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 7. Softlayer - security-Befehle</caption>
 <thead>
 <th colspan="5">Softlayer - security-Befehle</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl security sshkey-add](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_add)</td>
  <td>[bluemix sl security sshkey-edit](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_edit)</td>
  <td>[bluemix sl security sshkey-list](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_list)</td>
  <td>[bluemix sl security sshkey-print](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_print)</td>   
  <td>[bluemix sl security sshkey-remove](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[bluemix sl security cert-add](/docs/cli/reference/softlayer/index.html#sl_security_cert_add)</td>
  <td>[bluemix sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[bluemix sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[bluemix sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[bluemix sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}}-subnet-Befehle
 
 <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 8. Softlayer - subnet-Befehle</caption>
 <thead>
 <th colspan="5">Softlayer - subnet-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl subnet cancel](/docs/cli/reference/softlayer/index.html#sl_subnet_cancel)</td>
 <td>[bluemix sl subnet create](/docs/cli/reference/softlayer/index.html#sl_subnet_create)</td>
 <td>[bluemix sl subnet detail](/docs/cli/reference/softlayer/index.html#sl_subnet_detail)</td>
 <td>[bluemix sl subnet list](/docs/cli/reference/softlayer/index.html#sl_subnet_list)</td>
 <td>[bluemix sl subnet lookup](/docs/cli/reference/softlayer/index.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}}-Virtual-Server-Befehle

 <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 9. Softlayer - Virtual-Server-Befehle</caption>
 <thead>
 <th colspan="6">Softlayer - Virtual-Server-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[bluemix sl vs capture](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
 <td>[bluemix sl vs create](/docs/cli/reference/softlayer/index.html#sl_vs_create)</td>
 <td>[bluemix sl vs options](/docs/cli/reference/softlayer/index.html#sl_vs_options)</td>
 <td>[bluemix sl vs credentials](/docs/cli/reference/softlayer/index.html#sl_vs_credentials)</td>
 <td>[bluemix sl vs detail](/docs/cli/reference/softlayer/index.html#sl_vs_detail)</td>
 </tr><tr>
 <td>[bluemix sl vs dns-sync](/docs/cli/reference/softlayer/index.html#sl_vs_dns_sync)</td>
 <td>[bluemix sl vs edit](/docs/cli/reference/softlayer/index.html#sl_vs_edit)</td>
 <td>[bluemix sl vs list](/docs/cli/reference/softlayer/index.html#sl_vs_list)</td>
 <td>[bluemix sl vs pause](/docs/cli/reference/softlayer/index.html#sl_vs_pause)</td>
 <td>[bluemix sl vs power-off](/docs/cli/reference/softlayer/index.html#sl_vs_power_off)</td>
 <td>[bluemix sl vs power-on](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
 </tr><tr>
 <td>[bluemix sl vs ready](/docs/cli/reference/softlayer/index.html#sl_vs_ready)</td>
 <td>[bluemix sl vs reboot](/docs/cli/reference/softlayer/index.html#sl_vs_reboot)</td>
 <td>[bluemix sl vs reload](/docs/cli/reference/softlayer/index.html#sl_vs_reload)</td>
 <td>[bluemix sl vs rescure](/docs/cli/reference/softlayer/index.html#sl_vs_rescure)</td>
 <td>[bluemix sl vs resume](/docs/cli/reference/softlayer/index.html#sl_vs_resume)</td>
 <td>[bluemix sl vs upgrade](/docs/cli/reference/softlayer/index.html#sl_vs_upgrade)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}}-VLAN-Befehle

  <table summary="Allgemeine SoftLayer-Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 10. Softlayer-VLAN-Befehle</caption>
 <thead>
 <th colspan="6">Softlayer-VLAN-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[bluemix sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[bluemix sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[bluemix sl vlan edit](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[bluemix sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[bluemix sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### Verwendung der Befehle
Zur Anzeige der Hilfeinformationen für die Befehle führen Sie folgenden Befehl aus: `bluemix sl [Befehl] -h`. 

### bluemix sl init
{: #sl_init}

Konfigurationseinstellungen initialisieren, die für die Verbindung zur SoftLayer-Umgebung verwendet werden. Die Konfiguration enthält den Benutzernamen, den API-Schlüssel oder das Kennwort, das Konto und den Endpunkt. 
```
bluemix sl init [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>Softlayer-API-Endpunkt-URL, Standardwert: https://api.softlayer.com/rest/v3.1</dd>
   <dt>-u,--sl-user</dt>
   <dd>Softlayer-Benutzername</dd>
   <dt>-p,--sl-password</dt>
   <dd>Softlayer-Kennwort oder API-Schlüssel</dd>
   <dt>-c,--account-id</dt>
   <dd>Softlayer-Konto-ID</dd>
   </dl>

Beispiel: Mit dem Softlayer-Benutzernamen und dem Kennwort/API-Schlüssel anmelden.
```
$ bluemix sl config
Konfiguration der Softlayer-Authentifizierung auswählen:
1. Mit dem Softlayer-Benutzernamen und dem Kennwort/API-Schlüssel anmelden
2. Bluemix-Single-Sign-On verwenden
Geben Sie eine Zahl > 1 ein.
Softlayer-API-Endpunkt-URL: [https://api.softlayer.com/rest/v3.1]>
Benutzername: []> wangjunl@cn.ibm.com
API-Schlüssel oder Kennwort: []> abcd

Softlayer-API-Endpunkt:    https://api.softlayer.com/rest/v3.1
Konto-ID:                  278444
Benutzer-ID:               wangjunl@cn.ibm.com
API-Schlüssel:             xxxxxxxxxx
```
Beispiel: Bluemix Single Sign-on für die Softlayer-Anmeldung verwenden.
```
$ bx login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API-Endpunkt: api.ng.bluemix.net
Authentifizieren...
OK

Als Ziel ausgewähltes Konto Wilmas Konto (65ce8074c6c62b5)

Zielorganisation wangjunl@cn.ibm.com

Zielbereich Wilma

API-Endpunkt:   https://api.ng.bluemix.net (API version: 2.54.0)
Region:         us-south
Benutzer:       wangjunl@cn.ibm.com
Konto:          Wilma's Account (65ce8074c6c62b5)
Organisation:   wangjunl@cn.ibm.com
Bereich:        Wilma

$ bx sl init
Konfiguration der Softlayer-Authentifizierung auswählen:
1. Mit dem Softlayer-Benutzernamen und dem Kennwort/API-Schlüssel anmelden
2. Bluemix Single Sign-on verwenden
Geben Sie eine Zahl > 2 ein.
Softlayer-API-Endpunkt-URL: [https://api.softlayer.com/mobile/v3.1]>
Für Konto festlegen: 278444
OK

Softlayer-API-Endpunkt:    https://api.softlayer.com/mobile/v3.1
Konto-ID:                  278444
Benutzer-ID:               12345678
IMS-Token:                 xxxxxxxxxx
```

### bluemix sl help
{: #sl_help}

Hilfeinformationen für alle Befehle für den Betrieb der SoftLayer-Umgebung anzeigen.
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

Hosts für den Zugriff auf einen bestimmten Datenträger autorisieren.
```
bluemix sl block access-authorize VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>Die ID eines Hardware-Servers, der autorisiert werden soll. </dd>
   <dt>--virtual-id</dt>
   <dd>Die ID eines virtuellen Servers, der autorisiert werden soll. </dd>
   <dt>--ip-address-id</dt>
   <dd>Die ID einer IP-Adresse, die autorisiert werden soll. </dd>
   <dt>--ip-address</dt>
   <dd>Eine IP-Adresse, die autorisiert werden soll. </dd>
    </dl>

**Beispiele**:
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
Dieser Befehl autorisiert den virtuellen Server mit der ID `87654321` für den Zugriff auf den Datenträger mit der ID `12345678`.

### bluemix sl block access-list
{: #sl_block_access_list}

ACLs auflisten.
```
bluemix sl block access-list VOLUME_ID [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` oder `password`. </dd>
   <dt>--columns</dt>
   <dd>  Spalten für die Anzeige, Optionen: `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` oder `password`. </dd>
</dl>

**Beispiele**:
```
bluemix sl block access-list 12345678 --sortby id
```
Dieser Befehl listet alle Hosts auf, die für den Zugriff auf den Datenträger mit der ID `12345678` autorisiert sind, und sortiert diese nach ID.

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

Autorisierung für Hosts widerrufen, die auf einen bestimmten Datenträger zugreifen. 
```
bluemix sl block access-revoke VOLUME_ID [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>Die ID eines Hardware-Servers, der autorisiert werden soll. </dd>
   <dt>--virtual-id</dt>
   <dd>Die ID eines virtuellen Servers, der autorisiert werden soll. </dd>
   <dt>--ip-address-id</dt>
   <dd>Die ID einer IP-Adresse, die autorisiert werden soll. </dd>
   <dt>--ip-address</dt>
   <dd>Eine IP-Adresse, die autorisiert werden soll. </dd>
    </dl>

**Beispiele**:
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
Dieser Befehl widerruft den Zugriff des virtuellen Servers mit der ID `87654321` auf den Datenträger mit der ID `12345678`.

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

Failback eines Blockdatenträgers von einem Replikat
```
 bluemix sl block replica-failback VOLUME_ID
```
**Beispiele**:
```
 bluemix sl block replica-failback 12345678
```
Dieser Befehl führt eine Failback-Operation für den Datenträger mit der ID `12345678` aus.

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

Failover eines Blockdatenträgers auf den angegebenen Replikatdatenträger
```
bluemix sl block replica-failover VOLUME_ID REPLIKAT-ID
```

**Beispiele**:
```
 bluemix sl block replica-failover 12345678 87654321
```
Dieser Befehl führt eine Failover-Operation für den Datenträger mit der ID `12345678` auf den Replikatdatenträger mit der ID `87654321` aus.

### bluemix sl block replica-order
{: #sl_block_replica_order}

Blockspeicher-Replikatdatenträger bestellen
```
bluemix sl block replica-order VOLUME_ID [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>Erforderlich. Für die Replikation zu verwendender Snapshotplan. Optionen: `HOURLY`,`DAILY` oder `WEEKLY`. </dd>
   <dt>-d, --datacenter</dt>
   <dd>Erforderlich. Kurzname für Rechenzentrum des Replikats. Beispiel: `dal09`.</dd>
   <dt>--tier</dt>
   <dd>Optional. Endurance-Speicherstufe (E/A-Operationen pro Sekunde pro GB) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: `0.25`, `2`, `4` oder `10`.</dd>
   <dt>--os-type</dt>
   <dd>Optional. Betriebssystemtyp des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: `HYPER_V`, `LINUX`, `VMWARE`, `WINDOWS_2008`, `WINDOWS_GPT`, `WINDOWS` oder `XEN`.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
    </dl>

**Beispiele**:
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Dieser Befehl bestellt ein Replikat für den Datenträger mit der ID `12345678`, der eine DAILY-Replikation durchführt, mit dem Ort 'dal09', der Stufe `4` und dem Betriebssystem `Linux`.

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Abbruch für vorhandenen Snapshotbereich für einen bestimmten Datenträger.
```
 bluemix sl block snapshot-cancel SNAPSHOT-ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Ein optionaler Grund für den Abbruch.</dd>
   <dt>--immediate</dt>
   <dd>Snapshotbereich sofort abbrechen statt am Rechnungsstichtag.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
	</dl>

**Beispiele**:
```
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Snapshot mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

Snapshot für einen bestimmten Datenträger erstellen.
```
bluemix sl block snapshot-create VOLUME_ID [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt> -n, --note</dt>
   <dd>Anmerkungen zum neuen Snapshot</dd>
	</dl>

**Beispiele**:
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
Dieser Befehl erstellt einen Snapshot für den Datenträger mit der ID `12345678` und mit Zusatzanmerkung `snapshotforbluemix`.

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

Snapshots für den angegebenen Plan für einen bestimmten Datenträger inaktivieren.
```
bluemix sl block snapshot-disable VOLUME_ID [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Erforderlich. Snapshotplan: `HOURLY`, `DAILY` oder `WEEKLY`.</dd>
	</dl>

**Beispiele**:
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
Dieser Befehl inaktiviert den täglichen Snapshot für den Datenträger mit der ID `12345678`.

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

Snapshots für einen bestimmten Datenträger zum angegebenen Plan bearbeiten.
```
bluemix sl block snapshot-enable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Erforderlich. Snapshotplan: `HOURLY`, `DAILY` oder `WEEKLY`.</dd>
   <dt>-c, --retention-count</dt>
   <dd>Erforderlich. Anzahl der beizubehaltenden Snapshots.</dd>
   <dt>-m, --minute</dt>
   <dd>Minute der Stunde, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 59.</dd>
   <dt>--hour</dt>
   <dd>Stunde des Tages, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 23.</dd>
   <dt>-d, --day-of-week</dt>
   <dd>Wochentag, an dem Snapshot erfasst werden sollen; Ganzzahl zwischen 0 und 6.
0 steht für Sonntag, 1 für Montag, 2 für Dienstag, 3 für Mittwoch, 4 für Donnerstag, 5 für Freitag, 6 für Samstag.</dd>
	</dl>

**Beispiele**:
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Dieser Befehl inaktiviert den Snapshot für den Datenträger mit der ID `12345678`. Der Snapshot wird wöchentlich jeden Sonntag um 2:00 ausgeführt und bis zu 5 Snapshots werden beibehalten.

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

Snapshot für einen bestimmten Datenträger löschen.
```
  bluemix sl block snapshot-delete SNAPSHOT-ID
```

**Beispiele**:
```
 bluemix sl block snapshot-delete 12345678
```
Dieser Befehl löscht Snapshots mit der ID `12345678`.

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

Blockspeicher-Snapshots auflisten
```
bluemix sl block snapshot-list VOLUME_ID [OPTIONEN]

```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: `id`, `name`, `created` und `size_bytes`.</dd>
	</dl>

**Beispiele**:
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
Dieser Befehl listet alle Snapshots des Datenträgers mit ID `12345678` und sortiert diese nach ID.

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

Snapshotbereich für einen Blockspeicherdatenträger bestellen.
```
bluemix sl block snapshot-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-s, --size</dt>
   <dd>Erforderlich. Die Größe des zu erstellenden Snapshotbereichs in GB.</dd>
   <dt>-t, --tier</dt>
   <dd>Optional. Endurance-Speicherstufe (E/A-Operationen pro Sekunde pro GB) des Blockdatenträgers, für den ein Bereich bestellt wurde. Optionen: 0.25,2,4,10</dd>
   <dt>-u, --upgrade</dt>
   <dd>Flag zum Anzeigen, dass die Bestellung ein Upgrade ist.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
	</dl>

**Beispiele**:
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
Dieser Befehl bestellt Snapshotbereich für den Datenträger mit der ID `12345678`, Größe 1000 GB, Tier-Ebene 4 E/A-Operationen pro Sekunde pro GB.

### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

Blockdatenträger mithilfe eines bestimmten Snapshots wiederherstellen
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT-ID
```

**Beispiele**:
```
 bluemix sl block snapshot-restore 12345678 87654321
```
Dieser Befehl stellt den Datenträger mit der ID `12345678` aus dem Snapshot mit der ID `87654321` wieder her.

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

Abbruch für vorhandenen Blockspeicherdatenträger
```
bluemix sl block volume-cancel VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Ein optionaler Grund für den Abbruch.</dd>
   <dt>--immediate</dt>
   <dd>Snapshotbereich sofort abbrechen statt am Rechnungsstichtag.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
	</dl>

**Beispiele**:
```
 bluemix sl block volume-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Datenträger mit der ID `12345678` sofort ab, ohne zu einer Bestätigung aufzufordern.

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

Details zu einem angegebenen Datenträger anzeigen
```
 bluemix sl block volume-detail VOLUME_ID
```

**Beispiele**:
```
 bluemix sl block volume-detail 12345678
```
Dieser Befehl führt Details zu dem Datenträger mit der ID `12345678` auf.

### bluemix sl block volume-list
{: #sl_block_volume_list}

Blockspeicher auflisten
```
 bluemix sl block volume-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-u, --username</dt>
   <dd>Nach Datenträger-Benutzernamen filtern.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nach Kurzname des Rechenzentrums filtern.</dd>
   <dt>-t, --storage-type</dt>
   <dd>Nach Typ des Speicherdatenträgers filtern. Optionen: `performance` und `endurance`.</dd>
   <dt>--order</dt>
   <dd>Nach ID der Bestellung filtern, mit der der Blockspeicher gekauft wurde.</dd>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
   <dt>--columns</dt>
   <dd>Spalten für die Anzeige, Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Dieser Befehl listet alle Endurance-Datenträger für das aktuelle Konto mit dem Ort 'dal09' auf und sortiert sie nach Kapazität.


### bluemix sl block volume-order
{: #sl_block_volume_order}

Blockspeicherdatenträger bestellen
```
 bluemix sl block volume-order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--storage-type</dt>
   <dd>Typ des Speicherdatenträgers [erforderlich]; Optionen: performance,endurance.</dd>
   <dt>--size</dt>
   <dd>Größe des Speicherdatenträgers in GB [erforderlich]</dd>
   <dt>--iops</dt>
   <dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfache von 100 [erforderlich für Speichertyp 'Performance']</dd>
   <dt>--tier</dt>
   <dd>Endurance-Speicherstufe (E/A-Operationen pro Sekunde pro GB) [erforderlich für Endurance-Speichertyp], Optionen: 0.25,2,4,10</dd>
   <dt>--os-type</dt>
   <dd>Betriebssystem [erforderlich]; Optionen: HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Kurzname des Rechenzentrums [erforderlich]</dd>
   <dt>--snapshot-size</dt>
   <dd>Optionaler Parameter für die Bestellung eines Snapshotbereichs zusammen mit Endurance-Blockspeicher; gibt die Größe des zu bestellenden Snapshotbereichs in GB an</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>


**Beispiele**:

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Dieser Befehl bestellt einen Leistungsdatenträger mit Größe 1000 GB, 4000 E/A-Operationen pro Sekunde, Betriebssystem LINUX, Ort 'dal09'.

```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
Dieser Befehl bestellt einen Endurance-Datenträger mit der Größe 500 GB, Tier-Ebene 4 E/A-Operationen pro Sekunde pro GB, Betriebssystem XEN, Ort 'dal09' und zusätzlicher Snapshotbereichsgröße 500 GB.


### bluemix sl block volume-options
{: #sl_block_volume_options}

Alle Optionen für die Bestellung eines Blockspeichers auflisten
```
 bluemix sl block volume-options
```

**Beispiele**:
```
 bluemix sl block volume-options
```
Dieser Befehl listet alle Optionen für die Erstellung eines Blockspeicherdatenträgers auf, einschließlich Speichertyp, Datenträgergröße, Betriebssystemtyp, E/A-Operationen pro Sekunde, Tier-Ebene, Rechenzentrum und Snapshotgröße.


### bluemix sl dns import
{: #sl_dns_import}

Zone auf Basis einer BIND-Zonendatei importieren.
```
bluemix sl dns-import [OPTIONEN] ZONEFILE
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--dry-run</dt>
   <dd>Datensätze nicht tatsächlich erstellen.</dd>
    </dl>

**Beispiele**:
```
 bluemix sl dns import ~/blumix.net.txt
```
Dieser Befehl importiert die Zone und ihre Ressourcendatensätze aus der Datei ` ~/blumix.net.txt `.

### bluemix sl dns record-add
{: #sl_dns_record_add}
Ressourcendatensatz hinzufügen. 

```
bluemix sl dns-record-add [OPTIONEN] ZONE RECORD TYPE DATA
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--ttl</dt>
   <dd>Nach TTL-Wert in Sekunden filtern, z. B. 86400 [Standardwert: 7200].</dd>
    </dl>

**Beispiele**:
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Dieser Befehl fügt einen A-Datensatz zur Zone bluemix.net hinzu, der Host ist `ftp`, Daten sind `127.0.0.1` und TTL ist 86400 Sekunden.

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

Ressourcendatensätze in einer Zone aktualisieren
```
   bluemix sl dns record-edit ZONE [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--by-record</dt>
   <dd>Nach Hostdatensatz bearbeiten, z. B. www.</dd>
   <dt>--by-id</dt>
   <dd>Einzelnen Datensatz nach ID bearbeiten.</dd>
   <dt>--data</dt>
   <dd>Daten aufzeichnen, wie z. B. eine IP-Adresse.</dd>
   <dt>--ttl</dt>
   <dd>Nach TTL-Wert in Sekunden filtern, z. B. 86400.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Dieser Befehl bearbeitet Datensätze unter der Zone `bluemix.net`, deren ID `12345678` ist, und legt ihre Daten auf `127.0.0.2` und TTL auf 3600 fest.

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
Dieser Befehl bearbeitet Datensätze unter der Zone `bluemix.net`, deren Hostname `kibana` ist, und legt ihre TTL alle auf 3600 fest.

### bluemix sl dns record-list
{: #sl_dns_record_list}

Alle Ressourcendatensätze in einer Zone auflisten

```
   bluemix sl dns record-list ZONE [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--data</dt>
   <dd>Nach Datensatzdaten filtern, z. B. IP-Adresse.</dd>
   <dt>--record</dt>
   <dd>Nach Hostdatensatz filtern, z. B. www.</dd>
   <dt>--ttl</dt>
   <dd>Nach TTL-Wert in Sekunden filtern, z. B. 86400.</dd>
   <dt>--type</dt>
   <dd>Nach Datensatztyp filtern, z. B. A oder CNAME</dd>
   </dl>

**Beispiele**:
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Dieser Befehl listet alle A-Datensätze unter der Zone `bluemix.net`, auf; der Host, nach dem gefiltert wird, ist `elasticsearch` und TTL ist 900 Sekunden.


### bluemix sl dns record-remove
{: #sl_dns_record_remove}

Ressourcendatensatz aus einer Zone entfernen
```
 bluemix sl dns record-remove RECORD_ID
```

**Beispiele**:
```   
 bluemix sl dns record-remove 12345678
```
Dieser Befehl entfernt den Ressourcendatensatz mit der ID `12345678`.

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

Zone erstellen.
```
 bluemix sl dns zone-create ZONE
```
**Beispiele**:
```
 bluemix sl dns zone-create bluemix.net
```
Dieser Befehl erstellt eine Zone mit dem Namen `bluemix.net`.

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

Zone löschen.
```
 bluemix sl dns zone-delete ZONE
```
**Beispiele**:
```
 bluemix sl dns zone-delete bluemix.net
```
Dieser Befehl löscht eine Zone mit dem Namen `bluemix.net`.

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

Alle Zonen für eigenes Konto auflisten
```
   bluemix sl dns zone-list
```
**Beispiele**:
```
   bluemix sl dns zone-list
```
Dieser Befehl listet alle Zonen unter einem aktuellen Konto auf.

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

Zone und Ressourcendatensätze in BIND-Format ausgeben
```
 bluemix sl dns zone-print ZONE
```

**Beispiele**:
```
 bluemix sl dns zone-print bluemix.net
```
Dieser Befehl gibt eine Zone mit dem Namen bluemix.net im BIND-Format aus.


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

Globale IP einem Zielrouter oder -gerät zuweisen.
```
 bluemix sl globalip assign [OPTIONEN] IDENTIFIER TARGET
```
**Beispiele**:
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
Dieser Befehl ordnet eine IP-Adresse mit der ID 12345678 zu einem Zielgerät mit der IP-Adresse 9.111.123.456 zu.


### bluemix sl globalip-create
{: #sl_globalip_create}

Globale IP erstellen.
```
bluemix sl globalip-create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--v6</dt>
   <dd>IPv6-IP-Adresse bestellen.</dd>
   <dt>--test</dt>
   <dd>Testbestellung.</dd>
    <dt>-f, --force</dt>
   <dd>Globale IP ohne Bestätigung erstellen.</dd>
    </dl>

**Beispiele**:
```
     bluemix sl globalip create --v6
```
Dieser Befehl erstellt eine IPv6-Adresse.

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

Abbruch für globale IP.
```
bluemix sl globalip-cancel [OPTIONEN] IDENTIFIER
```
<strong>Befehlsoptionen</strong>:
   <dl>
    <dt>-f, --force</dt>
   <dd>Globale IP ohne Bestätigung erstellen.</dd>
    </dl>

**Beispiele**:
```
 bluemix sl globalip cancel 12345678
```
Dieser Befehl bricht die IP-Adresse mit der ID `12345678` ab.

### bluemix sl globalip-list
{: #sl_globalip_list}

Alle globalen IPs auflisten.
```
bluemix sl globalip-list [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--v4</dt>
   <dd>Nur IPv4-IPs anzeigen.</dd>
   <dt>--v6</dt>
   <dd>Nur IPv6-IPs anzeigen.</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

Zuordnung einer globalen IP aus einem Zielrouter oder -gerät aufheben
```
 bluemix sl globalip unassign IDENTIFIER
```
**Beispiele**:
```
 bluemix sl globalip unassign 12345678
```
Dieser Befehl hebt die Zuordnung einer IP-Adresse mit der ID `12345678` zu einem Zielgerät auf.


### bluemix sl image delete
{: #sl_dns_image_delete}

Image löschen.
```
   bluemix sl image delete IDENTIFIER
```
**Beispiele**:
```
   bluemix sl image delete 12345678
```
Dieser Befehl löscht das Image mit der ID `12345678`.


### bluemix sl image detail
{: #sl_dns_image_detail}

Details zu einem Image abrufen.
```
 bluemix sl image detail IDENTIFIER
```
**Beispiele**:
```
 bluemix sl image detail 12345678
```
Dieser Befehl ruft Details zu dem Image mit der ID 12345678 ab.

### bluemix sl image edit
{: #sl_dns_image_edit}

Details zu einem Image bearbeiten
```
   bluemix sl image edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Name des Images.</dd>
   <dt>--note</dt>
   <dd>Zusätzliche Anmerkung für das Image.</dd>
   <dt>--tag</dt>
   <dd>Tags für das Image.</dd>
   </dl>


**Beispiele**:
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Dieser Befehl bearbeitet ein Image mit der ID `12345678` und legt den Namen auf `ubuntu16`, die Anmerkung `testing` und den Tag auf `staging` fest.


### bluemix sl image edit
{: #sl_dns_image_edit}

Details zu einem Image bearbeiten
```
   bluemix sl image edit [OPTIONEN] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Name des Images.</dd>
   <dt>--note</dt>
   <dd>Zusätzliche Anmerkung für das Image.</dd>
   <dt>--tag</dt>
   <dd>Tags für das Image.</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

Alle Images für eigenes Konto auflisten
```
   bluemix sl image list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Nach Imagename filtern.</dt>
   <dd>--public</dt>
   <dd>Nur öffentliche Images anzeigen.</dd>
   <dt>--private</dt>
   <dd>Nur private Images anzeigen.</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

Abbruch für vorhandenen iSCSI-Datenträger
```
   bluemix sl iscsi cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Ein optionaler Grund für den Abbruch.</dd>
   <dt>--immediate</dt>
   <dd>iSCSI-Datenträger sofort abbrechen statt am Rechnungsstichtag.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

iSCSI-Datenträger erstellen
```
   bluemix sl iscsi create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--size</dt>
   <dd>Größe des zu erstellenden iSCSI-Datenträgers (in GiB) [erforderlich]</dd>
   <dt>--datacenter</dt>
   <dd>Kurzname des Rechenzentrums [erforderlich]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

Details zu einem iSCSI-Datenträger abrufen
```
   bluemix sl iscsi detail IDENTIFIER [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--password</dt>
   <dd>Berechtigungsnachweise für Zugriff auf das iSCSI-Ziel anzeigen.</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

iSCSI-Datenträger auflisten
```
   bluemix sl iscsi list [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--order</dt>
   <dd>Die ID der Bestellung, mit der dieser iSCSI-Speicher gekauft wurde</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

Abbruch/Löschen des iSCSI-Snapshots
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPTIONEN]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

Snapshot eines iSCSI-Datenträgers erstellen
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--notes</dt>
   <dd>Eine optionale Anmerkung für den Snapshot.</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

Snapshotbereich für bestimmten iSCSI-Datenträger bestellen
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--capacity</dt>
   <dd>Größe des zu erstellenden Snapshotbereichs.</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

Snapshots eines iSCSI-Datenträgers auflisten
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPTIONEN]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

Neuen SSH-Schlüssel hinzufügen
```
 bluemix sl security sshkey-add LABEL [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --in-file</dt>
   <dd>Die für diesen Schlüssel zu importierende Datei 'id_rsa.pub'</dd>
   <dt>-k, --key</dt>
   <dd>Der tatsächliche SSH-Schlüssel</dd>
   <dt>--note</dt>
   <dd>Zusätzliche Anmerkung, die dem Schlüssel zugeordnet wird</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Dieser Befehl fügt einen SSH-Schlüssel aus der Datei ~/.ssh/id_rsa.pub mit der Anmerkung "mykey" hinzu.


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH-Schlüssel bearbeiten
```
 bluemix sl security sshkey-edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--label</dt>
   <dd>Der neue Bezeichnung für den Schlüssel</dd>
   <dt>--note</dt>
   <dd>Neue Anmerkungen für den Schlüssel</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Dieser Befehl aktualisiert den SSH-Schlüssel mit der ID 12345678 und legt die Bezeichnung auf "Bluemix" und die Anmerkung auf "testing" fest.

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

Alle SSH-Schlüssel für eigenes Konto auflisten
```
 bluemix sl security sshkey-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: `id`, `label`, `fingerprint`, `notes`.</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security sshkey-list --sortby label
```
  Dieser Befehl listet alle SSH-Schlüssel für das aktuelle Konto auf und sortiert sie nach Bezeichnung.

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

Gibt einen SSH-Schlüssel am Bildschirm aus.
```
 bluemix sl security sshkey-print IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --out-file</dt>
   <dd>Der öffentliche SSH-Schlüssel wird in diese Datei geschrieben.</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
 Dieser Befehl zeigt die ID, die Bezeichnung und die Anmerkungen des SSH-Schlüssels mit der ID 12345678 an und schreibt den öffentlichen Schlüssel in die Datei ~/mykey.pub.

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

Entfernt einen SSH-Schlüssel permanent.
```
 bluemix sl security sshkey-remove IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security sshkey-remove 12345678 -f
```
 Dieser Befehl entfernt den SSH-Schlüssel mit der ID 12345678, ohne zu einer Bestätigung aufzufordern.

### bluemix sl security cert-add
{: #sl_security_cert_add}

Details zum SSL-Zertifikat hinzufügen und hochladen
```
 bluemix sl security cert-add [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>Zertifikatsdatei</dd>
   <dt>--csr</dt>
   <dd>Zertifikatssignieranforderungsdatei</dd>
   <dt>--icc</dt>
   <dd>Zwischenzertifikatsdatei</dd>
   <dt>--key</dt>
   <dd>Datei mit privatem Schlüssel</dd>
   <dt>--notes</dt>
   <dd>Zusätzliche Anmerkungen</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
 Dieser Befehl fügt die Zertifikatsdatei ~/bluemix.net.cert und die Datei mit privatem Schlüssel ~/bluemix.net.key für die Domäne bluemix.net hinzu.

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

SSL-Zertifikat bearbeiten
```
 bluemix sl security cert-edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>Zertifikatsdatei</dd>
   <dt>--csr</dt>
   <dd>Zertifikatssignieranforderungsdatei</dd>
   <dt>--icc</dt>
   <dd>Zwischenzertifikatsdatei</dd>
   <dt>--key</dt>
   <dd>Datei mit privatem Schlüssel</dd>
   <dt>--notes</dt>
   <dd>Zusätzliche Anmerkungen</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
 Dieser Befehl bearbeitet das Zertifikat mit der ID 12345678 und aktualisiert den zugehörigen privaten Schlüssel mit der Datei ~/bluemix.net.key.

### bluemix sl security cert-download
{: #sl_security_cert_download}

SSL-Zertifikat und Schlüsseldateien herunterladen
```
 bluemix sl security cert-download IDENTIFIER
```

**Beispiele**:
```
 bluemix sl security cert-download 12345678
```
  Dieser Befehl lädt 4 Dateien in das aktuelle Verzeichnis für das Zertifikat mit der ID 12345678 herunter. Diese 4 Dateien sind die Zertifikatsdatei, die Zertifikatssignieranforderungsdatei, die Zwischenzertifikatsdatei und die Datei mit privatem Schlüssel.

### bluemix sl security cert-list
{: #sl_security_cert_list}

Alle SSL-Zertifikate für eigenes Konto auflisten
```
 bluemix sl security cert-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--status</dt>
   <dd>Zertifikate mit diesem Status anzeigen; Standardwert: 'all'; Optionen: `all`, `valid`, `expired`</dd>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: `id`, `common_name`, `days_until_expire`, `notes`</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
 Dieser Befehl listet alle gültigen Zertifikate für das aktuelle Konto auf und sortiert sie nach Gültigkeitstagen.

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

SSL-Zertifikat entfernen
```
 bluemix sl security cert-remove IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt> -f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>


**Beispiele**:
```
 bluemix sl security cert-remove 12345678
```
 Dieser Befehl entfernt das Zertifikat mit der ID 12345678.

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

Abbruch für Teilnetz.
```
 bluemix sl subnet cancel [OPTIONEN] IDENTIFIER
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
    </dl>


**Beispiele**:
```
 bluemix sl subnet cancel 12345678 -f
```
Dieser Befehl bricht das Teilnetz mit der ID 12345678 ab, ohne zu einer Bestätigung aufzufordern

### bluemix sl subnet create
{: #sl_subnet_create}

Neues Teilnetz zu Ihrem Konto hinzufügen.
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONEN]
```

Die gültigen Mengen sind vom Typ abhängig.

 * Type    - Valid Quantities (IPv4)
    ** public  - 4, 8, 16, 32
    ** private - 4, 8, 16, 32, 64
 * Type    - Valid Quantities (IPv6)
    ** public  - 64

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>IPv6-Adressen bestellen.</dd>
   <dt>--test</dt>
   <dd>Teilnetz nicht bestellen, nur ein Angebot anfordern.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>

**Beispiele**:
```
 bluemix sl subnet create public 16 567
```
Dieser Befehl erstellt ein öffentliches Teilnetz mit 16 IPv4-Adressen und ordnet es im VLAN mit der ID 567 an.




### bluemix sl subnet detail
{: #sl_subnet_detail}

Details zu einem Teilnetz abrufen.
```
   bluemix sl subnet detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Liste des virtuellen Server ausblenden.</dd>
   <dt>--no-hardware</dt>
   <dd>Hardwareliste ausblenden.</dd>
   </dl>


**Beispiele**:
```
 bluemix sl subnet detail 12345678
```
Dieser Befehl zeigt Detailinformationen zum Teilnetz mit der ID 12345678 an, einschließlich Informationen zu virtuellen Servern und Hardware-Servern.


### bluemix sl subnet-list
{: #sl_subnet_list}

Alle Teilnetze für eigenes Konto auflisten
```
   bluemix sl subnet list [OPTIONEN]
```


<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nach Kurzname des Rechenzentrums filtern.</dd>
   <dt>--identifier</dt>
   <dd>Nach Netz-ID filtern.</dd>
   <dt>-t, --subnet-type</dt>
   <dd>Nach Teilnetztyp filtern.</dd>
   <dt>--network-space</dt>
   <dd>Nach Netzbereich filtern.</dd>
   <dt>--v4, --ipv4</dt>
   <dd>Nur IPv4-Teilnetze anzeigen.</dd>
   <dt>--v6, --ipv6</dt>
   <dd>Nur IPv6-Teilnetze anzeigen.</dd>
   <dt>--order</dt>
   <dd>Nach ID der Bestellung filtern, mit der die Teilnetze gekauft wurden.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Dieser Befehl listet IPv4-Teilnetze für das aktuelle Konto auf, gefiltert nach Rechenzentrum; Ort 'dal09', Teilnetztyp PRIMARY und Netzbereich PUBLIC.



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

IP-Adresse suchen und ihr Teilnetz sowie Gerätedaten anzeigen
```
   bluemix sl subnet lookup IP_ADDRESS
```

**Beispiele**:
```
 bluemix sl subnet lookup 9.125.235.255
```
Dieser Befehl sucht nach dem IP-Adressdatensatz mit der Adresse 9.125.235.255 und zeigt sein Teilnetz und die Gerätedaten an.


### bluemix sl vs cancel
{: #sl_vs_cancel}

Abbruch für virtuelle Serverinstanz
```
   bluemix sl vs cancel IDENTIFIER [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>

**Beispiele**:
```
 bluemix sl vs cancel 12345678
```
Dieser Befehl bricht die virtuelle Serverinstanz mit der ID of 12345678 ab.


### bluemix sl vs capture
{: #sl_vs_capture}

Virtuelle Serverinstanz in einem Image erfassen 
```
 bluemix sl vs capture IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-n, --name</dt>
   <dd>Name des Images [erforderlich].</dd>
   <dt>--all</dt>
   <dd>Alle zum virtuellen Server gehörigen Platten erfassen.</dd>
   <dt>--note</dt>
   <dd>Anmerkung hinzufügen, die dem Image zugeordnet werden soll.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
Dieser Befehl erfasst die virtuelle Serverinstanz mit der ID 12345678 mit allen Platten in ein Image mit dem Namen "mybluemix" und der Anmerkung "testing".



### bluemix sl vs create
{: #sl_vs_create}

Virtuelle Serverinstanz erstellen
```
   bluemix sl vs create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-H, --hostname</dt>
   <dd>Hostteil des FQDN [erforderlich]</dd>
   <dt>-D, --domain</dt>
   <dd>Domänenteil des FQDN [erforderlich]</dd>
   <dt>-c, --cpu</dt>
   <dd>Anzahl der CPU-Cores [erforderlich]</dd>
   <dt>-m, --memory</dt>
   <dd>Speicher in Megabyte [erforderlich]</dd>
   <dt>-d, --datacenter</dt>
   <dd>Kurzname des Rechenzentrums [erforderlich]</dd>
   <dt>-o, --os</dt>
   <dd>Betriebssystem-Installationscode. Tipp: Sie können <OS>_LATEST angeben.</dd>
   <dt>--image</dt>
   <dd>Image-ID. Siehe [bluemix sl image list](#bluemix_sl_image_list). </dd>
   <dt>--billing</dt>
   <dd>Verrechnungssatz. Standardwert: hourly. Optionen: hourly, monthly</dd>
   <dt>--dedicated</dt>
   <dd>Dedizierten virtuellen Server erstellen (privater Knoten)</dd>
   <dt>--san</dt>
   <dd>SAN-Speicher anstelle der lokalen Festplatte verwenden</dd>
   <dt>--test</dt>
   <dd>Virtuellen Server nicht tatsächlich erstellen</dd>
   <dt>--export</dt>
   <dd>Optionen in eine Vorlagendatei exportieren</dd>
   <dt>-i, --postinstall</dt>
   <dd>Nachinstallationsscript herunterladen</dd>
   <dt>-k, --key</dt>
   <dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig)</dd>
   <dt>--disk</dt>
   <dd>Plattengrößen (Mehrfachvorkommen zulässig)</dd>
   <dt>--private</dt>
   <dd>Erzwingt, dass der virtuelle Server nur auf das private Netz zugreifen kann</dd>
   <dt>--like</dt>
   <dd>Konfiguration von einem vorhandenen virtuellen Server verwenden</dd>
   <dt>-n, --network</dt>
   <dd>Übertragungsgeschwindigkeit des Netzports in MB/s</dd>
   <dt>--tag</dt>
   <dd>Zur Instanz hinzuzufügende Tags (Mehrfachvorkommen zulässig)</dd>
   <dt>-t, --template</dt>
   <dd>Eine Vorlagendatei, mit der die Befehlszeilenoptionen auf Standardwerte zurückgesetzt werden</dd>
   <dt>-u, --userdata</dt>
   <dd>Benutzerdefinierte Metadaten-Zeichenfolge</dd>
   <dt>-F, --userfile</dt>
   <dd>Benutzerdaten aus Datei lesen</dd>
   <dt>--vlan-public</dt>
   <dd>Die ID des öffentlichen VLANs, in dem der virtuelle Server angeordnet werden soll</dd>
   <dt>--vlan-private</dt>
   <dd>Die ID des privaten VLANs, in dem der virtuelle Server angeordnet werden soll</dd>
   <dt>--wait</dt>
   <dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
	</dl>

**Beispiele**:
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Dieser Befehl bestellt eine virtuelle Serverinstanz mit dem Hostnamen myvsi, der Domäne bluemix.net, 4 CPU-Cores, 4096 M Speicher und Position im Rechenzentrum dal10, Betriebssystem ist UBUNTU 16 64-Bit, 2 Platten, die eine mit 100 G, die andere mit 1000 G und Position im öffentlichen VLAN mit der ID 413.
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
Dieser Befehl testet, ob die Bestellung mit den obigen Optionen gültig ist, bevor die Bestellung tatsächlich aufgegeben wird.
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

Dieser Befehl exportiert die obigen Optionen in die Datei myvsi.txt unter dem Benutzerausgangsverzeichnis für die spätere Verwendung.


### bluemix sl vs options
{: #sl_vs_options}

Optionen für die Erstellung einer virtuellen Serverinstanz auflisten
```
   bluemix sl vs options [OPTIONEN]
```

**Beispiele**:
```
 bluemix sl vs options
```
Dieser Befehl listet alle Optionen für die Erstellung einer virtuellen Serverinstanz auf, z. B. Rechenzentren, CPU, Speicher, Betriebssystem, Netzgeschwindigkeit usw.



### bluemix sl vs credentials
{: #sl_vs_credentials}

Berechtigungsnachweise für virtuelle Serverinstanz auflisten
```
   bluemix sl vs credentials IDENTIFIER [OPTIONEN]
```
**Beispiele**:
```
 bluemix sl vs credentials 12345678
```
Dieser Befehl listet alle Benutzernamen- und Kennwortpaare der virtuellen Serverinstanz mit der ID 12345678 auf.

### bluemix sl vs detail
{: #sl_vs_detail}

Details zu einer virtuellen Serverinstanz abrufen
```
   bluemix sl vs detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--passwords</dt>
   <dd>Kennwörter anzeigen.</dd>
   <dt>--price</dt>
   <dd>Zugeordnete Preise anzeigen.</dd>
   </dl>


**Beispiele**:
```
   bluemix sl vs details 12345678
```
Dieser Befehl listet Detailinformationen zur virtuellen Serverinstanz mit der ID 12345678 auf.


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

DNS-Datensätze für eine virtuelle Serverinstanz synchronisieren
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONEN]
```
Hinweis: Wenn Sie keine Argumente angeben, wird versucht, sowohl die A-
   als auch die PTR-Datensätze zu aktualisieren. Wenn nicht beide Datensätze aktualisiert werden sollen, können Sie die
   Argumente -a oder --ptr verwenden, um die aktualisierten Datensätze einzugrenzen.

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-a, --a-record</dt>
   <dd>A-Datensatz für Host synchronisieren</dd>
   <dt>--aaaa-record</dt>
   <dd>AAAA-Datensatz für Host synchronisieren</dd>
   <dt>--ptr</dt>
   <dd>PTR-Datensatz für Host synchronisieren</dd>
   <dt>--ttl</dt>
   <dd>Legt TTL für die A- und/oder PTR-Datensätze fest; Standardwert: 7200</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>


**Beispiele**:
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
Dieser Befehl synchronisiert den A-Datensatz (IPv4-Adresse) der virtuellen Serverinstanz mit der ID 12345678 mit dem DNS-Server und legt das TTL dieses A-Datensatzes auf 3600 fest.
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
Dieser Befehl synchronisiert sowohl den AAAA-Datensatz (IPv6-Adresse) als auch den PTR-Datensatz der virtuellen Serverinstanz mit der ID 12345678 mit dem DNS-Server.


### bluemix sl vs edit
{: #sl_vs_edit}

Details zu einer virtuellen Serverinstanz bearbeiten
```
   bluemix sl vs edit IDENTIFIER [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-D, --domain</dt>
   <dd>Domänenteil des FQDN</dd>
   <dt>-H, --hostname</dt>
   <dd>Hostteil des FQDN. Beispiel: Server</dd>
   <dt>--tag</dt>
   <dd>Tags zum Festlegen oder leere Zeichenfolge, um alle zu entfernen</dd>
   <dt>-u, --userdata</dt>
   <dd>Benutzerdefinierte Metadaten-Zeichenfolge</dd>
   <dt>-F, --userfile</dt>
   <dd>Benutzerdaten aus Datei lesen</dd>
   <dt>--public-speed</dt>
   <dd>Übertragungsgeschwindigkeit des öffentlichen Ports; Optionen: 0, 10, 100, 1000, 10000</dd>
   <dt>--private-speed</dt>
   <dd>Übertragungsgeschwindigkeit des privaten Ports; Optionen: 0, 10, 100, 1000, 10000</dd>
   </dl>

**Beispiele**:
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Dieser Befehl aktualisiert die virtuelle Serverinstanz mit der ID `12345678` und legt ihre Domäne auf `bluemix.net`, den Hostnamen auf `myapp`, den Tag auf `testcli`, und die Übertragungsgeschwindigkeit des öffentliches Netzports auf 1000 MB/s fest.



### bluemix sl vs list
{: #sl_vs_list}
Virtuelle Serverinstanzen für eigenes Konto auflisten
```
   bluemix sl vs list [OPTIONEN]
```


<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Anzahl der CPU-Cores</dd>
   <dt>-D, --domain</dt>
   <dd>Domänenteil des FQDN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Kurzname des Rechenzentrums</dd>
   <dt>-H, --hostname</dt>
   <dd>Hostteil des FQDN</dd>
   <dt>-m, --memory</dt>
   <dd>Speicher in Megabyte</dd>
   <dt>-n, --network</dt>
   <dd>Übertragungsgeschwindigkeit des Netzports in MB/s</dd>
   <dt>--hourly</dt>
   <dd>Nur stündliche Instanzen anzeigen</dd>
   <dt>--monthly</dt>
   <dd>Nur monatliche Instanzen anzeigen</dd>
   <dt>--tag</dt>
   <dd>Nach Tags filtern (Mehrfachvorkommen zulässig)</dd>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Standardwert: hostname</dd>
   <dt>--columns</dt>
   <dd>Spalten für die Anzeige, Optionen: guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. Standardwert: id, hostname, primary_ip, backend_ip, datacenter, action</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
Dieser Befehl listet alle virtuellen Serverinstanzen mit stündlicher Abrechnung für das aktuelle Konto auf, gefiltert nach Domäne gleich "bluemix.net", und sortiert sie nach Speicher.



### bluemix sl vs-pause
{: #sl_vs_pause}

Aktive virtuelle Serverinstanz anhalten
```
   bluemix sl vs pause IDENTIFIER [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs pause 12345678 -f
```
   Dieser Befehl hält die virtuelle Serverinstanz mit der ID 12345678 an, ohne zu einer Bestätigung aufzufordern.


### bluemix sl vs power-off
{: #sl_vs_power_off}

Aktive virtuelle Serverinstanz abschalten
```
   bluemix sl vs power-off IDENTIFIER [OPTIONEN]
```

**Beispiele**:
```
   bluemix sl vs power-off 12345678 --soft
```
Dieser Befehl führt eine normale Abschaltung der virtuellen Serverinstanz mit der ID 12345678 durch.

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Erzwungenen Systemabschluss durchführen</dd>
   <dt>--soft</dt>
   <dd>Normalen Systemabschluss durchführen</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

Virtuelle Serverinstanz einschalten
```
 bluemix sl vs power-on IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs power-on 12345678
```
Dieser Befehl schaltet die virtuelle Serverinstanz mit der ID 12345678 ein.


### bluemix sl vs ready
{: #sl_vs_ready}

Prüfen, ob eine virtuelle Serverinstanz betriebsbereit ist
```
 bluemix sl vs ready IDENTIFIER [OPTIONEN]
```

**Beispiele**:
```
 bluemix sl vs ready 12345678 --wait 30
```
Dieser Befehl prüft den Status der virtuellen Serverinstanz mit der ID 12345678 darauf hin, ob sie durchgehend betriebsbereit ist, und wartet bis zu 30 Sekunden.

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--wait</dt>
   <dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

Warmstart für aktive virtuelle Serverinstanz durchführen
```
 bluemix sl vs reboot IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Kaltstart durchführen</dd>
   <dt>--soft</dt>
   <dd>Warmstart durchführen</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs reboot 12345678 --hard
```
Dieser Befehl führt einen Kaltstart für die virtuelle Serverinstanz mit der ID 12345678 durch.


### bluemix sl vs reload
{: #sl_vs_reload}

Betriebssystem auf virtueller Serverinstanz neu laden
```
 bluemix sl vs reload IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>Nachinstallationsscript herunterladen</dd>
   <dt>--image</dt>
   <dd>Image-ID. Standardeinstellung ist die Verwendung des aktuellen Betriebssystems.
Siehe 'bluemix sl image list'. </dd>
   <dt>-k, --key</dt>
   <dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig)</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
   bluemix sl vs reload 12345678
```
Dieser Befehl lädt das aktuelle Betriebssystem für die virtuelle Serverinstanz mit der ID 12345678 neu.
```
 bluemix sl vs reload 12345678 --image 1234
```
Dieser Befehl lädt das Betriebssystem aus dem Image mit der ID 1234 für die virtuelle Serverinstanz mit der ID 12345678 neu.

### bluemix sl vs rescure
{: #sl_vs_rescure}

Warmstart für virtuelle Serverinstanz in ein Wiederherstellungsimage durchführen
```
 bluemix sl vs rescue IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
   </dl>
   
**Beispiele**:
```
 bluemix sl vs rescue 12345678
```
Dieser Befehl startet die virtuelle Serverinstanz mit der ID 12345678 neu in ein Wiederherstellungsimage.

### bluemix sl vs resume
{: #sl_vs_resume}

Angehaltene virtuelle Serverinstanz wieder aufnehmen
```
   bluemix sl vs resume IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs resume 12345678
```
Dieser Befehl nimmt die virtuelle Serverinstanz mit der ID 12345678 wieder auf.

### bluemix sl vs upgrade
{: #sl_vs_upgrade}

Upgrade für eine virtuelle Serverinstanz durchführen
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONEN]
```
Hinweis: SoftLayer startet die Instanz automatisch neu, nachdem eine Upgrade-Anforderung gestellt wurde. Die Instanz wird angehalten, bis die Upgrade-Transaktion abgeschlossen ist. Für Network ist jedoch kein Warmstart erforderlich.

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Anzahl der CPU-Cores</dd>
   <dt>--private</dt>
   <dd>CPU-Core soll sich auf einem dedizierten Host-Server befinden.</dd>
   <dt>-m, --memory</dt>
   <dd>Speicher in Megabyte.</dd>
   <dt>--network</dt>
   <dd>Übertragungsgeschwindigkeit des Netzports in MB/s.</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen.</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Dieser Befehl führt ein Upgrade für die virtuelle Serverinstanz mit der ID 12345678 durch und legt die Anzahl der CPU-Cores auf 8, den Speicher auf 8192 M und die Übertragungsgeschwindigkeit des Netzports auf 1000 MT/s fest.

### bluemix sl vlan create
{: #sl_vlan_create}

Neues VLAN erstellen
```
   bluemix sl vlan create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>Der Typ des VLANs, entweder öffentlich oder privat</dd>
   <dt>-r, --router</dt>
   <dd>Der Hostname des Routers</dd>
   <dt>-d, --datacenter</dt>
   <dd>Der Kurzname des Rechenzentrums</dd>
   <dt>-s, --size</dt>
   <dd>Die Größe der Teilnetze; Optionen: 8 (5 verwendbare IPs) oder 16 (13 verwendbare IPs) oder 32 (29 verwendbare IPs)</dd>
   <dt>-n, --name</dt>
   <dd>Der Name des VLANs</dd>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Dieser Befehl erstellt ein öffentliches VLAN in Rechenzentrum dal09 mit 16 IP-Adressen und dem Namen myvlan.
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
Dieser Befehl erstellt ein VLAN auf Router bcr01a.dal09 mit 16 IP-Adressen und dem Namen myvlan.


### bluemix sl vlan cancel
{: #sl_vlan_cancel}

Abbruch für VLAN
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Operation ohne Bestätigung erzwingen</dd>
    </dl>

**Beispiele**:
```
   bluemix sl vlan cancel 12345678 -f
```
Dieser Befehl bricht das VLAN mit der ID 12345678 ab, ohne zu einer Bestätigung aufzufordern.


### bluemix sl vlan detail
{: #sl_vlan_detail}

Details zu einem VLAN abrufen
```
   bluemix sl vlan detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Liste des virtuellen Server ausblenden.</dd>
   <dt>--no-hardware</dt>
   <dd>Hardwareliste ausblenden.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
Dieser Befehl zeigt Details zum VLAN mit der ID 12345678 an, ohne virtuelle Server oder Hardware-Server aufzulisten.

### bluemix sl vlan edit
{: #sl_vlan_edite}

Details zu einem VLAN bearbeiten
```
   bluemix sl vlan edit IDENTIFIER [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--n, --name</dt>
   <dd>Der Name des VLANs</dd>
    </dl>

**Beispiele**:
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
Dieser Befehl aktualisiert das VLAN mit der ID 12345678 und benennt es in "myvlan-rename" um.


### bluemix sl vlan list
{: #sl_vlan_list}

Alle VLANs für eigenes Konto auflisten
```
 bluemix sl vlan list [OPTIONEN]
```
<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Spalte, nach der sortiert werden soll. Optionen: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nach Kurzname des Rechenzentrums filtern.</dd>
   <dt>-n, --number</dt>
   <dd>Nach VLAN-Nummer filtern.</dd>
   <dt>--name</dt>
   <dd>Nach VLAN-Name filtern.</dd>
   <dt>--order</dt>
   <dd>Nach ID der Bestellung filtern, mit der das VLAN gekauft wurde.</dd>
   </dl>

**Beispiele**:
```
 bluemix sl vlan list -d dal09 --sortby number
```
Dieser Befehl listet alle VLANs für das aktuelle Konto, gefiltert nach Rechenzentrum gleich dal09, und sortiert sie nach VLAN-Nummer.



### bluemix sl vlan options
{: #sl_vlan_options}

Alle Optionen für die VLAN-Erstellung auflisten
```
   bluemix sl vlan options
```
**Beispiele**:
```
 bluemix sl vlan options
```
Dieser Befehl listet alle Optionen für die VLAN-Erstellung auf, z. B. VLAN-Typ, Rechenzentren, Teilnetzgröße, Router usw.
