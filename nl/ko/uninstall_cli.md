---

copyright:
  years: 2019
lastupdated: "2019-08-05"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# 독립형 {{site.data.keyword.cloud_notm}} CLI 설치 제거
{: #uninstall-ibmcloud-cli}

특정 플랫폼에서 독립형 {{site.data.keyword.cloud_notm}} CLI를 설치 제거하려면 다음 단계를 사용하십시오.
{: shortdesc}

## Windows에서 설치 제거
{: #uninstall-cli-windows}

1. **시작** 단추를 클릭한 후에 **제어판**을 선택하십시오.
2. 팝업 창에서 **프로그램 설치 제거**를 클릭하십시오.
3. 팝업 애플리케이션 목록에서 **IBM Cloud 명령행 인터페이스**를 찾으십시오.
4. **IBM Cloud 명령행 인터페이스**를 마우스 오른쪽 단추로 클릭하고 **설치 제거**를 선택하십시오.
5. 설치 제거 프로그램이 시작됩니다. 지시사항에 따라 설치 제거를 완료하십시오.

## Linux 및 macOS에서 설치 제거
{: #uninstall-cli-linux-macos}

설치 제거 단계는 설치된 CLI의 버전에 따라 다릅니다.

{{site.data.keyword.cloud_notm}} CLI 버전을 판별하려면 다음을 실행하십시오.
```
ibmcloud -v
```
{: codeblock}

`0.9.0` 이전 버전을 설치 제거하려면 다음 명령을 실행하십시오.
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

자동 완성 스크립트를 구성한 경우 해당 스크립트를 정리하십시오. 세부사항은 [{{site.data.keyword.cloud_notm}} CLI의 쉘 자동 완성 사용 설정(Linux 및 Mac 전용)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)을 참조하십시오.

버전 `0.9.0` 이상을 설치 제거하려면 다음 명령을 실행하십시오.
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

모든 사용자 정의 자동 완료 스크립트를 정리하십시오. 세부사항은 [{{site.data.keyword.cloud_notm}} CLI의 쉘 자동 완성 사용 설정(Linux 및 Mac 전용)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)을 참조하십시오.
