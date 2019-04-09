---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl, virtual server, virtual server commands

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 가상 서버 작성 및 작업
{: #cli-virtual-servers}

{{site.data.keyword.BluVirtServers}}는 전용 코어와 메모리 할당을 포함하여 구매하는 확장 가능한 가상 서버입니다. 컴퓨팅 리소스를 찾고 있다면 이미지 템플리트와 같은 기능에 액세스하여 몇 분 안에 추가할 수 있는 최고의 옵션입니다. 

다음 명령을 사용하여 클래식 인프라 가상 서버를 관리하십시오.
{: shortdesc}

## ibmcloud sl vs cancel
{: #sl_vs_cancel}

가상 서버 인스턴스를 취소합니다.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs cancel 12345678
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스를 취소합니다.

## ibmcloud sl vs capture
{: #sl_vs_capture}

이미지로 가상 서버 인스턴스를 캡처합니다.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-n, --name</dt>
<dd>필수. 이미지의 이름입니다.</dd>
<dt>--all</dt>
<dd>VS에 소속된 모든 디스크 캡처.</dd>
<dt>--note</dt>
<dd>이미지와 연관시킬 참고 추가.</dd>
</dl>

**예제**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
{: codeblock}

이 명령은 모든 디스크와 함께 ID가 `12345678`인 가상 서버 인스턴스를 이름이 `mycloud`이며 `testing` 참고가 지정된 이미지로 캡처합니다.

## ibmcloud sl vs create
{: #sl_vs_create}

가상 서버 인스턴스를 작성합니다.
```
ibmcloud sl vs create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>필수. FQDN의 호스트 부분.</dd>
<dt>-D, --domain</dt>
<dd>필수. FQDN의 도메인 부분.</dd>
<dt>-c, --cpu</dt>
<dd>필수. CPU 코어 수.</dd>
<dt>-m, --memory</dt>
<dd>필수. 메모리(MB).</dd>
<dt>--flavor</dt>
<dd>공용 Virtual Server 특성 키 이름.</dd>
<dt>-d, --datacenter</dt>
<dd>필수. 데이터 센터의 짧은 이름.</dd>
<dt>-o, --os</dt>
<dd>OS 설치 코드. 팁: <OS>_LATEST를 지정할 수 있습니다.</dd>
<dt>--image</dt>
<dd>이미지 ID. 'ibmcloud sl image list'를 참조하십시오.</dd>
<dt>--billing</dt>
<dd>청구 비율. 기본값: hourly. 옵션: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>전용 Virtual Server 작성(개인용 노드).</dd>
<dt>--host-id</dt>
<dd>전용 Virtual Server를 프로비저닝할 호스트 ID.</dd>
<dt>--san</dt>
<dd>로컬 디스크 대신 SAN 스토리지 사용.</dd>
<dt>--test</dt>
<dd>가상 서버를 실제로 작성하지 않음.</dd>
<dt>--export</dt>
<dd>템플리트 파일로 옵션 내보내기.</dd>
<dt>-i, --postinstall</dt>
<dd>다운로드할 사후 설치 스크립트.</dd>
<dt>-k, --key</dt>
<dd>루트 사용자에게 추가할 SSH 키 ID(다중 발생 허용).</dd>
<dt>--disk</dt>
<dd>디스크 크기(다중 발생 허용).</dd>
<dt>--private</dt>
<dd>가상 서버가 사설 네트워크만 액세스하도록 강제 실행.</dd>
<dt>--like</dt>
<dd>기존 가상 서버의 구성 사용.</dd>
<dt>-n, --network</dt>
<dd>네트워크 포트 속도(Mbps).</dd>
<dt>-g, --tag</dt>
<dd>인스턴스에 추가할 태그(다중 발생 허용).</dd>
<dt>-t, --template</dt>
<dd>명령행 옵션을 기본값으로 설정하는 템플리트 파일.</dd>
<dt>-u, --userdata</dt>
<dd>사용자 정의 메타데이터 문자열.</dd>
<dt>-F, --userfile</dt>
<dd>파일에서 사용자 데이터 읽기.</dd>
<dt>--vlan-public</dt>
<dd>가상 서버를 배치하려는 공용 VLAN ID.</dd>
<dt>--vlan-private</dt>
<dd>가상 서버를 배치하려는 사설 VLAN ID.</dd>
<dt>-S, --public-security-group</dt>
<dd>공용 인터페이스와 연관시킬 보안 그룹 ID(다중 발생 허용).</dd>
<dt>-s, --private-security-group</dt>
<dd>사설 인터페이스와 연관시킬 보안 그룹 ID(다중 발생 허용).</dd>
<dt>--wait</dt>
<dd>리턴하기 전에 가상 서버가 프로비저닝을 완료할 때까지 최대 X초 동안 대기.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
{: codeblock}

이 명령은 호스트 이름이 myvsi이고 도메인이 ibm.com이며 4개의 CPU 코어와 4096M 메모리를 포함하며 데이터 센터 `dal10`에 위치하는 가상 서버 인스턴스를 주문합니다.

## ibmcloud sl vs options
{: #sl_vs_options}

가상 서버 인스턴스 작성을 위한 옵션을 나열합니다.
```
ibmcloud sl vs options [OPTIONS]
```

**예제**:
```
ibmcloud sl vs options
```
{: codeblock}

이 명령은 가상 서버 인스턴스 작성을 위한 모든 옵션(예: 데이터 센터, CPU, 메모리, OS, 디스크, 네트워크 속도 등)을 나열합니다.

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

가상 서버 인스턴스 인증 정보를 나열합니다.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```

**예제**:
```
ibmcloud sl vs credentials 12345678
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스의 모든 사용자 이름과 비밀번호 쌍을 나열합니다.

## ibmcloud sl vs detail
{: #sl_vs_detail}

가상 서버 인스턴스에 대한 세부사항을 가져옵니다.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--passwords</dt>
<dd>비밀번호를 표시합니다(유출되지 않도록 주의).</dd>
<dt>--price</dt>
<dd>연관된 가격을 표시합니다.</dd>
</dl>

**예제**:
```
ibmcloud sl vs details 12345678
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스에 대한 자세한 정보를 나열합니다.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

가상 가상의 인스턴스에 대한 DNS 레코드를 동기화합니다.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>호스트의 A 레코드를 동기화합니다.</dd>
<dt>--aaaa-record</dt>
<dd>호스트의 AAAA 레코드를 동기화합니다.</dd>
<dt>--ptr</dt>
<dd>호스트의 PTR 레코드를 동기화합니다.</dd>
<dt>--ttl</dt>
<dd>A 및/또는 PTR 레코드용 TTL을 설정합니다. 기본값은 7200입니다.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스의 A 레코드(IP V4 주소)를 DNS 서버에 동기화하고 이 A 레코드의 TTL을 3600으로 설정합니다.

## ibmcloud sl vs edit
{: #sl_vs_edit}

가상 서버 인스턴스의 세부사항을 편집합니다.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>FQDN의 도메인 부분.</dd>
<dt>-H, --hostname</dt>
<dd>FQDN의 호스트 부분. 예: server.</dd>
<dt>-g, --tag</dt>
<dd>설정할 태그 또는 모두 제거하려면 빈 문자열 지정.</dd>
<dt>-u, --userdata</dt>
<dd>사용자 정의 메타데이터 문자열.</dd>
<dt>-F, --userfile</dt>
<dd>파일에서 사용자 데이터 읽기.</dd>
<dt>--public-speed</dt>
<dd>공용 포트 속도. 옵션: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>개인용 포트 속도. 옵션: 0,10,100,1000,10000.</dd>
</dl>

**예제**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
이 명령은 ID가 `12345678`인 가상 서버 인스턴스를 업데이트하고 해당 도메인을 "ibm.com"으로, 호스트 이름을 "myapp"으로, 태그를 "testcli"로 설정합니다.

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

전용 가상 서버용 호스트를 작성합니다.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>필수. FQDN의 호스트 부분.</dd>
<dt>-D, --domain</dt>
<dd>필수. FQDN의 도메인 부분.</dd>
<dt>-d, --datacenter</dt>
<dd>필수. 데이터 센터의 짧은 이름.</dd>
<dt>-s, --size</dt>
<dd>전용 호스트 크기. 현재 하나의 크기(56_CORES_X_242_RAM_X_1_4_TB)만 사용 가능합니다.</dd>
<dt>-b, --billing</dt>
<dd>청구 비율. 기본값: hourly. 옵션: hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>전용 호스트를 배치할 사설 VLAN ID. 'ibmcloud sl vlan list'를 참조하십시오.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

계정의 전용 호스트를 나열합니다.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>명령 옵션</strong>:
<dl>
<dt>-n, --name</dt>
<dd>전용 호스트의 이름별 필터링.</dd>
<dt>-d, --datacenter</dt>
<dd>전용 호스트의 데이터 센터별 필터링.</dd>
<dt>--owner</dt>
<dd>전용 호스트의 소유자별 필터링.</dd>
<dt>--order</dt>
<dd>해당 전용 호스트를 구매한 주문 ID별 필터링.</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

계정의 가상 서버 인스턴스를 나열합니다.
```
ibmcloud sl vs list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU 코어 수별 필터링.</dd>
<dt>-D, --domain</dt>
<dd>FQDN의 도메인 부분별 필터링.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
<dt>-H, --hostname</dt>
<dd>FQDN의 호스트 부분별 필터링.</dd>
<dt>-m, --memory</dt>
<dd>메모리별 필터링(MB).</dd>
<dt>-n, --network</dt>
<dd>네트워크 포트 속도별 필터링(Mbps).</dd>
<dt>-P, --public-ip</dt>
<dd>공인 IP 주소별 필터링.</dd>
<dt>-p, --private-ip</dt>
<dd>사설 IP 주소별 필터링.</dd>
<dt>--hourly</dt>
<dd>시간별 인스턴스만 표시.</dd>
<dt>--monthly</dt>
<dd>월별 인스턴스만 표시.</dd>
<dt>-g, --tag</dt>
<dd>태그별 필터링(다중 발생 허용).</dd>
<dt>-o, --order</dt>
<dd>해당 인스턴스를 구매한 주문 ID별 필터링.</dd>
<dt>--owner</dt>
<dd>인스턴스를 소유한 사용자 ID별 필터링.</dd>
<dt>--sortby</dt>
<dd>정렬 기준 열, 기본값: hostname, options are:id,hostname,domain,datacenter,cpu,memory,public_ip,private_ip.</dd>
<dt>--columns</dt>
<dd>표시할 열, 기본값: id,hostname,public_ip,private_ip,datacenter,action, options are: guid,power_state,created_by,tags.</dd>
</dl>

**예제**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
이 명령은 현재 계정의 시간별 청구되는 모든 가상 서버 인스턴스를 나열합니다. 도메인 기준 필터링은 "ibm.com"과 동일하고 메모리별로 정렬합니다.

## ibmcloud sl vs pause
{: #sl_vs_pause}

활성 가상 서버 인스턴스를 일시정지합니다.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs pause 12345678 -f
```
이 명령은 확인 요청 없이 ID가 `12345678`인 가상 서버 인스턴스를 일시정지합니다.

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

활성 가상 서버 인스턴스의 전원을 끕니다.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--hard</dt>
<dd>하드 시스템 종료 수행.</dd>
<dt>--soft</dt>
<dd>소프트 시스템 종료 수행.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs power-off 12345678 --soft
```
이 명령은 ID가 `12345678`인 가상 서버 인스턴스에 대해 소프트 전원 끄기를 수행합니다.

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

가상 서버 인스턴스의 전원을 켭니다.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs power-on 12345678
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스에 대해 전원 공급을 수행합니다.

## ibmcloud sl vs ready
{: #sl_vs_ready}

가상 서버 인스턴스가 사용 준비가 되었는지 확인합니다.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--wait</dt>
<dd>리턴하기 전에 가상 서버가 프로비저닝을 완료할 때까지 최대 X초 동안 대기.</dd>
</dl>

**예제**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
이 명령은 계속 사용할 준비가 되었는지 확인하기 위해 ID가 `12345678`인 가상 서버 인스턴스 상태를 확인하고 최대 30초 동안 대기합니다.

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

활성 가상 서버 인스턴스를 다시 부팅합니다.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--hard</dt>
<dd>하드 재부팅 수행.</dd>
<dt>--soft</dt>
<dd>소프트 재부팅 수행.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs reboot 12345678 --hard
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스에 대해 하드 재부팅을 수행합니다.

## ibmcloud sl vs reload
{: #sl_vs_reload}

가상 서버 인스턴스의 운영 체제를 다시 로드합니다.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>다운로드할 사후 설치 스크립트.</dd>
<dt>--image</dt>
<dd>이미지 ID. 기본값은 현재 운영 체제를 사용하는 것입니다.</dd>
<dt>참조:</dt>
<dd>'ibmcloud sl image list'를 참조하십시오.</dd>
<dt>-k, --key</dt>
<dd>루트 사용자에게 추가할 SSH 키 ID(다중 발생 허용).</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs reload 12345678
```
이 명령은 ID가 `12345678`인 가상 서버 인스턴스에 대해 현재 운영 체제를 다시 로드합니다.

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

복구 이미지로 가상 서버 인스턴스를 다시 부팅합니다.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs rescue 12345678
```
이 명령은 ID가 `12345678`인 가상 서버 인스턴스를 복구 이미지로 다시 부팅합니다.

## ibmcloud sl vs resume
{: #sl_vs_resume}

일시정지된 가상 서버 인스턴스를 재개합니다.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs resume 12345678
```
이 명령은 ID가 `12345678`인 가상 서버 인스턴스를 재개합니다.

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

가상 서버 인스턴스를 업그레이드합니다.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU 코어 수.</dd>
<dt>--private</dt>
<dd>CPU 코어는 전용 호스트 서버에 위치합니다.</dd>
<dt>-m, --memory</dt>
<dd>메모리(MB).</dd>
<dt>--network</dt>
<dd>네트워크 포트 속도(Mbps).</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
{: codeblock}

이 명령은 ID가 `12345678`인 가상 서버 인스턴스를 업그레이드하고 CPU 코어 수를 8로, 메모리를 8192M로, 네트워크 포트 속도를 1000Mbps로 설정합니다.

