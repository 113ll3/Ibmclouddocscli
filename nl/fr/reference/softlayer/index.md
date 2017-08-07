---

copyright:

  years: 2016,2017

lastupdated: "2017-06-07"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Commandes {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl)
{: #softlayer_cli}

Le plug-in {{site.data.keyword.BluSoftlayer}} a été fusionné dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Vous n'avez plus besoin d'installer le plug-in.

Utilisez les commandes {{site.data.keyword.BluSoftlayer_notm}} dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} pour configurer et gérer vos services SoftLayer.


Pour commencer, installez l'interface de ligne de commande IBM {{site.data.keyword.Bluemix_notm}}. Voir le site
[Interface de ligne de commande Bluemix ![External link icon](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} pour obtenir plus d'informations.

Pour obtenir une liste complète de commandes {{site.data.keyword.Bluemix_notm}}, voir : [Commandes {{site.data.keyword.Bluemix_notm}} (bx)](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)


## Commandes {{site.data.keyword.BluSoftlayer_notm}} générales

Les commandes ci-après sont prises en charge. Utilisez la commande `bluemix sl` pour voir la liste des commandes disponibles :

<table summary="Commandes générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Table 1. Commandes Softlayer générales</caption>
 <thead>
 <th colspan="6">Commandes Softlayer générales</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## Commandes de stockage par blocs {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Table 2. Stockage par blocs Softlayer</caption>
 <thead>
 <th colspan="6">Stockage par blocs Softlayer</th>
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

## Commandes dns {{site.data.keyword.BluSoftlayer_notm}}

<table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Table 3. Commandes dns Softlayer</caption>
 <thead>
 <th colspan="6">Commandes dns Softlayer</th>
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

<table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 4. Adresses IP globales Softlayer</caption>
 <thead>
 <th colspan="6">Adresses IP globales Softlayer</th>
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

## Commandes d'image {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 5. Commandes d'image Softlayer</caption>
 <thead>
 <th colspan="6">Commandes d'image Softlayer</th>
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
 
## Commandes de stockage iSCSI existantes {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 6. Commandes de stockage iSCSI existantes Softlayer</caption>
 <thead>
 <th colspan="6">Commandes de stockage iSCSI existantes Softlayer</th>
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

## Commandes de sécurité {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 7. Commandes de sécurité Softlayer</caption>
 <thead>
 <th colspan="5">Commandes de sécurité Softlayer</th>
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

## Commandes de sous-réseau {{site.data.keyword.BluSoftlayer_notm}}
 
 <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 8. Commandes de sous-réseau Softlayer</caption>
 <thead>
 <th colspan="5">Commandes de sous-réseau Softlayer</th>
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
 
## Commandes de serveur virtuel {{site.data.keyword.BluSoftlayer_notm}}

 <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 9. Commandes de serveur virtuel Softlayer</caption>
 <thead>
 <th colspan="6">Commandes de serveur virtuel Softlayer</th>
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
 
## Commandes de réseau local virtuel {{site.data.keyword.BluSoftlayer_notm}}

  <table summary="Commandes SoftLayer générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 10. Commandes de réseau local virtuel Softlayer</caption>
 <thead>
 <th colspan="6">Commandes de réseau local virtuel Softlayer</th>
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

### Syntaxe de la commande
Afin d'afficher les informations d'aide pour les commandes, exécutez : `bluemix sl [commande] -h`.

### bluemix sl init
{: #sl_init}

Permet d'initialiser les paramètres de configuration qui sont utilisés pour établir une connexion à l'environnement SoftLayer. La configuration inclut un nom d'utilisateur, une clé d'API ou un mot de passe, un compte et un noeud final.
```
bluemix sl init [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>URL de noeud final d'API Softlayer, par défaut : https://api.softlayer.com/rest/v3.1</dd>
   <dt>-u,--sl-user</dt>
   <dd>Nom d'utilisateur Softlayer</dd>
   <dt>-p,--sl-password</dt>
   <dd>Mot de passe ou clé d'API Softlayer</dd>
   <dt>-c,--account-id</dt>
   <dd>ID de compte Softlayer</dd>
   </dl>

Par exemple, connectez-vous à l'aide du nom d'utilisateur et du mot de passe ou de la clé d'API Softlayer.
```
$ bluemix sl config
Choose how to configure Softlayer authentication:
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> wangjunl@cn.ibm.com
API key or password: []> abcd

Softlayer API endpoint:    https://api.softlayer.com/rest/v3.1
Account ID:                278444
User ID:                   wangjunl@cn.ibm.com
API Key:                   xxxxxxxxxx
```
Par exemple, utilisez Bluemix Single-Sign-On pour vous connecter à Softlayer
```
$ bx login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account Wilma's Account (65ce8074c6c62b5)

Targeted org wangjunl@cn.ibm.com

Targeted space Wilma
                  
API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           wangjunl@cn.ibm.com   
Account:        Wilma's Account (65ce8074c6c62b5)   
Org:            wangjunl@cn.ibm.com   
Space:          Wilma 

$ bx sl init
Choose how to configure Softlayer authentication: 
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number> 2
Softlayer API endpoint URL: [https://api.softlayer.com/mobile/v3.1]> 
Setting account to: 278444
OK
                              
Softlayer API endpoint:    https://api.softlayer.com/mobile/v3.1   
Account ID:                278444   
User ID:                   12345678   
IMS token:                 xxxxxxxxxx
```

### bluemix sl help
{: #sl_help}

Permet d'afficher de l'aide pour toutes les commandes exécutées dans un environnent Softlayer.
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

Permet d'autoriser les hôtes à accéder à un volume donné.
```
bluemix sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--hardware-id</dt>
   <dd>ID d'un serveur matériel à autoriser.</dd>
   <dt>--virtual-id</dt>
   <dd>ID d'un serveur virtuel à autoriser.</dd>
   <dt>--ip-address-id</dt>
   <dd>ID d'une adresse IP à autoriser.</dd>
   <dt>--ip-address</dt>
   <dd>Adresse IP à autoriser.</dd>
    </dl>

**Exemples** :
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
Cette commande autorise le serveur virtuel portant l'ID `87654321` à accéder au volume portant l'ID `12345678`.

### bluemix sl block access-list
{: #sl_block_access_list}

Permet de répertorier les listes de contrôle d'accès.
```
bluemix sl block access-list VOLUME_ID [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` ou `password`.</dd>
   <dt>--columns</dt>
   <dd>  Les options d'affichage des colonnes sont les suivantes : `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` ou `password`.</dd>
</dl>

**Exemples** :
```
bluemix sl block access-list 12345678 --sortby id
```
Cette commande répertorie tous les hôtes qui sont autorisés à accéder au volume portant l'ID `12345678` et les trie par ID.

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

Permet de révoquer l'autorisation des hôtes à accéder à un volume donné.
```
 bluemix sl block access-revoke VOLUME_ID [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--hardware-id</dt>
   <dd>ID d'un serveur matériel à autoriser.</dd>
   <dt>--virtual-id</dt>
   <dd>ID d'un serveur virtuel à autoriser.</dd>
   <dt>--ip-address-id</dt>
   <dd>ID d'une adresse IP à autoriser.</dd>
   <dt>--ip-address</dt>
   <dd>Adresse IP à autoriser.</dd>
    </dl>

**Exemples** :
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
Cette commande révoque l'accès du serveur virtuel portant l'ID `87654321` au volume portant l'ID `12345678`.

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

Permet d'effectuer une opération de reprise par restauration d'un volume de bloc à partir d'une réplique.
```
 bluemix sl block replica-failback VOLUME_ID
```
**Exemples** :
```
 bluemix sl block replica-failback 12345678
```
Cette commande effectue une opération de reprise par restauration du volume portant l'ID `12345678`.

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

Permet d'effectuer une opération de reprise en ligne d'un volume de bloc vers le volume de réplique donné.
```
bluemix sl block replica-failover VOLUME_ID REPLICA_ID
```

**Exemples** :
```
 bluemix sl block replica-failover 12345678 87654321
```
Cette commande effectue une opération de reprise en ligne du volume portant l'ID `12345678` vers le volume de réplique portant l'ID `87654321`.

### bluemix sl block replica-order
{: #sl_block_replica_order}

Permet de commander un volume de réplique de stockage par blocs.
```
 bluemix sl block replica-order VOLUME_ID [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>Obligatoire. Planning d'instantané à utiliser pour la réplication. Les options possibles sont les suivantes : `HOURLY`,`DAILY` ou `WEEKLY`.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Obligatoire. Nom abrégé du centre de données pour la réplique. Par exemple, `dal09`.</dd>
   <dt>--tier</dt>
   <dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume principal pour lequel une réplique est commandée. Les options possibles sont les suivantes : `0.25`, `2`, `4` ou `10`.</dd>
   <dt>--os-type</dt>
   <dd>Facultatif. Type de système d'exploitation du volume principal pour lequel une réplique est commandée. Les options possibles sont les suivantes : `HYPER_V`, `LINUX`, `VMWARE`, `WINDOWS_2008`, `WINDOWS_GPT`, `WINDOWS` ou `XEN`.</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

**Exemples** :
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Cette commande permet de commander une réplique pour le volume portant l'ID `12345678`. Il s'agit d'une réplication quotidienne (option DAILY), située sur dal09 avec le niveau `4` et le type de système d'exploitation `Linux`.

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Permet d'annuler l'espace d'image instantanée d'un volume donné.
```
 bluemix sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement l'image instantanée portant l'ID 12345678 sans demander de confirmation.

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

Permet de créer une image instantanée sur un volume donné.
```
 bluemix sl block snapshot-create VOLUME_ID [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt> -n, --note</dt>
   <dd>Notes à définir sur la nouvelle image instantanée</dd>
	</dl>

**Exemples** :
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
Cette commande crée une image instantanée pour un volume portant l'ID `12345678` et avec la note d'ajout `snapshotforbluemix`.

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

Permet de désactiver les images instantanées sur le planning spécifié pour un volume donné.
```
 bluemix sl block snapshot-disable VOLUME_ID [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Obligatoire. Les valeurs possibles pour le planning d'image instantanée sont les suivantes : `HOURLY`, `DAILY` ou `WEEKLY`.</dd>
	</dl>

**Exemples** :
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
Cette commande désactive la prise d'image instantanée quotidienne pour le volume portant l'ID `12345678`.

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

Permet d'activer les images instantanées sur le planning spécifié pour un volume donné.
```
 bluemix sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Obligatoire. Les valeurs possibles pour le planning d'image instantanée sont les suivantes : `HOURLY`, `DAILY` ou `WEEKLY`.</dd>
   <dt>-c, --retention-count</dt>
   <dd>Obligatoire. Nombre d'images instantanées à conserver.</dd>
   <dt>-m, --minute</dt>
   <dd>Minute de l'heure de la prise des images instantanées, entier compris entre 0 et 59.</dd>
   <dt>--hour</dt>
   <dd>Heure du jour de la prise des images instantanées, entier compris entre 0 et 23.</dd>
   <dt>-d, --day-of-week</dt>
   <dd>Jour de la semaine de la prise des images instantanées, entier compris entre 0 et 6.
0 signifie dimanche, 1 signifie lundi, 2 signifie mardi, 3 signifie mercredi, 4 signifie jeudi, 5 signifie vendredi, 6 signifie samedi.</dd>
	</dl>

**Exemples** :
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Cette commande active la prise d'image instantanée pour le volume portant l'ID `12345678`. L'image instantanée est prise à 2h00 tous les dimanches, et jusqu'à 5 images instantanées sont conservées.

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

Permet de supprimer une image instantanée sur un volume donné.
```
  bluemix sl block snapshot-delete SNAPSHOT_ID
```

**Exemples** :
```
 bluemix sl block snapshot-delete 12345678
```
Cette commande supprime les images instantanées portant l'ID `12345678`.

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

Répertorier les images instantanées du stockage par blocs
```
 bluemix sl block snapshot-list VOLUME_ID [OPTIONS]

```

<strong>Options de commande</strong> :
   <dl>
   <dt>--sortby</dt>
   <dd>Colonne à trier. Les options possibles sont les suivantes : `id`, `name`, `created` et `size_bytes`.</dd>
	</dl>

**Exemples** :
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
Cette commande répertorie toutes les images instantanées du volume portant l'ID `12345678` et les trie par ID.

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

Permet de commander l'espace d'image instantanée pour un volume de stockage par blocs.
```
 bluemix sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-s, --size</dt>
   <dd>Obligatoire. Taille, en Go, de l'espace d'image instantanée à créer.</dd>
   <dt>-t, --tier</dt>
   <dd>Facultatif. Niveau de stockage d'endurance (IOPS par Go) du volume de stockage par blocs pour lequel de l'espace est commandé. Les options possibles sont les suivantes : 0.25,2,4,10</dd>
   <dt>-u, --upgrade</dt>
   <dd>Indicateur permettant de signaler que la commande est une mise à niveau.</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
	</dl>

**Exemples** :
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
Cette commande permet de commander de l'espace d'image instantanée pour le volume portant l'ID `12345678`. La taille est de 1000 Go et le niveau est de 4 IOPS par Go.


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restaurer le volume de blocs à l'aide d'une image instantanée donnée
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**Exemples** :
```
 bluemix sl block snapshot-restore 12345678 87654321
```
Cette commande restaure un volume portant l'ID `12345678` à partir d'une image instantanée portant l'ID `87654321`.

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

Annuler un volume de stockage par blocs
```
 bluemix sl block volume-cancel VOLUME_ID [OPTIONS]
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
 bluemix sl block volume-cancel 12345678 --immediate -f
```
Cette commande annule immédiatement le volume portant l'ID `12345678` sans demander de confirmation.

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

Afficher les détails d'un volume donné
```
 bluemix sl block volume-detail VOLUME_ID
```

**Exemples** :
```
 bluemix sl block volume-detail 12345678
```
Cette commande affiche les détails relatifs au volume portant l'ID `12345678`.

### bluemix sl block volume-list
{: #sl_block_volume_list}

Permet de répertorier le stockage par blocs.
```
 bluemix sl block volume-list [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-u, --username</dt>
   <dd>Filtrer par nom de volume.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filtrer par nom abrégé de centre de données.</dd>
   <dt>-t, --storage-type</dt>
   <dd>Filtrer par type de volume de stockage. Les options possibles sont les suivantes : `performance` et `endurance`.</dd>
   <dt>--order</dt>
   <dd>Filtrer par ID de commande utilisé pour acheter le stockage par blocs.</dd>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
   <dt>--columns</dt>
   <dd>Les options d'affichage des colonnes sont les suivantes : id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
   </dl>

**Exemples** :
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Cette commande répertorie tous les volumes d'endurance pour le compte en cours qui se trouvent sur dal09, et les trie par capacité.


### bluemix sl block volume-order
{: #sl_block_volume_order}

Permet de commander un volume de stockage par blocs.
```
   bluemix sl block volume-order [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--storage-type</dt>
   <dd>Type de volume de stockage [obligatoire]. Les options possibles sont les suivantes : performance et endurance.</dd>
   <dt>--size</dt>
   <dd>Taille du volume de stockage en Go [obligatoire]</dd>
   <dt>--iops</dt>
   <dd>IOPS du stockage de type performance, compris entre 100 et 6000 en multiples de 100 [obligatoire pour un stockage de type performance]</dd>
   <dt>--tier</dt>
   <dd>Niveau de stockage Endurance (IOP par Go) [obligatoire pour le type de stockage endurance], options : 0.25,2,4,10</dd>
   <dt>--os-type</dt>
   <dd>Système d'exploitation [obligatoire]. Les options possibles sont les suivantes : HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nom abrégé du centre de données [obligatoire]</dd>
   <dt>--snapshot-size</dt>
   <dd>Paramètre facultatif pour la commande d'espace d'image instantanée avec un stockage par blocs de type endurance ; indique la taille (en Go) de l'espace d'image instantanée à commander</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
   </dl>


**Exemples** :

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Cette commande permet de commander un volume de performance d'une taille de 1000 Go, dont le niveau IOPS est 4000, le type de système d'exploitation LINUX, et qui se trouve sur dal09.

```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
Cette commande permet de commander un volume d'endurance d'une taille de 500 Go, dont le niveau est 4 IOPS par Go, le type de système d'exploitation XEN, qui se trouve sur dal09 et dont la taille d'espace instantanée supplémentaire est de 500 Go.


### bluemix sl block volume-options
{: #sl_block_volume_options}

Permet de répertorier toutes les options pour la commande d'un stockage par blocs.
```
 bluemix sl block volume-options
```

**Exemples** :
```
 bluemix sl block volume-options
```
Cette commande répertorie toutes les options relatives à la création d'un volume de stockage par blocs, y compris le type de stockage, la taille de volume, le type de système d'exploitation, la valeur IOPS, le niveau, le centre de données et la taille d'image instantanée.


### bluemix sl dns import
{: #sl_dns_import}

Permet d'importer une zone basée sur un fichier de zone BIND.
```
bluemix sl dns-import [OPTIONS] ZONEFILE
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--dry-run</dt>
   <dd>Indique de ne pas créer réellement d'enregistrements.</dd>
    </dl>

**Exemples** :
```
 bluemix sl dns import ~/blumix.net.txt
```
Cette commande importe une zone et ses enregistrements de ressource à partir d'un fichier : `~/blumix.net.txt`.

### bluemix sl dns record-add
{: #sl_dns_record_add}
Permet d'ajouter un enregistrement de ressource.

```
bluemix sl dns-record-add [OPTIONS] ZONE RECORD TYPE DATA
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--ttl</dt>
   <dd>Valeur de durée de vie, exprimée en secondes, par exemple, 86400 [par défaut : 7200].</dd>
    </dl>

**Exemples** :
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
Cette commande ajoute un enregistrement A à la zone bluemix.net, son hôte est `ftp`, ses données sont `127.0.0.1` et la valeur de durée de vie est de 86400 secondes.

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

Mettre à jour les enregistrements de ressource dans une zone
```
   bluemix sl dns record-edit ZONE [OPTIONS]
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
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Cette commande édite des enregistrements sous la zone `bluemix.net` pour l'ID `12345678`, et affecte la valeur `127.0.0.2` à leurs données et la valeur 3600 au paramètre de durée de vie.

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
Cette commande édite des enregistrements sous la zone `bluemix.net` pour le nom d'hôte `kibana`, et affecte la valeur 3600 à tous les paramètres de durée de vie.


### bluemix sl dns record-list
{: #sl_dns_record_list}

Répertorier tous les enregistrements de ressource d'une zone

```
   bluemix sl dns record-list ZONE [OPTIONS]
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
   <dd>Filtrer par type d'enregistrement, par exemple A ou CNAME.</dd>
   </dl>

**Exemples** :
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
Cette commande répertorie tous les enregistrements A sous la zone `bluemix.net`, la valeur de filtrage par hôte est `elasticsearch` et la valeur de durée de vie est 900 secondes.


### bluemix sl dns record-remove
{: #sl_dns_record_remove}

Retirer l'enregistrement de ressource d'une zone
```
 bluemix sl dns record-remove RECORD_ID
```

**Exemples** :
```   
 bluemix sl dns record-remove 12345678
```
Cette commande retire l'enregistrement de ressource portant l'ID `12345678`.

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

Permet de créer une zone.
```
 bluemix sl dns zone-create ZONE
```
**Exemples** :
```
 bluemix sl dns zone-create bluemix.net
```
Cette commande crée une zone nommée `bluemix.net`.

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

Permet de supprimer une zone.
```
 bluemix sl dns zone-delete ZONE
```
**Exemples** :
```
 bluemix sl dns zone-delete bluemix.net
```
Cette commande supprime une zone nommée `bluemix.net`.

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

Répertorier toutes les zones sur votre compte
```
   bluemix sl dns zone-list
```
**Exemples** :
```
   bluemix sl dns zone-list
```
Cette commande répertorie toutes les zones sous le compte en cours.

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

Imprimer les enregistrements de ressource et de zone au format BIND
```
 bluemix sl dns zone-print ZONE
```

**Exemples** :
```
 bluemix sl dns zone-print bluemix.net
```
Cette commande imprime une zone nommée bluemix.net au format BIND.


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

Permet d'affecter une adresse IP globale à un routeur ou un périphérique cible.
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**Exemples** :
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
Cette commande affecte une adresse IP portant l'ID 12345678 à une unité cible dont l'adresse IP est 9.111.123.456.


### bluemix sl globalip-create
{: #sl_globalip_create}

Permet de créer une adresse IP globale.
```
bluemix sl globalip-create [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--v6</dt>
   <dd>Indique qu'une adresse IP IPv6 doit être commandée.</dd>
   <dt>--test</dt>
   <dd>Indique qu'une commande doit être testée.</dd>
    <dt>-f, --force</dt>
   <dd>Indique qu'une adresse IP globale doit être créée sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

**Exemples** :
```
     bluemix sl globalip create --v6
```
 Cette commande crée une adresse IP V6.

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

Permet d'annuler une adresse IP globale.
```
bluemix sl globalip-cancel [OPTIONS] IDENTIFIER
```
<strong>Options de commande</strong> :
   <dl>
    <dt>-f, --force</dt>
   <dd>Indique qu'une adresse IP globale doit être créée sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

**Exemples** :
```
 bluemix sl globalip cancel 12345678
```
Cette commande annule une adresse IP portant l'ID `12345678`.

### bluemix sl globalip-list
{: #sl_globalip_list}

Permet de répertorier toutes les adresses IP globales.
```
bluemix sl globalip-list [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--v4</dt>
   <dd>Afficher uniquement les adresses IPv4.</dd>
   <dt>--v6</dt>
   <dd>Afficher uniquement les adresses IPv6.</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

Annuler l'affectation d'une adresse IP globale à partir d'un routeur ou d'un périphérique cible
```
 bluemix sl globalip unassign IDENTIFIER
```
**Exemples** :
```
 bluemix sl globalip unassign 12345678
```
Cette commande annule l'affectation d'une adresse IP portant l'ID `12345678` à partir de l'unité cible.


### bluemix sl image delete
{: #sl_dns_image_delete}

Permet de supprimer une image.
```
   bluemix sl image delete IDENTIFIER
```
**Exemples** :
```
   bluemix sl image delete 12345678
```
Cette commande supprime l'image portant l'ID `12345678`.


### bluemix sl image detail
{: #sl_dns_image_detail}

Permet d'obtenir les détails relatifs à une image.
```
 bluemix sl image detail IDENTIFIER
```
**Exemples** :
```
 bluemix sl image detail 12345678
```
Cette commande permet d'obtenir les détails relatifs à l'image portant l'ID 12345678.

### bluemix sl image edit
{: #sl_dns_image_edit}

Editer les détails d'une image
```
   bluemix sl image edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--name</dt>
   <dd>Nom de l'image.</dd>
   <dt>--note</dt>
   <dd>Note supplémentaire au sujet de l'image.</dd>
   <dt>--tag</dt>
   <dd>Etiquettes de l'image</dd>
   </dl>


**Exemples** :
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Cette commande édite l'image portant l'ID `12345678` en la nommant `ubuntu16` et en lui affectant la note `testing` et l'étiquette `staging`.


### bluemix sl image edit
{: #sl_dns_image_edit}

Editer les détails d'une image
```
   bluemix sl image edit [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--name</dt>
   <dd>Nom de l'image.</dd>
   <dt>--note</dt>
   <dd>Note supplémentaire au sujet de l'image.</dd>
   <dt>--tag</dt>
   <dd>Etiquettes de l'image</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

Permet de répertorier toutes les images sur votre compte
```
   bluemix sl image list [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--name</dt>
   <dd>Filtrer par nom d'image.</dt>
   <dd>--public</dt>
   <dd>Afficher uniquement les images publiques.</dd>
   <dt>--private</dt>
   <dd>Afficher uniquement les images privées.</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

Annuler un volume iSCSI existant
```
   bluemix sl iscsi cancel IDENTIFICATEUR [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--reason</dt>
   <dd>Motif (facultatif) de l'annulation.</dd>
   <dt>--immediate</dt>
   <dd>Annuler le volume iSCSI immédiatement sans attendre la date anniversaire de la facturation.</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

Créer un volume iSCSI
```
   bluemix sl iscsi create [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--size</dt>
   <dd>Taille du volume iSCSI à créer (en gibioctets) [obligatoire]</dd>
   <dt>--datacenter</dt>
   <dd>Nom abrégé du centre de données [obligatoire]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

Obtenir les détails sur un volume iSCSI
```
   bluemix sl iscsi detail IDENTIFICATEUR [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--password</dt>
   <dd>Permet d'afficher les données d'identification permettant d'accéder à la cible iSCSI.</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

Répertorier les volumes iSCSI
```
 bluemix sl iscsi list [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--order</dt>
   <dd>ID de la commande ayant acheté ce stockage iscsi</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

Annuler/supprimer l'image instantanée iSCSI
```
 bluemix sl iscsi snapshot-cancel IDENTIFICATEUR [OPTIONS]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

Créer une image instantanée d'un volume iSCSI
```
   bluemix sl iscsi snapshot-create IDENTIFICATEUR [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--notes</dt>
   <dd>Note (facultative) au sujet de l'image instantanée.</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

Commander de l'espace d'image instantanée pour un volume iSCSI donné
```
 bluemix sl iscsi snapshot-create-space IDENTIFICATEUR [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--capacity</dt>
   <dd>Taille de l'espace d'image instantanée à créer.</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

Répertorier les images instantanées d'un volume iSCSI
```
 bluemix sl iscsi snapshot-list IDENTIFICATEUR [OPTIONS]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

Ajouter une nouvelle clé SSH
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --in-file</dt>
   <dd>Fichier id_rsa.pub à importer pour cette clé</dd>
   <dt>-k, --key</dt>
   <dd>Clé SSH réelle</dd>
   <dt>--note</dt>
   <dd>Note supplémentaire qui sera associée à la clé</dd>
   </dl>


**Exemples** :
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Cette commande ajoute une clé SSH à partir d'un fichier : ~/.ssh/id_rsa.pub with a note "mykey".


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

Editer une clé SSH
```
 bluemix sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--label</dt>
   <dd>Nouveau libellé de la clé</dd>
   <dt>--note</dt>
   <dd>Nouvelles notes pour la clé</dd>
   </dl>


**Exemples** :
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Cette commande met à jour la clé SSH portant l'ID 12345678 et lui affecte le libellé "Bluemix" et la note "testing".

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

Répertorier les clés SSH sur votre compte
```
 bluemix sl security sshkey-list [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : `id`, `label`, `fingerprint`, `notes`.</dd>
   </dl>


**Exemples** :
```
 bluemix sl security sshkey-list --sortby label
```
 Cette commande répertorie toutes les clés SSH sur le compte en cours et les trie par libellé.

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

Imprime une clé SSH à l'écran
```
 bluemix sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --out-file</dt>
   <dd>La clé SSH publique sera écrite sur ce fichier.</dd>
   </dl>


**Exemples** :
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
 Cette commande affiche l'ID, le libellé et les notes de la clé SSH portant l'ID 12345678 et écrit la clé publique dans le fichier : ~/mykey.pub.

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

Supprime une clé SSH de manière définitive
```
 bluemix sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
   </dl>


**Exemples** :
```
 bluemix sl security sshkey-remove 12345678 -f
```
 Cette commande retire la clé SSH portant l'ID 12345678 sans demander de confirmation.

### bluemix sl security cert-add
{: #sl_security_cert_add}

Ajouter et transférer les détails du certificat SSL
```
 bluemix sl security cert-add [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--crt</dt>
   <dd>Fichier de certificat</dd>
   <dt>--csr</dt>
   <dd>Fichier de demande de signature de certificat</dd>
   <dt>--icc</dt>
   <dd>Fichier de certificat intermédiaire</dd>
   <dt>--key</dt>
   <dd>Fichier de clé privée</dd>
   <dt>--notes</dt>
   <dd>Notes supplémentaires</dd>
   </dl>


**Exemples** :
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
 Cette commande ajoute le fichier certificat ~/bluemix.net.cert et le fichier de clé privée ~/bluemix.net.key pour le domaine bluemix.net.

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

Editer le certificat SSL
```
 bluemix sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--crt</dt>
   <dd>Fichier de certificat</dd>
   <dt>--csr</dt>
   <dd>Fichier de demande de signature de certificat</dd>
   <dt>--icc</dt>
   <dd>Fichier de certificat intermédiaire</dd>
   <dt>--key</dt>
   <dd>Fichier de clé privée</dd>
   <dt>--notes</dt>
   <dd>Notes supplémentaires</dd>
   </dl>


**Exemples** :
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
 Cette commande édite le certificat portant l'ID 12345678 et met à jour sa clé privée avec le fichier ~/bluemix.net.key.

### bluemix sl security cert-download
{: #sl_security_cert_download}

Télécharger le certificat SSL et les fichiers de clés
```
 bluemix sl security cert-download IDENTIFIER
```

**Exemples** :
```
 bluemix sl security cert-download 12345678
```
  Cette commande télécharge 4 fichiers sur le répertoire de travail pour le certificat portant l'ID 12345678. Ces 4 fichiers sont : le fichier certificat, le fichier de demande de signature de certificat, le fichier de certificat intermédiaire et le fichier de clé privée.

### bluemix sl security cert-list
{: #sl_security_cert_list}

Répertorier les certificats SSL sur votre compte
```
 bluemix sl security cert-list [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--status</dt>
   <dd>Afficher les certificats avec ce statut. La valeur par défaut est all, les options possibles sont les suivantes : `all`, `valid`, `expired`</dd>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : `id`, `common_name`, `days_until_expire`, `notes`</dd>
   </dl>


**Exemples** :
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
 Cette commande répertorie tous les certificats valides sur le compte en cours et les trie par jours de validité.

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

Retirer le certificat SSL
```
 bluemix sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt> -f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
   </dl>


**Exemples** :
```
 bluemix sl security cert-remove 12345678
```
 Cette commande retire le certificat portant l'ID 12345678.

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

Permet d'annuler un sous-réseau.
```
 bluemix sl subnet cancel [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>


**Exemples** :
```
 bluemix sl subnet cancel 12345678 -f
```
Cette commande annule le sous-réseau portant l'ID 12345678 sans demander de confirmation.

### bluemix sl subnet create
{: #sl_subnet_create}

Permet d'ajouter un nouveau sous-réseau à votre compte.
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

Les quantités valides varient selon le type.

 * Type    - Valid Quantities (IPv4)
    ** public  - 4, 8, 16, 32
    ** private - 4, 8, 16, 32, 64
 * Type    - Valid Quantities (IPv6)
    ** public  - 64

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
 bluemix sl subnet create public 16 567
```
Cette commande crée un sous-réseau public avec 16 adresses IPv4 et le place sur le réseau local virtuel portant l'ID 567.



### bluemix sl subnet detail
{: #sl_subnet_detail}

Permet d'obtenir les détails relatifs à un sous-réseau.
```
   bluemix sl subnet detail IDENTIFIER [OPTIONS]
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
 bluemix sl subnet detail 12345678
```
Cette commande affiche des informations détaillées sur le sous-réseau portant l'ID 12345678, y compris les informations sur les serveurs virtuels et les serveurs matériels.


### bluemix sl subnet-list
{: #sl_subnet_list}

Répertorier tous les sous-réseaux sur votre compte
```
   bluemix sl subnet list [OPTIONS]
```


<strong>Options de commande</strong> :
   <dl>
   <dt>--sortby</dt>
   <dd>Colonne à trier. Les options possibles sont les suivantes : id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
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
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Cette commande répertorie les sous-réseaux IPv4 sur le compte en cours avec le centre de données dal09, le type de sous-réseau PRIMARY et l'espace de sous-réseau PUBLIC.



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

Rechercher une adresse IP et afficher les informations relatives au sous-réseau et aux périphériques associés
```
   bluemix sl subnet lookup IP_ADDRESS
```

**Exemples** :
```
 bluemix sl subnet lookup 9.125.235.255
```
Cette commande recherche l'enregistrement d'adresse IP portant l'adresse 9.125.235.255 et affiche ses informations de sous-réseau et d'unité.


### bluemix sl vs cancel
{: #sl_vs_cancel}

Annuler l'instance de serveur virtuel
```
   bluemix sl vs cancel IDENTIFIER [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
   </dl>

**Exemples** :
```
 bluemix sl vs cancel 12345678
```
Cette commande annule l'instance de serveur virtuel portant l'ID 12345678.


### bluemix sl vs capture
{: #sl_vs_capture}

Capturer l'instance de serveur virtuel dans une image
```
 bluemix sl vs capture IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-n, --name</dt>
   <dd>Nom de l'image [obligatoire].</dd>
   <dt>--all</dt>
   <dd>Capturer tous les disques appartenant au serveur virtuel.</dd>
   <dt>--note</dt>
   <dd>Ajouter une note à associer à l'image.</dd>
   </dl>

**Exemples** :
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
Cette commande capture l'instance de serveur virtuel portant l'ID 12345678 avec tous les disques dans une image nommée "mybluemix" et la note "testing".



### bluemix sl vs create
{: #sl_vs_create}

Créer une instance de serveur virtuel
```
   bluemix sl vs create [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-H, --hostname</dt>
   <dd>Portion hôte du nom de domaine complet [obligatoire]</dd>
   <dt>-D, --domain</dt>
   <dd>Portion domaine du nom de domaine complet [obligatoire]</dd>
   <dt>-c, --cpu</dt>
   <dd>Nombre de coeurs d'UC [obligatoire]</dd>
   <dt>-m, --memory</dt>
   <dd>Mémoire en mégaoctets [obligatoire]</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nom abrégé du centre de données [obligatoire]</dd>
   <dt>-o, --os</dt>
   <dd>Code d'installation du système d'exploitation. Astuce : vous pouvez spécifier <OS>_LATEST</dd>
   <dt>--image</dt>
   <dd>ID image. Voir [bluemix sl image list](#bluemix_sl_image_list) pour référence.</dd>
   <dt>--billing</dt>
   <dd>Taux de facturation. Par défaut : hourly. Options : hourly, monthly</dd>
   <dt>--dedicated</dt>
   <dd>Créer un serveur virtuel dédié (noeud privé)</dd>
   <dt>--san</dt>
   <dd>Utiliser le stockage SAN à la place d'un disque local</dd>
   <dt>--test</dt>
   <dd>Ne pas créer le serveur virtuel</dd>
   <dt>--export</dt>
   <dd>Exporte les options vers un fichier modèle</dd>
   <dt>-i, --postinstall</dt>
   <dd>Script de post-installation à télécharger</dd>
   <dt>-k, --key</dt>
   <dd>ID des clés SSH à ajouter à l'utilisateur root (plusieurs occurrences autorisées)</dd>
   <dt>--disk</dt>
   <dd>Tailles de disque (plusieurs occurrences autorisées)</dd>
   <dt>--private</dt>
   <dd>Force le serveur virtuel à n'avoir accès qu'au réseau privé</dd>
   <dt>--like</dt>
   <dd>Utiliser la configuration d'un serveur virtuel existant</dd>
   <dt>-n, --network</dt>
   <dd>Vitesse du port réseau en Mbit/s</dd>
   <dt>--tag</dt>
   <dd>Etiquettes à ajouter à l'instance (plusieurs occurrences autorisées)</dd>
   <dt>-t, --template</dt>
   <dd>Fichier modèle qui indique les options de ligne de commande par défaut.</dd>
   <dt>-u, --userdata</dt>
   <dd>Chaîne de métadonnées définie par l'utilisateur</dd>
   <dt>-F, --userfile</dt>
   <dd>Lire les données utilisateur à partir du fichier</dd>
   <dt>--vlan-public</dt>
   <dd>ID du VLAN public sur lequel vous voulez placer le serveur virtuel</dd>
   <dt>--vlan-private</dt>
   <dd>ID du VLAN privé sur lequel vous voulez placer le serveur virtuel</dd>
   <dt>--wait</dt>
   <dd>Attendre pendant X secondes maximum que le serveur virtuel soit mis à disposition avant de revenir</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
	</dl>

**Exemples** :
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Cette commande permet de commander une instance de serveur virtuel dont le nom d'hôte (hostname) est myvsi, le domaine (domain) bluemix.net, qui comporte 4 coeurs d'UC, 4096 Mo de mémoire, qui se trouve sur le centre de données dal10, dont le système d'exploitation est UBUNTU 16 64 bits, avec 2 disques (un de 100 Go et l'autre de 1000 Go) et qui est placée sur le réseau local virtuel public portant l'ID 413.
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
Cette commande effectue des tests afin de vérifier si la commande avec les options ci-dessus est valide avant qu'elle ne soit effectivement passée.
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

Cette commande exporte les options ci-dessus dans un fichier myvsi.txt sous le répertoire de base en vue d'une utilisation ultérieure.


### bluemix sl vs options
{: #sl_vs_options}

Répertorier les options de création de l'instance de serveur virtuel
```
   bluemix sl vs options [OPTIONS]
```

**Exemples** :
```
 bluemix sl vs options
```
Cette commande répertorie toutes les options de création d'une instance de serveur virtuel, par exemple, datacenter, cpu, memory, os, disk, network speed, etc.



### bluemix sl vs credentials
{: #sl_vs_credentials}

Répertorier les donnée d'identification de l'instance de serveur virtuel
```
   bluemix sl vs credentials IDENTIFIER [OPTIONS]
```
**Exemples** :
```
 bluemix sl vs credentials 12345678
```
Cette commande répertorie toutes les paires nom d'utilisateur-mot de passe d'une instance de serveur virtuel portant l'ID 12345678.

### bluemix sl vs detail
{: #sl_vs_detail}

Obtenir les détails sur une instance de serveur virtuel
```
   bluemix sl vs detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--passwords</dt>
   <dd>Afficher les mots de passe.</dd>
   <dt>--price</dt>
   <dd>Afficher les prix associés.</dd>
   </dl>


**Exemples** :
```
   bluemix sl vs details 12345678
```
Cette commande répertorie des informations détaillées sur l'instance de serveur virtuel portant l'ID 12345678.


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

Synchroniser les enregistrements DNS pour une instance de serveur virtuel
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONS]
```
remarque : si vous ne spécifiez pas d'arguments, la commande tentera de mettre à jour les enregistrements A et PTR. Si vous ne souhaitez pas mettre à jour les deux enregistrements, vous pouvez utiliser les arguments -a ou --ptr pour limiter les enregistrements mis à jour.

<strong>Options de commande</strong> :
   <dl>
   <dt>-a, --a-record</dt>
   <dd>Synchroniser l'enregistrement A pour l'hôte</dd>
   <dt>--aaaa-record</dt>
   <dd>Synchroniser l'enregistrement AAAA pour l'hôte</dd>
   <dt>--ptr</dt>
   <dd>Synchroniser l'enregistrement PTR pour l'hôte</dd>
   <dt>--ttl</dt>
   <dd>Définit la durée de vie des enregistrements A et/ou PTR, valeur par défaut : 7200</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
   </dl>


**Exemples** :
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
Cette commande synchronise l'enregistrement A (adresse IPv4) de l'instance de serveur virtuel portant l'ID 12345678 avec le serveur DNS et affecte la valeur 3600 au paramètre de durée de vie de cet enregistrement A.
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
Cette commande synchronise l'enregistrement AAAA(adresse IPv6) et l'enregistrement PTR de l'instance de serveur virtuel portant l'ID 12345678 avec le serveur DNS.


### bluemix sl vs edit
{: #sl_vs_edit}

Editer les détails d'une instance de serveur virtuel
```
   bluemix sl vs edit IDENTIFIER [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>-D, --domain</dt>
   <dd>Portion domaine du nom de domaine complet</dd>
   <dt>-H, --hostname</dt>
   <dd>Portion hôte du nom de domaine complet. Exemple : server</dd>
   <dt>--tag</dt>
   <dd>Etiquettes à définir ou chaîne vide pour tout retirer</dd>
   <dt>-u, --userdata</dt>
   <dd>Chaîne de métadonnées définie par l'utilisateur</dd>
   <dt>-F, --userfile</dt>
   <dd>Lire les données utilisateur à partir du fichier</dd>
   <dt>--public-speed</dt>
   <dd>Vitesse de port public. Les options possibles sont les suivantes : 0, 10, 100, 1000, 10000.</dd>
   <dt>--private-speed</dt>
   <dd>Vitesse de port privé. Les options possibles sont les suivantes : 0, 10, 100, 1000, 10000.</dd>
   </dl>

**Exemples** :
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
Cette commande met à jour l'instance de serveur virtuel portant l'ID `12345678` et lui affecte la valeur `bluemix.net` comme domaine, la valeur `myapp` comme nom d'hôte, la valeur `testcli` comme étiquette et la valeur 1000 Mbit/s comme vitesse de port de réseau public.



### bluemix sl vs list
{: #sl_vs_list}
Répertorier les instances de serveur virtuel sur votre compte
```
   bluemix sl vs list [OPTIONS]
```


<strong>Options de commande</strong> :
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Nombre de coeurs d'UC</dd>
   <dt>-D, --domain</dt>
   <dd>Portion domaine du nom de domaine complet</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nom abrégé du centre de données</dd>
   <dt>-H, --hostname</dt>
   <dd>Portion hôte du nom de domaine complet</dd>
   <dt>-m, --memory</dt>
   <dd>Mémoire en mégaoctets</dd>
   <dt>-n, --network</dt>
   <dd>Vitesse du port réseau en Mbit/s</dd>
   <dt>--hourly</dt>
   <dd>Afficher uniquement les instances horaires</dd>
   <dt>--monthly</dt>
   <dd>Afficher uniquement les instances mensuelles</dd>
   <dt>--tag</dt>
   <dd>Filtrer par étiquettes (plusieurs occurrences autorisées)</dd>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Valeur par défaut : hostname</dd>
   <dt>--columns</dt>
   <dd>Les options d'affichage des colonnes sont les suivantes : guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. La valeur par défaut est id, hostname, primary_ip, backend_ip, datacenter, action</dd>
    </dl>

**Exemples** :
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
Cette commande répertorie toutes les instances de serveur virtuel facturées à l'heure sur le compte en cours, avec comme nom de domaine "bluemix.net", et les trie par mémoire.



### bluemix sl vs-pause
{: #sl_vs_pause}

Mettre en pause une instance de serveur virtuel active
```
   bluemix sl vs pause IDENTIFIER [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

**Exemples** :
```
 bluemix sl vs pause 12345678 -f
```
   Cette commande met en pause l'instance de serveur virtuel portant l'ID 12345678 sans demander de confirmation.



### bluemix sl vs power-off
{: #sl_vs_power_off}

Mettre hors tension une instance de serveur virtuel active
```
   bluemix sl vs power-off IDENTIFIER [OPTIONS]
```

**Exemples** :
```
   bluemix sl vs power-off 12345678 --soft
```
Cette commande effectue une mise hors tension graduelle pour l'instance de serveur virtuel portant l'ID 12345678.

<strong>Options de commande</strong> :
   <dl>
   <dt>--hard</dt>
   <dd>Effectuer un arrêt immédiat</dd>
   <dt>--soft</dt>
   <dd>Effectuer un arrêt graduel</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

Mettre sous tension une instance de serveur virtuel
```
 bluemix sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>

**Exemples** :
```
 bluemix sl vs power-on 12345678
```
Cette commande effectue une mise sous tension pour l'instance de serveur virtuel portant l'ID 12345678.


### bluemix sl vs ready
{: #sl_vs_ready}

Vérifier si une instance de serveur virtuel est prête à être utilisée
```
 bluemix sl vs ready IDENTIFIER [OPTIONS]
```

**Exemples** :
```
 bluemix sl vs ready 12345678 --wait 30
```
Cette commande vérifie le statut de l'instance de serveur virtuel portant l'ID 12345678 pour voir si elle est prête pour une utilisation en continu, et attend pendant 30 secondes au maximum.

<strong>Options de commande</strong> :
   <dl>
   <dt>--wait</dt>
   <dd>Attendre pendant X secondes maximum que le serveur virtuel soit mis à disposition avant de revenir</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

Réamorcer une instance de serveur virtuel active
```
 bluemix sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--hard</dt>
   <dd>Effectuer un réamorçage immédiat</dd>
   <dt>--soft</dt>
   <dd>Effectuer un réamorçage immédiat</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
    </dl>

**Exemples** :
```
 bluemix sl vs reboot 12345678 --hard
```
Cette commande effectue un réamorçage immédiat pour l'instance de serveur virtuel portant l'ID 12345678.



### bluemix sl vs reload
{: #sl_vs_reload}

Recharger le système d'exploitation sur une instance de serveur virtuel
```
 bluemix sl vs reload IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>Script de post-installation à télécharger</dd>
   <dt>--image</dt>
   <dd>ID image. Par défaut, il convient d'utiliser le système d'exploitation en cours.
Voir 'bluemix sl image list' pour référence.</dd>
   <dt>-k, --key</dt>
   <dd>ID des clés SSH à ajouter à l'utilisateur root (plusieurs occurrences autorisées)</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>

**Exemples** :
```
   bluemix sl vs reload 12345678
```
Cette commande recharge le système d'exploitation en cours pour l'instance de serveur virtuel portant l'ID 12345678.
```
 bluemix sl vs reload 12345678 --image 1234
```
Cette commande recharge le système d'exploitation à partir de l'image portant l'ID 1234 pour l'instance de serveur virtuel portant l'ID 12345678.



### bluemix sl vs rescure
{: #sl_vs_rescure}

Réamorcer une instance de serveur serveur dans une image de secours
```
 bluemix sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
   </dl>
   
**Exemples** :
```
 bluemix sl vs rescue 12345678
```
Cette commande réamorce l'instance de serveur virtuel portant l'ID 12345678 dans une image de secours.


### bluemix sl vs resume
{: #sl_vs_resume}

Reprendre une instance de serveur virtuel mise en pause
```
   bluemix sl vs resume IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>

**Exemples** :
```
 bluemix sl vs resume 12345678
```
Cette commande effectue la reprise de l'instance de serveur virtuel portant l'ID 12345678.


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

Mettre à niveau une instance de serveur virtuel
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONS]
```
Remarque : SoftLayer réamorce automatiquement l'instance une fois que la demande de mise à niveau est placée. L'instance est arrêtée tant que la transaction de mise à niveau n'est pas terminée. En revanche, pour le réseau, aucun réamorçage n'est requis.

<strong>Options de commande</strong> :
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Nombre de coeurs d'UC</dd>
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
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Cette commande met à niveau l'instance de serveur virtuel portant l'ID 12345678 et lui affecte la valeur 8 comme nombre de coeurs d'UC, la valeur 8192 Mo comme mémoire et la valeur 1000 Mbit/s comme vitesse de port réseau.



### bluemix sl vlan create
{: #sl_vlan_create}

Créer un nouveau réseau local virtuel
```
   bluemix sl vlan create [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>Type de VLAN, public ou privé</dd>
   <dt>-r, --router</dt>
   <dd>Nom d'hôte du routeur</dd>
   <dt>-d, --datacenter</dt>
   <dd>Nom abrégé du centre de données</dd>
   <dt>-s, --size</dt>
   <dd>Taille des sous-réseaux, options : 8 (5 adresses IP utilisables) ou 16 (13 adresses IP utilisables) ou 32 (29 adresses IP utilisables)</dd>
   <dt>-n, --name</dt>
   <dd>Nom du VLAN</dd>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>

**Exemples** :
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Cette commande crée un réseau local virtuel public sur le centre de données dal09 avec 16 adresses IP, et lui affecte le nom myvlan.
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
Cette commande crée un réseau local virtuel sur le routeur bcr01a.dal09 avec 16 adresses IP, et lui affecte le nom myvlan.



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

Annuler un réseau local virtuel
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-f, --force</dt>
   <dd>Forcer l'opération sans confirmation</dd>
    </dl>

**Exemples** :
```
   bluemix sl vlan cancel 12345678 -f
```
Cette commande annule le réseau local virtuel portant l'ID 12345678 sans demander de confirmation.



### bluemix sl vlan detail
{: #sl_vlan_detail}

Permet d'obtenir les détails relatifs à un réseau local virtuel.
```
   bluemix sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>--no-vs</dt>
   <dd>Masquer la liste de serveurs virtuels</dd>
   <dt>--no-hardware</dt>
   <dd>Masquer la liste du matériel</dd>
   </dl>

**Exemples** :
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
Cette commande affiche les détails relatifs au réseau local virtuel portant l'ID 12345678 mais n'indique pas le serveur virtuel ou le serveur matériel.


### bluemix sl vlan edit
{: #sl_vlan_edite}

Editer les détails d'un réseau local virtuel
```
   bluemix sl vlan edit IDENTIFIER [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--n, --name</dt>
   <dd>Nom du VLAN</dd>
    </dl>

**Exemples** :
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
Cette commande met à jour le réseau local virtuel portant l'ID 12345678 et lui affecte le nouveau nom "myvlan-rename".


### bluemix sl vlan list
{: #sl_vlan_list}

Répertorier tous les réseaux locaux virtuels sur votre compte
```
 bluemix sl vlan list [OPTIONS]
```
<strong>Options de commande</strong> :
   <dl>
   <dt>--sortby</dt>
   <dd>Les options de tri des colonnes sont les suivantes : id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filtrer par nom abrégé du centre de données</dd>
   <dt>-n, --number</dt>
   <dd>Filtrer par numéro de réseau local virtuel</dd>
   <dt>--name</dt>
   <dd>Filtrer par nom de réseau local virtuel</dd>
   <dt>--order</dt>
   <dd>Filtrer par ID de commande utilisé pour acheter le réseau local virtuel</dd>
   </dl>

**Exemples** :
```
 bluemix sl vlan list -d dal09 --sortby number
```
Cette commande répertorie tous les réseaux locaux virtuels sur le compte en cours pour le centre de données dal09, et les trie par numéro de réseau local virtuel.




### bluemix sl vlan options
{: #sl_vlan_options}

Répertorier toutes les options de création de réseau local virtuel
```
   bluemix sl vlan options
```
**Exemples** :
```
 bluemix sl vlan options
```
Cette commande répertorie toutes les options de création d'un réseau local virtuel, par exemple, type de réseau local virtuel, centre de données, taille de sous-réseau, routeurs, etc.
