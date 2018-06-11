---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} Présentation
{: #overview}

{{site.data.keyword.dev_cli_notm}} est un outil de création, de développement et de déploiement d'applications à l'aide d'une ligne de commande qui est utilisée par les développeurs souhaitant utiliser une ligne de commande pour développer des applications Web, mobiles et de microservice de bout en bout. Commencez rapidement avec un jeu d'outils recommandé en exécutant l'un des scripts ci-après.
{: shortdesc}

## Prérequis pour {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Inscrivez-vous auprès de [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* Si vous utilisez Microsoft Windows, vous devez utiliser Windows 10 ou une version ultérieure.

* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Comment installer {{site.data.keyword.dev_cli_notm}}
{: #installation}

Pour installer le jeu d'outils, vous pouvez exécuter la commande appropriée afin de lancer le programme d'installation. Cette action entraîne l'installation des outils recommandés pour le développement d'{{site.data.keyword.Bluemix_notm}} (s'ils ne sont pas déjà installés) : `Homebrew` (Mac uniquement), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, plug-in {{site.data.keyword.dev_cli_notm}}, plug-in Cloud Functions, plug-in Container Registry, plug-in Container Service et plug-in `sdk-gen`.

**Mac et Linux :**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10 :**

* Remarque : ouvrez Windows PowerShell en cliquant avec le bouton droit de la souris sur l'icône Windows PowerShell et en sélectionnant "Run as Administrator".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

## Vérification de l'installation
Pour vérifier l'installation, exécutez la commande `help` :

```
ibmcloud dev help
```
{: codeblock}

Si l'installation a abouti, la sortie devrait indiquer les instructions d'utilisation, la version actuelle et les commandes prises en charge.


## Autres liens permettant d'explorer davantage {{site.data.keyword.dev_cli_notm}}

- [Configuration détaillée](/docs/cli/idt/setting_up_idt.html)
- [Syntaxe](/docs/cli/idt/index.html)
- [Commandes](/docs/cli/idt/commands.html)
- [Plug-in de l'interface de ligne de commande](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE Extension](/docs/cli/idt/vscode.html)
- [Installation manuelle de l'interface de ligne de commande IBM Cloud](/docs/cli/reference/bluemix_cli/get_started.html)
- [Signalement de problèmes sur GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Demandez un accès par équipe en cliquant [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/)
