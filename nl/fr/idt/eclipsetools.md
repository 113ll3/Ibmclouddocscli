---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Déploiement d'applications à l'aide d'IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} fournit des plug-in qui peuvent être installés dans un environnement Eclipse existant pour faciliter l'intégration de l'environnement de développement intégré (IDE) à Bluemix®. Les outils vous permettent de déployer vos fichiers JavaScript, WAR (archive Web) et EAR (archive d'entreprise), ainsi que les packages de serveur Liberty Profile sur le serveur Cloud directement à partir de votre environnement IDE Eclipse ou de WDT (WebSphere® Application Server Developer Tools). Ils vous permettent également de créer et de lier des services à votre application, ainsi que de définir des variables d'environnements dans le cadre du déploiement.

Si votre application est déjà en cours d'exécution dans Eclipse à l'aide de Websphere Application Developer Tools avec Liberty Profile, vous pouvez installer ces outils par dessus le programme en cours d'exécution. Vous pouvez déployer vos applications en les ajoutant au serveur Cloud dans le plan de travail. Grâce aux fonctions uniques du pack de construction Liberty pour la prise en charge du package de serveur, vous avez la possibilité de déployer la totalité du serveur Liberty Profile sur le cloud. Vous pouvez également déployer les applications JavaScript Node.js sur le cloud. 

## Installation des outils Eclipse Tools

Apprenez comment installer IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Un environnement d'exécution Java™ 1.7 ou de niveau ultérieur est requis. 

Il existe plusieurs méthodes pour installer IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, notamment :
* Installation depuis le Marketplace
* Installation depuis WASDev
* Téléchargement depuis le programme d'installation de WDT (IBM WebSphere Application Server Developer Tools)

### Installation depuis le Marketplace

L'installation requiert [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) ou [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers).

