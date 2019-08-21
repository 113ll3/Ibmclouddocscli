---

copyright:
  years: 2017, 2019
lastupdated: "2019-05-21"

keywords: cli, local app debug, java debug, node debug, debug, cli debug, local cli, ibmcloud dev, dev debug

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# {{site.data.keyword.dev_cli_notm}} CLI のローカル・アプリのデバッグ
{: #local-debug}

{{site.data.keyword.cloud_notm}} 内で Java&trade; や Node.js のアプリケーションをデバッグするのを支援するツールがあります。

## Java アプリのデバッグ
{: #java}

Java&trade; アプリ用のデバッグ・ツールを使用可能にするためのステップは以下のとおりです。

1. アプリ・プロジェクトのルート・ディレクトリーから、以下のコマンドを実行します。

  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. デバッガーをアプリに接続します。

	* Eclipse
      1. **既存の maven プロジェクト**を Eclipse にインポートします。
      2. [&trade; リモート・アプリ ](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: new_window} ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン") のデバッグ構成を作成します。
         1. IP アドレスまたは `localhost:<port>` を入力します。  
         2. ポート番号に `7777` を入力します。
         3. インポートしたプロジェクトの名前を指定します。
      6. IDE 内でブレークポイントを設定します。
      7. デバッグ構成を実行します。
      8. ブラウザーでエンドポイントにアクセスし、問題を再現します。  
	   
	   Java&trade; 基本マイクロサービス・エンドポイントのデフォルト・ポートは、`9080` です。
	   {: note}

	* [IntelliJ ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
	* [VSCode ](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
	* JDK コマンド・ライン: `jdb -attach <host:port>`

## Node.js アプリのデバッグ
{: #idt-node-debug}

Node.js アプリ用のデバッグ・ツールを使用可能にするためのステップは以下のとおりです。

1. アプリ・プロジェクトのルート・ディレクトリーから、以下のコマンドを実行します。
  ```
  ibmcloud dev debug
  ```
  {: codeblock}

2. デバッガーをアプリに接続します。
	* [VSCode ](https://blog.docker.com/2016/07/live-debugging-docker/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")
	* [WebStorm ](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")


<!--
## Swift app debugging - content from mike tunnicliffe
{: #swift}

Steps to enable debug for a Swift app:  

1. On the App server (or system where the Swift app will execute), you should start the 'lldb server':
 - `lldb-server platform -->
<!-- listen <port number>`
2. On the App server, build the Kitura-based server app using the debug configuration:
 - `swift build debug`
3. On the App server, start the Kitura-based server app:
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
