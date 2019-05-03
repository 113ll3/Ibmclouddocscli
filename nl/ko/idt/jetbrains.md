---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Jetbrains IDE용 IBM Cloud Developer Tools
{: #ibm-dev-tools-for-jetbrains}

`IntelliJ`, `WebStorm`, `Android Studio` 등을 포함하는 Jetbrains IDE용 {{site.data.keyword.cloud}} 개발자 도구 확장은 IDE 내에서 직접 {{site.data.keyword.dev_cli_notm}} CLI 명령에 액세스하는 새 메뉴 항목을 제공합니다. 이를 사용하면 앱 배치, {{site.data.keyword.cloud_notm}}에서의 앱 시작/중지/재시작, 원격 앱 로그 보기 등을 포함한 Docker 및 Cloud Foundry 워크플로우에서 `ibmcloud dev` 명령의 서브세트에 신속하게 액세스할 수 있으며, 이 모든 경우에 편집기의 컨텍스트에서 나가지 않아도 됩니다.
{:shortdesc}

![WebStorm IDE 내에서 실행 중인 IBM Cloud Developer Tools의 화면 캡처입니다. ](jetbrains.png "{{site.data.keyword.cloud_notm}} 개발자 도구 메뉴 예(WebStorm IDE 내에서 실행 중)")


## 종속 항목
{: #jetbrains-dependencies}

Jetbrains 기반 IDE용 {{site.data.keyword.cloud_notm}} 개발자 도구 확장을 사용하려면 시스템에 [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)를 설치해야 합니다.

## 설치
{: #jetbrains-installation}

Jetbrains IDE용 {{site.data.keyword.cloud_notm}} 개발자 도구 확장을 설치하는 가장 좋은 방법은 [{{site.data.keyword.cloud_notm}} 개발자 도구 Github 저장소의 Jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 페이지로 이동하여 다음 지시사항을 따르는 것입니다.

##  사용법
{: #jetbrains-usage}

기존 서버 측 앱을 사용하여 이를 {{site.data.keyword.cloud_notm}}에서 사용할 수 있도록 설정하거나, {{site.data.keyword.dev_cli_notm}} CLI를 사용하여 스타터 킷으로부터 새 앱을 작성할 수 있습니다(ibmcloud dev create). 앱의 프로젝트가 확보되면 이를 JetBrains IDE에서 여십시오.

일반 서버 측 앱이 있으면 도구 > IBM Cloud Developer Tools > {{site.data.keyword.cloud_notm}}에서 앱 사용을 선택하십시오. 그러면 모든 필수 파일이 확인되고 앱에 누락된 파일이 로컬로 추가되며 Cloud Foundry 앱을 사용하여 {{site.data.keyword.cloud_notm}}에 배치하거나 Kubernetes 클러스터 내에 배치하는 것도 가능합니다.

{{site.data.keyword.cloud_notm}} 개발자 도구 메뉴에서 기본 빌드, 실행 및 배치 조치를 사용하여 클라우드 네이티브 앱을 개발하십시오. 메뉴에 없는 조치를 수행해야 하는 경우 터미널 탭을 열고 원하는 명령을 수동으로 입력하십시오.
