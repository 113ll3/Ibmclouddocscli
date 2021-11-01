---

copyright:
  years: 2017, 2021
lastupdated: "2021-10-05"

keywords: cli, local app debug, java debug, node debug, debug, cli debug, local cli, ibmcloud dev, dev debug

subcollection: cli

---


{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}
{:external: target="_blank" .external}

# Local app debugging for the {{site.data.keyword.dev_cli_notm}} commands
{: #local-debug}

In the {{site.data.keyword.cloud}} Command Line Interface, tools are provided to help you debug your application in Java&trade; and Node.js in {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## Java app debugging
{: #java}

Steps to enable the debugging tool for a Java&trade; app:

1. From the root directory of your app project, run the following command:

   ```text
   ibmcloud dev debug
   ```
   {: codeblock}

2. Connecting the debugger to your app:

	* Eclipse
      1. Import the **Existing maven project** into Eclipse.
      1. Create a [Java&trade; remote app](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: external} debug configuration.
         1. Enter the IP address or `localhost:<port>`  
         2. Enter `7777` for port number.
         3. Specify the name of the project that you imported.
      1. Set a breakpoint in the IDE.
      1. Run the debug configuration.
      1. Access the endpoint with a browser to re-create the issue.  
	   
	   The default port is `9080` for the Java&trade; basic Microservices endpoint.
	   {: note}

	* [IntelliJ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: external}
	* [VSCode](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: external}
	* JDK command line: `jdb -attach <host:port>`

## Node.js app debugging
{: #idt-node-debug}

Steps to enable the debugging tool for a Node.js app:

1. From your app project's root directory, run the following command:
   ```text
   ibmcloud dev debug
   ```
   {: codeblock}

2. Connecting the debugger to your app:
	* [VSCode](https://blog.docker.com/2016/07/live-debugging-docker/){: external}
	* [WebStorm](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: external}
