---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-27"

keywords: local app debug, java debug, node debug, debug, cli debug, local cli, ibmcloud dev, dev debug

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Lokales Anwendungsdebugging für die {{site.data.keyword.dev_cli_notm}}-CLI
{: #local-debug}

Es gibt Tools zur Unterstützung des Debugging Ihrer Anwendung in Java und Node.js in {{site.data.keyword.cloud_notm}}.

## Java-Anwendungsdebugging
{: #java}

Schritte zum Aktivieren des Debugging-Tools für eine Java-Anwendung:

1. Führen Sie den folgenden Befehl im Stammverzeichnis Ihres Anwendungsprojekts aus:

  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. Verbinden Sie den Debugger mit Ihrer Anwendung:

	* Eclipse
      1. Importieren Sie das **vorhandene Maven-Projekt** in Eclipse.
      2. Erstellen Sie eine Debugkonfiguration für die [ferne Java-Anwendung ](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link").
      		1. Geben Sie die IP-Adresse oder `localhost:<port>`  
      		2. Geben Sie als Portnummer `7777` ein.
      		3. Geben Sie den Namen des Java-Projekts an, das Sie importiert haben.
      6. Legen Sie einen Unterbrechungspunkt in der IDE fest.
      7. Führen Sie die Debugkonfiguration aus.
      8. Greifen Sie mit einem Browser auf den Endpunkt zu, um das Problem erneut zu erstellen.  
	   
	   Der Standardport für den grundlegenden Mikroservices-Endpunkt in Java ist '9080'.
	   {: note}

	* [IntelliJ ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
	* [VSCode ](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
	* JDK-Befehlszeile: `jdb -attach <host:port>`

## Node.js-Anwendungsdebugging
{: #idt-node-debug}

Schritte zum Aktivieren des Debugging-Tools für eine Node.js-Anwendung:

1. Führen Sie den folgenden Befehl im Stammverzeichnis Ihres Anwendungsprojekts aus:
  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. Verbinden Sie den Debugger mit Ihrer Anwendung:
	* [VSCode ](https://blog.docker.com/2016/07/live-debugging-docker/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
	* [WebStorm ](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")


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
