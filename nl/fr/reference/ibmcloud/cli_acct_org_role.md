---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comptes, utilisateurs et organisations
{: #ibmcloud_commands_account}

Les commandes suivantes permettent de gérer des comptes, les utilisateurs d'un compte, ainsi que l'organisation, l'espace et les rôles des environnements Cloud Foundry publics.
{: shortdesc}

  <table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les comptes, les organisations , les espaces et les rôles.">
   <thead>
   </thead>
   <tbody>
   <tr>
   <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
   <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
   <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
   <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
   <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
   </tr>
   <tr>
   <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
   <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
   <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
   <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
   <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
   </tr>
   <tr>
   <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
   <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
   <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
   <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
   <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
   </tr>
   <tr>
   <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
   <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
   <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
   <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
   <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
  </tr>
   <td>[ibmcloud account list
](cli_acct_org_role.html#ibmcloud_account_list)</td>
   <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
   <td>[ibmcloud account users
](cli_acct_org_role.html#ibmcloud_account_users)</td>
   <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
   <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
   </tr>
   <tr>
    <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
   </tr>
   </tbody>
   </table>

 ## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Répertorier toutes les organisations

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Nom de région. Permet de répertorier les organisations de la région indiquée. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée. Si la valeur 'all' est indiquée, les organisations de toutes les régions sont répertoriées.</dd>
   <dt>--guid</dt>
   <dd>Afficher l'identificateur global unique des organisations Cette option exclut '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--guid'.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>ID compte. Permet de répertorier les organisations du compte spécifié. Par défaut, il s'agit du compte actuel si aucune valeur n'est indiquée. Si la valeur 'all' est indiquée, les organisations de tous les comptes sont répertoriées. Cette option exclut '-u'.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Nom du propriétaire du compte. Permet de répertorier les organisations des comptes appartenant à l'utilisateur indiqué. Par défaut, il s'agit du compte actuel si aucune valeur n'est indiquée. Si la valeur 'all' est indiquée, les organisations de tous les comptes sont répertoriées. Cette option exclut '-c'.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier toutes les organisations dans la région `us-south` en affichant leur identificateur global unique

```
ibmcloud account orgs -r us-south --guid
```

Répertorier toutes les organisations au format JSON

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Afficher les informations de l'organisation indiquée.

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>-r REGION</dt>
   <dd>Nom de région. Si aucun élément n'est défini, la région en cours est la valeur par défaut. Si 'all' est indiqué, les organisations de toutes les régions ayant le nom indiqué sont répertoriées.</dd>
   <dt>--guid</dt>
   <dd>Extraire et afficher l'identificateur global unique de l'organisation donnée. Toute autre sortie pour l'organisation est supprimée. Cette option exclut '--output'.</dd>
   <dt>--output REGION</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--guid'.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les informations de l'organisation `IBM` en indiquant son identificateur global unique (GUID)

```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
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

## ibmcloud account org-replicate
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

## ibmcloud account org-rename
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

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Répertorier tous les espaces

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>Nom de l'organisation. Liste des espaces sous l'organisation spécifiée. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>-r REGION-NAM</dt>
   <dd>Nom de région. Liste des espaces sous la région spécifiée. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier tous les espaces :

```
ibmcloud account spaces
```

Répertorier tous les espaces de l'organisation `org_example` au format JSON :

```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

Afficher les informations de l'espace indiqué

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace à afficher.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--guid</dt>
   <dd>Extraire et afficher l'identificateur global unique de l'espace donné. Toute autre sortie pour l'espace est supprimée. Cette option exclut '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Toute autre sortie pour l'espace est supprimée. Cette option exclut '--guid'.</dd>
   <dt>--security-group-rules</dt>
   <dd>Extraire les règles pour tous les groupes de sécurité associés à l'espace</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les informations de l'espace `space_example` :

```
ibmcloud account space space_example
```

Afficher l'identificateur global unique de l'espace `space_example` :

```
ibmcloud account space space_example --guid
```

Afficher les informations de l'espace `space_example` au format JSON :

```
ibmcloud account space space_example --output JSON
```

Afficher les règles du groupe de sécurité pour l'espace `space_example` :

```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Cette commande possède la même fonction et les mêmes options que la commande [cf rename-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Cette commande possède la même fonction et les mêmes options que la commande [cf delete-space ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## ibmcloud account org-users
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

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Ajouter un utilisateur à une organisation (un responsable d'organisation est requis).

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
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

## ibmcloud account org-roles
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

## ibmcloud account org-role-set
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

## ibmcloud account org-role-unset
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

## ibmcloud account space-users
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

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Affecte un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un responsable d'espace.

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

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Suppression de l'affectation d'un rôle d'espace à un utilisateur. Cette opération ne peut être réalisée que par un responsable d'espace.

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

## ibmcloud account list
{: #ibmcloud_account_list}

Afficher la liste de tous les comptes de l'utilisateur en cours

```
ibmcloud account list
```

<strong>Prérequis</strong> : Noeud final, Connexion

## ibmcloud account org-account
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

## ibmcloud account users
{: #ibmcloud_account_users}

Affiche les utilisateurs associés au compte. Cette opération ne peut être effectuée que par le propriétaire de compte.

```
ibmcloud account users
```

## ibmcloud account user-remove
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

## ibmcloud account user-invite
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

## ibmcloud account user-reinvite
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
