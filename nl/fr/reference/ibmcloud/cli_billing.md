---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Affichage de l'utilisation pour les comptes, les organisations, les groupes de ressources et les ressources 
{: #ibmcloud_billing}

Les commandes suivantes permettent d'extraire les informations sur la facturation et l'utilisation des ressources.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Afficher l'utilisation mensuelle du compte en cours (administrateur de compte uniquement) :
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Affichez des données pour le mois et la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
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

Afficher l'utilisation mensuelle pour une organisation (administrateur de compte ou responsable de facturation de l'organisation uniquement) :
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>ORG_NAME (obligatoire)</dt>
  <dd>Nom de l'organisation.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Affichez des données pour le mois et la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Afficher l'utilisation mensuelle pour un groupe de ressources (administrateur de compte ou administrateur de groupe de ressources uniquement) :
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>GROUP_NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Affichez des données pour le mois et la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Afficher l'utilisation mensuelle des instances de ressource sous le compte en cours :
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
  <dd>Affichez des données pour le mois et la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

Afficher des rapports d'utilisation d'entreprise :
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>--account ACCOUNT_NAME (facultatif)</dt>
  <dd>Nom du compte cible.</dd>
  <dt>--account-id ACCOUNT_ID (facultatif)</dt>
  <dd>ID du compte cible.</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME (facultatif)</dt>
  <dd>Nom du groupe de comptes cible.</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID (facultatif)</dt>
  <dd>ID du groupe de comptes cible.</dd>
  <dt>--children (facultatif)</dt>
  <dd>Affichez les rapports d'utilisation des enfants.</dd>
  <dt>--month MONTH (facultatif)</dt>
  <dd>Mois cible. Par défaut, il s'agit du compte actuel.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>
