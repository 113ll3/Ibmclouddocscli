---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"


---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 本端應用程式除錯
{: #local-debug}

在 {{site.data.keyword.cloud_notm}} 中，有一些工具可協助您使用 Java 及 Node.js 來除錯應用程式。

## Java 應用程式除錯
{: #java}

針對 Java 應用程式啟用除錯工具的步驟：

1. 從應用程式專案的根目錄中，執行下列指令：

```
bx dev debug
```

2. 將除錯器連接至您的應用程式：

	* Eclipse
      1. 將**現有 maven 專案**匯入至 Eclipse。
      2. 建立 [Java 遠端應用程式 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm) 除錯配置。
      		1. 輸入 IP 位址或 `localhost:<port>`  
      		2. 輸入 `7777` 作為埠號。
      		3. 指定您所匯入的 Java 專案名稱。
      6. 在 IDE 中設定岔斷點。
      7. 執行除錯配置。
      8. 使用瀏覽器存取端點，以重建問題。  
	   **附註**：Java 基本「微服務」端點的預設埠是 9080。
	* [IntelliJ ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html)
	* [VSCode ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger)
	* JDK 指令行：`jdb -attach <host:port>`

## Node.js 應用程式除錯
{: #node}

針對 Node.js 應用程式啟用除錯工具的步驟：

1. 從您應用程式專案的根目錄，執行下列指令：

```
bx dev debug
```

2. 將除錯器連接至您的應用程式：
	* [VSCode ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://blog.docker.com/2016/07/live-debugging-docker/)
	* [WebStorm ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/)


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
