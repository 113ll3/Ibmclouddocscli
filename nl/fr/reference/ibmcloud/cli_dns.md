---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Serveur DNS de l'infrastructure {{site.data.keyword.Bluemix_notm}}

Les commandes suivantes permettent de gérer les zones dans le service DNS de l'infrastructure {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Commandes DNS de l'infrastructure {{site.data.keyword.Bluemix_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires sur la commande">
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list
](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

## ibmcloud sl dns import
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
ibmcloud sl dns import ~/ibm.com.txt
```
Cette commande importe une zone et ses enregistrements de ressource à partir du fichier ~/ibm.com.txt.

## ibmcloud sl dns record-add
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
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
Cette commande ajoute un enregistrement A à la zone ibm.com. Son hôte est "ftp", ses données sont "127.0.0.1" et la valeur de durée de vie est de 86400 secondes.

## ibmcloud sl dns record-edit
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
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Cette commande modifie des enregistrements sous la zone ibm.com dont l'ID est 12345678, et affecte la valeur "127.0.0.2" au paramètre de données et la valeur 3600 au paramètre de durée de vie.

## ibmcloud sl dns record-list
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
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
Cette commande répertorie tous les enregistrements A sous la zone ibm.com. La valeur du paramètre de filtrage par hôte est elasticsearch et la valeur du paramètre de durée de vie est 900 secondes.

## ibmcloud sl dns record-remove
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

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Permet de créer une zone.
```
ibmcloud sl dns zone-create ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-create ibm.com
```
Cette commande crée une zone nommée ibm.com.

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Permet de supprimer une zone.
```
ibmcloud sl dns zone-delete ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-delete ibm.com
```
Cette commande supprime une zone nommée ibm.com.

## ibmcloud sl dns zone-list
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

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Permet d'imprimer les enregistrements de ressource et de zone au format BIND.
```
ibmcloud sl dns zone-print ZONE
```


**Exemples** :
```
ibmcloud sl dns zone-print ibm.com
```
Cette commande imprime une zone nommée ibm.com au format BIND.
