---

copyright:
  years: 2017, 2019
lastupdated: "2019-05-21"

keywords: cli, sdk generator, open api, ibmcloud sdk, ibmcloud sdk generate, generate, sdk validate, sdk list, cloud foundry, rest api 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# SDK 생성기
{: #sdk-cli}

{{site.data.keyword.IBM}} SDK SDK 생성기 플러그인은 {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)에 설치될 수 있습니다.

{{site.data.keyword.cloud_notm}}에서 개발자는 이 플러그인을 사용하여 [Open API 스펙 ](https://www.openapis.org/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 준수 REST API 정의에서 SDK를 생성할 수 있습니다. REST API 정의를 변경하는 경우 이 플러그인을 사용하여 전체 프로젝트가 아닌 SDK만 재생성할 수 있습니다.

또한 지정된 영역의 Cloud Foundry 애플리케이션이 SDK 생성에 유효한 REST API 정의를 포함하는지 여부를 확인할 수 있습니다. 마지막으로 SDK 생성기 요구사항에 부합하는지 REST API 정의를 유효성 검증하기 위해 {{site.data.keyword.IBM_notm}} SDK 생성기 플러그인을 사용할 수 있습니다.

이 {{site.data.keyword.IBM_notm}} SDK 생성기 플러그인을 사용하면 앱의 백엔드 서비스를 생성된 SDK와 쉽게 통합할 수 있습니다. REST API를 변경한 경우 SDK를 재생성하고 완벽한 SDK 업그레이드를 위해 이전 SDK를 대체할 수 있습니다. 또한 CLI를 DevOps 파이프라인과 통합하여 SDK가 앱이 빌드될 때마다 항상 API 스펙과 일치하도록 할 수도 있습니다.

REST API 정의는 유효해야 하며 라이브 서버 엔드포인트에서 호스팅되거나 시스템의 로컬 파일이어야 합니다. REST API 정의가 호스팅되는 경우 상대 URL을 `OPENAPI_SPEC` 환경 변수에 정의해야 합니다.

## 요구사항
{: #prereqs}

다음 요구사항을 충족하는지 확인하십시오.

* [{{site.data.keyword.cloud_notm}}](https://{DomainName}/login){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 계정이 있습니다.
* [Open API ](https://www.openapis.org/){: new_window} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘") 스펙에 부합하는 올바른 API 정의가 있습니다.

## 설치
{: #sdk-installation}

[{{site.data.keyword.cloud_notm}}개발자 도구](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)를 설치하십시오.

## 명령
{: #commands}

다음 명령을 사용하여 SDK를 생성하거나 Open API 정의 파일의 유효성을 검증하거나 Cloud Foundry 앱을 나열하십시오.

### SDK 생성
{: #gen}

`ibmcloud sdk generate [arguments...] [command options]`를 사용하십시오.

#### 인수
{: #gen-args}

* `APP_NAME` - 현재 영역에서 Cloud Foundry 앱의 이름
* `OPENAPI_DOC_LOCATION` - 원시 REST API 정의 JSON 또는 Yaml에 대한 상대 파일 경로 또는 URL
* `GENERATED_SDK_NAME` (선택적) - 생성된 SDK 이름


#### 옵션
{: #gen-options}

* `PLATFORM` (필수)
   * `--android` - Android SDK 생성
   * `--ios` - iOS Swift SDK 생성
   * `--swift` - Swift 서버 SDK 생성
   * `--js` - JavaScript SDK 생성
* `LOCATION` (필수) - `OPENAPI_DOC_LOCATION` 유형 지정
   * `-r` - 원격 URL
   * `-f` - 파일
   * `-a` - {{site.data.keyword.cloud_notm}}에서 실행되는 앱
   * `-l` - 로컬 호스트 URL
* `--output "YOUR_RELATIVE_PATH"` (선택적) - `YOUR_RELATIVE_PATH`에서 지정한 디렉토리에 생성된 SDK 배치(기존 SDK가 있을 경우 겹쳐쓰기)
* `--unzip` (선택적) - 생성된 SKD 추출(기존 SDK 아티팩트가 있을 경우 겹쳐쓰기)


####  사용법
{: #gen-usage}

{{site.data.keyword.cloud_notm}}에서 실행 중인 Cloud Foundry 앱에서 SDK를 생성하기 위해 CLI의 매개변수로 앱 이름을 사용할 수 있습니다. 다음 명령은 `SDK_Name`으로 앱의 이름을 사용합니다.

```
ibmcloud sdk generate [APP_NAME] [LOCATION] [PLATFORM]
```
{: codeblock}

Open API 정의 파일이나 로컬 JSON 또는 Yaml 파일에 대한 URL에서 SDK를 생성하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk generate [OPENAPI_DOC_LOCATION] [SDK_Name] [LOCATION] [PLATFORM]
```
{: codeblock}


### Open API 정의 유효성 검증
{: #validating}

`ibmcloud sdk validate [argument]`를 사용하십시오.


#### 인수
{: #val-args}

* `APP_NAME` - 현재 영역에서 Cloud Foundry 앱의 이름
* `OPENAPI_DOC_LOCATION` - 원시 REST API 정의 JSON 또는 Yaml에 대한 상대 파일 경로 또는 URL


####  사용법
{: #val-usage}

{{site.data.keyword.cloud_notm}}에서 실행 중인 Cloud Foundry 앱의 API 스펙을 유효성 검증하기 위해 CLI의 매개변수로 앱 이름을 사용할 수 있습니다.

```
ibmcloud sdk validate [APP_NAME] [LOCATION]
```
{: codeblock}

API 스펙 문서나 로컬 JSON 또는 Yaml 파일에 대한 URL에서 SDK를 생성하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk validate [OPENAPI_DOC_LOCATION] [LOCATION]
```
{: codeblock}



### 앱 나열(Cloud Foundry)
{: #list-apps}

앱을 나열하고 API 스펙의 유효성을 검증하려면 `ibmcloud sdk list [argument] [option]`을 사용하십시오. `OPENAPI_SPEC` 환경 변수가 스펙을 호스팅하는 상대 URL 경로로 설정되어야 합니다.


#### 인수
{: #list-args}

* `SPACE_NAME` (선택적) - 앱을 검색하려는 현재 조직 내의 Cloud Foundry 영역 이름입니다. 제공하지 않으면 현재 영역이 검색됩니다.


#### 옵션
{: #list-options}

* `--url` (선택적) - 목록에 있는 각 앱에 대해 Open API 정의의 완전히 형식화된 URL을 표시합니다.


####  사용법
{: #list-usage}

현재 영역에 있는 앱을 나열하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk list
```
{: codeblock}

현재 영역의 앱을 나열하고 API 스펙 URL을 표시하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk list --url
```
{: codeblock}

특정 영역의 앱을 나열하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk list [SPACE_NAME]
```
{: codeblock}

특정 영역의 앱을 나열하고 API 스펙 URL을 표시하려면 다음 명령을 사용하십시오.

```
ibmcloud sdk list [SPACE_NAME] --url
```
{: codeblock}
