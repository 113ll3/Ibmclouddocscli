---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestion des tickets de l'infrastructure classique
{: #manage-sl-tickets}

Les commandes suivantes permettent de gérer les tickets de l'infrastructure classique {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

Associer des appareils à un ticket :
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--hardware</dt>
<dd>Identificateur pour un matériel à connecter.</dd>
<dt>--virtual</dt>
<dd>Identificateur pour un serveur virtuel à connecter.</dd>
</dl>

**Exemples** :
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

Créer un ticket de support :
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--attachment</dt>
<dd>Numéro d'ID objet initial à connecter au ticket.</dd>
<dt>--rootpwd</dt>
<dd>Mot de passe root associé à l'ID de l'appareil associé.</dd>
<dt>--subject-id</dt>
<dd>Obligatoire. ID de l'objet à utiliser pour le ticket, exécutez `ibmcloudsl ticket subjects` pour obtenir la liste.</dd>
<dt>--title</dt>
<dd>Obligatoire. Titre du ticket</dd>
<dt>--body</dt>
<dd>Corps de ticket.</dd>
<dt>--priority</dt>
<dd>Priorité du ticket [1|2|3|4], de 1 (Critique) à 4 (Impact minimal). Peut être défini uniquement avec le support Avancé et Premium. Voir https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Indiquez le type d'élément joint, matériel ou virtuel. Par défaut, l'élément est matériel.</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

Dissocier des appareils d'un ticket :
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--hardware</dt>
<dd>Identificateur pour un matériel à déconnecter.</dd>
<dt>--virtual</dt>
<dd>Identificateur pour un serveur virtuel à déconnecter.</dd>
</dl>

**Exemples** :
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

Afficher les détails du ticket :
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--count</dt>
<dd>Nombre de mises à jour.</dd>
</dl>

**Exemples** :
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

Répertorier les tickets :
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--open</dt>
<dd>Afficher uniquement les tickets ouverts.</dd>
<dt>--closed</dt>
<dd>Afficher uniquement les tickets fermés.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

Répertorier les ID d'objet pour la création de ticket :
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

Afficher les informations récapitulatives sur les tickets :
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

Ajouter une mise à jour à un ticket existant :
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Exemples** :
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

Ajouter un élément à un ticket existant :
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>Options de commande</strong> :
<dl>
<dt>--name</dt>
<dd>Nom de l'élément ajouté présenté dans le ticket.</dd>
</dl>

**Exemples** :
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

