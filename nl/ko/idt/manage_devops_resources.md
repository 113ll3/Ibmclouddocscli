---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# CLI를 사용한 DevOps 리소스 관리
{: #managing-devops-resources-cli}

[{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started)를 사용하여 명령행에서 직접 DevOps 리소스를 관리할 수 있습니다. CLI를 사용하여 DevOps 도구 체인, 파이프라인 및 파이프라인 로그를 볼 수 있습니다.
{: shortdesc}

## 시작하기 전에
{: #set-toolchain-view}

도구 체인 보기는 현재 대상으로 지정된 리소스 그룹에 따라 다릅니다. 다음 명령을 사용하여 현재 대상으로 지정된 리소스 그룹을 식별하고 원하는 경우 변경하십시오.

* 현재 대상으로 지정된 리소스 그룹을 보려면 다음을 실행하십시오.
  ```
ibmcloud target
  ``` 
  {: codeblock}

* 설정된 리소스 그룹이 없거나 리소스 그룹을 변경하려면 다음을 실행하십시오. 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## 도구 체인 보기
{: #viewing-toolchains}

명령행에서 도구 체인 정보를 보거나 브라우저에서 볼 수 있습니다.

* 대상으로 지정된 리소스 그룹에서 도구 체인을 보려면 다음을 실행하십시오.
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* 해당 도구 체인에 대한 세부사항을 보려면 다음을 실행하십시오.
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* 브라우저에서 도구 체인 세부사항을 보려면 다음을 실행하십시오.
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## 파이프라인 보기
{: #viewing-pipeline}

파이프라인을 호출하는 데 필요한 세부사항을 가져오려면 `ibmcloud dev toolchains`를 실행하여 도구 체인의 이름을 가져오십시오. 이름이 이미 알려져 있는 경우, `ibmcloud dev toolchain-get [toolchain-name]`을 실행하여 도구 체인의 세부사항을 가져오십시오. 

* 파이프라인 및 해당 단계의 세부사항을 가져오려면 파이프라인과 해당 ID를 식별하여 다음 명령을 실행하십시오.
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* 이전 명령에서 파이프라인 ID를 사용하여 파이프라인을 실행할 수 있습니다.
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  이 명령은 단계 및 해당 작업의 실행을 호출합니다. 실행에 성공하면 선택한 단계의 각 작업에 대해 작업 실행이 수행됩니다.

## 파이프라인 로그 보기
{: #viewing-pipeline-logs}

* 파이프라인의 실행 로그를 보려면 다음을 실행하십시오.
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* 단계별로 로그를 필터링하려면 이전 명령을 적용하고 단계 ID를 추가하십시오.
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## 유용한 DevOps 명령
{: #helpful-devops-commands}

다음 `ibmcloud dev` 명령을 사용하여 DevOps 리소스를 관리하십시오.

### 도구 체인 명령
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) 대상으로 지정된 리소스 그룹의 도구 체인 목록을 봅니다.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) 대상으로 지정된 리소스 그룹 내의 선택된 도구 체인에 대한 세부사항을 봅니다.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) 브라우저에서 선택된 도구 체인을 엽니다.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) 도구 체인을 삭제합니다.

### 파이프라인 명령
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) 파이프라인의 세부사항을 봅니다.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) 파이프라인을 실행합니다.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) 브라우저에서 파이프라인을 엽니다.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) 파이프라인의 실행 로그를 봅니다.

자세한 정보는 전체 `ibmcloud dev` [명령 참조](/docs/cli/idt?topic=idt-cli)에서 볼 수 있습니다.
