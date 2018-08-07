---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI 설치를 위한 추가 옵션
{: #more_options_install}

[설치 프로그램](install_use_cli.html#getting_started) 외에도 {{site.data.keyword.Bluemix_notm}} CLI를 설치하는 기타 옵션이 있을 수 있습니다. 

* 쉘에서 설치
* 2진 패키지를 다운로드하여 사용자 정의 디렉토리에 설치

## 쉘에서 설치
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

## 사용자 정의 디렉토리에 설치

설치 프로그램 또는 쉘 스크립트를 사용하여 {{site.data.keyword.Bluemix_notm}} CLI를 설치하는 경우, 바이너리는 시스템 디렉토리에 배치됩니다. 다른 디렉토리를 지정하려는 경우에는 다음 단계를 사용하십시오.

1. 2진을 다운로드하십시오. 

   다음 링크를 사용하여 OS에 따라 2진 패키지를 다운로드하십시오. 

   |플랫폼 |다운로드 | 체크섬 |
   |----|----| --- |
   |macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. 지정한 디렉토리에 패키지의 압축을 푸십시오. 

   패키지의 압축을 푼 후의 컨텐츠는 다음과 같습니다.

   Linux 및 MacOS의 경우

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
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
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

1. `PATH` 환경 변수에 추가하고 쉘 자동 완성을 사용으로 설정하십시오. 

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI`를 `PATH` 환경 변수에 추가하십시오.
   * 쉘 자동 완성 지원(MacOS 및 Linux 전용)에 대해서는 [이 안내서](enable_cli_autocompletion.html)를 참조하십시오.

