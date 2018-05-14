---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# {{site.data.keyword.Bluemix_notm}} CLI 다운로드 및 설치
{: #download_install}

설치 프로그램 또는 쉘을 사용하여 CLI를 다운로드하고 설치할 수 있습니다.

## 설치 프로그램 사용
{: #installer}

{{site.data.keyword.Bluemix_notm}} CLI를 설치하려면 다음을 수행하십시오.
* [여기](all_versions.html)로 이동하여 설치 프로그램을 다운로드하십시오.
* macOS 및 Windows의 경우 설치 프로그램을 실행하십시오. 
* Linux의 경우 설치 프로그램 패키지를 다운로드한 후 압축을 풀고 루트 권한을 사용하여 설치 스크립트를 실행하십시오.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## 쉘에서 설치
{: #shell_install}


### macOS

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
