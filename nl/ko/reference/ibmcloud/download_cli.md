---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-19"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 독립형 {{site.data.keyword.cloud_notm}} CLI 설치
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI는 {{site.data.keyword.cloud_notm}}에서 리소스를 관리하기 위한 명령행 인터페이스를 제공합니다. 여전히 `cf` CLI를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인할 수 있지만, 이는 {{site.data.keyword.cloud_notm}}의 Cloud Foundry 서비스에서만 작동됩니다. 

{{site.data.keyword.cloud}} CLI 및 {{site.data.keyword.cloud_notm}}용 애플리케이션 개발을 위한 기타 권장 플러그인과 도구를 모두 설치하려면 [{{site.data.keyword.cloud_notm}} CLI로 시작하기](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)를 참조하십시오.
{: tip}

독립형 {{site.data.keyword.cloud_notm}} CLI를 설치하려면 다음 단계를 사용하십시오.

1. 다운로드할 OS의 설치 프로그램을 선택하십시오.

   Mac OS X 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
Windows 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
Linux X86 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
Linux LE 64비트(ppc64le): [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   32비트 이하 버전의 경우 [{{site.data.keyword.cloud_notm}} CLI 릴리스](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) 페이지로 이동하여 다운로드하십시오.

2. 설치 프로그램 실행
   * MacOS 및 Windows&trade;의 경우 설치 프로그램을 실행하십시오.
   * Linux&trade;의 경우 패키지의 압축을 풀고 `install` 스크립트를 실행하십시오.

3. API 엔드포인트를 대상으로 지정 및 {{site.data.keyword.cloud_notm}}에 로그인:
   ```
ibmcloud login
   ```
   {: codeblock}
   
이제 {{site.data.keyword.cloud_notm}} 리소스를 관리할 준비가 되었습니다. 명령 설명을 보려면 `ibmcloud help`를 입력하십시오.

연합 ID를 사용하는 경우 [여기](/docs/iam?topic=iam-federated_id#federated_id)의 지시사항을 따라 일회성 패스코드 또는 API 키로 로그인하십시오.  
{: tip}

설치 프로그램 외에, 다른 방법으로 {{site.data.keyword.cloud_notm}} CLI를 설치할 수도 있습니다.

* 쉘에서 설치
* 2진 패키지를 다운로드하여 사용자 정의 디렉토리에 설치

## 쉘에서 설치
{: #shell_install}

### macOS
{: #shell-install-macos}

다음 명령을 복사하여 Mac OS의 터미널에 붙여넣고 이를 실행하십시오.
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

다음 명령을 복사하여 Linux&trade; OS의 터미널에 붙여넣고 이를 실행하십시오.
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

다음 명령을 복사하여 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘") 터미널에 붙여넣고 이를 실행하십시오.
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## 사용자 정의 디렉토리에 설치
{: #install-custom-dir}

설치 프로그램 또는 쉘 스크립트를 사용하여 {{site.data.keyword.cloud_notm}} CLI를 설치하는 경우, 바이너리는 시스템 디렉토리에 배치됩니다. 다른 디렉토리를 지정하려는 경우에는 다음 단계를 사용하십시오.

### 1단계: 다음 링크를 사용하여 OS에 따라 2진 패키지를 다운로드하십시오.
{: #step1-custom-dir}

|플랫폼 |다운로드 | 체크섬 |
|---------|----------|---------|
|macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### 2단계: 지정한 디렉토리에 패키지의 압축을 푸십시오.
{: #step2-custom-dir}

   패키지의 압축을 푼 후 다음 컨텐츠를 볼 수 있습니다.

   Linux&trade; 및 macOS의 경우:

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   Windows의 경우

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### 3단계: `PATH` 환경 변수에 추가하고 쉘 자동 완성을 사용으로 설정하십시오.
{: #step3-custom-dir}

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI`를 `PATH` 환경 변수에 추가하십시오.
   * 쉘 자동 완성 지원(MacOS 및 Linux&trade; 전용)에 대해서는 [이 안내서](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)를 참조하십시오.

## 독립형 {{site.data.keyword.cloud_notm}} CLI 설치 제거
{: #uninstall-ibmcloud-cli}

다음 섹션에서는 특정 플랫폼에서 독립형 {{site.data.keyword.cloud_notm}} CLI를 설치 제거하는 방법에 관한 세부사항을 제공합니다.

### Windows에서 설치 제거
{: #uninstall-cli-windows}

1. `시작` 단추를 클릭한 후에 `제어판`을 선택하십시오.
2. 팝업 창에서 `프로그램 설치 제거`를 클릭하십시오.
3. 팝업 애플리케이션 목록에서 `IBM Cloud 명령행 인터페이스`를 찾으십시오.
4. `IBM Cloud 명령행 인터페이스`를 마우스 오른쪽 단추로 클릭하고 `설치 제거`를 선택하십시오.
5. 설치 제거 프로그램이 시작됩니다. 지시사항에 따라 설치 제거를 완료하십시오.

### Linux 및 macOS에서 설치 제거
{: #uninstall-cli-linux-macos}

#### `0.9.0` 이전 버전

1. 터미널을 열고 다음 명령을 실행하십시오.
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. 자동 완성 스크립트를 구성한 경우 해당 스크립트를 정리하십시오. 세부사항은 [{{site.data.keyword.cloud_notm}} CLI의 쉘 자동 완성 사용 설정(Linux 및 macOS 전용)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)을 참조하십시오.

#### `0.9.0` 이상

1. 터미널을 열고 다음 명령을 실행하십시오.
  * `/usr/local/ibmcloud/uninstall`
2. 모든 사용자 정의 자동 완료 스크립트를 정리하십시오. 세부사항은 [{{site.data.keyword.cloud_notm}} CLI의 쉘 자동 완성 사용 설정(Linux 및 macOS 전용)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)을 참조하십시오.

## {{site.data.keyword.cloud_notm}} CLI를 자세히 살펴보기 위한 기타 링크
{: #other-cli-links}

* [플러그인으로 {{site.data.keyword.cloud_notm}} CLI 확장](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [일반 CLI(ibmcloud) 명령](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## 문제 보고 및 피드백 제출
{: #issues}

다음 옵션을 사용하여 문제를 보고하거나 새 기능 요청을 제출하십시오.
* [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")에서 문제 항목을 작성하십시오.
* [{{site.data.keyword.cloud_notm}} 기술에 대한 Slack - #developer-tools 채널](https://ibm-cloud-tech.slack.com){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")에 메시지를 남기고 [여기](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")에서 팀 액세스 권한을 요청하십시오.
