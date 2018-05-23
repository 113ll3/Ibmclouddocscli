---
copyright:
  years: 2017, 2018
lastupdated: "2018-05-02"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# IBM Cloud Developer 도구 문제점 해결
{: #ts}

{{site.data.keyword.dev_cli_notm}}에 대한 일부 알려진 문제가 임시 해결책과 함께 문서화되어 있습니다.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## 알려진 문제
{: #knownissues}

다음 절에서는 알려진 문제 및 가능한 해결책에 대해 설명합니다.


### 비모바일 패턴이 있는 프로젝트를 작성하는 경우 호스트 이름에 오류 발생
{: #hostname}

웹 앱, BFF 또는 마이크로서비스 패턴에서 프로젝트를 작성하기 위해 {{site.data.keyword.dev_cli_short}}을 사용하는 경우 다음 오류가 표시될 수 있습니다.

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### 원인
{: #hostname-cause}
   
이 오류는 로그인 토큰이 만료되어 발생합니다.


#### 해결책
{: #hostname-resolution}

다시 로그인하십시오.

```
bx login
```
{: codeblock}


### {{site.data.keyword.dev_cli_short}}의 일반 장애
{: #general}

{{site.data.keyword.dev_cli_short}} create, delete, list 또는 code 명령을 사용하는 경우 다음 오류가 발생할 수 있습니다.

```
Failed to <command> project.
```
{: codeblock}


#### 원인
{: #general-cause}
   
이 오류는 로그인 토큰이 만료되어 발생합니다.


#### 해결책
{: #general-resolution}

다시 로그인하십시오.

```
bx login
```
{: codeblock}


### 오류: 새 프로젝트를 실행할 때 해당 이미지가 없음
{: #nosuchimage}

먼저 프로젝트를 빌드하지 않고 실행하면 다음 오류가 표시될 수 있습니다.

```
$ bx dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### 원인
{: #nosuchimage-cause}

프로젝트를 실행하기 전에 먼저 빌드해야 합니다. 


#### 해결책
{: #nosuchimage-resolution}

애플리케이션을 빌드하려면 현재 프로젝트 디렉토리에서 다음 명령을 실행하십시오.

```
bx dev build
```
{: codeblock}

애플리케이션을 시작하려면 현재 프로젝트 디렉토리에서 다음 명령을 실행하십시오.

```
bx dev run
```


### {{site.data.keyword.objectstorageshort}} 기능을 추가할 때 서비스 브로커 오류
{: #os}

{{site.data.keyword.objectstorageshort}} 기능으로 두 프로젝트를 작성하기 위해 {{site.data.keyword.dev_cli_short}}을 사용하는 경우 다음 오류가 표시될 수 있습니다.

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### 원인
{: #os-cause}
   
이 오류는 무료 {{site.data.keyword.objectstorageshort}} 사용제의 1개 인스턴스만 제공하는 {{site.data.keyword.objectstorageshort}} 서비스로 인해 발생합니다.


#### 해결책
{: #os-resolution}

이 오류를 피하기 위해 다른 플랜을 선택하라는 프롬프트가 표시됩니다.


### 프로젝트 작성 중에 코드 가져오기 실패
{: #code}

프로젝트를 작성하기 위해 {{site.data.keyword.dev_cli_short}}을 사용하는 경우 다음 오류가 표시될 수 있습니다.
	
```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
	

#### 원인
{: #code-cause}

이 오류는 내부 제한시간 초과로 인한 것입니다.
	

#### 해결책
{: #code-resolution}

다음 방법 중 하나로 코드를 가져올 수 있습니다.

* CLI를 사용하여 다음 명령을 실행하십시오.

   ```
   bx dev code <your-project-name>
   ```
   {: codeblock}

   프로젝트 작성 동안 지정한 프로젝트 이름으로 `<your-project-name>`을 대체하십시오.

* {{site.data.keyword.dev_console}}을 사용하십시오.

	1. {{site.data.keyword.dev_console}}에서 [프로젝트 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.{DomainName}/developer/projects)를 선택한 다음 **코드 가져오기**를 클릭하십시오.

	2. **코드 생성**을 클릭하십시오.

	3. 코드가 생성되면 **코드 다운로드**를 클릭하십시오.


### Node.js 프로젝트에 대해 `bx dev run` 실행 중 오류
{: #node}

Node.js 웹 또는 BFF 프로젝트에 대해 {{site.data.keyword.dev_cli_short}}으로 `bx dev run`을 실행하는 동안 다음 오류가 표시될 수 있습니다.

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### 원인
{: #node-cause}
   
이 오류는 `appmetrics` 모듈이 다른 아키텍처에 설치될 때 발생할 수 있습니다. 한 아키텍처에 설치된 기본 npm 모듈은 다른 아키텍처에서 작동하지 않습니다. 포함된 Docker 이미지는 Linux 커널을 기반으로 합니다.


#### 해결책
{: #node-resolution}

`node_modules` 폴더를 삭제하고 `bx dev run`을 다시 실행하십시오.


### Bluemix에 배치 실패
{: #failuretodeploy}

{{site.data.keyword.dev_cli_short}}으로 Bluemix에 배치하려고 시도할 수 있으며 Bluemix에 배치되지 않지만 오류는 발생하지 않습니다.


#### 원인
{: #cause1}

계정에 로그인되지 않았을 수 있습니다. 

#### 해결책
{: #resolution1}

로그인하고 다시 시도하십시오.

```
bx login
```


### Bluemix에서 Kubernetes에 배치 실패
{: #failuretodeploytokube}

클러스터 이름에 대한 초기 프롬프트 이후에 이 장애가 발생할 수 있습니다.

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### 원인
{: #cause2}

올바르지 않은 클러스터 이름 때문일 가능성이 높고 동일한 명령을 `--trace`와 함께 실행하여 확인할 수 있으며 오류 출력에 표시될 수 있습니다.

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### 해결책
{: #resolution2}

올바른 클러스터를 사용 중인지 확인하고 다음을 실행하여 배치에 대해 클러스터를 구성했는지 확인하십시오.

```
bx cs cluster-config <cluster-name>
```


### Bluemix에서 Kubernetes에 배치 실패

배치 이미지 대상에 대한 프롬프트 이후에 이 장애가 발생할 수 있습니다.

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### 원인
{: #cause3}

올바르지 않은 배치 이미지 대상 때문일 수 있습니다. 보다 구체적으로, 배치 이미지 대상의 중간 값인 네임스페이스가 올바르지 않을 수 있습니다. 


#### 해결책
{: #resolution3}

배치 이미지 대상의 네임스페이스가 다음을 실행하여 발견한 네임스페이스 중 하나와 일치하는지 확인하십시오.

```
bx cr namespaces
```



## 부록
{: #appendix}

대부분의 사용자를 위해 이 페이지 맨 위의 플랫폼 설치 프로그램을 사용하여 모든 전제조건이 설치딥니다. 컴포넌트를 수동으로 설치해야 하는 경우 다음 지시사항을 따르십시오. 

dev 플러그인을 설치하려면 먼저 [IBM Cloud CLI](../reference/bluemix_cli/get_started.md#getting-started)가 설치되어 있어야 합니다.

dev 플러그인 자체를 사용하려면 `bx plugin install dev -r Bluemix` 명령을 실행하여 설치해야 합니다.

애플리케이션을 로컬로 실행하고 디버깅하려면 [Docker ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.docker.com/get-docker)도 설치해야 합니다.

애플리케이션을 컨테이너로서 배치하려면 Kubernetes, Helm 및 다음 IBM Cloud CLI 플러그인도 설치해야 합니다.

Kubernetes를 설치하려면 다음을 수행하십시오.
* Mac 사용자:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Linux 사용자:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Windows 사용자:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Helm을 설치하려면 다음을 수행하십시오.
* Mac 및 Linux 사용자:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Windows 사용자:
https://github.com/kubernetes/helm/releases/tag/v2.6.0 사이트에서 2진을 다운로드하여 설치하십시오.

container-registry 플러그인을 설치하려면 다음을 수행하십시오.
`bx plugin install container-registry`

container-service 플러그인을 설치하려면 다음을 수행하십시오.
`bx plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## 도움 및 지원 받기
{: #gettinghelp}

{{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} 또는 {{site.data.keyword.dev_cli_notm}}에 대한 문제점이 발생하거나 질문이 있는 경우 정보를 검색하거나 포럼에 질문을 올려서 도움을 받으십시오. 지원 티켓을 열 수도 있습니다.

포럼에 질문을 게시하는 경우 {{site.data.keyword.Bluemix_notm}} 개발 팀에서 알 수 있도록 질문에 태그를 지정할 수 있습니다.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

{{site.data.keyword.dev_console}} 또는 {{site.data.keyword.dev_cli_notm}}으로 앱 개발 또는 배치에 대한 기술적인 질문이 있는 경우:

* [Stack Overflow ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix)에 질문을 게시하고 `bluemix-dev-services` 및 `ibm-bluemix`를 사용하여 질문에 태그를 지정하십시오.
* `bluemix-dev-services` 채널의 [Slack ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](http://ibm-cloud-tech.slack.com/)에 질문을 게시하십시오. 지금 [등록 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](http://ibm.biz/IBMCloudNativeSlack)하십시오.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

포럼 사용에 대한 자세한 정보는 [도움 받기 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](/docs/support/index.html#getting-help)를 참조하십시오. 

{{site.data.keyword.IBM}} 지원 티켓 개설 또는 지원 레벨 및 티켓 심각도에 대한 정보는 [지원 팀에 문의 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](/docs/support/index.html#contacting-support)를 참조하십시오.

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
