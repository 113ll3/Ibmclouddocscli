---

copyright:

  years: 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Jetbrains IDE용 IBM Developer Tools
{: #ibm-dev-tools-for-jetbrains}

Jetbrains IDE용 IBM Developer Extension은 IntelliJ, WebStorm, Android Studio 등을 포함하고 IDE 내에서 IDT CLI 명령에 직접 액세스할 수 있는 새로운 메뉴 항목을 제공합니다. 이를 사용하면 앱 배치, {{site.data.keyword.Bluemix_notm}}에서의 앱 시작/중지/재시작, 원격 앱 로그 보기 등을 포함한 Docker 및 CloudFoundry 워크플로우에서 `ibmcloud dev` 명령의 서브세트에 신속하게 액세스할 수 있으며, 이 모든 경우에 편집기의 컨텍스트에서 나가지 않아도 됩니다.
{:shortdesc}

![WebStorm IDE에서 실행되는 IBM Developer Tools의 화면 캡처](jetbrains.png "WebStorm IDE에서 실행되는 IDT 메뉴의 예")

## 종속 항목
{: #dependencies}

Jetbrains 기반 IDE용 IBM Developer Tools 확장을 사용하려면 시스템에 [IBM Cloud Developer Tools CLI](index.html)를 설치해야 합니다.

## 설치
{: #installation}

Jetbrains IDE용 IBM Developers Tools 확장을 설치하는 가장 간단한 방법은 [IDT Github 저장소의 jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) 페이지로 이동하여 다음 지시사항을 따르는 것입니다.

## 사용
{: #usage}

기존 서버 측 앱으로 시작하고 이를 IBM Cloud에서 사용할 수 있게 설정하거나, IDT CLI를 사용하여 스타터 킷으로부터 새 앱을 작성하십시오(ibmcloud dev create). 앱의 프로젝트가 있으면 JetBrains IDE에서 이를 여십시오.

일반 서버 측 앱이 있으면 도구 > IBM Cloud Developer Tools > IBM Cloud에서 앱 사용을 선택하십시오. 이렇게 하면 모든 필수 파일을 확인하고 앱을 로컬로 빌드할 수 있게 하는 누락된 파일을 추가하게 되며 Kubernetes 클러스터 내에 또는 Cloud Foundry 앱을 사용하는 IBM Cloud에 이 파일을 배치할 수 있습니다.

IDT 메뉴에서 기본 빌드/실행/배치 조치를 사용하여 클라우드 네이티브 앱을 개발하십시오. 메뉴에 없는 조치를 수행해야 하는 경우 터미널 탭을 열고 원하는 명령을 수동으로 입력하십시오.
