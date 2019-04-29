---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 플러그인으로 {{site.data.keyword.cloud_notm}} CLI 확장
{: #plug-ins}

{{site.data.keyword.cloud}} CLI는 해당 기능을 확장하도록 플러그인 프레임워크를 지원합니다. 저장소 또는 웹 URL에서 플러그인을 설치하거나 플러그인 2진을 로컬로 설치할 수 있습니다.

[{{site.data.keyword.cloud_notm}} CLI 플러그인 저장소](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)는 플러그인이 호스팅되는 공식 저장소입니다.

더 많은 플러그인 관리용 명령을 보려면 `ibmcloud plugin`을 실행하여 도움말 메시지를 보십시오.
{: tip}

## {{site.data.keyword.cloud_notm}} CLI 저장소에서 플러그인 설치
{: #install-from-repo}

### 1단계: 플러그인 검색
{: #step1-search-plugin}

1. `ibmcloud plugin repo-plugins -r REPO_NAME` 명령을 사용하여 저장소에서 플러그인을 찾으십시오.
2. {{site.data.keyword.cloud_notm}} CLI에는 'IBM Cloud'라는 이름의 공식 저장소가 있으며, 사용자는 다음 예제에 표시된 대로 공식 플러그인을 검색할 수 있습니다.
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                   Versions                       Description   
Update Available   container-service/kubernetes-service   0.2.99, 0.2.95, 0.2.80...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                        1.0.30, 1.0.29, 1.0.28...      IBM Cloud CLI plug-in for IBM Cloud Functions   
...
```
{: screen}

### 2단계: 플러그인 설치
{: step2-install-plugin}

`ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` 명령을 사용하여 플러그인을 설치하십시오. 예를 들어, 공식 IBM 플러그인 저장소 'IBM Cloud'에서 플러그인을 설치하려면 다음 명령을 사용하십시오.

```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
Looking up 'auto-scaling' from repository 'IBM Cloud'...
Plug-in 'auto-scaling 0.2.7' found in repository 'IBM Cloud'
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
```
{: screen}

## 로컬로 플러그인 설치
{: #install-plugin-locally}

`ibmcloud plugin install LOCAL_FILE_NAME` 명령을 사용하여 로컬 머신에 플러그인 2진을 설치하십시오. 예를 들어, 다음과 같습니다.

```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}

## 웹 URL에서 플러그인 설치
{: install-plugin-from-url}

`ibmcloud plugin install URL` 명령을 사용하여 웹 URL에서 직접 플러그인을 설치하십시오. 예를 들어, 다음과 같습니다.
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

출력:
```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}
