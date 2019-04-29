---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Foire aux questions (FAQ)
{: #ibm-cli-faq}

## Quelle est la structure de fichier pour les applications {{site.data.keyword.cloud_notm}} ?
{: #cli-file-structure}

Les applications créées ou activées à partir de l'interface de ligne de commande sont fournies avec des paramètres préconfigurés encapsulés dans le fichier `cli-config.yml`. Le fichier `cli-config.yml` contient des entrées par défaut utilisées par les commandes de l'interface de ligne de commande, qui peuvent être remplacées par des valeurs transmises via la ligne de commande.

Les applications déployées dans une chaîne d'outils DevOps peuvent également inclure des fichiers, tels que `toolchain.yml` et `pipeline.yml`. Les applications déployées manuellement peuvent inclure des fichiers de graphique Helm et un fichier `manifest.yml` (pour le déploiement dans Cloud Foundry ou Kubernetes, par exemple).

## Comment les conteneurs locaux sont-ils utilisés ?
{: #cli-faq-containers}

Le plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_long}} utilise deux conteneurs pour faciliter la génération et le test de votre application. Le premier est le conteneur tools, qui contient les utilitaires nécessaires pour générer et tester votre application. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Vous pouvez le considérer comme un conteneur de développement car il contient les outils qui sont normalement utilisés pour le développement d'un environnement d'exécution particulier.

Le second conteneur est le conteneur "run" qui reproduit fidèlement l'environnement d'exécution réel de votre application une fois cette dernière déployée sur le cloud. Il peut être déployé pour être utilisé dans {{site.data.keyword.cloud_notm}}, par exemple. Par conséquent, un point
d'entrée démarrant votre application est défini. Lorsque vous choisissez d'exécuter votre application via le plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_long}}, ce conteneur est utilisé. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

# Comment déployer le code existant ?
Pour déployer un codebase existant, procédez comme suit pour activer votre application[activer votre application](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Documentation, vidéos et blogues de référence
{: #cli-faq-reference}

### Blogues
{: #cli-blogs}

- [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Vidéos
{: #cli-videos}

- [How to deploy to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [How to deploy existing projects to {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Create, debug, and deploy a Node.js app with the {{site.data.keyword.dev_cli_long}} CLI Plug-in and VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Documentation et tutoriels
- [Continuous Deployment to Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Traitement des incidents liés au plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_long}}](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} Commandes du plug-in d'interface de ligne de commande (CLI) IBM Cloud Developer Tools (ibmcloud dev)](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Débogage d'application locale pour l'interface de ligne de commande {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-local-debug)

**Pour signaler des problèmes ou donner votre avis, vous pouvez utiliser le [canal {{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com) - Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**
