---



copyright:

  years: 2015, 2018
lastupdated: "2018-10-18"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Installation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} autonome
{: #install_use}

L'interface CLI d'{{site.data.keyword.Bluemix_notm}} fournit une interface de ligne de commande pour gérer les ressources dans {{site.data.keyword.Bluemix_notm}}. Vous pouvez continuer à utiliser l'interface de ligne de commande cf pour vous connecter à {{site.data.keyword.Bluemix_notm}}, mais elle ne fonctionne qu'avec un service Cloud Foundry dans {{site.data.keyword.Bluemix_notm}}. 

Si vous souhaitez installer l'interface de ligne de commande {{site.data.keyword.Bluemix}} ainsi que d'autres outils et plug-in recommandés pour le développement d'applications pour {{site.data.keyword.Bluemix_notm}}, suivez la méthode décrite [ici](/docs/cli/index.html).
{: tip}

Procédez comme suit pour installer l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} autonome :

1. Sélectionnez le programme d'installation de votre système d'exploitation afin de le télécharger

   Mac OS X 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le) : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Pour les versions 32 bits et les versions antérieures, accédez à la page répertoriant [toutes les versions](/docs/cli/reference/ibmcloud/all_versions.html) pour effectuer un téléchargement

1. Exécutez le programme d'installation
   * Pour Mac OS et Windows, exécutez simplement le programme d'installation.
   * Pour Linux, extrayez le package et exécutez le script `install`.

1. Ciblez un noeud final d'API et connectez-vous à {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Vous êtes maintenant prêt à gérer des ressources {{site.data.keyword.Bluemix_notm}}. Entrez `ibmcloud help` pour examiner les descriptions des commandes.

Si vous utilisez un ID fédéré, suivez les instructions décrites [ici](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) pour vous connecter avec un code d'accès unique ou une clé d'API.  
{: tip}

Outre les programmes d'installation, vous disposez d'autres options pour installer l'interface CLI {{site.data.keyword.Bluemix_notm}} :

* Installation à partir du shell
* Téléchargement du package binaire et installation dans un répertoire personnalisé

## Installation à partir du shell
{: #shell_install}

### MacOS

Copiez et collez la commande suivante dans un terminal de votre système Mac OS et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copiez et collez la commande suivante dans un terminal de votre système Linux OS et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copiez et collez la commande suivante dans une console de terminal [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} et exécutez-la :

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Installation dans un répertoire personnalisé

Lorsque vous utilisez des programmes d'installation ou un script shell pour installer l'interface CLI {{site.data.keyword.Bluemix_notm}}, les fichiers binaires sont placés dans les répertoires système. Si vous souhaitez indiquer un autre répertoire, procédez comme suit.

### Etape 1 : Téléchargement du package binaire en utilisant les liens suivants en fonction de votre système d'exploitation.

| Plateforme | Téléchargements | Total de contrôle |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### Etape 2 : Extraction du package dans un répertoire défini.

   Une fois le package extrait, le contenu est similaire à l'exemple suivant :

   Pour Linux et MacOS

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

   * Ajoutez `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` à la variable d'environnement `PATH`.
   * Pour le support de l'exécution automatique de shell (MacOS et Linux uniquement), consultez [ce guide](enable_cli_autocompletion.html).
   
<!-- ## Uninstalling the stand-alone {{site.data.keyword.Bluemix_notm}} CLI

The following sections provide details on how to uninstall the stand-alone {{site.data.keyword.Bluemix_notm}} CLI on specific platforms.

### Uninstalling on Windows

1. Click the `Start` button, and then select `Control Panel`.
2. In the pop-up window, click `Uninstall a program`.
3. In the pop-up application list, locate `IBM Cloud Command Line Interface`.
4. Right click `IBM Cloud Command Line Interface`, and select `Uninstall`.
5. The uninstaller will be launched. Follow the instructions to finish the uninstallation.

### Uninstalling on Linux/macOS

#### Prior to version `0.9.0`

1. Open a terminal, and run the following commands:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. Clean up the autocompletion scripts, if you've configured them. For more details, see [Enable CLI Autocompletion](enable_cli_autocompletion.html).

#### Version `0.9.0` and later

1. Open a terminal, and run the following command:
  * `/usr/local/ibmcloud/uninstall`
2. Clean up the autocompletion scripts, if you've configured them. For more details, see [Enable CLI Autocompletion](enable_cli_autocompletion.html). -->


## Autres liens permettant d'explorer davantage l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}

* [Extension de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} avec des plug-in](/docs/cli/reference/ibmcloud/extend_cli.html)
* [Référence de l'interface CLI {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud/bx_cli.html)

## Signaler des problèmes et soumettre des commentaires en retour
{: #issues}

Utilisez les options suivantes pour signaler des problèmes ou soumettre des demandes de nouvelle fonction :
 * Créez des problèmes dans [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg).
 * Laissez des messages dans le [canal IBM Cloud Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com). Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg).
