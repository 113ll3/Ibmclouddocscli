---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Virtual Server

Les commandes suivantes permettent de gérer les serveurs virtuels de l'infrastructure {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Commandes de serveur virtuel de l'infrastructure {{site.data.keyword.Bluemix_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires sur la commande">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options
](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ## ibmcloud sl vs cancel
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

## ibmcloud sl vs capture
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
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
Cette commande capture l'instance de serveur virtuel portant l'ID 12345678 avec tous les disques dans une image nommée "mycloud" et ayant la note "testing".

## ibmcloud sl vs create
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
<dt>--flavor</dt>
<dd>Nom de clé de la version Serveur virtuel public.</dd>
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
<dt>--host-id</dt>
<dd>ID hôte sur lequel mettre à disposition un serveur virtuel dédié.</dd>
<dt>--san</dt>
<dd>Utiliser le stockage SAN à la place d'un disque local.</dd>
<dt>--test</dt>
<dd>Ne pas créer le serveur virtuel.</dd>
<dt>--export</dt>
<dd>Exporter les options vers un fichier modèle.</dd>
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
<dt>-g, --tag</dt>
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
<dt>-S, --public-security-group</dt>
<dd>ID du groupe de sécurité à associer à l'interface publique (occurrences multiples permises).</dd>
<dt>-s, --private-security-group</dt>
<dd>ID du groupe de sécurité à associer à l'interface privée (occurrences multiples permises).</dd>
<dt>--wait</dt>
<dd>Attendre pendant X secondes au maximum que le serveur virtuel soit mis à disposition avant de revenir.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Cette commande permet de commander une instance de serveur virtuel dont le nom d'hôte (hostname) est myvsi, le domaine (domain) est ibm.com, qui comporte 4 coeurs d'UC, 4096 Mo de mémoire et qui se trouve sur le centre de données dal10

## ibmcloud sl vs options
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

## ibmcloud sl vs credentials
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

## ibmcloud sl vs detail
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

## ibmcloud sl vs dns-sync
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

## ibmcloud sl vs edit
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
<dt>-g, --tag</dt>
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
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
Cette commande met à jour l'instance de serveur virtuel portant l'ID 12345678 et lui affecte la valeur "ibm.com" comme domaine, la valeur "myapp" comme nom d'hôte et la valeur "testcli" comme étiquette

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Créer un hôte pour les serveurs virtuels dédiés.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-H, --hostname</dt>
<dd>Obligatoire. Partie hôte du nom de domaine complet.</dd>
<dt>-D, --domain</dt>
<dd>Obligatoire. Partie domaine du nom de domaine complet.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données.</dd>
<dt>-s, --size</dt>
<dd>Taille de l'hôte dédié. Une seule taille est actuellement disponible : 56_CORES_X_242_RAM_X_1_4_TB.</dd>
<dt>-b, --billing</dt>
<dd>Taux de facturation. Par défaut : hourly. Options : hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>ID du VLAN privé sur lequel vous voulez placer l'hôte dédié. Voir 'ibmcloud sl vlan list' pour référence.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

Répertorier tous les hôtes dédiés sur votre compte.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>Options de commande</strong> :
<dl>
<dt>-n, --name</dt>
<dd>Filtrer par nom de l'hôte dédié.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par centre de données de l'hôte dédié.</dd>
<dt>--owner</dt>
<dd>Filtrer par propriétaire de l'hôte dédié.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de la commande pour l'achat de cet hôte dédié.</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

Permet de répertorier les instances de serveur virtuel sur votre compte.
```
ibmcloud sl vs list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-c, --cpu</dt>
<dd>Filtrer par nombre de coeurs d'UC.</dd>
<dt>-D, --domain</dt>
<dd>Filtrer par portion de domaine du nom de domaine complet.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrer par portion d'hôte du nom de domaine complet.</dd>
<dt>-m, --memory</dt>
<dd>Filtrer par mémoire en mégaoctets.</dd>
<dt>-n, --network</dt>
<dd>Filtrer par vitesse du port réseau, exprimée en Mbit/s.</dd>
<dt>-P, --public-ip</dt>
<dd>Filtrer par adresse IP publique.</dd>
<dt>-p, --private-ip</dt>
<dd>Filtrer par adresse IP privée.</dd>
<dt>--hourly</dt>
<dd>Afficher uniquement les instances horaires.</dd>
<dt>--monthly</dt>
<dd>Afficher uniquement les instances mensuelles.</dd>
<dt>-g, --tag</dt>
<dd>Filtrer par étiquettes (plusieurs occurrences autorisées).</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de la commande pour l'achat de cette instance.</dd>
<dt>--owner</dt>
<dd>Filtrer par ID de l'utilisateur qui possède les instances.</dd>
<dt>--sortby</dt>
<dd>Colonne de tri par défaut : hostname, options :id, hostname, domain, datacenter, cpu, memory, public_ip, private_ip.</dd>
<dt>--columns</dt>
<dd>Colonnes à afficher par défaut :id, hostname, public_ip, private_ip, datacenter, action, options : guid, power_state, created_by, tags.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
Cette commande répertorie toutes les instances de serveur virtuel facturées à l'heure sur le compte en cours, avec comme nom de domaine "ibm.com", et les trie par mémoire.

## ibmcloud sl vs pause
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

## ibmcloud sl vs power-off
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

## ibmcloud sl vs power-on
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

## ibmcloud sl vs ready
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

## ibmcloud sl vs reboot
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

## ibmcloud sl vs reload
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

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

Permet de réamorcer une instance de serveur virtuel dans une image de secours.
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

## ibmcloud sl vs resume
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

## ibmcloud sl vs upgrade
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
