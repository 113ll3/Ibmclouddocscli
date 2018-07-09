---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes de l'interface CLI pour la gestion des comptes, des organisations et des rôles
 {: #ibmcloud_commands_account}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les comptes, les organisations, les espaces et les rôles.">
<caption>Tableau 1. Commandes de gestion des comptes, des organisations, des espaces et des rôles</caption>
 <thead>
 <th colspan="5">Commandes de gestion des comptes, des organisations, des espaces et des rôles</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](ic_cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](ic_cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](ic_cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](ic_cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](ic_cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](ic_cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](ic_cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](ic_cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](ic_cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](ic_cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](ic_cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](ic_cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](ic_cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](ic_cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](ic_cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](ic_cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](ic_cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](ic_cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](ic_cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](ic_cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](ic_cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](ic_cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](ic_cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](ic_cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](ic_cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](ic_cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Répertorier toutes les organisations

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r <i>REGION</i> (facultatif)</dt>
   <dd>Spécifie la région pour laquelle afficher les informations de l'organisation. Si vous spécifiez 'all', toutes les
organisations de toutes les régions sont répertoriées.</dd>
   <dt>--guid (facultatif)</dt>
   <dd>Affiche l'identificateur global unique (GUID) des organisations.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier toutes les organisations dans la région `us-south` en affichant leur identificateur global unique

```
ibmcloud account orgs -r us-south --guid
```

### ibmcloud account org
{: #ibmcloud_account_org}

Affiche des informations sur l'organisation spécifiée.

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>--guid (facultatif)</dt>
   <dd>Affiche l'identificateur global unique (GUID) de l'organisation.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les informations de l'organisation `IBM` en indiquant son identificateur global unique (GUID)

```
ibmcloud account org IBM --guid
```

### ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crée une nouvelle organisation. Cette opération ne peut être effectuée que par un propriétaire de compte.

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à créer.</dd>
   <dt>-f</dt>
   <dd>Forcer la création sans confirmation.</dd>
   </dl>

<strong>Exemples</strong> :

Création d'une organisation nommée `IBM`.

```
ibmcloud account org-create IBM
```

### ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Répliquez une organisation de la région en cours dans une autre région.

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation existante à répliquer.</dd>
   <dt>REGION_NAME (obligatoire)</dt>
   <dd>Nom de la région hébergeant l'organisation répliquée.</dd>
   </dl>

<strong>Exemples</strong> :

Réplication de l'organisation `mon_org` dans la région `eu-gb`:

```
ibmcloud account org-replicate myorg eu-gb
```

### ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Attribue un nouveau nom à une organisation. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>OLD_ORG_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'organisation qui sera renommée.</dd>
   <dt>NEW_ORG_NAME (obligatoire)</dt>
   <dd>Nouveau nom à affecter à l'organisation.</dd>
   </dl>

### ibmcloud account spaces
{: #ibmcloud_account_spaces}

Répertorier tous les espaces

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Options de commande</strong> :
   <dl>
   <dt>-o</dt>
   <dd>Nom de l'organisation. Liste des espaces sous l'organisation spécifiée. Valeur par défaut sur l'organisation actuelle si rien n'est indiqué.</dd>
   <dt>-r</dt>
   <dd>Nom de région. Liste des espaces sous la région spécifiée. Valeur par défaut sur la région actuelle si rien n'est indiqué.</dd>
   </dl>

### ibmcloud account space
{: #ibmcloud_account_space}

Cette commande possède la même fonction et les mêmes options que la commande [cf space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Cette commande possède la même fonction et les mêmes options que la commande [cf rename-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Cette commande possède la même fonction et les mêmes options que la commande [cf delete-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

### ibmcloud account org-users
{: #ibmcloud_account_org_users}

Affiche les utilisateurs dans l'organisation spécifiée, par rôle.

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>ORG_NAME (obligatoire)</dt>
<dd>Nom de l'organisation.</dd>
<dt>-a (facultatif)</dt>
<dd>Recense tous les utilisateurs de l'organisation spécifiés, sans les regrouper par rôle.</dd>
</dl>

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Ajouter un utilisateur à une organisation (un responsable d'organisation est requis).

```
 ibmcloud account org-user-add USER_NAME ORG
```

### ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Retirer un utilisateur d'une organisation (responsable d'organisation ou utilisateur/utilisatrice proprement dit(e))

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Options de commande</strong> :
<dl>
<dt>--force, -f</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Extraire tous les rôles d'organisation de l'utilisateur en cours

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>-u</dt>
   <dd>ID utilisateur. S'il n'est pas spécifié, la valeur par défaut est l'utilisateur en cours.</dd>
  </dl>

### ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Affecte un rôle de l'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à affecter.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>ORG_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation auquel cet utilisateur est affecté. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
  </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` sous le rôle `OrgManager` :

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Remarque **: vous pouvez définir des rôles d'organisation ou d'espace via l'interface CLI, mais pour les autres autorisations, il vous utiliser l'interface utilisateur. Pour plus d'informations, voir [Octroi d'un accès utilisateur](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

### ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Supprime l'affectation d'un rôle d'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à supprimer.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>ORG_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
    </dl>

<strong>Exemples</strong> :

Retirer l'utilisatrice `Mary` de l'organisation `IBM` sous le rôle `OrgManager` :

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

### ibmcloud account space-users
{: #ibmcloud_account_space_users}

Affichage des utilisateurs, par rôle, dans l'espace spécifié.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace.</dd>
   </dl>

### ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Affecte un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à affecter.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace auquel affecter cet utilisateur.</dd>
   <dt>SPACE_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace auquel affecter cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
    </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` et à l'espace `Cloud` sous le rôle `SpaceManager` :

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

### ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Suppression de l'affectation d'un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un gestionnaire d'espace.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à supprimer.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace dans lequel supprimer cet utilisateur.</dd>
   <dt>SPACE_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
    </dl>


<strong>Exemples</strong> :

Retirer l'utilisatrice `Mary` de l'organisation `IBM` et de l'espace `Cloud` sous le rôle `SpaceManager` :

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

### ibmcloud account list
{: #ibmcloud_account_list}

Afficher la liste de tous les comptes de l'utilisateur en cours

```
ibmcloud account list
```

<strong>Prérequis</strong> : Noeud final, Connexion

### ibmcloud account org-account
{: #ibmcloud_account_org_account}

Afficher le compte de l'organisation spécifiée (utilisateur d'organisation requis).

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--guid (facultatif)</dt>
  <dd>Affiche uniquement l'ID de compte</dd>
</dl>

### ibmcloud account users
{: #ibmcloud_account_users}

Affiche les utilisateurs associés au compte. Cette opération ne peut être effectuée que par le propriétaire de compte.

```
ibmcloud account users
```

### ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Retirer un utilisateur d'un compte (propriétaire de compte uniquement)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>USER_ID (obligatoire)</dt>
<dd>ID utilisateur</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID compte. Si ce paramètre n'est pas spécifié, le compte en cours est pris par défaut.</dd>
<dt>-f, --force</dt>
<dd>Forcer le retrait sans confirmation.</dd>
</dl>

### ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Inviter un utilisateur à rejoindre le compte

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur invité.</dd>
   <dt>-o ORG</dt>
   <dd>Organisation dans laquelle inviter l'utilisateur</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Rôle organisationnel. Les entrées valides sont les suivantes : OrgManager, BillingManager, OrgAuditor et OrgUser. Si aucun élément n'est indiqué, le rôle OrgUser est défini.</dd>
   <dt>-s SPACE</dt>
   <dd>Espace dans lequel inviter l'utilisateur</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Rôle d'espace. Les valeurs valides sont les suivantes : SpaceManager, SpaceDeveloper et SpaceAuditor.</dd>
</dl>

### ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Renvoyer l'invitation à un utilisateur (administrateur de compte).

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur invité.</dd>
</dl>

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Afficher les groupes d'accès du compte en cours.

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-u</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'utilisateur appartient. Cette option est propre à '-s'.</dd>
  <dt>-s</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'ID de service appartient. Cette option est propre à '-u'.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes d'accès :

```
ibmcloud iam access-groups
```

### ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Afficher les détails d'un groupe d'accès

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-id</dt>
  <dd>Afficher l'ID uniquement</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails du groupe d'accès `example_group` :

```
ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Créer un groupe d'accès

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-d, --description</dt>
  <dd>Description de groupe d'accès</dd>
</dl>

<strong>Exemples</strong> :

Créer un groupe d'accès `example_group` :

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Mettre à jour un groupe d'accès

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-n, --name</dt>
  <dd>Nom du nouveau groupe d'accès</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe d'accès `example_group` en `hello_world_group` :

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

### ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Supprimer un groupe d'accès

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
  <dt>-r, --recursive</dt>
  <dd>Supprimer un groupe d'accès et ses membres</dd>
</dl>

<strong>Exemples</strong> :

Supprimer le groupe d'accès `example_group` :

```
ibmcloud iam access-group-delete example_group --force
```

### ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Afficher la liste des utilisateurs d'un groupe d'accès

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste de tous les utilisateurs du groupe d'accès `example_group` :

```
ibmcloud iam access-group-users example_group
```

### ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Ajouter un ou plusieurs utilisateurs à un groupe d'accès

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Ajouter l'utilisateur `name@example.com` au groupe d'accès `example_group` :

```
ibmcloud iam access group-user-add example_group name@example.com
```

### ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Retirer un utilisateur d'un groupe d'accès

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Retirer l'utilisateur `name@example.com` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

### ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Retirer l'utilisateur de tous les groupes d'accès

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Retirer l'utilisateur `name@example.com` de tous les groupes d'accès :

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Afficher la liste des ID de service d'un groupe d'accès

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste des ID de service du groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-ids example_group
```

### ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Ajouter un ID de service à un groupe d'accès

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Ajouter l'ID de service `example-service` au groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-id-add example_group example-service
```

### ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Retirer un ID de service d'un groupe d'accès

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Retirer l'ID de service `example-service` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

### ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Retirer un ID de service de tous les groupes d'accès

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Retirer l'ID de service `example-service` de tous les groupes d'accès :

```
ibmcloud iam access-group-service-id-purge example --force
```

### ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Afficher la liste des règles d'un groupe d'accès

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher la liste de toutes les règles du groupe d'accès `example_group` :

```
ibmcloud iam access-group-policies example_group
```

### ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Afficher les détails d'une règle de groupe d'accès

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la règle `51b9717e-76b0-4f6a-bda7-b8132431f926` du groupe d'accès `example_group` :

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Créer une règle de groupe d'accès

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>-roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Créer une règle de groupe d'accès à partir d'un fichier JSON :

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Accorder le rôle `Administrateur` à `example_group` pour toutes les ressources `sample-service` :
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Accorder le rôle `Editeur` à `example_group` pour la ressource `key123` de l'instance `sample-service` ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Accorder le rôle `Opérateur` à `example_group` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Mettre à jour une règle de groupe d'accès

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>--roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle de groupe d'accès avec celle d'un fichier JSON de règles :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Administrator` à `example_group` pour toutes les ressources `sample-service` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Editor` à `example_group` pour la ressource `key123` de l'instance `sample-service` ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Operator` à `example_group` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Viewer` à `example_group` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Viewer` à `example_group` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Supprimer une règle de groupe d'accès

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la règle `51b9717e-76b0-4f6a-bda7-b8132431f926` du groupe d'accès `example_group` :
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
