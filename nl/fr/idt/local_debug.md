---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-29"

keywords: cli, local app debug, java debug, node debug, debug, cli debug, local cli, ibmcloud dev, dev debug

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Débogage d'application locale pour l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}
{: #local-debug}

Il existe des outils vous permettant de déboguer votre application Java et Node.js dans {{site.data.keyword.cloud_notm}}.

## Débogage d'une application Java
{: #java}

Etapes permettant d'activer l'outil de débogage pour une application Java :

1. Depuis le répertoire racine de votre projet d'application, exécutez la commande suivante :

  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. Connectez le débogueur à votre application :

	* Eclipse
      1. Importez le **projet maven existant** dans Eclipse.
      2. Créez une configuration de débogage d'[application distante Java ](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").
      		1. Entrez l'adresse IP ou `localhost:<port>`  
      		2. Entrez `7777` comme numéro de port.
      		3. Spécifiez le nom du projet que vous avez importé.
      6. Définissez un point d'arrêt dans l'environnement de développement intégré.
      7. Exécutez la configuration de débogage.
      8. Accédez au noeud final avec un navigateur pour recréer le problème.  
	   
	   Le port par défaut est `9080` pour le noeud final de base Microservices Java.
	   {: note}

	* [IntelliJ ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
	* [VSCode ](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
	* Ligne de commande du kit JDK : `jdb -attach <host:port>`

## Débogage d'une application Node.js
{: #idt-node-debug}

Etapes permettant d'activer l'outil de débogage pour une application Node.js :

1. Depuis le répertoire racine de votre projet d'application, exécutez la commande suivante :
  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. Connectez le débogueur à votre application :
	* [VSCode ](https://blog.docker.com/2016/07/live-debugging-docker/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
	* [WebStorm ](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")


<!--
## Swift application debugging - content from mike tunnicliffe
{: #swift}

Steps to enable debug for a Swift application:  

1. On the App server (or system where the Swift application will execute), you should start the 'lldb server':
 - `lldb-server platform -->
<!-- listen <port number>`
2. On the App server, build the Kitura-based server application using the debug configuration:
 - `swift build debug`
3. On the App server, start the Kitura-based server application:
 - `./build/debug/Kitura-Starter`
4. On the client system (also known as the host system), start the 'lldb client':
 - `lldb`
5. Configure lldb client to connect to lldb-server:
 - `(lldb) platform select remote-linux`
 - `(lldb) platform connect connect://<ip address server>:<port number server>`
6. Execute commands to debug remote program:
 - `(lldb) process attach -->
<!--pid 3626`
-->
