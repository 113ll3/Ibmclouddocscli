---

copyright:

  years: 2016,2018


lastupdated: "2018-06-08"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー (ibmcloud sl) コマンド
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} プラグインは、{{site.data.keyword.Bluemix_notm}} CLI にマージされました。 このプラグインのインストールは必要なくなりました。
{: tip}

{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) で {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンドを使用して、SoftLayer のサービスを管理および構成します。

2018 年 5 月、{{site.data.keyword.Bluemix_notm}} CLI コマンドは `bluemix` および `bx` から `ibmcloud` に変更されました。 ただし、後日削除されるまで、`bluemix` および `bx` CLI CLI コマンドを引き続き使用できます。
{: tip}


まず、{{site.data.keyword.Bluemix_notm}} CLI をインストールします。 詳しくは、『[IBM Cloud CLI ![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}』を参照してください。

{{site.data.keyword.Bluemix_notm}} CLI コマンドの完全リストについては、[{{site.data.keyword.Bluemix_notm}} (ibmcloud) コマンド](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)を参照してください。


## 汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド

以下のコマンドがサポートされます。 使用可能なコマンドのリストを表示するには、`ibmcloud sl` コマンドを使用します。

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用コマンド">
<caption>表 1. 汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド</caption>
 <thead>
 <th colspan="6">汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ブロック・ストレージ・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 2. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ブロック・ストレージ</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ブロック・ストレージ</th>
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

 ## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー CDN コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 3. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー CDN</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー CDN</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/softlayer/index.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/softlayer/index.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/softlayer/index.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/softlayer/index.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/softlayer/index.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options
](/docs/cli/reference/softlayer/index.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/softlayer/index.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/softlayer/index.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ファイル・ストレージ・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 4. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ファイル・ストレージ</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ファイル・ストレージ</th>
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
   <td>[ibmcloud sl file volume-options
](/docs/cli/reference/softlayer/index.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー DNS コマンド

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 5. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー DNS コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー DNS コマンド</th>
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


<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 6. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・グローバル IP コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・グローバル IP コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・イメージ・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 7. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・イメージ・コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・イメージ・コマンド</th>
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

 ## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー IPSec VPN コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 7. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー IPSec VPN コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー IPSec VPN コマンド</th>
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

 ## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ロード・バランサー・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 8. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ロード・バランサー・コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・ロード・バランサー・コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/softlayer/index.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/softlayer/index.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options
](/docs/cli/reference/softlayer/index.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/softlayer/index.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/softlayer/index.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks
](/docs/cli/reference/softlayer/index.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list
](/docs/cli/reference/softlayer/index.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods
](/docs/cli/reference/softlayer/index.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types
](/docs/cli/reference/softlayer/index.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/softlayer/index.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・セキュリティー・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 9. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・セキュリティー・コマンド</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・セキュリティー・コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・サブネット・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 10. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・サブネット・コマンド</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・サブネット・コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー仮想サーバー・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 11. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー仮想サーバー・コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー仮想サーバー・コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー VLAN コマンド

  <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
<caption>表 12. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー VLAN コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー VLAN コマンド</th>
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

### コマンドの使用法
コマンドのヘルプ情報を表示するには、`ibmcloud sl [command] -h` を実行します。

### ibmcloud sl init
{: #sl_init}

{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー環境への接続に使用される構成設定を初期化します。 この構成には、ユーザー名、API キーまたはパスワード、アカウント、およびエンドポイントが含まれます。
```
ibmcloud sl init [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー API エンドポイント URL。デフォルトは、API キー認証の場合は https://api.softlayer.com/rest/v3.1、IBMid 認証の場合は https://api.softlayer.com/mobile/v3.1。</dd>
<dt>-u, --sl-user</dt>
<dd>Softlayer ユーザー名。</dd>
<dt>-p, --sl-password</dt>
<dd>Softlayer パスワードまたは API キー。</dd>
<dt>-c, --account-id</dt>
<dd>Softlayer アカウント ID。</dd>
<dt>-q, --security-question-id</dt>
<dd>認証に使用されるセキュリティー質問 ID。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-w, --security-question-answer</dt>
<dd>認証に使用されるセキュリティー質問の回答。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-s, --security-code</dt>
<dd>二要素認証が有効になっている場合にセキュリティー・ベンダーによって生成されるセキュリティー・コード。</dd>
<dt>-v, --security-vendor</dt>
<dd>認証用のセキュリティー・コードを提供するセキュリティー・ベンダー。オプション: VERISIGN、TOTP、PHONE_FACTOR。</dd>
<dt>-t, --auth-token</dt>
<dd>電話認証が有効な場合の認証トークン。</dd>
</dl>

例えば、{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャーのユーザー名とパスワード/API キーを使用してログインします
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
例えば、{{site.data.keyword.Bluemix_notm}} の Single-Sign-On を使用して Softlayer にログインします
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
2. {{site.data.keyword.Bluemix_notm}} Single-Sign-On を使用します

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

{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー環境で作動するすべてのコマンドのヘルプ情報を表示します。
```
ibmcloud sl help

```

### ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

指定されたボリュームへのホストのアクセスを許可します。
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>許可する 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>許可する 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>許可する 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>許可する IP アドレス。</dd>
</dl>

**例**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーが、ID 12345678 のボリュームにアクセスすることを許可します。

### ibmcloud sl block access-list
{: #sl_block_access_list}

ACL をリストします。
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
</dl>

**例**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームへのアクセスを許可されているすべてのホストをリストし、それらを ID によってソートします。

### ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

指定されたボリュームにアクセスするホストの許可を取り消します。
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>取り消す 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>取り消す 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>取り消す 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>取り消す IP アドレス。</dd>
</dl>

**例**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーの、ID 12345678 のボリュームへのアクセスを取り消します。

### ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

レプリカからブロック・ボリュームをフェイルバックします。
```
ibmcloud sl block replica-failback VOLUME_ID
```


**例**:
```
ibmcloud sl block replica-failback 12345678
```
このコマンドは、ID 12345678 のボリュームのフェイルバック操作を実行します。

### ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

ブロック・ボリュームを、指定されたレプリカ・ボリュームにフェイルオーバーします。
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**例**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームの、ID 87654321 のレプリカ・ボリュームへのフェイルオーバー操作を実行します。

### ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

指定されたボリュームに適切な複製データ・センターをリストします。
```
ibmcloud sl block replica-locations VOLUME_ID
```


**例**:
```
ibmcloud sl block replica-locations 12345678
```
このコマンドは、ID 12345678 のブロック・ボリュームの適切な複製データ・センターをリストします。

### ibmcloud sl block replica-order
{: #sl_block_replica_order}

ブロック・ストレージ・レプリカ・ボリュームを注文します。
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>必須。 複製に使用するスナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 複製用のデータ・センターの短縮名。例えば、dal09 など。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 レプリカを注文する 1 次ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-o, --os-type</dt>
<dd>オプション。 レプリカを注文する 1 次ボリュームのオペレーティング・システム・タイプ (例: LINUX)。オプション: HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS、XEN。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
このコマンドは、ID 12345678 のボリュームのレプリカを注文します。このレプリカは、毎日の複製を実行し、dal09 にあり、層レベルは 4、OS タイプは Linux です。

### ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

ブロック・ボリュームの既存のレプリカ・ボリュームをリストします。
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**例**:
```
ibmcloud sl block replica-partners 12345678
```
このコマンドは、ID 12345678 のブロック・ボリュームの既存のレプリカ・ボリュームをリストします。

### ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

指定されたボリュームの既存のスナップショット・スペースを取り消します。
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時、スナップショット・スペースを取り消します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のスナップショットを、確認を要求せず、即時に取り消します。

### ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

指定されたボリュームにスナップショットを作成します。
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --note</dt>
<dd>新規スナップショットに設定するメモ。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforbluemix
```
このコマンドは、ID 12345678 のボリュームのスナップショットを、snapshotforbluemix の追加メモと共に作成します。

### ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

指定されたスケジュールでの指定されたボリュームのスナップショットを無効にします。
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
このコマンドは、ID 12345678 のボリュームの毎日のスナップショットを無効にします。

### ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

指定されたスケジュールで指定されたボリュームのスナップショットを有効にします。
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-c, --retention-count</dt>
<dd>必須。 保持するスナップショットの数。</dd>
<dt>-m, --minute</dt>
<dd>スナップショットを作成する時刻の分の部分。0 から 59 までの整数。</dd>
<dt>-r, --hour</dt>
<dd>スナップショットを作成する時刻の時の部分。0 から 23 までの整数。</dd>
<dt>-d, --day-of-week</dt>
<dd>スナップショットを作成する曜日。0 から 6 までの整数。 0 は日曜、1 は月曜、2 は火曜、3 は水曜、4 は木曜、5 は金曜、6 は土曜を表します。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
このコマンドは、ID 12345678 のボリュームのスナップショットを有効にします。スナップショットは、毎週日曜日の 2:00 に取られ、最高 5 個のスナップショットが保持されます。

### ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

指定されたボリュームのスナップショットを削除します。
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**例**:
```
ibmcloud sl block snapshot-delete 12345678
```
このコマンドは、ID 12345678 のスナップショットを削除します。

### ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

ブロック・ストレージ・スナップショットをリストします。
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、created、size_bytes。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームのすべてのスナップショットをリストし、それらを ID によってソートします。

### ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

ブロック・ストレージ・ボリュームのスナップショット・スペースを注文します。
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --size</dt>
<dd>必須。 作成するスナップショット・スペースのサイズ (GB 単位)。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 スペースを注文するブロック・ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。</dd>
<dt>-u, --upgrade</dt>
<dd>この注文がアップグレードであることを示すフラグを立てます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
このコマンドは、ID 12345678 のボリュームのスナップショット・スペースを注文します。サイズは 1000 GB、階層レベルは 1 GB 当たり 4 IOPS です。

### ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

指定されたスナップショットを使用してブロック・ボリュームをリストアします。
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**例**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームを、ID 87654321 のスナップショットからリストアします。

### ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

既存のブロック・ストレージ・ボリュームを取り消します。
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時、ブロック・ストレージ・ボリュームを取り消します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のボリュームを、確認を要求せず、即時に取り消します。

### ibmcloud sl block volume-list
{: #sl_block_volume_list}

ブロック・ストレージをリストします。
```
ibmcloud sl block volume-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-u, --username</dt>
<dd>ボリュームのユーザー名を基準にフィルター操作します。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-t, --storage-type</dt>
<dd>ストレージ・ボリュームのタイプを基準にフィルター操作します。オプション: performance、endurance。</dd>
<dt>-o, --order</dt>
<dd>ブロック・ストレージを購入した注文の ID を基準にフィルター操作します。</dd>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions、created_by。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、created_by。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
このコマンドは、dal09 にある、現行アカウントのすべてのエンデュランス・ボリュームをリストし、それらを容量によってソートします。

### ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

指定されたボリュームの詳細を表示します。
```
ibmcloud sl block volume-detail VOLUME_ID
```


**例**:
```
ibmcloud sl block volume-detail 12345678
```
このコマンドは、ID 12345678 のボリュームの詳細を表示します。

### ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

既存のボリュームを複写してブロック・ボリュームを注文します。
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>重複に使用する元のボリュームのスナップショットの ID。</dd>
<dt>-s, --duplicate-size</dt>
<dd>重複ブロック・ボリュームのサイズ (GB)。サイズが指定されない場合、元のボリュームのサイズが使用されます。</dd>
<dt>-i, --duplicate-iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-t, --duplicate-tier</dt>
<dd>エンデュランス・ストレージ層。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>重複用に注文するスナップショット・スペースのサイズ。スナップショット・スペース・サイズが指定されない場合、元のボリュームのスナップショット・スペース・サイズが使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-duplicate 12345678
```
このコマンドは、ID 12345678 のボリュームを複写して新規ボリュームを注文します。

### ibmcloud sl block volume-order
{: #sl_block_volume_order}

ブロック・ストレージ・ボリュームを注文します。
```
ibmcloud sl block volume-order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>必須。 ストレージ・ボリュームのタイプ。オプション: performance、endurance。</dd>
<dt>-s, --size</dt>
<dd>必須。 ストレージ・ボリュームのサイズ (GB)。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージの IOP (100 から 6000 までの範囲内の 100 の倍数) [storage-type が performance の場合は必須]。</dd>
<dt>-e, --tier</dt>
<dd>エンデュランス・ストレージ層 (GB 当たりの IOP) [storage-type が endurance の場合は必須]。オプションは、0.25、2、4、10 です。</dd>
<dt>-o, --os-type</dt>
<dd>必須。 オペレーティング・システム。オプション: HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS、XEN。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-n, --snapshot-size</dt>
<dd>エンデュランス・ブロック・ストレージと共にスナップショット・スペースを注文するためのオプション・パラメーター。注文するスナップショット・スペースのサイズ (GB) を指定します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
このコマンドは、サイズが 1000 GB、IOPS が 4000、OS タイプが LINUX、ロケーションが dal09 のパフォーマンス・ボリュームを注文します。

### ibmcloud sl block volume-options
{: #sl_block_volume_options}

ブロック・ストレージの注文に関するすべてのオプションをリストします。
```
ibmcloud sl block volume-options
```


**例**:
```
ibmcloud sl block volume-options
```
このコマンドは、ブロック・ストレージ・ボリュームの作成に関するすべてのオプション (ストレージ・タイプ、ボリューム・サイズ、OS タイプ、IOPS、階層レベル、データ・センター、およびスナップショット・サイズ) をリストします。

### ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

CDN アカウントを取り消します。
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
### ibmcloud sl cdn detail
{: #sl_cdn_detail}

CDN アカウントの詳細を表示します。
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
{: #sl_cdn_list}

すべての CDN アカウントをリストします。
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、type、created。</dd>
<dt>--order</dt>
<dd>注文 ID でフィルター操作します。</dd>
</dl>
### ibmcloud sl cdn load
{: #sl_cdn_load}

すべてのエッジ・ノード上で 1 つ以上のファイルをキャッシュに入れます。
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

CDN アカウントを注文します。
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN 処理能力。指定されていなければ、「従量課金 (PAYG)」価格が使用されます。</dd>
<dt>-s, --storage</dt>
<dd>CDN ストレージ。指定されていなければ、「従量課金 (PAYG)」価格が使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
### ibmcloud sl cdn options
{: #sl_cdn_options}

CDN アカウントを注文する際の処理能力とストレージのオプション。
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Origin Pull マッピングを作成します。
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --type</dt>
<dd>このマッピングのメディア・タイプ (http、flash、wm、...)。デフォルト: http。</dd>
<dt>-c, --cname</dt>
<dd>マッピングに付加する CNAME (オプション)。</dd>
</dl>
### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Origin Pull マッピングをリストします。
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Origin Pull マッピングを削除します。
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
### ibmcloud sl cdn purge
{: #sl_cdn_purge}

すべてのエッジ・ノードからキャッシュされているファイルをパージします。
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
### ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

指定されたボリュームへのホストのアクセスを許可します。
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>許可する 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>許可する 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>許可する 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>許可する IP アドレス。</dd>
<dt>-s, --subnet-id</dt>
<dd>許可する 1 つのサブネットの ID。</dd>
</dl>

**例**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーが、ID 12345678 のボリュームにアクセスすることを許可します。

### ibmcloud sl file access-list
{: #sl_file_access_list}

ACL をリストします。
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
</dl>

**例**:
```
ibmcloud sl file access-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームへのアクセスを許可されているすべてのホストをリストし、それらを ID によってソートします。

### ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

指定されたボリュームにアクセスするホストの許可を取り消します。
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>取り消す 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>取り消す 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>取り消す 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>取り消す IP アドレス。</dd>
<dt>-s, --subnet-id</dt>
<dd>取り消す 1 つのサブネットの ID。</dd>
</dl>

**例**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーの、ID 12345678 のボリュームへのアクセスを取り消します。

### ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

レプリカからファイル・ボリュームをフェイルバックします。
```
ibmcloud sl file replica-failback VOLUME_ID
```


**例**:
```
ibmcloud sl file replica-failback 12345678
```
このコマンドは、ID 12345678 のボリュームのフェイルバック操作を実行します。

### ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

ファイル・ボリュームを、指定されたレプリカ・ボリュームにフェイルオーバーします。
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**例**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームの、ID 87654321 のレプリカ・ボリュームへのフェイルオーバー操作を実行します。

### ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

指定されたボリュームに適切な複製データ・センターをリストします。
```
ibmcloud sl file replica-locations VOLUME_ID
```


**例**:
```
ibmcloud sl file replica-locations 12345678
```
このコマンドは、ID 12345678 のファイル・ボリュームの適切な複製データ・センターをリストします。

### ibmcloud sl file replica-order
{: #sl_file_replica_order}

ファイル・ストレージ・レプリカ・ボリュームを注文します。
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>必須。 複製に使用するスナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 複製用のデータ・センターの短縮名。例えば、dal09 など。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 レプリカを注文する 1 次ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
このコマンドは、ID 12345678 のボリュームのレプリカを注文します。このレプリカは、毎日の複製を実行し、dal09 にあり、層レベルは 4 です。

### ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

ファイル・ボリュームの既存のレプリカ・ボリュームをリストします。
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONS]
```


**例**:
```
ibmcloud sl file replica-partners 12345678
```
このコマンドは、ID 12345678 のファイル・ボリュームの既存のレプリカ・ボリュームをリストします。

### ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

指定されたボリュームの既存のスナップショット・スペースを取り消します。
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時、スナップショット・スペースを取り消します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のスナップショットを、確認を要求せず、即時に取り消します。

### ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

指定されたボリュームにスナップショットを作成します。
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --note</dt>
<dd>新規スナップショットに設定するメモ。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforbluemix
```
このコマンドは、ID 12345678 のボリュームのスナップショットを、snapshotforbluemix の追加メモと共に作成します。

### ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

指定されたスケジュールでの指定されたボリュームのスナップショットを無効にします。
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
このコマンドは、ID 12345678 のボリュームの毎日のスナップショットを無効にします。

### ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

指定されたスケジュールで指定されたボリュームのスナップショットを有効にします。
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-c, --retention-count</dt>
<dd>必須。 保持するスナップショットの数。</dd>
<dt>-m, --minute</dt>
<dd>スナップショットを作成する時刻の分の部分。0 から 59 までの整数。</dd>
<dt>-r, --hour</dt>
<dd>スナップショットを作成する時刻の時の部分。0 から 23 までの整数。</dd>
<dt>-d, --day-of-week</dt>
<dd>スナップショットを作成する曜日。0 から 6 までの整数。 0 は日曜、1 は月曜、2 は火曜、3 は水曜、4 は木曜、5 は金曜、6 は土曜を表します。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
このコマンドは、ID 12345678 のボリュームのスナップショットを有効にします。スナップショットは、毎週日曜日の 2:00 に取られ、最高 5 個のスナップショットが保持されます。

### ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

指定されたボリュームのスナップショットを削除します。
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**例**:
```
ibmcloud sl file snapshot-delete 12345678
```
このコマンドは、ID 12345678 のスナップショットを削除します。

### ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

ファイル・ストレージ・スナップショットをリストします。
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、created、size_bytes。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームのすべてのスナップショットをリストし、それらを ID によってソートします。

### ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

ファイル・ストレージ・ボリュームのスナップショット・スペースを注文します。
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --size</dt>
<dd>必須。 作成するスナップショット・スペースのサイズ (GB 単位)。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 スペースの注文対象であるファイル・ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。</dd>
<dt>-u, --upgrade</dt>
<dd>この注文がアップグレードであることを示すフラグを立てます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
このコマンドは、ID 12345678 のボリュームのスナップショット・スペースを注文します。サイズは 1000 GB、階層レベルは 1 GB 当たり 4 IOPS です。

### ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

指定されたスナップショットを使用してファイル・ボリュームをリストアします。
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**例**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームを、ID 87654321 のスナップショットからリストアします。

### ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

既存のファイル・ストレージ・ボリュームを取り消します。
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時、ファイル・ストレージ・ボリュームを取り消します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のボリュームを、確認を要求せず、即時に取り消します。

### ibmcloud sl file volume-list
{: #sl_file_volume_list}

ファイル・ストレージをリストします。
```
ibmcloud sl file volume-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-u, --username</dt>
<dd>ボリュームのユーザー名を基準にフィルター操作します。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-t, --storage-type</dt>
<dd>ストレージ・ボリュームのタイプを基準にフィルター操作します。オプション: performance、endurance。</dd>
<dt>-o, --order</dt>
<dd>ファイル・ストレージを購入した注文の ID を基準にしてフィルター操作します。</dd>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions、mount_addr。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、mount_addr。</dd>
</dl>

**例**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
このコマンドは、dal09 にある、現行アカウントのすべてのエンデュランス・ボリュームをリストし、それらを容量によってソートします。

### ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

指定されたボリュームの詳細を表示します。
```
ibmcloud sl file volume-detail VOLUME_ID
```


**例**:
```
ibmcloud sl file volume-detail 12345678
```
このコマンドは、ID 12345678 のボリュームの詳細を表示します。

### ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

既存のボリュームを複写してファイル・ボリュームを注文します。
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>重複に使用する元のボリュームのスナップショットの ID。</dd>
<dt>-s, --duplicate-size</dt>
<dd>重複ファイル・ボリュームのサイズ (GB)。サイズが指定されない場合、元のボリュームのサイズが使用されます。</dd>
<dt>-i, --duplicate-iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-t, --duplicate-tier</dt>
<dd>エンデュランス・ストレージ層。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>重複用に注文するスナップショット・スペースのサイズ。スナップショット・スペース・サイズが指定されない場合、元のボリュームのスナップショット・スペース・サイズが使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file volume-duplicate 12345678
```
このコマンドは、ID 12345678 のボリュームを複写して新規ボリュームを注文します。

### ibmcloud sl file volume-order
{: #sl_file_volume_order}

ファイル・ストレージ・ボリュームを注文します。
```
ibmcloud sl file volume-order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>必須。 ストレージ・ボリュームのタイプ。オプション: performance、endurance。</dd>
<dt>-s, --size</dt>
<dd>必須。 ストレージ・ボリュームのサイズ (GB)。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージの IOP (100 から 6000 までの範囲内の 100 の倍数) [storage-type が performance の場合は必須]。</dd>
<dt>-e, --tier</dt>
<dd>エンデュランス・ストレージ層 (GB 当たりの IOP) [storage-type が endurance の場合は必須]。オプションは、0.25、2、4、10 です。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-n, --snapshot-size</dt>
<dd>ボリュームと共にスナップショット・スペースを注文するためのオプション・パラメーター。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
このコマンドは、サイズが 1000 GB、IOPS が 4000、ロケーションが dal09 のパフォーマンス・ボリュームを注文します。

### ibmcloud sl file volume-options
{: #sl_file_volume_options}

ファイル・ストレージの注文に関するすべてのオプションをリストします。
```
ibmcloud sl file volume-options
```


**例**:
```
ibmcloud sl file volume-options
```
このコマンドは、ファイル・ストレージ・ボリュームの作成に関するすべてのオプション (ストレージ・タイプ、ボリューム・サイズ、IOPS、層レベル、データ・センター、およびスナップショット・サイズ) をリストします。

### ibmcloud sl dns import
{: #sl_dns_import}

BIND ゾーン・ファイルに基づいてゾーンをインポートします。
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--dry-run</dt>
<dd>実際にはレコードを作成しません。</dd>
</dl>

**例**:
```
ibmcloud sl dns import ~/blumix.net.txt
```
このコマンドは、ファイル ~/blumix.net.txt からゾーンとそのリソース・レコードをインポートします。

### ibmcloud sl dns record-add
{: #sl_dns_record_add}

ゾーン内のリソース・レコードを追加します。
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL(Time-To-Live (存続時間)) (秒)。例えば、86400 など。デフォルト: 7200。</dd>
</dl>

**例**:
```
ibmcloud sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
このコマンドは、A レコードをゾーン bluemix.net に追加します。ホストは「ftp」、データは「127.0.0.1」、および ttl は 86400 秒です。

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

ゾーン内のリソース・レコードを更新します
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--by-record</dt>
<dd>ホスト・レコード (www など) で編集します。</dd>
<dt>--by-id</dt>
<dd>単一レコードをその ID で編集します。</dd>
<dt>--data</dt>
<dd>レコード・データ (IP アドレスなど)。</dd>
<dt>--ttl</dt>
<dd>TTL 値 (秒) (例: 86400)。</dd>
</dl>

**例**:
```
ibmcloud sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
このコマンドは、ゾーン bluemix.net のレコードを編集します。ID は 12345678 です。データを「127.0.0.2」に設定し、ttl を 3600 に設定します。

### ibmcloud sl dns record-list
{: #sl_dns_record_list}

ゾーン内のすべてのリソース・レコードをリストします。
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--data</dt>
<dd>レコード・データ (IP アドレスなど) を基準にフィルター操作します。</dd>
<dt>--record</dt>
<dd>ホスト・レコード (www など) を基準にフィルター操作します。</dd>
<dt>--ttl</dt>
<dd>TTL 値 (秒) (例: 86400) を基準にフィルター操作します。</dd>
<dt>--type</dt>
<dd>レコード・タイプ (A または CNAME など) を基準にフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
このコマンドは、ゾーン bluemix.net のすべての A レコードをリストします。フィルター基準ホストは elasticsearch で TTL は 900 秒です。

### ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

ゾーンからリソース・レコードを削除します。
```
ibmcloud sl dns record-remove RECORD_ID
```


**例**:
```
ibmcloud sl dns record-remove 12345678
```
このコマンドは、ID 12345678 のリソース・レコードを削除します。

### ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

ゾーンを作成します。
```
ibmcloud sl dns zone-create ZONE
```


**例**:
```
ibmcloud sl dns zone-create bluemix.net
```
このコマンドは、bluemix.net という名前のゾーンを作成します。

### ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

ゾーンを削除します。
```
ibmcloud sl dns zone-delete ZONE
```


**例**:
```
ibmcloud sl dns zone-delete bluemix.net
```
このコマンドは、bluemix.net という名前のゾーンを削除します。

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

ユーザーのアカウントのすべてのゾーンをリストします。
```
ibmcloud sl dns zone-list
```


**例**:
```
ibmcloud sl dns zone-list
```
このコマンドは、現行アカウントにあるすべてのゾーンをリストします。

### ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

ゾーンおよびリソース・レコードを BIND フォーマットで出力します。
```
ibmcloud sl dns zone-print ZONE
```


**例**:
```
ibmcloud sl dns zone-print bluemix.net
```
このコマンドは、bluemix.net という名前のゾーンを BIND フォーマットで出力します。

### ibmcloud sl globalip create
{: #sl_globalip_create}

グローバル IP を作成します。
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--v6</dt>
<dd>IPv6 IP アドレスを注文します。</dd>
<dt>--test</dt>
<dd>テストの注文。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl globalip create --v6
```
このコマンドは、IP V6 アドレスを作成します。

### ibmcloud sl globalip assign
{: #sl_globalip_assign}

グローバル IP をターゲットのルーターまたはデバイスに割り当てます。
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**例**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
このコマンドは、ID 12345678 の IP アドレスを、IP アドレス 9.111.123.456 のターゲット・デバイスに割り当てます。

### ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

グローバル IP を取り消します。
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl globalip cancel 12345678
```
このコマンドは、ID 12345678 の IP アドレスを取り消します。

### ibmcloud sl globalip list
{: #sl_globalip_list}

アカウントのすべてのグローバル IP をリストします。
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--v4</dt>
<dd>IPv4 IP のみを表示します。</dd>
<dt>--v6</dt>
<dd>IPv6 IP のみを表示します。</dd>
<dt>--order</dt>
<dd>この IP アドレスを購入した注文の ID を基準にしてフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl globalip list --v4
```
このコマンドは、現行アカウントのすべての IP V4 アドレスをリストします。

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

ターゲットのルーターまたはデバイスからグローバル IP を割り当て解除します。
```
ibmcloud sl globalip unassign IDENTIFIER
```


**例**:
```
ibmcloud sl globalip unassign 12345678
```
このコマンドは、ID 12345678 の IP アドレスをターゲット・デバイスから割り当て解除します。

### ibmcloud sl image delete
{: #sl_image_delete}

イメージを削除します。
```
ibmcloud sl image delete IDENTIFIER
```
**例**:
```
   ibmcloud sl image delete 12345678
```
このコマンドは、ID `12345678` のイメージを削除します。

### ibmcloud sl image detail
{: #sl_image_detail}

イメージの詳細を取得します。
```
ibmcloud sl image detail IDENTIFIER
```
**例**:
```
 ibmcloud sl image detail 12345678
```
このコマンドは、ID 12345678 のイメージの詳細を取得します。

### ibmcloud sl image edit
{: #sl_image_edit}

イメージの詳細を編集します。
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--name</dt>
<dd>イメージの名前。</dd>
<dt>--note</dt>
<dd>イメージの追加のメモ。</dd>
<dt>--tag</dt>
<dd>イメージのタグ。</dd>
</dl>

*例**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
このコマンドは、ID `12345678` のイメージを編集し、名前を「`ubuntu16`」に設定し、メモを「`testing`」に設定し、タグを「`staging`」に設定します。

### ibmcloud sl image list
{: #sl_image_list}

ご使用のアカウントのすべてのイメージをリストします。
```
ibmcloud sl image list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--name</dt>
<dd>イメージ名を基準にフィルター操作します。</dd>
<dt>--public</dt>
<dd>パブリック・イメージのみを表示します。</dd>
<dt>--private</dt>
<dd>プライベート・イメージのみを表示します。</dd>
</dl>

### ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

IPSec VPN トンネル・コンテキストを取り消します。
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時に、IPSec を取り消します。</dd>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl ipsec config
{: #sl_ipsec_config}

トンネル・コンテキストの構成を要求します。
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

### ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

IPSec VPN トンネル・コンテキストの詳細をリストします。
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-i, --include</dt>
<dd>追加リソースを組み込みます。オプション: at、is、rs、sr、ss。</dd>
</dl>
### ibmcloud sl ipsec list
{: #sl_ipsec_list}

IPSec VPN トンネル・コンテキストをリストします。
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--order</dt>
<dd>IPSEC を購入した注文の ID を基準にフィルター操作します。</dd>
</dl>
### ibmcloud sl ipsec order
{: #sl_ipsec_order}

IPSec VPN トンネルを注文します。
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>必須。 IPSEC 用のデータ・センターの短縮名。例えば、dal09 など。</dd>
</dl>

### ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

IPSec トンネル・コンテキストにサブネットを追加します。
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>追加するサブネット ID (必須)。</dd>
<dt>-t, --subnet-type</dt>
<dd>追加するサブネット・タイプ (必須)。オプション: internal、remote、service。</dd>
<dt>-n, --network</dt>
<dd>作成するサブネット・ネットワーク ID。</dd>
</dl>

### ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

IPSEC トンネル・コンテキストからサブネットを削除します。
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

### ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

IPSec トンネルにアドレス変換を追加します。
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>静的 IP アドレス (必須)。</dd>
<dt>-r, --remote-ip</dt>
<dd>リモート IP アドレス (必須)。</dd>
<dt>-n, --note</dt>
<dd>注。</dd>
</dl>
### ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

IPSec から変換入力を削除します。
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

### ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

IPSec のアドレス変換を更新します。
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>静的 IP アドレス (必須)。</dd>
<dt>-r, --remote-ip</dt>
<dd>リモート IP アドレス (必須)。</dd>
<dt>-n, --note</dt>
<dd>注。</dd>
</dl>
### ibmcloud sl ipsec update
{: #sl_ipsec_update}

トンネル・コンテキストのプロパティーを更新します。
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>分かりやすい名前。</dd>
<dt>-r, --remote-peer</dt>
<dd>リモート・ピア IP アドレス。</dd>
<dt>-k, --preshared-key</dt>
<dd>事前共有鍵。</dd>
<dt>-a, --phase1-auth</dt>
<dd>フェーズ 1 認証。オプション: MD5、SHA1、SHA256。</dd>
<dt>-c, --phase1-crypto</dt>
<dd>フェーズ 1 暗号化。オプション: DES、3DES、AES128、AES192、AES256。</dd>
<dt>-d, --phase1-dh</dt>
<dd>フェーズ 1 Diffie-Hellman グループ。オプション: 0、1、2、5。</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>フェーズ 1 鍵存続時間。範囲: 120-172800。</dd>
<dt>-u, --phase2-auth</dt>
<dd>フェーズ 2 認証。オプション: MD5、SHA1、SHA256。</dd>
<dt>-y, --phase2-crypto</dt>
<dd>フェーズ 2 暗号化。オプション: DES、3DES、AES128、AES192、AES256。</dd>
<dt>-e, --phase2-dh</dt>
<dd>フェーズ 2 Diffie-Hellman グループ。オプション: 0、1、2、5。</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>フェーズ 2 Perfect Forward Secrecy。範囲: 0-1。</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>フェーズ 2 鍵存続時間。範囲: 120-172800。</dd>
</dl>

### ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

既存のロード・バランサーを取り消します。
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

create-options から返された ID を指定してロード・バランサーを追加します。
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

ロード・バランサーの作成に使用する価格オプションを取得します。
```
ibmcloud sl loadbal create-options
```

### ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

ロード・バランサーの詳細を取得します。
```
ibmcloud sl loadbal detail LOADBAL_ID
```

### ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

新規ロード・バランサー・サービスを追加します。
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>必須。 接続の割り振り済みパーセント。</dd>
<dt>-p, --port</dt>
<dd>必須。 ポート番号。</dd>
<dt>-t, --routing-type</dt>
<dd>必須。 ルーティング・タイプの ID。 ID を検出するには、「ibmcloud sl loadbal routing-types」を実行します。</dd>
<dt>-m, --routing-method</dt>
<dd>必須。 ルーティング・メソッドの ID。 ID を検出するには、「ibmcloud sl loadbal routing-methods」を実行します。</dd>
</dl>

### ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

既存のロード・バランサー・サービス・グループを削除します。
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

既存のロード・バランサー・サービス・グループを編集します。
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>接続の割り振り済みパーセントを変更します。</dd>
<dt>-p, --port</dt>
<dd>ポート番号を変更します。</dd>
<dt>-t, --routing-type</dt>
<dd>ルーティング・タイプの ID を変更します。 ID を検出するには、「ibmcloud sl loadbal routing-types」を実行します。</dd>
<dt>-m, --routing-method</dt>
<dd>ルーティング方式の ID を変更します。 ID を検出するには、「ibmcloud sl loadbal routing-methods」を実行します。</dd>
</dl>

### ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

特定のサービス・グループでの接続をリセットします。
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

ヘルス・チェック・タイプをリストします。
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

アクティブなロード・バランサーをリストします。
```
ibmcloud sl loadbal list
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-o, --order</dt>
<dd>ロード・バランサーを購入した注文の ID を基準にフィルター操作します。</dd>
<dt>-p, --ip-address</dt>
<dd>IP アドレスを基準にしてフィルター操作します。</dd>
</dl>
### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

ルーティング・メソッドをリストします。
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

ルーティング・タイプをリストします。
```
ibmcloud sl loadbal routing-types
```

### ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

新規のロード・バランサー・サービスを追加します。
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--disabled</dt>
<dd>オプション。 disabled としてサービスを作成します。指定されていない場合、デフォルトは enabled です。</dd>
<dt>-p, --port</dt>
<dd>必須。 サービスのポート番号。</dd>
<dt>-w, --weight</dt>
<dd>必須。 サービスの重み。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>必須。 ヘルス・チェック・タイプ。</dd>
<dt>-i, --ip-address</dt>
<dd>必須。 サービスの IP アドレス。</dd>
</dl>

### ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

既存のロード・バランサー・サービスを削除します。
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

サービス・グループのプロパティーを編集します。
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--disabled</dt>
<dd>サービスを無効にします。</dd>
<dt>--enabled</dt>
<dd>サービスを有効にします。</dd>
<dt>-p, --port</dt>
<dd>サービスのポート番号を変更します。</dd>
<dt>-w, --weight</dt>
<dd>サービスの重みを変更します。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>ヘルス・チェック・タイプを変更します。</dd>
<dt>-i, --ip-address</dt>
<dd>サービスの IP アドレスを変更します。</dd>
</dl>

### ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

既存のロード・バランサー・サービスの状況を切り替えます。
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

新規の SSH 鍵を追加します。
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>この鍵のためにインポートする id_rsa.pub ファイル。</dd>
<dt>-k, --key</dt>
<dd>実際の SSH 鍵。</dd>
<dt>--note</dt>
<dd>鍵に関連付けられる追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
このコマンドは、ファイル ~/.ssh/id_rsa.pub から SSH 鍵を、メモ「mykey」を付けて追加します。

### ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH 鍵を編集します。
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--label</dt>
<dd>鍵の新しいラベル。</dd>
<dt>--note</dt>
<dd>鍵についての新しいメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
このコマンドは、ID 12345678 の SSH 鍵を更新し、ラベルを「Bluemix」に設定し、メモを「testing」に設定します。

### ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

ご使用のアカウントの SSH 鍵をリストします。
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、label、fingerprint、notes。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-list --sortby label
```
このコマンドは、現行アカウントのすべての SSH 鍵をリストし、それらをラベルによってソートします。

### ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

SSH 鍵を画面に出力します。
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>SSH 公開鍵は、このファイルに書き込まれます。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
このコマンドは、ID 12345678 の SSH 鍵の ID、ラベル、およびメモを表示し、公開鍵をファイル ~/mykey.pub に書き込みます。

### ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

SSH 鍵を永久に削除します。
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
このコマンドは、ID 12345678 の SSH 鍵を、確認を求めずに削除します。

### ibmcloud sl security cert-add
{: #sl_security_cert_add}

SSL 証明書の詳細を追加してアップロードします。
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--crt</dt>
<dd>証明書ファイル。</dd>
<dt>--csr</dt>
<dd>証明書署名要求ファイル。</dd>
<dt>--icc</dt>
<dd>中間証明書ファイル。</dd>
<dt>--key</dt>
<dd>秘密鍵ファイル。</dd>
<dt>--notes</dt>
<dd>追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key
```
このコマンドは、ドメイン bluemix.net の証明書ファイル ~/bluemix.net.cert と秘密鍵ファイル ~/bluemix.net.key を追加します。

### ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

SSL 証明書を編集します。
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--crt</dt>
<dd>証明書ファイル。</dd>
<dt>--csr</dt>
<dd>証明書署名要求ファイル。</dd>
<dt>--icc</dt>
<dd>中間証明書ファイル。</dd>
<dt>--key</dt>
<dd>秘密鍵ファイル。</dd>
<dt>--notes</dt>
<dd>追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-edit 12345678 --key ~/bluemix.net.key
```
このコマンドは、ID 12345678 の証明書を編集し、ファイル ~/bluemix.net.key でその秘密鍵を更新します。

### ibmcloud sl security cert-download
{: #sl_security_cert_download}

SSL 証明書および鍵ファイルをダウンロードします。
```
ibmcloud sl security cert-download IDENTIFIER
```


**例**:
```
ibmcloud sl security cert-download 12345678
```
このコマンドは、現行ディレクトリーに ID 12345678 の証明書に関する 4 つのファイルをダウンロードします。 4 つのファイルというのは、証明書ファイル、証明書署名要求ファイル、中間証明書ファイル、および秘密鍵ファイルです。

### ibmcloud sl security cert-list
{: #sl_security_cert_list}

ご使用のアカウントの SSL 証明書をリストします。
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--status</dt>
<dd>指定の状況の証明書を表示します。デフォルトは all です。オプション: all、valid、expired。</dd>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、common_name、days_until_expire、notes。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
このコマンドは、現行アカウントのすべての有効な証明書をリストし、それらを有効期限日によってソートします。

### ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

SSL 証明書を削除します。
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-remove 12345678
```
このコマンドは、ID 12345678 の証明書を削除します。

### ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

サブネットを取り消します。
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet cancel 12345678 -f
```
このコマンドは、ID 12345678 のサブネットを、確認を求めずに取り消します。

### ibmcloud sl subnet create
{: #sl_subnet_create}

ご使用のアカウントに新規サブネットを追加します。
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>IPv6 アドレスを注文します。</dd>
<dt>--test</dt>
<dd>サブネットを注文せず、見積もりを取るだけです。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet create public 16 567
```
このコマンドは、16 個の IPv4 アドレスを持つパブリック・サブネットを作成し、ID 567 の VLAN に配置します。

### ibmcloud sl subnet detail
{: #sl_subnet_detail}

サブネットの詳細を取得します。
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--no-vs</dt>
<dd>仮想サーバー・リストを非表示にします。</dd>
<dt>--no-hardware</dt>
<dd>ハードウェア・リストを非表示にします。</dd>
</dl>

**例**:
```
ibmcloud sl subnet detail 12345678
```
このコマンドは、仮想サーバーおよびハードウェア・サーバーの情報を含め、ID 12345678 のサブネットに関する詳細情報を表示します。

### ibmcloud sl subnet list
{: #sl_subnet_list}

ご使用のアカウントのすべてのサブネットをリストします。
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準にする列。 オプション: id、identifier、type、network_space、datacenter、vlan_id、IPs、hardware、vs。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>--identifier</dt>
<dd>ネットワーク ID を基準にフィルター操作します。</dd>
<dt>-t, --subnet-type</dt>
<dd>サブネット・タイプを基準にフィルター操作します。</dd>
<dt>--network-space</dt>
<dd>ネットワーク・スペースを基準にフィルター操作します。</dd>
<dt>--v4, --ipv4</dt>
<dd>IPv4 サブネットのみを表示します。</dd>
<dt>--v6, --ipv6</dt>
<dd>IPv6 サブネットのみを表示します。</dd>
<dt>--order</dt>
<dd>サブネットを購入した注文の ID を基準にフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
このコマンドは、現行アカウントの IP V4 サブネットをリストします。フィルター基準のデータ・センターは dal09、サブネット・タイプは PRIMARY、およびネットワーク・スペースは PUBLIC です。

### ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

IP アドレスを検出し、そのサブネットとデバイスの情報を表示します。
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**例**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
このコマンドは、アドレス 9.125.235.255 の IP アドレス・レコードを検出し、そのサブネットとデバイスの情報を表示します。

### ibmcloud sl vlan create
{: #sl_vlan_create}

新規 VLAN を作成します。
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>VLAN のタイプ。public または private のいずれか。</dd>
<dt>-r, --router</dt>
<dd>ルーターのホスト名。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名。</dd>
<dt>-s, --size</dt>
<dd>サブネットのサイズ。オプションは、8 (5 個の使用可能な IP)、16 (13 個の使用可能な IP)、または 32 (29 個の使用可能な IP) です。</dd>
<dt>-n, --name</dt>
<dd>VLAN の名前。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
このコマンドは、データ・センター dal09 に、16 個の IP アドレスを持ち、myvlan という名前のパブリック VLAN を作成します。

### ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

VLAN を取り消します。
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vlan cancel 12345678 -f
```
このコマンドは、ID 12345678 の VLAN を、確認を求めずに取り消します。

### ibmcloud sl vlan detail
{: #sl_vlan_detail}

VLAN についての詳細を取得します。
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--no-vs</dt>
<dd>仮想サーバー・リストを非表示にします。</dd>
<dt>--no-hardware</dt>
<dd>ハードウェア・リストを非表示にします。</dd>
</dl>

**例**:
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
このコマンドは、ID 12345678 の VLAN の詳細を表示し、仮想サーバーおよびハードウェア・サーバーをリストしません。

### ibmcloud sl vlan edit
{: #sl_vlan_edit}

VLAN についての詳細を編集します。
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>VLAN の名前。</dd>
</dl>

**例**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
このコマンドは、ID 12345678 の VLAN を更新し、それに新しい名前「myvlan-rename」を付けます。

### ibmcloud sl vlan list
{: #sl_vlan_list}

ご使用のアカウントのすべての VLAN をリストします。
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、number、name、firewall、datacenter、hardware、virtual_servers、public_ips。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-n, --number</dt>
<dd>VLAN 番号を基準にフィルター操作します。</dd>
<dt>--name</dt>
<dd>VLAN 名を基準にフィルター操作します。</dd>
<dt>--order</dt>
<dd>VLAN を購入した注文の ID を基準にフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
このコマンドは、現行アカウントのすべての VLAN をリストします。フィルター基準のデータ・センターは dal09 で、VLAN 番号によってソートします。

### ibmcloud sl vlan options
{: #sl_vlan_options}

VLAN の作成に関するすべてのオプションをリストします。
```
ibmcloud sl vlan options
```


**例**:
```
ibmcloud sl vlan options
```
このコマンドは、VLAN を作成するためのすべてのオプション (例えば、VLAN タイプ、データ・センター、サブネット・サイズ、ルーターなど) をリストします。

### ibmcloud sl vs cancel
{: #sl_vs_cancel}

仮想サーバー・インスタンスを取り消します。
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs cancel 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを取り消します。

### ibmcloud sl vs capture
{: #sl_vs_capture}

仮想サーバー・インスタンスをイメージに取り込みます。
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>必須。 イメージの名前。</dd>
<dt>--all</dt>
<dd>この VS に属しているすべてのディスクを取り込みます。</dd>
<dt>--note</dt>
<dd>このイメージに関連付けるメモを追加します。</dd>
</dl>

**例**:
```
ibmcloud sl vs capture 12345678 -n mybluemix --all --note testing
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをすべてのディスクと共に、「mybluemix」という名前のイメージに、「testing」というメモを付けて取り込みます。

### ibmcloud sl vs create
{: #sl_vs_create}

仮想サーバー・インスタンスを作成します。
```
ibmcloud sl vs create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>必須。 FQDN のホスト部分。</dd>
<dt>-D, --domain</dt>
<dd>必須。 FQDN のドメイン部分。</dd>
<dt>-c, --cpu</dt>
<dd>必須。 CPU コアの数。</dd>
<dt>-m, --memory</dt>
<dd>必須。 メモリー (M バイト)。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-o, --os</dt>
<dd>OS インストール・コード。 ヒント: <OS>_LATEST を指定できます。</dd>
<dt>--image</dt>
<dd>イメージ ID。 「ibmcloud sl image list」を参照してください。</dd>
<dt>--billing</dt>
<dd>請求レート。 デフォルトは hourly です。 オプション: hourly、monthly。</dd>
<dt>--dedicated</dt>
<dd>専用仮想サーバー (プライベート・ノード) を作成します。</dd>
<dt>--san</dt>
<dd>ローカル・ディスクの代わりに SAN ストレージを使用します。</dd>
<dt>--test</dt>
<dd>実際には仮想サーバーを作成しません。</dd>
<dt>--export</dt>
<dd>オプションをテンプレート・ファイルにエクスポートします。</dd>
<dt>-i, --postinstall</dt>
<dd>ダウンロードするインストール後スクリプト。</dd>
<dt>-k, --key</dt>
<dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)。</dd>
<dt>--disk</dt>
<dd>ディスク・サイズ (複数のオカレンスが許可されます)。</dd>
<dt>--private</dt>
<dd>仮想サーバーがプライベート・ネットワークのみにアクセスすることを強制します。</dd>
<dt>--like</dt>
<dd>既存の仮想サーバーからの構成を使用します。</dd>
<dt>-n, --network</dt>
<dd>ネットワーク・ポート速度 (Mbps)。</dd>
<dt>--tag</dt>
<dd>インスタンスに追加するタグ (複数のオカレンスが許可されます)。</dd>
<dt>-t, --template</dt>
<dd>コマンド・ライン・オプションをデフォルト設定するテンプレート・ファイル。</dd>
<dt>-u, --userdata</dt>
<dd>ユーザー定義のメタデータ・ストリング。</dd>
<dt>-F, --userfile</dt>
<dd>ユーザー・データをファイルから読み取ります。</dd>
<dt>--vlan-public</dt>
<dd>仮想サーバーを配置するパブリック VLAN の ID。</dd>
<dt>--vlan-private</dt>
<dd>仮想サーバーを配置するプライベート VLAN の ID。</dd>
<dt>--wait</dt>
<dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
このコマンドは、ホスト名 myvsi、ドメイン bluemix.net、cpu コア x 4、4096M メモリー、データ・センター dal10 で仮想サーバー・インスタンスを注文します。

### ibmcloud sl vs options
{: #sl_vs_options}

仮想サーバー・インスタンスの作成に関するオプションをリストします。
```
ibmcloud sl vs options [OPTIONS]
```


**例**:
```
ibmcloud sl vs options
```
このコマンドは、仮想サーバー・インスタンス (例えば、データ・センター、CPU、メモリー、OS、ディスク、ネットワーク速度など) を作成するためのすべてのオプションをリストします。

### ibmcloud sl vs credentials
{: #sl_vs_credentials}

仮想サーバー・インスタンスの資格情報をリストします。
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**例**:
```
ibmcloud sl vs credentials 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのユーザー名とパスワードのすべてのペアをリストします。

### ibmcloud sl vs detail
{: #sl_vs_detail}

仮想サーバー・インスタンスの詳細を取得します。
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--passwords</dt>
<dd>パスワードを表示します (他人に見られないように注意してください)。</dd>
<dt>--price</dt>
<dd>関連付けられた価格を表示します。</dd>
</dl>

**例**:
```
ibmcloud sl vs details 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスに関する詳細情報をリストします。

### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

仮想サーバー・インスタンスの DNS レコードを同期します。
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>ホストの A レコードを同期します。</dd>
<dt>--aaaa-record</dt>
<dd>ホストの AAAA レコードを同期します。</dd>
<dt>--ptr</dt>
<dd>ホストの PTR レコードを同期します。</dd>
<dt>--ttl</dt>
<dd>A レコードまたは PTR レコード、あるいは両方の TTL を設定します。デフォルトは 7200 です。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの A レコード (IP V4 アドレス) を DNS サーバーに同期し、この A レコードの TTL を 3600 に設定します。

### ibmcloud sl vs edit
{: #sl_vs_edit}

仮想サーバー・インスタンスの詳細を編集します。
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>FQDN のドメイン部分。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN のホスト部分。 例: server。</dd>
<dt>--tag</dt>
<dd>設定するタグ、または、すべて削除する場合は空ストリング。</dd>
<dt>-u, --userdata</dt>
<dd>ユーザー定義のメタデータ・ストリング。</dd>
<dt>-F, --userfile</dt>
<dd>ユーザー・データをファイルから読み取ります。</dd>
<dt>--public-speed</dt>
<dd>パブリック・ポート速度。オプション: 0、10、100、1000、10000。</dd>
<dt>--private-speed</dt>
<dd>プライベート・ポート速度。オプション: 0、10、100、1000、10000。</dd>
</dl>

**例**:
```
ibmcloud sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを更新し、ドメインを「bluemix.net」、ホスト名を「myapp」、タグを「testcli」に設定します。

### ibmcloud sl vs list
{: #sl_vs_list}

ご使用のアカウントの仮想サーバー・インスタンスをリストします。
```
ibmcloud sl vs list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU コアの数。</dd>
<dt>-D, --domain</dt>
<dd>FQDN のドメイン部分。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN のホスト部分。</dd>
<dt>-m, --memory</dt>
<dd>メモリー (M バイト)。</dd>
<dt>-n, --network</dt>
<dd>ネットワーク・ポート速度 (Mbps)。</dd>
<dt>--hourly</dt>
<dd>時間単位のインスタンスのみを表示します。</dd>
<dt>--monthly</dt>
<dd>月単位のインスタンスのみを表示します。</dd>
<dt>--tag</dt>
<dd>タグを基準にフィルター操作します (複数のオカレンスが許可されます)。</dd>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、hostname、domain、datacenter、cpu、memory、primary_ip、backend_ip。 デフォルト: hostname。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: guid、primary_ip、backend_ip、datacenter、action、power_state、created_by、tags。 デフォルト: id、hostname、primary_ip、backend_ip、datacenter、action。</dd>
</dl>

**例**:
```
ibmcloud sl vs list --domain bluemix.net --hourly --sortby memory
```
このコマンドは、現行アカウントの、時間ごとに請求されるすべての仮想サーバー・インスタンスをリストします。フィルター基準のドメインは「bluemix.net」で、それらをメモリーによってソートします。

### ibmcloud sl vs pause
{: #sl_vs_pause}

アクティブな仮想サーバー・インスタンスを一時停止します。
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs pause 12345678 -f
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを、確認を求めずに一時停止します。

### ibmcloud sl vs power-off
{: #sl_vs_power_off}

アクティブな仮想サーバー・インスタンスをパワーオフします。
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hard</dt>
<dd>ハード・シャットダウンを実行します。</dd>
<dt>--soft</dt>
<dd>ソフト・シャットダウンを実行します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs power-off 12345678 --soft
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのソフト・パワーオフを実行します。

### ibmcloud sl vs power-on
{: #sl_vs_power_on}

仮想サーバー・インスタンスをパワーオンします。
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs power-on 12345678
```
このコマンドは、ID 12345678 の仮想サーバーのパワーオンを実行します。

### ibmcloud sl vs ready
{: #sl_vs_ready}

仮想サーバー・インスタンスの使用準備ができているかどうかをチェックします。
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--wait</dt>
<dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります。</dd>
</dl>

**例**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
このコマンドは、ID 12345678 の仮想サーバーの状況をチェックして、そのインスタンスが、連続して使用する準備ができているかどうか確認し、最大 30 秒待機します。

### ibmcloud sl vs reboot
{: #sl_vs_reboot}

アクティブな仮想サーバー・インスタンスをリブートします。
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hard</dt>
<dd>ハード・リブートを実行します。</dd>
<dt>--soft</dt>
<dd>ソフト・リブートを実行します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs reboot 12345678 --hard
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのハード・リブートを実行します。

### ibmcloud sl vs reload
{: #sl_vs_reload}

仮想サーバー・インスタンス上でオペレーティング・システムを再ロードします。
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>ダウンロードするインストール後スクリプト。</dd>
<dt>--image</dt>
<dd>イメージ ID。 デフォルトは、現行オペレーティング・システムを使用することです。</dd>
<dt>以下を参照してください。</dt>
<dd>「ibmcloud sl image list」。</dd>
<dt>-k, --key</dt>
<dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs reload 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの現行オペレーティング・システムを再ロードします。

### ibmcloud sl vs rescue
{: #sl_vs_rescue}

仮想サーバー・インスタンスをレスキュー・イメージでリブートします。
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs rescue 12345678
```
このコマンドは、ID 12345678 の仮想サーバーをレスキュー・イメージでリブートします。

### ibmcloud sl vs resume
{: #sl_vs_resume}

一時停止された仮想サーバー・インスタンスを再開します。
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs resume 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを再開します。

### ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

仮想サーバー・インスタンスを更新します。
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU コアの数。</dd>
<dt>--private</dt>
<dd>CPU コアは、専用ホスト・サーバーに置かれます。</dd>
<dt>-m, --memory</dt>
<dd>メモリー (M バイト)。</dd>
<dt>--network</dt>
<dd>ネットワーク・ポート速度 (Mbps)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをアップグレードし、CPU コア数を 8、メモリーを 8192 M、ネットワーク・ポート速度を 1000 Mbps に設定します。
