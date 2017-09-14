---



copyright:

  years: 2015, 2017

lastupdated: "2017-06-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Installation manuelle de l'interface de ligne de commande
{: #cli}

L'interface de ligne de commande {{site.data.keyword.Bluemix}} fournit une expérience de ligne de commande permettant de gérer votre environnement {{site.data.keyword.Bluemix_notm}}. Elle inclut également une interface de ligne de commande Cloud Foundry, cf, dans son installation, pour la gestion des applications et des services Cloud Foundry.
{:shortdesc}

Les deux outils de ligne de commande utilisent par défaut le port 443. Si un proxy HTTP est interposé entre les outils CLI et l'environnement {{site.data.keyword.Bluemix_notm}}, vous devez configurer la variable d'environnement `HTTP_PROXY` en spécifiant l'URL réelle du proxy HTTP et le port correspondant, si celui-ci est présent. Pour plus de détails, voir [Using the CLI with an HTTP Proxy Server ![External link icon](../icons/launch-glyph.svg)](http://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window}.

[Téléchargez l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} ](/docs/cli/reference/bluemix_cli/all_versions.html){: new_window} 

Si vous travaillez dans un environnement macOS, le moyen le plus facile de démarrer avec les outils IBM Cloud est d'utiliser [IBM Cloud Application Tools 2](/docs/cli/icat.html).
{: tip}

## ![](./images/CLI_Plugin.svg) Plug-in d'interface de ligne de commande
{: #cliplugins notoc}

Etendez facilement votre interface de ligne de commande {{site.data.keyword.Bluemix_notm}} avec des commandes supplémentaires. Pour accéder aux plug-in de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, voir le [référentiel de plug-in de l'interface de ligne de commande![External link icon](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window}.

### Etendez votre interface de ligne de commande {{site.data.keyword.Bluemix_notm}} : bx
{: #cli_bluemix_ext notoc}


Après l'installation de l'outil d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, le [référentiel de plug-in d'interface de ligne de commande ![External link icon](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window} est pré-configuré avec un alias de référentiel `Bluemix` par défaut. Vous pouvez installer directement les plug-in disponibles.

```
bluemix plugin install nom_plug-in -r Bluemix
```

| *Interface de ligne de commande {{site.data.keyword.autoscaling}}* |  *Service IBM Bluemix Container*  |
|-----|-----|
| Nom du plug-in : auto-scaling <br> [Afficher la documentation](/docs/cli/plugins/auto-scaling/index.html) |  Nom du plug-in : container-service  <br> [Afficher la documentation](/docs/containers/cs_cli_devtools.html) |
{: caption="Tableau 2. Plug-in" caption-side="top"}

|  *Appairage de réseaux privés* | *Schémas* | *Réseau privé virtuel*  |
|-----|-----|-----|
| Nom du plug-in : private-network-peering  <br> [Afficher la documentation](/docs/cli/plugins/pnp/index.html) | Nom du plug-in : Schematics  <br> [Afficher la documentation](/docs/services/schematics/schematics_reference.html) | Nom du plug-in : VPN  <br> [Afficher la documentation](/docs/cli/plugins/bx_vpn/index.html) |
{: caption="Tableau 3. Plug-in" caption-side="top"}

Vous pouvez également ajouter des plug-in à partir d'autres référentiels conformes à l'architecture d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.
1. Pour installer des plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} depuis un autre référentiel, définissez le noeud
final du registre des plug-in :
```
bluemix plugin repo-add bluemix-other-repo [url_référentiel]
```
où `url_référentiel` est l'URL HTTPS du référentiel de plug-in.

2. Exécutez la commande suivante pour installer un plug-in :
```
bluemix plugin install nom_plug-in -r bluemix-other-repo
```

### Etendez l'interface de ligne de commande Cloud Foundry : bx cf
{: #cli_cf_ext notoc}

Après l'installation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, une interface de ligne de commande Cloud Foundry est également installée dans le répertoire d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Exécutez les commandes d'interface de ligne de commande Cloud Foundry à l'aide de `bluemix cf`.

* Pour installer des plug-in d'interface de ligne de commande cf depuis le registre {{site.data.keyword.Bluemix_notm}}, définissez le noeud
final du registre des
plug-in :

```
bluemix cf add-plugin-repo bluemix-cf-repo https://plugins.ng.bluemix.net
```
{: codeblock}

* Ensuite, exécutez la commande suivante pour installer un plug-in :

```
bluemix cf install-plugin nom_plug-in -r bluemix-cf-repo
```
{: codeblock}

| *Console d'administration* | *Réseau privé virtuel* |
|-----------------|-----------------|
|  Nom du plug-in : bluemix-admin <br> [Afficher la documentation](/docs/cli/plugins/bluemix_admin/index.html) | Nom du plug-in : VPN <br> [Afficher la documentation](/docs/cli/plugins/vpn/index.html) |
{: caption="Tableau 4. Plug-in" caption-side="top"}


## ![](./images/Integrated_Dev_Tools.svg) Outils de développement intégrés
{: #ide notoc}

Téléchargez et installez des plug-in afin d'intégrer les services {{site.data.keyword.Bluemix_notm}} que
vous préférez.

| *Liberty for Java* | *MobileFirst* | *{{site.data.keyword.rules_short}}* | *API Connect* | *Eclipse Tools for Bluemix* |
|----------|----------|----------|----------|----------|
| [Liberty Eclipse Plug-in ![External link icon](../icons/launch-glyph.svg)](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/){: new_window} | [Eclipse Plug-in ![External link icon](../icons/launch-glyph.svg)](https://marketplace.eclipse.org/content/ibm-mobilefirst-platform-studio){: new_window} | [Rules Designer Eclipse Plug-in](../services/rules/index.html#rulov002) | [Developer Toolkit](/docs/services/apiconnect/apic_003.html#apic_001 ) | [Plug-in Bluemix Eclipse](/docs/manageapps/eclipsetools/eclipsetools.html) |
{: caption="Tableau 5. Plug-in" caption-side="top"}
