---

copyright:

  years: 2016,2018


lastupdated: "2018-05-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
{: #softlayer_cli}

Le plug-in {{site.data.keyword.BluSoftlayer}} a été fusionné dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Vous n'avez plus besoin d'installer le plug-in.
{: tip}

Utilisez les commandes de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}} dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} pour configurer et gérer des services SoftLayer.

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.Bluemix_notm}} ont été changées de `bluemix` et `bx` en `ibmcloud`. Vous pouvez toutefois continuer à utiliser les commandes `bluemix` et `bx` jusqu'à ce qu'elles soient déclarées obsolètes.
{: tip}


Pour commencer, installez l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Voir
[Interface de ligne de commande IBM Cloud![External link icon](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} pour plus d'informations.

Pour la liste complète des commandes {{site.data.keyword.Bluemix_notm}}, voir : [Commandes {{site.data.keyword.Bluemix_notm}} (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)


## Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

Les commandes ci-après sont prises en charge. Utilisez la commande `ibmcloud sl` pour consulter la liste des commandes disponibles :

<table summary="Commandes générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## Commandes de stockage par blocs de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 2. Stockage par blocs de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Stockage par blocs de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

 ## Commandes CDN de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 3. Commandes CDN de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">CDN de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes de stockage de fichier de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 4. Stockage de fichier de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Stockage de fichier de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes DNS de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

<table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 5. Commandes DNS de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes DNS de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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


<table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 6. Commandes IP globales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes IP globales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes d'image de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 7. Commandes d'image de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes d'image de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

 ## Commandes VPN IPSec de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 7. Commandes VPN IPSec de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes VPN IPSec de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

 ## Commandes d'équilibreur de charge de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 8. Commandes d'équilibreur de charge de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes d'équilibreur de charge de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes de sécurité de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 9. Commandes de sécurité de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de sécurité de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes de sous-réseau de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 10. Commandes de sous-réseau de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de sous-réseau de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes de serveur virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 11. Commandes de serveur virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes de serveur virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Commandes de réseau local virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 12. Commandes de réseau local virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes de réseau local virtuel de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
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

### Syntaxe de la commande
Pour afficher les informations d'aide sur les commandes, exécutez : `ibmcloud sl [commande] -h`.

### ibmcloud sl init
{: #sl_init}

Permet d'initialiser les paramètres de configuration qui sont utilisés pour établir une connexion à l'environnement de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}. La configuration inclut un nom d'utilisateur, une clé d'API ou un mot de passe, un compte et un noeud final.
```
ibmcloud sl init [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL de noeud final d'API {{site.data.keyword.BluSoftlayer_notm}}, par défaut : https://api.softlayer.com/rest/v3.1 pour l'authentification par clé d'API, https://api.softlayer.com/mobile/v3.1 pour l'authentification par IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nom d'utilisateur Softlayer</dd>
<dt>-p, --sl-password</dt>
<dd>Mot de passe ou clé d'API Softlayer</dd>
<dt>-c, --account-id</dt>
<dd>ID de compte Softlayer</dd>
<dt>-q, --security-question-id</dt>
<dd>ID de question de sécurité utilisé pour l'authentification. Adressez-vous à votre propriétaire de compte si vous ne connaissez pas cet ID.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Réponse à la question de sécurité utilisée pour l'authentification. Adressez-vous à votre propriétaire de compte si vous connaissez pas cette réponse.</dd>
<dt>-s, --security-code</dt>
<dd>Code de sécurité généré par le fournisseur de sécurité lorsque l'authentification à deux facteurs est activée.</dd>
<dt>-v, --security-vendor</dt>
<dd>Fournisseur de sécurité qu fournit le code de sécurité pour l'authentification. Les options possibles sont : VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Jeton d'authentification lorsque l'authentification par téléphone est activée.</dd>
</dl>

Par exemple, connectez-vous à l'aide du nom d'utilisateur et du mot de passe ou de la clé d'API de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}.
```
$ ibmcloud sl config
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> wangjunl@cn.ibm.com
API key or password: []> abcd

Softlayer API endpoint:    https://api.softlayer.com/rest/v3.1
Account ID:                278444
User ID:                   wangjunl@cn.ibm.com
API Key:                   xxxxxxxxxx
```
Par exemple, utilisez {{site.data.keyword.Bluemix_notm}} Single-Sign-On pour vous connecter à Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account Wilma's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           wangjunl@cn.ibm.com   
Account:        Wilma's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'

Tip: use 'ibmcloud cf <command>' to run the Cloud Foundry CLI with {{site.data.keyword.Bluemix_notm}} CLI context.
```

```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On

Enter a number: 2
Softlayer API endpoint URL: [https://api.softlayer.com/mobile/v3.1]
Setting account to: 278444 OK

Softlayer API endpoint:    https://api.softlayer.com/mobile/v3.1
Account ID:                278444
User ID:                   12345678
IMS token:                 xxxxxxxxxx
```

### ibmcloud sl help
{: #sl_help}

Permet d'afficher des informations d'aide pour toutes les commandes exécutées dans un environnement d'infrastructure {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help

```

### ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Permet d'autoriser les hôtes à accéder à un volume donné.
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --hardware-id</dt>
<dd>ID d'un serveur matériel à autoriser.</dd>
<dt>-v, --virtual-id</dt>
<dd>ID d'un serveur virtuel à autoriser.</dd>
<dt>-i, --ip-address-id</dt>
<dd>ID d'une adresse IP à autoriser.</dd>
<dt>-p, --ip-address</dt>
<dd>Adresse IP à autoriser.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
Cette commande autorise le serveur virtuel portant l'ID 87654321 à accéder au volume portant l'ID 12345678.

### ibmcloud sl block access-list
{: #sl_block_access_list}

Permet de répertorier les ACL.
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Options d'affichage des colonnes : id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block access-list 12345678 --sortby id
```
Cette commande répertorie tous les hôtes qui sont autorisés à accéder au volume portant l'ID 12345678 et les trie par ID.

### ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Permet de révoquer l'autorisation des hôtes à accéder à un volume donné.
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --hardware-id</dt>
<dd>ID d'un serveur matériel à révoquer.</dd>
<dt>-v, --virtual-id</dt>
<dd>ID d'un serveur virtuel à révoquer.</dd>
<dt>-i, --ip-address-id</dt>
<dd>ID d'une adresse IP à révoquer.</dd>
<dt>-p, --ip-address</dt>
<dd>Adresse IP à révoquer.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Cette commande révoque l'accès du serveur virtuel portant l'ID 87654321 au volume portant l'ID 12345678.

### ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Permet d'effectuer une opération de reprise par restauration d'un volume de blocs à partir d'une réplique.
```
ibmcloud sl block replica-failback VOLUME_ID
```


**Exemples** :
```
ibmcloud sl block replica-failback 12345678
```
Cette commande effectue une opération de reprise par restauration du volume portant l'ID 12345678.

### ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Permet d'effectuer une opération de reprise en ligne d'un volume de blocs vers le volume de réplique donné.
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Exemples** :
```
ibmcloud sl block replica-failover 12345678 87654321
```
Cette commande effectue une opération de reprise en ligne du volume portant l'ID 12345678 vers le volume de réplique portant l'ID 87654321.

### ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Permet de répertorier les centres de données de réplication appropriés pour le volume indiqué.
```
ibmcloud sl block replica-locations VOLUME_ID
```


**Exemples** :
```
ibmcloud sl block replica-locations 12345678
```
Cette commande répertorie les centres de données de réplication appropriés pour le volume de blocs portant l'ID 12345678.

### ibmcloud sl block replica-order
{: #sl_block_replica_order}

Permet de commander un volume de réplique de stockage par blocs.
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Obligatoire. Planning d'instantané à utiliser pour la réplication. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données pour la réplique, par exemple, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume principal pour lequel une réplique est commandée. Les options possibles sont : 0.25,2,4,10. Si aucun niveau n'est spécifié, le niveau du volume d'origine sera utilisé.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100. Si aucune opération d'E-S n'est spécifiée, les opérations d'E-S du volume d'origine seront  utilisées.</dd>
<dt>-o, --os-type</dt>
<dd>Facultatif. Type de système d'exploitation (par exemple, LINUX) du volume principal pour lequel une réplique est commandée. Les options possibles sont : HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Cette commande permet de commander une réplique pour le volume portant l'ID 12345678. Il s'agit d'une réplication quotidienne (option DAILY), située sur dal09 avec le niveau 4 et le type de système d'exploitation Linux.

### ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Permet de répertorier les volumes réplicants existants pour un volume de blocs.
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**Exemples** :
```
ibmcloud sl block replica-partners 12345678
```
Cette commande répertorie les volumes réplicants existants pour le volume de blocs portant l'ID 12345678.

### ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Permet d'annuler l'espace d'image instantanée d'un volume donné.
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>--immediate</dt>
<dd>Annuler l'espace d'image instantanée immédiatement sans attendre la date anniversaire de la facturation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement l'image instantanée portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Permet de créer une image instantanée sur un volume donné.
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --note</dt>
<dd>Notes à définir sur la nouvelle image instantanée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforbluemix
```
Cette commande crée une image instantanée pour un volume portant l'ID 12345678 et avec la note d'ajout snapshotforbluemix.

### ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Permet de désactiver les images instantanées sur le planning spécifié pour un volume donné.
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatoire. Planning d'image instantanée. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
Cette commande désactive la prise d'image instantanée quotidienne pour le volume portant l'ID 12345678.

### ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Permet d'activer les images instantanées sur le planning spécifié pour un volume donné.
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatoire. Planning d'image instantanée. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Obligatoire. Nombre d'images instantanées à conserver.</dd>
<dt>-m, --minute</dt>
<dd>Minute de l'heure de la prise des images instantanées, entier compris entre 0 et 59.</dd>
<dt>-r, --hour</dt>
<dd>Heure du jour de la prise des images instantanées, entier compris entre 0 et 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Jour de la semaine de la prise des images instantanées, entier compris entre 0 et 6. 0 signifie dimanche, 1 signifie lundi, 2 signifie mardi, 3 signifie mercredi, 4 signifie jeudi, 5 signifie vendredi, 6 signifie samedi.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Cette commande active la prise d'image instantanée pour le volume portant l'ID 12345678. L'image instantanée est prise à 2 heures tous les dimanches, et jusqu'à 5 images instantanées sont retenues.

### ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Permet de supprimer une image instantanée sur un volume donné.
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Exemples** :
```
ibmcloud sl block snapshot-delete 12345678
```
Cette commande supprime une image instantanée portant l'ID 12345678.

### ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Permet de répertorier les images instantanées de stockage par blocs.
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,name,created,size_bytes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
Cette commande répertorie toutes les images instantanées du volume portant l'ID 12345678 et les trie par ID.

### ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Permet de commander l'espace d'image instantanée pour un volume de stockage par blocs.
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --size</dt>
<dd>Obligatoire. Taille, en Go, de l'espace d'image instantanée à créer.</dd>
<dt>-t, --tier</dt>
<dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume de stockage par blocs pour lequel de l'espace est commandé. Les options possibles sont : 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Indicateur permettant de signaler que la commande est une mise à niveau.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
Cette commande permet de commander de l'espace d'image instantanée pour le volume portant l'ID 12345678. La taille est de 1000 Go et le niveau est de 4 IOPS par Go.

### ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Permet de restaurer le volume de blocs à l'aide d'une image instantanée donnée.
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Exemples** :
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
Cette commande restaure un volume portant l'ID 12345678 à partir d'une image instantanée portant l'ID 87654321.

### ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Permet d'annuler un volume de stockage par blocs existant.
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>--immediate</dt>
<dd>Annuler le volume de stockage par blocs immédiatement sans attendre la date anniversaire de facturation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement le volume portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl block volume-list
{: #sl_block_volume_list}

Permet de répertorier le stockage par blocs.
```
ibmcloud sl block volume-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-u, --username</dt>
<dd>Filtrer par nom de volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrer par type de volume de stockage. Les options possibles sont les suivantes : performance et endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter le stockage par blocs.</dd>
<dt>--sortby</dt>
<dd>Les options de tri des colonnes sont les suivantes : id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Les options d'affichage des colonnes sont les suivantes : id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Cette commande répertorie tous les volumes d'endurance pour le compte en cours qui se trouvent sur dal09, et les trie par capacité.

### ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Permet d'afficher les détails relatifs à un volume spécifié.
```
ibmcloud sl block volume-detail VOLUME_ID
```


**Exemples** :
```
ibmcloud sl block volume-detail 12345678
```
Cette commande affiche les détails relatifs au volume portant l'ID 12345678.

### ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Permet de commander un volume de blocs en dupliquant un volume existant.
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID d'une image instantanée de volume d'origine à utiliser pour duplication.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Taille de volume de blocs en double, en Go. Si aucune taille n'est spécifiée, la taille du volume d'origine est utilisée.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100. Si aucune opération d'E-S n'est spécifiée, les opérations d'E-S du volume d'origine seront utilisées.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Niveau de stockage d'endurance. Si aucun niveau n'est spécifié, le niveau du volume d'origine sera utilisé.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Taille d'espace d'image instantanée à commander pour le doublon. Si aucune taille n'est spécifiée, la taille de l'espace d'image instantanée du volume d'origine est utilisée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block volume-duplicate 12345678
```
Cette commande permet d'afficher la commande d'un nouveau volume en dupliquant le volume portant l'ID 12345678.

### ibmcloud sl block volume-order
{: #sl_block_volume_order}

Permet de commander un volume de stockage par blocs.
```
ibmcloud sl block volume-order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-t, --storage-type</dt>
<dd>Obligatoire. Type de volume de stockage. Les options possibles sont les suivantes : performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Obligatoire. Taille du volume de stockage, en Go.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100 [obligatoires pour les performances de type stockage].</dd>
<dt>-e, --tier</dt>
<dd>Niveau de stockage d'endurance (IOP par Go) [obligatoire pour l'endurance de type stockage]. Les options possibles sont : 0.25,2,4,10.</dd>
<dt>-o, --os-type</dt>
<dd>Obligatoire. Système d'exploitation. Les options possibles sont les suivantes : HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé de centre de données.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Paramètre facultatif pour la commande d'espace d'image instantanée avec un stockage par blocs de type endurance ; indique la taille (en Go) de l'espace d'image instantanée à commander.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Cette commande permet de commander un volume de performance d'une taille de 1000 Go, dont le niveau IOPS est 4000, le type de système d'exploitation LINUX, et qui se trouve sur dal09.

### ibmcloud sl block volume-options
{: #sl_block_volume_options}

Permet de répertorier toutes les options pour la commande d'un stockage par blocs.
```
ibmcloud sl block volume-options
```


**Exemples** :
```
ibmcloud sl block volume-options
```
Cette commande répertorie toutes les options relatives à la création d'un volume de stockage par blocs, y compris le type de stockage, la taille de volume, le type de système d'exploitation, la valeur IOPS, le niveau, le centre de données et la taille d'image instantanée.

### ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Permet d'annuler un compte CDN.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
### ibmcloud sl cdn detail
{: #sl_cdn_detail}

Permet d'afficher les détails d'un compte CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
{: #sl_cdn_list}

Permet de répertorier tous les comptes CDN.
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande.</dd>
</dl>
### ibmcloud sl cdn load
{: #sl_cdn_load}

Permet de mettre en cache un ou plusieurs fichiers sur tous les noeuds périphériques.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

Permet de commander un compte CDN.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-b, --bandwidth</dt>
<dd>Bande passante CDN. 'Pay as You Go' sera utilisé si cette option n'est pas spécifiée.</dd>
<dt>-s, --storage</dt>
<dd>Stockage CDN. 'Pay as You Go' sera utilisé si cette option n'est pas spécifiée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
### ibmcloud sl cdn options
{: #sl_cdn_options}

Options de bande passante et de stockage pour la commande d'un compte CDN.
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Permet de créer un mappage d'extraction d'origine.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-t, --type</dt>
<dd>Type de support pour ce mappage (http, flash, wm, ...). La valeur par défaut est : http.</dd>
<dt>-c, --cname</dt>
<dd>Type d'enregistrement CNAME facultatif à joindre au mappage.</dd>
</dl>
### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Permet de répertorier les mappages d'extraction d'origine.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Permet de retirer un mappage d'extraction d'origine.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
### ibmcloud sl cdn purge
{: #sl_cdn_purge}

Permet de purger les fichiers mis en cache depuis tous les noeuds périphériques.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
### ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Permet d'autoriser les hôtes à accéder à un volume donné.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --hardware-id</dt>
<dd>ID d'un serveur matériel à autoriser.</dd>
<dt>-v, --virtual-id</dt>
<dd>ID d'un serveur virtuel à autoriser.</dd>
<dt>-i, --ip-address-id</dt>
<dd>ID d'une adresse IP à autoriser.</dd>
<dt>-p, --ip-address</dt>
<dd>Adresse IP à autoriser.</dd>
<dt>-s, --subnet-id</dt>
<dd>ID d'un sous-réseau à autoriser.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
Cette commande autorise le serveur virtuel portant l'ID 87654321 à accéder au volume portant l'ID 12345678.

### ibmcloud sl file access-list
{: #sl_file_access_list}

Permet de répertorier les ACL.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Options d'affichage des colonnes : id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file access-list 12345678 --sortby id
```
Cette commande répertorie tous les hôtes qui sont autorisés à accéder au volume portant l'ID 12345678 et les trie par ID.

### ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Permet de révoquer l'autorisation des hôtes à accéder à un volume donné.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --hardware-id</dt>
<dd>ID d'un serveur matériel à révoquer.</dd>
<dt>-v, --virtual-id</dt>
<dd>ID d'un serveur virtuel à révoquer.</dd>
<dt>-i, --ip-address-id</dt>
<dd>ID d'une adresse IP à révoquer.</dd>
<dt>-p, --ip-address</dt>
<dd>Adresse IP à révoquer.</dd>
<dt>-s, --subnet-id</dt>
<dd>ID d'un sous-réseau à révoquer.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
Cette commande révoque l'accès du serveur virtuel portant l'ID 87654321 au volume portant l'ID 12345678.

### ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Permet d'effectuer une reprise par restauration d'un volume de fichier depuis une réplique.
```
ibmcloud sl file replica-failback VOLUME_ID
```


**Exemples** :
```
ibmcloud sl file replica-failback 12345678
```
Cette commande effectue une opération de reprise par restauration du volume portant l'ID 12345678.

### ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Permet d'effectuer un basculement d'un volume de fichier dans le volume de réplique donné.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Exemples** :
```
ibmcloud sl file replica-failover 12345678 87654321
```
Cette commande effectue une opération de reprise en ligne du volume portant l'ID 12345678 vers le volume de réplique portant l'ID 87654321.

### ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Permet de répertorier les centres de données de réplication appropriés pour le volume indiqué.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Exemples** :
```
ibmcloud sl file replica-locations 12345678
```
Cette commande répertorie les centres de données de réplication appropriés pour le volume de fichier portant l'ID 12345678.

### ibmcloud sl file replica-order
{: #sl_file_replica_order}

Permet de commander un volume de réplique de stockage par blocs.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Obligatoire. Planning d'image instantanée à utiliser pour la réplication. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données pour la réplique, par exemple, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume principal pour lequel une réplique est commandée. Les options possibles sont : 0.25,2,4,10. Si aucun niveau n'est spécifié, le niveau du volume d'origine sera utilisé.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100. Si aucune opération d'E-S n'est spécifiée, les opérations d'E-S du volume d'origine seront  utilisées.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
Cette commande permet de commander une réplique pour le volume portant l'ID 12345678. Il s'agit d'une réplication quotidienne (option DAILY), située sur dal09 avec le niveau 4.

### ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Permet de répertorier les volumes réplicants existants pour un volume de blocs.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONS]
```


**Exemples** :
```
ibmcloud sl file replica-partners 12345678
```
Cette commande répertorie les volumes réplicants existants pour le volume de fichier portant l'ID 12345678.

### ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Permet d'annuler l'espace d'image instantanée d'un volume donné.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>--immediate</dt>
<dd>Annuler l'espace d'image instantanée immédiatement sans attendre la date anniversaire de la facturation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement l'image instantanée portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Permet de créer une image instantanée sur un volume donné.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --note</dt>
<dd>Notes à définir sur la nouvelle image instantanée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforbluemix
```
Cette commande crée une image instantanée pour un volume portant l'ID 12345678 et avec la note d'ajout snapshotforbluemix.

### ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Permet de désactiver les images instantanées sur le planning spécifié pour un volume donné.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatoire. Planning d'image instantanée. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
Cette commande désactive la prise d'image instantanée quotidienne pour le volume portant l'ID 12345678.

### ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Permet d'activer les images instantanées sur le planning spécifié pour un volume donné.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatoire. Planning d'image instantanée. Les options possibles sont : HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Obligatoire. Nombre d'images instantanées à conserver.</dd>
<dt>-m, --minute</dt>
<dd>Minute de l'heure de la prise des images instantanées, entier compris entre 0 et 59.</dd>
<dt>-r, --hour</dt>
<dd>Heure du jour de la prise des images instantanées, entier compris entre 0 et 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Jour de la semaine de la prise des images instantanées, entier compris entre 0 et 6. 0 signifie dimanche, 1 signifie lundi, 2 signifie mardi, 3 signifie mercredi, 4 signifie jeudi, 5 signifie vendredi, 6 signifie samedi.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Cette commande active la prise d'image instantanée pour le volume portant l'ID 12345678. L'image instantanée est prise à 2 heures tous les dimanches, et jusqu'à 5 images instantanées sont retenues.

### ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Permet de supprimer une image instantanée sur un volume donné.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**Exemples** :
```
ibmcloud sl file snapshot-delete 12345678
```
Cette commande supprime une image instantanée portant l'ID 12345678.

### ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Permet de répertorier les images instantanées de stockage de fichier.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,name,created,size_bytes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
Cette commande répertorie toutes les images instantanées du volume portant l'ID 12345678 et les trie par ID.

### ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Permet de commander l'espace d'image instantanée pour un volume de stockage de fichiers.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --size</dt>
<dd>Obligatoire. Taille, en Go, de l'espace d'image instantanée à créer.</dd>
<dt>-t, --tier</dt>
<dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume de fichier pour lequel de l'espace est commandé. Les options possibles sont : 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Indicateur permettant de signaler que la commande est une mise à niveau.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Cette commande permet de commander de l'espace d'image instantanée pour le volume portant l'ID 12345678. La taille est de 1000 Go et le niveau est de 4 IOPS par Go.

### ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Permet de restaurer le volume de fichier à l'aide d'une image instantanée donnée.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Exemples** :
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
Cette commande restaure un volume portant l'ID 12345678 à partir d'une image instantanée portant l'ID 87654321.

### ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Permet d'annuler un volume de stockage de fichiers existant.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>--immediate</dt>
<dd>Annuler le volume de stockage de fichiers immédiatement sans attendre la date anniversaire de facturation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement le volume portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl file volume-list
{: #sl_file_volume_list}

Permet de répertorier le stockage de fichiers.
```
ibmcloud sl file volume-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-u, --username</dt>
<dd>Filtrer par nom de volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrer par type de volume de stockage. Les options possibles sont les suivantes : performance et endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter le stockage de fichiers.</dd>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Options d'affichage des colonnes : id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Cette commande répertorie tous les volumes d'endurance pour le compte en cours qui se trouvent sur dal09, et les trie par capacité.

### ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Permet d'afficher les détails relatifs à un volume spécifié.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Exemples** :
```
ibmcloud sl file volume-detail 12345678
```
Cette commande affiche les détails relatifs au volume portant l'ID 12345678.

### ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Permet de commander un volume de fichiers en dupliquant un volume existant.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID d'une image instantanée de volume d'origine à utiliser pour duplication.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Taille de volume de fichier en double, en Go. Si aucune taille n'est spécifiée, la taille du volume d'origine est utilisée.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100. Si aucune opération d'E-S n'est spécifiée, les opérations d'E-S du volume d'origine seront utilisées.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Niveau de stockage d'endurance. Si aucun niveau n'est spécifié, le niveau du volume d'origine sera utilisé.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Taille d'espace d'image instantanée à commander pour le doublon. Si aucune taille n'est spécifiée, la taille de l'espace d'image instantanée du volume d'origine est utilisée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-duplicate 12345678
```
Cette commande permet d'afficher la commande d'un nouveau volume en dupliquant le volume portant l'ID 12345678.

### ibmcloud sl file volume-order
{: #sl_file_volume_order}

Permet de commander un volume de stockage de fichiers.
```
ibmcloud sl file volume-order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-t, --storage-type</dt>
<dd>Obligatoire. Type de volume de stockage. Les options possibles sont les suivantes : performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Obligatoire. Taille du volume de stockage, en Go.</dd>
<dt>-i, --iops</dt>
<dd>Opérations d'E-S du stockage de type performance, comprises entre 100 et 6000 en multiples de 100 [obligatoires pour les performances de type stockage].</dd>
<dt>-e, --tier</dt>
<dd>Niveau de stockage d'endurance (IOP par Go) [obligatoire pour l'endurance de type stockage]. Les options possibles sont : 0.25,2,4,10.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé de centre de données.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Paramètre facultatif pour la commande d'espace d'image instantanée avec le volume.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Cette commande permet de commander un volume de performance d'une taille de 1000 Go, dont le niveau IOPS est 4000, et qui se trouve sur dal09.

### ibmcloud sl file volume-options
{: #sl_file_volume_options}

Permet de répertorier toutes les options pour la commande d'un stockage par blocs.
```
ibmcloud sl file volume-options
```


**Exemples** :
```
ibmcloud sl file volume-options
```
Cette commande répertorie toutes les options relatives à la création d'un volume de stockage de fichiers, y compris le type de stockage, la taille de volume, la valeur IOPS, le niveau, le centre de données et la taille d'image instantanée.

### ibmcloud sl dns import
{: #sl_dns_import}

Permet d'importer une zone basée sur un fichier de zone BIND.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--dry-run</dt>
<dd>Indique de ne pas créer réellement d'enregistrements.</dd>
</dl>

**Exemples** :
```
ibmcloud sl dns import ~/blumix.net.txt
```
Cette commande importe une zone et ses enregistrements de ressource à partir d'un fichier : ~/blumix.net.txt.

### ibmcloud sl dns record-add
{: #sl_dns_record_add}

Permet d'ajouter un enregistrement de ressource dans une zone.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--ttl</dt>
<dd>Valeur de durée de vie, exprimée en secondes, par exemple : 86400. La valeur par défaut est 7200.</dd>
</dl>

**Exemples** :
```
ibmcloud sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Cette commande ajoute un enregistrement A à la zone bluemix.net. Son hôte est "ftp", ses données sont "127.0.0.1" et la valeur de durée de vie est de 86400 secondes.

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Permet de mettre à jour des enregistrements de ressource dans une zone.
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--by-record</dt>
<dd>Editer par enregistrement d'hôte, par exemple, www.</dd>
<dt>--by-id</dt>
<dd>Editer par ID d'enregistrement unique.</dd>
<dt>--data</dt>
<dd>Données d'enregistrement, par exemple, une adresse IP.</dd>
<dt>--ttl</dt>
<dd>Valeur de durée de vie, exprimée en secondes, par exemple : 86400.</dd>
</dl>

**Exemples** :
```
ibmcloud sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Cette commande édite des enregistrements sous la zone bluemix.net dont l'ID est 12345678, et affecte la valeur "127.0.0.2" au paramètre de données et la valeur 3600 au paramètre de durée de vie.

### ibmcloud sl dns record-list
{: #sl_dns_record_list}

Permet de répertorier tous les enregistrements de ressource d'une zone.
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--data</dt>
<dd>Filtrer par données d'enregistrement, par exemple, une adresse IP.</dd>
<dt>--record</dt>
<dd>Filtrer par enregistrement d'hôte, par exemple, www.</dd>
<dt>--ttl</dt>
<dd>Filtrer par valeur de durée de vie, exprimée en secondes, par exemple, 86400.</dd>
<dt>--type</dt>
<dd>Filtrer par type d'enregistrement, par exemple, A ou CNAME.</dd>
</dl>

**Exemples** :
```
ibmcloud sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Cette commande répertorie tous les enregistrements A sous la zone bluemix.net. La valeur du paramètre de filtrage par hôte est elasticsearch et la valeur du paramètre de durée de vie est 900 secondes.

### ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Permet de retirer un enregistrement de ressource d'une zone.
```
ibmcloud sl dns record-remove RECORD_ID
```


**Exemples** :
```
ibmcloud sl dns record-remove 12345678
```
Cette commande retire l'enregistrement de ressource portant l'ID 12345678.

### ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Permet de créer une zone.
```
ibmcloud sl dns zone-create ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-create bluemix.net
```
Cette commande crée une zone nommée bluemix.net.

### ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Permet de supprimer une zone.
```
ibmcloud sl dns zone-delete ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-delete bluemix.net
```
Cette commande supprime une zone nommée bluemix.net.

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Permet de répertorier toutes les zones sur votre compte.
```
ibmcloud sl dns zone-list
```


**Exemples** :
```
ibmcloud sl dns zone-list
```
Cette commande répertorie toutes les zones sous le compte en cours.

### ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Permet d'imprimer les enregistrements de ressource et de zone au format BIND.
```
ibmcloud sl dns zone-print ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-print bluemix.net
```
Cette commande imprime une zone nommée bluemix.net au format BIND.

### ibmcloud sl globalip create
{: #sl_globalip_create}

Permet de créer une adresse IP globale.
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--v6</dt>
<dd>Commandez une adresse IP IPv6.</dd>
<dt>--test</dt>
<dd>Indique qu'une commande doit être testée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip create --v6
```
Cette commande crée une adresse IP V6.

### ibmcloud sl globalip assign
{: #sl_globalip_assign}

Permet d'affecter une adresse IP globale à un routeur ou un périphérique cible.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Exemples** :
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
Cette commande affecte une adresse IP portant l'ID 12345678 à une unité cible dont l'adresse IP est 9.111.123.456.

### ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Permet d'annuler une adresse IP globale.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip cancel 12345678
```
Cette commande annule une adresse IP portant l'ID 12345678.

### ibmcloud sl globalip list
{: #sl_globalip_list}

Permet de répertorier toutes les adresses IP globale sur votre compte.
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--v4</dt>
<dd>Afficher uniquement les adresses IPv4.</dd>
<dt>--v6</dt>
<dd>Afficher uniquement les adresses IPv6.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter cette adresse IP.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip list --v4
```
Cette commande répertorie toutes les adresses IP V4 sur le compte en cours.

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Permet d'annuler l'affectation d'une adresse IP globale à partir d'un routeur ou d'un périphérique cible.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Exemples** :
```
ibmcloud sl globalip unassign 12345678
```
Cette commande annule l'affectation d'une adresse IP portant l'ID 12345678 à partir de l'unité cible.

### ibmcloud sl image delete
{: #sl_image_delete}

Permet de supprimer une image.
```
ibmcloud sl image delete IDENTIFIER
```
**Exemples** :
```
   ibmcloud sl image delete 12345678
```
Cette commande supprime l'image portant l'ID `12345678`.

### ibmcloud sl image detail
{: #sl_image_detail}

Permet d'obtenir les détails relatifs à une image.
```
ibmcloud sl image detail IDENTIFIER
```
**Exemples** :
```
 ibmcloud sl image detail 12345678
```
Cette commande permet d'obtenir les détails relatifs à l'image portant l'ID 12345678.

### ibmcloud sl image edit
{: #sl_image_edit}

Permet d'éditer les détails relatifs à une image.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--name</dt>
<dd>Nom de l'image.</dd>
<dt>--note</dt>
<dd>Note supplémentaire au sujet de l'image.</dd>
<dt>--tag</dt>
<dd>Etiquettes de l'image.</dd>
</dl>

*Exemples** :
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Cette commande édite l'image portant l'ID `12345678` en la nommant `ubuntu16` et en lui affectant la note `testing` ainsi que l'étiquette `staging`.

### ibmcloud sl image list
{: #sl_image_list}

Permet de répertorier toutes les images de votre compte.
```
ibmcloud sl image list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--name</dt>
<dd>Filtrer par nom d'image.</dd>
<dt>--public</dt>
<dd>Afficher uniquement les images publiques.</dd>
<dt>--private</dt>
<dd>Afficher uniquement les images privées.</dd>
</dl>

### ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Permet d'annuler un contexte de tunnel VPN IPSec.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--immediate</dt>
<dd>Annuler le contexte IPSec immédiatement sans attendre la date anniversaire de facturation.</dd>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl ipsec config
{: #sl_ipsec_config}

Permet de demander la configuration d'un contexte de tunnel.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

### ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Permet de répertorier les détails relatifs à un contexte de tunnel VPN IPSec.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-i, --include</dt>
<dd>Permet d'ajouter des ressources supplémentaires. Les options possibles sont les suivantes : at,is,rs,sr,ss.</dd>
</dl>
### ibmcloud sl ipsec list
{: #sl_ipsec_list}

Permet de répertorier les contextes de tunnel VPN IPSec.
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter le contexte IPSec.</dd>
</dl>
### ibmcloud sl ipsec order
{: #sl_ipsec_order}

Permet de commander un tunnel VPN IPSec.
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données pour IPSec, par exemple, dal09.</dd>
</dl>

### ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Permet d'ajouter un sous-réseau à un contexte de tunnel IPSEC.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificateur de sous-réseau à ajouter (obligatoire).</dd>
<dt>-t, --subnet-type</dt>
<dd>Type de sous-réseau à ajouter (obligatoire). Les options possibles sont les suivantes : internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>Identificateur de sous-réseau à créer.</dd>
</dl>

### ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Permet de retirer un sous-réseau d'un contexte de tunnel IPSEC.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

### ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Permet d'ajouter une conversion d'adresse à un tunnel IPSec.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --static-ip</dt>
<dd>Adresse IP statique (obligatoire).</dd>
<dt>-r, --remote-ip</dt>
<dd>Adresse IP distante (obligatoire).</dd>
<dt>-n, --note</dt>
<dd>Remarque.</dd>
</dl>
### ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Permet de retirer une entrée de conversion d'un tunnel IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

### ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Permet de mettre à jour une conversion d'adresse pour un tunnel IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --static-ip</dt>
<dd>Adresse IP statique (obligatoire).</dd>
<dt>-r, --remote-ip</dt>
<dd>Adresse IP distante (obligatoire).</dd>
<dt>-n, --note</dt>
<dd>Remarque.</dd>
</dl>
### ibmcloud sl ipsec update
{: #sl_ipsec_update}

Permet de mettre à jour des propriétés de contexte de tunnel.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --name</dt>
<dd>Nom usuel.</dd>
<dt>-r, --remote-peer</dt>
<dd>Adresse IP de l'homologue distant.</dd>
<dt>-k, --preshared-key</dt>
<dd>Clé pré-partagée.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Athentification phase 1. Les options possibles sont les suivantes : MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Chiffrement phase 1. Les options possibles sont les suivantes : DES,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Groupe diffie hellman phase 1. Les options possibles sont les suivantes : 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Durée de vie de la clé phase 1. Les valeurs possibles sont comprises entre 120 et 172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Athentification phase 2. Les options possibles sont les suivantes : MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Chiffrement phase 2. Les options possibles sont les suivantes : DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Groupe diffie hellman phase 2. Les options possibles sont les suivantes : 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Confidentialité de transmission parfaite phase 2. Les valeurs possibles sont comprises entre 0 et 1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Durée de vie de la clé phase 2. Les valeurs possibles sont comprises entre 120 et 172800.</dd>
</dl>

### ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Permet d'annuler un équilibreur de charge existant.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

Permet d'ajouter un équilibreur de charge en fonction de l'id renvoyé par create-options.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Permet d'obtenir les options tarifaires afin de créer un équilibreur de charge.
```
ibmcloud sl loadbal create-options
```

### ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Permet d'obtenir les détails relatifs à un équilibreur de charge.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

### ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Permet d'ajouter un nouveau service load_balancer.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --allocation</dt>
<dd>Obligatoire. Pourcentage de connexions alloué.</dd>
<dt>-p, --port</dt>
<dd>Obligatoire. Numéro de port.</dd>
<dt>-t, --routing-type</dt>
<dd>Obligatoire. ID du type de routage. Exécutez 'ibmcloud sl loadbal routing-types' pour rechercher un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Obligatoire. ID de la méthode de routage. Exécutez 'ibmcloud sl loadbal routing-methods' pour rechercher un ID.</dd>
</dl>

### ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Permet de supprimer un groupe de services d'équilibreur de charge existant.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Permet d'éditer un groupe de services d'équilibreur de charge existant.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --allocation</dt>
<dd>Modifiez le pourcentage de connexions alloué.</dd>
<dt>-p, --port</dt>
<dd>Modifiez le numéro de port.</dd>
<dt>-t, --routing-type</dt>
<dd>Modifiez l'ID du type de routage. Exécutez 'ibmcloud sl loadbal routing-types' pour rechercher un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Modifiez l'ID de la méthode de routage. Exécutez 'ibmcloud sl loadbal routing-methods' pour rechercher un ID.</dd>
</dl>

### ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Permet de réinitialiser des connexions sur un groupe de services donné.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Permet de répertorier les types de diagnostic d'intégrité.
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

Permet de répertorier les équilibreurs de charge actifs.
```
ibmcloud sl loadbal list
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter l'équilibreur de charge.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtrer par adresse IP.</dd>
</dl>
### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Permet de répertorier les méthodes de routage.
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Permet de répertorier les types de routage.
```
ibmcloud sl loadbal routing-types
```

### ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Permet d'ajouter un nouveau service d'équilibreur de charge.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--disabled</dt>
<dd>Facultatif. Créer le service comme désactivé, il est activé par défaut si cette option n'est pas sélectionnée.</dd>
<dt>-p, --port</dt>
<dd>Obligatoire. Numéro de port du service.</dd>
<dt>-w, --weight</dt>
<dd>Obligatoire. Poids du service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Obligatoire. Type de diagnostic d'intégrité.</dd>
<dt>-i, --ip-address</dt>
<dd>Obligatoire. Adresse IP du service.</dd>
</dl>

### ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Permet de supprimer un service d'équilibreur de charge existant.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Permet d'éditer les propriétés d'un groupe de services.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--disabled</dt>
<dd>Désactivez le service.</dd>
<dt>--enabled</dt>
<dd>Activez le service.</dd>
<dt>-p, --port</dt>
<dd>Modifiez le numéro de port du service.</dd>
<dt>-w, --weight</dt>
<dd>Modifiez le poids du service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Modifiez le type de diagnostic d'intégrité.</dd>
<dt>-i, --ip-address</dt>
<dd>Modifiez l'adresse IP du service.</dd>
</dl>

### ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Permet de basculer le statut d'un service d'équilibreur de charge existant.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

### ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Permet d'ajouter une nouvelle clé SSH.
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --in-file</dt>
<dd>Fichier id_rsa.pub à importer pour cette clé.</dd>
<dt>-k, --key</dt>
<dd>Clé SSH réelle.</dd>
<dt>--note</dt>
<dd>Note supplémentaire qui sera associée à la clé.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Cette commande ajoute une clé SSH à partir d'un fichier : ~/.ssh/id_rsa.pub with a note "mykey".

### ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Permet d'éditer une clé SSH.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--label</dt>
<dd>Nouveau libellé de la clé.</dd>
<dt>--note</dt>
<dd>Nouvelles notes pour la clé.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Cette commande met à jour la clé SSH portant l'ID 12345678 et lui affecte le libellé "Bluemix" et la note "testing".

### ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

Permet de répertorier les clés SSH sur votre compte.
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,label,fingerprint,notes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-list --sortby label
```
Cette commande répertorie toutes les clés SSH sur le compte en cours et les trie par libellé.

### ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Permet d'imprimer une clé SSH sur l'écran.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --out-file</dt>
<dd>La clé SSH publique sera écrite sur ce fichier.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
Cette commande affiche l'ID, le libellé et les notes de la clé SSH portant l'ID 12345678 et écrit la clé publique dans le fichier : ~/mykey.pub.

### ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Permet de retirer définitivement une clé SSH.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-remove 12345678 -f
```
Cette commande retire la clé SSH portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl security cert-add
{: #sl_security_cert_add}

Permet d'ajouter et de télécharger les détails relatifs au certificat SSL.
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--crt</dt>
<dd>Fichier de certificat.</dd>
<dt>--csr</dt>
<dd>Fichier de demande de signature de certificat.</dd>
<dt>--icc</dt>
<dd>Fichier de certificat intermédiaire.</dd>
<dt>--key</dt>
<dd>Fichier de clé privée.</dd>
<dt>--notes</dt>
<dd>Notes supplémentaires.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key
```
Cette commande ajoute le fichier certificat ~/bluemix.net.cert et le fichier de clé privée ~/bluemix.net.key pour le domaine bluemix.net.

### ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Permet d'éditer un certificat SSL.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--crt</dt>
<dd>Fichier de certificat.</dd>
<dt>--csr</dt>
<dd>Fichier de demande de signature de certificat.</dd>
<dt>--icc</dt>
<dd>Fichier de certificat intermédiaire.</dd>
<dt>--key</dt>
<dd>Fichier de clé privée.</dd>
<dt>--notes</dt>
<dd>Notes supplémentaires.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-edit 12345678 --key ~/bluemix.net.key
```
Cette commande édite le certificat portant l'ID 12345678 et met à jour sa clé privée avec le fichier ~/bluemix.net.key.

### ibmcloud sl security cert-download
{: #sl_security_cert_download}

Permet de télécharger des fichiers de certificat et de clé SSL.
```
ibmcloud sl security cert-download IDENTIFIER
```


**Exemples** :
```
ibmcloud sl security cert-download 12345678
```
Cette commande télécharge 4 fichiers sur le répertoire de travail pour le certificat portant l'ID 12345678. Ces 4 fichiers sont : le fichier certificat, le fichier de demande de signature de certificat, le fichier de certificat intermédiaire et le fichier de clé privée.

### ibmcloud sl security cert-list
{: #sl_security_cert_list}

Permet de répertorier les certificats SSL présents sur votre compte.
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--status</dt>
<dd>Afficher les certificats avec ce statut. La valeur par défaut est all, les options possibles sont les suivantes : all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,common_name,days_until_expire,notes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Cette commande répertorie tous les certificats valides sur le compte en cours et les trie par jours de validité.

### ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Permet de retirer un certificat SSL.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-remove 12345678
```
Cette commande retire le certificat portant l'ID 12345678.

### ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Permet d'annuler un sous-réseau.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl subnet cancel 12345678 -f
```
Cette commande annule le sous-réseau portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl subnet create
{: #sl_subnet_create}

Permet d'ajouter un nouveau sous-réseau à votre compte.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--v6, --ipv6</dt>
<dd>Commander uniquement des adresses IPv6.</dd>
<dt>--test</dt>
<dd>Ne pas commander le sous-réseau, mais demander uniquement un devis.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl subnet create public 16 567
```
Cette commande crée un sous-réseau public avec 16 adresses IPv4 et le place sur le réseau local virtuel portant l'ID 567.

### ibmcloud sl subnet detail
{: #sl_subnet_detail}

Permet d'obtenir les détails relatifs à un sous-réseau.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--no-vs</dt>
<dd>Masquer la liste de serveurs virtuels.</dd>
<dt>--no-hardware</dt>
<dd>Masquer la liste de serveurs matériels.</dd>
</dl>

**Exemples** :
```
ibmcloud sl subnet detail 12345678
```
Cette commande affiche des informations détaillées sur le sous-réseau portant l'ID 12345678, y compris les informations sur les serveurs virtuels et les serveurs matériels.

### ibmcloud sl subnet list
{: #sl_subnet_list}

Permet de répertorier tous les sous-réseaux présents sur votre compte.
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Colonne à trier. Options possibles : id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>--identifier</dt>
<dd>Filtrer par identificateur de réseau.</dd>
<dt>-t, --subnet-type</dt>
<dd>Filtrer par type de sous-réseau.</dd>
<dt>--network-space</dt>
<dd>Filtrer par espace réseau.</dd>
<dt>--v4, --ipv4</dt>
<dd>Afficher uniquement les sous-réseaux IPv4.</dd>
<dt>--v6, --ipv6</dt>
<dd>Afficher uniquement les sous-réseaux IPv6.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter les sous-réseaux.</dd>
</dl>

**Exemples** :
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Cette commande répertorie les sous-réseaux IPv4 sur le compte en cours avec le centre de données dal09, le type de sous-réseau PRIMARY et l'espace de sous-réseau PUBLIC.

### ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

Permet de rechercher une adresse IP et afficher les informations relatives au sous-réseau et aux périphériques associés.
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**Exemples** :
```
ibmcloud sl subnet lookup 9.125.235.255
```
Cette commande recherche l'enregistrement d'adresse IP portant l'adresse 9.125.235.255 et affiche ses informations de sous-réseau et d'unité.

### ibmcloud sl vlan create
{: #sl_vlan_create}

Permet de créer un nouveau réseau local virtuel.
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-t, --vlan-type</dt>
<dd>Type de VLAN, public ou privé.</dd>
<dt>-r, --router</dt>
<dd>Nom d'hôte du routeur.</dd>
<dt>-d, --datacenter</dt>
<dd>Nom abrégé du centre de données.</dd>
<dt>-s, --size</dt>
<dd>Taille des sous-réseaux. Options possibles : 8 (5 adresses IP utilisables) ou 16 (13 adresses IP utilisables) ou 32 (29 adresses IP utilisables).</dd>
<dt>-n, --name</dt>
<dd>Nom du réseau local virtuel.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Cette commande crée un réseau local virtuel public sur le centre de données dal09 avec 16 adresses IP, et lui affecte le nom myvlan.

### ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Permet d'annuler un réseau local virtuel.
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan cancel 12345678 -f
```
Cette commande annule le réseau local virtuel portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl vlan detail
{: #sl_vlan_detail}

Permet d'obtenir les détails relatifs à un réseau local virtuel.
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--no-vs</dt>
<dd>Masquer la liste de serveurs virtuels.</dd>
<dt>--no-hardware</dt>
<dd>Masquer la liste de serveurs matériels.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
Cette commande affiche les détails relatifs au réseau local virtuel portant l'ID 12345678 mais n'indique pas le serveur virtuel ou le serveur matériel.

### ibmcloud sl vlan edit
{: #sl_vlan_edit}

Permet d'éditer les détails relatifs à un réseau local virtuel.
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --name</dt>
<dd>Nom du réseau local virtuel.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
Cette commande met à jour le réseau local virtuel portant l'ID 12345678 et lui affecte le nouveau nom "myvlan-rename".

### ibmcloud sl vlan list
{: #sl_vlan_list}

Permet de répertorier tous les réseaux locaux virtuels présents sur votre compte.
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Les options de tri des colonnes sont les suivantes : id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-n, --number</dt>
<dd>Filtrer par numéro de réseau local virtuel.</dd>
<dt>--name</dt>
<dd>Filtrer par nom de réseau local virtuel.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter le réseau local virtuel.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Cette commande répertorie tous les réseaux locaux virtuels sur le compte en cours pour le centre de données dal09, et les trie par numéro de réseau local virtuel.

### ibmcloud sl vlan options
{: #sl_vlan_options}

Permet de répertorier toutes les options de création de réseau local virtuel.
```
ibmcloud sl vlan options
```


**Exemples** :
```
ibmcloud sl vlan options
```
Cette commande répertorie toutes les options de création d'un réseau local virtuel, par exemple, type de réseau local virtuel, centre de données, taille de sous-réseau, routeurs, etc.

### ibmcloud sl vs cancel
{: #sl_vs_cancel}

Permet d'annuler une instance de serveur virtuel.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs cancel 12345678
```
Cette commande annule l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs capture
{: #sl_vs_capture}

Permet de capturer une instance de serveur virtuel dans une image.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --name</dt>
<dd>Obligatoire. Nom de l'image.</dd>
<dt>--all</dt>
<dd>Capturer tous les disques appartenant au serveur virtuel.</dd>
<dt>--note</dt>
<dd>Ajouter une note à associer à l'image.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs capture 12345678 -n mybluemix --all --note testing
```
Cette commande capture l'instance de serveur virtuel portant l'ID 12345678 avec tous les disques dans une image nommée "mybluemix" et la note "testing".

### ibmcloud sl vs create
{: #sl_vs_create}

Permet de créer une instance de serveur virtuel.
```
ibmcloud sl vs create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-H, --hostname</dt>
<dd>Obligatoire. Partie hôte du nom de domaine complet.</dd>
<dt>-D, --domain</dt>
<dd>Obligatoire. Partie domaine du nom de domaine complet.</dd>
<dt>-c, --cpu</dt>
<dd>Obligatoire. Nombre de coeurs d'UC.</dd>
<dt>-m, --memory</dt>
<dd>Obligatoire. Mémoire, exprimée en mégaoctets.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données.</dd>
<dt>-o, --os</dt>
<dd>Code d'installation du système d'exploitation. Astuce : vous pouvez spécifier <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>ID image. Voir : 'ibmcloud sl image list' pour référence.</dd>
<dt>--billing</dt>
<dd>Taux de facturation. Par défaut : hourly. Options : hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Créer un serveur virtuel dédié (noeud privé).</dd>
<dt>--san</dt>
<dd>Utiliser le stockage SAN à la place d'un disque local.</dd>
<dt>--test</dt>
<dd>Ne pas créer le serveur virtuel.</dd>
<dt>--export</dt>
<dd>Exporte les options vers un fichier modèle.</dd>
<dt>-i, --postinstall</dt>
<dd>Script de post-installation à télécharger.</dd>
<dt>-k, --key</dt>
<dd>ID des clés SSH à ajouter à l'utilisateur root (plusieurs occurrences autorisées).</dd>
<dt>--disk</dt>
<dd>Tailles de disque (plusieurs occurrences autorisées).</dd>
<dt>--private</dt>
<dd>Force le serveur virtuel à n'avoir accès qu'au réseau privé.</dd>
<dt>--like</dt>
<dd>Utiliser la configuration d'un serveur virtuel existant.</dd>
<dt>-n, --network</dt>
<dd>Vitesse du port réseau, exprimée en Mbit/s.</dd>
<dt>--tag</dt>
<dd>Etiquettes à ajouter à l'instance (plusieurs occurrences autorisées).</dd>
<dt>-t, --template</dt>
<dd>Fichier modèle qui indique les options de ligne de commande par défaut.</dd>
<dt>-u, --userdata</dt>
<dd>Chaîne de métadonnées définie par l'utilisateur.</dd>
<dt>-F, --userfile</dt>
<dd>Lire les données utilisateur à partir du fichier.</dd>
<dt>--vlan-public</dt>
<dd>ID du VLAN public sur lequel vous voulez placer le serveur virtuel.</dd>
<dt>--vlan-private</dt>
<dd>ID du VLAN privé sur lequel vous voulez placer le serveur virtuel.</dd>
<dt>--wait</dt>
<dd>Attendre pendant X secondes au maximum que le serveur virtuel soit mis à disposition avant de revenir.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Cette commande permet de commander une instance de serveur virtuel dont le nom d'hôte (hostname) est myvsi, le domaine (domain) bluemix.net, qui comporte 4 coeurs d'UC, 4096 Mo de mémoire, qui se trouve sur le centre de données dal10

### ibmcloud sl vs options
{: #sl_vs_options}

Permet de répertorier les options de création de l'instance de serveur virtuel.
```
ibmcloud sl vs options [OPTIONS]
```


**Exemples** :
```
ibmcloud sl vs options
```
Cette commande répertorie toutes les options de création d'une instance de serveur virtuel, par exemple, datacenters, cpu, memory, os, disk, network speed, etc.

### ibmcloud sl vs credentials
{: #sl_vs_credentials}

Permet de répertorier les données d'identification de l'instance de serveur virtuel.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**Exemples** :
```
ibmcloud sl vs credentials 12345678
```
Cette commande répertorie toutes les paires nom d'utilisateur-mot de passe d'une instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs detail
{: #sl_vs_detail}

Permet d'obtenir les détails relatifs à une instance de serveur virtuel.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--passwords</dt>
<dd>Afficher les mots de passe (à l'abri des regards).</dd>
<dt>--price</dt>
<dd>Afficher les prix associés.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs details 12345678
```
Cette commande répertorie des informations détaillées sur l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Permet de synchroniser les enregistrements DNS pour une instance de serveur virtuel.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --a-record</dt>
<dd>Synchroniser l'enregistrement A pour l'hôte.</dd>
<dt>--aaaa-record</dt>
<dd>Synchroniser l'enregistrement AAAA pour l'hôte.</dd>
<dt>--ptr</dt>
<dd>Synchroniser l'enregistrement PTR pour l'hôte.</dd>
<dt>--ttl</dt>
<dd>Définit la durée de vie des enregistrements A et/ou PTR. Valeur par défaut : 7200</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Cette commande synchronise l'enregistrement A (adresse IPv4) de l'instance de serveur virtuel portant l'ID 12345678 avec le serveur DNS et affecte la valeur 3600 au paramètre de durée de vie de cet enregistrement A.

### ibmcloud sl vs edit
{: #sl_vs_edit}

Permet d'éditer les détails relatifs à une instance de serveur virtuel.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-D, --domain</dt>
<dd>Partie domaine du nom de domaine complet.</dd>
<dt>-H, --hostname</dt>
<dd>Portion hôte du nom de domaine complet. Exemple : server</dd>
<dt>--tag</dt>
<dd>Etiquettes à définir ou chaîne vide pour tout retirer.</dd>
<dt>-u, --userdata</dt>
<dd>Chaîne de métadonnées définie par l'utilisateur.</dd>
<dt>-F, --userfile</dt>
<dd>Lire les données utilisateur à partir du fichier.</dd>
<dt>--public-speed</dt>
<dd>Vitesse de port public. Les options possibles sont les suivantes : 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Vitesse de port privé. Les options possibles sont les suivantes : 0,10,100,1000,10000.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Cette commande met à jour l'instance de serveur virtuel portant l'ID 12345678 et lui affecte la valeur "bluemix.net" comme domaine, la valeur "myapp" comme nom d'hôte et la valeur "testcli" comme étiquette

### ibmcloud sl vs list
{: #sl_vs_list}

Permet de répertorier les instances de serveur virtuel sur votre compte.
```
ibmcloud sl vs list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-c, --cpu</dt>
<dd>Nombre de coeurs d'UC.</dd>
<dt>-D, --domain</dt>
<dd>Partie domaine du nom de domaine complet.</dd>
<dt>-d, --datacenter</dt>
<dd>Nom abrégé du centre de données.</dd>
<dt>-H, --hostname</dt>
<dd>Portion hôte du nom de domaine complet.</dd>
<dt>-m, --memory</dt>
<dd>Mémoire, exprimée en mégaoctets.</dd>
<dt>-n, --network</dt>
<dd>Vitesse du port réseau, exprimée en Mbit/s.</dd>
<dt>--hourly</dt>
<dd>Afficher uniquement les instances horaires.</dd>
<dt>--monthly</dt>
<dd>Afficher uniquement les instances mensuelles.</dd>
<dt>--tag</dt>
<dd>Filtrer par étiquettes (plusieurs occurrences autorisées).</dd>
<dt>--sortby</dt>
<dd>Les options de tri des colonnes sont les suivantes : id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Valeur par défaut : hostname.</dd>
<dt>--columns</dt>
<dd>Les options d'affichage des colonnes sont les suivantes : guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. Valeur par défaut : id,hostname,primary_ip,backend_ip,datacenter,action.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs list --domain bluemix.net --hourly --sortby memory
```
Cette commande répertorie toutes les instances de serveur virtuel facturées à l'heure sur le compte en cours, avec comme nom de domaine "bluemix.net", et les trie par mémoire.

### ibmcloud sl vs pause
{: #sl_vs_pause}

Permet de mettre en pause une instance de serveur virtuel active.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs pause 12345678 -f
```
Cette commande met en pause l'instance de serveur virtuel portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl vs power-off
{: #sl_vs_power_off}

Permet de mettre hors tension une instance de serveur virtuel active.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--hard</dt>
<dd>Effectuer un arrêt immédiat.</dd>
<dt>--soft</dt>
<dd>Effectuer un arrêt graduel.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs power-off 12345678 --soft
```
Cette commande effectue une mise hors tension graduelle pour l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs power-on
{: #sl_vs_power_on}

Permet de mettre sous tension une instance de serveur virtuel.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs power-on 12345678
```
Cette commande effectue une mise sous tension pour l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs ready
{: #sl_vs_ready}

Permet de vérifier si une instance de serveur virtuel est prête à être utilisée.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--wait</dt>
<dd>Attendre pendant X secondes au maximum que le serveur virtuel soit mis à disposition avant de revenir.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs ready 12345678 --wait 30
```
Cette commande vérifie le statut de l'instance de serveur virtuel portant l'ID 12345678 pour voir si elle est prête pour une utilisation en continu, et attend pendant 30 secondes au maximum.

### ibmcloud sl vs reboot
{: #sl_vs_reboot}

Permet de réamorcer une instance de serveur virtuel active.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--hard</dt>
<dd>Effectuer un réamorçage immédiat.</dd>
<dt>--soft</dt>
<dd>Effectuer un réamorçage graduel.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs reboot 12345678 --hard
```
Cette commande effectue un réamorçage immédiat pour l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs reload
{: #sl_vs_reload}

Permet de recharger le système d'exploitation sur une instance de serveur virtuel.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de post-installation à télécharger.</dd>
<dt>--image</dt>
<dd>ID image. Par défaut, il convient d'utiliser le système d'exploitation en cours.</dd>
<dt>Voir :</dt>
<dd>'ibmcloud sl image list' for reference.</dd>
<dt>-k, --key</dt>
<dd>ID des clés SSH à ajouter à l'utilisateur root (plusieurs occurrences autorisées).</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs reload 12345678
```
Cette commande recharge le système d'exploitation en cours pour l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs rescue
{: #sl_vs_rescue}

Permet de réamorcer une instance de serveur serveur dans une image de secours.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs rescue 12345678
```
Cette commande réamorce l'instance de serveur virtuel portant l'ID 12345678 dans une image de secours.

### ibmcloud sl vs resume
{: #sl_vs_resume}

Permet de reprendre une instance de serveur virtuel mise en pause.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs resume 12345678
```
Cette commande effectue la reprise de l'instance de serveur virtuel portant l'ID 12345678.

### ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Permet de mettre à niveau une instance de serveur virtuel.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-c, --cpu</dt>
<dd>Nombre de coeurs d'UC.</dd>
<dt>--private</dt>
<dd>Le coeur d'UC sera sur un serveur hôte dédié.</dd>
<dt>-m, --memory</dt>
<dd>Mémoire, exprimée en mégaoctets.</dd>
<dt>--network</dt>
<dd>Vitesse du port réseau, exprimée en Mbit/s.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Cette commande met à niveau l'instance de serveur virtuel portant l'ID 12345678 et lui affecte la valeur 8 comme nombre de coeurs d'UC, la valeur 8192 Mo comme mémoire et la valeur 1000 Mbit/s comme vitesse de port réseau.
