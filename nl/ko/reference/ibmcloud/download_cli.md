---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# 독립형 {{site.data.keyword.cloud_notm}} CLI 설치
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI는 {{site.data.keyword.cloud_notm}}에서 리소스를 관리하기 위한 명령행 인터페이스를 제공합니다. 여전히 `cf` CLI를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인할 수 있지만, 이는 {{site.data.keyword.cloud_notm}}의 Cloud Foundry 서비스에서만 작동됩니다. 

최신 {{site.data.keyword.cloud}} CLI 및 {{site.data.keyword.cloud_notm}}용 애플리케이션 개발을 위한 기타 권장 플러그인과 도구를 모두 설치하려면 [{{site.data.keyword.cloud_notm}} CLI로 시작하기](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)를 참조하십시오.
{: tip}

## 시작하기 전에
{: #before-download-cli}

{{site.data.keyword.cloud_notm}} 데디케이티드 환경용으로 최신 버전이 아닌 32비트 버전이나 이전 버전을 사용해야 하는 경우에는 [{{site.data.keyword.cloud_notm}} CLI 릴리스](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")를 참조하십시오.

## 설치 프로그램으로 설치
{: #ibmcloud-cli-installer}

최신 독립형 {{site.data.keyword.cloud_notm}} CLI를 설치하려면 다음 단계를 사용하십시오.

1. 다운로드할 OS의 설치 프로그램을 선택하십시오.
  *  macOS X 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * Windows 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * Linux x86 64비트: [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * Linux LE 64비트(ppc64le): [설치 프로그램](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")

2. 다음과 같이 설치 프로그램을 실행하십시오.
  * Mac 및 Windows&trade;의 경우 설치 프로그램을 실행하십시오.
  * Linux&trade;의 경우 패키지의 압축을 풀고 `install` 스크립트를 실행하십시오.

3. {{site.data.keyword.cloud_notm}}에 로그인하십시오.
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  이제 {{site.data.keyword.cloud_notm}} 리소스를 관리할 준비가 되었습니다. 명령 설명을 보려면 `ibmcloud help`를 입력하십시오.

  연합 ID를 사용하는 경우 [일회성 패스코드 또는 API 키로 로그인]((/docs/iam?topic=iam-federated_id#federated_id)하십시오.
  {: tip}

## 쉘에서 설치
{: #shell_install}

쉘에서 수동으로 사용 중인 OS용 최신 CLI를 설치하려면 사용 중인 OS에 해당하는 다음 명령을 사용하십시오.

* **Mac**의 경우, 다음 명령을 복사하여 터미널에 붙여넣고 이를 실행하십시오.
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* **Linux&trade;**의 경우, 다음 명령을 복사하여 터미널에 붙여넣고 다음을 실행하십시오.
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* **Windows&trade;**의 경우, 다음 명령을 복사하여 [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘") 터미널 콘솔에 붙여넣고 다음을 실행하십시오.
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## 사용자 정의 디렉토리에 설치
{: #install-custom-dir}

설치 프로그램 또는 쉘 스크립트를 사용하여 {{site.data.keyword.cloud_notm}} CLI를 설치하면 시스템 디렉토리에 설치됩니다. 다른 디렉토리를 지정하려는 경우에는 다음 단계를 사용하십시오.

1. 다음 링크를 사용하여 OS에 해당하는 바이너리 패키지를 다운로드하십시오.
  * macOS: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * linux32: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * linux64: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * ppc64le: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * win32: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")
  * win64: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")/[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")

2. 지정한 디렉토리에 패키지의 압축을 푸십시오.

   다음과 같은 추출된 컨텐츠를 볼 수 있습니다.

   Linux&trade; 및 Mac의 경우:
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
   {: screen}

   Windows의 경우: 
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. `PATH` 환경 변수에 추가하고 쉘 자동 완성을 사용으로 설정하십시오.
  * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI`를 `PATH` 환경 변수에 추가하십시오.
  * 쉘 자동 완성 지원(Mac 및 Linux&trade; 전용)에 대해서는 [이 안내서](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)를 참조하십시오.

## {{site.data.keyword.cloud_notm}} CLI 업데이트
{: #update-ibmcloud-cli}

최신 버전의 CLI를 사용해야 합니다. 최신 버전을 사용하지 않는 경우 다음 명령을 실행하여 CLI를 업데이트하십시오.

```
ibmcloud update
```
{: codeblock}

{{site.data.keyword.cloud_notm}} CLI 버전을 판별하려면 다음 명령을 실행하십시오.
```
ibmcloud -v
```
{: codeblock}

현재 릴리스를 실행 중이면 다음 출력이 표시됩니다.
```
업데이트 확인 중...
업데이트가 필요하지 않습니다. CLI가 이미 최신 상태입니다.
```
{: screen}

새 {{site.data.keyword.cloud_notm}} CLI 릴리스에 대한 알림을 받으려면 [{{site.data.keyword.cloud_notm}} CLI 릴리스 저장소](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")를 구독하십시오.
