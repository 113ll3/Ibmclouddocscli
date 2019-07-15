---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-10"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# 일반 CLI(ibmcloud) 명령
{: #ibmcloud_cli}

{{site.data.keyword.cloud_notm}} 명령행 인터페이스(CLI)는 사용자가 {{site.data.keyword.cloud_notm}}와 상호작용할 수 있도록 네임스페이스별로 그룹화된 명령 세트를 제공합니다.
{: shortdesc}

{{site.data.keyword.cloud_notm}} 명령행 클라이언트는 Cloud Foundry 명령행 클라이언트를 해당 설치에서 번들화합니다. 자신에게 직접 설치한 Cloud Foundry CLI가 있는 경우에는 {{site.data.keyword.cloud_notm}} CLI 명령 및 해당 설치의 Cloud Foundry CLI 명을 동일한 컨텍스트에서 함께 사용하지 마십시오. Cloud Foundry CLI를 사용하여 {{site.data.keyword.cloud_notm}} CLI 컨텍스트에서 Cloud Foundry 리소스를 관리하려면 **`ibmcloud cf [command]`**를 대신 사용하십시오. **`ibmcloud cf api/login/logout/target`**은 허용되지 않으며 대신 **`ibmcloud api/login/logout/target`**을 사용해야 한다는 점을 참고하십시오.

2018년 5월부터 {{site.data.keyword.cloud_notm}} CLI 명령은 **`bluemix`** 및 **`bx`**에서 **`ibmcloud`**로 변경되었습니다. 그러나 나중에 제거되기 전까지는 여전히 **`bluemix`** 및 **`bx`** CLI 명령을 사용할 수 있습니다.
{: tip}

다음에는 해당 이름, 인수, 옵션, 필수 소프트웨어, 설명 및 예제를 포함하여 {{site.data.keyword.cloud_notm}} CLI에서 지원하는 자세한 명령이 나열되어 있습니다.

전제조건에는 명령을 사용하기 전에 필요한 조치가 나열되어 있습니다.

<dl>
<dt>Docker</dt>
<dd>Docker CLI를 설치하십시오.</dd>
<dt>엔드포인트</dt>
<dd>**`ibmcloud api`** 명령을 사용하여 API 엔드포인트를 설정하십시오.</dd>
<dt>로그인</dt>
<dd>**`ibmcloud login`** 명령을 사용하여 로그인하십시오. 연합 ID로 로그인하는 경우에는 **`--sso`** 용하여 일회성 패스코드로 인증하거나 **`--apikey`** 옵션을 사용하여 API 키로 인증하십시오.</dd>
<dt>대상</dt>
<dd>**`ibmcloud target`** 명령을 사용하여 조직 및 영역을 설정하십시오.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

첫 번째 레벨 기본 제공 명령 및 지원되는 {{site.data.keyword.cloud_notm}} CLI 네임스페이스에 대한 일반 도움말 또는 특정 기본 제공 명령 또는 네임스페이스의 도움말을 표시합니다.

```
ibmcloud help [COMMAND|NAMESPACE]
```

### 전제조건
{: #help-prereqs}

없음.

### 명령 옵션
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>해당 도움말이 표시되는 명령 또는 네임스페이스입니다. 값을 지정하지 않으면 {{site.data.keyword.cloud_notm}} CLI의 일반 도움말이 표시됩니다. 선택사항.</dd>
</dl>

### 예제
{: #help-examples}

{{site.data.keyword.cloud_notm}} CLI의 일반 도움말을 표시합니다.
```
ibmcloud help
```
{: codeblock}

**`dev`** 명령의 도움말을 표시합니다.
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

{{site.data.keyword.cloud_notm}} API 엔드포인트를 설정하거나 확인합니다.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### 전제조건
{: #api-prereqs}

없음.

### 명령 옵션
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>대상으로 지정된 API 엔드포인트입니다(예: `https://cloud.ibm.com`). **`API_ENDPOINT`** 및 **`--unset`** 옵션 중 하나를 지정하지 않으면 현재 API 엔드포인트가 표시됩니다. 선택사항.</dd>
<dt>--skip-ssl-validation</dt>
<dd>HTTP 요청의 SSL 유효성 검증을 무시합니다. 선택사항.</dd>
<dt>--unset</dt>
<dd>API 엔드포인트 설정을 제거합니다.</dd>
</dl>

### 예제
{: #api-examples}

API 엔드포인트를 cloud.ibm.com으로 설정합니다.
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

현재 API 엔드포인트를 확인합니다.
```
ibmcloud api
```
{: codeblock}

API 엔드포인트를 제거합니다.
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

구성 파일에 기본값을 작성합니다.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### 전제조건
{: #config-prereqs}

없음.

### 명령 옵션
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>CLI 버전 확인을 사용 또는 사용 안함으로 설정합니다. 올바른 값은 `true` 또는 `false`입니다.</dd>
<dt>--color</dt>
<dd>색상 출력을 사용 또는 사용 안함으로 설정합니다. 이 옵션은 기본적으로 사용 안함으로 설정되어 있습니다. 올바른 값은 `true` 또는 `false`입니다.</dd>
<dt>--http-timeout</dt>
<dd>HTTP 요청의 제한시간 값입니다. 기본값은 60초입니다.</dd>
<dt>--locale</dt>
<dd>기본 로케일을 설정합니다. 값이 지정되지 않은 경우 이전 로케일이 삭제됩니다. </dd>
<dt>--trace </dt>
<dd>터미널 또는 지정된 파일에 대한 HTTP 요청을 추적합니다. 올바른 값은 `true` 또는 `false`입니다.</dd>
</dl>

한 번에 하나의 옵션만 지정할 수 있습니다.
{: tip}

### 예제
{: #config-examples}

HTTP 요청 제한시간을 30초로 설정합니다.
```
ibmcloud config --http-timeout 30
```
{: codeblock}

HTTP 요청에 대한 추적 출력을 사용하도록 설정합니다.
```
ibmcloud config --trace true
```
{: codeblock}

`/home/usera/my_trace` 파일에 대한 HTTP 요청을 추적합니다.
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

색상 출력을 사용하지 않도록 설정합니다.
```
ibmcloud config --color false
```
{: codeblock}

로케일을 zh_Hans로 설정합니다.
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

로케일 설정을 지웁니다.
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

**`ibmcloud info`** 명령은 CLI 버전 0.14부터 더 이상 사용할 수 없습니다. 최신 CLI 버전을 설치하려면 [독립형 {{site.data.keyword.cloud_notm}} CLI 설치](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 참조하십시오.

## ibmcloud cf
{: #ibmcloud_cf}

임베디드 Cloud Foundry CLI를 호출합니다.
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### 전제조건
{: #info-prereqs}

없음.

### 명령 옵션
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>호출 메시지를 표시하지 않습니다.</dd>
</dl>

### 예제
{: #info-examples}

Cloud Foundry 앱을 나열합니다.

```
ibmcloud cf apps
```

`Invoking cf command...` 메시지를 표시하지 않고 Cloud Foundry 서비스를 나열합니다.
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf 설치
{: #ibmcloud_cf_install}

IBM Cloud CLI의 Cloud Foundry CLI 설치
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### 전제조건
{: #cfinstall-prereqs}

없음.

### 명령 옵션
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>설치할 Cloud Foundry CLI의 버전 지정</dd>
  <dt>--restore</dt>
  <dd>Cloud Foundry CLI의 사전 번들 버전 으로 복원</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 설치 강제 실행</dd>
</dl>

### 예제
{: #cfinstall-examples}

Cloud Foundry CLI `6.44.1` 설치:

```
ibmcloud cf install -v 6.44.1
```

확인 없이 최신 버전의 Cloud Foundry CLI 설치:

```
ibmcloud cf install -f
```

기본 번들 Cloud Foundry CLI로 복구:

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

{{site.data.keyword.cloud_notm}} CLI에 로그인합니다.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### 전제조건
{: #login-prereqs}

없음.

### 명령 옵션
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>API 엔드포인트입니다(예: `cloud.ibm.com`). </dd>
<dt>--apikey API_KEY 또는 @API_KEY_FILE_PATH</dt>
<dd>API 키 컨텐츠 또는 @로 표시되는 API 키 파일의 경로입니다.</dd>
<dt>-u USER_NAME</dt>
<dd>사용자 이름입니다. 선택사항.</dd>
<dt>-p PASS_WORD</dt>
<dd>사용자 비밀번호입니다. 선택사항.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>대상 계정의 ID입니다. 이 옵션은 **`--no account`** 옵션과 배타적입니다.</dd>
<dt>--no-account</dt>
<dd>계정 없이 강제 로그인합니다. 이 옵션은 권장되지 않습니다. 이는 **`-c`**와 배타적입니다.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>대상 리소스 그룹의 이름입니다. 선택사항.</dd>
<dt>-r REGION</dt>
<dd>대상 지역의 이름입니다(us-south 또는 eu-gb).</dd>
<dt>--no-region</dt>
<dd>지역을 대상으로 지정하지 않고 강제로 로그인합니다.</dd>
<dt>-o ORG</dt>
<dd>대상 조직의 이름입니다. 이 옵션은 더 이상 사용되지 않습니다. 대신 **`ibmcloud target -o org_name`**을 사용하십시오. 선택사항.</dd>
<dt>-s SPACE</dt>
<dd>대상 영역의 이름입니다. 이 옵션은 더 이상 사용되지 않습니다. 대신 **`ibmcloud target -s space_name`**을 사용하십시오. 선택사항.</dd>
<dt>--no-iam</dt>
<dd>공용 IAM 대신 로그인 서버를 통한 인증을 강제 실행합니다.</dd>
<dt>--skip-ssl-validation</dt>
<dd>HTTP 요청의 SSL 유효성 검증을 무시합니다. 이 옵션은 권장되지 않습니다.</dd>
</dl>

### 예제
{: #login-examples}

대화식으로 로그인합니다.

```
ibmcloud login
```
{: codeblock}

사용자 이름과 비밀번호로 로그인하고 대상 계정, 조직 및 영역을 설정합니다.
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

일회성 패스코드로 로그인하고 대상 계정, 조직 및 영역을 설정합니다.
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Cloud Found 조직 및 영역을 설정합니다. 다음 명령을 실행하여 조직 및 영역을 대화식으로 식별할 수 있습니다.

```
  ibmcloud target --cf
```
{: codeblock}

또는 서비스가 속하는 조직 및 영역을 알고 있는 경우 다음 명령을 사용할 수 있습니다.

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

연관된 계정이 있는 API 키를 사용합니다.

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

연관된 계정이 없는 API 키를 사용합니다.

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

API 키에 연관된 계정이 있는 경우, 다른 계정으로의 전환이 지원되지 않습니다.
{: note}

다음과 같이 일회성 패스코드를 사용하십시오.

```
ibmcloud login -u UserID --sso
```
{: codeblock}

그러면 CLI에서 URL 링크를 제공하고 패스코드를 위한 프롬프트가 표시됩니다.

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

브라우저에서 링크를 열어서 패스코드를 가져오십시오. 로그인할 콘솔에 지정된 패스코드를 입력하십시오.

## ibmcloud logout
{: #ibmcloud_logout}

CLI에서 로그아웃합니다.

```
ibmcloud logout
```
{: codeblock}

### 전제조건
{: #logout-prereqs}

없음.

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.cloud_notm}}의 모든 지역에 대한 정보를 확인합니다.

```
ibmcloud regions
```
{: codeblock}

### 전제조건
{: #regions-prereqs}

**`ibmcloud api`** 명령을 사용하여 API 엔드포인트를 설정하십시오.

## ibmcloud target
{: #ibmcloud_target}

대상 계정, 지역, 조직 또는 영역을 설정하거나 봅니다.

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### 전제조건
{: #target-prereqs}

* **`ibmcloud api`** 명령을 사용하여 API 엔드포인트를 설정하십시오.
* **`ibmcloud login`** 명령을 사용하여 로그인하십시오. 연합 ID로 로그인하는 경우에는 **`--sso`** 용하여 일회성 패스코드로 인증하거나 **`--apikey`** 옵션을 사용하여 API 키로 인증하십시오.

### 명령 옵션
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>대상 계정의 ID입니다. 선택사항.</dd>
<dt>-r REGION</dt>
<dd>대상 지역의 이름입니다(us-south 또는 eu-gb). 선택사항.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>대상 리소스 그룹의 이름입니다. 선택사항.</dd>
<dt>--cf</dt>
<dd>대상 조직 및 영역을 대화식으로 지정하십시오.</dd>
<dt>--cf-api</dt>
<dd>Cloud Foundry API 엔드포인트입니다.</dd>
<dt>-o ORG</dt>
<dd>대상 조직의 이름입니다. 선택사항.</dd>
<dt>-s SPACE</dt>
<dd>대상 영역의 이름입니다. 선택사항.</dd>
<dt>--unset-region</dt>
<dd>대상 지역을 지역을 지웁니다.</dd>
<dt>--unset-resource-group</dt>
<dd>대상 리소스 그룹을 지역을 지웁니다.</dd>
<dt>--output FORMAT</dt>
<dd>지정된 출력 형식입니다. JSON은 현재 유일하게 지원되는 형식입니다.</dd>
</dl>

옵션이 지정되지 않은 경우, 현재 계정, 영역, 조직 및 영역이 표시됩니다.
{: note}

### 예제
{: #target-examples}

현재 계정, 조직 및 영역 설정하기:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

새 지역으로 전환하기:
```
ibmcloud target -r eu-gb
```
{: codeblock}

현재 계정, 지역, 조직 및 영역 보기:
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

최신 버전으로 CLI를 업데이트합니다.

```
ibmcloud update [-f]
```
### 전제조건
{: #update-prereqs}

### 명령 옵션
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>확인 없이 업데이트를 강제 실행합니다. 루트 권한이 필요합니다.</dd>
</dl>

## 일반 클래식 인프라 서비스 명령
{: #classic-service-commands}

인프라 서비스를 구성하고 관리하려면 {{site.data.keyword.cloud_notm}} CLI에서 클래식 인프라 명령을 사용하십시오.

사용 가능한 명령의 목록을 보려면 **`ibmcloud sl`** 명령을 실행하십시오.
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Classic infrastructure Block Storage
   cdn             Classic infrastructure Content Delivery Network
   file            Classic infrastructure File Storage
   dns             Classic infrastructure Domain Name System
   globalip        Classic infrastructure Global IP addresses
   hardware        Classic infrastructure hardware servers
   image           Classic infrastructure Compute images
   ipsec           Classic infrastructure IPSEC VPN
   loadbal         Classic infrastructure Load balancers
   security        Classic infrastructure SSH Keys and SSL Certificates
   securitygroup   Classic infrastructure network security groups
   subnet          Classic infrastructure Network subnets
   ticket          Classic infrastructure Manage Tickets
   vlan            Classic infrastructure Network VLANs
   vs              Classic infrastructure Virtual Servers
   order           Classic infrastructure Orders
   user            Classic infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

명령에 대한 도움말 정보를 보려면 다음 명령을 실행하십시오.
```
ibmcloud sl [command] -h
```

**`ibmcloud sl init`** 명령은 CLI 버전 `0.14`부터 더 이상 사용할 수 없습니다. 최신 CLI 버전을 설치하려면 [독립형 {{site.data.keyword.cloud_notm}} CLI 설치](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 참조하십시오.
{: note}

## ibmcloud sl help
{: #sl_help}

클래식 인프라 환경을 운영하기 위한 모든 명령에 대한 도움말 정보를 봅니다.
```
ibmcloud sl help
```
{: codeblock}