Ensuite, exécutez les instructions décrites ici : [https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Installation depuis WASDev

1. Ouvrez la page de [téléchargement](https://developer.ibm.com/wasdev/downloads/) dans WASDev.
2. Faites glisser l'icône d'`installation` vers la barre d'outils dans Eclipse.
3. Par défaut, des fonctions sont déjà sélectionnées. Cliquez sur **Confirm**.
4. Acceptez le contrat de licence et cliquez sur **Finish**.

### Téléchargement depuis le programme d'installation de WDT (IBM WebSphere Application Server Developer Tools)

1. Ouvrez **Help > Install WebSphere Software**. Effectuez une recherche sur le terme Cloud.
2. Sélectionnez l'entrée `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` et cliquez sur **Install**.
3. Par défaut, des fonctions sont déjà sélectionnées. Cliquez sur **Confirm**.
4. Acceptez le contrat de licence et cliquez sur **Finish**.

## Prise en charge d'un package de serveur

Avec IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, plusieurs scénarios permettent d'envoyer par commande push un serveur Liberty ou un package de serveur au cloud et de confirmer le déploiement. 

* Créez le serveur Cloud. 
* Créez un serveur Liberty Profile à l'aide d'un fichier WAR ou EAR.
* Arrêtez le serveur.

Avec IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} pour la prise en charge de package de serveur, plusieurs scénarios permettent d'effectuer les actions suivantes :

* L'envoi par commande push d'un serveur Liberty au cloud.
* L'envoi par commande push d'un package de serveur Liberty au cloud.
* La vérification de la réussite du déploiement par le biais de tests.

De plus, vous pouvez importer des fichiers compressés contenant des packages de serveur dans n'importe quel projet de votre espace de travail. 

### Scénario 1 - Ajout d'un serveur Liberty arrêté au Cloud et test d'une application

1. Cliquez avec le bouton droit de la souris sur le serveur `Cloud` dans la vue Servers. 
2. Sélectionnez **Add and Remove**.
3. Dans la boîte de dialogue, les instances de serveur Liberty s'affichent. Sélectionnez-en une et cliquez sur **Add**.
4. Cliquez sur **Finish**.
5. Dans la boîte de dialogue Application, le nom par défaut est dérivé de l'instance de serveur Liberty. Vous pouvez modifier ce nom, mais il ne doit pas comporter d'espaces ou de caractères spéciaux. La valeur par défaut est acceptable si elle n'entre pas en conflit avec le nom des applications existantes dans le serveur Cloud. 
6. Cliquez sur **Finish** et attendez que l'application soit publiée sur le cloud.
7. Cliquez avec le bouton droit de la souris sur le module Liberty Server ajouté sous le serveur Cloud. Sélectionnez **Open Home Page**. L'URL racine de package de serveur s'ouvre dans votre navigateur Web par défaut. Utilisez cette URL racine pour construire l'URL de test des packages d'application WAR et EAR.

### Scénario 2 - Exécution d'une fonction de glisser-déposer pour un serveur Liberty arrêté vers le cloud

Le scénario 1 décrivait comment vous pouvez ajouter et supprimer des modules Liberty Server. Cette opération peut être simplifiée par une fonction de glisser-déposer.

1. Si vous poursuivez à partir du scénario 1, retirez le module Liberty Server du serveur Cloud. 
2. Sélectionnez et faites glisser l'instance de serveur Liberty arrêtée et déposez-la dans le serveur Cloud dans la vue Servers. La fenêtre Application Dialogue s'affiche.
3. Suivez les étapes 5 à 10 du scénario 1.

### Scénario 3 - Exécution d'un package de serveur sur le cloud

Le menu contextuel de l'instance de service Liberty Profile inclut une action Package Server. Cette action crée un package du serveur dans un fichier archive. Dans le cloud, une nouvelle action a été ajoutée pour créer un package du serveur dans un fichier compressé et le déployer dans Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

1. Si vous poursuivez à partir du scénario 1 ou 2, retirez le module de serveur Liberty du serveur Cloud. 
2. Cliquez avec le bouton droit de la souris sur l'instance de serveur Liberty Profile dans la vue Servers.
3. Sous le menu Utilities, sélectionnez **Package Server to {{site.data.keyword.Bluemix_notm}}**.
4. Dans la boîte de dialogue, choisissez le serveur Cloud sur lequel vous souhaitez déployer l'application.
5. Cliquez sur **OK**. La fenêtre Application Dialogue s'affiche.
6. Suivez les étapes 5 à 10 du scénario 1.
7. Si une boîte de dialogue de progression s'affiche, sélectionnez **Run
in background** et patientez jusqu'à ce que l'application soit déployée.

### Scénario 4 - Utilisation de fichiers compressés contenant des packages de serveur - Exécution sur le serveur

Les scénarios précédents décrivent comment gérer les instances Liberty répertoriées dans la vue Servers et comment les déployer sur le cloud. Vous pouvez également déployer sur le cloud des fichiers compressés existants contenant des packages de serveur. 

1. Créez ou procurez-vous un fichier compressé de package de serveur.
2. Importez le fichier compressé dans le projet de votre choix dans l'espace de travail.
3. Cliquez avec le bouton droit de la souris sur le fichier compressé et sélectionnez **Run As > Run on Server**. La boîte de dialogue Run On Server s'affiche.
4. Sélectionnez un serveur Cloud. 
5. Cliquez sur **Finish**. La fenêtre Application Dialogue s'affiche.
6. Suivez les étapes 5 à 10 du scénario 1. Le nom du module est dérivé du fichier compressé.

### Scénario 5 - Utilisation de fichiers compressés contenant des packages de serveur - Fonction glisser-déposer

1. Sélectionnez et faites glisser le fichier compressé contenant un package de serveur et déposez-le dans le serveur Cloud dans la vue Servers. La fenêtre Application Dialogue s'affiche.
2. Suivez les étapes 5 à 10 du scénario 1. Le nom du module est dérivé de celui du fichier compressé.

## Envoi d'un fichier EAR par commande push

Utilisez IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} pour envoyer par commande push un fichier EAR sur le cloud. 

Définissez un nouveau serveur.

1. Pour créer un nouveau serveur Cloud, sélectionnez **File > New > Other**.
2. Sélectionnez **Server** dans la catégorie Server, puis cliquez sur **Next**.
3. Sous IBM, recherchez Cloud.
4. Cliquez sur **Next**.
5. Entrez les informations relatives à votre compte Cloud. Cliquez sur **Sign Up** si vous ne disposez pas encore d'un compte.
6. Cliquez sur **Next**.
7. Sélectionnez vos organisations et espaces. La valeur par défaut est `dev`.
8. Cliquez sur **Next**.
9. Cliquez sur **Finish**.

Importez un fichier EAR

1. Cliquez à l'aide du bouton droit de la souris, puis sélectionnez **Import**.
2. Recherchez le fichier EAR.
3. Recherchez le fichier EAR que vous désirez importer.
4. Assurez-vous que le contexte d'exécution cible a pour valeur {{site.data.keyword.Bluemix_notm}} Runtime.

Déployez votre application.

