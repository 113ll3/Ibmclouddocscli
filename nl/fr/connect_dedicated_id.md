---



copyright:

  years: 2015，2018

lastupdated: "2018-04-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Connexion d'un ID dédié à votre IBMid public
{: #connect_dedicated_id}

Pour une connexion à un cloud dédié sur lequel un service IAM public est disponible, l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} exige que vous vous connectiez avec votre IBMid public plutôt que via l'ID dédié.


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  Noeud final d'API : https://api.{dedicated_env}.bluemix.net

  Le service de jeton IAM public est disponible dans l'environnement dédié.
  Connectez-vous avec votre IBMid public ou utilisez '--no-iam' pour vous connecter en tant qu'utilisateur dédié uniquement.

  E-mail>
```

Si votre ID dédié a déjà été connecté à l'IBMid public, il s'authentifie et se connecte :

```
  Authentification en cours...
  OK

  Connecté à l'utilisateur dédié my_dedicated_id
```

Toutefois, si votre ID dédié n'a pas été connecté à l'IBMid public, vous êtes invité à vous connecter manuellement à l'IBMid public :

```
  Vous vous connectez avec un IBMid qui n'est associé à aucun utilisateur dédié.
  Pour configurer la connexion, entrez les données d'identification de l'utilisateur dédié.

  Choisissez un type de données d'identification :
  1. Nom d'utilisateur et mot de passe
  2. Code temporel unique (En obtenir un à l'adresse https://login.{dedicated_env}.bluemix.net.com/passcode)
  Entrez un nombre>
```

Sélectionnez une option pour l'entrée des données d'identification pour l'ID dédié. Après une authentification réussie, votre ID dédié est connecté à votre ID public.

## Comment forcer une connexion au serveur UAA local ?

Pour forcer une connexion au serveur UAA avec un ID dédié, spécifiez l'option `--no-iam` dans la commande `bluemix login` :

```
  $ bluemix login --no-iam
```

## Déconnexion de votre ID dédié depuis l'IBMid public 

Vous pouvez utiliser `bluemix iam dedicated-id-disconnect` pour déconnecter l'IBMid public de l'ID dédié connecté.

```
  $ bluemix iam dedicated-id-disconnect
  Voulez-vous vraiment déconnecter my_dedicated_id de l'IBMid public ? (O/N)> y
  Déconnexion de l'utilisateur dédié my_dedicated_id de l'IBMid public...
  OK

  Déconnexion...
  OK
```

