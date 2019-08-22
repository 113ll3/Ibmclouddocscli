---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Gestion des ressources DevOps avec l'interface de ligne de commande
{: #managing-devops-resources-cli}

Vous pouvez utiliser l'[interface de ligne de commande {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-getting-started) pour gérer les ressources DevOps directement à partir de la ligne de commande. Apprenez à utiliser l'interface de ligne de commande pour afficher les chaînes d'outils DevOps ainsi que les pipelines et les journaux de pipeline.
{: shortdesc}

## Avant de commencer
{: #set-toolchain-view}

La vue de chaîne d'outils dépend du groupe de ressources actuellement ciblé. Utilisez les commandes suivantes pour identifier votre groupe de ressources actuellement ciblé et le modifier si vous le souhaitez.

* Pour afficher le groupe de ressources actuellement ciblé, exécutez :
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* Si aucun groupe de ressources n'est défini ou si vous voulez modifier le groupe de ressources, exécutez : 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Affichage d'une chaîne d'outils
{: #viewing-toolchains}

Vous pouvez afficher les informations relatives à la chaîne d'outils depuis la ligne de commande ou les visualiser dans un navigateur.

* Pour afficher les chaînes d'outils dans le groupe de ressources ciblé, exécutez :
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* Pour afficher les détails relatifs à la chaîne d'outils, exécutez :
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* Pour visualiser les détails relatifs à la chaîne d'outils dans le navigateur, exécutez :
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Affichage d'un pipeline
{: #viewing-pipeline}

Pour obtenir les détails requis pour appeler un pipeline, exécutez `ibmcloud dev toolchains` afin d'obtenir le nom de la chaîne d'outils. Si le nom est déjà connu, exécutez `ibmcloud dev toolchain-get [toolchain-name]` afin d'obtenir les détails de la chaîne d'outils. 

* Pour obtenir les détails d'un pipeline et de ses étapes, identifiez le pipeline et son ID afin d'exécuter la commande suivante :
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* En utilisant l'ID de pipeline de la commande précédente, vous pouvez exécuter le pipeline :
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  Cette commande appelle une exécution de l'étape et de ses travaux. L'opération, si elle aboutit, entraîne l'exécution du travail pour chaque travail de l'étape sélectionnée.

## Affichage des journaux de pipeline
{: #viewing-pipeline-logs}

* Pour afficher les journaux depuis l'exécution d'un pipeline, exécutez :
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* Pour filtrer les journaux par étape, appliquez la commande précédente et ajoutez l'ID d'étape :
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Commandes DevOps utiles
{: #helpful-devops-commands}

Utilisez les commandes `ibmcloud dev` suivantes pour gérer les ressources DevOps.

### Commandes de chaîne d'outils
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) - Affiche une liste de chaînes d'outils dans le groupe de ressources ciblé.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) - Affiche les détails pour une chaîne d'outils sélectionnée dans le groupe de ressources ciblé.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) - Ouvre la chaîne d'outils sélectionnée dans le navigateur.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) - Supprime une chaîne d'outils.

### Commandes de pipeline
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) - Affiche les détails d'un pipeline de chaîne d'outils.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) - Exécute un pipeline.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) - Ouvre le pipeline dans le navigateur.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) - Affiche les journaux de l'exécution d'un pipeline.

Pour plus d'informations, voir la référence de commande [ `ibmcloud dev` complète](/docs/cli/idt?topic=idt-cli).
