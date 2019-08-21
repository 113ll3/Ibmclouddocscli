---

copyright:
   years: 2017, 2019
lastupdated: "2019-07-12"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer plugin cli, dev plugin commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# {{site.data.keyword.dev_cli_notm}} CLI 플러그인(ibmcloud dev) 명령
{: #idt-cli}

버전: 2.1.18
릴리스 날짜: 2019년 3월 28일

2018년 5월 현재, {{site.data.keyword.cloud}} CLI 명령인 `bluemix` 및 `bx`는 이제 `ibmcloud`입니다. 그러나 나중에 제거되기 전까지는 여전히 `bluemix` 및 `bx` CLI 명령을 사용할 수 있습니다.
{: tip}

애플리케이션을 작성하고 이를 관리, 배치, 디버그 및 테스트하려면 {{site.data.keyword.dev_cli_notm}} CLI(`ibmcloud dev`) 명령을 사용하십시오.

[compound commands](#compound)를 사용하여 하나의 명령행 명령문에서 여러 개의 명령을 실행합니다.
{: tip}

## build
{: #build}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`build` 명령을 사용하여 앱을 빌드할 수 있습니다. `test`, `debug` 및 `run` 명령은 컴파일된 앱을 찾을 것을 예상하므로 이러한 명령 전에 `build` 오퍼레이션을 실행해야 합니다.

`build-cmd-debug` 구성 요소는 `run`을 제외한 모든 용도를 위해 앱을 빌드하는 데 사용됩니다. 디버깅을 위해 앱을 빌드하는 경우에는 명령행 옵션 `--debug`를 지정합니다. `build-cmd-run` 구성 요소는 `run` 명령과 함께 사용하기 위해 앱을 빌드하는 경우에 사용됩니다.

여러 컨테이너를 빌드하려면 `cli-config.yml`에 지정된 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘 ") 파일이 앱에 포함되어야 합니다. 또는 `dockerfile-tools` 명령 매개변수를 사용하여 이를 제공할 수 있습니다.

빌드를 시작하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

{{site.data.keyword.cloud_notm}}의 앱 템플리트 코드 및 구성 파일을 사용하여 이전에 작성된 앱을 다운로드하려면 `code` 명령을 사용하십시오. 앱의 두 번째 사본을 추출해야 하는 경우에 이 명령을 사용할 수 있습니다.

지정된 앱에서 코드를 다운로드하려면 다음 명령을 실행하십시오.
```
ibmcloud dev code <appName>
```
{: codeblock}

## console
{: #console}

웹 브라우저에서 {{site.data.keyword.cloud_notm}}에 있는 웹의 웹 콘솔을 열려면 `console` 명령을 사용하십시오. 사용자는 앱 폴더 내에서 `ibmcloud dev console` 명령을 실행할 수 있습니다. CLI는 {{site.data.keyword.cloud_notm}}에서 현재 디렉토리와 동일한 앱 ID를 가진 일치하는 앱을 찾으려 시도합니다. 시스템은 일치하는 이름을 찾을 수 없는 경우 특정 앱 대신 {{site.data.keyword.cloud_notm}}의 **웹 및 모바일** 대시보드를 엽니다.

사용자는 앱 이름을 제공할 수 있으며, 이렇게 하면 CLI가 폴더 또는 앱 이름을 기반으로 하는 일치 여부 판정을 건너뜁니다. 이 경우 CLI는 이름 지정된 앱의 콘솔을 웹 브라우저에서 엽니다.  

웹 브라우저로 앱의 웹 콘솔을 열려면 다음 명령을 실행하십시오.
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

리소스 유형, 언어, 스타터 킷 및 DevOps 도구 체인 옵션을 포함한 모든 정보에 대한 프롬프트를 표시하는 앱을 작성합니다 (IBM Cloud Foundry 또는 Cloud Foundry Enterprise Environment 및 Kubernetes를 포함). 앱은 현재 디렉토리에 작성됩니다.

현재 디렉토리에 앱을 작성하고 이를 서비스와 연관시키려면 다음 명령을 실행하십시오.
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`debug` 명령을 통해 앱을 디버그할 수 있습니다. 먼저 build 명령을 `--debug` 인수와 함께 사용하여 앱에 대해 빌드를 완료해야 합니다. `debug` 명령을 시작하면 cli-config.yml의 `container-port-map-debug` 값으로 정의되거나 명령행에 지정된 디버그 포트를 제공하는 컨테이너가 시작됩니다. 원하는 디버깅 도구를 포트에 연결하면 일반적인 경우와 다름없이 앱을 디버그할 수 있습니다.

먼저 앱을 컴파일하십시오.
```
ibmcloud dev build --debug
```
{: codeblock}

시작하려면, 다음 명령을 현재 앱 디렉토리에서 실행하여 디버깅을 시작하십시오.
```
ibmcloud dev debug
```
{: codeblock}

디버깅하려면 지정된 포트에 디버그 도구를 연결하십시오.

디버그 세션을 종료하려면 `CTRL-C`를 사용하십시오.

### debug 명령 매개변수
{: #debug-parameters}

다음 매개변수는 `debug` 명령 전용이며 앱 디버깅에 도움을 줍니다. 다른 명령과 공유되는 [추가 매개변수](#command-parameters)가 있습니다.

#### `container-port-map-debug`
{: #port-map-debug}

* 디버그 포트의 포트 맵핑입니다. 첫 번째 값은 호스트 OS에서 사용하는 포트이며 두 번째 값은 컨테이너의 포트입니다[`host-port:container-port`].
* 사용법: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* 디버그를 위한 코드를 빌드하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* tools 컨테이너에서 디버그를 시작하기 위한 명령을 지정하는 데 사용되는 매개변수입니다. `build-cmd-debug`가 앱을 디버그 모드로 시작하는 경우 이 매개변수를 사용하십시오.
* 사용법: `ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

{{site.data.keyword.cloud_notm}} 영역에서 앱을 제거하려면 `delete` 명령을 사용하십시오. 매개변수 없이 이 명령을 실행하여 사용 가능한 앱을 나열한 후 번호 지정된 목록에서 삭제할 앱을 선택할 수 있습니다. 앱 코드 및 디렉토리는 로컬 디스크 공간에서 제거되지 않습니다.

앱을 {{site.data.keyword.cloud_notm}}에서 삭제하려면 다음 명령을 실행하십시오.
```
ibmcloud dev delete [appName] [--force,-f]
```
{: codeblock}

{{site.data.keyword.cloud_notm}} 서비스가 제거되지 않습니다.
{: note}


### delete 명령 매개변수
{: #delete-command-parameters}

#### `force`
{: #delete-force}

* 애플리케이션 삭제에 대한 프롬프트 확인을 건너뛰기 위해 선택적으로 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev delete [appName] --force`

## deploy
{: #deploy}

앱을 Cloud Foundry 앱 또는 컨테이너로 배치할 수 있습니다.

앱을 {{site.data.keyword.cloud_notm}}에 Cloud Foundry 애플리케이션으로 배치하려면 앱의 루트 디렉토리에 `manifest.yml` 파일이 있어야 합니다.

앱을 컨테이너로 배치하기 전에 [Kubernetes](https://kubernetes.io/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 및 [Helm](https://github.com/helm/helm){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")을 로컬에 설치해야 합니다. Helm 클라이언트 버전이 Helm 서버 버전보다 높지 않도록 하십시오. `helm version`을 실행하여 두 버전 모두 확인할 수 있습니다. 클라이언트로는 v2.4.2 버전을 사용하는 것이 좋습니다.

앱을 Kubernetes에 배치하려면 `cli-config.yml`에서 `deploy-target`을 `container`로 지정하거나 매개변수 `-t container`를 사용해야 합니다.

Kubernetes 배치를 구성하는 데 필요한 다른 매개변수 또한 `cli-config.yml`에 지정하거나 명령행 인수를 사용하여 지정할 수 있습니다. `cli-config.yml`에서 이러한 항목을 정의하지 않은 경우에는 `-t container` 매개변수를 사용하여 배치해야 합니다. 그러면 모든 기타 값에 대한 프롬프트가 표시됩니다.

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

`cli-config.yml`에서는 예에 표시되어 있는 바와 같이 `chart-path` 특성에 Helm 차트의 위치를 정의하고 `deploy-image-target`을 구성할 수 있습니다. `cli-config.yml`의 `deploy-image-target` 요소는 `chart/values.yml` 파일의 `repository` 및 `tag` 요소 대신 사용됩니다. 구체적으로 {{site.data.keyword.cloud_notm}}에 배치하려면 구성 요소 `ibm-cluster`를 {{site.data.keyword.cloud_notm}}에서 작성한 Kubernetes 클러스터의 이름으로 설정하십시오.

앱을 빌드하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.  
```
ibmcloud dev build
```
{: codeblock}

앱을 배치하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev deploy
```
{: codeblock}

### {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment에 배치 
{: #deploy-cfee}

{{site.data.keyword.cloud_notm}} Foundry Enterprise Environment에 배치할 수 있습니다. 그러기 위해서는 `ibmcloud target --cf`를 사용하여 이 환경에 대한 올바른 로컬 환경을 구성한 다음 목록에서 올바른 환경을 선택하십시오. 그런 다음 {{site.data.keyword.cloud_notm}} Public Cloud Foundry의 경우와 같이 `deploy` 명령을 사용할 수 있습니다.

### deploy 명령 매개변수
{: #deploy-parameters}

다음 매개변수는 `deploy` 명령과 함께 사용하거나 앱의 `cli-config.yml` 파일을 직접 업데이트하여 사용할 수 있습니다. 다른 명령과 공유되는 [추가 매개변수](#command-parameters)가 있습니다.

#### `chart-path`
{: #chart-path}

* 컨테이너 배치에서 배치에 사용되는 Helm 차트의 위치를 지정하기 위해 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* 완료될 배치의 유형을 표시하기 위해 사용되는 매개변수입니다. 기본 배치 유형은 빌드팩입니다.
* 사용법: `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* 컨테이너 배치에서 배치의 대상 이미지 이름으로 사용되는 매개변수입니다. 이 값에는 버전이 포함되지 않아야 합니다. 예를 들어, image-name:{version}입니다. 버전은 `deploy`에 의해 자동으로 증가되어 추가되기 때문입니다.
* 사용법: `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* {{site.data.keyword.cloud_notm}}로의 컨테이너 배치에서 Kubernetes 클러스터의 이름을 정의하기 위해 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Cloud Foundry에 배치할 때 앱의 호스트 이름을 정의하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev deploy --host [hostname]`

#### `domain`
{: #domain}

* Cloud Foundry에 배치할 때 앱의 도메인을 정의하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev deploy --domain [domain]`

## diag
{: #diag}

`diag` 명령은 {{site.data.keyword.dev_cli_notm}} CLI에 대한 설치된 종속 항목의 버전 정보를 표시하기 위한 진단으로 사용됩니다. `diag` 실행은 종속 항목이 누락되었는지 판별하거나 디버깅 문제점에 대한 도움을 받을 때 유용합니다.

다음 명령을 실행하여 설치된 종속 항목의 버전을 표시하십시오.
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

기존 {{site.data.keyword.cloud_notm}} 앱과 연결, {{site.data.keyword.cloud_notm}} 관리 및 {{site.data.keyword.cloud_notm}} Kubernetes, Cloud Foundry 또는 Cloud Foundry Enterprise Environment로 배치되는 {{site.data.keyword.cloud_notm}} 도구 체인과 같은 옵션으로 애플리케이션을 편집하십시오. {{site.data.keyword.cloud_notm}}의 앱에 연결된 로컬 앱이 있으면 `edit`를 사용하여 새 서비스를 추가하거나, 기존 서비스를 연결하고 연결을 끊거나, 기존 서비스를 계정에서 제거할 수 있습니다. 또한 앱에 대한 {{site.data.keyword.cloud_notm}} 도구 체인을 작성하거나 볼 수 있습니다. 앱 디렉토리의 루트에서 다음 명령을 실행하십시오.
```
ibmcloud dev edit
```
{: codeblock}

계정에 기존 서비스가 없는 경우 이 명령은 앱에 연결할 서비스를 선택할 수 있는 서비스 그룹 목록을 표시합니다.

계정에 기존 서비스가 있는 경우 이 명령은 이러한 서비스의 목록, 그리고 각 서비스와 앱 간의 연결 여부를 표시합니다.

* 연결된 서비스는 해당 서비스와 앱의 연결을 끊거나, 계정에서 해당 서비스를 삭제하여 모든 앱으로부터 해당 서비스의 연결을 끊는 옵션을 제공합니다.

* 연결되지 않은 서비스는 해당 서비스를 앱에 연결하거나 계정에서 해당 서비스를 삭제하는 옵션을 제공합니다. 기존 서비스를 연결하면 인증 정보 및 소스 코드와 같은 파일도 다운로드됩니다.

또한 앱에 서비스를 추가할 수 있으며 이를 통해 서비스 선택 프롬프트를 안내하여 인증 정보 파일 또는 소스 코드와 같은 파일을 다운로드합니다.

## enable
{: #enable}

{{site.data.keyword.cloud_notm}} 배치에 기존 앱을 사용할 수 있도록 설정합니다. `enable` 명령은 기존 앱의 언어를 자동으로 발견하려 시도한 후 필요한 추가 정보에 대한 프롬프트를 표시합니다. 로컬 Docker 컨테이너, Cloud Foundry 배치, Cloud Foundry Enterprise Environment 배치 또는 Kubernetes 컨테이너 배치에 사용할 파일을 생성합니다. 모든 배치 환경은 수동 `deploy` 또는 DevOps 도구 체인을 통해 사용할 수 있습니다.

{{site.data.keyword.cloud_notm}}에 로그인한 상태로 이 로컬 앱을 이미 {{site.data.keyword.cloud_notm}}에 있는 앱과 연결하거나 새 {{site.data.keyword.cloud_notm}} 앱을 작성할 수 있습니다. 서비스 및 DevOps 도구 체인과 같은 {{site.data.keyword.cloud_notm}} 기능을 활용하려면 {{site.data.keyword.cloud_notm}}의 앱이 필요합니다. Git 저장소에서 복제된 앱에 대한 {{site.data.keyword.cloud_notm}} 앱이 작성되면 {{site.data.keyword.cloud_notm}} 앱의 구성에 이 저장소가 포함됩니다. 

`enable` 명령은 베타 기능입니다. `enable` 명령 사용에 문제가 있는 경우, [문제점 해결](/docs/cli?topic=cloud-cli-troubleshoot)을 참조하십시오. 특히 `enable`은 모바일 앱 또는 프레임워크를 대상으로 하지 않습니다. 여러 배치 가능한 자산을 생성하는 복합 앱의 경우 앱의 각 컴포넌트가 개별적으로 사용으로 설정되어야 합니다. 

현재 디렉토리에 있는 기본 앱을 사용하려면 다음 명령을 실행하십시오.
```
ibmcloud dev enable
```
{: codeblock}

필요한 파일들이 있으면 올바른 앱 구조를 위한 애플리케이션 언어 발견이 수행됩니다.  

* `package.json` 파일이 있는 경우 Node.js 앱이 식별됩니다.
* `package.swift` 파일이 있는 경우 Swift 앱이 식별됩니다.
* `setup.py` 또는 `requirements.txt` 파일이 있는 경우 Python 앱이 식별됩니다.
* `pom.xml` 또는 `build.gradle` 파일이 있는 경우 Java&trade; 앱이 식별됩니다.
	* `pom.xml`이 있는 경우 Maven 앱이 식별됩니다.
	* `build.gradle`이 있는 경우 Gradle 앱이 식별됩니다.

또한 `--language` 인수를 사용하여 발견된 앱 언어를 대체할 수도 있습니다. 올바르며 완전한 앱만 지원됩니다. enable 명령은 소스 코드를 수정하지 않습니다.

### enable 언어 옵션
{: #enable-language-options}

언어 옵션에는 다음 항목이 포함됩니다.
* Node
* Swift
* Python
* Java EE(Java&trade; - Java&trade; EE로 해석)
* Java-mp(Java&trade; - Java&trade; MicroProfile로 해석)
* Java-spring(Java&trade; - Spring Framework로 해석)

`ibmcloud dev enable` 명령을 사용하여 작성된 파일 중 앱 폴더에 있는 기존 파일과 이름이 충돌하는 파일은 `.merge` 파일 확장자를 사용하여 저장됩니다.

### enable 명령 매개변수
{: #enable-parameters}

다음 매개변수는 `enable` 명령과 함께 사용하거나 앱의 `cli-config.yml` 파일을 직접 업데이트하여 사용할 수 있습니다. 다른 명령과 공유되는 [추가 매개변수](#command-parameters)가 있습니다.

#### `language`
{: #enable-language}

* 사용으로 설정되는 앱의 언어를 지정하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* 이미 사용으로 설정된 앱을 다시 사용으로 설정하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* 로컬로 인에이블먼트 파일을 작성하고 {{site.data.keyword.cloud_notm}}에 앱을 작성하지 못하도록 하는 매개변수입니다.
* 사용법: `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

연결된 서비스를 사용할 수 있도록 앱에서 필요로 하는 인증 정보를 가져옵니다.

## help
{: #help}

기본적으로 조치 또는 인수가 전달되지 않았거나 'help' 조치가 제공된 경우 이 명령은 일반 "도움말" 텍스트를 표시합니다. 표시되는 일반 도움말은 기본 인수에 대한 설명 및 사용 가능한 조치에 대한 목록을 포함합니다.  

일반 도움말 정보를 표시하려면 다음 명령을 실행하십시오.
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

리소스 그룹 내의 모든 {{site.data.keyword.cloud_notm}} 앱을 나열할 수 있습니다.

앱을 나열하려면 다음 명령을 실행하십시오.
```
ibmcloud dev list
```
{: codeblock}

## pipeline-get
{: #pipeline-get}

파이프라인의 세부사항을 봅니다.

```
ibmcloud dev pipeline-get [pipelineID] [--json]
```
{: codeblock}

### pipeline-get 명령 매개변수
{: #pipeline-get-command-parameters}

#### `json`
{: #json-get}

* 파이프라인 세부사항을 JSON 형식으로 출력하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev pipeline-get [pipelineID] --json`

## pipeline-run
{: #pipeline-run}

파이프라인을 실행합니다.
```
ibmcloud dev pipeline-run [pipelineID] [--stage-id stageID] [--json]
```
{: codeblock}

### pipeline-run 명령 매개변수
{: #pipeline-run-command-parameters}

#### `stage-id`
{: #run-stage-id}

* 선택적으로 실행할 파이프라인의 단계를 선택하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev pipeline-run [pipelineID] --stage-id [stageID]`

#### `json`
{: #json-run}

* 파이프라인의 호출 세부사항을 JSON 형식으로 출력하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev pipeline-run [pipelineID] --json`

## pipeline-log
{: #pipeline-log}

`pipeline-log` 명령을 사용하여 최근 파이프라인 로그를 볼 수 있습니다. 

* 파이프라인 ID가 인수로 지정되면 해당 파이프라인에 대해 모든 단계 내의 모든 작업에 대한 모든 로그가 인쇄됩니다.
* 단계 ID 플래그가 채워지면 로그가 파이프라인 내의 해당 단계에 의해 필터링됩니다. 
* 작업 ID가 단계 ID로 지정되면 로그가 단계 내의 작업만으로 필터링됩니다. 
* 작업 실행 ID가 단계 ID 및 작업 ID와 함께 지정되면 지정된 작업 실행 ID와 일치하는 모든 사용 가능한 로그 중에서 검색이 수행됩니다.

사용법:
```
ibmcloud dev pipeline-log [pipelineID] [--stage-id stageID] [--job-id jobID] [--job-exec-id jobExecutionID]
```
{: codeblock}

### pipeline-log 명령 매개변수
{: #pipeline-log-command-parameters}

#### `stage-id`
{: #log-stage-id}

* 로그를 단계 ID로 필터링하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID]`

#### `job-id`
{: #job-id}

* 로그를 작업 ID로 필터링하는 데 사용되는 매개변수입니다.
* `stage-id` 플래그가 필요합니다.
* 사용법: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID]`

#### `job-exec-id`
{: #job-exec-id}

* 로그를 작업 실행 ID로 필터링하는 데 사용되는 매개변수입니다.
* `stage-id` 플래그가 필요합니다.
* `job-id` 플래그가 필요합니다.
* 사용법: `ibmcloud dev pipeline-log [pipelineID]  --stage-id [stageID] --job-id [jobID] --job-exec-id [jobExecutionID]`

## pipeline-open
{: #pipeline-open}

`pipeline-open` 명령을 통해 파이프라인에 대한 URL을 봅니다. `pipeline-open` 명령은 또한 이 URL을 기본 브라우저에서 엽니다.
```
ibmcloud dev pipeline-open [pipelineID]
```
{: codeblock}

## run
{: #run}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`run` 명령을 통해 앱을 실행할 수 있습니다. 먼저 `build` 명령을 사용하여 앱에 대해 빌드를 완료해야 합니다. `run` 명령을 실행하면 run 컨테이너가 시작되며 `container-port-map` 매개변수로 정의된 포트를 노출합니다. run 컨테이너 `Dockerfile`이 이 단계를 완료하는 데 필요한 시작점을 포함하지 않는 경우에는 앱을 호출하는 데 `run-cmd` 매개변수가 사용됩니다.

여러 컨테이너를 실행하려면 `cli-config.yml`에 지정된 [Compose](https://docs.docker.com/compose/overview/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘 ") 파일이 앱에 포함되어야 합니다. 또는 `dockerfile-run` 명령 매개변수를 사용하여 이를 제공할 수 있습니다.

먼저 앱을 컴파일하십시오.
```
ibmcloud dev build
```
{: codeblock}

앱을 시작하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev run
```
{: codeblock}

세션을 종료하려면 `CTRL-C`를 사용하십시오.

### run 명령 매개변수
{: #run-parameters}

다음 매개변수는 `run` 명령 전용이며 run 컨테이너 내에서 앱을 관리하는 데 도움을 줍니다. 다른 명령과 공유되는 [매개변수](#command-parameters)가 있습니다.

#### `container-name-run`
{: #container-name-run2}

* run 컨테이너의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev run --container-name-run [<appName>]`

#### `container-path-run`
{: #container-path-run}

* 실행 시 공유할 컨테이너 내의 위치입니다.
* 사용법: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* 실행 시 컨테이너에서 공유할 호스트 시스템 내의 위치입니다.
* 사용법: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* run 컨테이너의 Dockerfile입니다.
* 여러 컨테이너에서 실행하려는 경우, Compose 파일을 사용하십시오.
* 여러 compose 파일을 사용하려면 쉼표로 구분된 파일 이름 목록을 큰따옴표로 묶으십시오.
* 사용법: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* 사용법: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* `dockerfile-run`에서 작성할 이미지입니다.
* 사용법: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* run 컨테이너에 있는 코드를 실행하는 데 사용되는 매개변수입니다. 이미지가 앱을 시작하는 경우 이 매개변수를 사용하십시오.
* 사용법: `ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`shell` 명령을 사용하여 run 또는 tools 컨테이너 내에서 쉘을 열 수 있습니다.

다음 명령을 실행하면
```
ibmcloud dev shell
```
{: codeblock}

{{site.data.keyword.dev_cli_short}} CLI가 앱의 Docker 컨테이너에 대한 대화식 쉘을 엽니다. shell 명령의 기본 대상 컨테이너는 `cli-config.yml` 파일의 `container-shell-target` 값으로 정의되며, 올바른 값은 `run` 또는 `tools`입니다. 이 값이 정의되지 않거나 올바르지 않은 값이 지정된 경우 `shell` 명령은 기본적으로 `tools` 컨테이너를 대상으로 합니다. shell 명령은 해당 Dockerfile의 `WORKDIR` 명령어로 지정된 디렉토리에 컨테이너를 엽니다. Dockerfile에 `WORKDIR`이 나열되지 않은 경우에는 컨테이너 루트가 작업 디렉토리로 사용됩니다. 자세한 정보는 [이 참조](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")에서 확인하십시오.

또는 `run` 또는 `tools`를 인수로 전달하도록 결정할 수 있으며 이렇게 하면 해당 컨테이너가 선택되고 이 컨테이너에 대해 쉘이 열립니다. 마찬가지로, `container-name` 매개변수를 사용하여 쉘하려는 위치의 컨테이너 이름을 전달할 수 있습니다. 그러나 이 플래그는 실행 중인 컨테이너가 없는 경우를 위해 예약됩니다. `run` 및 `tools` 인수는 더 유연하며 한 컨테이너가 실행 중인 상태에서 컨테이너 간에 전환할 수 있습니다. 예를 들어, tools 컨테이너가 실행 중인 상태에서 `ibmcloud dev shell run`을 실행하는 경우 `tools` 컨테이너가 중지되고 `run` 컨테이너가 시작되며, 이는 반대의 경우도 마찬가지입니다.

`shell` 명령을 실행할 때 대상 `run` or `tools` 컨테이너가 이미 실행 중이 아닌 경우에는 대상 컨테이너가 시작됩니다. 그러나 Dockerfile의 기본 `Cmd` 또는 `Entrypoint`는 서버 프로세스를 시작하는 대신 직접 쉘에서 실행하기 위해 대체됩니다. 따라서 사용자가 `run` 또는 `tools` 컨테이너를 시작한 다음 임의의 또는 사용자 정의 명령을 사용하여 서버를 수동으로 시작할 수 있습니다.

`container-shell` 매개변수를 사용하여 열려는 쉘을 지정할 수도 있습니다. 기본적으로는 `/bin/sh`가 사용됩니다. bash 쉘을 사용하려는 경우에는 `container-shell` 값을 `/bin/bash`로 지정하십시오. 그러나 모든 Linux&trade; 변형에서 bash가 자동으로 사용 가능한 것은 아니라는 점을 기억하십시오.

플래그 외에 이 명령에 전달하는 추가 매개변수는 쉘이 열린 후 실행하는 명령으로 구문 분석됩니다. 명령을 제공하면 컨테이너 내의 쉘은 해당 명령을 실행한 후 종료되며 터미널로 리턴됩니다.

예를 들면, &trade; `bx dev shell tools ls`를 호출하여 tools 컨테이너 쉘 내에서 Linux `ls` 명령을 실행할 수 있습니다. 또한 `ibmcloud dev shell "ls -la"`와 같이 인수를 따옴표로 묶어 쉘 명령 실행에 전달되는 플래그를 지정할 수도 있습니다.

### shell 명령 매개변수
{: #shell-parameters}

#### `container-name`
{: #container-name}

* 쉘하려는 위치의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* 컨테이너 내에서 실행할 쉘을 지정합니다(기본값은 /bin/sh).
* 사용법: `ibmcloud dev shell --container-shell [path/to/shell]`

## status
{: #status}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`container-name-run` 및 `container-name-tools`로 정의된, {{site.data.keyword.dev_cli_short}} CLI에서 사용하는 컨테이너의 상태를 조회할 수 있습니다.

컨테이너 상태를 확인하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev status
```
{: codeblock}

[status 명령 매개변수](#command-parameters)

## stop
{: #stop}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`stop` 명령을 통해 컨테이너를 중지할 수 있습니다.

`cli-config.yml` 파일에 정의된 tools 및 run 컨테이너를 중지하려면 다음 명령을 실행하십시오.
```
ibmcloud dev stop
```
{: codeblock}

`cli-config.yml` 파일에 정의되지 않은 컨테이너를 중지하려는 경우에는 추가 명령행 매개변수를 지정하여 이를 대체할 수 있습니다. `cli-config.yml` 파일 또는 명령행에 컨테이너가 지정되지 않은 경우에는 stop 명령이 단순히 리턴됩니다.

### stop 명령 매개변수
{: #stop-parameters}

다음 매개변수는 `stop` 명령에 사용됩니다. 다른 명령과 공유되는 [매개변수](#command-parameters)가 있습니다.

#### `container-name-run`
{: #container-name-run}

* run 컨테이너의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`
{: #container-name-tools}

* tools 컨테이너의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev stop --container-name-tools [<appName>]`

## test
{: #test}

Windows&trade;를 사용하는 경우 Windows&trade; 10 Pro 이상을 실행해야 합니다.

`test` 명령을 통해 앱을 테스트할 수 있습니다. 먼저 `build --debug` 명령을 사용하여 앱에 대해 빌드를 완료해야 합니다. 그 후에는 앱에 대해 `test-cmd`를 시작하기 위해 tools 컨테이너가 사용됩니다.

먼저 앱을 컴파일하십시오.
```
ibmcloud dev build --debug
```
{: codeblock}

앱을 테스트하려면 다음 명령을 실행하십시오.
```
ibmcloud dev test
```
{: codeblock}

### test 명령 매개변수
{: #test-parameters}

다음 매개변수는 `test` 명령 전용입니다. 다른 명령과 공유되는 [매개변수](#command-parameters)가 있습니다.

#### `test-cmd`
{: #test-cmd}

* tools 컨테이너에서 코드를 테스트하기 위한 명령을 지정하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev test --test-cmd /the/test/command`

## toolchain-delete
{: #toolchain-delete}

도구 체인을 삭제합니다. 도구 체인 이름이 제공되지 않은 경우 목록에서 하나를 선택할 수 있습니다. 도구 체인의 목록은 현재 대상으로 지정된 리소스 그룹 및 지역에 따라 다릅니다.

대상으로 지정된 리소스 그룹은 `IBMCLOUD API Key`에서 찾을 수 있습니다. 자세한 정보는 [대상 계정, 지역 또는 리소스 그룹 설정 또는 보기](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)를 참조하십시오.
```
ibmcloud dev toolchain-delete [toolchainName] [--force,-f]
```
{: codeblock}

### toolchain-delete 명령 매개변수
{: #toolchain-delete-command-parameters}

#### `force`
{: #force}

* 도구 체인 삭제에 필요한 프롬프트 확인을 건너뛰기 위해 사용되는 매개변수
* 사용법: `ibmcloud dev toolchain-delete [toolchainName] --force`

## toolchain-get
{: #toolchain-get}

도구 체인의 세부사항을 봅니다. 도구 체인 이름이 제공되지 않은 경우 목록에서 하나를 선택할 수 있습니다. 

`IBMCLOUD API Key`에서 대상으로 지정된 리소스 그룹을 사용합니다. 자세한 정보는 [대상 계정, 지역 또는 리소스 그룹 설정 또는 보기](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)를 참조하십시오. 일부 Cloud Foundry 기반 도구 체인은 이 명령과 호환되지 않을 수 있습니다.
```
ibmcloud dev toolchain-get [toolchainName] [--json]
```
{: codeblock}

### toolchain-get 명령 매개변수
{: #toolchain-get-command-parameters}

#### `json`
{: #json-toolchain-get}

* 도구 체인 세부사항을 JSON 형식으로 출력하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev toolchain-get [toolchainName] --json`.

## toolchain-open
{: #toolchain-open}

`toolchain-open` 명령을 통해 도구 체인에 대한 URL을 봅니다. `toolchain-open` 명령은 또한 이 URL을 기본 브라우저에서 엽니다. 도구 체인 이름이 제공되지 않은 경우 도구 체인을 선택할 수 있는 목록이 제공됩니다.
```
ibmcloud dev toolchain-open [toolchainName]
```
{: codeblock}

## toolchains
{: #toolchains}

현재 리소스 그룹의 도구 체인 목록을 봅니다. 

`IBMCLOUD API Key`에서 대상으로 지정된 리소스 그룹을 사용합니다. 자세한 정보는 [대상 계정, 지역 또는 리소스 그룹 설정 또는 보기](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)를 참조하십시오. 일부 Cloud Foundry 기반 도구 체인은 이 명령과 호환되지 않을 수 있습니다.
```
ibmcloud dev toolchains [--json]
```
{: codeblock}

### toolchains 명령 매개변수
{: #toolchains-command-parameters}

#### `json`
{: #json-toolchains}

* 도구 체인을 JSON 형식으로 출력하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev toolchains --json`

## view
{: #view}

`view` 명령을 통해 앱이 배치된 URL을 볼 수 있습니다. 보려는 앱의 루트 디렉토리에서 이 명령을 실행하십시오. `view` 명령은 또한 이 URL을 기본 브라우저에서 엽니다.

Cloud Foundry에 배치된 앱의 경우, URL은 앱의 호스트 이름 및 앱의 도메인으로 구성됩니다.

Kubernetes에 배치된 앱의 경우, URL은 배치된 노드의 IP 주소 및 공용 포트로 구성됩니다. 이 명령에서 앱이 Kubernetes에 배치되었다고 판별하는 경우 CLI 도구는 확인을 위한 프롬프트를 표시합니다. 사용자가 앱이 실제로 Kubernetes에 배치되지 않았다고 지정하는 경우에는 Cloud Foundry URL이 표시됩니다. 이 명령이 Kubernetes 배치 앱에 대한 URL을 표시할 것으로 예상한 경우에는 `cli-config.yml`이 `chart-path`에 대한 항목을 포함하고 있는지 확인하거나 [여기](#chart-path)에 표시되어 있는 바와 같이 명령행을 통해 이를 제공하십시오.

앱을 보려면 다음 명령을 실행하십시오.
```
ibmcloud dev view
```
{: codeblock}

### view 명령 매개변수
{: #view-parameters}

다음 매개변수는 `view` 명령 전용입니다.

#### `deploy-target`
{: #commands-deploy-target}

* 프롬프트를 무시할 배치의 유형을 표시하기 위해 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* 브라우저를 열지 않도록 지정하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Cloud Foundry 및 Kubernetes 앱 URL에 추가할 프로젝트의 루트입니다.
* 사용법: `ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* 컨테이너 배치를 대상으로 하는 경우에 Kubernetes 클러스터의 이름을 정의하기 위해 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev view --ibm-cluster [cluster-name]`

## 복합 명령
{: #compound}

{{site.data.keyword.cloud_notm}} 개발자 도구 명령을 `/` 구분 기호로 구분하여 한 명령행 명령문에서 여러 명령을 실행할 수 있습니다. 복합 명령을 지정한 후에는 추가 명령행 플래그를 사용할 수 있습니다. 다음 명령은 복합 명령 사용 방법에 대한 예입니다.
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

모든 플래그는 마지막 명령 뒤에 와야 하며 해당 플래그가 연관된 모든 명령에 적용됩니다. 예를 들어, `ibmcloud dev build/deploy/view -t container --trace`에서 `--trace` 플래그는 세 명령 모두에 적용 가능하지만 `-t`는 마지막 두 명령에만 적용 가능하므로 `build` 명령에는 적용되지 않습니다.

이 기능을 사용할 수 있는 명령:
`build, debug, deploy, get-credentials, run, stop, test, view`

어떤 이유에서든 한 명령이 실패하면 후속 명령은 실행되지 않습니다.

`debug` 또는 `run` 뒤에 명령이 있는 경우에는 `debug` 또는 `run`이 현재 터미널 창에서 프로세스를 강제 종료하는 것 외의 방법으로 종료된 경우에만 실행이 계속됩니다. `CTRL+C`를 입력하여 프로세스를 강제 종료하고 후속 명령을 실행하지 마십시오. 예를 들면, 실행 중인 컨테이너를 중지하고 다음 명령 실행을 계속하기 위해 다른 터미널 창에서 `ibmcloud dev stop`을 실행할 수 있습니다.

## build, debug, run 및 test용 매개변수
{: #command-parameters}

다음 매개변수는 `build|debug|run|test` 명령과 함께 사용하거나 앱의 `cli-config.yml` 파일을 직접 업데이트하여 사용할 수 있습니다. 추가 매개변수는 [`debug`](#debug-parameters) 및 [`run`](#run-parameters) 명령에 대해 사용 가능합니다.

명령행에 입력된 명령 매개변수가 `cli-config.yml` 구성보다 우선합니다.
{: note}

#### `config-file`  
{: #config-file}

* 명령에 사용할 `cli-config.yml` 파일을 지정합니다.
* 사용법: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* run 컨테이너의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev <run|status|stop> --container-name-run [<appName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* tools 컨테이너의 컨테이너 이름입니다.
* 사용법: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<appName>]`

#### `host-path-tools`
{: #host-path-tools}

* 빌드, 디버그 및 테스트를 위해 공유할 호스트 내의 위치입니다.
* 사용법: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* 빌드, 디버그 및 테스트를 위해 공유할 컨테이너 내의 위치입니다.
* 사용법: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* 컨테이너의 포트 맵핑입니다. 첫 번째 값은 호스트 OS에서 사용하는 포트이며 두 번째 값은 컨테이너의 포트입니다[`host-port:container-port`].
* 사용법: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* tools 컨테이너의 Dockerfile입니다.
* 사용법: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* `dockerfile-tools`에서 작성할 이미지입니다.
* 사용법: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* 호스트 시스템과 run 컨테이너 간의 마운트를 정의하려면 이 옵션을 사용하십시오.
* `host-path-run` 및 `container-path-run` 값은 이 목록의 시작 부분에 삽입됩니다.
* 예기치 않은 결과가 발생하는 것을 방지하기 위한 우수 사례로서, 사용자는 동일한 마운트 설정을 사용하여 빌드 및 실행을 수행할 수 있습니다.
* 사용법: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* 호스트 시스템과 tools 컨테이너 간의 마운트를 정의하려면 이 옵션을 사용하십시오.
* `host-path-tools` 및 `container-path-tools` 값은 이 목록의 시작 부분에 삽입됩니다. * 예기치 않은 결과가 발생하는 것을 방지하기 위한 우수 사례로서, 사용자는 동일한 마운트 설정을 사용하여 빌드 및 디버그를 수행할 수 있습니다.
* 사용법: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* 디버그 외의 모든 용도를 위한 코드를 빌드하기 위한 명령을 지정하는 데 사용되는 매개변수입니다.
* 사용법: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* 상세 출력을 제공하려면 이 매개변수를 사용하십시오.
* 사용법: `ibmcloud dev <build|debug|run|test> --trace`
