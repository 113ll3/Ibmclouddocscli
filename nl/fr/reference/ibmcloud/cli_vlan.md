---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, vlan, classic vlan, ibmcloud sl vlan, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestion des réseaux locaux virtuels (VLAN) de l'infrastructure classique
{: #manage-classic-vlans}

Les réseaux locaux virtuels (VLAN) sont utilisés par {{site.data.keyword.cloud}} pour isoler le trafic diffusé sur le réseau public et le réseau privé. Ces réseaux sont affectés en fonction des besoins des autres offres.

Les commandes suivantes permettent de gérer les réseaux locaux virtuels de l'infrastructure classique.
{: shortdesc}

## ibmcloud sl vlan create
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
<dt>-n, --name</dt>
<dd>Nom du réseau local virtuel.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
{: codeblock}

Cette commande crée un réseau local virtuel public sur le centre de données `dal09` avec 16 adresses IP, et lui affecte le nom `myvlan`.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Annuler un réseau local virtuel :
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
{: codeblock}

Cette commande annule le réseau local virtuel portant l'ID `12345678` sans demander de confirmation.

## ibmcloud sl vlan detail
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
{: codeblock}

Cette commande affiche les détails relatifs au réseau local virtuel portant l'ID `12345678` mais n'indique pas le serveur virtuel ou le serveur matériel.

## ibmcloud sl vlan edit
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
{: codeblock}

Cette commande met à jour le réseau local virtuel portant l'ID `ID 12345678` et lui affecte le nouveau nom `myvlan-rename`.

## ibmcloud sl vlan list
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
Cette commande répertorie tous les réseaux locaux virtuels sur le compte en cours pour le centre de données `dal09`, et les trie par numéro de réseau local virtuel.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Permet de répertorier toutes les options de création de réseau local virtuel.
```
ibmcloud sl vlan options
```
{: codeblock}

**Exemples** :
```
ibmcloud sl vlan options
```
{: codeblock}

Cette commande répertorie toutes les options de création d'un réseau local virtuel, par exemple, type de réseau local virtuel, centre de données, taille de sous-réseau, routeurs, etc.
