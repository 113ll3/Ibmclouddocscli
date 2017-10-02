---



copyright:

  years: 2015, 2017
lastupdated: "2017-07-12"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} CLI 시작하기
{: #getting-started}

{{site.data.keyword.Bluemix_notm}} CLI는 명령행 인터페이스를 사용하여 애플리케이션, 컨테이너, 인프라 및 기타 서비스와 상호작용하기 위한 통합된 방법을 제공합니다. 

**제한사항**: {{site.data.keyword.Bluemix_notm}} CLI는 Cygwin에서 지원되지 않으므로 Cygwin 명령행 창에서는 {{site.data.keyword.Bluemix_notm}} CLI를 사용하지 마십시오. 

**참고**: 네트워크에 CLI를 실행하는 호스트와 {{site.data.keyword.Bluemix_notm}} 간에 HTTP 프록시 서버가 포함되어 있는 경우 HTTP_PROXY 환경 변수에 프록시 서버의 호스트 이름 또는 IP 주소를 지정해야 합니다. 

**참고:** {{site.data.keyword.Bluemix_notm}} CLI 도구는 설치에 Cloud Foundry 명령행 인터페이스를 번들화했습니다. 하지만 고유 cf cli 설치가 있는 경우 {{site.data.keyword.Bluemix_notm}} CLI 명령 `bx xxx`와 Cloud Foundry CLI 명령 `cf xxx`를 혼합해서 사용할 수 없습니다. 대신 cf cli를 사용하여 Cloud Foundry 리소스를 관리하려면 `bluemix cf`를 사용하십시오. 백엔드에서 {{site.data.keyword.Bluemix_notm}} CLI와의 공유 컨텍스트의 번들화된 Cloud Foundry CLI 명령을 실행합니다. 또한 `bluemix cf api/login/logout/target`이 허용되지 않으므로 대신 `bluemix api/login/logout/target`을 사용하십시오.

## {{site.data.keyword.Bluemix_notm}} CLI 설치
{: #install_bluemix_cli}

<!-- Online installation Currently Production Only! Please don't forget to replace the domain name-->

### 온라인 설치

인터넷 연결에 액세스한 상태에서 다음 명령을 터미널 콘솔에 복사해서 붙여넣고 실행하십시오.

**macOS**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/osx)
```

**Linux**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/linux)
```

**Windows PowerShell**

다음 명령을 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell) 터미널 콘솔에 복사해서 붙여넣고 실행하십시오.
```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```

### 오프라인 설치

<!-- End of online installation -->

