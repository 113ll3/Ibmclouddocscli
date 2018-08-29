---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion des adresses IP globales de l'infrastructure {{site.data.keyword.Bluemix_notm}}

<table summary="Commandes générales de l'infrastructure {{site.data.keyword.Bluemix_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes pour les adresses IP globales de l'infrastructure {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Commandes pour les adresses IP globales de l'infrastructure {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Permet d'affecter une adresse IP globale à un routeur ou un périphérique cible.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Exemples** :
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
Cette commande affecte une adresse IP portant l'ID 12345678 à une unité cible dont l'adresse IP est 9.111.123.456.

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Permet d'annuler une adresse IP globale.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip cancel 12345678
```
Cette commande annule une adresse IP portant l'ID 12345678.

 ## ibmcloud sl globalip create
{: #sl_globalip_create}

Permet de créer une adresse IP globale.
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--v6</dt>
<dd>Commandez une adresse IP IPv6.</dd>
<dt>--test</dt>
<dd>Indique qu'une commande doit être testée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip create --v6
```
Cette commande crée une adresse IP V6.

## ibmcloud sl globalip list
{: #sl_globalip_list}

Permet de répertorier toutes les adresses IP globale sur votre compte.
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--v4</dt>
<dd>Afficher uniquement les éléments IPv4.</dd>
<dt>--v6</dt>
<dd>Afficher uniquement les éléments IPv6.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter cette adresse IP.</dd>
</dl>

**Exemples** :
```
ibmcloud sl globalip list --v4
```
Cette commande répertorie toutes les adresses IP V4 sur le compte en cours.

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Permet d'annuler l'affectation d'une adresse IP globale à partir d'un routeur ou d'un périphérique cible.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Exemples** :
```
ibmcloud sl globalip unassign 12345678
```
Cette commande annule l'affectation d'une adresse IP portant l'ID 12345678 à partir de l'unité cible.
