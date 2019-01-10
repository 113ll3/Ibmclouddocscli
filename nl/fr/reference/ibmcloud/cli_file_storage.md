---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Utilisation du service File Storage

{{site.data.keyword.filestorage_full}} est un {{site.data.keyword.filestorage_short}} basé sur NFS, persistant, rapide et connecté au réseau de façon flexible. Cet environnement NAS vous permet d'avoir un contrôle total des fonctions et des performances de vos partages de fichiers.

Les commandes suivantes permettent de gérer un volume spécifique dans le service de stockage de fichier de l'infrastructure {{site.data.keyword.Bluemix_notm}} classique.
{: shortdesc}

<table summary="Commandes générales de l'infrastructure classique {{site.data.keyword.BluSoftlayer_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires pour la commande">
<caption>Tableau 1. Stockage par blocs de l'infrastructure classique {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Stockage de fichier de l'infrastructure classique {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl file access-authorize](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_authorize)</td>
  <td>[ibmcloud sl file access-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_list)</td>
  <td>[ibmcloud sl file access-revoke](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_revoke)</td>
  <td>[ibmcloud sl file replica-failback](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_failback)</td>
  <td>[ibmcloud sl file replica-failover](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_failover)</td>
  <td>[ibmcloud sl file replica-locations](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_locations)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl file replica-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_order)</td>
  <td>[ibmcloud sl file replica-partners](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_partners)</td>
  <td>[ibmcloud sl file snapshot-cancel](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_cancel)</td>
  <td>[ibmcloud sl file snapshot-create](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_create)</td>
  <td>[ibmcloud sl file snapshot-disable](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_disable)</td>
  <td>[ibmcloud sl file snapshot-enable](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_enable)</td>
  </tr>
 <tr>
  <td>[ibmcloud sl file snapshot-delete](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_delete)</td>
  <td>[ibmcloud sl file snapshot-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_list)</td>
  <td>[ibmcloud sl file snapshot-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_order)</td>
  <td>[ibmcloud sl file snapshot-restore](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_restore)</td>
  <td>[ibmcloud sl file snapshot-schedule-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_schedule_list)</td>
  <td>[ibmcloud sl file volume-cancel](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_cancel)</td>  
   </tr>
 <tr>
  <td>[ibmcloud sl file volume-count](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_count)</td>
  <td>[ibmcloud sl file volume-detail](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_detail)</td>
  <td>[ibmcloud sl file volume-duplicate](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_duplicate)</td>
  <td>[ibmcloud sl file volume-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_list)</td>
  <td>[ibmcloud sl file volume-modify](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_modify)</td>
  <td>[ibmcloud sl file volume-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_order)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl file volume-options
](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>
 
 ## ibmcloud sl file access-authorize
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

## ibmcloud sl file access-list
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

## ibmcloud sl file access-revoke
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

## ibmcloud sl file replica-failback
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

## ibmcloud sl file replica-failover
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

## ibmcloud sl file replica-locations
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

## ibmcloud sl file replica-order
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

## ibmcloud sl file replica-partners
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

## ibmcloud sl file snapshot-cancel
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

## ibmcloud sl file snapshot-create
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
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
Cette commande crée une image instantanée pour un volume portant l'ID 12345678 et ayant la note d'ajout snapshotforibmcloud.

## ibmcloud sl file snapshot-disable
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

## ibmcloud sl file snapshot-enable
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

## ibmcloud sl file snapshot-delete
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

## ibmcloud sl file snapshot-list
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

## ibmcloud sl file snapshot-order
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

## ibmcloud sl file snapshot-restore
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

## ibmcloud sl snapshot-schedule-list
{: #sl_snapshot_schedule_list}

Répertorier les plannings des instantanés pour un volume donné
```
ibmcloud sl snapshot-schedule-list VOLUME_ID
```

**Exemples** :
```
ibmcloud sl file snapshot-schedule-list 12345678
```
Cette commande répertorie les plannings des instantanés pour un volume dont l'ID est 12345678

## ibmcloud sl file volume-cancel
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

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

Permet de répertorier le nombre de volumes de stockage de fichier par centre de données.
```
ibmcloud sl file volume-count [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
</dl>

## ibmcloud sl file volume-list
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
<dd>Les options d'affichage des colonnes sont les suivantes : id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, mount_addr, notes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Cette commande répertorie tous les volumes d'endurance pour le compte en cours qui se trouvent sur dal09, et les trie par capacité.

## ibmcloud sl file volume-detail
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

## ibmcloud sl file volume-duplicate
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

## ibmcloud sl file volume-order
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
<dt>-b, --billing</dt>
<dd>Paramètre facultatif pour le taux de facturation (facturation mensuelle par défaut). La facturation peut être effectuée toutes les heures ou tous les mois.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Cette commande permet de commander un volume de performance d'une taille de 1000 Go, dont le niveau IOPS est 4000, et qui se trouve sur dal09.

## ibmcloud sl file volume-modify
{: #sl_file_volume_modify}

Modifier un volume de stockage de fichiers existant
```
ibmcloud sl file volume-modify VOLUME_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-c, --new-size</dt>
<dd>Nouvelle taille du volume de fichiers en Go. ***Si aucune taille n'est indiquée, la taille d'origine du volume est utilisée.*** Tailles potentielles : [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Taille minimale : [taille d'origine du volume]</dd>
<dt>-i, --new-iops</dt>
<dd>Niveau IOPS/Go du stockage de type performance, compris entre 100 et 6000 en multiples de 100 [uniquement pour les volumes de performance] ***Si aucune valeur IOPS n'est spécifiée, la valeur IOPS d'origine sera utilisée.*** Exigences : [Si la valeur IOPS/Go d'origine pour le volume est inférieure à 0,3, la nouvelle valeur IOPS/Go doit également être inférieure à 0,3. Si la valeur IOPS/Go d'origine pour le volume est supérieure ou égale à 0,3, la nouvelle valeur IOPS/Go pour le volume doit également être supérieure ou égale à 0,3.]</dd>
<dt>-t, --new-tier</dt>
<dd>Niveau de stockage d'endurance (IOPS/Go) [uniquement pour les volumes de performance] ***Si aucun niveau n'est spécifié, le niveau d'origine du volume sera utilisé.***
Exigences : [Si le niveau IOPS/Go d'origine pour le volume est égal à 0,25, le nouveau niveau IOPS/Go pour le volume doit aussi être égal à 0,25. Si le niveau IOPS/Go pour le volume est supérieur à 0,25, les nouveaux niveaux IOPS pour le volume doit également être supérieur à 0,25.]</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :

```
ibmcloud sl file volume-modify 12345678 --new-size 1000 --new-iops 4000
```
Cette commande permet de modifier un volume 12345678 d'une taille de 1 000 Go et dont le niveau IOPS est 4 000.

```
ibmcloud sl file volume-modify 12345678 --new-size 500 --new-tier 4
```
Cette commande permet de modifier un volume 12345678 d'une taille de 500 Go et dont le niveau est 4 IOPS/Go.


## ibmcloud sl file volume-options
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
