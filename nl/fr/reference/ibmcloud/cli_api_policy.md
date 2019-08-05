---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}

# Gestion de l'accès IAM, des clés d'API, des ID de service et des groupes d'accès
{: #ibmcloud_commands_iam}

Les commandes suivantes permettent de gérer les clés d'API, les ID de service, les groupes d'accès et les règles d'autorisation pour des utilisateurs, des services et des groupes d'accès.
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Répertorier tous les ID de service :
```
ibmcloud iam service-ids [--uuid] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel des ID de service uniquement</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier l'identificateur unique universel de tous les ID de service sous le compte en cours :
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Afficher les détails d'un ID de service :
```
ibmcloud iam service-id (NAME|UUID) [--uuid] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de l'ID de service</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'ID de service `sample-test` :
```
ibmcloud iam service-id sample-test
```
{: codeblock}

Afficher les détails de l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Créer un ID de service :
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock] [--output FORMAT]
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
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Créer un ID de service avec le nom de service `sample-test` et la description `hello, world!` :
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

Créer un ID de service verrouillé avec le nom de service `sample-test` et la description `hello, world!` :
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

Mettre à jour un ID de service :
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description du service</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer l'ID de service `sample-test` en `sample-test-2` sans confirmation :
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

Mettre à jour la description du service `sample-test` :
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

Renommer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` en `sample-test-3` avec la nouvelle description :
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Supprimer un ID de service :
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'ID de service `sample-teset` sans confirmation :
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

Supprimer l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Verrouiller un ID de service :
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller l'ID de service `sample-teset` sans confirmation :
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

Verrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Déverrouiller un ID de service :
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller l'ID de service `sample-teset` sans confirmation :
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

Déverrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Répertorier toutes les clés d'API de plateforme {{site.data.keyword.cloud_notm}} :
```
ibmcloud iam api-keys [--output FORMAT]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Créer une clé d'API de plateforme {{site.data.keyword.cloud_notm}} :
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock] [--output FORMAT]
```

L'utilisation de la connexion à l'interface CLI {{site.data.keyword.cloud_notm}} ne fonctionne pas avec la clé d'API SL existante disponible sur `control.softlayer.com`. Un compte {{site.data.keyword.cloud_notm}} mis à niveau dans lequel l'infrastructure est gérée via [cloud.ibm.com](https://cloud.ibm.com/registration){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") est requis pour la connexion à l'interface CLI {{site.data.keyword.cloud_notm}} avec une clé d'API.
{: note}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à créer.</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Description de la clé d'API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Sauvegarder les informations de clé d'API dans le fichier spécifié.</dd>
<dt>--lock</dt>
<dd>Verrouillez la clé d'API lors de sa création.</dd>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Créer une clé d'API et effectuer la sauvegarde dans un fichier :
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

Créer une clé d'API verrouillé portant le nom "test-key" :
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Mettre à jour une clé d'API de plateforme {{site.data.keyword.cloud_notm}} :
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Ancien nom de la clé d'API à mettre à jour, exclut UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à mettre à jour, exclut NAME</dd>
<dt>-n <i>NAME</i> (facultatif)</dt>
<dd>Nouveau nom de la clé d'API</dd>
<dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
<dd>Nouvelle description de la clé d'API</dd>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la description d'une clé d'API :
```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

