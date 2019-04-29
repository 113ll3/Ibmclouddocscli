---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# 수동으로 {{site.data.keyword.cloud_notm}} 개발자 도구 CLI 플러그인 설치
{: #install-devtools-manually}

구성요소 설치를 위해 더 세부적인 제어를 원하는 경우 {{site.data.keyword.cloud}} 개발자 도구 명령행 인터페이스(CLI) 플러그인을 수동으로 설치할 수 있습니다. 그렇지 않으면 대부분의 사용자를 위해 [플랫폼 설치 프로그램](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt)을 사용하여 모든 필수 소프트웨어가 설치됩니다.
{: shortdesc}

## 시작하기 전에
{: cli-before-you-begin}

* 독립형 [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 설치하여 {{site.data.keyword.cloud_notm}}에 대한 명령행 플러그인 설치의 지원을 받을 수 있습니다. 
* 명령행을 통해 패키지를 다운로드할 수 있도록 [curl](https://curl.haxx.se/download.html){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘") 명령을 설치하십시오.

## {{site.data.keyword.cloud_notm}} 개발자 도구 CLI 플러그인 설치
{: #install-devtools-idt}

{{site.data.keyword.cloud_notm}} 개발자 도구 CLI 명령을 사용하여 애플리케이션을 작성하고 이를 관리, 배치, 디버그 및 테스트할 수 있습니다.

{{site.data.keyword.cloud_notm}} 개발자 도구 플러그인을 설치하려면 다음 명령을 실행하십시오. 
```
ibmcloud plugin install dev
```
{: codeblock}

## Docker 설치
{: #install-devtools-docker}

앱을 로컬로 실행하고 디버깅하려면 [Docker ](https://www.docker.com/get-started){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")도 설치해야 합니다.

## Kubernetes 명령행 도구 설치
{: #idt-install-kube}

Kubernetes 대시보드의 로컬 버전을 보고 애플리케이션을 클러스터에 배치하려면 플랫폼에 대한 [Kubernetes 명령행 도구](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")를 설치하십시오. 

* MacOS:
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux&trade;:
  ```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows&trade;:
  ```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

Kubernetes 명령행 도구를 사용하여 명령을 실행하기 위한 접두부는 `kubectl`입니다. 자세한 정보는 [CLI 및 API 설치](/docs/containers?topic=containers-cs_cli_install#cs_cli_install)를 참조하십시오.

## {{site.data.keyword.registrylong_notm}} CLI 플러그인 설치
{: #idt-install-container-registry-cli-plugin}

`container-registry` CLI 플러그인을 사용하여 IBM이 호스트하고 관리하는 개인용 레지스트리에서 사용자 고유의 이미지 네임스페이스를 설정할 수 있습니다. 여기에서 Docker 이미지를 저장하고 {{site.data.keyword.cloud_notm}} 계정의 모든 사용자와 이를 공유할 수 있습니다. 

* {{site.data.keyword.registrylong}} 플러그인을 설치하려면 다음 명령을 실행하십시오.
  ```
ibmcloud plugin install container-registry
  ```
  {: codeblock}

자세한 정보는 [{{site.data.keyword.registrylong}} 명령 참조서](/docs/services/Registry?topic=registry-registry_cli_reference)를 참조하십시오. 

## {{site.data.keyword.containerlong_notm}} CLI 플러그인 설치
{: #idt-install-kubernetes-cli-plugin}

{{site.data.keyword.containerlong}}에서 Kubernetes 클러스터를 작성하고 관리하려면 다음을 수행하십시오. 

* {{site.data.keyword.registryshort_notm}} 플러그인을 설치하려면 다음 명령을 실행하십시오.
  ```
ibmcloud plugin install container-service
  ```
  {: codeblock}

자세한 정보는 [{{site.data.keyword.registryshort_notm}} 명령 참조서](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference)를 참조하십시오. 

## Helm 설치
{: #idt-install-helm}

Kubernetes 기반의 패키지 관리자인 [Helm](https://helm.sh/docs/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")을 설치하십시오.

* MacOS 및 Linux&trade; 사용자를 위해 다음 명령을 실행하십시오.
  ```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade; 사용자는 Helm [2진](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")을 다운로드하여 설치할 수 있습니다.

## {{site.data.keyword.openwhisk_short}} CLI 플러그인 설치
{: #idt-install-functions}

{{site.data.keyword.openwhisk}} CLI 플러그인을 사용하여 조치에서 코드 스니펫을 관리하고 조치를 패키지로 번들화하고 트리거와 규칙을 작성하여 조치가 이벤트에 응답하게 할 수 있습니다. 

{{site.data.keyword.openwhisk_short}} CLI 플러그인을 설치하려면 다음 명령을 실행하십시오.
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

자세한 정보는 [{{site.data.keyword.openwhisk_short}} CLI 플러그인 설치](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli)를 참조하십시오.

## SDK 생성기 CLI 플러그인 설치
{: #idt-install-sdk-gen}

{{site.data.keyword.cloud_notm}}에서 개발자는 이 플러그인을 사용하여 [Open API 스펙 ](https://www.openapis.org/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘") 준수 REST API 정의에서 SDK를 생성할 수 있습니다. REST API 정의를 변경하는 경우 이 플러그인을 사용하여 전체 프로젝트가 아닌 SDK만 재생성할 수 있습니다.

SDK 생성기 CLI 플러그인을 설치하려면 다음 명령을 실행하십시오.
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

자세한 정보는 [SDK 생성기](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli)를 참조하십시오.
