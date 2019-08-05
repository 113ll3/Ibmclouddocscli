---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# Gestion des comptes, des utilisateurs et des organisations Cloud Foundry
{: #ibmcloud_commands_account}

Les commandes suivantes permettent de gérer des comptes, les utilisateurs d'un compte, ainsi que l'organisation, l'espace et les rôles des environnements Cloud Foundry publics.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Répertorier toutes les organisations.
```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Nom de région. Permet de répertorier les organisations de la région indiquée. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée. Si la valeur 'all' est indiquée, les organisations de toutes les régions sont répertoriées.</dd>
   <dt>--guid</dt>
   <dd>Afficher l'identificateur global unique des organisations Cette option exclut `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut `--guid`.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>ID compte. Permet de répertorier les organisations du compte. Par défaut, il s'agit du compte actuel si aucune valeur n'est indiquée. Si la valeur `all` est indiquée, les organisations de tous les comptes sont répertoriées. Cette option exclut `-u`.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Nom du propriétaire du compte. Permet de répertorier les organisations des comptes appartenant à l'utilisateur. Par défaut, il s'agit du compte actuel si aucune valeur n'est indiquée. Si la valeur 'all' est indiquée, les organisations de tous les comptes sont répertoriées. Cette option exclut `-c`.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier toutes les organisations dans la région `us-south` en affichant leur identificateur global unique :
```
ibmcloud account orgs -r us-south --guid
```

Répertorier toutes les organisations au format JSON :
```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Afficher les informations de l'organisation spécifiée.
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>-r REGION</dt>
   <dd>Nom de région. Si aucun élément n'est défini, la région en cours est la valeur par défaut. Si la valeur `all` est indiquée, les organisations de toutes les régions avec le nom donné sont répertoriées.</dd>
   <dt>--guid</dt>
   <dd>Extrayez et affichez l'identificateur global unique de l'organisation. Toute autre sortie pour l'organisation est supprimée. Cette option exclut `--output`.</dd>
   <dt>--output REGION</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut `--guid`.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les informations de l'organisation `IBM` en indiquant son identificateur global unique (GUID)
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Créer une organisation. Cette opération peut uniquement être effectuée par le propriétaire de compte.
```
ibmcloud account org-create ORG_NAME [-r, --region REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation à créer.</dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
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
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation existante à répliquer.</dd>
   <dt>REGION_NAME (obligatoire)</dt>
   <dd>Nom de la région hébergeant l'organisation répliquée.</dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
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
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>OLD_ORG_NAME (obligatoire)</dt>
   <dd>Ancien nom de l'organisation qui sera renommée.</dd>
   <dt>NEW_ORG_NAME (obligatoire)</dt>
   <dd>Nouveau nom de l'organisation à renommer.</dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Répertorier tous les espaces de compte.
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>-o ORG_NAME (facultatif)</dt>
   <dd>Nom de l'organisation. Liste des espaces sous l'organisation spécifiée. L'organisation actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>-r REGION-NAME (facultatif)</dt>
   <dd>Nom de région. Liste des espaces sous la région spécifiée. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--output FORMAT (facultatif)</dt>
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

Afficher les informations d'un espace spécifique.
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
   <dd>Extrayez et affichez l'identificateur global unique de l'espace. Toute autre sortie pour l'espace est supprimée. Cette option exclut `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Toute autre sortie pour l'espace est supprimée. Cette option exclut `--guid`.</dd>
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

Cette commande a la même fonction et les mêmes options que la commande [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

Cette commande a la même fonction et les mêmes options que la commande [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

Cette commande a la même fonction et les mêmes options que la commande [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Affiche les utilisateurs dans l'organisation spécifiée, par rôle.

```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>ORG_NAME (obligatoire)</dt>
<dd>Nom de l'organisation.</dd>
<dt>-a, -all (facultatif)</dt>
<dd>Recense tous les utilisateurs de l'organisation spécifiés, sans les regrouper par rôle.</dd>
<dt>-r, --region REGION (facultatif)</dt>
<dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Ajouter un utilisateur à une organisation (un responsable d'organisation est requis).
```
 ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>ORG (obligatoire)</dt>
<dd>Nom de l'organisation.</dd>
<dt>-r, --region REGION (facultatif)</dt>
<dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Retirer un utilisateur d'une organisation (responsable d'organisation ou utilisateur uniquement)
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
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>-u</dt>
   <dd>ID utilisateur. S'il n'est pas spécifié, la valeur par défaut est l'utilisateur en cours.</dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Affecte un rôle de l'organisation à un utilisateur. Cette opération peut uniquement être effectuée par un responsable de l'organisation.
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
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
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
  </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` sous le rôle `OrgManager` :
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
Vous pouvez définir des rôles d'organisation et d'espace à l'aide de l'interface de ligne de commande, mais pour définir d'autres droits, vous devez utiliser l'interface utilisateur. Pour plus d'informations, voir [Managing access to resources](/docs/iam?topic=iam-iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Supprime l'affectation d'un rôle d'organisation à un utilisateur. Cette opération ne peut être réalisée que par un responsable de l'organisation.
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à retirer.</dd>
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
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
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
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace.</dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

Obtenir tous les rôles d'espace de l'utilisateur en cours pour une organisation spécifique

```
ibmcloud account space-roles ORG [-r, --region REGION] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>ORG (obligatoire)</dt>
   <dd>Nom de l'organisation.</dd>
   <dt>-r (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Affecte un rôle d'espace à un utilisateur. Cette opération peut uniquement être effectuée par un gestionnaire d'espace.
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
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
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
   </dl>

<strong>Exemples</strong> :

Affectez l'utilisatrice `Mary` à l'organisation `IBM` et à l'espace `Cloud` sous le rôle `SpaceManager` :
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Suppression de l'affectation d'un rôle d'espace à un utilisateur. Cette opération peut uniquement être effectuée par un gestionnaire d'espace.
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>USER_NAME (obligatoire)</dt>
   <dd>Nom de l'utilisateur à retirer.</dd>
   <dt>ORG_NAME (obligatoire)</dt>
   <dd>Nom de l'organisation dans laquelle supprimer cet utilisateur.</dd>
   <dt>SPACE_NAME (obligatoire)</dt>
   <dd>Nom de l'espace dans lequel supprimer cet utilisateur.</dd>
   <dt>SPACE_ROLE (obligatoire)</dt>
   <dd>Nom du rôle d'espace dans lequel supprimer cet utilisateur. Par exemple :
   <ul>
   <li>SpaceManager: ce rôle peut inviter et gérer des utilisateurs, et activer des fonctions.</li>
   <li>SpaceDeveloper : ce rôle peut créer et gérer des applications et des services, et consulter les journaux et les rapports.</li>
   <li>SpaceAuditor : ce rôle peut consulter les journaux, les rapports, et les paramètres de l'espace.</li>
   </ul></dd>
   <dt>-r, --region REGION (facultatif)</dt>
   <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
    </dl>


<strong>Exemples</strong> :

Retirer l'utilisatrice `Mary` de l'organisation `IBM` et de l'espace `Cloud` sous le rôle `SpaceManager` :
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Afficher la liste de tous les comptes de l'utilisateur en cours :
```
ibmcloud account list [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Afficher le compte de l'organisation spécifiée (utilisateur d'organisation requis)
```
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid | --output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-r (facultatif)</dt>
  <dd>Nom de région. La région actuelle constitue la valeur par défaut si aucune valeur n'est indiquée.</dd>
  <dt>--guid (facultatif)</dt>
  <dd>Affiche uniquement l'ID de compte</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Afficher les détails du compte.
```
ibmcloud account show
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Afficher les détails du compte actuellement ciblé :
```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

Mettre à jour un compte spécifique :
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Activer ou désactiver la connectivité des noeuds finaux de service pour un compte SoftLayer.</dd>
</dl>

<strong>Exemples</strong> :

Activer la connectivité de noeud final de service pour le compte actuel :
```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Répertorier les journaux d'audit de compte SoftLayer :
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>Action. Répertoriez les journaux d'audit contenant l'action.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>Date de fin. Répertoriez les journaux d'audit qui se situent avant la date de fin. Le format pris en charge est aaaa-MM-jjTHH:mm:ss.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>Objet. Répertoriez les journaux d'audit contenant l'objet.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>Type d'objet. Répertoriez les journaux d'audit contenant le type d'objet.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>Date de début. Répertoriez les journaux d'audit qui se situent après la date de début. Le format pris en charge est aaaa-MM-jjTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>Nom d'utilisateur. Répertoriez les journaux d'audit contenant le nom d'utilisateur.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les journaux d'audit :
```
ibmcloud account audit-logs
```

## ibmcloud account users
{: #ibmcloud_account_users}

Affiche les utilisateurs associés au compte. Cette opération peut uniquement être effectuée par le propriétaire du compte.
```
ibmcloud account users [-c, --account-id ACCOUNT_ID] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>-c (facultatif)</dt>
<dd>ID compte. Si ce paramètre n'est pas spécifié, le compte en cours est pris par défaut.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Retirer un utilisateur d'un compte (propriétaire de compte uniquement).
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

Inviter un utilisateur à rejoindre le compte :
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>USER_EMAIL (obligatoire)</dt>
   <dd>E-mail de l'utilisateur à inviter.</dd>
   <dt>-o ORG</dt>
   <dd>Organisation dans laquelle inviter l'utilisateur</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Rôle organisationnel. Entrées valides : OrgManager, BillingManager, OrgAuditor et OrgUser. Si aucun élément n'est indiqué, le rôle OrgUser est défini.</dd>
   <dt>-s SPACE</dt>
   <dd>Espace dans lequel inviter l'utilisateur</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Rôle d'espace. Les valeurs valides sont les suivantes : SpaceManager, SpaceDeveloper et SpaceAuditor.</dd>
</dl>

Si vous n'êtes pas prêt à affecter l'accès ou si vous souhaitez affecter une règle IAM plutôt qu'un accès Cloud Foundry, vous pouvez inviter un utilisateur sans accès et lui affecter un accès ultérieurement. Pour plus d'informations sur l'affectation d'accès aux utilisateurs, voir [Gestion de l'accès aux ressources](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
{: tip}

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
   <dd>E-mail de l'utilisateur à inviter à nouveau.</dd>
</dl>

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Répertorier les journaux d'audit du compte

```
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE] [--output FORMAT]
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--user-name <i>USER_NAME</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit contenant le nom d'utilisateur.</dd>
   <dt>--object-type <i>OBJECT_TYPE</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit contenant le type d'objet.</dd>
   <dt>--object <i>OBJECT</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit contenant l'objet.</dd>
   <dt>--action <i>ACTION</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit contenant l'action.</dd>
   <dt>--start-date <i>START_DATE</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit qui se situent après la date de début. Le format pris en charge est aaaa-MM-jjTHH:mm:ss.</dd>
   <dt>--end-date <i>END_DATE</i> (facultatif)</dt>
   <dd>Répertoriez les journaux d'audit qui se situent avant la date de fin. Le format pris en charge est aaaa-MM-jjTHH:mm:ss.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

Afficher les détails de préférence utilisateur

```
ibmcloud account user-preference [--output FORMAT]
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

Mettre à jour la préférence utilisateur

```
ibmcloud account user-preference-update (--position NEW_POSITION) [--output FORMAT]
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--position <i>NEW_POSITION</i> (facultatif)</dt>
   <dd>Définissez un poste pour l'utilisateur, tel que 'responsable' ou 'étudiant'.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

S'abonner aux notifications de la plateforme :
```
ibmcloud account platform-notification-subscribe (--type TYPE)
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--type <i>TYPE</i> (facultatif)</dt>
   <dd>Type de notification : 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

Se désabonner des notifications de la plateforme :
```
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>--type <i>TYPE</i> (facultatif)</dt>
   <dd>Type de notification : 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

Répertorier les informations de certificat d'un domaine :
```
ibmcloud account domain-cert DOMAIN_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>DOMAIN_NAME (obligatoire)</dt>
<dd>Domaine hébergeant le certificat.</dd>
</dl>


<strong>Exemples</strong> :

Affichage des informations de certificat du domaine `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert ibmcxo-eventconnect.com
```

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

Ajouter un certificat au domaine indiqué dans l'organisation en cours.
```
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine auquel ajouter le certificat.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de clé privée.</dd>
   <dt>-c <i>CERT_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de certificat.</dd>
   <dt>-p <i>PASSWORD</i> (facultatif)</dt>
   <dd>Mot de passe du certificat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (facultatif)</dt>
   <dd>Chemin du fichier de certificat intermédiaire.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (facultatif)</dt>
   <dd>Nom du fichier de clés certifiées.</dd>
   </dl>


<strong>Exemples</strong> :

Ajouter un certificat au domaine `ibmcxo-eventconnect.com` :
```
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

Supprimer un certificat du domaine spécifié dans l'organisation en cours.
```
ibmcloud account domain-cert-remove DOMAIN [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine duquel supprimer le certificat.</dd>
   <dt>-f (facultatif)</dt>
   <dd>Force une suppression sans demander de confirmation.</dd>
   </dl>
