---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 하드웨어

{{site.data.keyword.baremetal_long}}는 하드웨어 리소스에 대한 하위 레벨 액세스로 성능과 제어를 제공하는 단일 테넌트 실제 서버입니다. 베어메탈 서버는 그 자체로 강도 높은 워크로드가 요구되는 프로세서 및 디스크 I/O에 부합하는 뛰어난 성능을 제공합니다. 이러한 서버는 표준 기능 및 서비스가 포함된 가장 완벽한 패키지로 제공됩니다. 

다음 명령을 사용하여 {{site.data.keyword.Bluemix}} 인프라 베어메탈 하드웨어 서버를 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 인프라 베어메탈 서버 명령">
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

하드웨어 서버를 취소합니다.
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-i, --immediate</dt>
<dd>즉시 서버 취소(청구 주기 대신).</dd>
<dt>-r, --reason</dt>
<dd>선택적 취소 이유. 사용 가능한 옵션의 목록은 'ibmcloud sl hardware cancel-reasons'를 참조하십시오.</dd>
<dt>-c, --comment</dt>
<dd>취소 티켓에 추가할 선택적 주석.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

취소 이유의 목록을 표시합니다.
```
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

하드웨어 서버를 주문/작성합니다.
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN의 호스트 부분(필수).</dd>
<dt>-D, --domain</dt>
<dd>FQDN의 도메인 부분(필수).</dd>
<dt>-s, --size</dt>
<dd>하드웨어 크기(필수).</dd>
<dt>-o, --os</dt>
<dd>OS 설치 코드(필수).</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터의 짧은 이름(필수).</dd>
<dt>-p, --port-speed</dt>
<dd>포트 속도(필수).</dd>
<dt>-b, --billing</dt>
<dd>청구 비율(월별 또는 시간별, 지정되지 않은 경우 기본값은 시간별임).</dd>
<dt>-i, --post-install</dt>
<dd>다운로드할 사후 설치 스크립트.</dd>
<dt>-k, --key</dt>
<dd>루트 사용자에게 추가할 SSH 키(다중 발생 허용).</dd>
<dt>-n, --no-public</dt>
<dd>사설 네트워크만 표시.</dd>
<dt>-e, --extra</dt>
<dd>추가 옵션(다중 발생 허용).</dd>
<dt>-t, --test</dt>
<dd>가상 서버를 실제로 작성하지 않음.</dd>
<dt>-m, --template</dt>
<dd>명령행 옵션을 기본값으로 설정하는 템플리트 파일.</dd>
<dt>-x, --export</dt>
<dd>템플리트 파일로 옵션 내보내기.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

제공된 섀시에 대한 서버 주문 옵션입니다.
```
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

하드웨어 서버 인증 정보를 나열합니다.
```
ibmcloud sl hardware credentials IDENTIFIER
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

하드웨어 서버에 대한 세부사항을 가져옵니다.
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-p, --passwords</dt>
<dd>비밀번호를 표시합니다(유출되지 않도록 주의).</dd>
<dt>-c, --price</dt>
<dd>연관된 가격을 표시합니다.</dd>
</dl>

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

하드웨어 서버 세부사항을 편집합니다.
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN의 호스트 부분.</dd>
<dt>-D, --domain</dt>
<dd>FQDN의 도메인 부분.</dd>
<dt>-g, --tag</dt>
<dd>설정할 태그 또는 모두 제거하려면 빈 문자열 지정.</dd>
<dt>-F, --userfile</dt>
<dd>파일에서 사용자 데이터 읽기.</dd>
<dt>-u, --userdata</dt>
<dd>사용자 정의 메타데이터 문자열.</dd>
<dt>-p, --public-speed</dt>
<dd>공용 포트 속도. 옵션: 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>개인용 포트 속도. 옵션: 0,10,100,1000,10000.</dd>
</dl>

## ibmcloud sl hardware list
{: #sl_hardware_list}

하드웨어 서버를 나열합니다.
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU 코어 수별 필터링.</dd>
<dt>-D, --domain</dt>
<dd>도메인별 필터링.</dd>
<dt>-H, --hostname</dt>
<dd>호스트 이름별 필터링.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터별 필터링.</dd>
<dt>-m, --memory</dt>
<dd>메모리별 필터링(GB).</dd>
<dt>-n, --network</dt>
<dd>네트워크 포트 속도별 필터링(Mbps).</dd>
<dt>-g, --tag</dt>
<dd>태그별 필터링(다중 발생 허용).</dd>
<dt>-p, --public-ip</dt>
<dd>공인 IP 주소별 필터링.</dd>
<dt>-v, --private-ip</dt>
<dd>사설 IP 주소별 필터링.</dd>
<dt>-o, --order</dt>
<dd>하드웨어 서버를 구매한 주문 ID별 필터링.</dd>
<dt>--owner</dt>
<dd>소유자 ID별 필터링.</dd>
<dt>--sortby</dt>
<dd>정렬 기준 열, default:hostname, option:id,guid,hostname,domain,public_ip,private_ip,datacenter,status,ipmi_ip,created,created_by.</dd>
<dt>--columns</dt>
<dd>표시할 열, default:id,hostname,domain,public_ip,private_ip,datacenter,status, options:guid,cpu,memory,os,ipmi_ip,created,created_by,tags.</dd>
</dl>

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

서버의 전원을 껐다가 켭니다.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

활성 서버의 전원을 끕니다.
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

서버의 전원을 켭니다.
```
ibmcloud sl hardware power-on IDENTIFIER
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

활성 서버를 다시 부팅합니다.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
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

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

서버의 운영 체제를 다시 로드합니다.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>다운로드할 사후 설치 스크립트, HTTPS만 실행됨, HTTP는 파일을 /root에 배치함.</dd>
<dt>-k, --key</dt>
<dd>루트 사용자에게 추가할 SSH 키의 ID(다중 발생 허용).</dd>
<dt>-b, --upgrade-bios</dt>
<dd>BIOS 업그레이드.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>모든 하드 드라이브의 펌웨어 업그레이드.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

복구 이미지로 서버를 다시 부팅합니다.
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

서버 펌웨어를 업데이트합니다.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>
