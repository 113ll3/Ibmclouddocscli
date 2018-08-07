---

copyright:

  years: 2018


lastupdated: "2018-07-27"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes pour la gestion des services Cloud Foundry Enterprise Environment (expérimental)
{: #ibmcloud_commands_cfee}

<table summary="Gestion des services Cloud Foundry Enterprise Environment (expérimental)">
<caption>Tableau 1. Gestion des services Cloud Foundry Enterprise Environment (expérimental)</caption>
 <thead>
 <th colspan="5">Gestion des services Cloud Foundry Enterprise Environment (expérimental)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

 ### ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Répertorier les environnements CFEE.

```
ibmcloud cfee environments
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

### ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Afficher les détails d'un environnement CFEE.

```
ibmcloud cfee environment NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
  <dl>
   <dt>--id</dt>
   <dd>Afficher l'ID uniquement.</dd>
  </dl>

<strong>Exemples</strong> :

Afficher les détails d'un environnement CFEE env_example :

```
ibmcloud cfee environment env_example
```

Afficher l'ID d'un environnement CFEE env_example :

```
ibmcloud cfee environment env_example --id
```
