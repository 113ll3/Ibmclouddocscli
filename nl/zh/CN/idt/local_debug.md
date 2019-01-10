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

# {{site.data.keyword.dev_cli_notm}} CLI 的本地应用程序调试
{: #local-debug}

有多种工具可以帮助您在 {{site.data.keyword.cloud_notm}} 中调试用 Java 和 Node.js 编写的应用程序。

## Java 应用程序调试
{: #java}

为 Java 应用程序启用调试工具的步骤：

1. 从应用程序项目的根目录，运行以下命令：

```
ibmcloud dev debug
```

2. 将调试器连接到应用程序：

	* Eclipse
      1. 将**现有 Maven 项目**导入到 Eclipse 中。
      2. 创建 [Java 远程应用程序 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm) 调试配置。
      		1. 输入 IP 地址或 `localhost:<port>`  
      		2. 输入 `7777` 作为端口号。
      		3. 指定已导入的 Java 项目的名称。
      6. 在 IDE 中设置断点。
      7. 运行调试配置。
      8. 使用浏览器来访问端点以重现问题。  
	   
	   对于 Java 基本微服务端点，缺省端口是 9080。
	   {: note}

	* [IntelliJ ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html)
	* [VSCode ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger)
	* JDK 命令行：`jdb -attach <host:port>`

## Node.js 应用程序调试
{: #node}

为 Node.js 应用程序启用调试工具的步骤：

1. 从应用程序项目的根目录，运行以下命令：

```
ibmcloud dev debug
```

2. 将调试器连接到应用程序：
	* [VSCode ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://blog.docker.com/2016/07/live-debugging-docker/)
	* [WebStorm ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/)


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
