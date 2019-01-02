---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-30"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# {{site.data.keyword.Bluemix_notm}} Developer Tools CLI 플러그인의 문제점 해결
{: #troubleshoot}

{{site.data.keyword.dev_cli_short}} 명령행 인터페이스(CLI)를 사용하여 앱을 작성하는 데 관련된 일반적인 문제점에는 배치 실패 또는 검색할 수 없는 코드가 포함될 수 있습니다. 대부분 몇 가지 간단한 단계를 수행하여 이러한 문제점에서 복구할 수 있습니다.
{:shortdesc}

## 비모바일 패턴으로 앱을 작성할 때 호스트 이름 오류가 발생하는 이유
{: #hostname-error}
{: troubleshoot}

{{site.data.keyword.dev_cli_short}} CLI를 사용하여 Cloud Foundry에 앱을 배치하는 경우 다음 오류가 표시될 수 있습니다. 고유 호스트 이름을 입력해도 여전히 이 메시지가 표시될 수 있습니다.

```
The hostname <myHostname> is taken.
```
{: codeblock}
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
{: #general}
{: troubleshoot}

`create`, `delete`, `list` 또는 `code` 명령을 사용하는 경우 다음 오류가 표시될 수 있습니다.

```
Failed to <command> application.
```
{: codeblock}
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
{: #nosuchimage}
{: troubleshoot}

앱을 먼저 빌드하지 않고 실행하려고 하면 다음 오류가 표시될 수 있습니다.

```
$ ibmcloud dev run
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
{: #os}
{: troubleshoot}

CLI를 사용하여 {{site.data.keyword.objectstorageshort}} 기능으로 두 개의 앱을 작성하는 경우 다음 오류가 표시될 수 있습니다.

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

이 오류는 무료 {{site.data.keyword.objectstorageshort}} 플랜의 1개 인스턴스만 제공하는 {{site.data.keyword.objectstorageshort}} 서비스로 인해 발생합니다.
{: tsCauses}

다른 플랜을 선택하십시오.
{: tsResolve}

## 앱을 작성할 때 코드가 검색되지 않는 이유
{: #code}
{: troubleshoot}

CLI를 사용하여 앱을 작성할 때 다음 오류가 표시될 수 있습니다.

```
FAILED                            
Application created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
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

	1. {{site.data.keyword.dev_console}}에서 [앱 ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.bluemix.net/developer/appservice/apps)을 선택하십시오.

	2. **코드 다운로드**를 클릭하십시오.
{: tsResolve}

## Node.js 앱에 대해 `ibmcloud dev run` 명령을 실행할 수 없는 이유
{: #node}
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
{: codeblock}
{: tsSymptoms}

이 오류는 `appmetrics` 모듈이 다른 아키텍처에 설치될 때 발생할 수 있습니다. 한 아키텍처에 설치된 기본 npm 모듈은 다른 아키텍처에서 작동하지 않습니다. 포함된 Docker 이미지는 Linux 커널을 기반으로 합니다.
{: tsCauses}

`node_modules` 폴더를 삭제하고 `ibmcloud dev run` 명령을 다시 실행하십시오.
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}}에 배치할 수 없는 이유
{: troubleshoot}

{{site.data.keyword.Bluemix_notm}}에 배치하려고 할 때 실패가 발생하지만 오류가 표시되지 않습니다.
{: tsSymptoms}

사용자의 계정에 로그인하지 못할 수도 있습니다.
{: tsCauses}

로그인하는 다음 명령을 실행하여 다시 시도하십시오.
```
ibmcloud login
```
{: tsResolve}

## {{site.data.keyword.Bluemix_notm}}의 Kubernetes에 배치할 수 없는 이유
{: troubleshoot}

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

## 이미지 대상을 배치할 수 없는 이유
{: troubleshoot}

다음 장애는 배치 이미지 대상을 입력하라는 프롬프트가 표시된 후에 나타날 수 있습니다.
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

이는 올바르지 않은 배치 이미지 대상 때문일 가능성이 높습니다. 보다 구체적으로 배치 이미지 대상의 중간 값인 네임스페이스가 올바르지 않을 수 있습니다.
{: tsCauses}

배치 이미지 대상의 네임스페이스가 다음 명령을 실행할 때 표시되는 네임스페이스 중 하나와 일치하는지 확인하십시오.
```
ibmcloud cr namespaces
```
{: tsResolve}

## 내 앱의 언어를 판별할 수 없는 이유
{: troubleshoot}

앱을 시작하려고 하면 다음 실패가 표시될 수 있습니다.
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: tsSymptoms}

이 오류의 원인은 다음 중 하나일 수 있습니다.
- 애플리케이션의 소스 디렉토리가 아닌 디렉토리에서 [enable](/docs/cli/idt/commands.html#enable) 명령 실행.
- 현재 인식되지 않는 언어로 된 앱에 대해 [enable](/docs/cli/idt/commands.html#enable) 명령 실행.
{: tsCauses}

앱의 소스 코드를 포함하는 앱 디렉토리에서 명령을 실행하십시오. 그래도 문제점이 해결되지 않고 언어가 [지원되는 언어](/docs/cli/idt/commands.html#enable-language-options) 중 하나이면 `--language` 매개변수를 사용하여 언어를 지정하십시오.
{: tsResolve}

## 클라우드 배치에 사용된 앱을 빌드하거나 실행할 수 없는 이유
{: troubleshoot}

사용된 앱을 [빌드](/docs/cli/idt/commands.html#build)하거나 [실행](/docs/cli/idt/commands.html#run)하려는 중에 다양한 실패가 발생할 수 있습니다.
{: tsSymptoms}


다음과 같은 각 링크에서 여러 다른 가능한 원인을 찾을 수 있습니다.
{: tsCauses}

- Spring 앱에서 해당 문제점을 해결하는 데 관한 자세한 정보는 [클라우드 배치를 위해 기존 Spring 부트 애플리케이션 사용](/docs/java-spring/enable_existing.html#enable_existing)을 참조하십시오.
- `Node.js` 앱에서 해당 문제점을 해결하는 데 관한 자세한 정보는 [클라우드 배치를 위해 기존 Node.js 애플리케이션 사용](/docs/node/enable_existing.html#enable_existing)을 참조하십시오.
{: tsResolve}

## 수동으로 {{site.data.keyword.Bluemix_notm}} 개발자 도구를 설치하는 방법
{: #appendix}
대부분의 사용자를 위해 플랫폼 설치 프로그램을 사용하여 모든 필수 소프트웨어가 설치됩니다. 컴포넌트를 수동으로 설치해야 하는 경우 각각에 대해 다음 지시사항을 따르십시오. dev 플러그인을 설치하려면 먼저 [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use)를 설치해야 합니다. dev 플러그인 자체를 사용하려면 다음 명령을 실행하여 설치해야 합니다. 
```
ibmcloud plugin install dev
```
{: codeblock}
 
앱을 로컬로 실행하고 디버깅하려면 [Docker](https://www.docker.com/get-docker)도 설치해야 합니다.
 
앱을 컨테이너로 배치하려면 Kubernetes, Helm 및 다음 IBM Cloud CLI 플러그인도 설치해야 합니다.
 
### Kubernetes를 설치하려면 다음을 수행하십시오.
Mac 사용자:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Linux 사용자:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Windows 사용자:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### Helm을 설치하려면 다음을 수행하십시오.
Mac 및 Linux 사용자:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Windows 사용자:
[2진](https://github.com/kubernetes/helm/releases/tag/v2.7.2)을 다운로드하여 설치하십시오.

### container-registry 플러그인을 설치하려면 다음을 수행하십시오.
```
ibmcloud plugin install container-registry
```
{: codeblock}

### container-service 플러그인을 설치하려면 다음을 수행하십시오.
```
ibmcloud plugin install container-service
```
{: codeblock}
