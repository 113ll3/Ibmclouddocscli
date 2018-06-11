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

# Lokales Anwendungsdebugging
{: #local-debug}

Es gibt Tools zur Unterstützung des Debugging Ihrer Anwendung in Java und Node.js in {{site.data.keyword.cloud_notm}}.

## Java-Anwendungsdebugging
{: #java}

Schritte zum Aktivieren des Debugging-Tools für eine Java-Anwendung:

1. Führen Sie im Stammverzeichnis Ihres Anwendungsprojekts den folgenden Befehl aus:

```
ibmcloud dev debug
```

2. Verbinden Sie den Debugger mit Ihrer Anwendung:

	* Eclipse
      1. Importieren Sie das **vorhandene Maven-Projekt** in Eclipse.
      2. Erstellen Sie eine Debugkonfiguration für die [ferne Java-Anwendung ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm).
      		1. Geben Sie die IP-Adresse oder `localhost:<port>`  
      		2. Geben Sie als Portnummer `7777` ein.
      		3. Geben Sie den Namen des importierten Java-Projekts an.
      6. Legen Sie einen Unterbrechungspunkt in der IDE fest.
      7. Führen Sie die Debugkonfiguration aus.
      8. Greifen Sie über einen Browser auf den Endpunkt zu, um das Problem zu reproduzieren.  
	   **Hinweis**: Der Standardport für den grundlegenden Mikroservices-Endpunkt in Java ist '9080'.
	* [IntelliJ ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html)
	* [VSCode ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger)
	* JDK-Befehlszeile: `jdb -attach <host:port>`

## Node.js-Anwendungsdebugging
{: #node}

Schritte zum Aktivieren des Debugging-Tools für eine Node.js-Anwendung:

1. Führen Sie im Stammverzeichnis des Anwendungsprojekts den folgenden Befehl aus:

```
ibmcloud dev debug
```

2. Verbinden Sie den Debugger mit Ihrer Anwendung:
	* [VSCode ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://blog.docker.com/2016/07/live-debugging-docker/)
	* [WebStorm ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/)


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
