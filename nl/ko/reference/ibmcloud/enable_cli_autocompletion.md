---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} CLI의 쉘 자동 완성 사용 설정(Linux/MacOS 전용)

버전 `0.7.0`부터 {{site.data.keyword.Bluemix_notm}} CLI 설치 프로그램은 쉘 자동 완성을 자동으로 사용으로 설정하지 않습니다. 자동 완성 지원을 사용하려면 이를 수동으로 사용 설정해야 합니다. 자동 완성 스크립트는 다음 위치에 설치됩니다.

* `Bash` 자동 완성: `/usr/local/ibmcloud/autocomplete/bash_autocomplete`
* `Zsh` 자동 완성: `/usr/local/ibmcloud/autocomplete/zsh_autocomplete`

## Linux에서의 자동 완성 사용 설정

* `Bash`를 사용 중인 경우 

`source /usr/local/ibmcloud/autocomplete/bash_autocomplete`를 다음 파일 중 하나에 추가하십시오.

  * 로그인 쉘의 경우: `~/.bash_profile`
  * 비로그인 쉘의 경우: `~/.bash_rc`
  
* `Zsh`를 사용 중인 경우 

`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete`를 `~/.zshrc`에 추가하십시오.

## MacOS에서의 자동 완성 지원 사용 설정

* `Bash`를 사용 중인 경우 

`source /usr/local/ibmcloud/autocomplete/bash_autocomplete`를 `~/.bash_profile`에 추가하십시오.
* `Zsh`를 사용 중인 경우 

`source /usr/local/ibmcloud/autocomplete/zsh_autocomplete`를 `~/.zshrc`에 추가하십시오.
