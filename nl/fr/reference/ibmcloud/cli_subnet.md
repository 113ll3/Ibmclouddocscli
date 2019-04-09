---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Création, annulation et affichage de sous-réseaux

Un sous-réseau est une partition logique d'un réseau IP dans plusieurs segments de réseau plus petits. Les commandes suivantes permettent de gérer les sous-réseaux de l'infrastructure classique {{site.data.keyword.Bluemix}}.
{: shortdesc}

<table summary="Commandes Subnet de l'infrastructure classique {{site.data.keyword.Bluemix_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires pour la commande">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
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

## ibmcloud sl subnet create
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

## ibmcloud sl subnet detail
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

## ibmcloud sl subnet list
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

## ibmcloud sl subnet lookup
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
