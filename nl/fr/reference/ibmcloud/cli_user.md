---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-07"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestion des utilisateurs de l'infrastructure classique
{: #manage-sl-users}

Utilisez les commandes suivantes pour gérer les utilisateurs de l'infrastructure classique {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

Créer un utilisateur :
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Options de commande</strong> :
<dl>
<dt>--email</dt>
<dd>Adresse électronique de cet utilisateur. Cet élément est requis pour la création.</dd>
<dt>--password</dt>
<dd>Mot de passe à définir pour cet utilisateur. Si aucun mot de passe n'est indiqué, un message électronique expirant au bout de 24 heures est envoyé à l'utilisateur afin qu'il en génère un. Indiquez l'option '-p generate' pour qu'un mot de passe soit généré automatiquement pour vous. Les mots de passe doivent inclure au moins 8 caractères, des caractères minuscules, des caractères majuscules, un chiffre et un symbole.</dd>
<dt>--from-user</dt>
<dd>Utilisateur de base à employer comme modèle pour la création de cet utilisateur. Par défaut, il s'agit de l'utilisateur qui exécute cette commande. Les informations fournies dans --template remplacent ce modèle.</dd>
<dt>--template</dt>
<dd>Chaîne JSON qui décrit https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
<dt>--api-key</dt>
<dd>Créer une clé d'API pour cet utilisateur.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Attribue le statut `CANCEL_PENDING` à un utilisateur, ce qui permet de désactiver automatiquement le compte. L'utilisateur peut être retiré du compte par un processus interne automatisé.
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

Afficher les détails d'un utilisateur :
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>--keys</dt>
<dd>Afficher la clé de l'API d'utilisateurs.</dd>
<dt>--permissions</dt>
<dd>Afficher les droits affectés à cet utilisateur. Aucun droit n'est affiché pour les utilisateurs principaux.</dd>
<dt>--hardware</dt>
<dd>Afficher le matériel auquel cet utilisateur a accès.</dd>
<dt>--virtual</dt>
<dd>Afficher les invités virtuels auxquels cet utilisateur a accès.</dd>
<dt>--logins</dt>
<dd>Afficher l'historique de connexion de cet utilisateur au cours des 30 derniers jours.</dd>
<dt>--events</dt>
<dd>Afficher le journal d'audit pour cet utilisateur.</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

Editer les détails d'un utilisateur :
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>--template</dt>
<dd>Chaîne JSON qui décrit https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

Activer ou désactiver des droits utilisateur spécifiques :
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Options de commande</strong> :
<dl>
<dt>--enable</dt>
<dd>Activer ou désactiver les droits sélectionnés. Les entrées admises sont 'true' et 'false'. La valeur par défaut est 'true'.</dd>
<dt>--permission</dt>
<dd>Droit `keyName` à définir, plusieurs instances autorisées. Utilisez le mot clé ALL pour sélectionner tous les droits.</dd>
<dt>--from-user</dt>
<dd>Définir des droits qui correspondent aux droits de cet utilisateur. Ajoute et retire les droits appropriés.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

Répertorier les utilisateurs :
```
ibmcloud sl user list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--column</dt>
<dd>Colonne à afficher. [Options : id,username,email,displayName,status,hardwareCount,virtualGuestCount][default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

Afficher les droits utilisateur :
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

