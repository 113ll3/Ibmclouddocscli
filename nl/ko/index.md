---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-01"

keywords: IBM Cloud Developer Tools CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.cloud_notm}} CLI 시작하기
{: #ibmcloud-cli}

이 튜토리얼에서는 {{site.data.keyword.cloud}} 개발자 도구 세트를 설치하고, 설치를 확인하고, 환경을 구성합니다. {{site.data.keyword.cloud_notm}} 개발자 도구는 웹, 모바일, 마이크로서비스 애플리케이션의 작성, 개발, 배치를 위한 명령행 접근 방식을 제공합니다.
{: shortdesc}

이 설치를 통해 독립형 {{site.data.keyword.cloud_notm}} CLI 및 다음 도구를 얻을 수 있습니다.

* `Homebrew`(Mac 전용)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 플러그인
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 플러그인
* {{site.data.keyword.registrylong_notm}} 플러그인
* {{site.data.keyword.containerlong_notm}} 플러그인
* `sdk-gen` 플러그인

## 시작하기 전에
{: #idt-prereq}

[{{site.data.keyword.cloud_notm}} 계정](https://cloud.ibm.com/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘") 및 다음 시스템 요구사항이 필요합니다.

* Windows를 실행 중인 경우 Windows 10 Pro를 실행하지 않으면 동일한 기능은 지원되지 않습니다.
* 최소 버전 1.13.1의 안정된 Docker 채널을 사용해야 합니다.

## 1단계: 설치 명령 실행
{: #step1-install-idt}

* Mac 및 Linux의 경우 다음 명령을 실행하십시오.
  ```
curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Windows 10 Pro의 경우 관리자로 다음 명령을 실행하십시오.
  ```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

    Windows PowerShell 아이콘을 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 선택하십시오.
  {: tip}

  [GitHub 저장소](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에서 설치 프로그램 스크립트를 다운로드할 수도 있습니다.

<!--Uncomment when this linked topic goes to prod.
  For the steps to install these tools manually, see [Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->

## 2단계. 설치 확인
{: #step2-verify-idt}

CLI 및 개발자 도구가 설치되었는지 확인하려면 `help` 명령을 실행하십시오.
```
ibmcloud dev help
```
{: codeblock}

출력에 사용법 지시사항, 현재 버전 및 지원되는 명령이 나열됩니다.

## 3단계. 환경 구성
{: #step3-configure-idt-env}

1. IBM ID를 사용하여 {{site.data.keyword.cloud_notm}}에 로그인하십시오. 여러 계정이 있는 경우 사용할 계정을 선택하도록 프롬프트가 표시됩니다. `-r` 플래그로 지역을 지정하지 않은 경우, 지역도 선택해야 합니다.
  ```
ibmcloud login
  ```
  {: codeblock}
  
  인증 정보가 거부되는 경우 연합 ID를 사용 중일 수 있습니다. 연합 ID로 로그인하려면 `--sso` 플래그를 사용하십시오. 자세한 사항은 [연합 ID로 로그인](/docs/iam/federated_id?topic=iam-federated_id#federated_id)을 참조하십시오.
  {: tip}

2. Cloud Foundry 서비스를 사용하려면 조직 및 영역을 대상 지정하십시오.
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  선택적으로 이전 명령의 출력을 사용하여, 다음 명령을 통해 조직 및 영역을 수동으로 설정할 수 있습니다.
  ```
ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## 다음 단계
{: #next-steps}

이제 첫 번째 애플리케이션을 개발하고 배치할 준비가 되었습니다! 자세한 정보는 [CLI를 사용하여 앱 작성 및 배치](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli)를 참조하십시오.
