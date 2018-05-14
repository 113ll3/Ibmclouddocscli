---
copyright:

  years: 2018

lastupdated: "2018-04-17"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}} CLI 설정
{: #add-cli}

{{site.data.keyword.dev_cli_short}} CLI는 엔드 투 엔드 웹, 모바일 및 마이크로서비스 애플리케이션을 개발할 때 명령행을 사용하려는 개발자를 위한 것으로, 애플리케이션 작성, 개발 및 배치에 대한 명령행 방식입니다.
{: shortdesc}

## 전제조건
{: #prereq}

[{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net)에 등록하십시오.

*  Microsoft Windows&trade;를 사용하는 경우 Windows 10 이상을 사용해야 합니다.

* 최소 버전 1.13.1의 안정된 Docker 채널을 사용해야 합니다.

## 설치
{: #installation}

도구를 설치하기 위해 관련 명령을 실행하여 설치 프로그램을 시작할 수 있습니다. 이는 IBM Cloud CLI, Kubernetes, Helm 및 Docker 등의 종속 항목도 설치합니다. 설치하려면 다음 설치 단계를 사용하십시오.

**Mac 및 Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* 참고: 마우스 오른쪽 단추를 클릭하여 Windows PowerShell을 열고 "관리자로서 실행"을 선택하십시오.

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

다음 명령을 실행하여 플러그인이 제대로 설치되었는지 검증하십시오.  

```
bx dev
```
{: codeblock}

## 환경 구성
{: #configure-environment}

1. [{{site.data.keyword.Bluemix_notm}} 지역](/docs/overview/cf.html#ov_intro_reg)에서 API 엔드포인트에 연결하십시오. 예를 들어, 다음 명령을 입력하여 {{site.data.keyword.Bluemix_notm}} 미국 남부 지역에 연결하십시오.

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. IBM ID를 사용하여 {{site.data.keyword.Bluemix_notm}}에 로그인하십시오.

	```
	bx login
	```
	{: codeblock}

	**참고:** 신임 정보가 거부되면 연합 ID를 사용할 수 있습니다. 연합 ID를 사용하여 인증하려면 다음 단계를 따르십시오.

	1. [{{site.data.keyword.iamshort}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.bluemix.net/iam/#/apikeys){: new_window}에 로그인하십시오.
	2. **API 키 작성**을 선택하십시오.
		* apiKey 이름 및 설명을 입력하십시오.
	3. apiKey를 다운로드하십시오.
	4. 파일을 열고 `apiKey` 필드에서 값을 복사하십시오.
	5. 다음 명령을 사용하여 로그인하십시오.

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. 다음을 사용하여 사용자의 조직 및 영역을 설정하십시오.

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## 자세히 보기
{: #learn}

{{site.data.keyword.dev_cli_short}}가 설치되었으므로 이 강력한 도구로 효율성을 높일 수 있는 방법을 배울 수 있습니다.
- [IDT CLI로 시작하기](index.html)
- [IDT (bx dev) 명령](commands.html)
- [VS 코드를 위한 개발자 도구](vscode.html)
- [Jetbrains IDE를 위한 개발자 도구](jetbrains.html)

{{site.data.keyword.dev_cli_short}} CLI를 사용하여 클라우드 네이티브 앱을 작성하는 방법을 보여주는 [튜토리얼](/docs/apps/tutorials/tutorial_bff.html)을 확인하십시오.

## 추가 읽기
{: #learn-more}

다음 리소스는 클라우드 네이티브 앱을 IBM Developer Tools CLI로 개발할 때 유용할 수 있습니다.

- [IBM Cloud Developer Tools 기본 시작 페이지](https://www.ibm.com/cloud/cli) - IDT CLI에 대한 기본 제품 페이지
- [IBM Developer Tools 설치 프로그램](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - 자세한 설치 지시사항이 있는 공용 GitHub 저장소
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - 클라우드 네이티브 앱을 작성하고 관리하기 위한 IDT 도구의 컴패니온인 IBM Cloud 콘솔 페이지
- [IBM Cloud TechTech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - IDT 도구 논의, 답변 얻기, 아이디어 제시 등
	- [팀 액세스 요청](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**언어에 초점**

- [IBM Cloud의 Node,js](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**블로그 및 튜토리얼**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
