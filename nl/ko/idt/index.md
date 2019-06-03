---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# 앱 개발 및 배치
{: #developing}

{{site.data.keyword.dev_cli_notm}} CLI를 사용한 클라우드 네이티브 애플리케이션 개발은 아주 간단한 플로우를 따릅니다.

1. [배치용 앱 작성 또는 사용](#idt-create).
2. 컨테이너를 사용하여 로컬로 앱 [코딩, 빌드 및 실행](#code-build-run)
3. 앱을 {{site.data.keyword.cloud_notm}}에 [배치](#cli-deploy)

## 클라우드 배치용 앱 작성 또는 사용
{: #idt-create}

앱을 작성할 수 있는 여러 방법이 있습니다.
- 일반 웹 앱 및 마이크로서비스를 위한 [앱 서비스 웹 콘솔](https://cloud.ibm.com/developer/appservice/dashboard)
- Watson 기반 기능 사용 스타터 앱 작성을 위한 [Watson 대시보드](https://cloud.ibm.com/developer/watson/dashboard).
    - 기타 산업 및 기술 기반 대시보드는 {{site.data.keyword.cloud_notm}} 홈 페이지의 "Hamburger" 메뉴에서 사용 가능합니다. 모두 스타터 킷을 사용하여 새 앱을 작성하는 것과 유사한 접근 방법을 사용합니다.
- 앱을 새로 작성하는 {{site.data.keyword.dev_cli_notm}} CLI [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) 명령
- 기존 서버 측 앱에서 빠르게 클라우드를 사용할 수 있게 해 주는 {{site.data.keyword.dev_cli_notm}} CLI [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 명령

이전 작성 방법의 경우에도 플로우는 유사합니다. 사용할 프로젝트 유형, 구현 언어 및 앱 패턴을 선택합니다. 또한 인증 또는 지속성과 같이 서비스를 앱에 추가하도록 선택할 수 있습니다. 마지막으로 DevOps 기능을 앱에 추가할 수 있으며, 이는 소스 제어 및 팀 커뮤니케이션의 완전한 도구 체인을 제공합니다. {{site.data.keyword.cloud_notm}}에 앱을 유효성 검증, 빌드, 배치하기 위해 각 커미트에서 트리거되는 파이프라인을 포함합니다.

![ {{site.data.keyword.dev_cli_notm}} CLI를 사용하는 샘플 작성 플로우](create_flow.png " {{site.data.keyword.dev_cli_notm}} CLI를 사용하는 샘플 작성 플로우"){: caption="그림 1. {{site.data.keyword.dev_cli_notm}} CLI를 사용하는 샘플 작성 플로우" caption-side="bottom"}

{{site.data.keyword.dev_cli_notm}} CLI는 개발 중에 원활한 경험을 제공하기 위해 긴밀하게 협업합니다. 웹 콘솔에서 작성된 프로젝트는 추가 개발을 위해 워크스테이션에 생성된 소스 코드를 다운로드할 수 있는 **코드 다운로드** 단추를 제공합니다.

### 유용한 CLI 명령
{: #helpful}

다음 `ibmcloud dev` CLI 명령은 프로젝트 및 웹 콘솔에 대한 작업을 지원합니다.
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code): 앱 소스 코드를 워크스테이션에 다운로드하는 데 사용합니다.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console): 브라우저를 열어 {{site.data.keyword.cloud_notm}}에서 현재 앱의 프로젝트 페이지를 표시합니다.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create): 명령은 새 앱을 작성합니다.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete): {{site.data.keyword.cloud_notm}} 프로젝트 영역에서 현재 앱을 삭제하는 데 사용됩니다.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable): 명령은 기존 서버 측 앱을 클라우드에서 사용할 수 있게 합니다.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials): 바인딩된 서비스를 사용하기 위해 프로젝트에서 요구하는 인증 정보를 가져옵니다.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list): CLI나 콘솔에서 현재 선택한 조직 및 영역에 작성한 모든 앱을 나열합니다.

### 앱의 프로젝트 구조 탐색
{: #exploring-project}

개발자 도구와 함께 사용하도록 설정되거나 작성된 프로젝트는 `cli-config.yml` 파일에 캡슐화된 사전 구성된 설정과 함께 제공됩니다. `cli-config.yml`은 `ibmcloud dev` 명령에서 사용하는 기본 항목을 포함하며, 이러한 항목은 명령행을 통해 전달되는 값으로 대체할 수 있습니다.

### 참조 블로그 및 동영상
{: #ref1}

- 동영상: [Installing {{site.data.keyword.cloud_notm}} developer tools on Ubuntu Linux&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
- 블로그: [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")

## 코딩, 빌드 및 실행
{: #code-build-run}

일단 프로젝트가 작성되었으면 프로젝트를 더 유용하게 만드는 것은 사용자에게 달려있습니다. 일반적인 플로우는 소스 코드 편집 후 [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build)를 실행하여 앱의 언어 및 구성에 고유한 로컬 컨테이너 내에서 앱을 컴파일하는 것으로 구성되어 있습니다. 사용하는 앱의 언어와 생성기에 따라 로컬로 빌드 및 실행을 지원하기 위해 기본 설정된 하나 이상의 컨테이너가 있습니다. 일반적으로 빌드와 로컬 디버깅을 위한 "도구" 컨테이너입니다. 이 컨테이너는 개발에서 사용자를 지원하기 위해 추가 도구 및 기능을 보유합니다. 또한 Cloud Foundry 또는 IBM의 Kubernetes 기반 컨테이너 환경에서 클라우드에 배치된 앱의 런타임 환경을 모방하는 "실행" 컨테이너도 있습니다.

선호하는 편집기나 IDE가 무엇이든 자유롭게 사용하여 앱을 코딩할 수 있습니다. {{site.data.keyword.IBM_notm}}은 편집기 내에서 직접 모든 IDE 명령에 액세스할 수 있는 Microsoft&trade; Visual Studio Code(VSCode) 편집기 확장을 제공합니다.

프로젝트가 빌드되면 [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 또는 [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug)를 사용하여 앱을 실행하십시오. 앱은 적절한 컨테이너에서 실행됩니다. 일부 앱 패턴은 앱의 여러 외부 컨테이너를 지원합니다. 앱은 실행 또는 디버그 동안 자동으로 시작되고 구성됩니다. 또한 앱과 연관된 테스트 케이스를 실행하는 [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) 명령이 있습니다.

### 로컬 컨테이너 사용 방법
{: #local-containers}

{{site.data.keyword.dev_cli_long}} CLI는 앱 빌드와 테스트를 위해 두 컨테이너를 사용합니다. 첫 번째는 tools 컨테이너로서 앱 빌드와 테스트에 필요한 유틸리티를 포함합니다. 이 컨테이너를 위한 Dockerfile은 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 매개변수로 정의됩니다. 특정 런타임의 개발에 일반적으로 사용되는 도구를 포함하고 있으므로 개발 컨테이너로 생각할 수 있습니다.

두 번째 컨테이너는 run 컨테이너입니다. 이 컨테이너는 예를 들어 {{site.data.keyword.cloud}}에서 사용하기 위해 배치하는 데 적합한 양식으로 되어 있습니다. 결과적으로 앱을 시작하는 시작점이 정의됩니다. {{site.data.keyword.dev_cli_short}} CLI를 통해 앱을 실행하도록 선택하면 이 컨테이너가 사용됩니다. 이 컨테이너를 위한 Dockerfile은 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) 매개변수로 정의됩니다.

### 유용한 CLI 명령
{: #helpful2}

다음 CLI 명령을 사용하여 프로젝트를 디버깅하십시오.
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build)는 로컬 컨테이너에 프로젝트를 빌드합니다.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug)는 로컬 컨테이너에 있는 애플리케이션을 디버깅합니다.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run)은 로컬 컨테이너에 있는 애플리케이션을 실행합니다.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell)은 로컬 컨테이너에서 쉘을 엽니다.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status)는 {{site.data.keyword.dev_cli_notm}} CLI에서 사용하는 컨테이너 상태를 확인합니다.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop)은 컨테이너를 중지합니다.
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test)는 로컬 컨테이너에 있는 애플리케이션을 테스트합니다.

### 로컬 앱 디버깅
{: #ref2}

- [로컬 앱 디버깅](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## 배치
{: #cli-deploy}

적절한 클라우드 네이티브 환경에서 다양한 여러 기능 및 모든 배치를 관리하기 위한 완전한 기능의 DevOps 파이프라인을 활용합니다. 작성 플로우 동안 IBM Cloud의 DevOps를 사용하기 위해 앱을 설정할 수 있습니다. 기본 제공 DevOps를 사용할 준비가 되지 않은 경우에는 수동으로 [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) 명령을 실행하여 앱을 배치하거나 고유 DevOps 파이프라인 내에서 `deploy` 명령을 사용할 수 있습니다.

### 유용한 CLI 명령
{: #helpful3}

다음 CLI 명령은 배치 프로세스 동안 프로젝트 작업을 지원합니다.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console): 프로젝트에 대한 {{site.data.keyword.cloud_notm}} 콘솔을 엽니다.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy): 애플리케이션을 {{site.data.keyword.cloud_notm}}에 배치합니다.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view): 프로젝트의 URL을 표시합니다.

### 참조 블로그 및 동영상
{: #ref3}

- 블로그: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
- 블로그: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")
