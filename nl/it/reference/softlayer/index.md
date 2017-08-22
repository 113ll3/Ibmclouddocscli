---

copyright:

  years: 2016,2017

lastupdated: "2017-06-27"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Comandi {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)
{: #softlayer_cli}

Il plug-in {{site.data.keyword.BluSoftlayer}} è stato inglobato nella CLI {{site.data.keyword.Bluemix_notm}} e non devi più installarlo.

Utilizza i comandi {{site.data.keyword.BluSoftlayer_notm}} nella CLI (command line interface) {{site.data.keyword.Bluemix_notm}} per configurare e gestire i servizi SoftLayer.


Per iniziare, installa la CLI di IBM {{site.data.keyword.Bluemix_notm}}. Per i dettagli, vedi
[CLI Bluemix ![Icona link esterno](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}.

Per un elenco completo dei comandi {{site.data.keyword.Bluemix_notm}}, vedi: [Comandi {{site.data.keyword.Bluemix_notm}} (bx)](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)


## Comandi {{site.data.keyword.BluSoftlayer_notm}} generali

Sono supportati i seguenti comandi. Utilizza il comando `bluemix sl` per visualizzare l'elenco di comandi disponibili:

<table summary="Comandi generali riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Comandi Softlayer generali</caption>
 <thead>
 <th colspan="6">Comandi Softlayer generali</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## Comandi di archiviazione blocchi {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 2. Archiviazione blocchi Softlayer</caption>
 <thead>
 <th colspan="6">Archiviazione blocchi Softlayer</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} dns commands

<table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 3. Comandi dns Softlayer</caption>
 <thead>
 <th colspan="6">Comandi dns Softlayer</th>
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

<table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 4. Indirizzi IP globali Softlayer</caption>
 <thead>
 <th colspan="6">Indirizzi IP globali Softlayer</th>
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

## Comandi di immagine {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 5. Comandi di immagine Softlayer</caption>
 <thead>
 <th colspan="6">Comandi di immagine Softlayer</th>
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
 
## Comandi di archiviazione ISCSI legacy {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 6. Comandi di archiviazione ISCSI legacy Softlayer</caption>
 <thead>
 <th colspan="6">Comandi di archiviazione ISCSI legacy Softlayer</th>
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

## Comandi di sicurezza {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 7. Comandi di sicurezza Softlayer</caption>
 <thead>
 <th colspan="5">Comandi di sicurezza Softlayer</th>
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

## Comandi di sottorete {{site.data.keyword.BluSoftlayer_notm}}
 
 <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 8. Comandi di sottorete Softlayer</caption>
 <thead>
 <th colspan="5">Comandi di sottorete Softlayer</th>
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
 
## Comandi di server virtuale {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 9. Comandi di server virtuale Softlayer</caption>
 <thead>
 <th colspan="6">Comandi di server virtuale Softlayer</th>
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
 
## Comandi VLAN {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Comandi generali di Softlayer riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 10. Comandi VLAN Softlayer</caption>
 <thead>
 <th colspan="6">Comandi VLAN Softlayer</th>
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

### Utilizzo dei comandi
Per visualizzare le informazioni sulla guida per i comandi, esegui: `bluemix sl [command] -h`.

### bluemix sl init
{: #sl_init}

Inizializza le impostazioni di configurazione utilizzate per connettersi all'ambiente SoftLayer. La configurazione include nome utente, chiave API o password, account ed endpoint.
```
bluemix sl init [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>URL endpoint API Softlayer, il valore predefinito è: https://api.softlayer.com/rest/v3.1</dd>
   <dt>-u,--sl-user</dt>
   <dd>Nome utente Softlayer</dd>
   <dt>-p,--sl-password</dt>
   <dd>Password o chiave API Softlayer</dd>
   <dt>-c,--account-id</dt>
   <dd>ID account Softlayer</dd>
   </dl>

Ad esempio, accedi con nome utente e password o chiave API Softlayer
```
$ bluemix sl config
Scegli come configurare l'autenticazione Softlayer:
1. Accedi con nome utente e password/chiave API Softlayer
2. Utilizza SSO (Single-Sign-On) Bluemix
Immetti un numero>1
URL endpoint API Softlayer: [https://api.softlayer.com/rest/v3.1]>
Nome utente: []> wangjunl@cn.ibm.com
Chiave API o password: []> abcd

Endpoint API Softlayer:    https://api.softlayer.com/rest/v3.1
ID account:                278444
ID utente:                   wangjunl@cn.ibm.com
Chiave API:                   xxxxxxxxxx
```
Ad esempio, utilizza SSO (Single-Sign-On) Bluemix per accedere a Softlayer
```
$ bx login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
Endpoint API: api.ng.bluemix.net
Autenticazione in corso...
OK

Account di destinazione account di Wilma (65ce8074c6c62b5)

Organizzazione di destinazione: wangjunl@cn.ibm.com

Spazio di destinazione Wilma
                  
Endpoint API:   https://api.ng.bluemix.net (API version: 2.54.0)   
Regione:         us-south
Utente:           wangjunl@cn.ibm.com
Account:        Account di Wilma (65ce8074c6c62b5)   
Organizzazione:            wangjunl@cn.ibm.com
Spazio:          Wilma 

$ bx sl init
Scegli come configurare l'autenticazione Softlayer:
1. Accedi con nome utente e password/chiave API Softlayer
2. Utilizza SSO (Single-Sign-On) Bluemix
Immetti un numero> 2
URL endpoint API Softlayer: [https://api.softlayer.com/mobile/v3.1]> 
Impostazione dell'account su: 278444
OK
                              
Endpoint API Softlayer:    https://api.softlayer.com/mobile/v3.1
ID account:                278444
ID utente:                   12345678
Token IMS:                 xxxxxxxxxx
```

### bluemix sl help
{: #sl_help}

Visualizza le informazioni sulla guida di tutti i comandi per operare con l'ambiente Softlayer.
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

Autorizza gli host ad accedere a un determinato volume.
```
bluemix sl block access-authorize ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>L'ID di un server hardware da autorizzare.</dd>
   <dt>--virtual-id</dt>
   <dd>L'ID di un server virtuale da autorizzare.</dd>
   <dt>--ip-address-id</dt>
   <dd>L'ID di un indirizzo IP da autorizzare.</dd>
   <dt>--ip-address</dt>
   <dd>Un indirizzo IP da autorizzare.</dd>
    </dl>

**Esempi**:
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
Questo comando autorizza il server virtuale con ID `87654321` ad accedere al volume con ID `12345678`.

### bluemix sl block access-list
{: #sl_block_access_list}

Elenca ACL.
```
bluemix sl block access-list ID_VOLUME [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: `id`, `name`,  `type`, `private_ip_address`, `host_iqn`, `username` o `password`.</dd>
   <dt>--columns</dt>
   <dd>  Colonne da visualizzare, le opzioni sono:  `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` o `password`.</dd>
</dl>

**Esempi**:
```
bluemix sl block access-list 12345678 --sortby id
```
Questo comando elenca tutti gli host autorizzati ad accedere al volume con ID `12345678` e li ordina per ID.

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

Revoca l'autorizzazione agli host che accedono a un determinato volume.
```
 bluemix sl block access-revoke ID_VOLUME [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>L'ID di un server hardware da autorizzare.</dd>
   <dt>--virtual-id</dt>
   <dd>L'ID di un server virtuale da autorizzare.</dd>
   <dt>--ip-address-id</dt>
   <dd>L'ID di un indirizzo IP da autorizzare.</dd>
   <dt>--ip-address</dt>
   <dd>Un indirizzo IP da autorizzare.</dd>
    </dl>

**Esempi**:
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
Questo comando revoca l'accesso del server virtuale con ID `87654321` al volume con ID `12345678`.

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

Failback di un volume di blocchi dalla replica.
```
 bluemix sl block replica-failback ID_VOLUME
```
**Esempi**:
```
 bluemix sl block replica-failback 12345678
```
Questo comando esegue l'operazione di failback per il volume con ID `12345678`.

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

Failover di un volume di blocchi nel volume di replica fornito.
```
bluemix sl block replica-failover ID_VOLUME ID_REPLICA
```

**Esempi**:
```
 bluemix sl block replica-failover 12345678 87654321
```
Questo comando esegue l'operazione di failover per il volume con ID `12345678` nel volume di replica con ID `87654321`.

### bluemix sl block replica-order
{: #sl_block_replica_order}

Ordina un volume di replica dell'archiviazione blocchi.
```
 bluemix sl block replica-order ID_VOLUME [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>Obbligatorio. Pianificazione dell'istantanea da utilizzare per la replica. Le opzioni sono: `HOURLY`,`DAILY` o `WEEKLY`.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Obbligatorio. Nome breve del datacenter per la replica. Ad esempio, `dal09`.</dd>
   <dt>--tier</dt>
   <dd>Facoltativo. Livello archiviazione durata (IOPS per GB) del volume primario per cui è ordinata una replica. Le opzioni sono: `0.25`, `2`, `4` o `10`.</dd>
   <dt>--os-type</dt>
   <dd>Facoltativo. Tipo di sistema operativo del volume primario per cui è ordinata una replica. Le opzioni sono: `HYPER_V`, `LINUX`, `VMWARE`, `WINDOWS_2008`, `WINDOWS_GPT`, `WINDOWS` o `XEN`.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>

**Esempi**:
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Questo comando ordina una replica per il volume con ID `12345678`, che esegue la replica GIORNALIERA, è ubicato in dal09 con classe di livello `4` e tipo di sistema operativo `Linux`.

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Annulla lo spazio di istantanea esistente per un determinato volume.
```
 bluemix sl block snapshot-cancel ID_ISTANTANEA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Un motivo facoltativo per l'annullamento.</dd>
   <dt>--immediate</dt>
   <dd>Annulla lo spazio dell'istantanea immediatamente invece che a una ricorrenza di fatturazione.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
	</dl>

**Esempi**:
```
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
Questo comando annulla l'istantanea con ID 12345678 immediatamente e senza richiedere conferma.

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

Crea un'istantanea in un determinato volume.
```
 bluemix sl block snapshot-create ID_VOLUME [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt> -n, --note</dt>
   <dd>Note da impostare nella nuova istantanea</dd>
	</dl>

**Esempi**:
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
Questo comando crea un'istantanea per il volume con ID `12345678` e con una nota aggiunta come `snapshotforbluemix`.

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

Disabilita le istantanee nella pianificazione specificata per un determinato volume.
```
 bluemix sl block snapshot-disable ID_VOLUME [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Obbligatorio. La pianificazione dell'istantanea: `HOURLY`, `DAILY` o `WEEKLY`.</dd>
	</dl>

**Esempi**:
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
Questo comando disabilita l'istantanea giornaliera per il volume con ID `12345678`.

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

Abilita le istantanee per un determinato volume nella pianificazione specificata.
```
 bluemix sl block snapshot-enable ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Obbligatorio. La pianificazione dell'istantanea: `HOURLY`, `DAILY` o `WEEKLY`.</dd>
   <dt>-c, --retention-count</dt>
   <dd>Obbligatorio. Numero di istantanee da conservare.</dd>
   <dt>-m, --minute</dt>
   <dd>Minuto dell'ora in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 59.</dd>
   <dt>--hour</dt>
   <dd>Ora del giorno in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 23.</dd>
   <dt>-d, --day-of-week</dt>
   <dd>Giorno della settimana in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 6.
0 indica domenica, 1 indica lunedì, 2 indica martedì, 3 indica mercoledì, 4 indica giovedì, 5 indica venerdì, 6 indica sabato.</dd>
	</dl>

**Esempi**:
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Questo comando abilita l'istantanea per il volume con ID `12345678`. L'istantanea viene acquisita ogni domenica alle 2:00 e vengono conservate fino a 5 istantanee.

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

Elimina un'istantanea in un determinato volume.
```
  bluemix sl block snapshot-delete ID_ISTANTANEA
```

**Esempi**:
```
 bluemix sl block snapshot-delete 12345678
```
Questo comando elimina le istantanee con ID `12345678`.

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

Elenca le istantanee dell'archiviazione blocchi
```
 bluemix sl block snapshot-list ID_VOLUME [OPZIONI]

```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare. Le opzioni sono: `id`, `name`, `created` e `size_bytes`.</dd>
	</dl>

**Esempi**:
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
Questo comando elenca tutte le istantanee del volume con ID `12345678` e le ordina per ID.

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

Ordina lo spazio dell'istantanea per un volume dell'archiviazione blocchi.
```
 bluemix sl block snapshot-order ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-s, --size</dt>
   <dd>Obbligatorio. La dimensione dello spazio dell'istantanea da creare in GB.</dd>
   <dt>-t, --tier</dt>
   <dd>Facoltativo. Livello archiviazione durata (IOPS per GB) di un volume di blocchi per cui è ordinato lo spazio. Le opzioni sono: 0.25,2,4,10</dd>
   <dt>-u, --upgrade</dt>
   <dd>Contrassegno per indicare che l'ordine è un aggiornamento.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
	</dl>

**Esempi**:
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
Questo comando ordina lo spazio dell'istantanea per il volume con ID `12345678`, la dimensione è 1000 GB, la classe di livello è 4 IOPS per GB.


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

Ripristina il volume di blocchi utilizzando una determinata istantanea
```
 bluemix sl block snapshot-restore ID_VOLUME ID_ISTANTANEA
```

**Esempi**:
```
 bluemix sl block snapshot-restore 12345678 87654321
```
Questo comando ripristina il volume con ID `12345678` dall'istantanea con ID `87654321`.

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

Annulla un volume di archiviazione blocchi esistente
```
 bluemix sl block volume-cancel ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Un motivo facoltativo per l'annullamento.</dd>
   <dt>--immediate</dt>
   <dd>Annulla lo spazio dell'istantanea immediatamente invece che a una ricorrenza di fatturazione.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
	</dl>

**Esempi**:
```
 bluemix sl block volume-cancel 12345678 --immediate -f
```
Questo comando annulla il volume con ID `12345678` immediatamente e senza richiedere conferma.

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

Visualizza i dettagli di un volume specificato
```
 bluemix sl block volume-detail ID_VOLUME
```

**Esempi**:
```
 bluemix sl block volume-detail 12345678
```
Questo comando mostra i dettagli del volume con ID `12345678`.

### bluemix sl block volume-list
{: #sl_block_volume_list}

Elenca l'archiviazione blocchi.
```
 bluemix sl block volume-list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-u, --username</dt>
   <dd>Filtra per nome utente del volume.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filtra per nome breve del datacenter.</dd>
   <dt>-t, --storage-type</dt>
   <dd>Filtra per tipo di volume di archiviazione. Le opzioni sono: `performance` e `endurance`.</dd>
   <dt>--order</dt>
   <dd>Filtra per ID dell'ordine di acquisto dell'archiviazione blocchi.</dd>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
   <dt>--columns</dt>
   <dd>Colonne da visualizzare, le opzioni sono: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
   </dl>

**Esempi**:
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Questo comando elenca i volumi di durata sull'account corrente ubicati in dal09 e li ordina per capacità.


### bluemix sl block volume-order
{: #sl_block_volume_order}

Ordina un volume dell'archiviazione blocchi
```
   bluemix sl block volume-order [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--storage-type</dt>
   <dd>Tipo di volume di archiviazione [obbligatorio], le opzioni sono: performance,endurance.</dd>
   <dt>--size</dt>
   <dd>Dimensione del volume di archiviazione in GB [obbligatorio]</dd>
   <dt>--iops</dt>
   <dd>IOPs archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100 [obbligatorio per storage-type performance]</dd>
   <dt>--tier</dt>
   <dd>Livello archiviazione durata (IOP per GB) [obbligatorio per storage-type endurance], le opzioni sono: 0.25,2,4,10</dd>
   <dt>--os-type</dt>
   <dd>Sistema operativo [obbligatorio], le opzioni sono: HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nome breve del datacenter [obbligatorio]</dd>
   <dt>--snapshot-size</dt>
   <dd>Parametro facoltativo per l'ordinamento dello spazio dell'istantanea con l'archiviazione blocchi della durata; specifica la dimensione (in GB) dello spazio dell'istantanea da ordinare</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>


**Esempi**:

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Questo comando ordina un volume delle prestazioni con dimensione di 1000 GB, IOPS di 4000, tipo di SO LINUX, ubicato in dal09.

```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
Questo comando ordina un volume di durata con dimensione di 500GB, classe di livello di 4 IOPS per GB, tipo di SO XEN, ubicato in dal09 e la dimensione dello spazio dell'istantanea aggiuntivo è di 500 GB.


### bluemix sl block volume-options
{: #sl_block_volume_options}

Elenca tutte le opzioni per l'ordinamento di un archiviazione blocchi
```
 bluemix sl block volume-options
```

**Esempi**:
```
 bluemix sl block volume-options
```
Questo comando elenca tutte le opzioni per la creazione di un volume di archiviazione blocchi, inclusi il tipo di archiviazione, la dimensione del volume, il tipo di SO, l'IOPS, la classe di livello, il datacenter e la dimensione dell'istantanea.


### bluemix sl dns import
{: #sl_dns_import}

Importa una zona in base a un file di zona BIND.
```
bluemix sl dns-import [OPZIONI] ZONEFILE
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--dry-run</dt>
   <dd>Non creare al momento i record.</dd>
    </dl>

**Esempi**:
```
 bluemix sl dns import ~/blumix.net.txt
```
Questo comando importa la zona e i suoi record della risorsa dal file: `~/blumix.net.txt`.

### bluemix sl dns record-add
{: #sl_dns_record_add}
Aggiungi il record della risorsa.

```
bluemix sl dns-record-add [OPZIONI] ZONE RECORD TYPE DATA
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--ttl</dt>
   <dd>Valore TTL in secondi, ad esempio 86400  [valore predefinito: 7200].</dd>
    </dl>

**Esempi**:
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Questo comando aggiunge un record A alla zona: bluemix.net, l'host è `ftp`, i dati sono `127.0.0.1` e ttl è 86400 secondi.

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

Aggiorna i record della risorsa in una zona
```
   bluemix sl dns record-edit ZONE [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--by-record</dt>
   <dd>Modifica per record host, ad esempio www.</dd>
   <dt>--by-id</dt>
   <dd>Modifica un solo record dal suo ID</dd>
   <dt>--data</dt>
   <dd>Dati di record, ad esempio un indirizzo IP.</dd>
   <dt>--ttl</dt>
   <dd>Valore TTL in secondi, ad esempio: 86400.</dd>
   </dl>

**Esempi**:
```
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Questo comando modifica i record nella zona `bluemix.net` con `12345678` e imposta i suoi dati su `127.0.0.2` e ttl su 3600.

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
Questo comando modifica i record nella zona `bluemix.net` con il nome host `kibana` e imposta i propri ttl su 3600.


### bluemix sl dns record-list
{: #sl_dns_record_list}

Elenca tutti i record della risorsa in una zona

```
   bluemix sl dns record-list ZONE [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--data</dt>
   <dd>Filtra per dati di record, ad esempio un indirizzo IP.</dd>
   <dt>--record</dt>
   <dd>Filtra per record host, ad esempio www.</dd>
   <dt>--ttl</dt>
   <dd>Filtra per valore TTL in secondi, ad esempio 86400.</dd>
   <dt>--type</dt>
   <dd>Filtra per tipo di record, ad esempio A o CNAME</dd>
   </dl>

**Esempi**:
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Questo comando elenca tutti i record A nella zona `bluemix.net`, filtrati per l'host `elasticsearch` e con il ttl di 900 secondi.


### bluemix sl dns record-remove
{: #sl_dns_record_remove}

Rimuovi record della risorsa da una zona
```
 bluemix sl dns record-remove RECORD_ID
```

**Esempi**:
```   
 bluemix sl dns record-remove 12345678
```
Questo comando rimuove il record della risorsa con ID `12345678`.

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

Crea una zona.
```
 bluemix sl dns zone-create ZONE
```
**Esempi**:
```
 bluemix sl dns zone-create bluemix.net
```
Questo comando crea una zona denominata `bluemix.net`.

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

Elimina una zona.
```
 bluemix sl dns zone-delete ZONE
```
**Esempi**:
```
 bluemix sl dns zone-delete bluemix.net
```
Questo comando elimina una zona denominata `bluemix.net`.

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

Elenca tutte le zone nel tuo account
```
   bluemix sl dns zone-list
```
**Esempi**:
```
   bluemix sl dns zone-list
```
Questo comando elenca tutte le zone nell'account corrente.

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

Stampa la zona e i record della risorsa nel formato BIND
```
 bluemix sl dns zone-print ZONE
```

**Esempi**:
```
 bluemix sl dns zone-print bluemix.net
```
Questo comando stampa la zona denominata bluemix.net in formato BIND.


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

Assegna un IP globale a un dispositivo o a un router di destinazione.
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**Esempi**:
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
Questo comando assegna l'indirizzo IP con ID 12345678 a un dispositivo di destinazione il cui indirizzo IP è 9.111.123.456.


### bluemix sl globalip-create
{: #sl_globalip_create}

Crea un IP globale.
```
bluemix sl globalip-create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--v6</dt>
   <dd>Ordina un IP IPv6.</dd>
   <dt>--test</dt>
   <dd>Verifica l'ordine.</dd>
    <dt>-f, --force</dt>
   <dd>Crea un IP globale senza richiedere conferma.</dd>
    </dl>

**Esempi**:
```
     bluemix sl globalip create --v6
```
 Questo comando crea un indirizzo IP V6.

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

Annulla un IP globale.
```
bluemix sl globalip-cancel [OPZIONI] IDENTIFIER
```
<strong>Opzioni del comando</strong>:
   <dl>
    <dt>-f, --force</dt>
   <dd>Crea un IP globale senza richiedere conferma.</dd>
    </dl>

**Esempi**:
```
 bluemix sl globalip cancel 12345678
```
Questo comando annulla l'indirizzo IP con ID `12345678`.

### bluemix sl globalip-list
{: #sl_globalip_list}

Elenca tutti gli IP globali.
```
bluemix sl globalip-list [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--v4</dt>
   <dd>Visualizza solo gli IP IPv4.</dd>
   <dt>--v6</dt>
   <dd>Visualizza solo gli IP IPv6.</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

Annulla l'assegnazione di un IP globale da un router o un dispositivo di destinazione
```
 bluemix sl globalip unassign IDENTIFIER
```
**Esempi**:
```
 bluemix sl globalip unassign 12345678
```
Questo comando annulla l'assegnazione dell'indirizzo IP con ID `12345678` dal dispositivo di destinazione.


### bluemix sl image delete
{: #sl_dns_image_delete}

Elimina un'immagine.
```
   bluemix sl image delete IDENTIFIER
```
**Esempi**:
```
   bluemix sl image delete 12345678
```
Questo comando elimina l'immagine con ID `12345678`.


### bluemix sl image detail
{: #sl_dns_image_detail}

Ottieni i dettagli per un'immagine.
```
 bluemix sl image detail IDENTIFIER
```
**Esempi**:
```
 bluemix sl image detail 12345678
```
Questo comando ottiene i dettagli per l'immagine con ID 12345678.

### bluemix sl image edit
{: #sl_dns_image_edit}

Modifica i dettagli di un'immagine
```
   bluemix sl image edit IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Nome dell'immagine.</dd>
   <dt>--note</dt>
   <dd>Nota supplementare per l'immagine.</dd>
   <dt>--tag</dt>
   <dd>Tag per l'immagine</dd>
   </dl>


**Esempi**:
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Questo comando modifica l'immagine con ID `12345678` e imposta il suo nome su `ubuntu16`, la nota su `testing` e la tag su `staging`.


### bluemix sl image edit
{: #sl_dns_image_edit}

Modifica i dettagli di un'immagine
```
   bluemix sl image edit [OPZIONI] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Nome dell'immagine.</dd>
   <dt>--note</dt>
   <dd>Nota supplementare per l'immagine.</dd>
   <dt>--tag</dt>
   <dd>Tag per l'immagine</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

Elenca tutte le immagini nel tuo account
```
   bluemix sl image list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Filtra il nome dell'immagine.</dt>
   <dd>--public</dt>
   <dd>Visualizza solo le immagini pubbliche.</dd>
   <dt>--private</dt>
   <dd>Visualizza solo le immagini private.</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

Annulla un volume iSCSI esistente
```
   bluemix sl iscsi cancel IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>Un motivo facoltativo per l'annullamento.</dd>
   <dt>--immediate</dt>
   <dd>Annulla l'iSCSI immediatamente invece che a una ricorrenza di fatturazione.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

Crea un volume iSCSI
```
   bluemix sl iscsi create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--size</dt>
   <dd>Dimensione del volume iSCSI da creare (in gigabyte) [obbligatorio]</dd>
   <dt>--datacenter</dt>
   <dd>Nome breve del datacenter [obbligatorio]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

Ottieni i dettagli per un volume iSCSI
```
   bluemix sl iscsi detail IDENTIFIER [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--password</dt>
   <dd>Mostra le credenziali per accedere alla destinazione iSCSI.</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

Elenca i volumi iSCSI
```
 bluemix sl iscsi list [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--order</dt>
   <dd>L'ID dell'ordine che ha acquistato questa archiviazione iscsi</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

Annulla/Elimina l'istantanea iSCSI
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPZIONI]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

Crea un'istantanea di un volume iSCSI
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--notes</dt>
   <dd>Una nota facoltativa per l'istantanea.</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

Ordina lo spazio dell'istantanea per il volume iSCSI fornito
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--capacity</dt>
   <dd>Dimensione dello spazio dell'istantanea da creare.</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

Elenca le istantanee di un volume iSCSI
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPZIONI]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

Aggiungi una nuova chiave SSH
```
 bluemix sl security sshkey-add LABEL [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --in-file</dt>
   <dd>Il file id_rsa.pub da importare per questa chiave</dd>
   <dt>-k, --key</dt>
   <dd>La chiave SSH corrente</dd>
   <dt>--note</dt>
   <dd>Nota aggiuntiva che verrà associata alla chiave</dd>
   </dl>


**Esempi**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Questo comando aggiunge una chiave SSH dal file: ~/.ssh/id_rsa.pub con una nota "mykey".


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

Modifica una chiave SSH
```
 bluemix sl security sshkey-edit IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--label</dt>
   <dd>La nuova etichetta per la chiave</dd>
   <dt>--note</dt>
   <dd>Nuove note per la chiave</dd>
   </dl>


**Esempi**:
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Questo comando aggiorna la chiave SSH con ID 12345678 e imposta l'etichetta su "Bluemix" e la nota su "testing".

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

Elenca le chiavi SSH nel tuo account
```
 bluemix sl security sshkey-list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: `id`, `label`, `fingerprint`, `notes`.</dd>
   </dl>


**Esempi**:
```
 bluemix sl security sshkey-list --sortby label
```
 Questo comando elenca tutte le chiavi SSH nell'account corrente e le ordina per etichetta.

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

Stampa una chiave SSH sulla schermata
```
 bluemix sl security sshkey-print IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --out-file</dt>
   <dd>La chiave SSH pubblica verrà scritta in questo file.</dd>
   </dl>


**Esempi**:
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
 Questo comando mostra l'ID, l'etichetta e le note della chiave SSH con ID 12345678 e scrive la chiave pubblica nel file: ~/mykey.pub.

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

Rimuove permanentemente una chiave SSH
```
 bluemix sl security sshkey-remove IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>


**Esempi**:
```
 bluemix sl security sshkey-remove 12345678 -f
```
 Questo comando rimuove la chiave SSH con ID 12345678 senza richiedere conferma.

### bluemix sl security cert-add
{: #sl_security_cert_add}

Aggiungi e carica i dettagli del certificato SSL
```
 bluemix sl security cert-add [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>File del certificato</dd>
   <dt>--csr</dt>
   <dd>File richiesta firma certificato (CSR)</dd>
   <dt>--icc</dt>
   <dd>File certificato intermedio</dd>
   <dt>--key</dt>
   <dd>File chiave privata</dd>
   <dt>--notes</dt>
   <dd>Note supplementari</dd>
   </dl>


**Esempi**:
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
 Questo comando aggiunge il file del certificato: ~/bluemix.net.cert e il file della chiave privata  ~/bluemix.net.key per il dominio bluemix.net.

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

Modifica il certificato SSL
```
 bluemix sl security cert-edit IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>File del certificato</dd>
   <dt>--csr</dt>
   <dd>File richiesta firma certificato (CSR)</dd>
   <dt>--icc</dt>
   <dd>File certificato intermedio</dd>
   <dt>--key</dt>
   <dd>File chiave privata</dd>
   <dt>--notes</dt>
   <dd>Note supplementari</dd>
   </dl>


**Esempi**:
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
 Questo comando modifica il certificato con ID 12345678 e aggiorna la sua chiave privata con il file: ~/bluemix.net.key.

### bluemix sl security cert-download
{: #sl_security_cert_download}

Scarica i file di chiave e certificato SSL
```
 bluemix sl security cert-download IDENTIFIER
```

**Esempi**:
```
 bluemix sl security cert-download 12345678
```
  Questo comando scarica 4 file nella directory corrente per il certificato con ID 12345678. I 4 file sono: il file del certificato, il file della richiesta di firma del certificato, il file del certificato intermedio e il file della chiave privata.

### bluemix sl security cert-list
{: #sl_security_cert_list}

Elenca i certificati SSL nel tuo account
```
 bluemix sl security cert-list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--status</dt>
   <dd>Mostra certificati con questo stato, il valore predefinito è: all, le opzioni sono: `all`, `valid`, `expired`</dd>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: `id`, `common_name`, `days_until_expire`, `notes`</dd>
   </dl>


**Esempi**:
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
 Questo comando elenca tutti i certificati validi nell'account corrente e li ordina per giorni di validità.

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

Rimuovi il certificato SSL
```
 bluemix sl security cert-remove IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt> -f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>


**Esempi**:
```
 bluemix sl security cert-remove 12345678
```
 Questo comando rimuove il certificato con ID 12345678.

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

Annulla una sottorete.
```
 bluemix sl subnet cancel [OPZIONI] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>


**Esempi**:
```
 bluemix sl subnet cancel 12345678 -f
```
Questo comando annulla la sottorete con ID 12345678 senza richiedere conferma.

### bluemix sl subnet create
{: #sl_subnet_create}

Aggiungi una nuova sottorete al tuo account.
```
   bluemix sl subnet create QUANTITÀ RETE ID_VLAN [OPZIONI]
```

Le quantità valide variano in base al tipo.

 * Tipo    - Quantità valide (IPv4)
    ** pubblica  - 4, 8, 16, 32
    ** privata - 4, 8, 16, 32, 64
 * Tipo    - Quantità valide (IPv6)
    ** pubblica  - 64

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>Ordina indirizzi IPv6.</dd>
   <dt>--test</dt>
   <dd>Non ordinare la sottorete; ottieni solo un preventivo.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>

**Esempi**:
```
 bluemix sl subnet create public 16 567
```
Questo comando crea una sottorete pubblica con 16 indirizzi IP v4 e la posiziona nella vlan con ID 567.



### bluemix sl subnet detail
{: #sl_subnet_detail}

Ottieni i dettagli di una sottorete.
```
   bluemix sl subnet detail IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Nascondi elenco server virtuali.</dd>
   <dt>--no-hardware</dt>
   <dd>Nascondi elenco hardware.</dd>
   </dl>


**Esempi**:
```
 bluemix sl subnet detail 12345678
```
Questo comando mostra informazioni dettagliate sulla sottorete con ID 12345678, incluse le informazioni sui server virtuali e i server hardware.


### bluemix sl subnet-list
{: #sl_subnet_list}

Elenca tutte le sottoreti nel tuo account
```
   bluemix sl subnet list [OPZIONI]
```


<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare. Le opzioni sono: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filtra per nome breve del datacenter.</dd>
   <dt>--identifier</dt>
   <dd>Filtra per identificativo di rete.</dd>
   <dt>-t, --subnet-type</dt>
   <dd>Filtra per tipo di sottorete.</dd>
   <dt>--network-space</dt>
   <dd>Filtra per spazio di rete.</dd>
   <dt>--v4, --ipv4</dt>
   <dd>Visualizza solo le sottoreti IPv4.</dd>
   <dt>--v6, --ipv6</dt>
   <dd>Visualizza solo le sottoreti IPv6.</dd>
   <dt>--order</dt>
   <dd>Filtra per ID dell'ordine di acquisto delle sottoreti</dd>
   </dl>

**Esempi**:
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Questo comando elenca le sottoreti IP V4 nell'account corrente eseguendo il filtro per il datacenter dal09, il tipo di sottorete è PRIMARY e lo spazio di rete è PUBLIC.



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

Trova un indirizzo IP e visualizzane le informazioni su sottorete e dispositivo
```
   bluemix sl subnet lookup IP_ADDRESS
```

**Esempi**:
```
 bluemix sl subnet lookup 9.125.235.255
```
Questo comando trova il record dell'indirizzo IP con indirizzo 9.125.235.255 e ne visualizza le informazioni su sottorete e dispositivo.


### bluemix sl vs cancel
{: #sl_vs_cancel}

Annulla l'istanza del server virtuale
```
   bluemix sl vs cancel IDENTIFIER [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>

**Esempi**:
```
 bluemix sl vs cancel 12345678
```
Questo comando annulla l'istanza del server virtuale con ID 12345678.


### bluemix sl vs capture
{: #sl_vs_capture}

Acquisisci l'istanza del server virtuale in un'immagine
```
 bluemix sl vs capture IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-n, --name</dt>
   <dd>Nome dell'immagine [obbligatorio].</dd>
   <dt>--all</dt>
   <dd>Acquisisci tutti i dischi appartenenti al server virtuale.</dd>
   <dt>--note</dt>
   <dd>Aggiungi una nota da associare all'immagine.</dd>
   </dl>

**Esempi**:
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
Questo comando acquisisce l'istanza del server virtuale con ID 12345678 con tutti i dischi in un'immagine denominata "mybluemix" con la nota "testing".



### bluemix sl vs create
{: #sl_vs_create}

Crea istanza del server virtuale
```
   bluemix sl vs create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-H, --hostname</dt>
   <dd>Porzione host del FQDN [obbligatorio]</dd>
   <dt>-D, --domain</dt>
   <dd>Porzione dominio del FQDN [obbligatorio]</dd>
   <dt>-c, --cpu</dt>
   <dd>Numero di core CPU [obbligatorio]</dd>
   <dt>-m, --memory</dt>
   <dd>Memoria in megabyte [obbligatorio]</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nome breve del datacenter [obbligatorio]</dd>
   <dt>-o, --os</dt>
   <dd>Codice di installazione SO. Suggerimento: puoi specificare <OS>_LATEST</dd>
   <dt>--image</dt>
   <dd>ID immagine. Vedi: [bluemix sl image list](#bluemix_sl_image_list) per i riferimenti</dd>
   <dt>--billing</dt>
   <dd>Frequenza di fatturazione. Il valore predefinito è: hourly. Le opzioni sono: hourly, monthly</dd>
   <dt>--dedicated</dt>
   <dd>Crea un server virtuale dedicato (nodo privato)</dd>
   <dt>--san</dt>
   <dd>Utilizza l'archiviazione SAN invece del disco locale</dd>
   <dt>--test</dt>
   <dd>Non creare al momento il server virtuale</dd>
   <dt>--export</dt>
   <dd>Esporta le opzioni in un file modello</dd>
   <dt>-i, --postinstall</dt>
   <dd>Script di post installazione da scaricare</dd>
   <dt>-k, --key</dt>
   <dd>Gli ID delle chiavi SSH da aggiungere all'utente root (più ricorrenze consentite)</dd>
   <dt>--disk</dt>
   <dd>Dimensioni disco (più ricorrenze consentite)</dd>
   <dt>--private</dt>
   <dd>Forza il server virtuale ad avere accesso solo alla rete privata</dd>
   <dt>--like</dt>
   <dd>Utilizza la configurazione da un server virtuale esistente</dd>
   <dt>-n, --network</dt>
   <dd>Velocità della porta di rete in Mbps</dd>
   <dt>--tag</dt>
   <dd>Tag da aggiungere all'istanza (più ricorrenze consentite)</dd>
   <dt>-t, --template</dt>
   <dd>Un file modello che rende predefinite le opzioni della riga di comando</dd>
   <dt>-u, --userdata</dt>
   <dd>Stringa di metadati definita dall'utente</dd>
   <dt>-F, --userfile</dt>
   <dd>Leggi dati utente dal file</dd>
   <dt>--vlan-public</dt>
   <dd>L'ID della VLAN pubblica in cui desideri posizionare il server virtuale</dd>
   <dt>--vlan-private</dt>
   <dd>L'ID della VLAN privata in cui desideri posizionare il server virtuale</dd>
   <dt>--wait</dt>
   <dd>Attendi finché il server virtuale non ha terminato il provisioning fino a X secondi prima di ritornare</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
	</dl>

**Esempi**:
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Questo comando ordina un'istanza del server virtuale con nome host myvsi, dominio bluemix.net, 4 core cpu, 4096M di memoria, ubicata nel datacenter: dal10,
  con sistema operativo UBUNTU 16 a 64 bit, 2 dischi, uno da 100G, l'altro da 1000G e ubicata nella vlan pubblica con ID 413.
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
Questo comando controlla se l'ordine è valido con le opzioni precedenti prima che sia effettivamente effettuato.
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

Questo comando esporta le opzioni precedenti in un file: myvsi.txt nella directory home dell'utente per un utilizzo successivo.


### bluemix sl vs options
{: #sl_vs_options}

Elenca le opzioni per la creazione dell'istanza del server virtuale
```
   bluemix sl vs options [OPZIONI]
```

**Esempi**:
```
 bluemix sl vs options
```
Questo comando elenca tutte le opzioni per la creazione di un'istanza del server virtuale, ad es. datacenter, cpu, memoria, so, disco, velocità di rete, ecc.



### bluemix sl vs credentials
{: #sl_vs_credentials}

Elenca le credenziali dell'istanza del server virtuale
```
   bluemix sl vs credentials IDENTIFIER [OPZIONI]
```
**Esempi**:
```
 bluemix sl vs credentials 12345678
```
Questo comando elenca tutte le coppie di nome utente e password dell'istanza del server virtuale con ID 12345678.

### bluemix sl vs detail
{: #sl_vs_detail}

Ottieni i dettagli per un'istanza del server virtuale
```
   bluemix sl vs detail IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--passwords</dt>
   <dd>Mostra le password.</dd>
   <dt>--price</dt>
   <dd>Mostra i prezzi associati.</dd>
   </dl>


**Esempi**:
```
   bluemix sl vs details 12345678
```
Questo comando elenca informazioni dettagliate sull'istanza del server virtuale con ID 12345678.


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

Sincronizza i record DNS per un'istanza del server virtuale
```
   bluemix sl vs dns-sync IDENTIFIER [OPZIONI]
```
Nota: se non specifichi alcun argomento, tenterà di aggiornare sia il record A
   che PTR. Se non vuoi aggiornare entrambi i record, puoi utilizzare gli argomenti
   -a o --ptr per limitare i record aggiornati.

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-a, --a-record</dt>
   <dd>Sincronizza il record A per l'host</dd>
   <dt>--aaaa-record</dt>
   <dd>Sincronizza il record AAAA per l'host</dd>
   <dt>--ptr</dt>
   <dd>Sincronizza il record PTR per l'host</dd>
   <dt>--ttl</dt>
   <dd>Imposta il TTL per i record A e/o PTR, il valore predefinito è: 7200</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>


**Esempi**:
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
Questo comando sincronizza il record A (indirizzo IP V4) dell'istanza del server virtuale con ID 12345678 con il server DNS e imposta il ttl di questo record A su 3600.
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
Questo comando sincronizza sia il record AAAA (indirizzo IP V6) che il record PTR dell'istanza del server virtuale con ID 12345678 con il server DNS.


### bluemix sl vs edit
{: #sl_vs_edit}

Modifica i dettagli di un'istanza del server virtuale
```
   bluemix sl vs edit IDENTIFIER [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-D, --domain</dt>
   <dd>Porzione dominio del FQDN</dd>
   <dt>-H, --hostname</dt>
   <dd>Porzione host del FQDN. Ad esempio: server</dd>
   <dt>--tag</dt>
   <dd>Tag da impostare o stringa vuota per rimuovere tutto</dd>
   <dt>-u, --userdata</dt>
   <dd>Stringa di metadati definita dall'utente</dd>
   <dt>-F, --userfile</dt>
   <dd>Leggi dati utente dal file</dd>
   <dt>--public-speed</dt>
   <dd>Velocità porta pubblica, le opzioni sono: 0, 10, 100, 1000, 10000</dd>
   <dt>--private-speed</dt>
   <dd>Velocità porta privata, le opzioni sono: 0, 10, 100, 1000, 10000</dd>
   </dl>

**Esempi**:
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Questo comando aggiorna l'istanza del server virtuale con ID `12345678` e ne imposta il dominio su `bluemix.net`, il nome host su `myapp`, la tag su `testcli` e la velocità della porta di rete pubblica su 1000 Mbps.



### bluemix sl vs list
{: #sl_vs_list}
Elenca le istanze del server virtuale nel tuo account
```
   bluemix sl vs list [OPZIONI]
```


<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Numero di core CPU</dd>
   <dt>-D, --domain</dt>
   <dd>Porzione dominio del FQDN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nome breve del datacenter</dd>
   <dt>-H, --hostname</dt>
   <dd>Porzione host del FQDN</dd>
   <dt>-m, --memory</dt>
   <dd>Memoria in megabyte</dd>
   <dt>-n, --network</dt>
   <dd>Velocità della porta di rete in Mbps</dd>
   <dt>--hourly</dt>
   <dd>Mostra solo le istanze orarie</dd>
   <dt>--monthly</dt>
   <dd>Mostra solo le istanze mensili</dd>
   <dt>--tag</dt>
   <dd>Filtra per tag (più ricorrenze consentite)</dd>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Il valore predefinito è: hostname</dd>
   <dt>--columns</dt>
   <dd>Colonne da visualizzare, le opzioni sono: guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. Il valore predefinito è: id, hostname, primary_ip, backend_ip, datacenter, action</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
Questo comando elenca tutte le istanze del server virtuale con fatturazione oraria nell'account corrente filtrando per dominio uguale a "bluemix.net" e ordinandole per memoria.



### bluemix sl vs-pause
{: #sl_vs_pause}

Metti in pausa un'istanza del server virtuale attiva
```
   bluemix sl vs pause IDENTIFIER [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs pause 12345678 -f
```
   Questo comando mette in pausa l'istanza del server virtuale con ID 12345678 senza richiedere conferma.



### bluemix sl vs power-off
{: #sl_vs_power_off}

Disattiva un'istanza del server virtuale attiva
```
   bluemix sl vs power-off IDENTIFIER [OPZIONI]
```

**Esempi**:
```
   bluemix sl vs power-off 12345678 --soft
```
Questo comando esegue un arresto semplice dell'istanza del server virtuale con ID 12345678.

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Esegui un arresto forzato</dd>
   <dt>--soft</dt>
   <dd>Esegui un arresto non forzato</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

Attiva un'istanza del server virtuale
```
 bluemix sl vs power-on IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs power-on 12345678
```
Questo comando esegue un avvio dell'istanza del server virtuale con ID 12345678.


### bluemix sl vs ready
{: #sl_vs_ready}

Verifica se un'istanza del server virtuale è pronta per l'utilizzo
```
 bluemix sl vs ready IDENTIFIER [OPZIONI]
```

**Esempi**:
```
 bluemix sl vs ready 12345678 --wait 30
```
Questo comando verifica lo stato dell'istanza del server virtuale con ID 12345678 per vedere se è pronta per l'utilizzo continuo e attende fino a 30 secondi.

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--wait</dt>
   <dd>Attendi finché il server virtuale non ha terminato il provisioning fino a X secondi prima di ritornare</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

Riavvia un'istanza del server virtuale attiva
```
 bluemix sl vs reboot IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Esegui un riavvio forzato</dd>
   <dt>--soft</dt>
   <dd>Esegui un riavvio non forzato</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs reboot 12345678 --hard
```
Questo comando esegue un riavvio forzato dell'istanza del server virtuale con ID 12345678.



### bluemix sl vs reload
{: #sl_vs_reload}

Ricarica il sistema operativo su un'istanza del server virtuale
```
 bluemix sl vs reload IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>Script di post installazione da scaricare</dd>
   <dt>--image</dt>
   <dd>ID immagine. L'impostazione predefinita è l'utilizzo del sistema operativo corrente.
Vedi: 'bluemix sl image list' per i riferimenti</dd>
   <dt>-k, --key</dt>
   <dd>Gli ID delle chiavi SSH da aggiungere all'utente root (più ricorrenze consentite)</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>

**Esempi**:
```
   bluemix sl vs reload 12345678
```
Questo comando ricarica il sistema operativo corrente per l'istanza del server virtuale con ID 12345678.
```
 bluemix sl vs reload 12345678 --image 1234
```
Questo comando ricarica il sistema operativo dall'immagine con ID 1234 per l'istanza del server virtuale con ID 12345678.



### bluemix sl vs rescure
{: #sl_vs_rescure}

Riavvia un'istanza del server virtuale in un'immagine di salvataggio
```
 bluemix sl vs rescue IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
   </dl>
   
**Esempi**:
```
 bluemix sl vs rescue 12345678
```
Questo comando riavvia l'istanza del server virtuale con ID 12345678 in un'immagine di salvataggio.


### bluemix sl vs resume
{: #sl_vs_resume}

Riprendi un'istanza del server virtuale in pausa
```
   bluemix sl vs resume IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs resume 12345678
```
Questo comando riprende l'istanza del server virtuale con ID 12345678.


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

Aggiorna un'istanza del server virtuale
```
   bluemix sl vs upgrade IDENTIFIER [OPZIONI]
```
Nota: SoftLayer riavvia automaticamente l'istanza una volta effettuata la richiesta di aggiornamento. L'istanza viene interrotta finché la transazione di aggiornamento non viene completata. Tuttavia, per la rete non è richiesto alcun riavvio.

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Numero di core CPU</dd>
   <dt>--private</dt>
   <dd>Il core CPU sarà su un server host dedicato</dd>
   <dt>-m, --memory</dt>
   <dd>Memoria in megabyte.</dd>
   <dt>--network</dt>
   <dd>Velocità della porta di rete in Mbps.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma.</dd>
    </dl>

**Esempi**:
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Questo comando aggiorna l'istanza del server virtuale con ID 12345678 e imposta il numero di core CPU su 8, la memoria su 8192M e la velocità della porta di rete su 1000 Mbps.



### bluemix sl vlan create
{: #sl_vlan_create}

Crea una nuova VLAN
```
   bluemix sl vlan create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>Il tipo di VLAN, pubblica o privata</dd>
   <dt>-r, --router</dt>
   <dd>Il nome host del router</dd>
   <dt>-d, --datacenter</dt>
   <dd>Il nome breve del datacenter</dd>
   <dt>-s, --size</dt>
   <dd>La dimensione delle sottoreti, le opzioni sono: 8 (5 IP utilizzabili) o 16 (13 IP utilizzabili) o 32 (29 IP utilizzabili)</dd>
   <dt>-n, --name</dt>
   <dd>Il nome della VLAN</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>

**Esempi**:
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Questo comando crea una vlan pubblica ubicata nel datacenter dal09 con 16 indirizzi IP e con il nome myvlan.
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
Questo comando crea una vlan ubicata nel router bcr01a.dal09 con 16 indirizzi IP e con il nome myvlan.



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

Annulla una VLAN
```
   bluemix sl vlan cancel IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Forza l'operazione senza conferma</dd>
    </dl>

**Esempi**:
```
   bluemix sl vlan cancel 12345678 -f
```
Questo comando annulla la vlan con ID 12345678 senza richiedere conferma.



### bluemix sl vlan detail
{: #sl_vlan_detail}

Ottieni i dettagli di una VLAN.
```
   bluemix sl vlan detail IDENTIFIER [OPZIONI]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Nascondi elenco server virtuali</dd>
   <dt>--no-hardware</dt>
   <dd>Nascondi elenco hardware</dd>
   </dl>

**Esempi**:
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
Questo comando mostra i dettagli della vlan con ID 12345678 e non elenca il server virtuale o il server hardware.


### bluemix sl vlan edit
{: #sl_vlan_edite}

Modifica i dettagli di una VLAN
```
   bluemix sl vlan edit IDENTIFIER [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--n, --name</dt>
   <dd>Il nome della VLAN</dd>
    </dl>

**Esempi**:
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
Questo comando aggiorna la vlan con ID 12345678 e le fornisce un nuovo nome "myvlan-rename".


### bluemix sl vlan list
{: #sl_vlan_list}

Elenca tutte le VLAN nel tuo account
```
 bluemix sl vlan list [OPZIONI]
```
<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Colonna da ordinare, le opzioni sono: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filtra per nome breve del datacenter</dd>
   <dt>-n, --number</dt>
   <dd>Filtra per numero VLAN</dd>
   <dt>--name</dt>
   <dd>Filtra per nome VLAN</dd>
   <dt>--order</dt>
   <dd>Filtra per ID dell'ordine di acquisto della VLAN</dd>
   </dl>

**Esempi**:
```
 bluemix sl vlan list -d dal09 --sortby number
```
Questo comando elenca tutte le vlan nell'account corrente eseguendo il filtro per un datacenter uguale a dal09 e le ordina per numero di vlan.




### bluemix sl vlan options
{: #sl_vlan_options}

Elenca tutte le opzioni per la creazione della VLAN
```
   bluemix sl vlan options
```
**Esempi**:
```
 bluemix sl vlan options
```
Questo comando elenca tutte le opzioni per la creazione di una vlan, ad es. il tipo di vlan, i datacenter, la dimensione della sottorete, i router, ecc
