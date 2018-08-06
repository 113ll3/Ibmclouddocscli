---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-23"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 독립형 {{site.data.keyword.Bluemix_notm}} CLI 설치
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI는 {{site.data.keyword.Bluemix_notm}}에서 애플리케이션, 컨테이너, 인프라, 서비스 및 기타 리소스를 관리하기 위한 명령행 인터페이스를 제공합니다.

{{site.data.keyword.Bluemix}} CLI와 {{site.data.keyword.Bluemix_notm}}용 애플리케이션을 개발하기 위해 권장되는 플러그인 및 도구를 모두 설치하려면 [여기](/docs/cli/index.html)에 설명된 방법을 따르십시오.
{: tip}

독립형 {{site.data.keyword.Bluemix_notm}} CLI를 설치하려면 다음 단계를 사용하십시오.

1. 다운로드할 OS의 설치 프로그램 선택

   Mac OS X 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64비트: [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64비트(ppc64le): [설치 프로그램](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

1. 설치 프로그램 실행
   * macOS 및 Windows의 경우 설치 프로그램을 실행하십시오.
   * Linux의 경우 패키지의 압축을 풀고 `install_bluemix_cli` 스크립트를 실행하십시오.

1. API 엔드포인트를 대상으로 지정 및 {{site.data.keyword.Bluemix_notm}}에 로그인

   ```
ibmcloud login
   ```
   {: codeblock}
   
이제 {{site.data.keyword.Bluemix_notm}} 리소스를 관리할 준비가 되었습니다. 명령 설명을 보려면 `ibmcloud help`를 입력하십시오.

연합 ID를 사용하는 경우 [여기](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)의 지시사항을 따라 일회성 패스코드 또는 API 키로 로그인하십시오.  
{: tip}

## {{site.data.keyword.Bluemix_notm}} CLI 설치 프로그램의 모든 버전

항상 {{site.data.keyword.Bluemix_notm}} CLI의 최신 버전을 사용하되, 32비트 버전이나 최신 버전 외의 이전 버전을 사용해야 하는 경우에는 다음 표를 참조하십시오. 

|버전 |업데이트  | 설치 프로그램 다운로드 | 2진 아카이브 |
|---------|-----------|-----------|----------|
| [0.8.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.8.0) | 2018-07-13 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/checksum) |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/archive/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/archive) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/archive/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/archive/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/archive/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/archive/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/archive/checksum) |
| [0.7.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.1) | 2018-06-07 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le/checksum) | |
| [0.7.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.0) | 2018-05-31 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le/checksum) | |
|[0.6.7](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.7) |2018-05-15 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le/checksum) | |
|[0.6.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.6) |2018-03-19 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32/checksum) | |
|[0.6.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.5) |2018-02-05 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32/checksum) | |
|[0.6.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.4) |2017-12-19 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32/checksum) | |
|[0.6.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.3) |2017-12-12 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32/checksum) | |
|[0.6.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.2) |2017-11-16 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32/checksum) | |
|[0.6.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.1) |2017-10-05 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32/checksum) | |
|[0.6.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.0) |2017-09-30 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32/checksum) | |
|[0.5.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.6) |2017-08-17 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32/checksum) | |
|[0.5.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.5) |2017-07-03 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32/checksum) | |
|[0.5.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.4) |2017-05-18 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32/checksum) | |
|[0.5.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.3) |2017-05-16 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32/checksum) | |
|[0.5.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.2) |2017-04-10 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32/checksum) | |
|[0.5.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.1) |2017-03-18 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64/checksum) [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32/checksum) | |


설치 프로그램 외에, 다른 방법으로 {{site.data.keyword.Bluemix_notm}} CLI를 설치할 수도 있습니다. 

* 쉘에서 설치
* 2진 패키지를 다운로드하여 사용자 정의 디렉토리에 설치

## 쉘에서 설치
{: #shell_install}

### MacOS

다음 명령을 복사하여 Mac OS의 터미널에 붙여넣고 이를 실행하십시오.

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

다음 명령을 복사하여 Linux OS의 터미널에 붙여넣고 이를 실행하십시오.

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

다음 명령을 복사하여 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 터미널 콘솔에 붙여넣고 이를 실행하십시오.

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## 사용자 정의 디렉토리에 설치

설치 프로그램 또는 쉘 스크립트를 사용하여 {{site.data.keyword.Bluemix_notm}} CLI를 설치하는 경우, 바이너리는 시스템 디렉토리에 배치됩니다. 다른 디렉토리를 지정하려는 경우에는 다음 단계를 사용하십시오. 

### 1단계: 다음 링크를 사용하여 OS에 따라 2진 패키지를 다운로드하십시오. 

|플랫폼 |다운로드 | 체크섬 |
|---------|----------|---------|
|macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### 2단계: 지정한 디렉토리에 패키지의 압축을 푸십시오. 

   패키지의 압축을 푼 후의 컨텐츠는 다음과 같습니다. 

   Linux 및 MacOS의 경우

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   Windows의 경우

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### 3단계: `PATH` 환경 변수에 추가하고 쉘 자동 완성을 사용으로 설정하십시오. 

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI`를 `PATH` 환경 변수에 추가하십시오. 
   * 쉘 자동 완성 지원(MacOS 및 Linux 전용)에 대해서는 [이 안내서](enable_cli_autocompletion.html)를 참조하십시오. 

## {{site.data.keyword.Bluemix_notm}} CLI를 자세히 살펴보기 위한 기타 링크

* [쉘 자동 완성 사용 설정](/docs/cli/reference/bluemix_cli/enable_cli_autocompletion.html)
* [플러그인으로 {{site.data.keyword.Bluemix_notm}} CLI 기능 확장](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [일반 {{site.data.keyword.Bluemix_notm}} CLI 명령 사용법](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [일반 {{site.data.keyword.Bluemix_notm}} (ibmcloud sl) 명령 사용법](/docs/cli/reference/softlayer/index.html)

## 문제 보고 및 피드백 제출
{: #issues}

다음 옵션을 사용하여 문제를 보고하거나 새 기능 요청을 제출하십시오.
 * [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)에 문제 항목을 작성하십시오. 
 * [IBM Cloud 기술에 대한 Slack - #developer-tools 채널](https://ibm-cloud-tech.slack.com)에 메시지를 남기십시오. [여기](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)에서 팀 액세스 권한을 요청하십시오. 
