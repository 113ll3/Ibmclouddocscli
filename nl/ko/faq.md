---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# 자주 묻는 질문(FAQ)
{: #ibm-cli-faq}

## {{site.data.keyword.cloud_notm}} 애플리케이션의 파일 구조는 무엇입니까?
{: #cli-file-structure}

CLI에서 사용으로 설정되거나 작성된 애플리케이션은 `cli-config.yml` 파일에서 캡슐화된 사전 구성 설정과 함께 제공됩니다. `cli-config.yml`은 CLI의 명령에서 사용하는 기본 항목을 포함하며, 이러한 항목은 명령행을 통해 전달되는 값으로 대체될 수 있습니다.

DevOps 도구 체인에 배치된 애플리케이션은 `toolchain.yml` 및 `pipeline.yml`과 같은 파일을 포함할 수도 있습니다. 수동으로 배치되는 애플리케이션은 `manifest.yml` 및 Helm 차트 파일을 포함할 수 있습니다(예를 들어 Cloud Foundry 또는 Kubernetes에 배치를 위해). 

## 로컬 컨테이너는 어떻게 사용됩니까?
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 플러그인은 두 개의 컨테이너를 사용하여 애플리케이션 빌드와 테스트를 용이하게 합니다. 첫 번째는 tools 컨테이너로서 애플리케이션 빌드와 테스트에 필요한 유틸리티를 포함합니다. 이 컨테이너를 위한 `Dockerfile`은 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 매개변수로 정의됩니다. 특정 런타임의 개발에 일반적으로 사용되는 도구를 포함하고 있으므로 개발 컨테이너로 생각할 수 있습니다.

두 번째 컨테이너는 앱이 클라우드에 배치되면 앱의 실제 런타임 환경을 근접하게 모방하는 run 컨테이너입니다. 이 컨테이너는 예를 들어 {{site.data.keyword.cloud_notm}}에서 사용하기 위해 배치하는 데 적합한 양식으로 되어 있습니다. 결과적으로 애플리케이션을 시작하는 시작점이 정의됩니다. {{site.data.keyword.dev_cli_long}} CLI 플러그인 CLI를 통해 애플리케이션을 실행하도록 선택하면 이 컨테이너가 사용됩니다. 이 컨테이너를 위한 `Dockerfile`은 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 매개변수로 정의됩니다.

# 기존 코드를 어떻게 배치합니까?
기존 코드 베이스를 배치하려면 [앱 사용 설정](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)의 단계를 수행하여 앱을 사용하도록 설정하십시오. 

## 블로그, 비디오 및 문서 참조
{: #cli-faq-reference}

### 블로그
{: #cli-blogs}

- [{{site.data.keyword.dev_cli_long}} CLI 플러그인을 사용하여 {{site.data.keyword.cloud_notm}} Private에 배치](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인을 사용하여 {{site.data.keyword.cloud_notm}}의 Kubernetes에 배치](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [{{site.data.keyword.dev_cli_long}}CLI 플러그인을 사용하여 {{site.data.keyword.cloud_notm}}에 대한 기존 프로젝트 사용](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### 동영상
{: #cli-videos}

- [{{site.data.keyword.dev_cli_long}} CLI 플러그인을 사용하여 {{site.data.keyword.cloud_notm}}의 Kubernetes에 배치](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인을 사용하여 기존 프로젝트를 {{site.data.keyword.cloud_notm}}에 배치하는 방법](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인 및 VSCode를 사용하여 Node.js 앱을 작성, 디버그 및 배치](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### 문서 및 튜토리얼
- [Kubernetes에 지속적 배치](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인에 대한 문제점 해결](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인(ibmcloud dev) 명령](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [{{site.data.keyword.dev_cli_long}} CLI 플러그인에 대한 로컬 애플리케이션 디버깅](/docs/cli/idt?topic=cloud-cli-local-debug)

**문제를 보고하거나 피드백을 제공하려는 경우에는 [{{site.data.keyword.cloud_notm}} Tech의 Slack(#developer-tools 채널)을 사용할 수 있습니다](https://ibm-cloud-tech.slack.com). [여기](https://slack-invite-ibm-cloud-tech.mybluemix.net/)서 팀 액세스 권한을 요청하십시오. **
