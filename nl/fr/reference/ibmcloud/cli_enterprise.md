---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion de l'entreprise, des groupes de comptes et des comptes
{: #ibmcloud_enterprise}

Les commandes suivantes permettent de gérer l'entreprise, les groupes de comptes et les comptes.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Créer une entreprise.
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de l'entreprise.</dd>
<dt>-d, --domain DOMAIN_NAME (facultatif)</dt>
<dd>Nom du domaine.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (facultatif)</dt>
<dd>ID utilisateur du contact principal de l'entreprise.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Mettre à jour les informations de l'entreprise.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>-f, --force (facultatif)</dt>
<dd>Procédez à une mise à jour sans confirmation.</dd>
<dt>-n, --name NEW_NAME (obligatoire)</dt>
<dd>Nouveau nom de l'entreprise.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Afficher les détails de l'entreprise.
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Créer un groupe de comptes.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom du groupe de comptes.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (facultatif)</dt>
<dd>Nom du groupe de comptes parent. Si cette valeur est omise, le parent sera l'entreprise en cours.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (facultatif)</dt>
<dd>ID utilisateur du contact principal du groupe de comptes.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Mettre à jour un groupe de comptes.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--id ID (obligatoire)</dt>
<dd>ID du groupe de comptes cible. Cette option exclut `-n, --name`.</dd>
<dt>-n, --name NAME (obligatoire)</dt>
<dd>Nom du groupe de comptes cible. Cette option exclut `--id`.</dd>
<dt>--new-name NEW_NAME (obligatoire)</dt>
<dd>Nouveau nom du groupe de comptes cible.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Afficher les détails du groupe de comptes.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--id ID (obligatoire)</dt>
<dd>ID du groupe de comptes. Cette option exclut `-n, --name`.</dd>
<dt>-n, --name NAME (obligatoire)</dt>
<dd>Nom du groupe de comptes. Cette option exclut `--id`.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

Répertorier les groupes de comptes.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (facultatif)</dt>
<dd>Nom du groupe de comptes parent. Cette option exclut `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (facultatif)</dt>
<dd>ID du groupe de comptes parent. Cette option exclut `--parent-account-group`.</dd>
<dt>--recursive (facultatif)</dt>
<dd>Affichez les groupes de comptes descendants.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Créer un compte.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom du groupe de comptes.</dd>
<dt>--owner USER_ID (facultatif)</dt>
<dd>ID utilisateur du groupe de comptes.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (facultatif).</dt>
<dd>Nom du groupe de comptes parent. Si cette valeur est omise, le parent sera l'entreprise en cours.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Déplacer un compte sous un autre parent.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--id ID (obligatoire)</dt>
<dd>ID du compte cible. Cette option exclut `-n, --name`.</dd>
<dt>-n, --name NAME (obligatoire)</dt>
<dd>Nom du compte cible. Cette option exclut `--id`.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (obligatoire)</dt>
<dd>Nom du groupe de comptes parent. Cette option exclut `--parent-account-group-id` et `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (obligatoire)</dt>
<dd>ID du groupe de comptes parent. Cette option exclut `--parent-account-group` et `--parent-enterprise`.</dd>
<dt>--parent-enterprise (obligatoire)</dt>
<dd>Définissez l'entreprise comme parent. Cette option exclut `--parent-account-group` et `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Afficher les détails d'un compte.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--id ID (obligatoire)</dt>
<dd>ID du compte. Cette option exclut `-n, --name`.</dd>
<dt>-n, --name NAME (obligatoire)</dt>
<dd>Nom du compte. Cette option exclut `--id`.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

Répertorier des comptes.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (facultatif)</dt>
<dd>Nom du groupe de comptes parent. Cette option exclut `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (facultatif)</dt>
<dd>ID du groupe de comptes parent. Cette option exclut `--parent-account-group`.</dd>
<dt>--recursive (facultatif)</dt>
<dd>Affichez les comptes descendants.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Importer un compte autonome.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
<dt>--account-id</dt>
<dd>ID du compte source.</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (facultatif)</dt>
<dd>Nom du groupe de comptes parent. Cette option exclut `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (facultatif)</dt>
<dd>ID du groupe de comptes parent. Cette option exclut `--parent-account-group`.</dd>
</dl>
