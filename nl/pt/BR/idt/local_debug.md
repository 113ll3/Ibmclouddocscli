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

# Depuração de aplicativo local para a CLI do {{site.data.keyword.dev_cli_notm}}
{: #local-debug}

Há ferramentas para ajudá-lo a depurar seu aplicativo no Java&trade; e Node.js no {{site.data.keyword.cloud_notm}}.

## Depuração do aplicativo Java
{: #java}

Etapas para ativar a ferramenta de depuração para um aplicativo Java&trade;:

1. No diretório raiz de seu projeto do aplicativo, execute o comando a seguir:

  ```
  Ibmcloud dev debug
  ```
  {: codeblock}

2. Conectando o depurador a seu aplicativo:

	* Eclipse
      1. Importe o **Projeto maven existente** no Eclipse.
      2. Crie uma configuração de depuração do [aplicativo remoto Java&trade;](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").
      		1. Insira o endereço IP ou `localhost:<port>`  
      		2. Insira `7777` para o número da porta.
      		3. Especifique o nome do projeto importado.
      6. Configure um ponto de interrupção no IDE.
      7. Execute a configuração de depuração.
      8. Acesse o terminal com um navegador para recriar o problema.  
	   
	   A porta padrão é `9080` para o terminal Microsserviços básico do Java&trade;.
	   {: note}

	* [IntelliJ ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
	* [VSCode ](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
	* Linha de comandos do JDK: `jdb -attach <host:port>`

## Depuração do aplicativo Node.js
{: #idt-node-debug}

Etapas para ativar a ferramenta de depuração para um aplicativo Node.js:

1. No diretório raiz do projeto do aplicativo, execute o comando a seguir:
  ```
  Ibmcloud dev debug
  ```
  {: codeblock}

2. Conectando o depurador a seu aplicativo:
	* [VSCode ](https://blog.docker.com/2016/07/live-debugging-docker/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
	* [WebStorm ](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")


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
