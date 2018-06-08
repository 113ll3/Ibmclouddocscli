---

copyright:

  years: 2016,2018


lastupdated: "2018-05-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.BluSoftlayer_notm}} infraestrutura (sl ibmcloud) comandos
{: #softlayer_cli}

O plug-in do {{site.data.keyword.BluSoftlayer}} foi mesclado na
CLI do {{site.data.keyword.Bluemix_notm}}. Não é mais necessário instalar o plug-in.
{: tip}

Use os comandos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}} na interface da linha de comandos (CLI) do {{site.data.keyword.Bluemix_notm}} para configurar e gerenciar os serviços do SoftLayer.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.Bluemix_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que eles sejam descontinuados em uma data posterior.
{: tip}


Para iniciar, instale o {{site.data.keyword.Bluemix_notm}} CLI. Veja
[IBM Cloud CLI ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} para obter detalhes.

Para obter uma lista completa de comandos do {{site.data.keyword.Bluemix_notm}}, veja: [Comandos do {{site.data.keyword.Bluemix_notm}} (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)


## Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}

Os comandos a seguir são compatíveis. Use o comando `ibmcloud sl` para ver a lista de comandos disponíveis:

<table summary="Comandos gerais ordenados alfabeticamente que possuem links que levam a mais informações sobre o comando">
<caption>Tabela 1. Comandos gerais de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## Comandos de armazenamento de bloco de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 2. Armazenamento de bloco de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Armazenamento de bloco de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[Ibmcloud sl block replica-locations](/docs/cli/reference/softlayer/index.html#sl_block_replica_locations)</td>
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
  <td>[Ibmcloud sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[ibmcloud sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
   </tr>
 <tr>
   <td>[ibmcloud sl block volume-duplicados](/docs/cli/reference/softlayer/index.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

 ## Comandos CDN de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 3. CDN de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">CDN de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/softlayer/index.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/softlayer/index.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/softlayer/index.html#sl_cdn_list)</td>
  <td>[Sl cdn load ibmcloud](/docs/cli/reference/softlayer/index.html#sl_cdn_load)</td>
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

## Comandos de armazenamento de arquivos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 4. Armazenamento de arquivos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Armazenamento de arquivos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl file access-authorize](/docs/cli/reference/softlayer/index.html#sl_file_access_authorize)</td>
  <td>[ibmcloud sl file access-list](/docs/cli/reference/softlayer/index.html#sl_file_access_list)</td>
  <td>[ibmcloud sl file access-revoke](/docs/cli/reference/softlayer/index.html#sl_file_access_revoke)</td>
  <td>[Ibmcloud sl file replica-failback](/docs/cli/reference/softlayer/index.html#sl_file_replica_failback)</td>
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
  <td>[Ibmcloud sl file snapshot-list](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_list)</td>
  <td>[ibmcloud sl file snapshot-order](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_order)</td>
  <td>[ibmcloud sl file snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_file_snapshot_restore)</td>
  <td>[ibmcloud sl file volume-cancel](/docs/cli/reference/softlayer/index.html#sl_file_volume_cancel)</td>  
  <td>[ibmcloud sl file volume-detail](/docs/cli/reference/softlayer/index.html#sl_file_volume_detail)</td>
   </tr>
 <tr>
   <td>[ibmcloud sl file volume-duplicados](/docs/cli/reference/softlayer/index.html#sl_file_volume_duplicate)</td>
   <td>[ibmcloud sl file volume-list](/docs/cli/reference/softlayer/index.html#sl_file_volume_list)</td>
   <td>[ibmcloud sl file volume-order](/docs/cli/reference/softlayer/index.html#sl_file_volume_order)</td>
   <td>[ibmcloud sl file volume-options](/docs/cli/reference/softlayer/index.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>

## Comandos DNS de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

<table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 5. Comandos DNS de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos DNS de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[Ibmcloud sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
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


<table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 6. Comandos de IP global de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos de IP global de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[Ibmcloud sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>

## Comandos de imagem de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 7. Comandos de imagem de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos de imagem de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
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

 ## Comandos VPN de IPSec de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 7. Comandos VPN de IPSec de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos VPN de IPSec de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl ipsec cancel](/docs/cli/reference/softlayer/index.html#sl_ipsec_cancel)</td>
 <td>[ibmcloud sl ipsec config](/docs/cli/reference/softlayer/index.html#sl_ipsec_config)</td>
 <td>[ibmcloud sl ipsec detail](/docs/cli/reference/softlayer/index.html#sl_ipsec_detail)</td>
 <td>[Sl ipsec list ibmcloud](/docs/cli/reference/softlayer/index.html#sl_ipsec_list)</td>
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

 ## Comandos de balanceador de carga de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 8. Comandos do balanceador de carga de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos de balanceador de carga de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/softlayer/index.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/softlayer/index.html#sl_loadbal_create)</td>
 <td>[Ibmcloud sl loadbal create-options](/docs/cli/reference/softlayer/index.html#sl_loadbal_create_options)</td>
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
 <td>[Ibmcloud sl loadbal service-add](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

## Comandos de segurança de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 9. Comandos de segurança de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="5">Comandos de segurança de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
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
  <td>[Ibmcloud sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

## Comandos da sub-rede de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 10. Comandos da sub-rede de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="5">Comandos da sub-rede de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</th>
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

## Comandos do servidor virtual de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 11. Comandos do servidor virtual de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos do servidor virtual de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[Sl vs capture ibmcloud](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
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
 <td>[Sl vs power-ibmcloud](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
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

## Comandos da VLAN de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 12. Comandos da VLAN de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos da VLAN de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[Sl vlan edit ibmcloud](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### Uso do comando
Para visualizar informações da ajuda para os comandos, execute: `ibmcloud sl [command] -h`.

### Ibmcloud sl init
{: #sl_init}

Inicializar as definições de configuração que são usadas para se conectar ao ambiente de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}. A configuração inclui o nome do usuário, a chave API ou a senha, a conta e o terminal.
```
Ibmcloud sl init [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL do terminal de API da infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}, o padrão é: https://api.softlayer.com/rest/v3.1 para autenticação da chave API, https://api.softlayer.com/mobile/v3.1 para autenticação do IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nome do usuário do Softlayer.</dd>
<dt>-p, --sl-password</dt>
<dd>Senha ou chave API do Softlayer.</dd>
<dt>-c, --account-id</dt>
<dd>ID da conta do Softlayer.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID da pergunta de segurança usado para autenticar; pergunte ao proprietário da conta se você não souber.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Resposta à pergunta de segurança usada para autenticação; pergunte ao proprietário da conta se você não souber.</dd>
<dt>-s, --security-code</dt>
<dd>Código de segurança gerado pelo fornecedor de segurança quando a autenticação de 2 fatores está ativada.</dd>
<dt>-v, --security-vendor</dt>
<dd>Fornecedor de segurança que fornece o código de segurança para autenticação, as opções são: VERISIGN, TOTP, PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Token de autenticação quando a autenticação de telefone está ativada.</dd>
</dl>

Por exemplo, login com nome do usuário e senha/chave API da infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}
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
Por exemplo, use a conexão única do {{site.data.keyword.Bluemix_notm}} para efetuar login no Softlayer
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
Setting account to: 278444
OK

Softlayer API endpoint:    https://api.softlayer.com/mobile/v3.1
Account ID:                278444
User ID:                   12345678
IMS token:                 xxxxxxxxxx
```

### ibmcloud sl help
{: #sl_help}

Visualizar informações da ajuda para todos os comandos para operar o ambiente de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help

```

### Ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Autorizar hosts a acessar um determinado volume.
```
Ibmcloud sl block access-authorize VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser autorizado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser autorizado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser autorizado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser autorizado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
Esse comando autoriza o servidor virtual com ID 87654321 a acessar o volume com ID 12345678.

### ibmcloud sl block access-list
{: #sl_block_access_list}

Listar ACLs.
```
Ibmcloud sl block access-list VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
Esse comando lista todos os hosts que estão autorizados a acessar o volume com ID 12345678 e os classifica por ID.

### Ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Revogar autorização para hosts que acessam um determinado volume.
```
Ibmcloud sl block access-revoke VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser revogado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser revogado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser revogado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser revogado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Esse comando revoga o acesso do servidor virtual com ID 87654321 para o volume com ID 12345678.

### Ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Efetuar failback de um volume de bloco da réplica.
```
Ibmcloud sl block replica-failback VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-failback 12345678
```
Esse comando executa a operação de failback para o volume com ID 12345678.

### Ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Efetuar failover de um volume de bloco no volume de réplica especificado.
```
Ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-failover 12345678 87654321
```
Esse comando executa a operação de failover do volume com ID 12345678 para o volume de réplica com ID 87654321.

### Ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Listar data centers de replicação adequados para o volume especificado.
```
Ibmcloud sl block replica-locations VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-locations 12345678
```
Esse comando lista os data centers de replicação adequados para o volume de bloco com ID 12345678.

### Ibmcloud sl block replica-order
{: #sl_block_replica_order}

Pedir um volume de réplica de armazenamento de bloco.
```
Ibmcloud sl block replica-order VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Requerido. Planejamento de captura instantânea a ser usada para replicação, as opções são: HOURLY, DAILY, WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para a réplica, por exemplo, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume primário para o qual uma réplica é pedida, as opções são: 0.25, 2, 4, 10. Se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-o, --os-type</dt>
<dd>Opcional. Tipo de sistema operacional (por exemplo, LINUX) do volume primário para o qual uma réplica é pedida, as opções são: HYPER_V,LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Esse comando pede uma réplica para o volume com ID 12345678, que executa a replicação DAILY, está localizado em dal09, o nível de camada é 4, o tipo de OS é Linux.

### Ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Listar volumes replicantes existentes para um volume de bloco.
```
Ibmcloud sl block replica-partners VOLUME_ID [ OPTIONS ]
```


**Exemplos**:
```
Ibmcloud sl block replica-partners 12345678
```
Esse comando lista volumes replicantes existentes para o volume de bloco com ID 12345678.

### Ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Cancelar o espaço de captura instantânea existente para um determinado volume.
```
Ibmcloud sl block snapshot-cancel SNAPSHOT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o espaço de captura instantânea imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
Esse comando cancela a captura instantânea com ID 12345678 imediatamente sem pedir confirmação.

### Ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Criar uma captura instantânea em um determinado volume.
```
Ibmcloud sl block snapshot-create VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notas a serem configuradas na nova captura instantânea.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforbluemix
```
Esse comando cria uma captura instantânea para o volume com ID 12345678 e com nota de adição como snapshotforbluemix.

### Ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Desativar capturas instantâneas no planejamento especificado para um determinado volume.
```
Ibmcloud sl block snapshot-disable VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
Esse comando desativa a captura instantânea diária para o volume com ID 12345678.

### ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Ativar capturas instantâneas para um determinado volume no planejamento especificado.
```
Ibmcloud sl block snapshot-enable VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Requerido. Número de capturas instantâneas a serem retidas.</dd>
<dt>-m, --minute</dt>
<dd>Minuto da hora em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 59.</dd>
<dt>-r, --hour</dt>
<dd>Hora do dia em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Dia da semana em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 6. 0 significa domingo, 1 significa segunda-feira, 2 significa terça-feira, 3 significa quarta-feira, 4 significa quinta-feira, 5 significa sexta-feira, 6 significa sábado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Esse comando ativa a captura instantânea para o volume com ID 12345678, a captura instantânea é tomada semanalmente todo domingo às 2h e até cinco capturas instantâneas são retidas.

### Ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Excluir uma captura instantânea em um determinado volume.
```
Ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl block snapshot-delete 12345678
```
Esse comando exclui a captura instantânea com ID 12345678.

### Ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Listar capturas instantâneas de armazenamento de bloco.
```
Ibmcloud sl block snapshot-list VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,created,size_bytes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
Esse comando lista todas as capturas instantâneas do volume com ID 12345678 e as classifica por ID.

### Ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Pedir espaço de captura instantânea para um volume de armazenamento de bloco.
```
Ibmcloud sl block snapshot-order VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do espaço de captura instantânea a ser criado em GB.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume de bloco para o qual o espaço é pedido, as opções são: 0,25, 2, 4, 10.</dd>
<dt>-i, --iops</dt>
<dd>IOPs do armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Sinalização para indicar que a ordem é um upgrade.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
Esse comando pede o espaço de captura instantânea para o volume com ID 12345678; o tamanho é 1.000 GB, o nível de camada é 4 IOPS por GB.

### Ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restaurar volume de bloco usando uma captura instantânea especificada.
```
Ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl block snapshot-restore 12345678 87654321
```
Esse comando restaura o volume com ID 12345678 da captura instantânea com ID 87654321.

### Ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Cancelar um volume de armazenamento de bloco existente.
```
Ibmcloud sl block volume-cancel VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o volume de armazenamento de bloco imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
Esse comando cancela o volume com ID 12345678 imediatamente e sem pedir confirmação.

### Ibmcloud sl block volume-list
{: #sl_block_volume_list}

Listar armazenamento de bloco.
```
Ibmcloud sl block volume-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filtrar pelo nome do usuário do volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrar por tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrar pelo ID da ordem que comprou o armazenamento de bloco.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Esse comando lista todos os volumes de resistência na conta atual que estão localizados em dal09 e os classifica por capacidade.

### Ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Exibir detalhes para um volume especificado.
```
Ibmcloud sl block volume-detail VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block volume-detail 12345678
```
Esse comando mostra os detalhes do volume com ID 12345678.

### Ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Pedir um volume de bloco duplicando um volume existente.
```
Ibmcloud sl block volume-duplicate VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID de uma captura instantânea do volume de origem a ser usado para duplicação.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Tamanho do volume de bloco duplicado em GB; se nenhum tamanho for especificado, o tamanho do volume original será usado.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Camada de armazenamento de resistência, se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>O tamanho do espaço de captura instantânea a ser pedido para a duplicata; se nenhum tamanho de espaço de captura instantânea for especificado, o tamanho do espaço de captura instantânea do volume de origem será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl block volume-duplicate 12345678
```
Esse comando mostra a ordem de um novo volume duplicando o volume com ID 12345678.

### Ibmcloud sl block volume-order
{: #sl_block_volume_order}

Pedir um volume de armazenamento de bloco.
```
Ibmcloud sl block volume-order [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Requerido. Tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do volume de armazenamento em GB.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100 [necessário para desempenho de tipo de armazenamento].</dd>
<dt>-e, --tier</dt>
<dd>Camada de armazenamento de resistência (IOP por GB) [necessária para resistência de tipo de armazenamento], as opções são: 0.25, 2, 4, 10.</dd>
<dt>-o, --os-type</dt>
<dd>Requerido. Sistema operacional, as opções são: HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parâmetro opcional para pedir espaço de captura instantânea junto ao armazenamento de bloco de resistência; especifica o tamanho (em GB) do espaço de captura instantânea a ser pedido.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Esse comando pede um volume de desempenho com tamanho 1.000 GB, IOPS 4.000, tipo de OS LINUX, localizado em dal09.

### ibmcloud sl block volume-options
{: #sl_block_volume_options}

Listar todas as opções para pedir um armazenamento de bloco.
```
ibmcloud sl block volume-options
```


**Exemplos**:
```
ibmcloud sl block volume-options
```
Esse comando lista todas as opções para criar um volume de armazenamento de bloco, incluindo tipo de armazenamento, tamanho do volume, tipo de OS, IOPS, nível de camada, data center e tamanho da captura instantânea.

### Sl cdn cancel ibmcloud
{: #sl_cdn_cancel}

Cancelar uma conta do CDN.
```
Ibmcloud sl cdn cancel ACCOUNT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
### Sl cdn detail ibmcloud
{: #sl_cdn_detail}

Detalhar uma Conta do CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### Sl cdn list ibmcloud
{: #sl_cdn_list}

Listar todas as contas do CDN.
```
Sl cdn list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem.</dd>
</dl>
### Sl cdn load ibmcloud
{: #sl_cdn_load}

Armazenar em cache um ou mais arquivos em todos os nós da borda.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### Ordem ibmcloud sl cdn
{: #sl_cdn_order}

Pedir uma conta do CDN.
```
Sl cdn order ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>Largura da banda do CDN, o preço 'Pagamento por uso' será usado, se não especificado.</dd>
<dt>-s, --storage</dt>
<dd>Armazenamento do CDN, o preço 'Pagamento por uso' será usado, se não especificado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
### ibmcloud sl cdn options
{: #sl_cdn_options}

Opções de largura da banda e de armazenamento para pedir a conta do CDN.
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Criar um mapeamento pull de origem.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --type</dt>
<dd>O tipo de mídia para esse mapeamento (http, flash, wm...), o padrão é: http.</dd>
<dt>-c, --cname</dt>
<dd>Um CNAME opcional para anexar ao mapeamento.</dd>
</dl>
### Ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Listar mapeamentos pull de origem.
```
Ibmcloud sl cdn origin-list ACCOUNT_ID
```

### Ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Remover um mapeamento pull de origem.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
### Sl cdn purge ibmcloud
{: #sl_cdn_purge}

Limpar arquivos em cache de todos os nós da borda.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
### Sl file access-authorize ibmcloud
{: #sl_file_access_authorize}

Autorizar hosts a acessar um determinado volume.
```
Sl file access-ibmcloud authorize VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser autorizado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser autorizado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser autorizado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser autorizado.</dd>
<dt>-s, --subnet-id</dt>
<dd>Um ID de uma sub-rede a ser autorizada.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
Esse comando autoriza o servidor virtual com ID 87654321 a acessar o volume com ID 12345678.

### Ibmcloud sl file access-list
{: #sl_file_access_list}

Listar ACLs.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-list 12345678 --sortby id
```
Esse comando lista todos os hosts que estão autorizados a acessar o volume com ID 12345678 e os classifica por ID.

### Sl file access-revoke ibmcloud
{: #sl_file_access_revoke}

Revogar autorização para hosts que acessam um determinado volume.
```
Sl file access-ibmcloud revoke VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser revogado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser revogado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser revogado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser revogado.</dd>
<dt>-s, --subnet-id</dt>
<dd>Um ID de uma sub-rede a ser revogada.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
Esse comando revoga o acesso do servidor virtual com ID 87654321 para o volume com ID 12345678.

### Ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Efetuar failback de um volume de arquivo da réplica.
```
Ibmcloud sl file replica-failback VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl file replica-failback 12345678
```
Esse comando executa a operação de failback para o volume com ID 12345678.

### Ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Efetuar failover de um volume de arquivo no volume de réplica especificado.
```
Ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Exemplos**:
```
Ibmcloud sl file replica-failover 12345678 87654321
```
Esse comando executa a operação de failover do volume com ID 12345678 para o volume de réplica com ID 87654321.

### Ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Listar data centers de replicação adequados para o volume especificado.
```
Ibmcloud sl file replica-locations VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl file replica-locations 12345678
```
Esse comando lista data centers de replicação adequados para o volume de arquivo com ID 12345678.

### ibmcloud sl file replica-order
{: #sl_file_replica_order}

Pedir um volume de réplica de armazenamento de arquivo.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Requerido. Planejamento da captura instantânea a ser usado para replicação, as opções são: HOURLY, DAILY, WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para a réplica, por exemplo, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume primário para o qual uma réplica é pedida, as opções são: 0.25, 2, 4, 10. Se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
Esse comando pede uma réplica para o volume com ID 12345678, que executa a replicação DAILY, está localizado em dal09, o nível de camada é 4.

### Ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Listar volumes replicantes existentes para um volume de arquivo.
```
Ibmcloud sl file replica-partners VOLUME_ID [ OPTIONS ]
```


**Exemplos**:
```
Ibmcloud sl file replica-partners 12345678
```
Esse comando lista volumes replicantes existentes para o volume de arquivo com ID 12345678.

### Ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Cancelar o espaço de captura instantânea existente para um determinado volume.
```
Sl file snapshot-cancel SNAPSHOT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o espaço de captura instantânea imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
Esse comando cancela a captura instantânea com ID 12345678 imediatamente sem pedir confirmação.

### Ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Criar uma captura instantânea em um determinado volume.
```
Sl file snapshot-create VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notas a serem configuradas na nova captura instantânea.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforbluemix
```
Esse comando cria uma captura instantânea para o volume com ID 12345678 e com nota de adição como snapshotforbluemix.

### Sl file snapshot-disable ibmcloud
{: #sl_file_snapshot_disable}

Desativar capturas instantâneas no planejamento especificado para um determinado volume.
```
Sl file snapshot-disable VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
Esse comando desativa a captura instantânea diária para o volume com ID 12345678.

### Sl file snapshot-enable ibmcloud
{: #sl_file_snapshot_enable}

Ativar capturas instantâneas para um determinado volume no planejamento especificado.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Requerido. Número de capturas instantâneas a serem retidas.</dd>
<dt>-m, --minute</dt>
<dd>Minuto da hora em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 59.</dd>
<dt>-r, --hour</dt>
<dd>Hora do dia em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Dia da semana em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 6. 0 significa domingo, 1 significa segunda-feira, 2 significa terça-feira, 3 significa quarta-feira, 4 significa quinta-feira, 5 significa sexta-feira, 6 significa sábado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Esse comando ativa a captura instantânea para o volume com ID 12345678, a captura instantânea é tomada semanalmente todo domingo às 2h e até cinco capturas instantâneas são retidas.

### Ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Excluir uma captura instantânea em um determinado volume.
```
Ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl file snapshot-delete 12345678
```
Esse comando exclui a captura instantânea com ID 12345678.

### Ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Listar capturas instantâneas do armazenamento de arquivo.
```
Ibmcloud sl file snapshot-list VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,created,size_bytes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
Esse comando lista todas as capturas instantâneas do volume com ID 12345678 e as classifica por ID.

### Ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Pedir espaço de captura instantânea para um volume de armazenamento de arquivo.
```
Ibmcloud sl file snapshot-order VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do espaço de captura instantânea a ser criado em GB.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume de arquivo para o qual o espaço é pedido, as opções são: 0,25, 2, 4, 10.</dd>
<dt>-i, --iops</dt>
<dd>IOPs do armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Sinalização para indicar que a ordem é um upgrade.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Esse comando pede espaço de captura instantânea para o volume com ID 12345678, o tamanho é 1.000 GB, o nível de camada é 4 IOPS por GB.

### Ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Restaurar volume de arquivo usando uma captura instantânea especificada.
```
Ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl file snapshot-restore 12345678 87654321
```
Esse comando restaura o volume com ID 12345678 da captura instantânea com ID 87654321.

### ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Cancelar um volume de armazenamento de arquivo existente.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o volume de armazenamento de arquivo imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
Esse comando cancela o volume com ID 12345678 imediatamente e sem pedir confirmação.

### Ibmcloud sl file volume-list
{: #sl_file_volume_list}

Listar armazenamento de arquivo.
```
Ibmcloud sl file volume-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filtrar pelo nome do usuário do volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrar por tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID da ordem que comprou o armazenamento de arquivo.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, mount_addr.</dd>
<dt>--columns</dt>
<dd>Colunas pelas quais classificar, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, mount_addr.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Esse comando lista todos os volumes de resistência na conta atual que estão localizados em dal09 e os classifica por capacidade.

### Ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Exibir detalhes para um volume especificado.
```
Ibmcloud sl file volume-detail VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl file volume-detail 12345678
```
Esse comando mostra os detalhes do volume com ID 12345678.

### Ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Pedir um volume de arquivo duplicando um volume existente.
```
Sl file volume-duplicate VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID de uma captura instantânea do volume original a ser usado para duplicação.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Tamanho do volume de arquivo duplicado em GB; se nenhum tamanho for especificado, o tamanho do volume original será usado.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Camada de armazenamento de resistência, se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>O tamanho do espaço de captura instantânea a ser pedido para a duplicata; se nenhum tamanho de espaço de captura instantânea for especificado, o tamanho do espaço de captura instantânea do volume original será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl file volume-duplicate 12345678
```
Esse comando mostra a ordem de um novo volume duplicando o volume com ID 12345678.

### Ibmcloud sl file volume-order
{: #sl_file_volume_order}

Pedir um volume de armazenamento de arquivo.
```
Ibmcloud sl file volume-order [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Requerido. Tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do volume de armazenamento em GB.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100 [necessário para desempenho de tipo de armazenamento].</dd>
<dt>-e, --tier</dt>
<dd>Camada de armazenamento de resistência (IOP por GB) [necessária para resistência de tipo de armazenamento], as opções são: 0.25, 2, 4, 10.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parâmetro opcional para pedir espaço de captura instantânea junto ao volume.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Esse comando pede um volume de desempenho com o tamanho 1.000 GB, IOPS de 4.000, localizado em dal09.

### ibmcloud sl file volume-options
{: #sl_file_volume_options}

Listar todas as opções para pedir um armazenamento de arquivo.
```
ibmcloud sl file volume-options
```


**Exemplos**:
```
ibmcloud sl file volume-options
```
Esse comando lista todas as opções para criar um volume de armazenamento de arquivo, incluindo o tipo de armazenamento, o tamanho do volume, o IOPS, o nível de camada, o data center e o tamanho da captura instantânea.

### Sl dns import ibmcloud
{: #sl_dns_import}

Importar uma zona com base em um arquivo de zona BIND.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--dry-run</dt>
<dd>Não criar registros realmente.</dd>
</dl>

**Exemplos**:
```
Sl dns import ibmcloud
```
Esse comando importa a zona e seus registros de recursos do arquivo: ~/blumix.net.txt.

### Ibmcloud sl dns record-add
{: #sl_dns_record_add}

Incluir registro de recurso em uma zona.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL (Tempo de vida) em segundos, como: 86.400, o padrão é: 7.200.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Esse comando inclui um registro A na zona: bluemix.net, seu host é "ftp", os dados são "127.0.0.1" e ttl é 86400 segundos.

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Atualizar registros de recurso em uma zona.
```
Ibmcloud sl dns record-edit ZONE [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--by-record</dt>
<dd>Editar pelo registro do host, como www.</dd>
<dt>--by-id</dt>
<dd>Editar um registro único por seu ID.</dd>
<dt>--data</dt>
<dd>Registrar dados, como um endereço IP.</dd>
<dt>--ttl</dt>
<dd>Valor TTL em segundos, como: 86400.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Esse comando edita registros na zona: bluemix.net, cujo ID é 12345678 e configura seus dados como "127.0.0.2" e ttl como 3600.

### Ibmcloud sl dns record-list
{: #sl_dns_record_list}

Listar todos os registros de recurso em uma zona.
```
Ibmcloud sl dns record-list ZONE [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--data</dt>
<dd>Filtrar por dados do registro, como um endereço IP.</dd>
<dt>--record</dt>
<dd>Filtrar pelo registro do host, como www.</dd>
<dt>--ttl</dt>
<dd>Filtrar pelo valor TTL em segundos, como: 86400.</dd>
<dt>--type</dt>
<dd>Filtrar pelo tipo de registro, como A ou CNAME.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Esse comando lista todos os registros A na zona: bluemix.net, filtrado pelo host é elasticsearch e ttl é 900 segundos.

### Ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Remover registro de recurso de uma zona.
```
Ibmcloud sl dns record-remove RECORD_ID
```


**Exemplos**:
```
Ibmcloud sl dns record-remove 12345678
```
Esse comando remove o registro de recurso com ID 12345678.

### Ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Criar uma zona.
```
ibmcloud sl dns zone-create ZONE
```


**Exemplos**:
```
Ibmcloud sl dns zone-create bluemix.net
```
Esse comando cria uma zona denominada bluemix.net.

### Ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Excluir uma zona.
```
Ibmcloud sl dns zone-delete ZONE
```


**Exemplos**:
```
Ibmcloud sl dns zone-delete bluemix.net
```
Esse comando exclui uma zona denominada bluemix.net.

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Listar todas as zonas em sua conta.
```
ibmcloud sl dns zone-list
```


**Exemplos**:
```
ibmcloud sl dns zone-list
```
Esse comando lista todas as zonas na conta atual.

### Ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Imprimir registros de zona e recurso no formato BIND.
```
Ibmcloud sl dns zone-print ZONE
```


**Exemplos**:
```
Ibmcloud sl dns zone-print bluemix.net
```
Esse comando imprime a zona chamada bluemix.net no formato BIND.

### Ibmcloud sl globalip create
{: #sl_globalip_create}

Criar um IP global.
```
Ibmcloud sl globalip create [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v6</dt>
<dd>Pedir um endereço IP IPv6.</dd>
<dt>--test</dt>
<dd>Testar a ordem.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Sl globalip create ibmcloud -- v6
```
Esse comando cria um endereço IP V6.

### ibmcloud sl globalip assign
{: #sl_globalip_assign}

Designar um IP global a um roteador ou dispositivo de destino.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Exemplos**:
```
Ibmcloud sl globalip assign 12345678 9.111.123.456
```
Esse comando designa um endereço IP com ID 12345678 a um dispositivo de destino cujo endereço IP é 9.111.123.456.

### Sl globalip cancel ibmcloud
{: #sl_globalip_cancel}

Cancelar um IP global.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl globalip cancel 12345678
```
Esse comando cancela o endereço IP com ID 12345678.

### Sl globalip list ibmcloud
{: #sl_globalip_list}

Listar todos os IPs globais em sua conta.
```
Sl globalip list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v4</dt>
<dd>Exibir IPs IPv4 somente.</dd>
<dt>--v6</dt>
<dd>Exibir IPs IPv6 somente.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou esse endereço IP.</dd>
</dl>

**Exemplos**:
```
Sl globalip list ibmcloud -- v4
```
Esse comando lista todos os endereços IP V4 na conta atual.

### Sl globalip unassign ibmcloud
{: #sl_globalip_unassign}

Remover designação de um IP global de um roteador ou dispositivo de destino.
```
Ibmcloud sl globalip unassign IDENTIFIER
```


**Exemplos**:
```
Ibmcloud sl globalip unassign 12345678
```
Esse comando remove a designação do endereço IP com ID 12345678 do dispositivo de destino.

### Sl image delete ibmcloud
{: #sl_image_delete}

Excluir uma imagem.
```
Sl image delete IDENTIFIER ibmcloud
```
**Exemplos**:
```
   Ibmcloud sl image delete 12345678
```
Esse comando exclui a imagem com ID `12345678`.

### Sl image detail ibmcloud
{: #sl_image_detail}

Obter detalhes para uma imagem.
```
Sl image detail IDENTIFIER ibmcloud
```
**Exemplos**:
```
 Ibmcloud sl image detail 12345678
```
Esse comando obtém detalhes para a imagem com ID 12345678.

### Sl image edit ibmcloud
{: #sl_image_edit}

Editar detalhes de uma imagem.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--name</dt>
<dd>Nome da imagem.</dd>
<dt>--note</dt>
<dd>Nota adicional para a imagem.</dd>
<dt>--tag</dt>
<dd>Tags para a imagem.</dd>
</dl>

*Exemplos**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Esse comando edita a imagem com o ID `12345678` e configura seu nome para `ubuntu16`, a nota para `testing` e a tag para `staging`.

### Sl image list ibmcloud
{: #sl_image_list}

Listar todas as imagens em sua conta.
```
Sl image list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--name</dt>
<dd>Filtrar no nome da imagem.</dd>
<dt>--public</dt>
<dd>Exibir somente imagens públicas.</dd>
<dt>--private</dt>
<dd>Exibir somente imagens privadas.</dd>
</dl>

### Sl ipsec cancel ibmcloud
{: #sl_ipsec_cancel}

Cancelar um contexto do túnel VPN IPSec.
```
Ibmcloud sl ipsec cancel CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--immediate</dt>
<dd>Cancelar o IPSec imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### Ibmcloud sl ipsec config
{: #sl_ipsec_config}

Solicitar configuração de um contexto de túnel.
```
Sl ipsec config CONTEXT_ID ibmcloud [ OPTIONS ]
```

### ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Listar detalhes de contexto do túnel VPN IPSec.
```
Ibmcloud sl ipsec detail CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Incluir recursos adicionais, as opções são: at, is, rs, sr, ss.</dd>
</dl>
### Sl ipsec list ibmcloud
{: #sl_ipsec_list}

Listar contextos do túnel VPN IPSec.
```
Sl ipsec list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou o IPSEC.</dd>
</dl>
### Sl ipsec order ibmcloud
{: #sl_ipsec_order}

Pedir um túnel VPN IPSec.
```
Sl ipsec order ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para o IPSEC, por exemplo, dal09.</dd>
</dl>

### Sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Incluir uma sub-rede em um contexto do túnel IPSec.
```
Ibmcloud sl ipsec subnet-add CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificador de sub-rede a ser incluído, necessário.</dd>
<dt>-t, --subnet-type</dt>
<dd>Tipo de sub-rede a ser incluído, necessário, as opções são: internal, remote, service.</dd>
<dt>-n, --network</dt>
<dd>O identificador de rede da sub-rede a ser criado.</dd>
</dl>

### Ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Remover uma sub-rede de um contexto do túnel IPSec.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

### Sl ipsec translation-add
{: #sl_ipsec_translation_add}

Incluir uma conversão de endereço em um túnel IPSec.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Endereço IP estático, necessário.</dd>
<dt>-r, --remote-ip</dt>
<dd>Endereço IP remoto, necessário.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>
### Ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Remover uma entrada de conversão de um IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

### Ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Atualizar uma conversão de endereço para um IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Endereço IP estático, necessário.</dd>
<dt>-r, --remote-ip</dt>
<dd>Endereço IP remoto, necessário.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>
### Sl ipsec update ibmcloud
{: #sl_ipsec_update}

Atualizar propriedades de contexto de túnel.
```
Sl ipsec update ibmcloud CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Nome fácil.</dd>
<dt>-r, --remote-peer</dt>
<dd>Endereço IP peer remoto.</dd>
<dt>-k, --preshared-key</dt>
<dd>Chave pré-compartilhada.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Autenticação fase 1, as opções são: MD5, SHA1, SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Criptografia fase 1, as opções são: DES, 3DES, AES128, AES192, AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Grupo diffie hellman fase 1, as opções são: 0, 1, 2, 5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Duração da chave fase 1, o intervalo é 120 - 172.800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Autenticação fase 2, as opções são: MD5, SHA1, SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Criptografia fase 2, as opções são: DES, 3DES, AES128, AES192, AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Grupo diffie hellman fase 2, as opções são: 0, 1, 2, 5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Segredo de encaminhamento perfeito fase 2, o intervalo é 0 - 1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Duração da chave fase 2, o intervalo é 120 - 172.800.</dd>
</dl>

### Sl loadbal cancel ibmcloud
{: #sl_loadbal_cancel}

Cancelar um balanceador de carga existente.
```
Ibmcloud sl loadbal cancel LOADBAL_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

Inclui um balanceador de carga devido ao ID retornado de opções de criação.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Obter opções de preço para criar um balanceador de carga.
```
ibmcloud sl loadbal create-options
```

### Sl loadbal detail ibmcloud
{: #sl_loadbal_detail}

Obter detalhes do balanceador de carga.
```
Sl loadbal detail LOADBAL_ID ibmcloud
```

### Ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Inclui um novo serviço de balanceador de carga.
```
Ibmcloud sl loadbal group-add LOADBAL_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Requerido. O percentual de conexões alocado.</dd>
<dt>-p, --port</dt>
<dd>Requerido. O número da porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Requerido. O ID do tipo de roteamento. Execute 'ibmcloud sl loadbal routing-types' para localizar um ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Requerido. O ID do método de roteamento. Execute 'ibmcloud sl loadbal routing-methods' para localizar um ID.</dd>
</dl>

### Ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Exclui um grupo de serviços do balanceador de carga existente.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### Ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Editar um grupo de serviços do balanceador de carga existente.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Mudar o percentual de conexões alocado.</dd>
<dt>-p, --port</dt>
<dd>Mudar o número da porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Mude o ID do tipo de roteamento. Execute 'ibmcloud sl loadbal routing-types' para localizar um ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Mude o ID do método de roteamento. Execute 'ibmcloud sl loadbal routing-methods' para localizar um ID.</dd>
</dl>

### Ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Reconfigurar conexões em um determinado grupo de serviços.
```
Ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Listar tipos de verificação de funcionamento.
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

Listar balanceadores de carga ativos.
```
ibmcloud sl loadbal list
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-o, --order</dt>
<dd>Filtrar pelo ID da ordem que comprou o balanceador de carga.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtrar pelo endereço IP.</dd>
</dl>
### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Listar métodos de roteamento.
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Listar tipos de roteamento.
```
ibmcloud sl loadbal routing-types
```

### Ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Inclui um novo serviço do balanceador de carga.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Opcional. Crie o serviço como desativado, o padrão será ativado, se não especificado.</dd>
<dt>-p, --port</dt>
<dd>Requerido. O número da porta para o serviço.</dd>
<dt>-w, --weight</dt>
<dd>Requerido. O peso do serviço.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Requerido. O tipo de verificação de funcionamento.</dd>
<dt>-i, --ip-address</dt>
<dd>Requerido. O endereço IP do serviço.</dd>
</dl>

### Ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Exclui um serviço do balanceador de carga existente.
```
Ibmcloud sl loadbal service-delete SERVICE_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### Ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Editar as propriedades de um grupo de serviços.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Desativar o serviço.</dd>
<dt>--enabled</dt>
<dd>Ativar o serviço.</dd>
<dt>-p, --port</dt>
<dd>Mudar o número da porta do serviço.</dd>
<dt>-w, --weight</dt>
<dd>Mudar o peso do serviço.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Mudar o tipo de verificação de funcionamento.</dd>
<dt>-i, --ip-address</dt>
<dd>Mudar o endereço IP do serviço.</dd>
</dl>

### Ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Alternar o status de um serviço do balanceador de carga existente.
```
Ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Incluir uma nova chave SSH.
```
Ibmcloud sl security sshkey-add LABEL [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>O arquivo id_rsa.pub a ser importado para essa chave.</dd>
<dt>-k, --key</dt>
<dd>A chave SSH real.</dd>
<dt>--note</dt>
<dd>Nota extra que será associada à chave.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Esse comando inclui uma chave SSH por meio do arquivo: ~/.ssh/id_rsa.pub with a note "mykey".

### Ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Editar uma chave SSH.
```
Ibmcloud sl security sshkey-edit IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--label</dt>
<dd>O novo rótulo para a chave.</dd>
<dt>--note</dt>
<dd>Novas notas para a chave.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Esse comando atualiza a chave SSH com ID 12345678, configura a etiqueta como "Bluemix" e a nota como "testing".

### Ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

Listar chaves SSH em sua conta.
```
Ibmcloud sl security sshkey-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, label, fingerprint, notes.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security sshkey-list -- sortby label
```
Esse comando lista todas as chaves SSH na conta atual e as classifica pela etiqueta.

### Ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Imprime uma chave SSH na tela.
```
Ibmcloud sl security sshkey-print IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>A chave SSH pública será gravada neste arquivo.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
Esse comando mostra o ID, o rótulo e as notas da chave SSH com ID 12345678 e grava a chave pública no arquivo: ~/mykey.pub.

### Ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Remove permanentemente uma chave SSH.
```
Ibmcloud sl security sshkey-remove IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security sshkey-remove 12345678 -f
```
Esse comando remove a chave SSH com ID 12345678 sem solicitar confirmação.

### Ibmcloud sl security cert-add
{: #sl_security_cert_add}

Incluir e fazer upload de detalhes do certificado SSL.
```
Ibmcloud sl security cert-add [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--crt</dt>
<dd>Arquivo de certificado.</dd>
<dt>--csr</dt>
<dd>Arquivo de solicitação de assinatura de certificado.</dd>
<dt>--icc</dt>
<dd>Arquivo de certificado intermediário.</dd>
<dt>--key</dt>
<dd>Arquivo de chave privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionais.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key
```
Esse comando inclui o arquivo de certificado: ~/bluemix.net.cert e o arquivo de chave privado ~/bluemix.net.key para o domínio bluemix.net.

### Ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Editar certificado SSL.
```
Ibmcloud sl security cert-edit IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--crt</dt>
<dd>Arquivo de certificado.</dd>
<dt>--csr</dt>
<dd>Arquivo de solicitação de assinatura de certificado.</dd>
<dt>--icc</dt>
<dd>Arquivo de certificado intermediário.</dd>
<dt>--key</dt>
<dd>Arquivo de chave privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionais.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-edit 12345678 --key ~/bluemix.net.key
```
Esse comando edita o certificado com ID 12345678 e atualiza sua chave privada com o arquivo: ~/bluemix.net.key.

### Ibmcloud sl security cert-download
{: #sl_security_cert_download}

Fazer download do certificado SSL e dos arquivos-chave.
```
Ibmcloud sl security cert-download IDENTIFIER
```


**Exemplos**:
```
Ibmcloud sl security cert-download 12345678
```
Esse comando faz download de 4 arquivos no diretório atual para o certificado com ID 12345678. Os 4 arquivos são: arquivo de certificado, arquivo de solicitação de assinatura de certificado, arquivo de certificado intermediário e arquivo de chave privado.

### Ibmcloud sl security cert-list
{: #sl_security_cert_list}

Listar certificados SSL em sua conta.
```
Ibmcloud sl security cert-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--status</dt>
<dd>Mostrar certificados com este status, o padrão é: all, as opções são: all, valid, expired.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, common_name, days_until_expire, notes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Esse comando lista todos os certificados válidos na conta atual e os classifica pelos dias de validade.

### Ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Remover certificado SSL.
```
Ibmcloud sl security cert-remove IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security cert-remove 12345678
```
Esse comando remove o certificado com ID 12345678.

### ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Cancelar uma sub-rede.
```
Ibmcloud sl subnet cancel IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Esse comando cancela a sub-rede com ID 12345678 sem solicitar confirmação.

### Ibmcloud sl subnet create
{: #sl_subnet_create}

Inclua uma nova sub-rede em sua conta.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Pedir endereços IPv6.</dd>
<dt>--test</dt>
<dd>Não pedir a sub-rede; obter apenas uma cota.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet create public 16 567
```
Esse comando cria uma sub-rede pública com 16 endereços IP v4 e a coloca na vlan com ID 567.

### Sl subnet detail ibmcloud
{: #sl_subnet_detail}

Obter detalhes de uma sub-rede.
```
Sl subnet detail IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Ocultar listagem de servidor virtual.</dd>
<dt>--no-hardware</dt>
<dd>Ocultar listagem de hardware.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl subnet detail 12345678
```
Esse comando mostra informações detalhadas sobre a sub-rede com ID 12345678, incluindo informações de servidores virtuais e de hardware.

### Sl subnet list ibmcloud
{: #sl_subnet_list}

Listar todas as sub-redes em sua conta.
```
Sl subnet list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar. As opções são: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>--identifier</dt>
<dd>Filtrar pelo identificador de rede.</dd>
<dt>-t, --subnet-type</dt>
<dd>Filtrar pelo tipo de sub-rede.</dd>
<dt>--network-space</dt>
<dd>Filtrar pelo espaço de rede.</dd>
<dt>--v4, --ipv4</dt>
<dd>Exibir somente sub-redes IPv4.</dd>
<dt>--v6, --ipv6</dt>
<dd>Exibir somente sub-redes IPv6.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou as sub-redes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Esse comando lista sub-redes IP V4 na conta atual filtrando pelo data center dal09, tipo de sub-rede PRIMARY e espaço de rede PUBLIC.

### Sl subnet lookup ibmcloud
{: #sl_subnet_lookup}

Localizar um endereço IP e exibir suas informações de sub-rede e dispositivo.
```
Ibmcloud sl subnet lookup IP_ADDRESS
```


**Exemplos**:
```
Ibmcloud sl subnet lookup 9.125.235.255
```
Esse comando localiza o registro de endereço IP com endereço 9.125.235.255 e exibe suas informações sobre a sub-rede e o dispositivo.

### Ibmcloud sl vlan create
{: #sl_vlan_create}

Criar uma nova VLAN.
```
Sl vlan create ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>O tipo da VLAN, público ou privado.</dd>
<dt>-r, --router</dt>
<dd>O nome do host do roteador.</dd>
<dt>-d, --datacenter</dt>
<dd>O nome abreviado do data center.</dd>
<dt>-s, --size</dt>
<dd>O tamanho das sub-redes, as opções são: 8 (5 IPs utilizáveis) ou 16 (13 IPs utilizáveis) ou 32 (29 IPs utilizáveis).</dd>
<dt>-n, --name</dt>
<dd>O nome da VLAN.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Esse comando cria uma vlan pública localizada no data center dal09 com 16 endereços IP e o nome é myvlan.

### Sl vlan cancel ibmcloud
{: #sl_vlan_cancel}

Cancelar uma VLAN.
```
Sl vlan cancel IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vlan cancel 12345678 -f
```
Esse comando cancela a vlan com ID 12345678 sem solicitar confirmação.

### Sl vlan detail ibmcloud
{: #sl_vlan_detail}

Obter detalhes sobre uma VLAN.
```
Sl vlan detail IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Ocultar listagem de servidor virtual.</dd>
<dt>--no-hardware</dt>
<dd>Ocultar listagem de hardware.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
Esse comando mostra detalhes da vlan com ID 12345678 e não lista o servidor virtual ou o servidor de hardware.

### Sl vlan edit ibmcloud
{: #sl_vlan_edit}

Editar os detalhes sobre uma VLAN.
```
Sl vlan edit IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>O nome da VLAN.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
Esse comando atualiza a vlan com ID 12345678 e fornece um novo nome a ela "myvlan-rename".

### Sl vlan list ibmcloud
{: #sl_vlan_list}

Listar todas as VLANs em sua conta.
```
Sl vlan list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-n, --number</dt>
<dd>Filtrar pelo número da VLAN.</dd>
<dt>--name</dt>
<dd>Filtrar pelo nome da VLAN.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou a VLAN.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Esse comando lista todas as vlans na conta atual, a filtragem por data center é igual a dal09 e a classificação é pelo número da vlan.

### ibmcloud sl vlan options
{: #sl_vlan_options}

Listar todas as opções para criar a VLAN.
```
ibmcloud sl vlan options
```


**Exemplos**:
```
ibmcloud sl vlan options
```
Esse comando lista todas as opções para criar uma vlan, por exemplo, tipo de vlan, data centers, tamanho da sub-rede, roteadores, etc.

### Ibmcloud sl vs cancel
{: #sl_vs_cancel}

Cancelar a instância de servidor virtual.
```
Ibmcloud sl vs cancel IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs cancel 12345678
```
Esse comando cancela a instância de servidor virtual com ID de 12345678.

### Sl vs capture ibmcloud
{: #sl_vs_capture}

Capturar a instância do servidor virtual em uma imagem.
```
Ibmcloud sl vs capture IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Requerido. Nome da imagem.</dd>
<dt>--all</dt>
<dd>Capturar todos os discos pertencentes ao VS.</dd>
<dt>--note</dt>
<dd>Incluir uma nota a ser associada à imagem.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs capture 12345678 -n mybluemix --all --note testing
```
Esse comando captura a instância de servidor virtual com ID de 12345678 com todos os discos em uma imagem chamada "mybluemix" com a nota "testing".

### Ibmcloud sl vs create
{: #sl_vs_create}

Criar instância de servidor virtual.
```
Ibmcloud sl vs create [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Requerido. Parte de host do FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Requerido. Parte de domínio do FQDN.</dd>
<dt>-c, --cpu</dt>
<dd>Requerido. Número de núcleos da CPU.</dd>
<dt>-m, --memory</dt>
<dd>Requerido. Memória em megabytes.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-o, --os</dt>
<dd>Código de instalação do OS. Dica: é possível especificar <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>ID da imagem. Veja: 'ibmcloud sl image list' para referência.</dd>
<dt>--billing</dt>
<dd>Taxa de faturamento. O padrão é: de hora em hora. As opções são: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Criar um Virtual Server dedicado (Nó privado).</dd>
<dt>--san</dt>
<dd>Usar o armazenamento SAN, em vez de disco local.</dd>
<dt>--test</dt>
<dd>Não criar realmente o servidor virtual.</dd>
<dt>--export</dt>
<dd>Exporta opções para um arquivo de modelo.</dd>
<dt>-i, --postinstall</dt>
<dd>Script de pós-instalação para download.</dd>
<dt>-k, --key</dt>
<dd>Os IDs das chaves SSH a serem incluídas para o usuário raiz (múltiplas ocorrências permitidas).</dd>
<dt>--disk</dt>
<dd>Tamanhos do disco (múltiplas ocorrências permitidas).</dd>
<dt>--private</dt>
<dd>Força o servidor virtual a ter acesso somente à rede privada.</dd>
<dt>--like</dt>
<dd>Usar a configuração de um servidor virtual existente.</dd>
<dt>-n, --network</dt>
<dd>Velocidade da porta de rede em Mbps.</dd>
<dt>--tag</dt>
<dd>Tags a serem incluídas na instância (múltiplas ocorrências permitidas).</dd>
<dt>-t, --template</dt>
<dd>Um arquivo de modelo que padroniza as opções da linha de comandos.</dd>
<dt>-u, --userdata</dt>
<dd>Sequência de metadados definidos pelo usuário.</dd>
<dt>-F, --userfile</dt>
<dd>Leia os dados do usuário do arquivo.</dd>
<dt>--vlan-public</dt>
<dd>O ID da VLAN pública na qual você deseja colocar o servidor virtual.</dd>
<dt>--vlan-private</dt>
<dd>O ID da VLAN privada na qual você deseja colocar o servidor virtual.</dd>
<dt>--wait</dt>
<dd>Aguarde até que o servidor virtual conclua o fornecimento por até X segundos antes de retornar.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Esse comando pede uma instância de servidor virtual com o nome de host myvsi, domínio bluemix.net, 4 núcleos de CPU, 4.096 M de memória, localizada no data center: dal10,

### ibmcloud sl vs options
{: #sl_vs_options}

Listar opções para criar a instância de servidor virtual.
```
As opções ibmcloud sl vs [ OPTIONS ]
```


**Exemplos**:
```
ibmcloud sl vs options
```
Esse comando lista todas as opções para criar uma instância de servidor virtual, por exemplo, data centers, CPU, memória, sistema operacional, disco, velocidade de rede, etc.

### Sl vs ibmcloud credenciais
{: #sl_vs_credentials}

Listar credenciais da instância de servidor virtual.
```
Ibmcloud sl vs credentials IDENTIFIER [ OPTIONS ]
```


**Exemplos**:
```
As credenciais sl vs ibmcloud 12345678
```
Esse comando lista todos os pares de nome de usuário e senha de instância de servidor virtual com ID 12345678.

### Sl vs detail ibmcloud
{: #sl_vs_detail}

Obter detalhes para uma instância de servidor virtual.
```
Ibmcloud sl vs detail IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--passwords</dt>
<dd>Mostrar senhas (verifique se tem alguém olhando!).</dd>
<dt>--price</dt>
<dd>Mostrar preços associados.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs details 12345678
```
Esse comando lista informações detalhadas sobre a instância de servidor virtual com ID 12345678.

### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Sincronizar registros DNS para uma instância de servidor virtual.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>Sincronizar o registro A para o host.</dd>
<dt>--aaaa-record</dt>
<dd>Sincronizar o registro AAAA para o host.</dd>
<dt>--ptr</dt>
<dd>Sincronizar o registro PTR para o host.</dd>
<dt>--ttl</dt>
<dd>Configura o TTL para os registros A e/ou PTR, o padrão é: 7200.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Esse comando sincroniza o registro A (endereço IP V4) da instância de servidor virtual com ID 12345678 para o servidor DNS e configura ttl desse registro A como 3.600.

### Sl vs edit ibmcloud
{: #sl_vs_edit}

Editar detalhes de uma instância de servidor virtual.
```
Sl vs edit IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Parte de domínio do FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Parte de host do FQDN. Exemplo: servidor.</dd>
<dt>--tag</dt>
<dd>Tags para configurar ou sequência de caracteres vazia para remover todos.</dd>
<dt>-u, --userdata</dt>
<dd>Sequência de metadados definidos pelo usuário.</dd>
<dt>-F, --userfile</dt>
<dd>Leia os dados do usuário do arquivo.</dd>
<dt>--public-speed</dt>
<dd>Velocidade da porta pública, as opções são: 0, 10, 100, 1000, 10000.</dd>
<dt>--private-speed</dt>
<dd>Velocidade da porta privada, as opções são: 0, 10, 100, 1000, 10000.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Esse comando atualiza a instância de servidor virtual com o ID 12345678 e configura seu domínio para ser "bluemix.net", hostname para "myapp", tag para "testcli",

### Sl vs list ibmcloud
{: #sl_vs_list}

Listar instâncias de servidor virtual em sua conta.
```
Sl vs list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Número de núcleos da CPU.</dd>
<dt>-D, --domain</dt>
<dd>Parte de domínio do FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Nome abreviado do data center.</dd>
<dt>-H, --hostname</dt>
<dd>Parte de host do FQDN.</dd>
<dt>-m, --memory</dt>
<dd>Memória em megabytes.</dd>
<dt>-n, --network</dt>
<dd>Velocidade da porta de rede em Mbps.</dd>
<dt>--hourly</dt>
<dd>Mostrar apenas instâncias de hora em hora.</dd>
<dt>--monthly</dt>
<dd>Mostrar apenas instâncias mensais.</dd>
<dt>--tag</dt>
<dd>Filtrar por tags (múltiplas ocorrências permitidas).</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. O padrão é: hostname.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. O padrão é: id, hostname, primary_ip, backend_ip, datacenter, action.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs list --domain bluemix.net --hourly --sortby memory
```
Esse comando lista todas as instâncias de servidor virtual de faturamento por hora na conta atual, o domínio de filtragem é igual a "bluemix.net" e a classificação é pela memória.

### Ibmcloud sl vs pause
{: #sl_vs_pause}

Pausar uma instância de servidor virtual ativa.
```
Sl vs pause IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs pause 12345678 -f
```
Esse comando pausa a instância de servidor virtual com ID 12345678 sem solicitar confirmação.

### Ibmcloud sl vs power-off
{: #sl_vs_power_off}

Desligar uma instância de servidor virtual ativa.
```
Ibmcloud sl vs power-off IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Executar um encerramento forçado.</dd>
<dt>--soft</dt>
<dd>Executar um encerramento normal.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs power-off 12345678 -- soft
```
Esse comando executa um desligamento normal da instância de servidor virtual com ID 12345678.

### Sl vs power-ibmcloud
{: #sl_vs_power_on}

Ligar uma instância de servidor virtual.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs power-on 12345678
```
Esse comando executa uma ligação da instância de servidor virtual com ID 12345678.

### Sl vs ibmcloud pronto
{: #sl_vs_ready}

Verificar se uma instância de servidor virtual está pronta para uso.
```
Ibmcloud sl vs ready IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--wait</dt>
<dd>Aguarde até que o servidor virtual conclua o fornecimento por até X segundos antes de retornar.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Esse comando verifica a instância de servidor virtual com o status de ID 12345678 para ver se está pronto para ser usado continuamente e aguarda até 30 segundos.

### Ibmcloud sl vs reboot
{: #sl_vs_reboot}

Reinicializar uma instância de servidor virtual ativa.
```
Ibmcloud sl vs reboot IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Execute uma reinicialização forçada.</dd>
<dt>--soft</dt>
<dd>Executa uma reinicialização normal.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs reboot 12345678 -- hard
```
Esse comando executa uma reinicialização permanente da instância de servidor virtual com ID 12345678.

### Sl vs reload ibmcloud
{: #sl_vs_reload}

Recarregar o sistema operacional em uma instância de servidor virtual.
```
Sl vs reload IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de pós-instalação para download.</dd>
<dt>--image</dt>
<dd>ID da imagem. O padrão é usar o sistema operacional atual.</dd>
<dt>Veja:</dt>
<dd>" Ibmcloud sl image list ' para referência.</dd>
<dt>-k, --key</dt>
<dd>Os IDs das chaves SSH a serem incluídas para o usuário raiz (múltiplas ocorrências permitidas).</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs reload 12345678
```
Esse comando recarrega o sistema operacional atual para a instância de servidor virtual com ID 12345678.

### Sl vs rescue ibmcloud
{: #sl_vs_rescue}

Reinicializar uma instância de servidor virtual em uma imagem de resgate.
```
Sl vs rescue IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs rescue 12345678
```
Esse comando reinicializa a instância de servidor virtual com ID 12345678 em uma imagem de resgate.

### ibmcloud sl vs resume
{: #sl_vs_resume}

Continuar uma instância de servidor virtual pausada.
```
Ibmcloud sl vs resume IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs resume 12345678
```
Esse comando continua a instância de servidor virtual com ID 12345678.

### Ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Fazer upgrade de uma instância de servidor virtual.
```
Ibmcloud sl vs upgrade IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Número de núcleos da CPU.</dd>
<dt>--private</dt>
<dd>O núcleo da CPU ficará em um servidor host dedicado.</dd>
<dt>-m, --memory</dt>
<dd>Memória em megabytes.</dd>
<dt>--network</dt>
<dd>Velocidade da porta de rede em Mbps.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Esse comando faz upgrade da instância de servidor virtual com ID 12345678 e configura o número de núcleos da CPU como 8, a memória como 8.192 M, a velocidade da porta de rede como 1.000 Mbps.
