---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-05"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Utilisation du service Cloud Foundry Enterprise Environment
{: #ibmcloud_commands_cfee}

{{site.data.keyword.cfee_full}} (CFEE) vous permet d'instancier à la demande plusieurs plateformes Cloud Foundry d'entreprise isolées. Les instances du service IBM Cloud Foundry Enterprise s'exécutent dans votre propre compte dans {{site.data.keyword.cloud_notm}}. L'environnement est déployé sur du matériel isolé (clusters Kubernetes). Vous avez le contrôle complet de l'environnement, y compris le contrôle d'accès, la capacité, les mises à jour de version, l'utilisation et la surveillance des ressources.

Les commandes suivantes permettent de gérer les rôles, les utilisateurs, les espaces, les organisations et les environnements CFEE.
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Répertorier les environnements CFEE :
```
ibmcloud cfee environments
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Afficher les détails d'un environnement CFEE :
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
{: codeblock}

Afficher l'ID d'un environnement CFEE `env_example` :
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Répertorier toutes les organisations :
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
{: codeblock}

Répertorier toutes les organisations de l'environnement CFEE `env_example` :
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Afficher les détails d'une organisation :
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
{: codeblock}

Afficher les détails d'une organisation CFEE `org_example` de l'environnement CFEE `env_example` :
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

Afficher l'identificateur global unique d'une organisation CFEE `org_example` :
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Créer une organisation :
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
{: codeblock}

Créer une organisation CFEE `org_example` de l'environnement CFEE `env_example` :
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

Créer une organisation CFEE `org_example` avec le quota `quote_example` :
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Supprimer une organisation :
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
{: codeblock}

Supprimer une organisation CFEE `org_example` de l'environnement CFEE `env_example` :
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

Supprimer une organisation CFEE `org_example` sans confirmation :
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Afficher par rôle les utilisateurs de l'organisation spécifiée :
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
{: codeblock}

Afficher les utilisateurs de l'organisation CFEE `org_example` se trouvant dans l'environnement CFEE `env_example` :
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

Répertorier tous les utilisateurs de l'organisation CFEE `org_example` :
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

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
   <dd>E-mail de l'utilisateur à affecter.</dd>
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
{: codeblock}

Affecter le rôle `BillingManager` à l'utilisateur `test@exmaple.com` dans l'organisation `org_example` de l'environnement CFEE `env_example` :
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Retirer un rôle d'organisation pour un utilisateur (responsable d'organisation ou utilisateur uniquement) :
```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>E-mail de l'utilisateur à retirer.</dd>
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
{: codeblock}

Retirer le rôle `BillingManager` de l'utilisateur `test@exmaple.com` dans l'organisation `org_example` de l'environnement CFEE `env_example` :
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Répertorier tous les espaces :
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

Répertorier tous les espaces :
```
ibmcloud cfee spaces
```
{: codeblock}

Répertorier tous les espaces de l'organisation `org_example` et de l'environnement CFEE `env_example`
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

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
   <dd>Extrayez et affichez l'identificateur global unique de l'espace. Toute autre sortie pour l'espace est supprimée.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nom de l'organisation. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--security-group-rules</dt>
   <dd>Extraire les règles pour tous les groupes de sécurité associés à l'espace</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les détails d'un espace nommé `space_example`:
```
ibmcloud cfee space space_example
```
{: codeblock}

Extraire et afficher l'identificateur global unique de l'espace `space_example` :
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

Afficher les règles de tous les groupes de sécurité associés à l'espace `space_example` :
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

Afficher les détails de l'espace `space_example`, de l'organisation `org_example` et de l'environnement CFEE `env_example`:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Créer un espace :
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

Créer un espace nommé `space_example` :
```
ibmcloud cfee space-create space_example
```
{: codeblock}

Créer un espace nommé `space_example`, sous l'organisation `org_example` et dans l'environnement CFEE `env_example` :
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renommer un espace :
```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>OLD_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'espace à renommer.</dd>
   <dt>NEW_NAME (obligatoire)</dt>
   <dd>Nouveau nom de l'espace à renommer.</dd>
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
{: codeblock}

Renommer l'espace `space_example` en `new_pace_example` dans l'organisation `org_example` et l'environnement CFEE `env_example` :
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Supprimer un espace :
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
{: codeblock}

Supprimer l'espace `space_example` dans l'organisation `org_example` et l'environnement CFEE `env_example` sans confirmation :
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

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
   <dd>E-mail de l'utilisateur à affecter.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation à laquelle l'utilisateur est affecté.</dd>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace auquel affecter cet utilisateur.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace auquel affecter cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager : ce rôle peut inviter et gérer des utilisateurs et activer des fonctions dans un espace.</li>
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
{: codeblock}

Affecter l'utilisateur `test@exmaple.com` à l'organisation `org_example` et à l'espace `space_example` en utilisant le rôle `SpaceManager` sous l'environnement `env_example` :
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
   <dd>E-mail de l'utilisateur à retirer.</dd>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>SPACE (obligatoire)</dt>
   <dd>Nom de l'espace dans lequel supprimer cet utilisateur.</dd>
   <dt>ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager : ce rôle peut inviter et gérer des utilisateurs et activer des fonctions dans un espace.</li>
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
{: codeblock}

Supprimer l'utilisateur `test@exmaple.com` dans l'organisation `org_example` et l'espace `space_example` en utilisant le rôle `SpaceManager` sous l'environnement `env_example` :
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

Obtenir tous les rôles d'espace de l'utilisateur en cours dans l'organisation `org_example` et l'environnement `env_example` :
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Afficher tous les utilisateurs de l'espace `space_example`, de l'organisation `org_example` et de l'environnement `env_example` :
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Effectuer une demande de création d'une instance de Cloud Foundry Enterprise Environment :
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-n, --name NAME (obligatoire)</dt>
  <dd>Spécifier le nom de l'environnement CFEE. Il doit comporter 24 caractères au maximum, commencer par une lettre et contenir uniquement des caractères alphanumériques, `-`, `_` et `.`.</dd>
  <dt>--location LOCATION (obligatoire)</dt>
  <dd>Spécifiez le centre de données pour la mise à disposition de cet environnement CFEE (dal10, par exemple). Pour trouver les centres de données disponibles, exécutez la commande `ibmcloud cfee create-locations`.</dd>
  <dt>--cells CELLS</dt>
  <dd>Spécifiez le nombre de cellules pour cette instance CFEE. La valeur par défaut est 2 et la valeur minimale est 1. Dans une cellule CFEE, il ne peut pas y avoir de haute disponibilité.</dd>
  <dt>--private-access</dt>
  <dd>Spécifiez le type d'accès réseau de la base de données PostgreSQL mise à disposition dans le cadre de CFEE. Ne définissez l'indicateur que si le compte est VRF et le noeud final de service activé. Si cet indicateur est défini, le noeud final d'accès privé est utilisé.</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>Avec un matériel dédié, vos noeuds worker sont hébergés sur l'infrastructure réservée à votre compte. Avec un matériel partagé, les ressources d'infrastructure, telles que l'hyperviseur et le matériel physique, sont partagés avec d'autres clients IBM mais chaque noeud worker est un noeud à service exclusif qui vous est propre. `Partagé` est la valeur par défaut si l'indicateur n'est PAS défini. L'utilisation d'un noeud worker `dédié` entraîne des coûts supplémentaires.</dd>
  <dt>--private-vlan ID</dt>
  <dd>Spécifiez l'ID de VLAN privé. Par défaut, un ensemble disponible de réseaux VLAN est utilisé ou une paire est créée pour vous.</dd>
  <dt>--public-vlan ID</dt>
  <dd>Spécifiez l'ID de VLAN public. Par défaut, un ensemble disponible de réseaux VLAN est utilisé ou une paire est créée pour vous.</dd>
  <dt>--plan ID</dt>
  <dd>Spécifiez l'ID de plan. Par défaut, un plan Standard est utilisé.</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques à l'API, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir le site accessible via https://cloud.ibm.com/apidocs/cfaas#provision-new-cfee-environment, pour l'entrée  de catalogue particulière. Cette opération est nécessaire pour la mise à disposition des environnements CFEE à zones multiples. Remarque : tous les autres indicateurs sont ignorés et les zones resource_group_id, access_token et refresh_token sont gérées par la commande de l'interface de ligne de commande.</dd>
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
ibmcloud cfee create-locations [--output FORMAT]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Permet de vérifier si un utilisateur dispose de tous les droits nécessaires pour créer une instance CFEE. La commande vérifie les règles d'accès suivantes pour l'utilisateur cible : éditeur sur les services CFEE, rôle d'administrateur sur le service Kubernetes, rôle d'éditeur de plateforme et gestionnaire pour le rôle d'accès au service Cloud Object Storage, et rôle de développeur sur l'espace en cours de l'organisation en cours pour la mise à disposition de Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Nom du groupe d'accès dans lequel vérifier les droits. Le groupe d'accès par défaut est `cfee-provision-access-group`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie pour les droits. Seul JSON est pris en charge pour l'instant.</dd>
  </dl>
  
<strong>Exemples</strong> :

Recherchez les droits de création d'instance CFEE pour l'utilisateur `name@example.com` :
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

Recherchez les droits de création d'instance CFEE pour l'utilisateur `name@example.com` et dans le groupe d'accès `test-access-group` :
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Permet d'accorder à l'utilisateur tous les droits nécessaires pour créer une instance CFEE. La commande crée les règles d'accès suivantes pour l'utilisateur cible : rôle d'éditeur sur le service CFEE, rôle d'administrateur pour le service Kubernetes, rôle d'éditeur de plateforme et de gestionnaire pour le rôle d'accès au service Cloud Object Storage, et rôle de développeur pour l'espace en cours de l'organisation en cours pour la mise à disposition de Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
  <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Nom du groupe d'accès dans lequel accorder des droits. Le groupe d'accès par défaut est `cfee-provision-access-group`.</dd>
  </dl>
  
<strong>Exemples</strong> :

Accorder à l'utilisateur `name@example.com` les droits de création d'une instance CFEE via le groupe d'accès par défaut :
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

Accorder à l'utilisateur `name@example.com` les droits de création d'une instance CFEE via le groupe d'accès `test-access-group` :
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Vérifier l'état de la mise à disposition d'une instance CFEE :
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>Nom ou ID (obligatoire)</dt>
   <dd>Nom ou ID de l'instance CFEE.</dd>
   <dt>--poll</dt>
   <dd>Spécifiez si vous souhaitez rendre cet appel récurrent, afin d'effectuer des interrogations jusqu'à obtenir un état stable.</dd>
   <dt>--output FORMAT</dt>
   <dd>Spécifiez un format de sortie pour le statut. Seul JSON est pris en charge pour l'instant.</dd>
  </dl>

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

Activer la surveillance sur l'environnement CFEE ciblé :
```
ibmcloud cfee monitoring-enable
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

Désactiver la surveillance sur l'environnement CFEE ciblé :
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

Vérifiez le statut de l'opération d'activation/désactivation de surveillance la plus récente dans l'environnement CFEE ciblé :
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>--poll</dt>
   <dd>Indiquez si vous souhaitez que cet appel soit récurrent, afin d'effectuer des interrogations jusqu'à obtenir un état stable</dd>
  </dl>
