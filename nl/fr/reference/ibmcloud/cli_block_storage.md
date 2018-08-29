---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion du stockage par blocs de l'infrastructure {{site.data.keyword.Bluemix_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.Bluemix_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Stockage par blocs de l'infrastructure {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Stockage par blocs de l'infrastructure {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_password)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_cancel)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-count](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_count)</td>    <td>[ibmcloud sl block volume-detail](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_detail)</td>
   <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_options)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>

## ibmcloud sl block access-authorize
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

## ibmcloud sl block access-list
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

## ibmcloud sl block access-password
{: #sl_block_access_password}

Change le mot de passe pour l'accès à un volume.
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## ibmcloud sl block access-revoke
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

## ibmcloud sl block replica-failback
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

## ibmcloud sl block replica-failover
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

## ibmcloud sl block replica-locations
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

## ibmcloud sl block replica-order
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

## ibmcloud sl block replica-partners
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

## ibmcloud sl block snapshot-cancel
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

## ibmcloud sl block snapshot-create
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
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
Cette commande crée une image instantanée pour un volume portant l'ID 12345678 et ayant la note d'ajout snapshotforibmcloud.

## ibmcloud sl block snapshot-disable
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

## ibmcloud sl block snapshot-enable
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

## ibmcloud sl block snapshot-delete
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

## ibmcloud sl block snapshot-list
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

## ibmcloud sl block snapshot-order
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

## ibmcloud sl block snapshot-restore
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

## ibmcloud sl block volume-cancel
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

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

Répertorier le nombre de volumes de stockage par blocs par centre de données.
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
</dl>

## ibmcloud sl block volume-list
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

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

Définir l'ID LUN sur un volume de stockage par blocs existant.
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## ibmcloud sl block volume-detail
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

## ibmcloud sl block volume-duplicate
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

## ibmcloud sl block volume-order
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

## ibmcloud sl block volume-options
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
