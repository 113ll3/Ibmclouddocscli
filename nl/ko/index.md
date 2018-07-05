---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} CLI 시작하기
{: #overview}

이 튜토리얼에서 사용자는 {{site.data.keyword.Bluemix}} 개발자 도구를 설치하고, 설치를 확인하며, 환경을 구성합니다. {{site.data.keyword.Bluemix}} 개발자 도구는 엔드 투 엔드 웹, 모바일 및 마이크로서비스 애플리케이션을 작성하고, 개발하고, 배치할 수 있는 명령행 접근 방법을 제공합니다.
{:shortdesc}

이 설치를 통해 {{site.data.keyword.Bluemix_notm}} CLI 및 다음 도구를 얻을 수 있습니다.  

* `Homebrew`(Mac 전용)
* `Git`
* `Docker`
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

[{{site.data.keyword.Bluemix_notm}} 계정](https://console.bluemix.net/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘") 및 다음 시스템 요구사항이 필요합니다.

* Microsoft Windows&trade;를 사용하는 경우 Windows 10 이상을 사용해야 합니다.
* 최소 버전 1.13.1의 안정된 Docker 채널을 사용해야 합니다.

## 1단계: 설치 명령 실행
{: #step1}

* Mac 및 Linux의 경우 다음 명령을 실행하십시오.

  ```
curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br><br>

* Windows 10의 경우 관리자로 다음 명령을 실행하십시오. 

  ```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br><br>
  Windows PowerShell 아이콘을 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 선택하십시오.
  {: tip}

## 2단계: 설치 확인
{: #step2}

CLI 및 개발자 도구가 설치되었는지 확인하려면 `help` 명령을 실행하십시오.

```
ibmcloud dev help
```
{: codeblock}
<br><br>
출력에 사용법 지시사항, 현재 버전 및 지원되는 명령이 나열됩니다. 

## 3단계: 환경 구성
{: #step3}

1. {{site.data.keyword.Bluemix_notm}} 지역의 API 엔드포인트에 연결하십시오. 예를 들어, 다음 명령을 입력하여 {{site.data.keyword.Bluemix_notm}} 미국 남부 지역에 연결하십시오.

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. IBM ID를 사용하여 {{site.data.keyword.Bluemix_notm}}에 로그인하십시오.

	```
	ibmcloud login
	```
	{: codeblock}
<br><br>
	신임 정보가 거부되면 연합 ID를 사용할 수 있습니다. 자세한 사항은 [연합 ID로 로그인](/docs/iam/login_fedid.html#using-an-api-key)을 참조하십시오.
	{: tip}

3. 조직 및 영역을 설정하십시오.

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 다음 단계
{: #next-steps}

이제 첫 번째 앱을 개발하고 배치할 준비가 되었습니다! 자세한 정보는 [스타터 킷을 사용한 기본 웹 앱 작성](/docs/apps/tutorials/tutorial_web.html)을 참조하십시오.
