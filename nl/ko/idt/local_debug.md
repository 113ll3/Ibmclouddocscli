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

# {{site.data.keyword.dev_cli_notm}} CLI용 로컬 애플리케이션 디버깅
{: #local-debug}

{{site.data.keyword.cloud_notm}}에서 Java 및 Node.js의 애플리케이션을 디버그하도록 도와주는 도구가 있습니다.

## Java 애플리케이션 디버깅
{: #java}

Java 애플리케이션용 디버깅 도구를 사용하기 위한 단계:

1. 애플리케이션 프로젝트의 루트 디렉토리에서 다음 명령을 실행하십시오.

  ```
ibmcloud dev debug
  ```
  {: codeblock}

2. 디버거를 애플리케이션에 연결하십시오.

	* Eclipse
      1. **기본 maven 프로젝트**를 Eclipse로 가져오십시오.
      2. [Java 원격 애플리케이션 ](http://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Ftasks%2Ftask-remotejava_launch_config.htm){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 디버그 구성을 작성하십시오.
      		1. IP 주소 또는 다음을 입력하십시오. `localhost:<port>`  
      		2. 포트 번호에 `7777`을 입력하십시오.
      		3. 가져온 Java 프로젝트의 이름을 지정하십시오.
      6. IDE에 중단점을 설정하십시오.
      7. 디버그 구성을 실행하십시오.
      8. 브라우저에서 엔드포인트에 액세스하여 문제를 다시 작성하십시오.  
	   
	   Java 기본 마이크로서비스 엔드포인트의 경우 기본 포트는 9080입니다.
	   {: note}

	* [IntelliJ ](https://www.jetbrains.com/help/idea/2016.3/run-debug-configuration-remote.html){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
	* [VSCode ](https://marketplace.visualstudio.com/items?itemName=donjayamanne.javadebugger){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
	* JDK 명령행: `jdb -attach <host:port>`

## Node.js 애플리케이션 디버깅
{: #idt-node-debug}

Node.js 애플리케이션용 디버깅 도구를 사용하기 위한 단계:

1. 애플리케이션 프로젝트의 루트 디렉토리에서 다음 명령을 실행하십시오.
  ```
ibmcloud dev debug
  ```
  {: codeblock}

2. 디버거를 애플리케이션에 연결하십시오.
	* [VSCode ](https://blog.docker.com/2016/07/live-debugging-docker/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
	* [WebStorm ](https://blog.alexseifert.com/2016/10/25/debugging-node-js-in-a-docker-container-with-webstorm/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")


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