1. Cliquez avec le bouton droit de la souris sur le serveur Cloud. Sélectionnez **Add and Remove**.
2. Choisissez le fichier EAR, puis cliquez sur **Add**.
3. Cliquez sur **Finish**. La fenêtre Application Details s'affiche.
4. Attribuez un nom à l'application, puis cliquez sur **Next**. Un nom valide peut comporter les caractères A-Z, 0-9, -, et _. Il ne doit pas contenir d'espaces, ni d'autres caractères spéciaux. Les informations Launch Deployment sont définies par défaut. 
5. Cliquez sur **Next**.
6. Si nécessaire, sélectionnez des services. Cliquez sur **Next**.
7. Si nécessaire, ajoutez des variables. Cliquez sur **Finish**.
8. Une fois l'application propagée, cliquez avec le bouton droit de la souris sur le projet et sélectionnez **Open Home Page**.
9. Ajoutez le nom du module Web et le nom de l'application dans l'URL.
10. Pour sauvegarder les paramètres et les variables que vous avez indiqués,
cochez la case **Save to the manifest file** de la fenêtre Application details.

## Déploiement d'une application Node.js
Utilisez IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} pour déployer un projet Node.js nouveau ou existant dans le cloud, définir les caractéristiques du déploiement d'application et vérifier les résultats dans un navigateur. 

Si vous ne possédez pas encore d'application Node.js, commencez à l'étape 1. Si vous possédez déjà une application Node.js, commencez à l'étape 7. 

1. Sélectionnez **File > New > Project**.
2. Sélectionnez **JavaScript project** dans la catégorie JavaScript. 
3. Cliquez sur **Next**.
4. Attribuez un nom au projet.
5. Cliquez sur **Finish**.

Définissez un nouveau serveur.

1. Pour créer un nouveau serveur Cloud, sélectionnez **File > New > Other**.
2. Sélectionnez **Server** dans la catégorie Server, puis cliquez sur **Next**.
3. Sous IBM, recherchez Cloud.
4. Cliquez sur **Next**.
5. Entrez les informations relatives à votre compte Cloud. Cliquez sur **Sign Up** si vous ne disposez pas encore d'un compte.
6. Cliquez sur **Next**.
7. Sélectionnez vos organisations et espaces. La valeur par défaut est `dev`.
8. Cliquez sur **Next**.
9. Cliquez sur **Finish**.

Activez l'application pour la publication sur le cloud

1. Cliquez avec le bouton droit de la souris sur le projet dans l'explorateur de projets et choisissez **Properties > Project Facet**.
2. Cliquez sur **Convert to faceted form**.
3. Sous Project Facets, sélectionnez **Node.js Application**.
4. Cliquez sur **OK**. 

Déployez votre application.

1. Cliquez avec le bouton droit de la souris sur le serveur Cloud. Sélectionnez **Add and Remove**.
2. Choisissez le projet, puis cliquez sur **Add**.
3. Cliquez sur **Finish**. La fenêtre Application Details s'affiche.
4. Pour sauvegarder la configuration de déploiement dans le fichier manifeste d'application, cochez la case **Save to the manifest file** dans la fenêtre Application details.
5. Attribuez un nom à l'application, puis cliquez sur **Next**. Un nom valide peut comporter les caractères A-Z, 0-9, -, et _. Il ne doit pas contenir d'espaces, ni d'autres caractères spéciaux.
6. Acceptez les valeurs par défaut sur le panneau d'informations Launch Deployment. 
7. Cliquez sur **Next**.
8. Si nécessaire, sélectionnez des services. Cliquez sur **Next**.
9. Si nécessaire, ajoutez des variables. Cliquez sur **Finish**.
10. Une fois l'application propagée, cliquez avec le bouton droit de la souris sur le projet et sélectionnez **Open Home Page**.

## Publication incrémentielle

Vous pouvez mettre à jour les fichiers de l'application de manière
incrémentielle sans avoir à renvoyer la totalité de l'application par commande
push.
Une publication incrémentielle vous évite d'effectuer un redéploiement
complet pour chaque modification, ce qui vous fait gagner du temps au cours du
développement.

Cette fonction prend en charge les applications Web (WAR et EAR), ainsi que les packages de serveur. 

L'utilisation de la publication incrémentielle nécessite d'activer le [mode développement](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) pour l'application ou le package de serveur. 

1. Ajoutez une application ou un package de serveur au serveur cloud, sauf s'ils figurent déjà sur le serveur.
**Remarque :** cette fonction ne peut pas être activée si le nom de déploiement d'application comporte un trait de soulignement. 

2. Pour activer le mode développement, cliquez avec le bouton droit de la souris sur l'application ou le package de serveur et sélectionnez **Enable Development Mode**.

Une fois le mode développement activé, utilisez la fonction de
publication incrémentielle :

1. Modifiez l'application comme vous le souhaitez.
   **Remarque :** pour les packages de serveur, il n'est pas possible de modifier la configuration. 

