---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Configuration matérielle

Les commandes suivantes permettent de gérer les serveurs matériels bare metal de l'infrastructure {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Commandes de serveur bare metal de l'infrastructure {{site.data.keyword.Bluemix_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires sur la commande">
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Annuler un serveur matériel
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-i, --immediate</dt>
<dd>Annule immédiatement le serveur (et non à la date anniversaire de facturation).</dd>
<dt>-r, --reason</dt>
<dd>Motif facultatif d'annulation. Pour obtenir la liste des options disponibles, voir 'ibmcloud sl hardware cancel-reasons'.</dd>
<dt>-c, --comment</dt>
<dd>Commentaire facultatif à ajouter au ticket d'annulation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Afficher la liste des raisons de l'annulation.
```
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

Commander/créer un serveur matériel.
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-H, --hostname</dt>
<dd>Portion hôte du nom de domaine complet, obligatoire.</dd>
<dt>-D, --domain</dt>
<dd>Portion de domaine du nom de domaine complet, obligatoire.</dd>
<dt>-s, --size</dt>
<dd>Taille du matériel, obligatoire.</dd>
<dt>-o, --os</dt>
<dd>Code d'installation du système d'exploitation, obligatoire.</dd>
<dt>-d, --datacenter</dt>
<dd>Nom abrégé du centre de données, obligatoire.</dd>
<dt>-p, --port-speed</dt>
<dd>Vitesse du port, obligatoire.</dd>
<dt>-b, --billing</dt>
<dd>Taux de facturation, horaire ou mensuel. Si aucune valeur n'est spécifiée, la valeur par défaut hourly (horaire) est utilisée.</dd>
<dt>-i, --post-install</dt>
<dd>Script de post-installation à télécharger.</dd>
<dt>-k, --key</dt>
<dd>Clés SSH à ajouter à l'utilisateur root, plusieurs occurrences autorisées.</dd>
<dt>-n, --no-public</dt>
<dd>Réseau privé uniquement.</dd>
<dt>-e, --extra</dt>
<dd>Options supplémentaires, plusieurs occurrences autorisées.</dd>
<dt>-t, --test</dt>
<dd>Ne pas créer le serveur virtuel.</dd>
<dt>-m, --template</dt>
<dd>Fichier modèle qui indique les options de ligne de commande par défaut.</dd>
<dt>-x, --export</dt>
<dd>Exporter les options vers un fichier modèle.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Options de commande de serveur pour un châssis donné.
```
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

Répertorier les données d'identification du serveur matériel.
```
ibmcloud sl hardware credentials IDENTIFIER
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

Obtenir les détails d'un serveur matériel.
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-p, --passwords</dt>
<dd>Afficher les mots de passe (à l'abri des regards).</dd>
<dt>-c, --price</dt>
<dd>Afficher les prix associés.</dd>
</dl>

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

Modifier les détails du serveur matériel.
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-H, --hostname</dt>
<dd>Portion hôte du nom de domaine complet.</dd>
<dt>-D, --domain</dt>
<dd>Partie domaine du nom de domaine complet.</dd>
<dt>-g, --tag</dt>
<dd>Etiquettes à définir ou chaîne vide pour tout retirer.</dd>
<dt>-F, --userfile</dt>
<dd>Lire les données utilisateur à partir du fichier.</dd>
<dt>-u, --userdata</dt>
<dd>Chaîne de métadonnées définie par l'utilisateur.</dd>
<dt>-p, --public-speed</dt>
<dd>Vitesse de port public. Les options possibles sont les suivantes : 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Vitesse de port privé. Les options possibles sont les suivantes : 0,10,100,1000,10000.</dd>
</dl>

## ibmcloud sl hardware list
{: #sl_hardware_list}

Répertorier les serveurs matériels.
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-c, --cpu</dt>
<dd>Filtrer par nombre de coeurs d'UC.</dd>
<dt>-D, --domain</dt>
<dd>Filtrer par domaine.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrer par nom d'hôte.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrer par centre de données.</dd>
<dt>-m, --memory</dt>
<dd>Filtrer par mémoire en gigaoctets.</dd>
<dt>-n, --network</dt>
<dd>Filtrer par vitesse du port réseau, exprimée en Mbit/s.</dd>
<dt>-g, --tag</dt>
<dd>Filtrer par étiquettes, plusieurs occurrences autorisées.</dd>
<dt>-p, --public-ip</dt>
<dd>Filtrer par adresse IP publique.</dd>
<dt>-v, --private-ip</dt>
<dd>Filtrer par adresse IP privée.</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de commande ayant acheté le serveur matériel.</dd>
<dt>--owner</dt>
<dd>Filtrer par ID de propriétaire.</dd>
<dt>--sortby</dt>
<dd>Colonne à utiliser pour le tri : default:hostname, option:id, guid,hostname, domain, public_ip, private_ip, datacenter, status, ipmi_ip, created, created_by.</dd>
<dt>--columns</dt>
<dd>Colonnes à afficher : default:id, hostname, domain, public_ip, private_ip, datacenter, status, options:guid, cpu, memory, os, ipmi_ip, created, created_by, tags.</dd>
</dl>

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Arrêter puis redémarrer un serveur.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Mettre hors tension un serveur actif.
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Mettre sous tension un serveur.
```
ibmcloud sl hardware power-on IDENTIFIER
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Réamorcer un serveur actif.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
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

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

Recharger un système d'exploitation sur un serveur.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de post-installation à télécharger, exécuté uniquement par HTTPS, HTTP sauvegarde le fichier sous /root.</dd>
<dt>-k, --key</dt>
<dd>ID de la clé SSH à ajouter à l'utilisateur root, plusieurs occurrences autorisées.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>Mettre à niveau le système BIOS.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Mettre à niveau le microprogramme de tous les disques durs.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Réamorcer un serveur dans une image de secours.
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Mettre à jour le microprogramme du serveur.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
