---

copyright:
  years: 2015, 2019
lastupdated: "2019-07-12"

keywords: cli, vpn cli plug-in, vpn plugin, cloud foundry vpn, vpn cli, install vpn plugin, vpn parameters

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:note: .note}

# cf CLI의 VPN CLI 플러그인
{: #vpn_cli_for_cf}

명령행 인터페이스(CLI)를 사용하여 {{site.data.keyword.vpn_full}} 서비스를 구성하고 관리할 수 있습니다. {{site.data.keyword.vpn_short}} CLI 플러그인은 두 개의 버전으로 사용 가능합니다(Cloud Foundry CLI 플러그인으로 사용할 항목 및 {{site.data.keyword.cloud}} CLI 플러그인으로 사용할 다른 항목). 두 플러그인 버전 모두 동일한 기능을 제공합니다.
{:shortdesc}

{{site.data.keyword.vpn_short}} 플러그인은 Windows, MAC 및 Linux 운영 체제에 사용 가능합니다. 사용자에게 적용 가능한 항목을 사용해야 합니다.

## cf CLI 플러그인 설치
{: #install-cf-cli-plugin}

시작하기 전에 cf CLI를 설치하십시오. 세부사항은 [Cloud Foundry 명령행 인터페이스](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 참조하십시오.

## VPN CLI 플러그인 설치
{: #install-vpn-cli-plugin}

설치된 {{site.data.keyword.vpn_short}} CLI 플러그인의 이전 버전이 설치되어 있는 경우 우선 이를 삭제해야 합니다. 다음 명령을 사용하십시오.
{: note}

```
cf uninstall-plugin vpn
```
{: codeblock}

### 로컬로 설치

1. [{{site.data.keyword.cloud_notm}} CLI 플러그인 저장소](https://plugins.cloud.ibm.com/ui/repository.html#cf-plugins){: new_window} ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")에서 플랫폼에 대한 {{site.data.keyword.vpn_short}} 플러그인을 다운로드하십시오.

2. 다음 명령을 사용하여 {{site.data.keyword.vpn_short}} 플러그인을 설치하십시오.

	{{site.data.keyword.vpn_short}} 플러그인의 위치로 전환하거나 플러그인 위치에 대한 경로를 지정하십시오.
	{: note}

	- MS Windows OS의 경우:
	```
	cf install-plugin vpn_windows64.exe
	```
	{: codeblock}

	- Apple MAC OS의 경우:
	```
	cf install-plugin vpn_mac_os_amd64
	```
	{: codeblock}

	- Linux OS의 경우:
	```
	cf install-plugin vpn_linuxamd64
	```
	{: codeblock}

### {{site.data.keyword.cloud_notm}} 저장소에서 설치
{: #install-from-ibm-repo}

1. Cloud Foundry CLI 저장소에 {{site.data.keyword.cloud_notm}} 저장소를 추가하십시오. 다음 명령을 사용하십시오.
	```
	cf add-plugin-repo "IBM Cloud" http://plugins.cloud.ibm.com
	```
	{: codeblock}

2. 다음 명령을 실행하십시오.
	```
	cf install-plugin vpn -r IBM Cloud
	```
	{: codeblock}

##VPN 서비스 명령의 목록
{: #list-vpn-cli-commands}

### cf vpn-create connection
{: #cli-vpn-create-connection}

VPN 연결을 작성합니다.
```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### 매개변수
{: #p1}

**connection name:**
연결 이름입니다.

**gateway name:**
게이트웨이 이름입니다.

**-k:**
사전 공유된 키입니다.

**subnet/mask:**
CIDR 형식의 원격 서브넷 주소입니다.

**customer gateway IP address:**
VPN 터널의 원격 엔드포인트 IP 주소입니다.

##### 선택적 매개변수:
{: #op1}

**-d:** 지정된 매개변수에 대한 설명입니다.

**-peer_id:** 원격 피어의 ID입니다. VPN 터널의 다른 엔드포인트입니다.

**-admin_state:** VPN 연결 상태입니다. 값: UP 또는 DOWN.

**-dpd-action:** 피어가 작동 중지된 것으로 발견될 때 수행해야 하는 조치입니다. 값: hold, clear, disabled, restart, restart-by-peer. 기본값: hold

**-gateway_ip:** 로컬 VPN 터널 엔드포인트의 IP 주소입니다.

**-i:** 개시자의 상태입니다. 기본값: 양방향.

**-dpd-timeout:** 세션이 종료되는 제한시간 값(초)입니다. 범위: 6 - 86400초. 기본값: 120초. 활성 상태 지속 제한시간 값은 활성 상태 지속 간격 값보다 커야 합니다.

**-dpd-interval:** 활성 상태 지속 간격(초)입니다. 구성된 간격으로 킵얼라이브 메시지를 전송하여 피어가 작동 중인지 확인하십시오. 범위: 5-86399초. 기본값: 15초

**-ike:** IKE 정책의 이름입니다.

**-ipsec:** IPSec 정책의 이름입니다.


### cf vpn-create ike
{: #cf-vpn-create}

IKE 정책을 작성합니다.
```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 매개변수
{: #p2}

**policy name:**
IKE 정책의 이름입니다.

**gateway name:**
게이트웨이 이름입니다.

##### 선택적 매개변수:
{: #op2}

**-d:** 지정된 매개변수에 대한 설명입니다.

**-pfs:** DH(Diffie-Hellman) 그룹 ID입니다. 값: Group2, Group5, Group14. 기본값: Group2

**-e:** 암호화 알고리즘입니다. 값: aes-128, aes-192, aes-256, 3des. 기본값: aes-128

**-lv:** IKE SA(Security Association)의 수명 값입니다. 범위: 60 - 86400초. 기본값: 86400초

**-auth:** 권한 부여 알고리즘입니다. 값: sha1 또는 sha256

### cf vpn-create ipsec
{: #cf-vpn-create-ipsec}

IPSec 정책을 작성합니다.
```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 매개변수
{: #p3}

**policy name:**
IPSec 정책의 이름입니다.

**gateway name:**
게이트웨이 이름입니다.

##### 선택적 매개변수:
{: #op3}

**-d:** 지정된 매개변수에 대한 설명입니다.

**-pfs:** DH(Diffie-Hellman) 그룹 ID입니다. 값: Group2, Group5, Group14. 기본값: Group2

**-e:** 암호화 알고리즘입니다. 값: aes-128, aes-192, aes-256, 3des. 기본값: aes-128

**-lv:** SA(Security Association)의 수명 값입니다. 범위: 60 - 86400초. 기본값: 3600초

**-auth:** 권한 부여 알고리즘입니다. 값: sha1 또는 sha256

### cf vpn-create gateway

VPN 게이트웨이를 작성합니다.

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 매개변수
{: #p4}

**gateway name:**
게이트웨이 이름입니다.

**-t:** 서비스를 사용하려는 컨테이너입니다. 값: allSingleContainers, allContainerGroups, allContainers. 기본값: 기본값은 없으며 유형을 지정해야 합니다.

#####선택적 매개변수:
{: #op4}

**-gateway_ip:**
게이트웨이의 IP 주소입니다.

**-subnets:**
CIDR 형식의 서브넷 주소입니다.

### cf vpn-show gateways
{: #cf-vpn-show-gateways}

현재 게이트웨이에 대한 정보를 표시합니다.
```
cf vpn-show gateways
```
{: codeblock}

### cf vpn-show ikes
{: #cf-vpn-show-ikes}

현재 IKE 연결에 대한 정보를 표시합니다.
```
cf vpn-show ikes
```
{: codeblock}

### cf vpn-show ipsecs
{: #cf-vpn-show-ipsecs}

현재 IPSec 연결에 대한 정보를 표시합니다.
```
cf vpn-show ipsecs
```
{: codeblock}

### cf vpn-show connections
{: #cf-vpn-show-connections}

모든 현재 연결에 대한 정보를 표시합니다.
```
cf vpn-show connections
```
{: codeblock}

### cf vpn-show ike
{: #cf-vpn-show-ike}

IKE 연결에 대한 정보를 표시합니다.
```
cf vpn-show ike <policy name>
```
{: codeblock}

### cf vpn-show ipsec
{: #cf-vpn-show-ipsec}

IPSec 연결에 대한 정보를 표시합니다.
```
cf vpn-show ipsec <policy name>
```
{: codeblock}

### cf vpn-show gateway
{: #cf-vpn-show-gateway}

게이트웨이에 대한 연결 정보를 표시합니다.
```
cf vpn-show gateway <gateway name>
```
{: codeblock}

### cf vpn-show connection
{: #cf-vpn-show-connection}

특정 연결에 대한 모든 정보를 표시합니다.
```
cf vpn-show connection <connection name>
```
{: codeblock}

### cf vpn-delete
{: #cf-vpn-delete}

기존 연결, 정책 또는 게이트웨이를 삭제합니다.
```
cf vpn-delete ike <policy name>
```
{: codeblock}

```
cf vpn-delete ipsec <policy name>
```
{: codeblock}

```
cf vpn-delete connection <connection name>
```
{: codeblock}

```
cf vpn-delete gateway <gateway name>
```
{: codeblock}

### cf vpn-update connection
{: #cf-vpn-update-connection}

기존 VPN 연결을 업데이트합니다.
```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### 매개변수
{: #p5}

**connection name:**
연결 이름입니다.

##### 선택적 매개변수:
{: #op5}

**gateway name:**
게이트웨이 이름입니다.

**customer gateway IP address:**
VPN 터널의 원격 엔드포인트 IP 주소입니다.

**subnet/mask:**
CIDR 형식의 서브넷 주소입니다.

**-k:**
사전 공유된 키입니다.

**-d:** 지정된 매개변수에 대한 설명입니다.

**-peer_id:** 원격 피어의 ID입니다. VPN 터널의 다른 엔드포인트입니다.

**-admin_state:** VPN 연결 상태입니다. 값: UP 또는 DOWN.

**-dpd-action:** 피어가 작동 중지된 것으로 발견될 때 수행해야 하는 조치입니다. 값: hold, clear, disabled, restart, restart-by-peer. 기본값: hold

**-gateway_ip:** 로컬 VPN 터널 엔드포인트의 IP 주소입니다.

**-i:** 개시자의 상태입니다. 기본값: 양방향.

**-dpd-timeout:** 세션이 종료되는 제한시간 값(초)입니다. 범위: 6 - 86400초. 기본값: 120초

**-dpd-interval:** 활성 상태 지속 간격(초)입니다. 구성된 간격으로 킵얼라이브 메시지를 전송하여 피어가 작동 중인지 확인하십시오. 범위: 5-86399초. 기본값: 15초

**-ike:** IKE 정책의 이름입니다.

**-ipsec:** IPSec 정책의 이름입니다.

### cf vpn-update ike
{: #cf-vpn-update-ike}

IKE 정책을 업데이트합니다.
```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 매개변수
{: #p6}

**policy name:**
IKE 정책의 이름입니다.

##### 선택적 매개변수:
{: #op6}

**gateway name:** 게이트웨이 이름입니다.

**-d:** 지정된 매개변수에 대한 설명입니다.

**-pfs:** DH(Diffie-Hellman) 그룹 ID입니다. 값: Group2, Group5, Group14. 기본값: Group2

**-e:** 암호화 알고리즘입니다. 값: aes-128, aes-192, aes-256, 3des. 기본값: aes-128

**-lv:** IKE SA(Security Association)의 수명 값입니다. 범위: 60 - 86400초. 기본값: 86400초

**-auth:** 권한 부여 알고리즘입니다. 값: sha1 또는 sha256

### cf vpn-update ipsec
{: #cf-vpn-update-ipsec}

IPSec 정책을 업데이트합니다.
```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 매개변수
{: #p7}

**policy name:**
IPSec 정책의 이름입니다.

##### 선택적 매개변수:
{: #op7}

**gateway name:**
게이트웨이 이름입니다.

**-d:** 지정된 매개변수에 대한 설명입니다.

**-pfs:** DH(Diffie-Hellman) 그룹 ID입니다. 값: Group2, Group5, Group14. 기본값: Group2

**-e:** 암호화 알고리즘입니다. 값: aes-128, aes-192, aes-256, 3des. 기본값: aes-128

**-lv:** SA(Security Association)의 수명 값입니다. 범위: 60 - 86400초. 기본값: 3600초

**-auth:** 권한 부여 알고리즘입니다. 값: sha1 또는 sha256

### cf vpn-update gateway
{: #cf-vpn-update-gateway}

기존 VPN 게이트웨이를 업데이트합니다.
```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 매개변수
{: #p8}

**gateway name:**
게이트웨이 이름입니다.

#####선택적 매개변수:
{: #op8}

**-t:** 서비스를 사용하려는 컨테이너입니다. 값: allSingleContainers, allContainerGroups, allContainers. 기본값: 기본값은 없으며 유형을 지정해야 합니다.

**-gateway_ip:**
게이트웨이의 IP 주소입니다.

**-subnets:**
CIDR 형식의 서브넷 주소입니다.

