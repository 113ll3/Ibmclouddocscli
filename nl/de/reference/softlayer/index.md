---

copyright:

  years: 2016,2018


lastupdated: "2018-06-08"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Befehle der {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur (ibmcloud sl)
{: #softlayer_cli}

Das Plug-in für {{site.data.keyword.BluSoftlayer}} wurde in die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle integriert. Sie müssen das Plug-in nicht mehr installieren.
{: tip}

Verwenden Sie die Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI), um die SoftLayer-Services zu konfigurieren und zu verwalten.

Ab Mai 2018 wird an Stelle der {{site.data.keyword.Bluemix_notm}}-CLI-Befehle `bluemix` und `bx` künftig der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch auch weiterhin noch so lange verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}


Zu Beginn installieren Sie die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle. Details hierzu finden Sie in [IBM Cloud-Befehlszeilenschnittstelle (CLI) ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}.

Eine umfassende Liste mit den Befehlen der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle finden Sie in [{{site.data.keyword.Bluemix_notm}}-Befehle (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).


## Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}

Folgende Befehle werden unterstützt. Verwenden Sie den Befehl `ibmcloud sl`, um die Liste der verfügbaren Befehle anzuzeigen:

<table summary="Allgemeine Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## Blockspeicherbefehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 2. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Blockspeicher</caption>
 <thead>
 <th colspan="6">Blockspeicher der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/softlayer/index.html#sl_block_replica_locations)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/softlayer/index.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/softlayer/index.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_disable)</td>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_enable)</td>
  </tr>
 <tr>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[ibmcloud sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
   </tr>
 <tr>
   <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/softlayer/index.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

 ## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - CDN-Befehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 3. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Content Delivery Network</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur - CDN</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/softlayer/index.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/softlayer/index.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/softlayer/index.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/softlayer/index.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/softlayer/index.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options](/docs/cli/reference/softlayer/index.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/softlayer/index.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Dateispeicherbefehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 4. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Dateispeicher</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur - Dateispeicher</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl file access-authorize](/docs/cli/reference/softlayer/index.html#sl_file_access_authorize)</td>
  <td>[ibmcloud sl file access-list](/docs/cli/reference/softlayer/index.html#sl_file_access_list)</td>
  <td>[ibmcloud sl file access-revoke](/docs/cli/reference/softlayer/index.html#sl_file_access_revoke)</td>
  <td>[ibmcloud sl file replica-failback](/docs/cli/reference/softlayer/index.html#sl_file_replica_failback)</td>
  <td>[ibmcloud sl file replica-failover](/docs/cli/reference/softlayer/index.html#sl_file_replica_failover)</td>
  <td>[ibmcloud sl file replica-locations](/docs/cli/reference/softlayer/index.html#sl_file_replica_locations)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl file replica-order](/docs/cli/reference/softlayer/index.html#sl_file_replica_order)</td>
  <td>[ibmcloud sl file replica-partners](/docs/cli/reference/softlayer/index.html#sl_file_replica_partners)</td>
  <td>[ibmcloud sl file snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_cancel)</td>
  <td>[ibmcloud sl file snapshot-create](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_create)</td>
  <td>[ibmcloud sl file snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_disable)</td>
  <td>[ibmcloud sl file snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_enable)</td>
  </tr>
 <tr>
  <td>[ibmcloud sl file snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_delete)</td>
  <td>[ibmcloud sl file snapshot-list](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_list)</td>
  <td>[ibmcloud sl file snapshot-order](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_order)</td>
  <td>[ibmcloud sl file snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_restore)</td>
  <td>[ibmcloud sl file volume-cancel](/docs/cli/reference/softlayer/index.html#sl_file_volume_cancel)</td>  
  <td>[ibmcloud sl file volume-detail](/docs/cli/reference/softlayer/index.html#sl_file_volume_detail)</td>
   </tr>
 <tr>
   <td>[ibmcloud sl file volume-duplicate](/docs/cli/reference/softlayer/index.html#sl_file_volume_duplicate)</td>
   <td>[ibmcloud sl file volume-list](/docs/cli/reference/softlayer/index.html#sl_file_volume_list)</td>
   <td>[ibmcloud sl file volume-order](/docs/cli/reference/softlayer/index.html#sl_file_volume_order)</td>
   <td>[ibmcloud sl file volume-options](/docs/cli/reference/softlayer/index.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - DNS-Befehle

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 5. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - DNS-Befehle</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - DNS-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/softlayer/index.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/softlayer/index.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/softlayer/index.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/softlayer/index.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/softlayer/index.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/softlayer/index.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/softlayer/index.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>


<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 6. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Befehle für globales IP (globalip)</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur - Befehle für globales IP</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Image-Befehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 7. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Image-Befehle</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Image-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/softlayer/index.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/softlayer/index.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/softlayer/index.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/softlayer/index.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

 ## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - IPSec-VPN-Befehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 7. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - IPSec-VPN-Befehle</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - IPSec-VPN-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl ipsec cancel](/docs/cli/reference/softlayer/index.html#sl_ipsec_cancel)</td>
 <td>[ibmcloud sl ipsec config](/docs/cli/reference/softlayer/index.html#sl_ipsec_config)</td>
 <td>[ibmcloud sl ipsec detail](/docs/cli/reference/softlayer/index.html#sl_ipsec_detail)</td>
 <td>[ibmcloud sl ipsec list](/docs/cli/reference/softlayer/index.html#sl_ipsec_list)</td>
 <td>[ibmcloud sl ipsec order](/docs/cli/reference/softlayer/index.html#sl_ipsec_order)</td>
 <td>[ibmcloud sl ipsec subnet-add](/docs/cli/reference/softlayer/index.html#sl_ipsec_subnet_add)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl ipsec subnet-remove](/docs/cli/reference/softlayer/index.html#sl_ipsec_subnet_remove)</td>
 <td>[ibmcloud sl ipsec translation-add](/docs/cli/reference/softlayer/index.html#sl_ipsec_translation_add)</td>
 <td>[ibmcloud sl ipsec translation-remove](/docs/cli/reference/softlayer/index.html#sl_ipsec_translation_remove)</td>
 <td>[ibmcloud sl ipsec translation-update](/docs/cli/reference/softlayer/index.html#sl_ipsec_translation_update)</td>
 <td>[ibmcloud sl ipsec update](/docs/cli/reference/softlayer/index.html#sl_ipsec_update)</td>
 </tr>
   </tbody>
 </table>

 ## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Befehle der Lastausgleichsfunktion (loadbal)

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 8. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Befehle der Lastausgleichsfunktion (loadbal)</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Befehle der Lastausgleichsfunktion (loadbal)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/softlayer/index.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/softlayer/index.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options](/docs/cli/reference/softlayer/index.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/softlayer/index.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks](/docs/cli/reference/softlayer/index.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list](/docs/cli/reference/softlayer/index.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods](/docs/cli/reference/softlayer/index.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types](/docs/cli/reference/softlayer/index.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Sicherheitsbefehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 9. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Sicherheitsbefehle (security)</caption>
 <thead>
 <th colspan="5">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Sicherheitsbefehle</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_add)</td>
  <td>[ibmcloud sl security sshkey-edit](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_edit)</td>
  <td>[ibmcloud sl security sshkey-list](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_list)</td>
  <td>[ibmcloud sl security sshkey-print](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_print)</td>   
  <td>[ibmcloud sl security sshkey-remove](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl security cert-add](/docs/cli/reference/softlayer/index.html#sl_security_cert_add)</td>
  <td>[ibmcloud sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Teilnetzbefehle (subnet)

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 10. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Teilnetzbefehle (subnet)</caption>
 <thead>
 <th colspan="5">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Teilnetzbefehle (subnet)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/softlayer/index.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/softlayer/index.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/softlayer/index.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/softlayer/index.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/softlayer/index.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Virtual-Server-Befehle

 <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 11. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Virtual-Server-Befehle</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Virtual-Server-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/softlayer/index.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/softlayer/index.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/softlayer/index.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/softlayer/index.html#sl_vs_detail)</td>
 </tr><tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/softlayer/index.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/softlayer/index.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/softlayer/index.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/softlayer/index.html#sl_vs_pause)</td>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/softlayer/index.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
 </tr><tr>
 <td>[ibmcloud sl vs ready](/docs/cli/reference/softlayer/index.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/softlayer/index.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/softlayer/index.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescure](/docs/cli/reference/softlayer/index.html#sl_vs_rescure)</td>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/softlayer/index.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/softlayer/index.html#sl_vs_upgrade)</td>
 </tr>
   </tbody>
 </table>

## Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - VLAN-Befehle

  <table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 12. Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - VLAN-Befehle</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - VLAN-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### Verwendung der Befehle
Zur Anzeige der Hilfeinformationen für die Befehle führen Sie folgenden Befehl aus: `ibmcloud sl [Befehl] -h`.

### ibmcloud sl init
{: #sl_init}

Konfigurationseinstellungen initialisieren, die für die Verbindung zur {{site.data.keyword.BluSoftlayer_notm}}-Infrastrukturumgebung verwendet werden. Die Konfiguration enthält den Benutzernamen, den API-Schlüssel oder das Kennwort, das Konto und den Endpunkt.
```
ibmcloud sl init [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL des API-Endpunkts für die {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur, Standardwert: https://api.softlayer.com/rest/v3.1 für API-Schlüssel-Authentifizierung, https://api.softlayer.com/mobile/v3.1 für IBMid-Authentifizierung.</dd>
<dt>-u, --sl-user</dt>
<dd>Der SoftLayer-Benutzername.</dd>
<dt>-p, --sl-password</dt>
<dd>Das SoftLayer-Kennwort oder der API-Schlüssel.</dd>
<dt>-c, --account-id</dt>
<dd>Die SoftLayer-Konto-ID.</dd>
<dt>-q, --security-question-id</dt>
<dd>Die ID der Sicherheitsfrage für die Authentifizierung; wenden Sie sich an den Kontoeigner, wenn sie nicht bekannt ist.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Die Antwort auf die Sicherheitsfrage für die Authentifizierung; wenden Sie sich an den Kontoeigner, wenn sie nicht bekannt ist.</dd>
<dt>-s, --security-code</dt>
<dd>Der vom Sicherheitsanbieter generierte Sicherheitscode, wenn die 2-Faktor-Authentifizierung aktiviert ist.</dd>
<dt>-v, --security-vendor</dt>
<dd>Der Sicherheitsanbieter, der den Sicherheitscode für die Authentifizierung bereitstellt; Optionen: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Das Authentifizierungstoken, wenn die Telefonauthentifizierung aktiviert ist.</dd>
</dl>

Beispiel: Mit dem Benutzernamen und dem Kennwort/API-Schlüssel der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} anmelden.
```
$ ibmcloud sl config
Konfiguration der Authentifizierung für die Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} auswählen:
1. Mit dem Benutzernamen und dem Kennwort/API-Schlüssel der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} anmelden.
2. Single Sign-On für {{site.data.keyword.Bluemix_notm}} verwenden.
Geben Sie eine Zahl > 1 ein.
Softlayer-API-Endpunkt-URL: [https://api.softlayer.com/rest/v3.1]>
Benutzername: []> wangjunl@cn.ibm.com
API-Schlüssel oder Kennwort: []> abcd

Softlayer-API-Endpunkt:    https://api.softlayer.com/rest/v3.1
Konto-ID:                  278444
Benutzer-ID:               wangjunl@cn.ibm.com
API-Schlüssel:             xxxxxxxxxx
```
Beispiel: {{site.data.keyword.Bluemix_notm}}-Single Sign-on für die Softlayer-Anmeldung verwenden.
```
$ ibmcloud login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API-Endpunkt: api.ng.bluemix.net
Authentifizieren...
OK

Als Ziel ausgewähltes Konto Wilmas Konto (65ce8074c6c62b5)

API-Endpunkt:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south
Benutzer:       wangjunl@cn.ibm.com
Konto:          Wilma's Account (65ce8074c6c62b5)   
Keine Organisation oder keinen Bereich als Ziel ausgewählt, verwenden Sie 'ibmcloud target --cf oder ibmcloud target -o ORG -s SPACE'

Tipp: Verwenden Sie 'ibmcloud cf <command>', um die Cloud Foundry-Befehlszeilenschnittstelle mit dem Kontext der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle auszuführen.
```

```
$ ibmcloud sl init
Konfiguration der Authentifizierung der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} auswählen:
1. Mit dem Benutzernamen und dem Kennwort/API-Schlüssel der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} anmelden.
2. {{site.data.keyword.Bluemix_notm}}-Single Sign-on verwenden

Geben Sie eine Zahl ein: 2
Softlayer-API-Endpunkt-URL: [https://api.softlayer.com/mobile/v3.1]
Für Konto festlegen: 278444
OK

Softlayer-API-Endpunkt:    https://api.softlayer.com/mobile/v3.1
Konto-ID:                 278444
Benutzer-ID:              12345678
IMS-Token:                xxxxxxxxxx
```

### ibmcloud sl help
{: #sl_help}

Hilfeinformationen für alle Befehle für den Betrieb der Infrastrukturumgebung von {{site.data.keyword.BluSoftlayer_notm}} anzeigen.
```
ibmcloud sl help

```

### ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Hosts für den Zugriff auf einen bestimmten Datenträger autorisieren.
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines Hardware-Servers, der autorisiert werden soll.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines virtuellen Servers, der autorisiert werden soll.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer IP-Adresse, die autorisiert werden soll.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine IP-Adresse, die autorisiert werden soll.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
Dieser Befehl autorisiert den virtuellen Server mit der ID 87654321 für den Zugriff auf den Datenträger mit der ID 12345678.

### ibmcloud sl block access-list
{: #sl_block_access_list}

Listet ACLs auf.
```
ibmcloud sl block access-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Anzuzeigende Spalten. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
Dieser Befehl listet alle Hosts auf, die für den Zugriff auf den Datenträger mit der ID 12345678 autorisiert sind, und sortiert diese nach ID.

### ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Autorisierung für Hosts widerrufen, die auf einen bestimmten Datenträger zugreifen.
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines der zu widerrufenden Hardware-Server.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines der zu widerrufenden virtuellen Server.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer der zu widerrufenden IP-Adressen.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine zu widerrufende IP-Adresse.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Dieser Befehl widerruft den Zugriff des virtuellen Servers mit der ID 87654321 auf den Datenträger mit der ID 12345678.

### ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Failback eines Blockdatenträgers von einem Replikat.
```
ibmcloud sl block replica-failback VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block replica-failback 12345678
```
Dieser Befehl führt eine Failback-Operation für den Datenträger mit der ID 12345678 aus.

### ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Failover eines Blockdatenträgers auf den angegebenen Replikatdatenträger.
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Beispiele**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
Dieser Befehl führt eine Failover-Operation für den Datenträger mit der ID 12345678 auf den Replikatdatenträger mit der ID 87654321 aus.

### ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Geeignete Replikationsrechenzentren für den angegebenen Datenträger auflisten.
```
ibmcloud sl block replica-locations VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block replica-locations 12345678
```
Dieser Befehl listet passende Replikationsrechenzentren für den Blockdatenträger mit der ID 12345678 auf.

### ibmcloud sl block replica-order
{: #sl_block_replica_order}

Blockspeicher-Replikatdatenträger bestellen.
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Erforderlich. Für die Replikation zu verwendender Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname für Rechenzentrum des Replikats, z. B. dal09.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: 0.25,2,4,10. Wenn kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-o, --os-type</dt>
<dd>Optional. Betriebssystemtyp (z. B. Linux) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Dieser Befehl bestellt ein Replikat für den Datenträger mit der ID 12345678, der eine DAILY-Replikation durchführt, mit dem Ort 'dal09', der Tierebene 4 und dem Betriebssystemtyp Linux.

### ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Vorhandene Replicant-Datenträger für Blockdatenträger auflisten.
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl block replica-partners 12345678
```
Dieser Befehl listet vorhandene Replicant-Datenträger für den Blockdatenträger mit der ID 12345678 auf.

### ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Vorhandenen Snapshotbereich für einen bestimmten Datenträger abbrechen.
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONEN]
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
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Snapshot mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Snapshot für einen bestimmten Datenträger erstellen.
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Anmerkungen zum neuen Snapshot.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforbluemix
```
Dieser Befehl erstellt einen Snapshot für den Datenträger mit der ID 12345678 und mit Zusatzanmerkung snapshotforbluemix.

### ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Snapshots für den angegebenen Zeitplan für einen bestimmten Datenträger inaktivieren.
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
Dieser Befehl inaktiviert den täglichen Snapshot für den Datenträger mit der ID 12345678.

### ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Snapshots für einen bestimmten Datenträger gemäß angegebenem Zeitplan aktivieren.
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Erforderlich. Anzahl der beizubehaltenden Snapshots.</dd>
<dt>-m, --minute</dt>
<dd>Minute der Stunde, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 59.</dd>
<dt>-r, --hour</dt>
<dd>Stunde des Tages, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Wochentag, an dem Snapshot erfasst werden sollen; Ganzzahl zwischen 0 und 6. 0 steht für Sonntag, 1 für Montag, 2 für Dienstag, 3 für Mittwoch, 4 für Donnerstag, 5 für Freitag, 6 für Samstag.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Dieser Befehl aktiviert den Snapshot für den Datenträger mit der ID 12345678; der Snapshot wird wöchentlich jeden Sonntag um 2:00 ausgeführt und bis zu 5 Snapshots werden beibehalten.

### ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Snapshot für einen bestimmten Datenträger löschen.
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl block snapshot-delete 12345678
```
Dieser Befehl löscht den Snapshot mit der ID 12345678.

### ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Blockspeichersnapshots auflisten.
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,created,size_bytes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
Dieser Befehl listet alle Snapshots des Datenträgers mit der ID 12345678 auf und sortiert diese nach ID.

### ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Snapshotbereich für einen Blockspeicherdatenträger bestellen.
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Erforderlich. Die Größe des zu erstellenden Snapshotbereichs in GB.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Blockdatenträgers, für den ein Bereich bestellt wurde. Optionen: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag zum Anzeigen, dass die Bestellung ein Upgrade ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
Dieser Befehl bestellt Snapshotbereich für den Datenträger mit der ID 12345678, Größe 1000 GB, Tierebene 4 E/A-Operationen pro Sekunde pro GB.

### ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Blockdatenträger mithilfe eines bestimmten Snapshots wiederherstellen.
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
Dieser Befehl stellt den Datenträger mit der ID 12345678 aus dem Snapshot mit der ID 87654321 wieder her.

### ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Abbruch für vorhandenen Blockspeicherdatenträger.
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>--immediate</dt>
<dd>Blockspeicherdatenträger sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Datenträger mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl block volume-list
{: #sl_block_volume_list}

Blockspeicher auflisten.
```
ibmcloud sl block volume-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Nach Datenträger-Benutzernamen filtern.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-t, --storage-type</dt>
<dd>Nach Typ des Speicherdatenträgers filtern, Optionen: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der der Blockspeicher gekauft wurde.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Spalten für die Anzeige, Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Dieser Befehl listet alle Endurance-Datenträger für das aktuelle Konto mit dem Ort 'dal09' auf und sortiert sie nach Kapazität.

### ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Details zu einem angegebenen Datenträger anzeigen.
```
ibmcloud sl block volume-detail VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block volume-detail 12345678
```
Dieser Befehl führt Details zu dem Datenträger mit der ID 12345678 auf.

### ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Blockdatenträger durch Duplizieren eines vorhandenen Datenträgers bestellen.
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID eines Ursprungsdatenträgersnapshots zur Verwendung für die Duplizierung.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Größe des duplizierten Blockdatenträgers in GB; falls keine Größe angegeben wird, verwendet das System die Größe des Originaldatenträgers.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance-Speichertier; falls kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Die Größe des Snapshotbereichs, der für das Duplikat bestellt werden muss; falls keine Größe für den Snapshotbereich angegeben wird, verwendet das System die Snapshotbereichsgröße des Ursprungsdatenträgers.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-duplicate 12345678
```
Dieser Befehl zeigt die Bestellung eines neuen Datenträgers durch Duplizierung des Datenträgers mit der ID 12345678 an.

### ibmcloud sl block volume-order
{: #sl_block_volume_order}

Blockspeicherdatenträger bestellen.
```
ibmcloud sl block volume-order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Erforderlich. Typ des Speicherdatenträgers; Optionen: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Erforderlich. Größe des Speicherdatenträgers in GB.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfache von 100 [erforderlich für Speichertyp 'Performance'].</dd>
<dt>-e, --tier</dt>
<dd>Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) [erforderlich für Endurance-Speichertyp], Optionen: 0.25,2,4,10.</dd>
<dt>-o, --os-type</dt>
<dd>Erforderlich. Betriebssystem; Optionen: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Rechenzentrum-Kurzname.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optionaler Parameter für die Bestellung eines Snapshotbereichs zusammen mit Endurance-Blockspeicher; gibt die Größe des zu bestellenden Snapshotbereichs in GB an.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Dieser Befehl bestellt einen Leistungsdatenträger mit Größe 1000 GB, 4000 E/A-Operationen pro Sekunde, Betriebssystem LINUX, Ort 'dal09'.

### ibmcloud sl block volume-options
{: #sl_block_volume_options}

Alle Optionen für die Anforderung eines Blockspeichers auflisten.
```
ibmcloud sl block volume-options
```


**Beispiele**:
```
ibmcloud sl block volume-options
```
Dieser Befehl listet alle Optionen für die Erstellung eines Blockspeicherdatenträgers auf, einschließlich Speichertyp, Datenträgergröße, Betriebssystemtyp, E/A-Operationen pro Sekunde, Tierebene, Rechenzentrum und Snapshotgröße.

### ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Abbruch für CDN-Konto.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
### ibmcloud sl cdn detail
{: #sl_cdn_detail}

Details eines CDN-Kontos aufführen.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
{: #sl_cdn_list}

Alle CDN-Konten auflisten.
```
ibmcloud sl cdn list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Nach Bestell-ID filtern.</dd>
</dl>
### ibmcloud sl cdn load
{: #sl_cdn_load}

Zwischenspeicherung von mindestens einer Datei auf allen Edge-Knoten.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

CDN-Konto bestellen.
```
ibmcloud sl cdn order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN-Bandbreite; Preis für nutzungsabhängige Gebühren wird verwendet, falls keine Angabe vorhanden ist.</dd>
<dt>-s, --storage</dt>
<dd>CDN-Speicher; Preis für nutzungsabhängige Gebühren wird verwendet, falls keine Angabe vorhanden ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
### ibmcloud sl cdn options
{: #sl_cdn_options}

Optionen für die Bandbreite und den Speicher bei der Anforderung eines CDN-Kontos.
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Origin-Pull-Zuordnung erstellen.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --type</dt>
<dd>Der Medientyp für diese Zuordnung (http, flash, wm, ...). Standardwert: http.</dd>
<dt>-c, --cname</dt>
<dd>Ein optionaler CNAME zum Verknüpfen mit der Zuordnung.</dd>
</dl>
### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Origin-Pull-Zuordnungen auflisten.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Origin-Pull-Zuordnung entfernen.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
### ibmcloud sl cdn purge
{: #sl_cdn_purge}

Zwischengespeicherte Dateien aus allen Edge-Knoten löschen.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
### ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Hosts für den Zugriff auf einen bestimmten Datenträger autorisieren.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines Hardware-Servers, der autorisiert werden soll.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines virtuellen Servers, der autorisiert werden soll.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer IP-Adresse, die autorisiert werden soll.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine IP-Adresse, die autorisiert werden soll.</dd>
<dt>-s, --subnet-id</dt>
<dd>Eine ID für ein zu autorisierendes Teilnetz.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
Dieser Befehl autorisiert den virtuellen Server mit der ID 87654321 für den Zugriff auf den Datenträger mit der ID 12345678.

### ibmcloud sl file access-list
{: #sl_file_access_list}

Listet ACLs auf.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Anzuzeigende Spalten. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file access-list 12345678 --sortby id
```
Dieser Befehl listet alle Hosts auf, die für den Zugriff auf den Datenträger mit der ID 12345678 autorisiert sind, und sortiert diese nach ID.

### ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Autorisierung für Hosts widerrufen, die auf einen bestimmten Datenträger zugreifen.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines der zu widerrufenden Hardware-Server.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines der zu widerrufenden virtuellen Server.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer der zu widerrufenden IP-Adressen.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine zu widerrufende IP-Adresse.</dd>
<dt>-s, --subnet-id</dt>
<dd>Eine ID für ein zu widerrufendes Teilnetz.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
Dieser Befehl widerruft den Zugriff des virtuellen Servers mit der ID 87654321 auf den Datenträger mit der ID 12345678.

### ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Failback eines Dateidatenträgers von einem Replikat.
```
ibmcloud sl file replica-failback VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file replica-failback 12345678
```
Dieser Befehl führt eine Failback-Operation für den Datenträger mit der ID 12345678 aus.

### ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Failover eines Dateidatenträgers auf den angegebenen Replikatdatenträger.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Beispiele**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
Dieser Befehl führt eine Failover-Operation für den Datenträger mit der ID 12345678 auf den Replikatdatenträger mit der ID 87654321 aus.

### ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Geeignete Replikationsrechenzentren für den angegebenen Datenträger auflisten.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file replica-locations 12345678
```
Dieser Befehl listet passende Replikationsrechenzentren für den Dateidatenträger mit der ID 12345678 auf.

### ibmcloud sl file replica-order
{: #sl_file_replica_order}

Datenspeicher-Replikatdatenträger bestellen.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Erforderlich. Für die Replikation zu verwendender Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname für Rechenzentrum des Replikats, z. B. dal09.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: 0.25,2,4,10. Wenn kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
Dieser Befehl bestellt ein Replikat für den Datenträger mit der ID 12345678, der eine DAILY-Replikation durchführt, mit dem Ort 'dal09' und der Tierebene 4.

### ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Vorhandene Replicant-Datenträger für einen Dateidatenträger auflisten.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl file replica-partners 12345678
```
Dieser Befehl listet vorhandene Replicant-Datenträger für den Dateidatenträger mit der ID 12345678 auf.

### ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Vorhandenen Snapshotbereich für einen bestimmten Datenträger abbrechen.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONEN]
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
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Snapshot mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Snapshot für einen bestimmten Datenträger erstellen.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Anmerkungen zum neuen Snapshot.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforbluemix
```
Dieser Befehl erstellt einen Snapshot für den Datenträger mit der ID 12345678 und mit Zusatzanmerkung snapshotforbluemix.

### ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Snapshots für den angegebenen Zeitplan für einen bestimmten Datenträger inaktivieren.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
Dieser Befehl inaktiviert den täglichen Snapshot für den Datenträger mit der ID 12345678.

### ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Snapshots für einen bestimmten Datenträger gemäß angegebenem Zeitplan aktivieren.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Erforderlich. Anzahl der beizubehaltenden Snapshots.</dd>
<dt>-m, --minute</dt>
<dd>Minute der Stunde, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 59.</dd>
<dt>-r, --hour</dt>
<dd>Stunde des Tages, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Wochentag, an dem Snapshot erfasst werden sollen; Ganzzahl zwischen 0 und 6. 0 steht für Sonntag, 1 für Montag, 2 für Dienstag, 3 für Mittwoch, 4 für Donnerstag, 5 für Freitag, 6 für Samstag.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Dieser Befehl aktiviert den Snapshot für den Datenträger mit der ID 12345678; der Snapshot wird wöchentlich jeden Sonntag um 2:00 ausgeführt und bis zu 5 Snapshots werden beibehalten.

### ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Snapshot für einen bestimmten Datenträger löschen.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl file snapshot-delete 12345678
```
Dieser Befehl löscht den Snapshot mit der ID 12345678.

### ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Dateidatenträgersnapshots auflisten.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,created,size_bytes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
Dieser Befehl listet alle Snapshots des Datenträgers mit der ID 12345678 auf und sortiert diese nach ID.

### ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Snapshotbereich für einen Dateispeicherdatenträger bestellen.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Erforderlich. Die Größe des zu erstellenden Snapshotbereichs in GB.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Dateidatenträgers, für den ein Bereich bestellt wurde. Optionen: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag zum Anzeigen, dass die Bestellung ein Upgrade ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Diese Befehle bestellen Snapshotbereich für den Datenträger mit der ID 12345678, Größe 1000 GB, Tierebene 4 E/A-Operationen pro Sekunde pro GB.

### ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Dateidatenträger mithilfe eines bestimmten Snapshots wiederherstellen.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
Dieser Befehl stellt den Datenträger mit der ID 12345678 aus dem Snapshot mit der ID 87654321 wieder her.

### ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Abbruch für vorhandenen Dateispeicherdatenträger.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>--immediate</dt>
<dd>Dateispeicherdatenträger sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Datenträger mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl file volume-list
{: #sl_file_volume_list}

Dateispeicher auflisten.
```
ibmcloud sl file volume-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Nach Datenträger-Benutzernamen filtern.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-t, --storage-type</dt>
<dd>Nach Typ des Speicherdatenträgers filtern, Optionen: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der der Dateispeicher gekauft wurde.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Spalten für die Anzeige, Optionen: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Dieser Befehl listet alle Endurance-Datenträger für das aktuelle Konto mit dem Ort 'dal09' auf und sortiert sie nach Kapazität.

### ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Details zu einem angegebenen Datenträger anzeigen.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file volume-detail 12345678
```
Dieser Befehl führt Details zu dem Datenträger mit der ID 12345678 auf.

### ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Dateidatenträger durch Duplizieren eines vorhandenen Datenträgers bestellen.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID eines Originaldatenträgersnapshots zur Verwendung für die Duplizierung.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Größe des duplizierten Dateidatenträgers in GB; falls keine Größe angegeben wird, verwendet das System die Größe des Originaldatenträgers.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance-Speichertier; falls kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Die Größe des Snapshotbereichs, der für das Duplikat bestellt werden muss; falls keine Größe für den Snapshotbereich angegeben wird, verwendet das System die Snapshotbereichsgröße des Originaldatenträgers.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-duplicate 12345678
```
Dieser Befehl zeigt die Bestellung eines neuen Datenträgers durch Duplizierung des Datenträgers mit der ID 12345678 an.

### ibmcloud sl file volume-order
{: #sl_file_volume_order}

Dateispeicherdatenträger bestellen.
```
ibmcloud sl file volume-order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Erforderlich. Typ des Speicherdatenträgers; Optionen: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Erforderlich. Größe des Speicherdatenträgers in GB.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfache von 100 [erforderlich für Speichertyp 'Performance'].</dd>
<dt>-e, --tier</dt>
<dd>Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) [erforderlich für Endurance-Speichertyp], Optionen: 0.25,2,4,10.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Rechenzentrum-Kurzname.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optionaler Parameter für die Bestellung eines Snapshotbereichs zusammen mit dem Datenträger.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Dieser Befehl bestellt einen Leistungsdatenträger mit einer Größe von 1000 GB. Der Wert für die E/A-Operationen pro Sekunde beträgt 4000, der Ort ist 'dal09'.

### ibmcloud sl file volume-options
{: #sl_file_volume_options}

Alle Optionen für die Anforderung eines Dateispeichers auflisten.
```
ibmcloud sl file volume-options
```


**Beispiele**:
```
ibmcloud sl file volume-options
```
Dieser Befehl listet alle Optionen für die Erstellung eines Dateispeicherdatenträgers auf, einschließlich Speichertyp, Datenträgergröße, E/A-Operationen pro Sekunde, Tierebene, Rechenzentrum und Snapshotgröße.

### ibmcloud sl dns import
{: #sl_dns_import}

Zone auf Basis einer BIND-Zonendatei importieren.
```
ibmcloud sl dns import ZONEFILE [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--dry-run</dt>
<dd>Datensätze nicht tatsächlich erstellen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns import ~/blumix.net.txt
```
Dieser Befehl importiert die Zone und ihre Ressourcendatensätze aus der Datei ~/blumix.net.txt.

### ibmcloud sl dns record-add
{: #sl_dns_record_add}

Ressourcendatensatz in einer Zone hinzufügen.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL-Wert (Time-To-Live) in Sekunden, z. B. 86400; Standardwert ist: 7200.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Dieser Befehl fügt einen A-Datensatz zur Zone bluemix.net hinzu, der Host ist "ftp", Daten sind "127.0.0.1" und TTL ist 86400 Sekunden.

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Ressourcendatensätze in einer Zone aktualisieren.
```
ibmcloud sl dns record-edit ZONE [OPTIONEN]
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
ibmcloud sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Dieser Befehl bearbeitet Datensätze unter der Zone bluemix.net, deren ID 12345678 ist, und legt ihre Daten auf \"127.0.0.2\" und TTL auf 3600 fest.

### ibmcloud sl dns record-list
{: #sl_dns_record_list}

Alle Ressourcendatensätze in einer Zone auflisten.
```
ibmcloud sl dns record-list ZONE [OPTIONEN]
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
<dd>Nach Datensatztyp filtern, z. B. A oder CNAME.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Dieser Befehl listet alle A-Datensätze unter der Zone bluemix.net auf; der Host, nach dem gefiltert wird, ist elasticsearch und TTL ist 900 Sekunden.

### ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Ressourcendatensätze aus einer Zone entfernen.
```
ibmcloud sl dns record-remove RECORD_ID
```


**Beispiele**:
```
ibmcloud sl dns record-remove 12345678
```
Dieser Befehl entfernt den Ressourcendatensatz mit der ID 12345678.

### ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Zone erstellen.
```
ibmcloud sl dns zone-create ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-create bluemix.net
```
Dieser Befehl erstellt eine Zone mit dem Namen bluemix.net.

### ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Zone löschen.
```
ibmcloud sl dns zone-delete ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-delete bluemix.net
```
Dieser Befehl löscht eine Zone mit dem Namen bluemix.net.

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Alle Zonen für eigenes Konto auflisten.
```
ibmcloud sl dns zone-list
```


**Beispiele**:
```
ibmcloud sl dns zone-list
```
Dieser Befehl listet alle Zonen unter einem aktuellen Konto auf.

### ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Zone und Ressourcendatensätze in BIND-Format ausgeben.
```
ibmcloud sl dns zone-print ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-print bluemix.net
```
Dieser Befehl gibt eine Zone mit dem Namen bluemix.net im BIND-Format aus.

### ibmcloud sl globalip create
{: #sl_globalip_create}

Globale IP erstellen.
```
ibmcloud sl globalip create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--v6</dt>
<dd>IPv6-IP-Adresse bestellen.</dd>
<dt>--test</dt>
<dd>Testbestellung.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip create --v6
```
Dieser Befehl erstellt eine IPv6-Adresse.

### ibmcloud sl globalip assign
{: #sl_globalip_assign}

Globale IP einem Zielrouter oder -gerät zuordnen.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Beispiele**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
Dieser Befehl ordnet eine IP-Adresse mit der ID 12345678 zu einem Zielgerät mit der IP-Adresse 9.111.123.456 zu.

### ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Abbruch für globale IP.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip cancel 12345678
```
Dieser Befehl bricht die IP-Adresse mit der ID 12345678 ab.

### ibmcloud sl globalip list
{: #sl_globalip_list}

Alle globalen IPs für eigenes Konto auflisten.
```
ibmcloud sl globalip list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--v4</dt>
<dd>Nur IPv4-IPs anzeigen.</dd>
<dt>--v6</dt>
<dd>Nur IPv6-IPs anzeigen.</dd>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der diese IP-Adresse gekauft wurde.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip list --v4
```
Dieser Befehl listet alle IPv4-Adressen für ein aktuelles Konto auf.

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Zuordnung einer globalen IP zu einem Zielrouter oder -gerät aufheben.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Beispiele**:
```
ibmcloud sl globalip unassign 12345678
```
Dieser Befehl hebt die Zuordnung einer IP-Adresse mit der ID 12345678 zu einem Zielgerät auf.

### ibmcloud sl image delete
{: #sl_image_delete}

Image löschen.
```
ibmcloud sl image delete IDENTIFIER
```
**Beispiele**:
```
   ibmcloud sl image delete 12345678
```
Dieser Befehl löscht das Image mit der ID `12345678`.

### ibmcloud sl image detail
{: #sl_image_detail}

Details zu einem Image abrufen.
```
ibmcloud sl image detail IDENTIFIER
```
**Beispiele**:
```
 ibmcloud sl image detail 12345678
```
Dieser Befehl ruft Details zu dem Image mit der ID 12345678 ab.

### ibmcloud sl image edit
{: #sl_image_edit}

Details zu einem Image bearbeiten.
```
ibmcloud sl image edit IDENTIFIER [OPTIONEN]
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

*Beispiele**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Dieser Befehl bearbeitet ein Image mit der ID `12345678` und legt den Namen auf `ubuntu16`, die Anmerkung auf `testing` und den Tag auf `staging` fest.

### ibmcloud sl image list
{: #sl_image_list}

Alle Images für eigenes Konto auflisten.
```
ibmcloud sl image list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--name</dt>
<dd>Nach Imagename filtern.</dd>
<dt>--public</dt>
<dd>Nur öffentliche Images anzeigen.</dd>
<dt>--private</dt>
<dd>Nur private Images anzeigen.</dd>
</dl>

### ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Abbruch für IPSec-VPN-Tunnelkontext.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--immediate</dt>
<dd>IPSec sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl ipsec config
{: #sl_ipsec_config}

Konfiguration von Tunnelkontext anfordern.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONEN]
```

### ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Details für IPSec-VPN-Tunnelkontext auflisten.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Zusätzliche Ressourcen einschließen. Optionen: at,is,rs,sr,ss.</dd>
</dl>
### ibmcloud sl ipsec list
{: #sl_ipsec_list}

IPSec-VPN-Tunnelkontexte auflisten.
```
ibmcloud sl ipsec list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der IPSec gekauft wurde.</dd>
</dl>
### ibmcloud sl ipsec order
{: #sl_ipsec_order}

IPSec-VPN-Tunnel bestellen.
```
ibmcloud sl ipsec order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname des Rechenzentrums für IPSec, z. B. dal09.</dd>
</dl>

### ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Teilnetz zu IPSec-Tunnelkontext hinzufügen.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>ID des hinzuzufügenden Teilnetzes, erforderlich.</dd>
<dt>-t, --subnet-type</dt>
<dd>Typ des hinzuzufügenden Teilnetzes, erforderlich. Optionen: internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>ID des zu erstellenden Teilnetzes.</dd>
</dl>

### ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Teilnetz aus IPSEC-Tunnelkontext entfernen.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONEN]
```

### ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Adressumsetzung zu IPSec-Tunnel hinzufügen.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Statische IP-Adresse, erforderlich.</dd>
<dt>-r, --remote-ip</dt>
<dd>Ferne IP-Adresse, erforderlich.</dd>
<dt>-n, --note</dt>
<dd>Hinweis.</dd>
</dl>
### ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Umsetzungseintrag aus IPSec entfernen.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONEN]
```

### ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Adressumsetzung für IPSec aktualisieren.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Statische IP-Adresse, erforderlich.</dd>
<dt>-r, --remote-ip</dt>
<dd>Ferne IP-Adresse, erforderlich.</dd>
<dt>-n, --note</dt>
<dd>Hinweis.</dd>
</dl>
### ibmcloud sl ipsec update
{: #sl_ipsec_update}

Eigenschaften für Tunnelkontext aktualisieren.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Anzeigename.</dd>
<dt>-r, --remote-peer</dt>
<dd>Ferne Peer-IP-Adresse.</dd>
<dt>-k, --preshared-key</dt>
<dd>Vorab verteilter Schlüssel.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Authentifizierung der Phase 1; Optionen: MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Verschlüsselung der Phase 1; Optionen: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Diffie-Hellman-Gruppe der Phase 1; Optionen: 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Schlüssellebenszyklus für Phase 1; Bereich: 120-172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Authentifizierung der Phase 2; Optionen: MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Verschlüsselung der Phase 2; Optionen: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Diffie-Hellman-Gruppe der Phase 2; Optionen: 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Absolute vorwärts gerichtete Sicherheit für Phase 2; Bereich: 0-1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Schlüssellebenszyklus für Phase 2; Bereich: 120-172800.</dd>
</dl>

### ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Abbruch für vorhandene Lastausgleichsfunktion.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

Fügt eine Lastausgleichsfunktion hinzu, der die ID zugewiesen wird, die von 'create-options' zurückgegeben wurde.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Preisoptionen zum Erstellen einer Lastausgleichsfunktion abrufen.
```
ibmcloud sl loadbal create-options
```

### ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Details zu Lastausgleichsfunktion abrufen.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

### ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Fügt einen neuen 'load_balancer'-Service hinzu.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Erforderlich. Der zugeordnete Prozentsatz an Verbindungen.</dd>
<dt>-p, --port</dt>
<dd>Erforderlich. Die Portnummer.</dd>
<dt>-t, --routing-type</dt>
<dd>Erforderlich. Die ID des Routing-Typs. Führen Sie 'ibmcloud sl loadbal routing-types' aus, um eine ID zu suchen.</dd>
<dt>-m, --routing-method</dt>
<dd>Erforderlich. Die ID der Routing-Methode. Führen Sie 'ibmcloud sl loadbal routing-methods' aus, um eine ID zu suchen.</dd>
</dl>

### ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Löscht eine vorhandene Gruppe von Services für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Bearbeitet eine vorhandene Gruppe von Services für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Ändert den zugeordneten Prozentsatz an Verbindungen.</dd>
<dt>-p, --port</dt>
<dd>Ändert die Portnummer.</dd>
<dt>-t, --routing-type</dt>
<dd>Ändert die ID des Routing-Typs. Führen Sie 'ibmcloud sl loadbal routing-types' aus, um eine ID zu suchen.</dd>
<dt>-m, --routing-method</dt>
<dd>Ändert die ID der Routing-Methode. Führen Sie 'ibmcloud sl loadbal routing-methods' aus, um eine ID zu suchen.</dd>
</dl>

### ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Verbindungen für bestimmte Servicegruppe zurücksetzen.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Statusprüfungstypen auflisten.
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

Aktive Lastausgleichsfunktionen auflisten.
```
ibmcloud sl loadbal list
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der die Lastausgleichsfunktion gekauft wurde.</dd>
<dt>-p, --ip-address</dt>
<dd>Nach IP-Adresse filtern.</dd>
</dl>
### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Routing-Methoden auflisten.
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Routing-Typen auflisten.
```
ibmcloud sl loadbal routing-types
```

### ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Fügt einen neuen Service für die Lastausgleichsfunktion hinzu.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--disabled</dt>
<dd>Optional. Erstellt den Service als 'inaktiviert'; Standardwert ist 'aktiviert', wenn nicht angegeben.</dd>
<dt>-p, --port</dt>
<dd>Erforderlich. Die Portnummer für den Service.</dd>
<dt>-w, --weight</dt>
<dd>Erforderlich. Die Gewichtung des Service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Erforderlich. Der Statusprüfungstyp.</dd>
<dt>-i, --ip-address</dt>
<dd>Erforderlich. Die IP-Adresse des Service.</dd>
</dl>

### ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Löscht einen vorhandenen Service für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Bearbeitet die Eigenschaften einer Servicegruppe.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--disabled</dt>
<dd>Inaktiviert den Service.</dd>
<dt>--enabled</dt>
<dd>Aktiviert den Service.</dd>
<dt>-p, --port</dt>
<dd>Ändert die Portnummer für den Service.</dd>
<dt>-w, --weight</dt>
<dd>Ändert die Gewichtung des Service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Ändert den Typ der Statusprüfung.</dd>
<dt>-i, --ip-address</dt>
<dd>Ändert die IP-Adresse des Service.</dd>
</dl>

### ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Wechselt den Status eines vorhandenen Service für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl security sshkey-add
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
Dieser Befehl fügt einen SSH-Schlüssel aus der Datei ~/.ssh/id_rsa.pub mit der Anmerkung "mykey" hinzu.

### ibmcloud sl security sshkey-edit
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
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Dieser Befehl aktualisiert den SSH-Schlüssel mit der ID 12345678 und legt die Bezeichnung auf "Bluemix" und die Anmerkung auf "testing" fest.

### ibmcloud sl security sshkey-list
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
Dieser Befehl listet alle SSH-Schlüssel für das aktuelle Konto auf und sortiert sie nach Bezeichnung.

### ibmcloud sl security sshkey-print
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
Dieser Befehl zeigt die ID, die Bezeichnung und die Anmerkungen des SSH-Schlüssels mit der ID 12345678 an und schreibt den öffentlichen Schlüssel in die Datei ~/mykey.pub.

### ibmcloud sl security sshkey-remove
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
Dieser Befehl entfernt den SSH-Schlüssel mit der ID 12345678, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl security cert-add
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
ibmcloud sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key
```
Dieser Befehl fügt die Zertifikatsdatei ~/bluemix.net.cert und die Datei mit privatem Schlüssel ~/bluemix.net.key für die Domäne bluemix.net hinzu.

### ibmcloud sl security cert-edit
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
ibmcloud sl security cert-edit 12345678 --key ~/bluemix.net.key
```
Dieser Befehl bearbeitet das Zertifikat mit der ID 12345678 und aktualisiert den zugehörigen privaten Schlüssel mit der Datei ~/bluemix.net.key.

### ibmcloud sl security cert-download
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

### ibmcloud sl security cert-list
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

### ibmcloud sl security cert-remove
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

### ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Abbruch für Teilnetz.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Dieser Befehl bricht das Teilnetz mit der ID 12345678 ab, ohne zu einer Bestätigung aufzufordern

### ibmcloud sl subnet create
{: #sl_subnet_create}

Neues Teilnetz zu eigenem Konto hinzufügen.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>IPv6-Adressen bestellen.</dd>
<dt>--test</dt>
<dd>Teilnetz nicht bestellen, nur ein Angebot anfordern.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet create public 16 567
```
Dieser Befehl erstellt ein öffentliches Teilnetz mit 16 IPv4-Adressen und ordnet es im VLAN mit der ID 567 an.

### ibmcloud sl subnet detail
{: #sl_subnet_detail}

Details zu einem Teilnetz abrufen.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONEN]
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
ibmcloud sl subnet detail 12345678
```
Dieser Befehl zeigt Detailinformationen zum Teilnetz mit der ID 12345678 an, einschließlich Informationen zu virtuellen Servern und Hardware-Servern.

### ibmcloud sl subnet list
{: #sl_subnet_list}

Alle Teilnetze für eigenes Konto auflisten.
```
ibmcloud sl subnet list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
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
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Dieser Befehl listet IPv4-Teilnetze für das aktuelle Konto auf, gefiltert nach Rechenzentrum; Ort 'dal09', Teilnetztyp PRIMARY und Netzbereich PUBLIC.

### ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

IP-Adresse suchen und ihr Teilnetz sowie Gerätedaten anzeigen.
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**Beispiele**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
Dieser Befehl sucht nach dem IP-Adressdatensatz mit der Adresse 9.125.235.255 und zeigt sein Teilnetz und die Gerätedaten an.

### ibmcloud sl vlan create
{: #sl_vlan_create}

Neues VLAN erstellen.
```
ibmcloud sl vlan create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>Der Typ des VLANs, entweder öffentlich oder privat.</dd>
<dt>-r, --router</dt>
<dd>Der Hostname des Routers.</dd>
<dt>-d, --datacenter</dt>
<dd>Der Kurzname des Rechenzentrums.</dd>
<dt>-s, --size</dt>
<dd>Die Größe der Teilnetze; Optionen: 8 (5 verwendbare IPs) oder 16 (13 verwendbare IPs) oder 32 (29 verwendbare IPs).</dd>
<dt>-n, --name</dt>
<dd>Der Name des VLANs.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Dieser Befehl erstellt ein öffentliches VLAN in Rechenzentrum dal09 mit 16 IP-Adressen und dem Namen myvlan.

### ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Abbruch für VLAN.
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan cancel 12345678 -f
```
Dieser Befehl bricht das VLAN mit der ID 12345678 ab, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl vlan detail
{: #sl_vlan_detail}

Details zu einem VLAN abrufen.
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONEN]
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
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
Dieser Befehl zeigt Details zum VLAN mit der ID 12345678 an, ohne virtuelle Server oder Hardware-Server aufzulisten.

### ibmcloud sl vlan edit
{: #sl_vlan_edit}

Details zu einem VLAN bearbeiten.
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Der Name des VLANs.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
Dieser Befehl aktualisiert das VLAN mit der ID 12345678 und benennt es in "myvlan-rename" um.

### ibmcloud sl vlan list
{: #sl_vlan_list}

Alle VLANs für eigenes Konto auflisten.
```
ibmcloud sl vlan list [OPTIONEN]
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
ibmcloud sl vlan list -d dal09 --sortby number
```
Dieser Befehl listet alle VLANs für das aktuelle Konto, gefiltert nach Rechenzentrum gleich dal09, und sortiert sie nach VLAN-Nummer.

### ibmcloud sl vlan options
{: #sl_vlan_options}

Alle Optionen für die VLAN-Erstellung auflisten.
```
ibmcloud sl vlan options
```


**Beispiele**:
```
ibmcloud sl vlan options
```
Dieser Befehl listet alle Optionen für die VLAN-Erstellung auf, z. B. VLAN-Typ, Rechenzentren, Teilnetzgröße, Router usw.

### ibmcloud sl vs cancel
{: #sl_vs_cancel}

Abbruch für virtuelle Serverinstanz.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs cancel 12345678
```
Dieser Befehl bricht die virtuelle Serverinstanz mit der ID of 12345678 ab.

### ibmcloud sl vs capture
{: #sl_vs_capture}

Virtuelle Serverinstanz in einem Image erfassen.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Erforderlich. Name des Images.</dd>
<dt>--all</dt>
<dd>Alle zum virtuellen Server gehörigen Platten erfassen.</dd>
<dt>--note</dt>
<dd>Anmerkung hinzufügen, die dem Image zugeordnet werden soll.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs capture 12345678 -n mybluemix --all --note testing
```
Dieser Befehl erfasst die virtuelle Serverinstanz mit der ID 12345678 mit allen Platten in ein Image mit dem Namen "mybluemix" und der Anmerkung "testing".

### ibmcloud sl vs create
{: #sl_vs_create}

Virtuelle Serverinstanz erstellen.
```
ibmcloud sl vs create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Erforderlich. Hostteil des FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Erforderlich. Domänenteil des FQDN.</dd>
<dt>-c, --cpu</dt>
<dd>Erforderlich. Anzahl der CPU-Cores.</dd>
<dt>-m, --memory</dt>
<dd>Erforderlich. Speicher in Megabyte.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname des Rechenzentrums.</dd>
<dt>-o, --os</dt>
<dd>Betriebssystem-Installationscode. Tipp: Sie können <OS>_LATEST angeben.</dd>
<dt>--image</dt>
<dd>Image-ID. Siehe 'ibmcloud sl image list'.</dd>
<dt>--billing</dt>
<dd>Verrechnungssatz. Standardwert: hourly. Optionen: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Dedizierten virtuellen Server erstellen (privater Knoten).</dd>
<dt>--san</dt>
<dd>SAN-Speicher anstelle der lokalen Festplatte verwenden.</dd>
<dt>--test</dt>
<dd>Virtuellen Server nicht tatsächlich erstellen.</dd>
<dt>--export</dt>
<dd>Optionen in eine Vorlagendatei exportieren.</dd>
<dt>-i, --postinstall</dt>
<dd>Nachinstallationsscript herunterladen.</dd>
<dt>-k, --key</dt>
<dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig).</dd>
<dt>--disk</dt>
<dd>Plattengrößen (Mehrfachvorkommen zulässig).</dd>
<dt>--private</dt>
<dd>Erzwingt, dass der virtuelle Server nur auf das private Netz zugreifen kann.</dd>
<dt>--like</dt>
<dd>Konfiguration von einem vorhandenen virtuellen Server verwenden.</dd>
<dt>-n, --network</dt>
<dd>Übertragungsgeschwindigkeit des Netzports in MB/s.</dd>
<dt>--tag</dt>
<dd>Zur Instanz hinzuzufügende Tags (Mehrfachvorkommen zulässig).</dd>
<dt>-t, --template</dt>
<dd>Eine Vorlagendatei, mit der die Befehlszeilenoptionen auf Standardwerte zurückgesetzt werden.</dd>
<dt>-u, --userdata</dt>
<dd>Benutzerdefinierte Metadaten-Zeichenfolge.</dd>
<dt>-F, --userfile</dt>
<dd>Benutzerdaten aus Datei lesen.</dd>
<dt>--vlan-public</dt>
<dd>Die ID des öffentlichen VLANs, in dem der virtuelle Server angeordnet werden soll.</dd>
<dt>--vlan-private</dt>
<dd>Die ID des privaten VLANs, in dem der virtuelle Server angeordnet werden soll.</dd>
<dt>--wait</dt>
<dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat, bevor Sie zurückkehren.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Dieser Befehl bestellt eine virtuelle Serverinstanz mit dem Hostnamen myvsi, der Domäne bluemix.net, 4 CPU-Cores, 4096 M Speicher und Position im Rechenzentrum dal10.

### ibmcloud sl vs options
{: #sl_vs_options}

Optionen für Erstellung einer virtuellen Serverinstanz auflisten.
```
ibmcloud sl vs options [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl vs options
```
Dieser Befehl listet alle Optionen für die Erstellung einer virtuellen Serverinstanz auf, z. B. Rechenzentren, CPU, Speicher, Betriebssystem, Platte, Netzgeschwindigkeit usw.

### ibmcloud sl vs credentials
{: #sl_vs_credentials}

Berechtigungsnachweise für virtuelle Serverinstanz auflisten.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl vs credentials 12345678
```
Dieser Befehl listet alle Benutzernamen- und Kennwortpaare der virtuellen Serverinstanz mit der ID 12345678 auf.

### ibmcloud sl vs detail
{: #sl_vs_detail}

Details zu einer virtuellen Serverinstanz abrufen.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--passwords</dt>
<dd>Kennwörter anzeigen (achten Sie darauf, dass niemand dabei zusehen kann!).</dd>
<dt>--price</dt>
<dd>Zugeordnete Preise anzeigen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs details 12345678
```
Dieser Befehl listet Detailinformationen zur virtuellen Serverinstanz mit der ID 12345678 auf.

### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

DNS-Datensätze für eine virtuelle Serverinstanz synchronisieren.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>A-Datensatz für Host synchronisieren.</dd>
<dt>--aaaa-record</dt>
<dd>AAAA-Datensatz für Host synchronisieren.</dd>
<dt>--ptr</dt>
<dd>PTR-Datensatz für Host synchronisieren.</dd>
<dt>--ttl</dt>
<dd>Legt TTL für die A- und/oder PTR-Datensätze fest; Standardwert: 7200.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Dieser Befehl synchronisiert den A-Datensatz (IPv4-Adresse) der virtuellen Serverinstanz mit der ID 12345678 mit dem DNS-Server und legt das TTL dieses A-Datensatzes auf 3600 fest.

### ibmcloud sl vs edit
{: #sl_vs_edit}

Details zu einer virtuellen Serverinstanz bearbeiten.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Domänenteil des FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Hostteil des FQDN. Beispiel: Server.</dd>
<dt>--tag</dt>
<dd>Tags zum Festlegen oder leere Zeichenfolge, um alle zu entfernen.</dd>
<dt>-u, --userdata</dt>
<dd>Benutzerdefinierte Metadaten-Zeichenfolge.</dd>
<dt>-F, --userfile</dt>
<dd>Benutzerdaten aus Datei lesen.</dd>
<dt>--public-speed</dt>
<dd>Übertragungsgeschwindigkeit des öffentlichen Ports; Optionen: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Übertragungsgeschwindigkeit des privaten Ports; Optionen: 0,10,100,1000,10000.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Dieser Befehl aktualisiert die virtuelle Serverinstanz mit der ID 12345678 und legt ihre Domäne auf 'bluemix.net', den Hostnamen auf 'myapp' und den Tag auf 'testcli' fest.

### ibmcloud sl vs list
{: #sl_vs_list}

Virtuelle Serverinstanzen für eigenes Konto auflisten.
```
ibmcloud sl vs list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Anzahl der CPU-Cores.</dd>
<dt>-D, --domain</dt>
<dd>Domänenteil des FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Kurzname des Rechenzentrums.</dd>
<dt>-H, --hostname</dt>
<dd>Hostteil des FQDN.</dd>
<dt>-m, --memory</dt>
<dd>Speicher in Megabyte.</dd>
<dt>-n, --network</dt>
<dd>Übertragungsgeschwindigkeit des Netzports in MB/s.</dd>
<dt>--hourly</dt>
<dd>Nur stündliche Instanzen anzeigen.</dd>
<dt>--monthly</dt>
<dd>Nur monatliche Instanzen anzeigen.</dd>
<dt>--tag</dt>
<dd>Nach Tags filtern (Mehrfachvorkommen zulässig).</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Standardwert: hostname.</dd>
<dt>--columns</dt>
<dd>Spalten für die Anzeige, Optionen: guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. Standardwert: id,hostname,primary_ip,backend_ip,datacenter,action.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs list --domain bluemix.net --hourly --sortby memory
```
Dieser Befehl listet alle virtuellen Serverinstanzen mit stündlicher Abrechnung für das aktuelle Konto auf, gefiltert nach Domäne gleich "bluemix.net", und sortiert sie nach Speicher.

### ibmcloud sl vs pause
{: #sl_vs_pause}

Aktive virtuelle Serverinstanz anhalten.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs pause 12345678 -f
```
Dieser Befehl hält die virtuelle Serverinstanz mit der ID 12345678 an, ohne zu einer Bestätigung aufzufordern.

### ibmcloud sl vs power-off
{: #sl_vs_power_off}

Aktive virtuelle Serverinstanz ausschalten.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hard</dt>
<dd>Erzwungenen Systemabschluss durchführen.</dd>
<dt>--soft</dt>
<dd>Normalen Systemabschluss durchführen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs power-off 12345678 --soft
```
Dieser Befehl führt eine normale Abschaltung der virtuellen Serverinstanz mit der ID 12345678 durch.

### ibmcloud sl vs power-on
{: #sl_vs_power_on}

Virtuelle Serverinstanz einschalten.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs power-on 12345678
```
Dieser Befehl schaltet die virtuelle Serverinstanz mit der ID 12345678 ein.

### ibmcloud sl vs ready
{: #sl_vs_ready}

Prüfen, ob eine virtuelle Serverinstanz betriebsbereit ist.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--wait</dt>
<dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat, bevor Sie zurückkehren.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Dieser Befehl prüft den Status der virtuellen Serverinstanz mit der ID 12345678 darauf hin, ob sie durchgehend betriebsbereit ist, und wartet bis zu 30 Sekunden.

### ibmcloud sl vs reboot
{: #sl_vs_reboot}

Aktive virtuelle Serverinstanz neu starten.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hard</dt>
<dd>Kaltstart durchführen.</dd>
<dt>--soft</dt>
<dd>Warmstart durchführen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs reboot 12345678 --hard
```
Dieser Befehl führt einen Kaltstart für die virtuelle Serverinstanz mit der ID 12345678 durch.

### ibmcloud sl vs reload
{: #sl_vs_reload}

Betriebssystem auf virtueller Serverinstanz erneut laden.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Nachinstallationsscript herunterladen.</dd>
<dt>--image</dt>
<dd>Image-ID. Standardeinstellung ist die Verwendung des aktuellen Betriebssystems.</dd>
<dt>Siehe:</dt>
<dd>'ibmcloud sl image list' for reference.</dd>
<dt>-k, --key</dt>
<dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig).</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs reload 12345678
```
Dieser Befehl lädt das aktuelle Betriebssystem für die virtuelle Serverinstanz mit der ID 12345678 neu.

### ibmcloud sl vs rescue
{: #sl_vs_rescue}

Warmstart für virtuelle Serverinstanz in ein Wiederherstellungsimage durchführen.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONEN
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs rescue 12345678
```
Dieser Befehl startet die virtuelle Serverinstanz mit der ID 12345678 neu in ein Wiederherstellungsimage.

### ibmcloud sl vs resume
{: #sl_vs_resume}

Angehaltene virtuelle Serverinstanz wieder aufnehmen.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs resume 12345678
```
Dieser Befehl nimmt die virtuelle Serverinstanz mit der ID 12345678 wieder auf.

### ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Upgrade für eine virtuelle Serverinstanz durchführen.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Anzahl der CPU-Cores.</dd>
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
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Dieser Befehl führt ein Upgrade für die virtuelle Serverinstanz mit der ID 12345678 durch und legt die Anzahl der CPU-Cores auf 8, den Speicher auf 8192 M und die Übertragungsgeschwindigkeit des Netzports auf 1000 MT/s fest.
