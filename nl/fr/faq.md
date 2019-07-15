---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Foire aux questions
{: #ibm-cli-faq}

## Faut-il utiliser la dernière version de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} ?
{: #cli-latest-version}

Oui, vous devez utiliser la dernière version. Vous pouvez déterminer la version que vous utilisez en exécutant la commande suivante :

```
ibmcloud -v
```
{: codeblock}

## Comment mettre à jour l'interface de ligne de commande
{: #cli-update-version}

Exécutez la commande suivante pour effectuer une mise à jour vers la dernière version de l'interface de ligne de commande :

```
ibmcloud update
```
{: codeblock}

## Comment recevoir des notifications pour les nouvelles éditions de l'interface de ligne de commande ?
{: #cli-get-notified}

Oui, vous recevez des notifications relatives aux nouvelles éditions de l'interface de ligne de commande dès qu'elles sont disponibles. Abonnez-vous au [{{site.data.keyword.cloud_notm}}référentiel d'éditions CLI](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")

## Quelle est la structure de fichier pour les applications {{site.data.keyword.cloud_notm}} ?
{: #cli-file-structure}

Les applications créées ou activées à partir de l'interface de ligne de commande sont fournies avec des paramètres préconfigurés encapsulés dans le fichier `cli-config.yml`. Le fichier `cli-config.yml` contient des entrées par défaut utilisées par les commandes de l'interface de ligne de commande, qui peuvent être remplacées par des valeurs transmises via la ligne de commande.

Les applications déployées dans une chaîne d'outils DevOps peuvent également inclure des fichiers, tels que `toolchain.yml` et `pipeline.yml`. Les applications déployées manuellement peuvent inclure des fichiers de graphique Helm et un fichier `manifest.yml` (pour le déploiement dans Cloud Foundry ou Kubernetes, par exemple).

## Comment les conteneurs locaux sont-ils utilisés ?
{: #cli-faq-containers}

Le plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_long}} utilise deux conteneurs pour faciliter la génération et le test de votre application. Le premier est le conteneur tools, qui contient les utilitaires nécessaires pour générer et tester votre application. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Vous pouvez le considérer comme un conteneur de développement car il contient les outils qui sont normalement utilisés pour le développement d'un environnement d'exécution particulier.

Le second conteneur est le conteneur "run" qui reproduit fidèlement l'environnement d'exécution réel de votre application une fois cette dernière déployée sur le cloud. Il peut être déployé pour être utilisé dans {{site.data.keyword.cloud_notm}}, par exemple. Par conséquent, un point d'entrée démarrant votre application est défini. Lorsque vous choisissez d'exécuter votre application via le plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_long}}, ce conteneur est utilisé. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

## Comment déployer du code existant ?

Pour déployer une base de code existante, voir [Génération d'actifs de déploiement et d'activation de cloud](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