2. Sauvegardez les modifications.

3. Cliquez avec le bouton droit sur le serveur de cloud et sélectionnez **Publish**.

Modes mis en cache : après que vous avez redémarré le plan de travail, si l'application était en mode développement ou en mode débogage, une fenêtre de progression s'affiche avec le texte "Retrieving development and debug states". Une fois la progression terminée, le mode développement et le mode débogage sont régénérés. 

## Débogage à distance

Exécutez le débogage à distance sur une application Liberty ou Node.js. 

L'exécution du débogage nécessite que le [mode développement](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) soit activé. Ce mode s'exécute automatiquement lorsque vous sélectionnez Enable
Application Debug.

### Activation du débogage d'EAR, de WAR ou de Liberty Server

Actuellement, un port local gratuit est généré de façon aléatoire, mais s'il est bloqué par un pare-feu client, le scénario de débogage échoue. Pour contourner ce problème, démarrez le mode développement, localisez le fichier bluemixcache.xml et ajoutez port="#", où # correspond au numéro de port de la machine locale. 

1. Sous le serveur Cloud, cliquez avec le bouton droit de la souris sur l'application que vous souhaitez déboguer. 

   **Remarque :** cette fonction ne peut pas être activée si le nom de déploiement d'application comporte un trait de soulignement. Modifiez le nom avant d'activer le débogage à distance.

2. Cliquez sur **Enable Application Debug**.

   La vue de progression affiche le statut `Establishing debug session for <AppName>``.

   L'application affiche le statut `Developing, Debugging <AppName>`.

   Le débogueur est en cours d'exécution et prêt à être utilisé. 

### Désactivation du débogage d'EAR, de WAR ou de Liberty Server

Vous pouvez désactiver le processus de débogage et laisser le mode développement activé. 

1. Cliquez sur l'application avec le bouton droit de la souris.
2. Cliquez sur **Disable Application Debug**.
3. Une boîte de dialogue vous demande si vous souhaitez également désactiver le mode développement. Cliquez sur **Yes** ou **No**.

Si le mode développement est toujours en cours d'exécution, l'application affiche le statut `Developing <AppName>``.

 Si les deux modes sont désactivés, l'application affiche le statut `Deployed as <AppName>`.

### Activation du débogage des applications Node.js

**Remarque :** Avant de continuer, vérifiez qu'une application JavaScript est déployée sur le serveur cloud. Pour plus d'informations sur le déploiement d'une application JavaScript, voir les étapes précédentes. 

1. Dans la vue Servers, cliquez avec le bouton droit de la souris sur l'application Node.js et sélectionnez **Open** JavaScript Debugger. Une boîte de dialogue s'affiche et vous demande si vous souhaitez augmenter la limite de mémoire de l'application.
2. Cliquez sur Yes. L'activation du débogage JavaScript augmente les exigences en matière de mémoire d'application, et l'application redémarre plus rapidement avec la limite de mémoire mise à jour. 
3. Sélectionnez une installation de navigateur à utiliser pour le débogage. Google Chrome est le seul navigateur pris en charge. Si l'option Google Chrome n'est pas disponible, sélectionnez le lien **Manage...** et ajoutez un lien vers l'installation Google Chrome locale. 
4. Cliquez sur **OK**. Un moniteur de progression s'affiche avec le texte Updating (your app) to debug mode. Une fois le mode débogage activé, Google Chrome s'ouvre sur le site approprié. 
5. Authentifiez-vous dans Google Chrome avec votre nom de connexion et le mot de passe correspondant. Une fois l'authentification réussie, la console de débogage s'affiche. Vous pouvez à présent déboguer l'application.

Modes mis en cache : après que vous avez redémarré le plan de travail, si l'application était en mode développement ou en mode débogage, une fenêtre de progression s'affiche avec le texte Retrieving development and debug states. Une fois la progression terminée, le mode développement et le mode débogage sont régénérés. 

## Connexion à un serveur Liberty distant

Apprenez comment utiliser IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} pour vous connecter à un serveur Liberty distant. Vous pouvez vous connecter à un serveur Liberty distant qui exécute WebSphere Application Server en tant que service.

Pour vous connecter à un serveur liberty distant, vous devez installer Liberty Tools. Vous devez également créer un service WebSphere Application Server sur le cloud. 

1. Cliquez avec le bouton droit de la souris sur votre serveur Cloud et sélectionnez **Configure remote servers...**.

   Cette option n'est disponible que si Liberty Tools est installé. 

