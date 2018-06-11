---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-23"


---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Débogage d'une application locale
{: #local-debug}

Il existe des outils vous permettant de déboguer votre application en Java et Node.js dans {{site.data.keyword.cloud_notm}}.

## Débogage d'une application Java
{: #java}

Etapes permettant d'activer l'outil de débogage pour une application Java :

1. Depuis le répertoire principal de votre projet d'application, exécutez la commande suivante :

```
ibmcloud dev debug
```

2. Connectez le débogueur à votre application :

	* Eclipse
      1. Importez le **projet maven existant** dans Eclipse.
      2. Créez une configuration de débogage d'[application distante Java ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm).
      		1. Entrez l'adresse IP ou `localhost:<port>`  
      		2. Entrez `7777` comme numéro de port.
      		3. Spécifiez le nom du projet java que vous avez importé.
      6. Définissez un point d'arrêt dans l'environnement de développement intégré.
      7. Exécutez la configuration de débogage.
      8. Accédez au noeud final avec un navigateur pour recréer le problème.  
	   **Remarque** : le port par défaut est 9080 pour le noeud final de base Microservices Java.
	* [IntelliJ ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html)
	* [VSCode ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger)
	* Ligne de commande du kit JDK : `jdb -attach <host:port>`

## Débogage d'une application Node.js
{: #node}

Etapes permettant d'activer l'outil de débogage pour une application Node.js :

1. Depuis le répertoire racine de vos projets d'application, exécutez la commande suivante :

```
ibmcloud dev debug
```

2. Connectez le débogueur à votre application :
	* [VSCode ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://blog.docker.com/2016/07/live-debugging-docker/)
	* [WebStorm ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/)


<!--
## Swift application debugging - content from mike tunnicliffe
{: #swift}

Steps to enable debug for a Swift application:  

1. On the App server (or system where the Swift application will run), you must start the 'lldb server':
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
