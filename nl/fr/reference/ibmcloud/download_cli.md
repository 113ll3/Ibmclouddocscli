---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome
{: #install-ibmcloud-cli}

L'interface CLI {{site.data.keyword.cloud}} fournit une interface de ligne de commande permettant de gérer les ressources dans {{site.data.keyword.cloud_notm}}. Vous pouvez toujours utiliser l'interface de ligne de commande `cf` pour vous connecter à {{site.data.keyword.cloud_notm}} mais elle fonctionne uniquement avec un service Cloud Foundry dans {{site.data.keyword.cloud_notm}}. 

Si vous souhaitez installer la dernière interface de ligne de commande {{site.data.keyword.cloud}} ainsi que d'autres outils et plug-in pour le développement d'applications pour {{site.data.keyword.cloud_notm}}, voir [Initiation à l'interface de ligne de commande {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

## Avant de commencer
{: #before-download-cli}

Si vous avez besoin d'utiliser une version 32 bits ou une version antérieure autre que la dernière version pour les environnements dédiés {{site.data.keyword.cloud_notm}}, voir [Editions de l'interface CLI {{site.data.keyword.cloud_notm}} ](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

## Installation à l'aide d'un programme d'installation
{: #ibmcloud-cli-installer}

Procédez comme suit pour installer la dernière version autonome de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} :

1. Sélectionnez le programme d'installation de votre système d'exploitation à télécharger :
  *  macOS X 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * Windows 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * Linux x86 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * Linux LE 64 bits (ppc64le) : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")

2. Exécutez le programme d'installation :
  * Pour Mac et Windows&trade;, exécutez le programme d'installation.
  * Pour Linux&trade;, extrayez le package et exécutez le script `install`.

3. Connectez-vous à {{site.data.keyword.cloud_notm}} :
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Vous êtes maintenant prêt à gérer les ressources {{site.data.keyword.cloud_notm}}. Entrez `ibmcloud help` pour visualiser les descriptions de commande.

  Si vous utilisez un ID fédéré, [connectez-vous avec un code d'accès unique ou une clé d'API](/docs/iam?topic=iam-federated_id).
  {: tip}

## Installation à partir du shell
{: #shell_install}

Pour installer manuellement la dernière interface de ligne de commande pour votre système d'exploitation à partir du shell, utilisez la commande suivante :

* Pour **Mac**, copiez et collez la commande suivante sur un terminal et exécutez-la :
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* Pour **Linux&trade;**, copiez et collez la commande suivante sur un terminal et exécutez-la :
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* Pour **Windows&trade;**, copiez et collez la commande suivante sur une console de terminal [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") et exécutez-la :
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Installation dans un répertoire personnalisé
{: #install-custom-dir}

Lorsque vous utilisez des programmes d'installation ou un script shell pour installer l'interface CLI {{site.data.keyword.cloud_notm}}, elle est installée dans votre répertoires système. Si vous souhaitez indiquer un autre répertoire, procédez comme suit :

1. Téléchargez le package binaire correspondant à votre système d'exploitation en utilisant les liens suivants :
  * macOS : [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * linux32 : [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * linux64 : [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * ppc64le : [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * win32 : [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") /[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
  * win64 : [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")

2. Extrayez le package dans un répertoire défini.

   Vous pouvez voir le contenu extrait suivant :

   Pour Linux&trade; et Mac :
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   Windows :
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Ajoutez la variable d'environnement `PATH` et activez l'exécution automatique de shell.
  * Ajoutez `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` à la variable d'environnement `PATH`.
  * Pour obtenir des informations de support sur l'exécution automatique de shell (Mac et Linux uniquement), consultez [ce guide](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Mise à jour de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}
{: #update-ibmcloud-cli}

Vous devez utiliser la dernière version de l'interface de ligne de commande. Si vous n'utilisez pas la dernière version, exécutez la commande suivante pour mettre à jour votre interface de ligne de commande :

```
ibmcloud update
```
{: codeblock}

Pour déterminer la version de votre interface de ligne de commande {{site.data.keyword.cloud_notm}}, exécutez la commande suivante :
```
ibmcloud -v
```
{: codeblock}

Si vous exécutez l'édition en cours, le résultat suivant s'affiche :
```
Recherche des mises à jour...
Aucune mise à jour n'est requise. Votre interface de ligne de commande est déjà à jour.
```
{: screen}

Pour recevoir des notifications sur les éditions de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}, abonnez-vous au [référentiel d'éditions CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").
