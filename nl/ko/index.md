---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} 개요
{: #overview}

{{site.data.keyword.dev_cli_notm}}은 엔드 투 엔드 웹, 모바일 및 마이크로서비스 애플리케이션을 개발하는 데 명령행을 사용하려는 개발자를 위한 애플리케이션 작성, 개발 및 배치용 명령행 방식입니다. 다음 스크립트 중 하나를 실행하여 권장 도구 세트를 빠르게 시작하십시오.
{: shortdesc} 

## {{site.data.keyword.dev_cli_notm}}의 전제조건
{: #prereq}

[{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration)에 등록하십시오.

* Microsoft Windows&trade;를 사용하는 경우 Windows 10 이상을 사용해야 합니다.

* 최소 버전 1.13.1의 안정된 Docker 채널을 사용해야 합니다.

## {{site.data.keyword.dev_cli_notm}} 설치 방법
{: #installation}

도구 세트를 설치하기 위해 관련 명령을 실행하여 설치 프로그램을 시작할 수 있습니다. {{site.data.keyword.Bluemix_notm}} 개발을 위한 다음 권장 도구 `Homebrew`(Mac 전용), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, {{site.data.keyword.Bluemix_notm}} CLI, {{site.data.keyword.dev_cli_notm}} 플러그인, Cloud Functions 플러그인, Container Registry 플러그인, Container Service 플러그인 및 `sdk-gen` 플러그인을 설치합니다(아직 설치되지 않은 경우). 

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


## {{site.data.keyword.dev_cli_notm}}을 자세히 살펴보기 위한 기타 링크

- [세부 설정](/docs/cli/idt/setting_up_idt.html)
- [사용](/docs/cli/idt/index.html)
- [명령](/docs/cli/idt/commands.html)
- [CLI 플러그인](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE 확장](/docs/cli/idt/vscode.html)
- [수동으로 IBM Cloud CLI 설치](/docs/cli/reference/bluemix_cli/get_started.html)
