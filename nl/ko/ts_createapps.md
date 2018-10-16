---

copyright:
  years: 2015, 2018
lastupdated: "2018-10-04"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# {{site.data.keyword.Bluemix_notm}} Developer Tools CLI 플러그인의 문제점 해결
{: #troubleshoot}

앱을 작성하기 위해 {{site.data.keyword.dev_cli_short}}을 사용할 때 발생하는 일반 문제점에는 앱 작성 시 검색할 수 없는 코드 또는 배치 실패가 포함될 수 있습니다. 대부분 몇 가지 간단한 단계를 수행하여 이러한 문제점에서 복구할 수 있습니다.
{:shortdesc}

## 비모바일 패턴이 있는 앱을 작성할 때 호스트 이름 오류
{: #hostname-error}

앱을 Cloud Foundry에 배치하기 위해 {{site.data.keyword.dev_cli_short}} CLI를 사용하는 경우 다음 오류가 발생할 수 있습니다. 고유하다고 생각하는 호스트 이름을 입력하는 경우에도 이 메시지가 계속 표시될 수 있습니다.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

이 오류는 로그인 토큰이 만료되어 발생합니다.
{: tsCauses}

다시 로그인하십시오.

```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## {{site.data.keyword.dev_cli_short}} CLI의 일반 장애
{: #general}

{{site.data.keyword.dev_cli_short}} CLI의 `create`, `delete`, `list` 또는 `code` 명령을 사용하는 경우 다음 오류가 표시될 수 있습니다.

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

이 오류는 로그인 토큰이 만료되어 발생합니다.
{: tsCauses}

다시 로그인하십시오.

```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 오류: 새 앱을 실행할 때 해당 이미지가 없음
{: #nosuchimage}

먼저 앱을 빌드하지 않고 실행하면 다음 오류가 표시될 수 있습니다.

```
$ ibmcloud dev run
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
{: tsSymptoms}

앱을 실행하기 전에 먼저 빌드해야 합니다.
{: tsCauses}

앱을 빌드하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.

```
ibmcloud dev build
```
{: codeblock}

앱을 시작하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.

```
ibmcloud dev run
```
{: tsResolve}

## {{site.data.keyword.objectstorageshort}} 기능을 추가할 때 서비스 브로커 오류
{: #os}

{{site.data.keyword.objectstorageshort}} 기능으로 두 개 앱을 작성하기 위해 {{site.data.keyword.dev_cli_short}} CLI를 사용하는 경우 다음 오류가 발생할 수 있습니다.

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

이 오류는 무료 {{site.data.keyword.objectstorageshort}} 플랜의 1개 인스턴스만 제공하는 {{site.data.keyword.objectstorageshort}} 서비스로 인해 발생합니다.
{: tsCauses}

이 오류를 피하기 위해 다른 플랜을 선택하라는 프롬프트가 표시됩니다.
{: tsResolve}

## 앱 작성 시 코드 가져오기 실패
{: #code}

앱을 작성하기 위해 {{site.data.keyword.dev_cli_short}} CLI를 사용하는 경우 다음 오류가 표시될 수 있습니다.

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

이 오류는 내부 제한시간 초과로 인한 것입니다.
{: tsCauses}

다음 방법 중 하나로 코드를 가져올 수 있습니다.

* CLI를 사용하여 다음 명령을 실행하십시오.

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   `<your-app-name>`을 앱 작성 중에 지정한 앱 이름으로 대체하십시오.

* {{site.data.keyword.dev_console}}을 사용하십시오.

	1. {{site.data.keyword.dev_console}}에서 [앱 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.bluemix.net/developer/appservice/apps)을 선택하십시오.

	2. **코드 다운로드**를 클릭하십시오.

{: tsResolve}

## Node.js 앱에 대해 `ibmcloud dev run` 실행 중 오류
{: #node}

Node.js 웹 또는 BFF 앱에 대해 {{site.data.keyword.dev_cli_short}} CLI로 `ibmcloud dev run`을 실행하는 동안 다음 오류가 표시될 수 있습니다.

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/ibmcloud-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/ibmcloud-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}
{: tsSymptoms}

이 오류는 `appmetrics` 모듈이 다른 아키텍처에 설치될 때 발생할 수 있습니다. 한 아키텍처에 설치된 기본 npm 모듈은 다른 아키텍처에서 작동하지 않습니다. 포함된 Docker 이미지는 Linux 커널을 기반으로 합니다.
{: tsCauses}

`node_modules` 폴더를 삭제하고 `ibmcloud dev run` 명령을 다시 실행하십시오.
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}}에 배치 실패

{{site.data.keyword.dev_cli_short}} CLI로 {{site.data.keyword.Bluemix_notm}}에 배치를 시도할 때 장애가 발생했지만 오류가 표시되지 않습니다.
{: tsSymptoms}

사용자의 계정에 로그인하지 못할 수도 있습니다.
{: tsCauses}

로그인하고 다시 시도하십시오.

```
ibmcloud login
```
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}}에서 Kubernetes에 배치 실패

다음 장애는 클러스터 이름을 입력하라는 프롬프트가 표시된 후에 나타날 수 있습니다.

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

이는 올바르지 않은 클러스터 이름 때문일 가능성이 높습니다. 동일한 명령을 `--trace`와 함께 실행하여 원인을 확인할 수 있으며 다음 세부사항이 오류 출력에 포함될 수 있습니다.

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

올바른 클러스터를 사용 중인지 확인하고 다음을 실행하여 배치에 대해 클러스터를 구성했는지 확인하십시오.

```
ibmcloud cs cluster-config <cluster-name>
```
{: tsResolve}

## 이미지 대상을 배치하는 데 실패

다음 장애는 배치 이미지 대상을 입력하라는 프롬프트가 표시된 후에 나타날 수 있습니다.

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

이는 올바르지 않은 배치 이미지 대상 때문일 가능성이 높습니다. 보다 구체적으로 배치 이미지 대상의 중간 값인 네임스페이스가 올바르지 않을 수 있습니다.

배치 이미지 대상의 네임스페이스가 다음을 실행하여 발견한 네임스페이스 중 하나와 일치하는지 확인하십시오.

```
ibmcloud cr namespaces
```
{: tsResolve}

## 재설치 도구
{: #appendix}

대부분의 사용자를 위해 플랫폼 설치 프로그램을 사용하여 모든 필수 소프트웨어가 설치됩니다. 컴포넌트를 수동으로 설치해야 하는 경우 다음 지시사항을 따르십시오.

dev 플러그인을 설치하려면 먼저 [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use)를 설치해야 합니다.

dev 플러그인 자체를 사용하려면 `ibmcloud plugin install dev -r IBM Cloud` 명령을 실행하여 설치해야 합니다.

앱을 로컬로 실행하고 디버깅하려면 [Docker](https://www.docker.com/get-docker)도 설치해야 합니다.

앱을 컨테이너로서 배치하려면 Kubernetes, Helm 및 다음 IBM Cloud CLI 플러그인도 설치해야 합니다.

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
`ibmcloud plugin install container-registry`

container-service 플러그인을 설치하려면 다음을 수행하십시오.
`ibmcloud plugin install container-service`
