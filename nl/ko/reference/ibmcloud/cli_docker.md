---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Docker 컨테이너에서 {{site.data.keyword.dev_cli_notm}} 사용

{{site.data.keyword.dev_cli_notm}} Docker 컨테이너를 사용하여 {{site.data.keyword.Bluemix}} CLI 및 다음 도구를 사용할 수 있습니다.

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 플러그인
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 플러그인
* {{site.data.keyword.registrylong_notm}} 플러그인
* {{site.data.keyword.containerlong_notm}} 플러그인
* `sdk-gen` 플러그인

## 시작하기 전에
{: #prereq}

[{{site.data.keyword.Bluemix_notm}} 계정](https://console.bluemix.net/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")이 필요하며 다음 단계를 수행하기 전에 안정된 최신 Docker 버전을 설치해야 합니다. 

## 1단계. Docker 허브에서 Docker 이미지를 가져오십시오.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 2단계. Docker 컨테이너를 시작하십시오.
{: #step2}

다음 명령을 사용하여 {{site.data.keyword.dev_cli_notm}} Docker 컨테이너를 시작하십시오.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## 3단계. IBM ID를 사용하여 {{site.data.keyword.Bluemix_notm}}에 로그인하십시오.
{: #step3}

```
ibmcloud login
```
{: codeblock}


인증 정보가 거부되면 연합 ID를 사용할 수 있습니다. 자세한 사항은 [연합 ID로 로그인](/docs/iam/login_fedid.html#federated_id)을 참조하십시오.
{: tip}

이제 {{site.data.keyword.Bluemix_notm}} 리소스를 관리하고 애플리케이션을 개발 및 배치하기 위해 {{site.data.keyword.dev_cli_notm}}을 사용할 준비가 되었습니다.
