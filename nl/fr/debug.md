---

copyright:
  years: 2015, 2018
lastupdated: "2018-07-17"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# Débogage des applications cf pour {{site.data.keyword.Bluemix_notm}}
{: #debugging}

Si vous rencontrez des problèmes avec {{site.data.keyword.Bluemix}}, vous pouvez afficher les fichiers journaux et déboguer les erreurs.
{:shortdesc}

Les journaux fournissent des informations telles que l'exécution réussie d'un travail ou son échec. Ils fournissent également des informations
appropriées qui peuvent être utilisées pour le débogage et la détermination de la cause d'un problème.

Les journaux ont un format fixe. Vous pouvez filtrer les journaux prolixes ou utiliser des hôtes de
journalisation externes pour
stocker et traiter les journaux. Pour plus d'informations sur les formats de journal, l'affichage et le filtrage des journaux et la configuration de la journalisation externe, voir [Journalisation des applications qui s'exécutent dans Cloud Foundry ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](/docs/monitor_log/logging.html#logging){: new_window}.


## Débogage des erreurs de constitution
{: #debugging-staging-errors}
Vous pouvez rencontrer des problèmes lorsque vous constituez vos applications dans {{site.data.keyword.Bluemix_notm}}. Si le transfert de votre application
échoue, vous pouvez rechercher et examiner les journaux de transfert (STG) afin de déterminer ce qui s'est passé lors du déploiement
de l'application et corriger le problème. Pour plus d'informations sur les méthodes d'affichage des journaux pour les applications {{site.data.keyword.Bluemix}}, voir [Affichage des journaux ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}.  

Pour comprendre la raison pour laquelle votre application ne fonctionne pas dans {{site.data.keyword.Bluemix_notm}}, vous devez savoir comment une application est déployée et exécutée dans {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations, voir [Déploiement d'application ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](/docs/cfapps/depapps.html#appdeploy){: new_window}.


La procédure suivante présente l'utilisation de la commande `cf logs` pour déboguer des erreurs. Avant de continuer, vérifiez que vous avez installé l'interface de ligne de commande Cloud Foundry. Pour plus d'informations sur l'installation de l'interface de ligne de commande Cloud Foundry, voir [Installation de l'interface de ligne de commande Cloud Foundry ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](/docs/starters/install_cli.html){: new_window}.

  1. Connectez-vous à {{site.data.keyword.Bluemix_notm}} en entrant la commande suivante sur l'interface de ligne de commande Cloud Foundry :
     ```
	 cf api https://api.ng.bluemix.net
	 ```

  2. Connectez-vous à {{site.data.keyword.Bluemix_notm}} en entrant `cf login`.

  3. Extrayez les journaux récents en entrant `cf logs nom_application --recent`. Si vous désirez filtrer un journal prolixe, utilisez l'option `grep`. Par exemple, vous pouvez entrer le code suivant pour afficher les journaux [STG] seulement :
    ```
	cf logs nom_app --recent | grep '\[STG\]'
	```
  4. Examinez la première erreur affichée dans le journal.

Si vous utilisez le plug-in des outils IBM Eclipse for {{site.data.keyword.Bluemix_notm}} pour déployer des applications, dans l'onglet **Console** de l'outil Eclipse figurent des journaux similaires à la sortie des journaux cf. Vous pouvez également ouvrir une fenêtre Eclipse distincte pour suivi des journaux lorsque vous déployez l'application.

Outre la commande `cf logs`, dans {{site.data.keyword.Bluemix_notm}}, vous pouvez également utiliser le service {{site.data.keyword.loganalysisshort}} pour collecter les informations des journaux.

### Débogage des erreurs de constitution pour une application Node.js

L'exemple suivant illustre un journal affiché après l'entrée de la commande `cf logs nom_application --recent`. On présuppose que des erreurs se sont produites pour une application Node.js :
```
2014-08-11T14:19:36.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0]   ERR
2014-08-11T14:20:44.43+0100 [DEA]     OUT Stopping app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA]     OUT Stopped app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA]     OUT Got request for app with id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG]     OUT -----> Download app package (4.1M)
2014-08-11T14:20:51.90+0100 [STG]     OUT -----> Download app buildpack cache (1.1M)
2014-08-11T14:20:52.78+0100 [STG]     OUT -----> Buildpack Version: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG]     ERR parse error: Expected another key-value pair at line 18, column 3
2014-08-11T14:20:52.79+0100 [STG]     OUT 0 info it worked if it ends with ok
```
{: screen}


La première erreur dans le journal indique la raison pour laquelle la constitution a échoué. Dans cet exemple, la première erreur correspond à une
sortie du composant DEA au cours de la phase de constitution.
```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


Dans le cas d'une application Node.js, l'agent DEA utilise les informations du fichier `package.json` pour télécharger les modules. A partir de cette erreur, vous pouvez voir que l'erreur s'est produite pour le module. Par conséquent, vous devrez peut-être vérifier la ligne 18 du fichier `package.json`.

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


Vous pouvez constater qu'une virgule figure à la fin de la ligne 17 ; par conséquent une paire clé-valeur se trouvant à la ligne 18 est attendue. Pour corriger le problème, supprimez la virgule :

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## Débogage des erreurs en phase d'exécution
{: #debugging-runtime-errors}
Si vous rencontrez des erreurs avec votre application en phase d'exécution, les journaux d'application peuvent vous aider à isoler la cause de l'erreur et à corriger le problème.

La journalisation vers stdout (sortie standard) et stderr (erreur standard) peut être activée. Pour plus d'informations sur la manière de configurer les fichiers journaux pour des applications déployées à l'aide du pack de construction intégré {{site.data.keyword.Bluemix_notm}}, consultez la liste ci-après :

  * Pour les applications Liberty for Java™, voir [Liberty : journalisation et trace ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/rwlp_logging.html){: new_window}.
  * Pour les applications Node.js, voir [Node.js debugging starts with better logging! ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/blogs/bluemix/2015/03/node-js-better-logging/){: new_window}.
  * Pour les applications PHP, voir [error_log ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](http://php.net/manual/en/function.error-log.php){: new_window}.
  * Pour les applications Python, voir [Logging HOWTO ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://docs.python.org/2/howto/logging.html){: new_window}.
  * Pour les applications Ruby on Rails, voir [The Logger ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}.
  * Pour les applications Ruby Sinatra, voir [Logging ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](http://www.sinatrarb.com/intro.html#Logging){: new_window}.

Lorsque vous entrez la commande `cf logs nom_application --recent` dans l'interface de ligne de commande Cloud Foundry, seuls les journaux les plus récents sont affichés. Pour accéder aux erreurs précédentes, vous devez extraire tous les journaux. Pour ce faire, utilisez l'une des méthodes suivantes :
<dl>
<dt><strong>{{site.data.keyword.loganalysisshort}}</strong></dt>
<dd>Les fonctionnalités intégrées de recherche et d'analyse de fichier journal du service {{site.data.keyword.loganalysisshort}} permettent d'identifier rapidement les erreurs. Pour plus d'informations, voir
<a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">{{site.data.keyword.loganalysisfull}}</a>.</dd>
<dt><strong>Outils tiers </strong></dt>
<dd>Vous pouvez collecter et exporter les journaux de votre application sur un hôte de journaux externe. Pour plus d'informations, voir
<a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">Configuration d'hôtes de journaux externes</a>.</dd>
<dt><strong>Scripts pour collecter et exporter les journaux  </strong></dt>
<dd>Pour utiliser un script permettant de collecter et d'exporter automatiquement les journaux vers un fichier externe, vous devez vous connecter à la
console {{site.data.keyword.Bluemix_notm}} depuis votre ordinateur et disposer de suffisamment d'espace pour télécharger les journaux. Pour plus d'informations, voir <a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">Collecte d'informations de diagnostic</a>. </dd>
</dl>

Auparavant, les fichiers `stdout.log` et `stderr.log` étaient accessibles par défaut via la vue d'application dans la console {{site.data.keyword.Bluemix_notm}} sous **Fichiers** > **journaux**. Toutefois, cette journalisation d'application n'est plus disponible dans la version en cours de Cloud Foundry, où {{site.data.keyword.Bluemix_notm}} est hébergé. Pour pouvoir continuer à accéder aux journaux stdout et stderr de l'application via la console {{site.data.keyword.Bluemix_notm}} sous **Fichiers** > **journaux**, vous pouvez rediriger la sortie de journal vers d'autres fichiers dans le système de fichiers {{site.data.keyword.Bluemix_notm}}, en fonction de votre environnement d'exécution.

  * Pour les applications Liberty for Java, la sortie dirigée aux fichiers stdout et stderr est déjà intégrée dans le fichier `messages.log` sous le répertoire 'logs'. Recherchez les entrées portant le préfixe SystemOut et SystemErr.
  * Pour les applications Node.js, vous pouvez redéfinir la fonction console.log afin de consigner explicitement la sortie journal dans un fichier sous le répertoire 'logs'.
  * Pour les applications PHP, vous pouvez utiliser la fonction error_log pour consigner la sortie journal dans un fichier sous le répertoire 'logs'.
  * Pour les applications Python, vous pouvez indiquer au consignateur d'utiliser un fichier situé sous le répertoire 'logs' : `logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * Pour les applications Ruby, vous pouvez indiquer au consignateur d'utiliser un fichier situé sous le répertoire 'logs'.


### Débogage des modifications du code
{: #debug_code_changes}

Si vous apportez des modifications au code d'une application déjà déployée et en opération, mais que ces modifications ne sont pas encore reflétées dans {{site.data.keyword.Bluemix_notm}}, vous pouvez déboguer l'application à l'aide des journaux. Que votre application soit en
exécution ou non, vous pouvez examiner les journaux générés lors du déploiement de l'application ou en phase d'exécution afin de déterminer pourquoi le nouveau code
ne fonctionne pas.

Selon la manière dont le nouveau code est déployé, choisissez l'une des méthodes suivantes pour déboguer les modifications du code :

  * Si vous avez déployé un nouveau code depuis la ligne de commande cf, vérifiez la sortie de la commande *cf push*. Par ailleurs, vous pouvez utiliser la commande *cf logs* pour plus d'indices sur la manière de résoudre le problème. Pour plus d'informations sur l'utilisation de la commande *cf logs*, voir [Affichage des journaux dans l'interface de ligne de commande](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs).

  * Dans le cas d'un nouveau code déployé depuis une interface graphique telle que la console {{site.data.keyword.Bluemix_notm}}, DevOps Delivery Pipeline ou Travis-CI, vous pouvez examiner les journaux depuis l'interface. Par exemple, si vous déployez le nouveau code depuis
la console {{site.data.keyword.Bluemix_notm}}, vous pouvez accéder au tableau de bord, rechercher votre application, puis afficher
tous les journaux pour repérer des indices.   Pour plus d'informations sur l'affichage des journaux depuis la console {{site.data.keyword.Bluemix_notm}}, voir [Affichage des journaux depuis le tableau de bord {{site.data.keyword.Bluemix}}](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana).
