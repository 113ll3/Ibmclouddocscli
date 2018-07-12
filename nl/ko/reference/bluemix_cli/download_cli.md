---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-27"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 독립형 {{site.data.keyword.Bluemix_notm}} CLI 설치
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI는 {{site.data.keyword.Bluemix_notm}}에서 애플리케이션, 컨테이너, 인프라, 서비스 및 기타 리소스를 관리하기 위한 명령행 인터페이스를 제공합니다.

{{site.data.keyword.Bluemix}} CLI와 {{site.data.keyword.Bluemix_notm}}용 애플리케이션을 개발하기 위해 권장되는 플러그인 및 도구를 모두 설치하려면 [여기](/docs/cli/index.html)에 설명된 방법을 따르십시오.
{: tip}

독립형 {{site.data.keyword.Bluemix_notm}} CLI를 설치하려면 다음 단계를 사용하십시오.

1. 다운로드할 OS의 설치 프로그램 선택

   Mac OS X 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64비트(ppc64le): [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32비트 릴리스 및 이전 버전은 [여기서](all_versions.html) 찾을 수 있습니다.

1. 설치 프로그램 실행
   * macOS 및 Windows의 경우 설치 프로그램을 실행하십시오.
   * Linux의 경우 패키지의 압축을 풀고 `install_bluemix_cli` 스크립트를 실행하십시오.

1. API 엔드포인트를 대상으로 지정 및 {{site.data.keyword.Bluemix_notm}}에 로그인

  ![예제](example.gif){: gif}

이제 {{site.data.keyword.Bluemix_notm}} 리소스를 관리할 준비가 되었습니다. 명령 설명을 보려면 `ibmcloud help`를 입력하십시오.

연합 ID를 사용하는 경우 [여기](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)의 지시사항을 따라 일회성 패스코드 또는 API 키로 로그인하십시오.  
{: tip}

## {{site.data.keyword.Bluemix_notm}} CLI를 설치하기 위한 추가 옵션
{: #more_options_install}


[설치 프로그램](install_use_cli.html#getting_started) 이외에 쉘을 사용하여 CLI를 다운로드하고 설치할 수도 있습니다. 


### 쉘에서 설치
{: #shell_install}


### MacOS

다음 명령을 복사하여 Mac OS의 터미널에 붙여넣고 이를 실행하십시오.

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

다음 명령을 복사하여 Linux OS의 터미널에 붙여넣고 이를 실행하십시오.

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

다음 명령을 복사하여 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 터미널 콘솔에 붙여넣고 이를 실행하십시오.

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## {{site.data.keyword.Bluemix_notm}} CLI를 자세히 살펴보기 위한 기타 링크

* [플러그인으로 {{site.data.keyword.Bluemix_notm}} CLI 기능 확장](extend_cli.html)
* [{{site.data.keyword.Bluemix_notm}} CLI 명령 사용법](ic_cli_cmds.html) 문서


## 문제 보고 및 피드백 제출
{: #issues}

다음 옵션을 사용하여 문제를 보고하거나 새 기능 요청을 제출하십시오.
 * [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)에서 문제 작성
 * [Slack 채널](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)에 메시지 남기기