2. Sélectionnez un service WebSphere Application Server. 

   Si vous ne disposez pas de service WebSphere Application Server, il se peut qu'un message d'erreur soit généré. Vous devez créer un service WebSphere Application Server sur le serveur Cloud avant de pouvoir effectuer cette configuration. 

3. Pour définir un environnement d'exécution, sélectionnez **Configure runtime environments...**.

   **Remarque :** si vous avez déjà créé un environnement d'exécution, vous pouvez ignorer cette étape.

4. Cliquez sur **Next**.

5. Entrez les informations relatives à la connexion serveur. 

6. Cliquez sur **Finish**.

Vous vous êtes connecté à un serveur Liberty distant à l'aide d'IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

## Activation de Cloud Foundry Diego sur des applications en cloud

Activez la fonction d'architecture Diego à partir d'IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Pour activer Diego, vous devez disposer d'un serveur Cloud qui est défini dans la vue Servers. 

Diego est une nouvelle architecture Cloud Foundry que les instances Cloud Foundry utilisent pour gérer des conteneurs d'application en cours d'exécution. L'architecture Diego remplace l'architecture Droplet Execution Agents (DEA) auparavant utilisée par Cloud Foundry. Les installations Cloud Foundry vont être transférées vers Diego, et les applications utilisateur vont basculer vers la nouvelle architecture automatiquement et en toute transparence. 

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} prend en charge Diego et DEA. Vous pouvez publier des applications, activer la publication d'application incrémentielle et déboguer des applications. Diego permet également à IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} de créer des tunnels Secure Shell (SSH) dans des applications en cloud déployées, afin d'établir des connexions plus rapides et plus fiables vers les applications en cloud pendant le débogage. Vous pouvez également activer SSH de manière à pouvoir créer vos propres tunnels pour accéder à des ressources d'application. 

Procédez comme suit afin d'utiliser l'architecture Diego pour vos applications avant que le cloud ne commence à utiliser Diego par défaut pour le déploiement : 

1. Cliquez avec le bouton droit de la souris sur l'application déployée dans la vue Servers.
2. Si Diego est pris en charge sur votre serveur Cloud et que votre application n'est pas encore déployée à l'aide de Diego, sélectionnez **Enable Diego** dans le menu. 
3. Si le serveur prend en charge la tunnellisation, le programme vous demande si vous souhaitez activer SSH pour votre application. Les tunnels SSH constituent un mécanisme plus fiable pour communiquer avec votre application. Toutefois, si vous sélectionnez **No**, les fonctions dans IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} continuent de fonctionner à l'aide d'un mécanisme qui ne requiert pas la tunnelisation SSH. 

L'application est redéployée à l'aide de l'architecture Diego.

## Création d'un serveur à l'aide de Cloud Enterprise Federation

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} prend en charge Cloud Enterprise Federation, un service de connexion unique qui permet aux utilisateurs d'accéder en toute sécurité à des services cloud. Grâce à Cloud Enterprise Federation, vous pouvez activer une authentification tierce personnalisée qui est fournie par votre propre organisation, sans l'authentification de connexion standard, afin de permettre à d'autres utilisateurs de pouvoir accéder aux applications en toute sécurité. 

Cloud Enterprise Federation authentifie un ensemble d'utilisateurs pour accéder à des services de cloud. Après que vous avez activé Cloud Enterprise Federation, vos utilisateurs reçoivent l'authentification pour les applications optimisées par le cloud via l'option de connexion unique. Les utilisateurs doivent sélectionner l'option de connexion unique pour créer un serveur dans le plan de travail Eclipse et se connecter à l'aide du nom et du mot de passe de connexion de l'organisation. Après que vous avez activé Cloud Enterprise Federation, l'ID et le mot de passe utilisateur IBM Cloud traditionnels dans Eclipse Tools ne sont plus utilisés pour authentifier les utilisateurs. 

1. Dans IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, sélectionnez **File > New > Other...**.
2. Sélectionnez **Server > Server > Next**.
3. Dans l'arborescence, sélectionnez **IBM > {{site.data.keyword.Bluemix_notm}} > Next**.
4. Cochez la case **Use a one-time password to log in (SSO)**.
5. Un lien hypertexte apparaît dans la boîte de dialogue de connexion. Cliquez sur ce lien hypertexte pour ouvrir la page d'authentification au cloud. 
6. Entrez votre adresse électronique et le mot de passe souhaité. 
7. Une fois que vous vous êtes connecté, vous recevez un code d'accès à usage unique. Copiez ce code d'accès dans la zone Passcode de la boîte de dialogue Eclipse Tools for Cloud New Server. 
8. Cliquez sur **Finish**.

Une entrée de serveur Cloud apparaît dans la vue Servers avec le statut de serveur Connected. 
