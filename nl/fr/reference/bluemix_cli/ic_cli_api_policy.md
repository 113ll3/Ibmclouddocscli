---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes de l'interface CLI pour la gestion des règles et des clés d'API
{: #ibmcloud_commands_iam}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les clés d'API et les règles.">
 <caption>Tableau 1. Commandes de gestion des clés d'API et des règles</caption>
  <thead>
  <th colspan="5">Commandes de gestion des clés d'API et des règles</th>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-ids](ic_cli_api_policy.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam service-id](ic_cli_api_policy.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](ic_cli_api_policy.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](ic_cli_api_policy.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](ic_cli_api_policy.html#ibmcloud_iam_service_id_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-id-lock](ic_cli_api_policy.html#ibmcloud_iam_service_id_lock)</td>
   <td>[ibmcloud iam service-id-unlock](ic_cli_api_policy.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam api-keys](ic_cli_api_policy.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](ic_cli_api_policy.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](ic_cli_api_policy.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](ic_cli_api_policy.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](ic_cli_api_policy.html#ibmcloud_iam_api_key_lock)</td>
   <td>[ibmcloud iam api-key-unlock](ic_cli_api_policy.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](ic_cli_api_policy.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](ic_cli_api_policy.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](ic_cli_api_policy.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](ic_cli_api_policy.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](ic_cli_api_policy.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-api-key-lock](ic_cli_api_policy.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[ibmcloud iam service-api-key-unlock](ic_cli_api_policy.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
    <td>[ibmcloud iam service-policies](ic_cli_api_policy.html#ibmcloud_iam_service_policies)</td>
    <td>[ibmcloud iam service-policy](ic_cli_api_policy.html#ibmcloud_iam_service_policy)</td>
    <td>[ibmcloud iam service-policy-create](ic_cli_api_policy.html#ibmcloud_iam_service_policy_create)</td>
    <td>[ibmcloud iam service-policy-update](ic_cli_api_policy.html#ibmcloud_iam_service_policy_update)</td>
    <td>[ibmcloud iam service-policy-delete](ic_cli_api_policy.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](ic_cli_api_policy.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](ic_cli_api_policy.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](ic_cli_api_policy.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](ic_cli_api_policy.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](ic_cli_api_policy.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam oauth-tokens](ic_cli_api_policy.html#ibmcloud_iam_oauth_tokens)</td>
     <td>[ibmcloud iam dedicated-id-disconnect](ic_cli_api_policy.html#ibmcloud_iam_dedicated_id_disconnect)</td>
     <td>[ibmcloud iam authorization-policy-create](ic_cli_api_policy.html#ibmcloud_iam_authorization_policy_create)</td>
     <td>[ibmcloud iam authorization-policy-delete](ic_cli_api_policy.html#ibmcloud_iam_authorization_policy_delete)</td>
     <td>[ibmcloud iam authorization-policy](ic_cli_api_policy.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam authorization-policies](ic_cli_api_policy.html#ibmcloud_iam_authorization_policies)</td>
  </tr>
  </tbody>
  </table>
  
  ### ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Répertorier tous les ID de service

```
ibmcloud iam service-ids [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel des ID de service uniquement</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les identificateurs uniques universels de tous les ID de service sous le compte en cours

```
ibmcloud iam service-ids --uuid
```

### ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Afficher les détails d'un ID de service

```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de l'ID de service</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'ID de service `sample-test`

```
ibmcloud iam service-id sample-test
```
Afficher les détails de l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

### ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Créez un ID de service

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Description de l'ID de service</dd>
  <dt>--lock</dt>
  <dd>Verrouiller l'ID de service lors de la création</dd>
</dl>

<strong>Exemples</strong> :

Créez un ID de service avec le nom `sample-test` et la description `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Créer un ID de service verrouillé ayant le nom de service `sample-test` et la description `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```

### ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Mettre à jour un ID de service

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description du service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez l'ID de service `sample-test` en `sample-test-2` sans demander de confirmation

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Mettre à jour la description du service `sample-test`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Renommer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` en `sample-test-3` avec une nouvelle description

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```

### ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Supprimer un ID de service

```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'ID de service `sample-teset` sans demander de confirmation

```
ibmcloud iam service-id-delete sample-teset -f
```

Supprimer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

### ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Verrouiller un ID de service

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller l'ID de service `sample-teset` sans confirmation

```
ibmcloud iam service-id-lock sample-teset -f
```

Verrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

### ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Déverrouiller un ID de service

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, s'utilise exclusivement avec UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, s'utilise exclusivement avec NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller l'ID de service `sample-teset` sans confirmation

```
ibmcloud iam service-id-unlock sample-teset -f
```

Déverrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

### ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Répertorier toutes les clés d'API de la plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Prérequis</strong> : Noeud final, Connexion

### ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Créez une nouvelle clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à créer.</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Description de la clé d'API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
<dt>--lock</dt>
<dd>Verrouiller la clé d'API lors de la création</dd>
</dl>

<strong>Exemples</strong> :

Créez une clé d'API et de la sauvegarder dans un fichier

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Créer une clé d'API verrouillée portant le nom "test-key"

```
ibmcloud iam api-key-create test-key --lock
```

### ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Mettre à jour une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Ancien nom de la clé d'API à mettre à jour, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à mettre à jour, s'utilise exclusivement avec NAME</dd>
<dt>-n <i>NAME</i> (facultatif)</dt>
<dd>Nouveau nom de la clé d'API</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Nouvelle description de la clé d'API</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la description d'une clé d'API :

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

### ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Supprimer une clé d'API de plateforme {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à supprimer, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

### ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

Verrouiller une clé d'API de plateforme

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à verrouiller, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le verrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

Verrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

### ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Déverrouiller une clé d'API de plateforme

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à déverrouiller, s'utilise exclusivement avec UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à déverrouiller, s'utilise exclusivement avec NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le déverrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

Déverrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

### ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Répertorier toutes les clés d'API d'un service

```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les clés d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les clés d'API du service `sample-service` :

```
ibmcloud iam service-api-keys sample-service
```

### ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Répertorier les détails d'une clé d'API de service

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de la clé d'API de service</dd>
  <dt>-f, --force</dt>
  <dd>Afficher la clé d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la clé d'API de service `sample-key` du service `sample-service` :

```
ibmcloud iam service-api-key sample-key sample-service
```

### ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Créez une clé d'API de service

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service ou de la clé d'API de service nouvellement créée</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Description de la clé d'API</dd>
  <dt>--file</dt>
  <dd>Sauvegarder les informations de clé d'API dans le fichier spécifié. Si cette option n'est pas spécifiée, le contenu JSON s'affiche.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer la clé d'API de service `sample-key` pour le service `sample-service` sans confirmation :

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

### ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Mettre à jour une clé d'API de service

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de la clé d'API de service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description de la clé d'API de service</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez la clé d'API de service `sample-key` en `new-sample-key` :

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

### ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Supprimer une clé d'API de service

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

### ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Verrouiller une clé d'API de service

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

### ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Déverrouiller une clé d'API de service

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

### ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Afficher les règles de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policies name@example.com
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel les règles appartiennent</dd>
</dl>

<strong>Exemples</strong> :

Afficher les règles de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policies name@example.com
```

### ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Afficher les détails d'une règle utilisateur

```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle</dd>
</dl>

<strong>Exemples</strong> :

Afficher la règle `0bb730daa` de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

### ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Créez une règle utilisateur

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>--file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Créez une règle utilisateur pour l'utilisateur `name@example.com` à partir du fichier JSON de règles `policy.json` :

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

Accorder le rôle `Administrateur` à `name@example.com` pour toutes les ressources `sample-service` :

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Accorder le rôle `Editeur` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Accorder le rôle `Opérateur` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Mettre à jour une règle utilisateur

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle à mettre à jour</dd>
<dt>--file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. S'utilise exclusivement avec les options '--file', '--resource' et '--resource-group-name'.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle utilisateur avec celle définie dans le fichier JSON

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Administrator` à `name@example.com` pour toutes les ressources `sample-service` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Mettre à jour une règle d'utilisateur afin d'accorder le rôle `Editor` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Operator` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Viewer` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Supprimer une règle utilisateur

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation la règle utilisateur</dd>
</dl>

<strong>Exemples</strong> :
Supprimer les règles `user-policy-id` de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Supprimer sans confirmation les règles `user-policy-id` de l'utilisateur `name@example.com` :

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

### ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Répertorier toutes les règles de service du service spécifié

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>-json</dt>
  <dd>Afficher la règle au format JSON</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les règles de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les règles du service `test` :

```
ibmcloud iam service-policies test
```
Répertorier les règles du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

### ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Afficher les détails d'une règle de service

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-json</dt>
  <dd>Afficher la règle au format JSON</dd>
  <dt>-f, --force</dt>
  <dd>Afficher la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Afficher la règle `140798e2-8ea7db3` du service `test` :

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Afficher la règle `140798e2-8ea7db3` du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

### ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Créer une règle de service

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. S'utilise exclusivement avec les options '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' et '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource</dt>
  <dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Créer la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une règle de service à partir du fichier JSON pour le service `test` :

```
ibmcloud iam service-policy-create test --file @policy.json
```
Créer une règle de service à partir du fichier JSON pour le service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

### ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Mettre à jour une règle de service

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. S'utilise exclusivement avec les options -r, --roles, --service-name, --service-instance, --region, --resource-type, --resource, resource-group-name et resource-group-id.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez 'ibmcloud iam roles --service SERVICE_NAME'. Cette option s'utilise exclusivement avec '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. S'utilise exclusivement avec l'option '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. Cette option s'utilise exclusivement avec '--file' et '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `test` :

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

### ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Supprimer une règle de service

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la règle `140798e2-8ea7db3` du service `test`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Supprimer la règle `140798e2-8ea7db3` du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

### ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Extraire et afficher les jetons OAuth de la session en cours.

```
ibmcloud iam oauth-tokens
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Actualiser et afficher les jetons OAuth.

```
ibmcloud iam oauth-tokens
```

### ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Déconnecter l'IBMid public de l'ID non IBMid dédié.

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la déconnexion sans confirmation</dd>
</dl>

### ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Créer une règle d'autorisation permettant à une instance de service d'accéder à une autre instance de service.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME] [—-target-service-instance TARGET_SERVICE_INSTANCE_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Service source dont l'accès peut être autorisé.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Service cible auquel le service source peut être autorisé à accéder.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>Rôles permettant d'accéder au service source.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service source ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service source.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance de service cible ; s'il n'est pas spécifié, l'accès sera autorisé pour toutes les instances du service cible.</dd>
</dl>

### ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Supprimer une règle d'autorisation.

```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la règle d'autorisation à supprimer.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation.</dd>
</dl>

### ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Afficher les détails d'une règle d'autorisation.

```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la règle d'autorisation à afficher.</dd>
</dl>

### ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Répertorier les règles d'autorisation du compte en cours.

```
ibmcloud iam authorization-policies
```

<strong>Prérequis</strong> : Noeud final, Connexion
