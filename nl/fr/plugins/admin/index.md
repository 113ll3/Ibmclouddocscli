---

copyright:
  years: 2015, 2019
lastupdated: "2019-07-12"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# Interface de ligne de commande pour l'administration de {{site.data.keyword.cloud_notm}}
{: #ibmcloud-admincli}

Vous pouvez gérer votre environnement {{site.data.keyword.cloud_notm}} local ou {{site.data.keyword.cloud_notm}} dédié en utilisant l'interface de ligne de commande Cloud Foundry avec le plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}}. Par exemple, vous pouvez ajouter des utilisateurs depuis un registre LDAP.

Avant de commencer, installez l'interface de ligne de commande de Cloud Foundry. Le plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}} requiert `cf` 6.11.2 ou version ultérieure. [Téléchargez l'interface de ligne de commande Cloud Foundry](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

L'interface de ligne de commande Cloud Foundry n'est pas prise en charge par Cygwin. Utilisez l'interface de ligne de commande Cloud Foundry dans une fenêtre de ligne de commande autre que la fenêtre de ligne de commande Cygwin.

L'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}} est utilisée uniquement pour l'environnement {{site.data.keyword.cloud_notm}} local et l'environnement {{site.data.keyword.cloud_notm}} dédié. Elle n'est pas prise en charge par l'environnement {{site.data.keyword.cloud_notm}} public.
{: note}

## Ajout du plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}}
{: #add-admin-cli}

Une fois que vous avez installé l'interface de ligne de commande Cloud Foundry, vous pouvez ajouter le plug-in d'interface de ligne de commande d'administration
{{site.data.keyword.cloud_notm}}.

Si vous avez déjà installé le plug-in d'administration {{site.data.keyword.cloud_notm}}, il peut être nécessaire de le désinstaller, de supprimer le référentiel puis de réinstaller le plug-in pour obtenir les dernières mises à jour.
{: tip}

Procédez comme suit pour ajouter le référentiel et installer le plug-in :

1. Pour ajouter le plug-in d'administration {{site.data.keyword.cloud_notm}}, exécutez la commande suivante :
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  Vous trouverez la même commande avec le noeud final réel sur la page de l'interface de ligne de commande de la console d'administration, `https://<customer_console_endpoint>.bluemix.net/cli`.
  {: note}

2. Pour installer le plug-in de l'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}}, exécutez la commande suivante :
  ```
  cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
```
  {: codeblock}

## Désinstallation du plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}}
{: #remove-admin-cli}

Procédez comme suit pour désinstaller le plug-in : 

1. Désinstaller le plug-in :
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. Retirer le référentiel de plug-in :
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

Vous pouvez ensuite ajouter le référentiel mis à jour et installer la dernière version du plug-in.

## Utilisation du plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}}
{: #using-admin-cli}

Vous pouvez utiliser le plug-in d'interface de ligne de commande d'administration {{site.data.keyword.cloud_notm}} pour ajouter ou retirer des utilisateurs, affecter des utilisateurs à des organisations ou annuler leur affectation, et effectuer d'autres tâches de gestion.

Pour afficher la liste des commandes, exécutez la commande suivante :
```
cf plugins
```
{: codeblock}

Pour obtenir de l'aide supplémentaire sur une commande, utilisez l'option `-help`.

### Connexion à {{site.data.keyword.cloud_notm}} et ouverture de session
{: #connecting-ibm-cloud}

1. Pour vous connecter au noeud final d'API {{site.data.keyword.cloud_notm}}, exécutez la commande suivante :
  ```
  cf api api.us-south.cf.cloud.ibm.com
  ```
  {: codeblock}
  
  Même si les noeuds finaux de l'API Cloud Foundry `api.*.bluemix.net` existants sont toujours disponibles, vous pouvez mettre à jour les scripts et l'automatisation d'infrastructure afin d'utiliser les noeuds finaux d'API Cloud Foundry mis à jour suivants pour votre région :

  * api.us-south.cf.cloud.ibm.com (auparavant api.ng.bluemix.net)
  * api.eu-gb.cf.cloud.ibm.com (auparavant api.eu-gb.bluemix.net)
  * api.us-east.cf.cloud.ibm.com (auparavant api.us-east.bluemix.net)
  * api.eu-de.cf.cloud.ibm.com (auparavant api.eu-de.bluemix.net)
  * api.au-syd.cf.cloud.ibm.com (auparavant api.au-syd.bluemix.net)

  Vous trouverez l'adresse URL correcte dans la page des informations et des ressources de la console d'administration. L'adresse URL est affichée dans la section Informations sur l'API, dans la zone **URL de l'API**.

2. Connectez-vous à {{site.data.keyword.cloud_notm}} en exécutant la commande suivante :
  ```
  cf login
  ```
  {: codeblock}

## Administration des utilisateurs
{: #admin_users}

### Ajout d'un utilisateur
{: #admin_add_user}

Pour ajouter un utilisateur à votre environnement {{site.data.keyword.cloud_notm}} à partir du registre d'utilisateurs de votre environnement, utilisez la commande suivante :
```
cf ba add-user user_name organization first_name last_name
```
{: codeblock}

Pour ajouter un utilisateur à une organisation spécifique, vous devez être administrateur et disposer du droit users.write (ou Superuser). Si vous êtes responsable de l'organisation, un superutilisateur qui exécute la commande **`enable-managers-add-users`** peut également vous accorder la capacité d'ajouter des utilisateurs à votre organisation. Pour plus d'informations, voir [Permettre aux responsables d'ajouter des utilisateurs](#clius_emau).

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur dans le registre LDAP.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}} à laquelle ajouter l'utilisateur.</dd>
<dt>first_name</dt>
<dd>Prénom de l'utilisateur à ajouter à l'organisation.</dd>
<dt>last_name</dt>
<dd>Nom de l'utilisateur à ajouter à l'organisation.</dd>
</dl>

Vous pouvez aussi utiliser **`ba au`** comme alias pour le nom de commande plus long **`ba add-user`**.
{: tip}

### Invitation d'un utilisateur depuis {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_invite_public}

Chaque environnement {{site.data.keyword.Bluemix_dedicated_notm}} dispose d'un compte d'entreprise, public et appartenant au client, dans {{site.data.keyword.cloud_notm}}. Pour que les utilisateurs de l'environnement dédié puissent créer des clusters dans{{site.data.keyword.containershort}}, l'administrateur doit ajouter ces utilisateurs à ce compte public d'entreprise. Quand les utilisateurs sont ajoutés au compte public d'entreprise, leurs comptes publics et dédiés sont liés entre eux. L'utilisateur peut se servir de son IBMid pour se connecter simultanément au compte public et au compte dédié et peut créer des ressources dans le compte public depuis l'interface dédiée. Pour plus d'informations, voir la rubrique relative à la [configuration d'IBM Cloud Container Service en environnement dédié](/docs/containers?topic=containers-dedicated#dedicated_setup). Pour inviter des utilisateurs dédiés dans le compte public :
```
cf ba invite-users-to-public -userid=user_email -organization=dedicated_org_id -apikey=public_api_key -public_org_id=public_org_id
```
{: pre}

Pour ajouter des utilisateurs d'environnement dédié à votre compte public {{site.data.keyword.cloud_notm}}, vous devez être administrateur du compte dédié.

<dl>
<dt>user_email</dt>
<dd>Si vous invitez un utilisateur unique, cette entrée contient l'e-mail de cet utilisateur.</dd>
<dt>dedicated_org_id</dt>
<dd>Si vous invitez tous les utilisateurs qui se trouvent actuellement dans une organisation de compte dédié, cette entrée contient l'ID de cette organisation.</dd>
<dt>public_api_key</dt>
<dd>Clé d'API pour inviter des utilisateurs dans le compte public. Doit être générée par l'administrateur du compte public.</dd>
<dt>public_org_id</dt>
<dd>ID de l'organisation de compte public dans laquelle vous invitez des utilisateurs.</dd>
</dl>

### Etablissement de la liste des utilisateurs invités depuis {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_list}

Si vous invitez des utilisateurs d'un environnement dédié dans votre compte {{site.data.keyword.cloud_notm}} avec la [commande **`invite-users-to-public`**](#admin_dedicated_invite_public), vous pouvez répertorier les utilisateurs de votre compte pour voir leur statut d'invitation. Les utilisateurs invités avec un IBMid existant ont un statut ACTIF. Les utilisateurs invités ne disposant pas d'un IBMid existant ont un statut EN ATTENTE ou ACTIF, selon que l'invitation ait été déjà acceptée ou non. Pour répertorier les utilisateurs de votre compte {{site.data.keyword.cloud_notm}} :

```
cf ba invite-users-status -apikey=public_api_key
```
{: pre}

Pour ajouter des utilisateurs d'environnement dédié à votre compte public {{site.data.keyword.cloud_notm}}, vous devez être administrateur du compte dédié.

<dl>
<dt>public_api_key</dt>
<dd>Clé d'API qui a été utilisée pour inviter les utilisateurs dans le compte. Doit être générée par l'administrateur du compte public.</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### Recherche d'un utilisateur
{: #admin_search_user}

Pour rechercher un utilisateur, entrez la commande suivante avec les paramètres de filtre de recherche facultatifs (name, permission, organization et role) :

```
cf ba search-users -name=user_name -permission=permission_value -organization=organization_value -role=role_value
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>permission_value</dt>
<dd>Droit accordé à l'utilisateur. Les droits d'accès disponibles sont : admin (ou superuser), log in (ou basic), catalog.read, catalog.write, reports.read, reports.write, users.read ou users.write. Vous ne pouvez pas utiliser ce paramètre avec le paramètre organization dans la même requête.</dd>
<dt>organization_value</dt>
<dd>Nom de l'organisation à laquelle appartient l'utilisateur. Vous ne pouvez pas utiliser ce paramètre avec le paramètre permission dans la même requête.</dd>
<dt>role_value</dt>
<dd>Rôle de l'organisation affecté à l'utilisateur. Les rôles disponibles sont auditors, managers et billing_managers. Vous devez spécifier l'organisation avec ce paramètre.</dd>
</dl>

Vous pouvez aussi utiliser **`ba su`** comme alias pour le nom de commande plus long **`ba search-users`**.
{: tip}

### Définition des droits d'un utilisateur
{: #admin_setperm_user}

Vous ne pouvez définir qu'un droit à la fois. Pour définir les droits d'un utilisateur indiqué, entrez la commande suivante :
```
cf ba set-permissions user_name permission access
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>permission</dt>
<dd>Permet de définir les droits qui sont affectés à l'utilisateur. Les droits d'accès disponibles sont : admin (ou superuser), log in (ou basic), catalog.read, catalog.write, reports.read, reports.write, users.read ou users.write. Vous ne pouvez pas utiliser ce paramètre avec le paramètre organization dans la même requête.</dd>
<dt>access</dt>
<dd>Pour les droits catalog, reports ou user, vous devez aussi définir le niveau d'accès `read` ou `write`.</dd>
</dl>

Vous pouvez aussi utiliser **`ba sp`** comme alias pour le nom de commande plus long **`ba set-permissions`**.
{: tip}

<!-- staging-only commands end -->

### Retrait d'un utilisateur
{: #admin_remov_user}

Pour retirer un utilisateur de votre environnement {{site.data.keyword.cloud_notm}}, utilisez la commande suivante :

```
cf ba remove-user user_name
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur dans {{site.data.keyword.cloud_notm}}.</dd>
</dl>

Vous pouvez aussi utiliser **`ba ru`** comme alias pour le nom de commande plus long **`ba remove-user`**.
{: tip}

### Procédure visant à permettre aux responsables d'ajouter des utilisateurs
{: #clius_emau}

Si vous disposez du droit Superuser dans votre environnement {{site.data.keyword.cloud_notm}}, vous pouvez permettre aux responsables de l'organisation d'ajouter des utilisateurs aux organisations qu'ils gèrent. Pour permettre aux responsables d'ajouter des utilisateurs, entrez la commande suivante :

```
cf ba enable-managers-add-users
```
{: codeblock}

Vous pouvez aussi utiliser **`ba emau`** comme alias pour le nom de commande plus long **`ba enable-managers-add-users`**.
{: tip}

### Procédure visant à empêcher les responsables d'ajouter des utilisateurs
{: #clius_dmau}

Pour empêcher les responsables d'ajouter des utilisateurs, utilisez la commande suivante :

```
cf ba disable-managers-add-users
```
{: codeblock}

Vous pouvez aussi utiliser **`ba dmau`** comme alias pour le nom de commande plus long **`ba disable-managers-add-users`**.
{: tip}

## Administration des organisations
{: #admin_orgs}

### Ajout d'une organisation
{: #admin_add_org}

Pour ajouter une organisation, utilisez la commande suivante :

```
cf ba create-org organization manager
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}} à ajouter.</dd>
<dt>manager</dt>
<dd>Nom d'utilisateur du responsable de l'organisation.</dd>
</dl>

Vous pouvez aussi utiliser **`ba co`** comme alias pour le nom de commande plus long **`ba create-org`**.
{: tip}

### Suppression d'une organisation
{: #admin_delete_org}

Pour supprimer une organisation, utilisez la commande suivante :

```
cf ba delete-org organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}}
à supprimer.</dd>
</dl>

Vous pouvez aussi utiliser **`ba do`** comme alias pour le nom de commande plus long **`ba delete-org`**.
{: tip}

### Affectation d'un utilisateur à une organisation
{: #admin_ass_user_org}

Pour affecter un utilisateur de votre environnement {{site.data.keyword.cloud_notm}} à une organisation particulière, utilisez la commande suivante :

```
cf ba set-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}} à laquelle affecter l'utilisateur.</dd>
<dt>role</dt>
<dd>Rôle de l'utilisateur. Les valeurs valides sont OrgManager, BillingManager, OrgAuditor. Voir [Rôles](/docs/iam?topic=iam-userroles#userroles) pour obtenir des descriptions de rôle.</dd>
</dl>

Vous pouvez aussi utiliser **`ba so`** comme alias pour le nom de commande plus long **`ba set-org`**.
{: tip}

### Annulation de l'affectation d'un utilisateur à une organisation
{: #admin_unass_user_org}

Pour annuler l'affectation d'un utilisateur de votre environnement {{site.data.keyword.cloud_notm}} à une organisation particulière, entrez la commande suivante :

```
cf ba unset-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}}.</dd>
<dt>role</dt>
<dd>Rôle de l'utilisateur. Les valeurs valides sont OrgManager, BillingManager, OrgAuditor. Voir [Rôles](/docs/iam?topic=iam-userroles#userroles) pour obtenir des descriptions de rôle.</dd>
</dl>

Vous pouvez aussi utiliser **`ba uo`** comme alias pour le nom de commande plus long **`ba unset-org`**.
{: tip}

### Définition d'un quota pour une organisation
{: #admin_set_org_quota}

Pour définir le quota d'utilisation d'une organisation donnée, entrez la commande suivante :

```
cf ba set-quota organization plan
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}}
pour laquelle définir le quota.</dd>
<dt>plan</dt>
<dd>Plan d'établissement des quotas pour une organisation.</dd>
</dl>

Vous pouvez aussi utiliser **`ba sq`** comme alias pour le nom de commande plus long **`ba set-quota`**.
{: tip}


### Recherche des quotas de conteneur d'une organisation
{: #admin_find_containquotas}

Pour rechercher le quota de conteneur d'une organisation, utilisez la commande suivante :

```
cf ibmcloud-admin containers-quota organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou ID de l'organisation dans IBM Cloud. Ce paramètre est obligatoire.</dd>
</dl>

Vous pouvez aussi utiliser **`ba cq`** comme alias pour le nom de commande plus long **`ibmcloud-admin containers-quota`**.
{: tip}

### Définition des quotas de conteneur pour une organisation
{: #admin_set_containquotas}

Pour définir le quota de conteneur d'une organisation, utilisez la commande suivante avec au moins une des options :

```
cf ibmcloud-admin set-containers-quota organization options
```
{: codeblock}

Vous pouvez inclure plusieurs options, mais vous devez en indiquer au moins une.
{: note}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation {{site.data.keyword.cloud_notm}} pour laquelle définir le quota.</dd>
<dt>options</dt>
<dd>Choix possibles : floating-ips-max value (nom abrégé fim), memory-max value (nom abrégé mm), memory-space-default value (nom abrégé msd) et image-limit value (nom abrégé il). La valeur doit être un entier.</dd>
</dl>

Vous pouvez, si vous le souhaitez, fournir un fichier contenant des paramètres de configuration spécifiques dans un objet JSON valide. Si vous utilisez l'option **`-file`**, elle prévaut sur les autres options qui sont ignorées. Pour indiquer un fichier au lieu des options, entrez la commande suivante :

```
cf ibmcloud-admin set-containers-quota organization -file path_to_JSON_file
```
{: codeblock}

Le fichier JSON doit être au format indiqué dans l'exemple suivant :

```
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: codeblock}

Vous pouvez aussi utiliser **`ba scq`** comme alias pour le nom de commande plus long **`ibmcloud-admin set-containers-quota`**.
{: tip}

## Administration d'espaces
{: #admin_spaces}

### Ajout d'un espace à l'organisation

Pour ajouter un espace à l'organisation, utilisez la commande suivante :

```
cf ibmcloud-admin create-space organization space_name
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation à laquelle ajouter l'espace.</dd>
<dt>space_name</dt>
<dd>Nom de l'espace que vous ajoutez à l'organisation.</dd>
</dl>

Vous pouvez aussi utiliser **`ba cs`** comme alias pour le nom de commande plus long **`ba create-space`**.
{: tip}

### Suppression d'un espace dans l'organisation

Pour retirer un espace de l'organisation, utilisez la commande suivante :

```
cf ibmcloud-admin delete-space organization space_name
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique (GUID) de l'organisation dont l'espace doit être retiré.</dd>
<dt>space_name</dt>
<dd>Nom de l'espace que vous retirez de l'organisation.</dd>
</dl>

Vous pouvez aussi utiliser **`ba cs`** comme alias pour le nom de commande plus long **`ba delete-space`**.
{: tip}

### Ajout d'un utilisateur à un espace avec un rôle

Pour créer un utilisateur dans un espace en le dotant d'un rôle spécifié, utilisez le commande suivante :

```
cf ibmcloud-admin set-space organization space_name user_name role
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique (GUID) de l'organisation à laquelle l'utilisateur est ajouté.</dd>
<dt>space_name</dt>
<dd>Nom de l'espace auquel l'utilisateur est ajouté.</dd>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>role</dt>
<dd>Rôle de l'utilisateur. Les valeurs valides sont Manager (responsable), Developer (développeur) et Auditor (auditeur).</dd>
</dl>

Vous pouvez aussi utiliser **`ba ss`** comme alias pour le nom de commande plus long **`ba set-space`**.
{: tip}


### Retrait du rôle d'un utilisateur dans un espace

Pour retirer le rôle d'un utilisateur dans un espace, utilisez la commande suivante :

```
cf ibmcloud-admin unset-space organization space_name user_name role
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Nom ou identificateur global unique (GUID) de l'organisation à laquelle l'utilisateur appartient.</dd>
<dt>space_name</dt>
<dd>Nom de l'espace auquel l'utilisateur appartient.</dd>
<dt>user_name</dt>
<dd>Nom de l'utilisateur.</dd>
<dt>role</dt>
<dd>Rôle de l'utilisateur. Les valeurs valides sont Manager (responsable), Developer (développeur) et Auditor (auditeur).</dd>
</dl>

Vous pouvez aussi utiliser **`ba us`** comme alias pour le nom de commande plus long **`ba unset-space`**.
{: tip}

## Administration du catalogue
{: #admin_catalog}

### Activation des services pour toutes les organisations
{: #admin_ena_service_org}

Pour activer l'affichage d'un service dans le catalogue {{site.data.keyword.cloud_notm}} pour toutes les organisations, entrez la commande suivante :

```
cf ba enable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Nom ou identificateur global unique (GUID) du plan de service à activer. Si vous entrez un nom de plan de service qui n'est pas unique, par exemple, "Standard" ou "Basic", vous êtes invité à sélectionner un plan de service. Pour identifier un nom de plan de service, sélectionnez la catégorie du service dans la page d'accueil, puis <b>Ajouter</b> pour afficher les services de cette catégorie. Cliquez sur le nom du service pour ouvrir la vue détaillée, depuis laquelle vous pourrez examiner les noms des plans de service disponibles pour ce service. </dd>
</dl>

Vous pouvez aussi utiliser **`ba esp`** comme alias pour le nom de commande plus long **`ba enable-service-plan`**.
{: tip}

### Désactivation des services pour toutes les organisations
{: #admin_dis_service_org}

Pour désactiver l'affichage d'un service dans le catalogue {{site.data.keyword.cloud_notm}} pour toutes les organisations, utilisez la commande suivante :

```
cf ba disable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Nom ou identificateur global unique (GUID) du plan de service à activer. Si vous entrez un nom de plan de service qui n'est pas unique, par exemple, "Standard" ou "Basic", vous êtes invité à sélectionner un plan de service. Pour identifier un nom de plan de service, sélectionnez la catégorie du service dans la page d'accueil, puis <b>Ajouter</b> pour afficher les services de cette catégorie. Cliquez sur le nom du service pour ouvrir la vue détaillée, depuis laquelle vous pourrez examiner les noms des plans de service disponibles pour ce service.</dd>
</dl>

Vous pouvez aussi utiliser **`ba dsp`** comme alias pour le nom de commande plus long **`ba disable-service-plan`**.
{: tip}

### Ajout de la visibilité d'un service pour les organisations
{: #admin_addvis_service_org}

Vous pouvez ajouter une organisation dans la liste des organisations pouvant voir un service spécifique dans le catalogue {{site.data.keyword.cloud_notm}}. Pour permettre à une organisation de voir un service spécifique dans le catalogue, entrez la commande suivante :

```
cf ba add-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Nom ou identificateur global unique (GUID) du plan de service à activer. Si vous entrez un nom de plan de service qui n'est pas unique, par exemple, "Standard" ou "Basic", vous êtes invité à sélectionner un plan de service. Pour identifier un nom de plan de service, sélectionnez la catégorie du service dans la page d'accueil, puis <b>Ajouter</b> pour afficher les services de cette catégorie. Cliquez sur le nom du service pour ouvrir la vue détaillée, depuis laquelle vous pourrez examiner les noms des plans de service disponibles pour ce service.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation à ajouter à la liste de visibilité du service.</dd>
</dl>

Vous pouvez aussi utiliser **`ba aspv`** comme alias pour le nom de commande plus long **`ba add-service-plan-visibility`**.
{: tip}

### Suppression de la visibilité d'un service pour les organisations
{: #admin_remvis_service_org}

Vous pouvez retirer une organisation de la liste des organisations pouvant voir un service spécifique dans le catalogue {{site.data.keyword.cloud_notm}}. Afin de supprimer la visibilité d'un service dans le catalogue pour une organisation, entrez la commande suivante :

```
cf ba remove-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Nom ou identificateur global unique (GUID) du plan de service à activer. Si vous entrez un nom de plan de service qui n'est pas unique, par exemple, "Standard" ou "Basic", vous êtes invité à sélectionner un plan de service. Pour identifier un nom de plan de service, sélectionnez la catégorie du service dans la page d'accueil, puis <b>Ajouter</b> pour afficher les services de cette catégorie. Cliquez sur le nom du service pour ouvrir la vue détaillée, depuis laquelle vous pourrez examiner les noms des plans de service disponibles pour ce service.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation à retirer de la liste de visibilité du service.</dd>
</dl>

Vous pouvez aussi utiliser **`ba rspv`** comme alias pour le nom de commande plus long **`ba remove-service-plan-visibility`**.
{: tip}

### Edition de la visibilité d'un service pour les organisations
{: #admin_editvis_service_org}

Vous pouvez modifier et remplacer la liste des services que des organisations spécifiques peuvent voir dans le catalogue {{site.data.keyword.cloud_notm}}. Afin de remplacer tous les services visibles existants pour une organisation ou plusieurs organisations, entrez la commande suivante :

```
cf ba edit-service-plan-visibilities plan_identifier organization_1 optional_organization_2
```
{: codeblock}

Cette commande remplace les services visibles existants pour les organisations spécifiées par le service que vous indiquez dans la commande.

<dl>
<dt>plan_identifier</dt>
<dd>Nom ou identificateur global unique (GUID) du plan de service à activer. Si vous entrez un nom de plan de service qui n'est pas unique, par exemple, "Standard" ou "Basic", vous êtes invité à sélectionner un plan de service. Pour identifier un nom de plan de service, sélectionnez la catégorie du service dans la page d'accueil, puis <b>Ajouter</b> pour afficher les services de cette catégorie. Cliquez sur le nom du service pour ouvrir la vue détaillée, depuis laquelle vous pourrez examiner les noms des plans de service disponibles pour ce service.</dd>
<dt>organization</dt>
<dd>Nom ou identificateur global unique de l'organisation pour laquelle ajouter la visibilité. Vous pouvez activer la visibilité du service pour plusieurs organisations en entrant des noms ou des identificateurs globaux uniques supplémentaires dans la commande.</dd>
</dl>

Vous pouvez aussi utiliser **`ba espv`** comme alias pour le nom de commande plus long **`ba edit-service-plan-visibility`**.
{: tip}

## Administration des rapports
{: #admin_add_report}

### Ajout de rapports
{: #admin_adding_report}

Pour ajouter un rapport de sécurité, entrez la commande suivante :

```
cf ba add-report category date PDF|TXT|LOG RTF
```
{: codeblock}

Si vous disposez de droits d'accès en écriture pour les rapports, vous pouvez créer une nouvelle catégorie et ajouter un rapport en utilisant l'un des formats admis pour vos utilisateurs. Entrez le nom de la nouvelle catégorie pour le paramètre
**`catégorie`** ou ajoutez votre nouveau rapport à une catégorie existante.

<dl>
<dt>category</dt>
<dd>Catégorie du rapport. Si le nom comporte un espace, placez-le entre guillemets.</dd>
<dt>date</dt>
<dd>Date du rapport au format AAAAMMJJ.</dd>
<dt>PDF|TXT|LOG</dt>
<dd>Chemin d'accès au rapport au format PDF, au fichier texte ou au fichier journal à télécharger.</dd>
<dt>RTF</dt>
<dd>Option permettant d'inclure une version RTF (Rich Text Format) du document PDF. Elle ne s'applique que si vous avez inclus un chemin d'accès au rapport au format PDF. La version RTF est utilisée pour l'indexation et la recherche.</dd>
</dl>

Vous pouvez aussi utiliser **`ba ar`** comme alias pour le nom de commande plus long **`ba add-report`**.
{: tip}

### Suppression de rapports
{: #admin_del_report}

Pour supprimer un rapport de sécurité, entrez la commande suivante :

```
cf ba delete-report category date name
```
{: codeblock}

<dl>
<dt>category</dt>
<dd>Catégorie du rapport. Si le nom comporte un espace, placez-le entre guillemets.</dd>
<dt>date</dt>
<dd>Date du rapport au format AAAAMMJJ.</dd>
<dt>name</dt>
<dd>Nom du rapport.</dd>
</dl>

Vous pouvez aussi utiliser **`ba d`r** comme alias pour le nom de commande plus long **`ba delete-report`**.
{: tip}

### Extraction de rapports
{: #admin_retr_report}

Pour extraire un rapport de sécurité, utilisez la commande suivante :

```
cf ba retrieve-report search
```
{: codeblock}

<dl>
<dt>search</dt>
<dd>Nom de fichier du rapport. Si le nom comporte un espace, placez-le entre guillemets.</dd>
</dl>

Vous pouvez aussi utiliser **`ba rr`** comme alias pour le nom de commande plus long **`ba retrieve-report`**.
{: tip}

## Affichage des informations relatives aux mesures des ressources
{: #cliresourceusage}

Vous pouvez afficher des informations sur les mesures des ressources,
notamment sur l'utilisation de la mémoire, du disque et de l'unité centrale. Vous pouvez consulter un récapitulatif des ressources physiques et réservées disponibles et de l'utilisation de ces ressources. Vous pouvez également afficher les données d'utilisation des agents DEA (Droplet Execution Agent) et des cellules (architecture Diego). Pour afficher les informations sur les mesures des ressources, entrez la commande suivante :

```
cf ba resource-metrics
```

Vous pouvez aussi utiliser **`ba rsm`** comme alias pour le nom de commande plus long **`ba resource-metrics`**.
{: tip}

## Affichage de l'historique relatif aux mesures des ressources
{: #cliresourceusagehistory}

Vous pouvez obtenir l'historique des mesures de ressources à des fins d'utilisation de la mémoire et du disque. Les valeurs renvoyées incluent la quantité de ressources utilisées par rapport à la quantité totale disponible, à la fois pour les ressources physiques et les ressources réservées. Les données d'historique relatives à l'utilisation de la mémoire et du disque peuvent être affichées sur une base horaire, quotidienne ou mensuelle. Indiquez une date de début et une date de fin pour extraire les données d'une période donnée. Lorsque aucune date n'est spécifiée, les données d'historique par défaut sont les données mémoire horaires des dernières 48 heures. Les données sont affichées par ordre décroissant, les dates les plus récentes en premier. Pour afficher les informations d'historique relatives aux mesures des ressources, entrez la commande suivante :

```
cf ba resource-metrics-history hourly|daily|monthly  memory|disk   start|end
```
{: codeblock}

<dl>
<dt>--hourly</dt>
<dd>Affiche les données d'historique des dernières 48 heures. Il s'agit de la valeur par défaut.</dd>
<dt>--daily</dt>
<dd>Affiche la moyenne quotidienne des données d'historique au cours des 30 derniers jours.</dd>
<dt>--monthly</dt>
<dd>Affiche la moyenne mensuelle des données d'historique au cours des 6 derniers mois.</dd>
<dt>--memory</dt>
<dd>Affiche la valeur utilisée et la valeur totale de la mémoire physique et réservée.</dd>
<dt>--disk</dt>
<dd>Affiche la valeur utilisée et la valeur totale du disque physique et réservé.</dd>
<dt>--start</dt>
<dd>Indique une date de début pour une base quotidienne ou mensuelle au format mm-jj-aaaa, ou une date et une heure de début pour une base horaire au format de fuseau horaire mm-jj-aaaa.</dd>
<dt>--end</dt>
<dd>Indique une date de fin pour une base quotidienne ou mensuelle au format mm-jj-aaaa, ou une date et une heure de fin pour une base horaire au format de fuseau horaire mm-jj-aaaa.</dd>
</dl>

### Exemples
{: #cliresourceusagehistoryex}

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

Vous pouvez afficher la liste précédente des paramètres de commande et des exemples en utilisant la commande suivante :

```
cf ba resource-metrics-history -help
```

Vous pouvez aussi utiliser **`ba rsmh`** comme alias pour le nom de commande plus long **`ba resource-metrics-history`**.
{: tip}

## Administration des courtiers de services
{: #admin_servbro}

### Liste des courtiers de services
{: #clilistservbro}

Pour dresser la liste des courtiers de services, utilisez la commande suivante :

```
cf ba service-brokers broker_name
```
{: codeblock}

Pour répertorier tous les courtiers de services, entrez la commande sans le paramètre **`broker_name`**.

<dl>
<dt>broker_name</dt>
<dd>Nom du courtier de services personnalisé. Utilisez ce paramètre pour obtenir des informations sur un courtier de services spécifique. Facultatif.</dd>
</dl>

Vous pouvez aussi utiliser **`ba sb`** comme alias pour le nom de commande plus long **`ba service-brokers`**.
{: tip}

### Ajout d'un courtier de services
{: #cliaddservbro}

Pour ajouter un courtier de services afin de pouvoir ajouter un service personnalisé au catalogue {{site.data.keyword.cloud_notm}}, utilisez la commande suivante :

```
cf ba add-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>Nom du courtier de services personnalisé.</dd>
<dt>user_name</dt>
<dd>Nom d'utilisateur du compte ayant accès au courtier de services.</dd>
<dt>password</dt>
<dd>Mot de passe du compte ayant accès au courtier de services.</dd>
<dt>broker_url</dt>
<dd>Adresse URL du courtier de services.</dd>
</dl>

Vous pouvez aussi utiliser **`ba asb`** comme alias pour le nom de commande plus long **`ba add-service-broker`**.
{: tip}

### Suppression d'un courtier de services
{: #clidelservbro}

Pour supprimer un courtier de services qui retire le service personnalisé du catalogue {{site.data.keyword.cloud_notm}}, utilisez la commande suivante :

```
cf ba delete-service-broker service_broker
```
{: codeblock}

<dl>
<dt>service_broker</dt>
<dd>Nom ou identificateur global unique du courtier de services personnalisé.</dd>
</dl>

Vous pouvez aussi utiliser **`ba dsb`** comme alias pour le nom de commande plus long **`ba delete-service-broker`**.
{: tip}

### Mise à jour d'un courtier de services
{: #cliupdservbro}

Pour mettre à jour un courtier de services, utilisez la commande suivante :

```
cf ba update-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>Nom du courtier de services personnalisé.</dd>
<dt>user_name</dt>
<dd>Nom d'utilisateur du compte ayant accès au courtier de services.</dd>
<dt>password</dt>
<dd>Mot de passe du compte ayant accès au courtier de services.</dd>
<dt>broker_url</dt>
<dd>Adresse URL du courtier de services.</dd>
</dl>

Vous pouvez aussi utiliser **`ba usb`** comme alias pour le nom de commande plus long **`ba update-service-broker`**.
{: tip}

## Administration des groupes de sécurité d'application
{: #admin_secgro}

Pour utiliser des groupes de sécurité d'application, vous devez être un administrateur avec accès complet pour l'environnement local ou dédié. Tous les utilisateurs de l'environnement peuvent répertorier les groupes de sécurité d'application disponibles pour l'organisation ciblée par la commande. En revanche, pour créer, mettre à jour ou lier des groupes de sécurité d'application, vous devez être un administrateur de l'environnement {{site.data.keyword.cloud_notm}}.

Les groupes de sécurité d'application fonctionnent comme des pare-feux virtuels qui contrôlent le trafic sortant des applications de votre environnement {{site.data.keyword.cloud_notm}}. Chaque groupe de sécurité d'application comprend une liste de règles autorisant un trafic et des communications spécifiques vers et depuis le réseau externe. Vous pouvez lier un ou plusieurs groupes de sécurité d'application à un ensemble de groupes spécifique en appliquant, par exemple, un accès global pour un ensemble de groupes ou en effectuant une liaison à des espaces d'une organisation de votre environnement {{site.data.keyword.cloud_notm}}.

A l'origine, {{site.data.keyword.cloud_notm}} est configuré avec un accès global restreint au réseau externe. Deux groupes de sécurité créés par IBM, `public_networks` et `dns`, permettent un accès global au réseau externe lorsque vous liez ces deux groupes aux ensembles de groupes de sécurité Cloud Foundry. Les deux ensembles de groupes de sécurité Cloud Foundry qui sont utilisés pour appliquer un accès global sont **Default Staging** et **Default Running**. Ces ensembles de groupes appliquent les règles autorisant le trafic vers toutes les applications en cours d'exécution ou toutes les applications en cours de constitution. Si vous ne souhaitez pas établir de liaison à ces deux ensembles de groupes de sécurité, vous pouvez annuler la liaison à ces ensembles de groupes Cloud Foundry, puis lier le groupe de sécurité à un espace donné. Pour plus d'informations, voir [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

Le fait de supprimer la liaison entre les ensembles de groupes **Default Staging** ou **Default Running** et les deux groupes de sécurité créés par IBM, `public_networks` et `dns`, désactive l'accès global au réseau externe. Tenez compte des répercussions possibles sur l'ensemble des applications en cours d'exécution ou de transfert dans votre environnement quand vous supprimez une liaison.
{: important}

Les commandes suivantes, qui vous permettent d'utiliser les groupes de sécurité, sont basées sur la version 1.6 de Cloud Foundry. Pour plus d'informations, y compris sur les zones obligatoires et facultatives, reportez-vous aux informations Cloud Foundry concernant la [création de groupes de sécurité d'application](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

### Liste des groupes de sécurité
{: #clilissecgro}

Pour dresser la liste de tous les groupes de sécurité, utilisez la commande suivante :

```
cf ba security-groups
```
{: codeblock}

Pour afficher les détails d'un groupe de sécurité donné, utilisez la commande suivante :

```
cf ba security-groups security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Nom du groupe de sécurité.</dd>
</dl>

Vous pouvez aussi utiliser **`ba sg`** comme alias pour le nom de commande plus long **`ba security-groups`**.
{: tip}

### Création d'un groupe de sécurité
{: #clicreasecgro}

Pour créer un groupe de sécurité, utilisez la commande suivante :
```
cf ba create-security-group security-group path-to-rules-file
```
{: codeblock}

Le préfixe `adminconsole_` est ajouté au nom de chaque groupe de sécurité que vous créez afin de le distinguer des groupes de sécurité créés par IBM.

<dl>
<dt>security-group</dt>
<dd>Nom du groupe de sécurité.</dd>
<dt>path-to-rules-file</dt>
<dd>Chemin d'accès relatif ou absolu à un fichier de règles.</dd>
</dl>

Vous pouvez aussi utiliser **`ba csg`** comme alias pour le nom de commande plus long **`ba create-security-group`**.
{: tip}

Pour plus d'informations sur la création de groupes de sécurité et les règles qui définissent le trafic sortant, voir [Creating Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

### Mise à jour d'un groupe de sécurité
{: #cliupdsecgro}

Pour mettre à jour un groupe de sécurité, utilisez la commande suivante :

```
cf ba update-security-group security-group path-to-rules-file
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Nom du groupe de sécurité.</dd>
<dt>path-to-rules-file</dt>
<dd>Chemin d'accès relatif ou absolu à un fichier de règles.</dd>
</dl>

Vous pouvez aussi utiliser **`ba usg`** comme alias pour le nom de commande plus long **`ba update-security-group`**.
{: tip}

### Suppression d'un groupe de sécurité
{: #clidelsecgro}

Pour supprimer un groupe de sécurité, utilisez la commande suivante :
```
cf ba delete-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Nom de votre groupe de sécurité</dd>
</dl>

Vous pouvez aussi utiliser **`ba dsg`** comme alias pour le nom de commande plus long **`ba delete-security-group`**.
{: tip}

### Liaison de groupes de sécurité
{: #clibindsecgro}

Pour établir une liaison vers l'ensemble de groupes de sécurité Default Staging, utilisez la commande suivante :

```
cf ba bind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Nom de votre groupe de sécurité</dd>
</dl>

Vous pouvez aussi utiliser **`ba bssg`** comme alias pour le nom de commande plus long **`ba bind-staging-security-group`**.
{: tip}

Pour établir une liaison vers l'ensemble de groupes de sécurité Default Running, utilisez la commande suivante :

```
cf ba bind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd class="pd">Nom de votre groupe de sécurité</dd>
</dl>

Vous pouvez aussi utiliser **`ba brsg`** comme alias pour le nom de commande plus long **`ba bind-running-security-group`**.
{: tip}

Pour lier un groupe de sécurité à un espace, utilisez la commande suivante :

```
cf ba bind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Nom du groupe de sécurité.</dd>
<dt>org</dt>
<dd>Nom de l'organisation à laquelle associer le groupe de sécurité.</dd>
<dt>space</dt>
<dd>Nom de l'espace dans l'organisation à laquelle associer le groupe de sécurité.</dd>
</dl>

Vous pouvez aussi utiliser **`ba bsg`** comme alias pour le nom de commande plus long **`ba bind-security-group`**.
{: tip}

Pour plus d'informations sur la liaison des groupes de sécurité, voir [Binding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

### Annulation de la liaison de groupes de sécurité
{: #cliunbindsecgro}

La suppression de la liaison entre l'ensemble de groupes Default Staging et les deux groupes de sécurité créés par IBM, `public_networks` et `dns`, désactive l'accès global au réseau externe et doit être utilisé avec prudence en tenant compte des répercussions possibles sur l'ensemble des applications en cours de transfert dans votre environnement. Pour annuler la liaison vers l'ensemble de groupes de sécurité Default Staging, utilisez la commande suivante :

```
cf ba unbind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Nom du groupe de sécurité.</dd>
</dl>

Vous pouvez aussi utiliser **`ba ussg`** comme alias pour le nom de commande plus long **`ba unbind-staging-security-group`**.
{: tip}

La suppression de la liaison entre l'ensemble de groupes Default Running et les deux groupes de sécurité créés par IBM, `public_networks` et `dns`, désactive l'accès global au réseau externe et doit être utilisé avec prudence en tenant compte des répercussions possibles sur l'ensemble des applications en cours d'exécution dans votre environnement. Pour annuler la liaison vers l'ensemble de groupes de sécurité Default Running, utilisez la commande suivante :

```
cf ba unbind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Security group</dt>
<dd>Nom du groupe de sécurité.</dd>
</dl>

Vous pouvez aussi utiliser **`ba brsg`** comme alias pour le nom de commande plus long **`ba unbind-running-security-group`**.
{: tip}

Pour annuler la liaison d'un groupe de sécurité à un espace, utilisez la commande suivante :

```
cf ba unbind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Nom du groupe de sécurité.</dd>
<dt>org</dt>
<dd>Nom de l'organisation dont vous souhaitez annuler la liaison avec le groupe de sécurité.</dd>
<dt>space</dt>
<dd>Nom de l'espace dans l'organisation dont vous souhaitez annuler la liaison avec le groupe de sécurité.</dd>
</dl>

Vous pouvez aussi utiliser **`ba usg`** comme alias pour le nom de commande plus long **`ba unbind-security-group`**.
{: tip}

Pour plus d'informations sur l'annulation de la liaison des groupes de sécurité, voir [Unbinding Application Security Groups](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

## Administration des packs de construction
{: #admin_buildpack}

### Affichage de la liste des packs de construction
{: #clilistbuildpack}

Si vous disposez des droits en écriture dans le catalogue des applications, vous pouvez répertorier les packs de construction. Pour répertorier tous les packs de construction ou visualiser un pack de construction spécifique, utilisez la commande suivante :

```
cf ba buildpacks buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Paramètre facultatif permettant de spécifier un pack de construction particulier à afficher.</dd>
</dl>

Vous pouvez aussi utiliser **`ba lb`** comme alias pour le nom de commande plus long **`ba buildpacks`**.
{: tip}

### Création et téléchargement d'un pack de construction
{: #clicreupbuildpack}

Si vous disposez des droits en écriture dans le catalogue des applications, vous pouvez créer et télécharger un pack de construction. Vous pouvez télécharger tout fichier compressé dont le type est `.zip`. Pour télécharger un pack de construction, utilisez la commande suivante :

```
cf ba create-buildpack buildpack_name file_path position
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Nom du pack de construction à télécharger.</dd>
<dt>file_path</dt>
<dd>Chemin du fichier compressé du pack de construction.</dd>
<dt>position</dt>
<dd>Ordre dans lequel les packs de construction sont recherchés au cours de la détection automatique des packs de construction.</dd>
</dl>

Vous pouvez aussi utiliser **`ba cb`** comme alias pour le nom de commande plus long **`ba create-buildpack`**.
{: tip}

### Mise à jour d'un pack de construction
{: #cliupdabuildpack}

Si vous disposez des droits en écriture dans le catalogue des applications, vous pouvez mettre à jour un pack de construction existant. Pour mettre à jour un pack de construction, utilisez la commande suivante :
```
cf ba update-buildpack buildpack_name position enabled locked
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Nom du pack de construction à mettre à jour.</dd>
<dt>position</dt>
<dd>Ordre dans lequel les packs de construction sont recherchés au cours de la détection automatique des packs de construction.</dd>
<dt>enabled</dt>
<dd>Indique si le pack de construction est utilisé pour la constitution.</dd>
<dt>locked</dt>
<dd>Indique si le pack de construction est verrouillé pour empêcher les mises à jour.</dd>
</dl>

Vous pouvez aussi utiliser **`ba ub`** comme alias pour le nom de commande plus long **`ba update-buildpack`**.
{: tip}

### Suppression d'un pack de construction
{: #clidelbuildpack}

Si vous disposez des droits en écriture dans le catalogue des applications, vous pouvez supprimer un pack de construction existant. Pour supprimer un pack de construction, utilisez la commande suivante :
```
cf ba delete-buildpack buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Nom du pack de construction à supprimer.</dd>
</dl>

Vous pouvez aussi utiliser **`ba db`** comme alias pour le nom de commande plus long **`ba delete-buildpack`**.
{: tip}
