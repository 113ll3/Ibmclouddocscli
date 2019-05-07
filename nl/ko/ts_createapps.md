---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-29"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

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
{:troubleshoot: data-hd-content-type='troubleshoot'}

# {{site.data.keyword.cloud_notm}} Developer Tools CLI 플러그인의 문제점 해결
{: #troubleshoot}

{{site.data.keyword.dev_cli_short}} 명령행 인터페이스(CLI)의 일반 문제에 대한 솔루션을 참조하십시오. 대부분 몇 가지 간단한 단계를 수행하여 이러한 문제점에서 복구할 수 있습니다.
{: shortdesc}

## 비모바일 패턴으로 앱을 작성할 때 호스트 이름 오류가 발생하는 이유
{: #ts-cli-hostname-error}
{: troubleshoot}

{{site.data.keyword.dev_cli_short}} CLI를 사용하여 Cloud Foundry에 앱을 배치하는 경우 다음 오류가 표시될 수 있습니다. 고유 호스트 이름을 입력해도 여전히 이 메시지가 표시될 수 있습니다.
```
The hostname <myHostname> is taken.
```
{: screen}
{: tsSymptoms}

이 오류는 로그인 토큰이 만료되어 발생합니다.
{: tsCauses}

다음 명령을 실행하여 다시 로그인하십시오.
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 일반 명령 실패가 발생하는 이유
{: #ts-cli-general-failures}
{: troubleshoot}

`create`, `delete`, `list` 또는 `code` 명령을 사용하는 경우 다음 오류가 표시될 수 있습니다.
```
Failed to <command> app.
```
{: screen}
{: tsSymptoms}

이 오류는 로그인 토큰이 만료되어 발생합니다.
{: tsCauses}

다음 명령을 실행하여 다시 로그인하십시오.
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## 새 앱의 이미지를 인식하지 못하는 이유
{: #ts-cli-nosuchimage}
{: troubleshoot}

앱을 먼저 빌드하지 않고 `ibmcloud dev run`하려고 시도하면 다음 오류가 표시될 수 있습니다.
```
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: screen}
{: tsSymptoms}

앱을 실행하기 전에 먼저 빌드해야 합니다. 현재 앱 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

앱을 시작하려면 현재 앱 디렉토리에서 다음 명령을 실행하십시오.
```
ibmcloud dev run
```
{: tsResolve}

## {{site.data.keyword.objectstorageshort}} 기능을 추가할 때 서비스 브로커 오류가 발생하는 이유
{: #ts-cli-object-storage}
{: troubleshoot}

CLI를 사용하여 {{site.data.keyword.objectstorageshort}} 기능으로 두 개의 앱을 작성하는 경우 다음 오류가 표시될 수 있습니다.

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

이 오류는 무료 {{site.data.keyword.objectstorageshort}} 플랜의 1개 인스턴스만 제공하는 {{site.data.keyword.objectstorageshort}} 서비스로 인해 발생합니다.
{: tsCauses}

다른 플랜을 선택하십시오.
{: tsResolve}

## 앱을 작성할 때 코드가 검색되지 않는 이유
{: #retrieve-code-error}
{: troubleshoot}

CLI를 사용하여 앱을 작성할 때 다음 오류가 표시될 수 있습니다.
```
FAILED                            
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

이 오류는 내부 제한시간 초과로 인한 것입니다.
{: tsCauses}

다음 방법 중 하나를 사용하여 코드를 가져오십시오.

* 다음 명령을 실행하십시오.

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   `<your-app-name>`을 앱 작성 중에 지정한 앱 이름으로 대체하십시오.

* {{site.data.keyword.dev_console}}을 사용하십시오.

	1. {{site.data.keyword.dev_console}}에서 [앱 ](https://cloud.ibm.com/resources){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")을 선택하십시오.

	2. **코드 다운로드**를 클릭하십시오.
{: tsResolve}

## Node.js 앱에 대해 `ibmcloud dev run` 명령을 실행할 수 없는 이유는 무엇입니까?
{: #ts-cli-node}
{: troubleshoot}

Node.js 웹 또는 BFF 앱에 대해 `ibmcloud dev run` 명령을 실행하는 경우 다음 오류가 표시될 수 있습니다.

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
{: screen}
{: tsSymptoms}

이 오류는 `appmetrics` 모듈이 다른 아키텍처에 설치될 때 발생할 수 있습니다. 한 아키텍처에 설치된 기본 npm 모듈은 다른 아키텍처에서 작동하지 않습니다. 포함된 Docker 이미지는 Linux&trade; 커널을 기반으로 합니다.
{: tsCauses}

`node_modules` 폴더를 삭제하고 `ibmcloud dev run` 명령을 다시 실행하십시오.
{: tsResolve}

## {{site.data.keyword.cloud_notm}}에 배치할 수 없는 이유
{: #ts-cli-deploy-issues}
{: troubleshoot}

{{site.data.keyword.cloud_notm}}에 배치하려고 시도하는 경우 실패가 발생하지만 오류는 표시되지 않습니다.
{: tsSymptoms}

사용자의 계정에 로그인하지 못할 수도 있습니다.
{: tsCauses}

로그인하는 다음 명령을 실행하여 다시 시도하십시오.
```
ibmcloud login
```
{: tsResolve}

## {{site.data.keyword.cloud_notm}}의 Kubernetes에 배치할 수 없는 이유
{: #ts-cli-kube-deploy}
{: troubleshoot}

다음 실패는 클러스터 이름을 입력하라는 프롬프트가 표시된 후에 나타날 수 있습니다.
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

이 문제점은 올바르지 않은 클러스터 이름 때문일 가능성이 높습니다. 동일한 명령을 `--trace`와 함께 실행하여 원인을 확인할 수 있으며 다음 세부사항이 오류 출력에 포함될 수 있습니다.
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

다음을 실행하여 올바른 클러스터를 사용 중이며 배치에 대해 구성되어 있는지 확인하십시오.
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## 이미지 대상을 배치할 수 없는 이유
{: #ts-deploy-image-target}
{: troubleshoot}

다음 실패는 배치 이미지 대상을 입력하라는 프롬프트가 표시된 후에 발생할 수 있습니다.
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

이 문제점은 올바르지 않은 배치 이미지 대상 때문일 가능성이 높습니다. 보다 구체적으로는 배치 이미지 대상의 중간 값인 네임스페이스가 올바르지 않을 수 있습니다.
{: tsCauses}

배치 이미지 대상의 네임스페이스가 다음 명령을 실행할 때 표시되는 네임스페이스 중 하나와 일치하는지 확인하십시오.
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## 내 앱의 언어를 판별할 수 없는 이유
{: #ts-cli-determine-language}
{: troubleshoot}

앱을 시작할 때 다음 실패 메시지가 표시될 수 있습니다.
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

이 오류의 원인은 다음 중 하나일 수 있습니다.
- 애플리케이션의 소스 디렉토리가 아닌 디렉토리에서 [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 명령 실행.
- 인식되지 않는 언어로 된 앱에 대해 [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) 명령 실행.
{: tsCauses}

앱의 소스 코드를 포함하는 앱 디렉토리에서 명령을 실행하는지 확인하십시오. 문제가 해결되지 않고 언어가 [지원되는 언어](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options) 중 하나이면 `--language` 매개변수를 사용하여 언어를 지정하십시오.
{: tsResolve}

## 클라우드 배치에 사용된 앱을 빌드하거나 실행할 수 없는 이유
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

클라우드 배치에 사용으로 설정된 앱을 [빌드](/docs/cli/idt?topic=cloud-cli-idt-cli#build)하거나 [실행](/docs/cli/idt?topic=cloud-cli-idt-cli#run)하는 데 다양한 실패가 발생할 수 있습니다.
{: tsSymptoms}

다음과 같은 각 링크에서 여러 다른 가능한 원인을 찾을 수 있습니다.
{: tsCauses}

- Spring 앱에서 해당 문제점을 해결하는 데 관한 자세한 정보는 [클라우드 배치를 위해 기존 Spring 부트 애플리케이션 사용](/docs/java-spring?topic=java-spring-enable_existing#enable_existing)을 참조하십시오.
- `Node.js` 앱에서 해당 문제점을 해결하는 데 관한 자세한 정보는 [클라우드 배치를 위해 기존 Node.js 애플리케이션 사용](/docs/node?topic=nodejs-enable_existing#enable_existing)을 참조하십시오.
{: tsResolve}

## {{site.data.keyword.dev_cli_notm}} CLI 컴포넌트를 개별적으로 수동으로 설치하는 방법
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

{{site.data.keyword.dev_cli_notm}} CLI 컴포넌트를 개별적으로 수동으로 설치하려면 다음 [단계](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually)를 따르십시오.

## 왜 Docker 이미지를 빌드할 수 없습니까?
{: $ts-cli-docker}
{: troubleshoot}

다음과 같은 오류가 표시되는 경우: 
```
FAILED
An error exit status 1 was encountered while building the Docker 
image.
```
{: screen}

이 오류의 원인은 다음 중 하나일 수 있습니다.
- Docker가 설치되어 있지 않습니다.
- Docker 디먼이 실행 중이 아닙니다.
{: tsCauses}

Docker가 설치되어 실행 중인지 확인하십시오.
- [Mac용 Docker](https://docs.docker.com/docker-for-mac/install/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")를 설치하거나 시작하기
- [Windows용 Docker&trade;](https://docs.docker.com/docker-for-windows/install/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")를 설치하거나 시작하기
- [Linux용 Docker&trade;](https://docs.docker.com/v17.12/install/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")를 설치하거나 시작하기
{: tsResolve}

## 호환되지 않는 helm 버전을 해결하는 방법
{: ts-cli-helm}
{: troubleshoot}

클라이언트 및 서버 helm 버전이 동기화되지 않은 경우 다음 오류가 표시될 수 있습니다.
```
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED: 
configmaps is forbidden: User "system:serviceaccount:kube-system:default" 
cannot list resource "configmaps" in API group "" in the namespace 
"kube-system"
```
{: screen}

```
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

이 문제를 해결하려면 클라이언트의 버전을 클러스터의 버전과 동일하게 설정하십시오. 예를 들어, 2.8.1 helm 버전을 설치하려면 다음 명령을 실행하십시오.
{: tsResolve}

* Mac 및 Linux&trade;의 경우 다음 명령을 실행하십시오.
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* Windows&trade;의 경우: 관리자로 다음을 수행하십시오. `helm` 바이너리를 [https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에서 다운로드하여 설치하십시오.
  
  PowerShell 터미널에서 다음 명령을 실행하십시오.
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```
  {: codeblock}

## ibmcloud dev 빌드가 "@"를 포함하는 사용자 이름 때문에 실패하는 이유
{: ts-cli-username}
{: troubleshoot}
이미지 빌드 프로세스 중에 사용자 이름이 Docker 도구 이미지의 사용자에 대해 사용됩니다. 사용자 이름에 '@' 또는 '-'와 같은 특수 문자가 포함되어 있는 경우, Docker 이미지 빌드 프로세스가 실패하고 다음 오류가 발생합니다.
```
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Dumping output from the command:
```
{: screen}

이 문제를 해결하려면 특수 문자를 포함하지 않도록 사용자 이름을 변경하거나 다음 플래그를 지정하여 루트 사용자를 대신 사용하십시오.
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
