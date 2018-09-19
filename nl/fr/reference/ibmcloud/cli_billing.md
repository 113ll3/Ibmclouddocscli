---

copyright:

  years: 2018


lastupdated: "2018-09-04"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Facturation 
{: #ibmcloud_billing}

Les commandes suivantes permettent de gérer l'utilisation et la facturation {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Commandes ibmcloud permettant de gérer l'utilisation et la facturation {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Afficher l'utilisation mensuelle du compte en cours (administrateur de compte seulement)

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Afficher le rapport d'utilisation et des coûts du compte en cours pour 2016-06 :

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Afficher l'utilisation mensuelle pour une organisation (administrateur de compte ou responsable de facturation d'organisation seulement)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>ORG_NAME (obligatoire)</dt>
  <dd>Nom de l'organisation.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Afficher l'utilisation mensuelle pour un groupe de ressources (administrateur de compte ou administrateur de groupe de ressources seulement)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>GROUP_NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Afficher l'utilisation mensuelle des instances de ressource sous le compte en cours.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-o ORG_NAME (facultatif)</dt>
  <dd>Filtrer les instances par organisation.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrer l'instance par groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>
