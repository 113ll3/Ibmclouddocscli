---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}} 사용 
{: developing}

{{site.data.keyword.dev_cli_notm}}을 사용한 클라우드 네이티브 앱 개발은 아주 간단한 플로우를 따릅니다. 

1. [앱 작성 또는 사용](#create)
2. 컨테이너를 사용하여 로컬로 앱을 [코딩, 빌드 및 실행](#build)
3. 앱을 {{site.data.keyword.Bluemix_notm}}에 [배치](#deploy)

## 앱 작성 또는 사용
{: #create}

클라우드 앱을 작성할 수 있는 여러 방법이 있습니다. 
- 일반 웹 앱 및 마이크로서비스를 위한 [앱 서비스 웹 콘솔](https://console.bluemix.net/developer/appservice)
- Watson 기반 기능 사용 스타터 앱 작성을 위한 [Watson 대시보드](https://console.bluemix.net/dashboard/watson).
    - 기타 산업 및 기술 기반 대시보드는 {{site.data.keyword.Bluemix_notm}} 홈 페이지의 "Hamburger" 메뉴에서 사용 가능합니다. 모두 새 앱 작성을 위해 스타터 킷을 사용하는 것과 유사한 접근 방법을 사용합니다. 
- 새 앱을 작성하기 위한 {{site.data.keyword.dev_cli_notm}} CLI의 [`bx dev create`](./commands.html#create) 명령.
- 클라우드에서 신속하게 기존 서버 측 앱을 사용할 수 있게 하는 {{site.data.keyword.dev_cli_notm}} CLI의 [`bx dev enable`](./commands.html#enable) 명령.

위 작성 방법 모두 플로우는 유사합니다. 사용할 프로젝트 유형, 구현 언어, 앱 패턴을 선택할 수 있습니다. 또한 인증 또는 지속성과 같이 부가 가치 서비스를 앱에 추가하도록 선택할 수 있습니다. 마지막으로 IBM Cloud에서 앱을 유효성 검증, 빌드, 배치하기 위해 각 커미트에서 트리거된 파이프라인을 비롯하여 소스 제어 및 팀 통신의 완전한 도구 체인을 제공하는 DevOps 기능을 앱에서 사용하도록 선택할 수 있습니다.  

![IDT CLI를 사용한 샘플 플로우 작성](create_flow.png "IDT CLI를 사용한 샘플 플로우 작성") <br> IDT CLI를 사용한 샘플 플로우 작성

{{site.data.keyword.dev_cli_notm}} CLI는 개발 동안 완벽한 경험을 제공하기 위해 긴밀히 작업합니다. 웹 콘솔 내에서 작성된 프로젝트는 더 많은 개발을 위해 워크스테이션에 생성된 소스 코드를 다운로드할 수 있는 "코드 다운로드" 단추를 제공합니다. 

### 유용한 CLI 명령
다음 CLI 명령은 프로젝트 및 웹 콘솔에 대한 작업을 지원합니다.
- [`code`](./commands.html#enable)는 앱의 생성된 소스 코드를 워크스테이션으로 직접 가져옵니다. 
- [`console`](./commands.html#console)은 브라우저를 열어서 {{site.data.keyword.Bluemix_notm}}에서 앱의 프로젝트 페이지를 표시합니다. 
- [`create`](./commands.html#create) 명령은 새 앱을 작성합니다. 
- [`delete`](./commands.html#delete)는 {{site.data.keyword.Bluemix_notm}} 프로젝트 영역에서 현재 앱을 삭제합니다.
- [`enable`](./commands.html#enable) 명령은 기존 서버 측 앱을 클라우드에서 사용할 수 있게 합니다.
- [`get-credentials`](./commands.html#get-credentials)는 바인딩된 서비스를 사용하기 위해 프로젝트에서 요구하는 신임 정보를 가져옵니다. 
- [`list`](./commands.html#list)는 CLI나 콘솔에서 현재 선택한 조직/영역에 작성한 모든 앱을 나열합니다. 


### 앱의 프로젝트 구조 탐색
{: exploring-project}

도구와 함께 사용하도록 설정되거나 작성된 프로젝트는 `cli-config.yml` 파일에서 캡슐화된 사전 구성 설정과 함께 제공됩니다.  `cli-config.yml`은 도구의 명령에서 사용하는 기본 항목을 포함하며, 이러한 항목은 명령행을 통해 전달된 값으로 대체될 수 있습니다.

프로젝트 구조의 추가 세부사항은 다음에서 볼 수 있습니다. 
- [Java 프로젝트](/docs/apps/projects/java_project_contents.html)
- [NodeJS 프로젝트](/docs/apps/projects/node_project_contents.html)
- [Python 프로젝트](/docs/apps/projects/python_project_contents.html)
- [Swift 프로젝트](/docs/apps/projects/swift_project_contents.html)


### 참조 블로그 및 동영상
- 동영상: [Ubuntu Linux에서 IDT 설치]()
- 블로그: [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## 코딩, 빌드 및 실행
{: #build}


일단 프로젝트가 작성되었으면 프로젝트를 더 유용하게 만드는 것은 사용자에게 달려있습니다. 일반적인 플로우는 소스 코드 편집 후 [`bx dev build`](commands.html#build)를 실행하여 앱의 언어 및 구성에 특정한 로컬 컨테이너 내에서 앱을 컴파일하는 것으로 구성되어 있습니다. 사용하는 앱의 언어와 생성기에 따라 로컬로 빌드 및 실행을 지원하기 위해 기본 설정된 하나 이상의 컨테이너가 있습니다. 일반적으로 빌드와 로컬 디버깅을 위한 "도구" 컨테이너입니다. 이 컨테이너는 대개 개발에서 사용자를 지원하기 위해 추가 도구 및 기능을 보유합니다. 또한 Cloud Foundry 또는 IBM의 Kubernetes 기반 컨테이너 환경에서 클라우드에 이미 배치된 앱의 실제 런타임 환경을 근접하게 모방하는 "실행" 컨테이너도 있습니다. 


선호하는 편집기나 IDE가 무엇이든 자유롭게 사용하여 애플리케이션을 코딩할 수 있습니다. 편집기 내에서 직접 모든 IDE 명령에 액세스할 수 있는 Microsoft VisualStudio Code(VSCode) 편집기 확장을 제공합니다. 

일단 프로젝트가 빌드되면 앱의 생성기 구성에 따라 [`bx dev run`](commands.html#run) 또는 [`bx dev debug`](commands.html#debug)를 사용하여 앱을 실행하려고 할 것입니다. 앱은 적절한 컨테이너에서 실행됩니다. 일부 앱 패턴은 지속성 또는 다른 기능 등을 앱의 여러 외부 컨테이너로 지원합니다. 이는 실행 또는 디버그 동안 자동으로 시작되고 구성됩니다. 또한 앱과 연관된 테스트 케이스를 실행하는 [`bx dev test`](commands.html#test) 명령이 있습니다.


### 로컬 컨테이너 사용 방법
{: local-containers}

{{site.data.keyword.dev_cli_long}}에서는 애플리케이션 빌드와 테스트를 용이하게 하기 위해 두 컨테이너를 사용합니다. 첫 번째는 도구 컨테이너로서 애플리케이션 빌드와 테스트에 필요한 유틸리티를 포함합니다. 이 컨테이너를 위한 Dockerfile은 [`dockerfile-tools`](commands.html#command-parameters) 매개변수로 정의됩니다. 특정 런타임의 개발에 일반적으로 사용되는 도구를 포함하고 있으므로 개발 컨테이너로 생각할 수 있습니다.

두 번째 컨테이너는 실행 컨테이너입니다. 이 컨테이너는 예를 들어 {{site.data.keyword.Bluemix}}에서 사용하기 위해 배치하는 데 적합한 양식으로 되어 있습니다. 결과적으로 애플리케이션을 시작하는 시작점이 정의됩니다. {{site.data.keyword.dev_cli_short}}을 통해 애플리케이션을 실행하도록 선택하면 이 컨테이너가 사용됩니다. 이 컨테이너를 위한 Dockerfile은 [`dockerfile-run`](commands.html#run-parameters) 매개변수로 정의됩니다. 


### 유용한 CLI 명령
다음 CLI 명령은 프로젝트 코딩, 빌드 및 실행 주기 동안 작업을 지원합니다. 
- [`build`](./commands.html#build)는 로컬 컨테이너에 프로젝트를 빌드합니다. 
- [`debug`](./commands.html#debug)는 로컬 컨테이너에서 애플리케이션을 디버깅합니다. 
- [`run`](./commands.html#run)은 로컬 컨테이너에서 애플리케이션을 실행합니다. 
- [`shell`](./commands.html#shell)은 로컬 컨테이너에서 shell을 엽니다. 
- [`status`](./commands.html#status)는 CLI에서 사용하는 컨테이너 상태를 확인합니다. 
- [`stop`](./commands.html#stop)은 컨테이너를 중지합니다. 
- [`test`](./commands.html#test)는 로컬 컨테이너에서 애플리케이션을 테스트합니다. 

### 참조 블로그 및 동영상
- [로컬 앱 디버깅](local_debug.html)





## 배치
{: deploy}

적절한 클라우드 네이티브 환경에서 다양한 여러 기능뿐 아니라 모든 배치를 관리하기 위한 완전한 기능의 DevOps 파이프라인을 활용하기를 원할 것입니다. 작성 플로우 동안 IBM Cloud의 DevOps를 사용하기 위해 앱을 설정할 수 있습니다.  기본 제공 DevOps를 사용할 준비가 되지 않았다면 사용자의 앱을 수동으로 [`bx dev deploy`](./commands.html#deploy)하거나 자체 DevOps 파이프라인 내에서 배치 명령을 사용할 수 있습니다.   



### 유용한 CLI 명령
다음 CLI 명령은 배치 프로세스 동안 프로젝트 작업을 지원합니다.
- [`console`](./commands.html#console)은 프로젝트를 위해 IBM Cloud 콘솔을 엽니다. 
- [`deploy`](./commands.html#deploy)는 IBM Cloud에 애플리케이션을 배치합니다. 
- [`view`](./commands.html#view)는 프로젝트의 URL을 표시합니다. 


### 참조 블로그 및 동영상
- 블로그: [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- 블로그: [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
