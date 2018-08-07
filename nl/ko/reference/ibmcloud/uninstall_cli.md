---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI 설치 제거

특정 플랫폼에서 {{site.data.keyword.Bluemix_notm}}의 설치 제거 방법에 대한 지시사항은 다음 섹션을 참조하십시오. 

## Windows에서 설치 제거

* `시작` 단추를 클릭한 후에 `제어판`을 선택하십시오.
* 팝업 창에서 `프로그램 설치 제거`를 클릭하십시오. 
* 팝업 애플리케이션 목록에서 `IBM Cloud 명령행 인터페이스`를 찾으십시오. 
* `IBM Cloud 명령행 인터페이스`를 마우스 오른쪽 단추로 클릭하고 `설치 제거`를 선택하십시오. 
* 설치 제거 프로그램이 시작됩니다. 지시사항에 따라 설치 제거를 완료하십시오.

## Linux/macOS에서 설치 제거

### 버전 `0.9.0` 이전

* 터미널을 열고 다음 명령을 실행하십시오. 
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* 자동 완성 스크립트를 구성한 경우에는 이를 정리하십시오. 세부사항은 [CLI 자동 완성 사용](enable_cli_autocompletion.html)을 참조하십시오. 

### `0.9.0` 이상

* 터미널을 열고 다음 명령을 실행하십시오. 
  * `/usr/local/ibmcloud/uninstall`
* 자동 완성 스크립트를 구성한 경우에는 이를 정리하십시오. 세부사항은 [CLI 자동 완성 사용](enable_cli_autocompletion.html)을 참조하십시오. 