Mac OS 및 Windows의 경우, [{{site.data.keyword.Bluemix_notm}} CLI 패키지](/docs/cli/index.html#downloads)를 다운로드하고 설치 프로그램을 실행하십시오. 

Linux의 경우, 다음 단계를 수행하십시오. 

  1. 패키지를 다운로드하여 압축을 푸십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~$ tar -xvf Bluemix_CLI.tar.gz
  Bluemix_CLI/
  Bluemix_CLI/update_global_config
  Bluemix_CLI/install_bluemix_cli
  Bluemix_CLI/bx/
  Bluemix_CLI/bx/bash_autocomplete
  Bluemix_CLI/bx/zsh_autocomplete
  Bluemix_CLI/bin/
  Bluemix_CLI/bin/bluemix
  ~$
  ```

  2. `Bluemix_CLI` 디렉토리로 이동하여 루트 권한으로 `./install_bluemix_cli` 명령을 실행하십시오. 루트 사용자로 명령을 실행하거나 `sudo` 명령을 사용하여 루트 권한을 확보하십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~# cd Bluemix_CLI
  ~/Bluemix_CLI# sudo ./install_bluemix_cli
  Superuser privileges are required to run this script.
  The Cloud Foundry CLI version 6.15 is already installed.
  Copying files...
  The Bluemix CLI installed successfully. To get started, open a new Linux terminal and enter "bluemix help", or enter "bx help" as short name.
  ~/Bluemix_CLI#
  ```

이제 {{site.data.keyword.Bluemix_notm}} CLI 사용을 시작하거나 추가 플러그인을 설치할 수 있습니다.

## {{site.data.keyword.Bluemix_notm}} CLI의 첫 번째 단계

{{site.data.keyword.Bluemix_notm}} CLI 도구를 설정하려면 사용할 API를 지정해야 합니다. 이는 사용자가 작업할 지역에 따라 달라집니다. 목록을 가져오려면 다음을 사용하십시오. 

```
 ~ $ bluemix regions
Listing Bluemix regions...

Name       Geolocation      Customer   Deployment   Domain               CF API Endpoint                  Type
eu-de      Germany          IBM        Production   eu-de.bluemix.net    https://api.eu-de.bluemix.net    public
au-syd     Sydney           IBM        Production   au-syd.bluemix.net   https://api.au-syd.bluemix.net   public
us-south   US South         IBM        Production   ng.bluemix.net       https://api.ng.bluemix.net       public
eu-gb      United Kingdom   IBM        Production   eu-gb.bluemix.net    https://api.eu-gb.bluemix.net    public
```

액세스하려는 지역에 대한 해당 `CF API Endpoint`를 찾아서 이를 사용하여 다음과 같이 API 엔드포인트를 지정하십시오. 

```
~ $ bluemix api https://api.eu-gb.bluemix.net
Setting api endpoint to https://api.eu-gb.bluemix.net...
OK

API endpoint: https://api.eu-gb.bluemix.net (CF API version: 2.75.0)
Not logged in. Use 'bx login' to log in.
```

그런 다음 프롬프트를 따라 로그인하십시오. 

```
 ~ $ bluemix login
API endpoint: https://api.eu-gb.bluemix.net

Email> user@example.com

Password>
    Authenticating...
    OK
  
    ```

`-o` 및 `-s` 스위치와 함께 사용할 조직과 영역을 지정할 수 있습니다. 그렇지 않으면 로그인 명령에서 둘 이상이 있는 곳을 선택하도록 사용자에게 프롬프트를 표시합니다. 

이제 {{site.data.keyword.Bluemix_notm}} CLI가 설정되었으며 사용할 준비가 되었습니다. 

## 플러그인 설치
{: #install_plug-in}

{{site.data.keyword.Bluemix_notm}} CLI는 플러그인 확장 프레임워크를 지원하여 기본 제공 명령 외에 다른 명령을 통합합니다.


저장소에서, 로컬로 또는 원격 서버에서 플러그인을 설치할 수 있습니다. {{site.data.keyword.Bluemix_notm}}에는 {{site.data.keyword.Bluemix_notm}} CLI 플러그인 및 Cloud Foundry CLI 플러그인을 호스팅하는 저장소가 있습니다. 

   * [{{site.data.keyword.Bluemix_notm}} CLI 플러그인 저장소](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)는 {{site.data.keyword.Bluemix_notm}} CLI의 플러그인을 호스팅합니다.

저장소에서 설치하려면 다음 단계를 수행하십시오. 

  1. 저장소에서 플러그인을 찾으십시오. {{site.data.keyword.Bluemix_notm}} CLI를 설치하고 나면, 기본적으로 공식 저장소 `Bluemix`가 추가됩니다. `bluemix plugin repo-plugins` 명령을 사용하여 `Bluemix` 저장소에 플러그인을 나열할 수 있습니다. 예를 들어, 다음과 같습니다. 

  ```
  ~$ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   Bluemix CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            Bluemix Network Security Group plugin          0.1.1

  ~$
  ```

  2. `bluemix plugin install` 명령을 사용하여 `Bluemix` 저장소에서 플러그인을 설치하십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~$ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


로컬 환경에서 플러그인을 설치하려면 다음 단계를 수행하십시오. 

  1. 플러그인을 다운로드하십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~$ wget http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2--2016-02-18 14:02:12-- http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2
  Resolving public.dhe.ibm.com... 9.17.248.112
  Connection to public.dhe.ibm.com|9.17.248.112|:80... connected.
  HTTP request sent, awaiting response... 200 OK
  Length: 9857792 (9.4M) [text/plain]
  Saving to: 'auto-scaling-darwin-amd64-0.2.2'

  auto-scaling-darwin-0.2.2 100%[===================>] 9.40M 518KB/s in 22s

  2016-02-18 14:02:34 (443 KB/s) - `auto-scaling-darwin-amd64-0.2.2' saved [9857792/9857792]
  ```

  2. UNIX 계열 시스템의 경우 `chmod` 명령을 사용하여 다운로드된 파일을 실행 파일로 만들어야 합니다. 예를 들어, 다음과 같습니다. 

  ```
  ~$ sudo chmod 755 auto-scaling-darwin-amd64-0.2.2
  Password:
  ~$
  ```

  3. `bluemix plugin install` 명령을 사용하여 플러그인을 설치하십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~$ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```

원격 서버에서 설치하려면 다음 단계를 수행하십시오. 

  1. `bluemix plugin install` 명령을 사용하여 원격 URL에서 직접 플러그인을 설치하십시오. 예를 들어, 다음과 같습니다. 

  ```
  ~$ bluemix plugin install http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


{{site.data.keyword.Bluemix_notm}} 명령행을 사용할 준비가 되었습니다. `bluemix help`를 실행하여 명령 및 설명 목록을 확인하십시오. 

## 연락하기

릴리스 정보 찾기, 피드백 제공, 질문하기에는 다음 옵션을 사용하십시오. 
 * 최신 릴리스에 대한 세부사항의 경우 및 문제 보고하기: [{{site.data.keyword.Bluemix_notm}} CLI SDK](https://github.com/IBM-Bluemix/bluemix-cli-sdk){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)
 * 질문하기 및 커뮤니티와 지식 공유하기: [bluemix-cli Slack channel](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg)
