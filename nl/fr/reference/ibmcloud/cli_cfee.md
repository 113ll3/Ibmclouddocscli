---

copyright:

  years: 2018


lastupdated: "2018-11-08"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Environnements CFEE (Cloud Foundry Enterprise Environment)
{: #ibmcloud_commands_cfee}

{{site.data.keyword.cfee_full}} (CFEE) vous permet d'instancier à la demande plusieurs plateformes Cloud Foundry d'entreprise isolées. Les instances du service IBM Cloud Foundry Enterprise s'exécutent dans votre propre compte dans IBM Cloud. L'environnement est déployé sur du matériel isolé (clusters Kubernetes). Vous avez le contrôle complet de l'environnement, y compris le contrôle d'accès, la capacité, les mises à jour de version, l'utilisation et la surveillance des ressources.

Les commandes suivantes permettent de gérer les environnements, les organisations, les espaces, les utilisateurs et les rôles CFEE.
{: shortdesc}

<table summary="Gestion des services Cloud Foundry Enterprise Environment (expérimental)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 <td>[ibmcloud cfee create](cli_cfee.html#ibmcloud_cfee_create)</td>
 <td>[ibmcloud cfee create-locations](cli_cfee.html#ibmcloud_cfee_create_locations)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee create-permission-get](cli_cfee.html#ibmcloud_create_permission_get)</td>
 <td>[ibmcloud cfee create-permission-set](cli_cfee.html#ibmcloud_create_permission_set)</td>
 <td>[ibmcloud cfee create-status](cli_cfee.html#ibmcloud_create_status)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Répertorier les environnements CFEE.

```
ibmcloud cfee environments
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Afficher les détails d'un environnement CFEE

```
ibmcloud cfee environment NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>NAME (obligatoire)</dt>
   <dd>Nom de l'environnement à afficher.</dd>
   <dt>--id</dt>
   <dd>Afficher l'ID uniquement</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les détails d'un environnement CFEE `env_example` :

```
ibmcloud cfee environment env_example
```

Afficher l'ID d'un environnement CFEE `env_example` :

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Répertorier toutes les organisations

```
ibmcloud cfee orgs [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Répertorier toutes les organisations :

```
ibmcloud cfee orgs
```

Répertorier toutes les organisations de l'environnement CFEE `env_example` :

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Afficher les détails d'une organisation

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>--guid</dt>
   <dd>Afficher l'identificateur global unique de l'organisation uniquement. Toute autre sortie relative à l'organisation est supprimée.</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les détails d'une organisation CFEE `org_example` :

```
ibmcloud cfee org org_example
```

Afficher les détails d'une organisation CFEE `org_example` de l'environnement CFEE `env_example` :

```
ibmcloud cfee org org_example --env env_example
```

Afficher l'identificateur global unique d'une organisation CFEE `org_example` :

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Créer une organisation

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation à créer.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>Quota à affecter à l'organisation nouvellement créée (utilisez le quota par défaut si aucun n'est indiqué)</dd>
  </dl>

<strong>Exemples</strong> :

Créer une organisation CFEE `org_example` :

```
ibmcloud cfee org-create org_example
```

Créer une organisation CFEE `org_example` de l'environnement CFEE `env_example` :

```
ibmcloud cfee org-create org_example --env env_example
```

Créer une organisation CFEE `org_example` avec le quota `quote_example` :

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Supprimer une organisation

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation à supprimer.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>-f, --force</dt>
   <dd>Forcer la suppression sans confirmation</dd>
  </dl>

<strong>Exemples</strong> :

Supprimer une organisation CFEE `org_example` :

```
ibmcloud cfee org-delete org_example
```

Supprimer une organisation CFEE `org_example` de l'environnement CFEE `env_example` :

```
ibmcloud cfee org-delete org_example --env env_example
```

Supprimer une organisation CFEE `org_example` sans confirmation :

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Afficher les utilisateurs de l'organisation spécifiée par rôle

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>-a, --all</dt>
   <dd>Répertorier tous les utilisateurs de l'organisation indiquée</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les utilisateurs de l'organisation CFEE `org_example` :

```
ibmcloud cfee org-users org_example
```

Afficher les utilisateurs de l'organisation CFEE `org_example` se trouvant dans l'environnement CFEE `env_example` :

```
ibmcloud cfee org-users org_example --env env_example
```

Répertorier tous les utilisateurs de l'organisation CFEE `org_example` :

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Affecter un rôle d'organisation à un utilisateur (gestionnaire d'organisation requis)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur à affecter.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation auquel cet utilisateur est affecté. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Affecter le rôle `BillingManager` à l'utilisateur `test@exmaple.com` dans l'organisation `org_example` :

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

Affecter le rôle `BillingManager` à l'utilisateur `test@exmaple.com` dans l'organisation `org_example` de l'environnement CFEE `env_example` :

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Retirer un rôle d'organisation à un utilisateur (gestionnaire d'organisation ou utilisateur lui-même)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur à supprimer.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'organisation dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>OrgManager : ce rôle peut inviter et gérer des utilisateurs, sélectionner et changer de plan, et définir des plafonds de dépense.</li>
   <li>BillingManager : ce rôle peut créer et gérer le compte de facturation et les informations de paiement.</li>
   <li>OrgAuditor : ce rôle dispose d'un accès en lecture seule aux informations de l'organisation et aux rapports.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Retirer le rôle `BillingManager` de l'utilisateur `test@exmaple.com` dans l'organisation `org_example` :

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

Retirer le rôle `BillingManager` de l'utilisateur `test@exmaple.com` dans l'organisation `org_example` de l'environnement CFEE `env_example` :

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Répertorier tous les espaces

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Répertorier tous les espaces

```
ibmcloud cfee spaces
```

Répertorier tous les espaces de l'organisation `org_example` et de l'environnement CFEE `env_example`

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Afficher les informations de l'espace indiqué

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace à afficher.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>--guid</dt>
   <dd>Extraire et afficher l'identificateur global unique de l'espace donné. Toute autre sortie pour l'espace est supprimée.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--security-group-rules</dt>
   <dd>Extraire les règles pour tous les groupes de sécurité associés à l'espace</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les informations de l'espace `space_example` :

```
ibmcloud cfee space space_example
```

Extraire et afficher l'identificateur global unique de l'espace `space_example` :

```
ibmcloud cfee space space_example --guid
```

Afficher les règles de tous les groupes de sécurité associés à l'espace `space_example` :

```
ibmcloud cfee space space_example --security-group-rules
```

Afficher les informations de l'espace `space_example` de l'organisation `org_example` et de l'environnement CFEE `env_example` :

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Créer un espace

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace à créer.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
  </dl>

<strong>Exemples</strong> :

Créer un nouvel espace `space_example` :

```
ibmcloud cfee space-create space_example
```

Créer un nouvel espace `space_example` sous l'organisation `org_example` et l'environnement CFEE `env_example` :

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renommer un espace

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>OLD_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'espace à renommer.</dd>
   <dt>NEW_NAME (obligatoire)</dt>
   <dd>Nouveau nom à affecter à l'espace.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
  </dl>

<strong>Exemples</strong> :

Renommer l'espace `space_example` en `new_pace_example` :

```
ibmcloud cfee space-rename space_example new_pace_example
```

Renommer l'espace `space_example` en `new_pace_example` dans l'organisation `org_example` et l'environnement CFEE `env_example` :

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Supprimer un espace

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace à afficher.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
   <dt>-f, --force</dt>
   <dd>Force une suppression sans demander de confirmation.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
  </dl>

<strong>Exemples</strong> :

Supprimer l'espace `space_example` :

```
ibmcloud cfee space-delete space_example
```

Supprimer l'espace `space_example` dans l'organisation `org_example` et l'environnement CFEE `env_example` sans confirmation :

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Affecter un rôle d'espace à un utilisateur

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur à affecter.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace auquel affecter cet utilisateur.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace auquel affecter cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Affecter l'utilisateur `test@exmaple.com` à l'organisation `org_example` et à l'espace `space_example` en utilisant le rôle `SpaceManager` :

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Affecter l'utilisateur `test@exmaple.com` à l'organisation `org_example` et à l'espace `space_example` en utilisant le rôle `SpaceManager` sous l'environnement `env_example` :

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Supprimer un rôle d'espace pour un utilisateur

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>Adresse électronique de l'utilisateur à supprimer.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace dans lequel supprimer cet utilisateur.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions dans un espace spécifique.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Supprimer l'utilisateur `test@exmaple.com` dans l'organisation `org_example` et l'espace `space_example` en utilisant le rôle `SpaceManager` :

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Supprimer l'utilisateur `test@exmaple.com` dans l'organisation `org_example` et l'espace `space_example` en utilisant le rôle `SpaceManager` sous l'environnement `env_example` :

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Obtenir tous les rôles d'espace de l'utilisateur en cours pour une organisation spécifique

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Obtenir tous les rôles d'espace de l'utilisateur en cours dans l'organisation `org_example` :

```
ibmcloud cfee space-roles org_example
```

Obtenir tous les rôles d'espace de l'utilisateur en cours dans l'organisation `org_example` et l'environnement `env_example` :

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Afficher les utilisateurs dans l'espace spécifié par rôle

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace.</dd>
   <dt>--env ENV</dt>
   <dd>Nom de l'environnement CFEE. Par défaut, environnement CFEE en cours si aucun élément n'a été spécifié.</dd>
  </dl>

<strong>Exemples</strong> :

Afficher tous les utilisateurs de l'espace `space_example` et de l'organisation `org_example` :

```
ibmcloud cfee space-users org_example space_example
```

Afficher tous les utilisateurs de l'espace `space_example`, de l'organisation `org_example` et de l'environnement `env_example` :

```
ibmcloud cfee space-users org_example space_example --env env_example
```

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Créer une demande afin de créer une nouvelle instance de Cloud Foundry Enterprise Environment

```
ibmcloud cfee create NAME LOCATION [--cells CELLS] [--isolation ISOLATION] [--private-vlan ID, --public-vlan ID] [--plan ID]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
  <dl>
   <dt>NAME (obligatoire)</dt>
   <dd>Nom de l'instance.</dd>
   <dt>LOCATION (obligatoire)</dt>
   <dd>Emplacement où créer l'instance. </dd>
   <dt>--cells CELLS</dt>
   <dd>Spécifiez le nombre de cellules pour cette instance CFEE. La valeur par défaut est 2 et la valeur minimale est 1. Dans une instance CFEE comportant une cellule, la haute disponibilité n'est pas possible. </dd>
   <dt>--isolation ISOLATION</dt>
   <dd>Spécifiez l'isolement du cluster IBM kubernetes. Les options sont "dédié" et "partagé". L'option par défaut est "partagé" ; un cluster "dédié" implique des frais supplémentaires. </dd>
   <dt>--private-vlan ID</dt>
   <dd>Spécifiez l'ID de VLAN privé. Par défaut, nous trouverons un ensemble de VLAN disponible ou nous créerons une paire pour vous. </dd>
   <dt>--public-vlan ID</dt>
   <dd>Spécifiez l'ID de VLAN public. Par défaut, nous trouverons un ensemble de VLAN disponible ou nous créerons une paire pour vous. </dd>
   <dt>--plan ID</dt>
   <dd>Spécifiez l'ID de plan. Par défaut, nous mettrons à disposition un plan standard. </dd>
  </dl>

<strong>Exemples</strong> :

Créez une instance nommée `test-cfee` dans `dal10` :

```
ibmcloud cfee create test-cfee dal10
```

Créez une instance `dédiée` nommée `test-cfee` dans `dal10` avec `4` cellules :

```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Créez une demande afin d'obtenir une liste de centres de données disponibles pour les régions ciblées

```
ibmcloud cfee create-locations
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :


## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Permet de vérifier si un utilisateur dispose de tous les droits nécessaires pour créer une instance CFEE. La commande recherche les règles d'accès suivantes pour l'utilisateur cible : rôle Editeur sur les services CFEE, rôle Administrateur sur Kubernetes Service, rôle d'éditeur de plateforme et rôle d'accès aux services de gestionnaire sur le service Cloud Object Storage, et rôle de développeur sur l'espace en cours dans l'organisation en cours pour la mise à disposition de Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Nom du groupe d'accès dans lequel vérifier les droits. Le groupe d'accès par défaut est "cfee-provision-access-group".</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie pour les droits. Seul JSON est pris en charge pour l'instant.</dd>
  </dl>
  
<strong>Exemples</strong> :

Recherchez les droits de création d'instance CFEE pour l'utilisateur `name@example.com` :

```
ibmcloud cfee create-permission-get name@example.com
```

Recherchez les droits de création d'instance CFEE pour l'utilisateur `name@example.com` et dans le groupe d'accès `test-access-group` :

```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Permet d'accorder à l'utilisateur tous les droits nécessaires pour créer une instance CFEE. La commande crée les règles d'accès suivantes pour l'utilisateur cible : rôle Editeur sur les services CFEE, rôle Administrateur sur Kubernetes service, rôle d'éditeur de plateforme et rôle d'accès aux services de gestionnaire sur le service Cloud Object Storage, et rôle de développeur sur l'espace en cours dans l'organisation en cours pour la mise à disposition de Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Nom du groupe d'accès dans lequel accorder des droits. Le groupe d'accès par défaut est "cfee-provision-access-group".</dd>
  </dl>
  
<strong>Exemples</strong> :

Accorder à l'utilisateur `name@example.com` les droits de création d'une instance CFEE via le groupe d'accès par défaut :

```
ibmcloud cfee create-permission-set name@example.com
```

Accorder à l'utilisateur `name@example.com` les droits de création d'une instance CFEE via le groupe d'accès `test-access-group` :

```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Vérifier l'état de la mise à disposition d'une instance CFEE

```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>Nom ou ID (obligatoire)</dt>
   <dd>Nom ou ID de l'instance CFEE. </dd>
   <dt>--poll</dt>
   <dd>Indiquez si vous souhaitez que cet appel soit récurrent, afin d'effectuer des interrogations jusqu'à obtenir un état stable</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie pour l'état. Seul JSON est pris en charge pour l'instant.</dd>
  </dl>
