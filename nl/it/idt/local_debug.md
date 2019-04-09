---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-30"


---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Debug dell'applicazione locale per la CLI {{site.data.keyword.dev_cli_notm}}
{: #local-debug}

Esistono degli strumenti per aiutarti ad eseguire il debug della tua applicazione in Java e Node.js in {{site.data.keyword.cloud_notm}}.

## Debug dell'applicazione Java
{: #java}

Procedura per abilitare lo strumento di debug per un'applicazione Java:

1. Dalla directory root del tuo progetto dell'applicazione esegui il seguente comando:

```
ibmcloud dev debug
```

2. Collegamento del programma di debug alla tua applicazione:

	* Eclipse
      1. Importa il progetto **Existing maven project** in Eclipse.
      2. Crea una configurazione di debug dell'[applicazione remota Java ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm).
      		1. Immetti l'indirizzo IP o il `localhost<port>`  
      		2. Immetti `7777` per il numero di porta.
      		3. Specifica il nome del progetto java che hai importato.
      6. Imposta un punto di interruzione nell'IDE.
      7. Esegui la configurazione di debug.
      8. Accedi all'endpoint con un browser per ricreare il problema.  
	   
	   La porta predefinita è 9080 per l'endpoint dei microservizi di base Java.
	   {: note}

	* [IntelliJ ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html)
	* [VSCode ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger)
	* Riga di comando JDK: `jdb -attach <host:port>`

## Debug dell'applicazione Node.js
{: #node}

Procedura per abilitare lo strumento di debug per un'applicazione Node.js:

1. Dalla tua directory root del progetto dell'applicazione esegui il seguente comando:

```
ibmcloud dev debug
```

2. Collegamento del programma di debug alla tua applicazione:
	* [VSCode ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://blog.docker.com/2016/07/live-debugging-docker/)
	* [WebStorm ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/)


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