Supprimer une clé d'API de plateforme {{site.data.keyword.cloud_notm}} :
```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, exclut UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à supprimer, exclut NAME</dd>
<dt>-f, --force</dt>
<dd>Force une suppression sans demander de confirmation.</dd>
</dl>

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

Verrouiller une clé d'API de plateforme :
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, exclut UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à verrouiller, exclut NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le verrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API test-api-key :
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

Verrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué :
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}s

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Déverrouiller une clé d'API de plateforme :
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à déverrouiller, exclut UUID</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à déverrouiller, exclut NAME</dd>
<dt>-f, --force</dt>
<dd>Forcer le déverrouillage sans confirmation.</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API test-api-key :
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

Déverrouiller sans confirmation la clé d'API ayant l'identificateur unique universel indiqué :
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Répertorier toutes les clés d'API d'un service :
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Afficher les clés d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les clés d'API du service `sample-service` :
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Répertorier les détails d'une clé d'API de service :
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, exclut APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, exclut APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>Afficher l'identificateur unique universel de la clé d'API de service</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Afficher la clé d'API de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la clé d'API de service `sample-key` du service `sample-service` :
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Créer une clé d'API de service :
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [--output FORMAT] [-f, --force] [--lock]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service ou de la clé d'API de service nouvellement créée</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Description de la clé d'API</dd>
  <dt>--file</dt>
  <dd>Sauvegarder les informations de clé d'API dans le fichier spécifié.</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer la clé d'API de service `sample-key` pour le service `sample-service` sans confirmation :
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Mettre à jour une clé d'API de service :
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, exclut APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, exclut APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de la clé d'API de service</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description de la clé d'API de service</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommez la clé d'API de service `sample-key` en `new-sample-key` :
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Supprimer une clé d'API de service :
```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, exclut APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, exclut APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Supprimer sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la clé d'API de service `sample-key` de l'ID de service `sample-service` :
```
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Verrouiller une clé d'API de service :
```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, exclut APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, exclut APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :
```
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Déverrouiller une clé d'API de service :
```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, exclut APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, exclut APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, exclut SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, exclut SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :
```
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Répertorier les règles d'un utilisateur
```
ibmcloud iam user-policies USER_NAME [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel les règles appartiennent</dd>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :
 
Afficher les règles de l'utilisateur `name@example.com` :
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Afficher les détails d'une règle utilisateur :
```
ibmcloud iam user-policy USER_NAME POLICY_ID [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>POLICY_ID (obligatoire)</dt>
<dd>ID de la règle</dd>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher la règle `0bb730daa` de l'utilisateur `name@example.com` :
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Créer une règle utilisateur :
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Compte ciblé

<strong>Options de commande</strong> :
<dl>
<dt>USER_NAME (obligatoire)</dt>
<dd>Nom de l'utilisateur auquel la règle appartient</dd>
<dt>--file <i>FILE</i> (facultatif)</dt>
<dd>Fichier JSON de définition de règle</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (facultatif)</dt>
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Cette option exclut les indicateurs `--file`, `--resource` et `--resource-group-id`.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Cette option exclut les indicateurs `--file`, `--resource` et `--resource-group-name`.</dd>
<dt>--account-management (facultatif)</dt>
<dd>Accordez l'accès à tous les services de gestion des comptes.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
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

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Mettre à jour une règle utilisateur :
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT]
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
<dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (facultatif)</dt>
<dd>Nom de service de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--service-instance <i>SERVICE_INSTANCE_GUID</i> (facultatif)</dt>
<dd>Identificateur global unique de l'instance de service de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--region <i>REGION</i> (facultatif)</dt>
<dd>Région de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (facultatif)</dt>
<dd>Type de ressource de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource <i>RESOURCE</i> (facultatif)</dt>
<dd>Ressource de la définition de règle. Exclut l'option `--file`.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (facultatif)</dt>
<dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Cette option exclut les indicateurs `--file`, `--resource` et `--resource-group-id`.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (facultatif)</dt>
<dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Cette option exclut les indicateurs `--file`, `--resource` et `--resource-group-name`.</dd>
<dt>--account-management (facultatif)</dt>
<dd>Accordez l'accès à tous les services de gestion des comptes.</dd>
<dt>--output FORMAT (facultatif)</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle utilisateur avec celle définie dans le fichier JSON
```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Administrateur` à `name@example.com` pour toutes les ressources `sample-service` :
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

Mettre à jour une règle d'utilisateur afin d'accorder le rôle `Editeur` à `name@example.com` pour la ressource `key123` de l'exemple d'instance de service ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Opérateur` à `name@example.com` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle utilisateur afin d'accorder le rôle `Afficheur` à `name@example.com` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
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

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Répertorier toutes les règles de service du service spécifié :
```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie pour les stratégies de service. Seul JSON est pris en charge pour l'instant.</dd>
  <dt>-f, --force (facultatif)</dt>
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

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Afficher les détails d'une règle de service :
```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie pour la stratégie de service. Seul JSON est pris en charge pour l'instant.</dd>
  <dt>-f, --force (facultatif)</dt>
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

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Créer une règle de service :
```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. Cette option exclut les indicateurs `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `--resource-group-name` et `--resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
  <dt>--service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>--resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>--resource</dt>
  <dd>Ressource de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-name`.</dd>
  <dt>--account-management (facultatif)</dt>
  <dd>Accorder l'accès à tous les services de gestion des comptes</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Créer la stratégie de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une stratégie de service à partir du fichier JSON pour le service `test` :
```
ibmcloud iam service-policy-create test --file @policy.json
```

Créer une stratégie de service à partir du fichier JSON pour le service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

Accorder au service `test` le rôle `Administrateur` pour tous les services de gestion de compte :
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

Accorder au service `test` le rôle `Afficheur` pour toutes les ressources du compte :
```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Mettre à jour une règle de service :
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service</dd>
  <dt>POLICY_ID (obligatoire)</dt>
  <dd>ID de la règle de service<dd>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle. Cette option exclut les indicateurs `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `resource-group-name` et `resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option exclut l'indicateur `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-name`.</dd>
  <dt>--account-management (facultatif)</dt>
  <dd>Accorder l'accès à tous les services de gestion des comptes</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Mettre à jour la règle de service sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `test` :
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Mettre à jour la règle de service `140798e2-8ea7db3` à partir du fichier JSON pour le service `test` :
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Mettre à jour la règle de service `140798e2-8ea7db3` afin d'accorder au service `test` le rôle `Administrateur` pour tous les services de gestion de compte :
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

Mettre à jour la règle de service `140798e2-8ea7db3` pour accorder au service `test` le rôle `Afficheur` pour toutes les ressources du compte :
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Supprimer une règle de service :
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

Supprimer la règle `140798e2-8ea7db3` du service `test` :
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```

Supprimer la règle `140798e2-8ea7db3` du service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` :
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Extraire et afficher les jetons OAuth pour la session en cours :
```
ibmcloud iam oauth-tokens [--output FORMAT]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Actualiser et afficher les jetons OAuth :
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

Répertorier les rôles de plateforme et de service définis :
```
ibmcloud iam roles [--service SERVICE_NAME] [--output FORMAT]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--service SERVICE_NAME</dt>
  <dd>Nom du service. Répertorier uniquement les rôles définis dans la plateforme s'il n'est pas spécifié.</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les rôles de plateforme
```
ibmcloud iam roles
```

Répertorier les rôles du service `cloudantnosql` au format JSON :
```
ibmcloud iam roles --service cloudantnosql --output JSON
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Déconnecter l'IBMid public de l'ID non IBMid dédié :
```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-f, --force</dt>
  <dd>Forcer la déconnexion sans confirmation</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Créer une règle d'autorisation permettant à une instance de service d'accéder à une autre instance de service :

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-type RESOURCE_TYPE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME] [--target-resource-type RESOURCE_TYPE | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--output FORMAT]
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
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom d'instance de service source, exclut `--source-service-instance-id`. S'il n'est pas spécifié, toutes les instances du service source disposent d'un droit d'accès.</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>ID d'instance de service source, exclut `--source-service-instance-name`. S'il n'est pas spécifié, toutes les instances du service source disposent d'un droit d'accès.</dd>
  <dt>--source-resource-type</dt>
  <dd>Type de ressource du service source</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nom de l'instance du service cible, exclut `--target-service-instance-id`. S'il n'est pas spécifié, toutes les instances du service cible disposent d'un droit d'accès.</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>ID de l'instance du service cible, exclut `--target-service-instance-name`. S'il n'est pas spécifié, toutes les instances du service cible disposent d'un droit d'accès.</dd>
  <dt>--target-resource-type</dt>
  <dd>Type de ressource du service cible</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Supprimer une règle d'autorisation :
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

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Afficher les détails d'une règle d'autorisation :
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID de la règle d'autorisation à afficher.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl> 

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Répertorier les règles d'autorisation du compte en cours :
```
ibmcloud iam authorization-policies [--output FORMAT]
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
   </dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Afficher les groupes d'accès du compte en cours :
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-u</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'utilisateur appartient. Cette option est propre à '-s'.</dd>
  <dt>-s</dt>
  <dd>Afficher la liste des groupes d'accès auxquels l'ID de service appartient. Cette option est propre à '-u'.</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes d'accès :
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Afficher les détails d'un groupe d'accès :
```
ibmcloud iam access-group GROUP_NAME [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-id</dt>
  <dd>Afficher l'ID uniquement</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails du groupe d'accès `example_group` :
```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Créez un groupe d'accès :
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-d, --description</dt>
  <dd>Description de groupe d'accès</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Créer un groupe d'accès `example_group` :
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Mettre à jour un groupe d'accès :
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-n, --name</dt>
  <dd>Nom du nouveau groupe d'accès</dd>
  <dt>-d, --description</dt>
  <dd>Nouvelle description</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe d'accès `example_group` en `hello_world_group` :
```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
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

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Répertorier les utilisateurs d'un groupe d'accès :
```
ibmcloud iam access-group-users GROUP_NAME [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher la liste de tous les utilisateurs du groupe d'accès `example_group` :
```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Ajouter des utilisateurs à un groupe d'accès :
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

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Retirer un utilisateur d'un groupe d'accès :
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

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Retirer l'utilisateur de tous les groupes d'accès :
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

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Répertorier les ID de service d'un groupe d'accès :
```
ibmcloud iam access-group-service-ids GROUP_NAME [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>--output FORMAT</dt>
<dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher la liste des ID de service du groupe d'accès `example_group` :
```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Ajouter l'ID de service à un groupe d'accès :
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

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Retirer un ID de service d'un groupe d'accès :
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

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Retirer un ID de service de tous les groupes d'accès :
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

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Répertorier les règles d'un groupe d'accès :
```
ibmcloud iam access-group-policies GROUP_NAME [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher la liste de toutes les règles du groupe d'accès `example_group` :
```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Afficher les détails d'une règle de groupe d'accès :
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de la règle `51b9717e-76b0-4f6a-bda7-b8132431f926` du groupe d'accès `example_group` :
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Créer une règle de groupe d'accès :
```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>-roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
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

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Mettre à jour une règle de groupe d'accès :
```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--file</dt>
  <dd>Fichier JSON de définition de règle</dd>
  <dt>--roles</dt>
  <dd>Noms de rôle de la définition de règle. Pour connaître les rôles pris en charge d'un service spécifique, exécutez `ibmcloud iam roles --service SERVICE_NAME`. Cette option exclut `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nom de service de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>Identificateur global unique de l'instance de service de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-region</dt>
  <dd>Région de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Type de ressource de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource</dt>
  <dd>Ressource de la définition de règle. Cette option exclut `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nom du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID du groupe de ressources. `*` correspond à tous les groupes de ressources. Exclut `--file` et `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge.</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une règle de groupe d'accès avec celle d'un fichier JSON de règles :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Administrateur` à `example_group` pour toutes les ressources `sample-service` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Editeur` à `example_group` pour la ressource `key123` de l'instance `sample-service` ayant l'identificateur global unique `d161aeea-fd02-40f8-a487-df1998bd69a9` dans la région `us-south` :
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Opérateur` à `example_group` pour le groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources `sample-resource-group` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Mettre à jour une règle de groupe d'accès afin d'accorder le rôle `Afficheur` à `example_group` pour les membres du groupe de ressources portant l'ID `dda27e49d2a1efca58083a01dfde18f6` :
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Supprimer une règle de groupe d'accès :
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
