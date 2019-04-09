---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome
{: #install-ibmcloud-cli}

L'interface CLI {{site.data.keyword.cloud}} fournit une interface de ligne de commande permettant de gérer les ressources dans {{site.data.keyword.cloud_notm}}. Vous pouvez toujours utiliser l'interface de ligne de commande `cf` pour vous connecter à {{site.data.keyword.cloud_notm}} mais elle fonctionne uniquement avec un service Cloud Foundry dans {{site.data.keyword.cloud_notm}}. 

Si vous souhaitez installer l'interface de ligne de commande {{site.data.keyword.cloud}} ainsi que d'autres outils et plug-in pour le développement d'applications pour {{site.data.keyword.cloud_notm}}, voir [Initiation à l'interface de ligne de commande {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Pour installer l'interface de ligne de commande autonome {{site.data.keyword.cloud_notm}}, procédez comme suit :

1. Sélectionnez le programme d'installation de votre système d'exploitation à télécharger.

   Mac OS X 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bits : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le) : [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Pour les versions 32 bits et les versions antérieures, accédez à la page répertoriant [{{site.data.keyword.cloud_notm}}les éditions d'interface CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) à télécharger.

2. Exécutez le programme d'installation
   * Pour MacOS et Windows, exécutez le programme d'installation.
   * Pour Linux, extrayez le package et exécutez le script `install`.

3. Ciblez un noeud final d'API et connectez-vous à {{site.data.keyword.cloud_notm}} :
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Vous êtes maintenant prêt à gérer les ressources {{site.data.keyword.cloud_notm}}. Entrez `ibmcloud help` pour examiner les descriptions des commandes.

Si vous utilisez un ID fédéré, suivez les instructions décrites [ici](/docs/iam?topic=iam-federated_id#federated_id) pour vous connecter avec un code d'accès unique ou une clé d'API.  
{: tip}

Outre les programmes d'installation, vous disposez d'autres options pour installer l'interface CLI {{site.data.keyword.cloud_notm}} :

* Installation à partir du shell
* Téléchargement du package binaire et installation dans un répertoire personnalisé

## Installation à partir du shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Copiez et collez la commande suivante dans un terminal de votre système Mac OS et exécutez-la :
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Copiez et collez la commande suivante dans un terminal de votre système Linux et exécutez-la :
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Copiez et collez la commande suivante dans une console de terminal [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") et exécutez-la :
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Installation dans un répertoire personnalisé
{: #install-custom-dir}

Lorsque vous utilisez des programmes d'installation ou un script shell pour installer l'interface CLI {{site.data.keyword.Bluemix_notm}}, les fichiers binaires sont placés dans les répertoires système. Si vous souhaitez indiquer un autre répertoire, procédez comme suit.

### Etape 1 : Téléchargement du package binaire en utilisant les liens suivants en fonction de votre système d'exploitation.
{: #step1-custom-dir}

| Plateforme | Téléchargements | Total de contrôle |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Etape 2 : Extraction du package dans un répertoire défini.
{: #step2-custom-dir}

   Une fois le package extrait, vous pouvez voir le contenu présenté ci-dessous. 

   Pour Linux et macOS :

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
   {: codeblock}

   Pour Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Etape 3 : Ajout à la variable d'environnement `PATH` et activation de l'exécution automatique de shell
{: #step3-custom-dir}

   * Ajoutez `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` à la variable d'environnement `PATH`.
   * Pour obtenir des informations de support sur l'exécution automatique de shell (MacOS et Linux uniquement), consultez [ce guide](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Désinstallation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome
{: #uninstall-ibmcloud-cli}

Les sections ci-après contiennent des informations détaillées relatives à la désinstallation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome sur certaines plateformes.

### Désinstallation sous Windows
{: #uninstall-cli-windows}

1. Cliquez sur le bouton `Démarrer`, puis sélectionnez `Panneau de configuration`.
2. Dans la fenêtre en incrustation, cliquez sur `Désinstaller un programme`.
3. Dans la liste d'applications en incrustation, recherchez `IBM Cloud Command Line Interface`.
4. Avec le bouton droit de la souris, cliquez sur `IBM Cloud Command Line Interface` et sélectionnez `Désinstaller`.
5. Le programme de désinstallation est démarré. Suivez les instructions pour mener à terme la désinstallation.

### Désinstallation sur Linux et macOS
{: #uninstall-cli-linux-macos}

#### Versions antérieures à la version `0.9.0`

1. Ouvrez un terminal et exécutez les commandes suivantes :
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Nettoyez les scripts d'exécution automatique si vous les avez configurés. Pour plus de détails, voir [Activation de l'exécution automatique de shell pour l'interface CLI {{site.data.keyword.cloud_notm}} (Linux/MacOS uniquement)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Version `0.9.0` et versions ultérieures

1. Ouvrez un terminal et exécutez la commande suivante :
  * `/usr/local/ibmcloud/bin/uninstall`
2. Nettoyez les scripts d'exécution automatique personnalisés. Pour plus de détails, voir [Activation de l'exécution automatique de shell pour l'interface CLI {{site.data.keyword.cloud_notm}} (Linux/MacOS uniquement)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Autres liens permettant d'explorer davantage l'interface de ligne de commande {{site.data.keyword.cloud_notm}}
{: #other-cli-links}

* [Extension de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} avec des plug-in](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [Commandes générales de l'interface CLI (ibmcloud)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Signaler des problèmes et soumettre des commentaires en retour
{: #issues}

Utilisez les options suivantes pour signaler des problèmes ou soumettre des demandes de nouvelle fonction :
* Signalez des problèmes dans [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").
* Laissez des messages dans le [{{site.data.keyword.cloud_notm}}canal Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe"). Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").
