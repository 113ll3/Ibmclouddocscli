---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# FAQ
{: #ibm-cli-faq}

## 최신 버전의 {{site.data.keyword.cloud_notm}} CLI를 사용해야 합니까?
{: #cli-latest-version}

예, 최신 버전을 사용해야 합니다. 다음 명령을 실행하여 사용 중인 버전을 확인할 수 있습니다.

```
ibmcloud -v
```
{: codeblock}

## CLI 업데이트 방법
{: #cli-update-version}

다음 명령을 실행하여 최신 버전의 CLI로 업데이트하십시오.

```
ibmcloud update
```
{: codeblock}

## 새 CLI 릴리스에 대한 알림을 받을 수 있는 방법은 무엇입니까?
{: #cli-get-notified}

예, 사용할 수 있는 CLI의 새 릴리스에 대한 최신 정보를 받을 수 있습니다. [{{site.data.keyword.cloud_notm}} CLI 릴리스 저장소](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")를 구독하십시오.

## {{site.data.keyword.cloud_notm}} 애플리케이션의 파일 구조는 무엇입니까?
{: #cli-file-structure}

CLI에서 사용으로 설정되거나 작성된 애플리케이션은 `cli-config.yml` 파일에서 캡슐화된 사전 구성 설정과 함께 제공됩니다. `cli-config.yml`은 CLI의 명령에서 사용하는 기본 항목을 포함하며, 이러한 항목은 명령행을 통해 전달되는 값으로 대체될 수 있습니다.

DevOps 도구 체인에 배치된 앱은 `toolchain.yml` 및 `pipeline.yml`과 같은 파일을 포함할 수도 있습니다. 수동으로 배치되는 앱은 `manifest.yml` 및 Helm 차트 파일을 포함할 수 있습니다(예를 들어 Cloud Foundry 또는 Kubernetes에 배치를 위해).

## 로컬 컨테이너는 어떻게 사용됩니까?
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 플러그인은 두 개의 컨테이너를 사용하여 앱 빌드와 테스트를 용이하게 합니다. 첫 번째는 tools 컨테이너로서 앱 빌드와 테스트에 필요한 유틸리티를 포함합니다. 이 컨테이너를 위한 `Dockerfile`은 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 매개변수로 정의됩니다. 특정 런타임의 개발에 일반적으로 사용되는 도구를 포함하고 있으므로 개발 컨테이너로 생각할 수 있습니다.

두 번째 컨테이너는 앱이 클라우드에 배치되면 앱의 실제 런타임 환경을 근접하게 모방하는 run 컨테이너입니다. 이 컨테이너는 예를 들어 {{site.data.keyword.cloud_notm}}에서 사용하기 위해 배치하는 데 적합한 양식으로 되어 있습니다. 결과적으로 앱을 시작하는 시작점이 정의됩니다. {{site.data.keyword.dev_cli_long}} CLI 플러그인 CLI를 통해 앱을 실행하도록 선택하면 이 컨테이너가 사용됩니다. 이 컨테이너를 위한 `Dockerfile`은 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 매개변수로 정의됩니다.

## 기존 코드를 배치하는 방법은 무엇입니까?

기존 코드 베이스를 배치하려면 [배치 및 클라우드 인에이블먼트 자산 생성](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)을 참조하십시오.

