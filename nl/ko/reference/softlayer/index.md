---

copyright:

  years: 2016,2017

lastupdated: "2017-06-27"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl) 명령
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} 플러그인은 {{site.data.keyword.Bluemix_notm}} CLI에 병합되었습니다. 더 이상 플러그인을 설치할 필요가 없습니다.

{{site.data.keyword.Bluemix_notm}} 명령행 인터페이스(CLI)에서 {{site.data.keyword.BluSoftlayer_notm}} 명령을 사용하여 SoftLayer 서비스를 구성하고 관리하십시오.


시작하려면 IBM {{site.data.keyword.Bluemix_notm}} CLI를 설치하십시오. 세부사항은
[Bluemix CLI ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}를 참조하십시오.

{{site.data.keyword.Bluemix_notm}} 명령의 전체 목록은 [{{site.data.keyword.Bluemix_notm}} (bx) 명령](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)을 참조하십시오.


## 일반 {{site.data.keyword.BluSoftlayer_notm}} 명령

다음 명령이 지원됩니다. 사용 가능한 명령의 목록을 보려면 `bluemix sl` 명령을 사용하십시오.

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 명령">
<caption>표 1. 일반 Softlayer 명령</caption>
 <thead>
 <th colspan="6">일반 Softlayer 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## {{site.data.keyword.BluSoftlayer_notm}} 블록 스토리지 명령

 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 2. Softlayer 블록 스토리지</caption>
 <thead>
 <th colspan="6">Softlayer 블록 스토리지</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[bluemix sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[bluemix sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[bluemix sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[bluemix sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[bluemix sl block replica-order](/docs/cli/reference/softlayer/index.html#sl_block_replica_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_cancel)</td>
 <td>[bluemix sl block snapshot-create](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_create)</td>
 <td>[bluemix sl block snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_disable)</td>
 <td>[bluemix sl block snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_enable)</td>
 <td>[bluemix sl block snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_delete)</td>
 <td>[bluemix sl block snapshot-list](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_list)</td>
  </tr>
 <tr>
 <td>[bluemix sl block snapshot-order](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_order)</td>
  <td>[bluemix sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[bluemix sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[bluemix sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
  <td>[bluemix sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
  <td>[bluemix sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} dns 명령

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 3. Softlayer dns 명령</caption>
 <thead>
 <th colspan="6">Softlayer dns 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[bluemix sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
 <td>[bluemix sl dns record-edit](/docs/cli/reference/softlayer/index.html#sl_dns_record_edit)</td>
 <td>[bluemix sl dns record-list](/docs/cli/reference/softlayer/index.html#sl_dns_record_list)</td>
 <td>[bluemix sl dns record-remove](/docs/cli/reference/softlayer/index.html#sl_dns_record_remove)</td>
  <td>[bluemix sl dns zone-create](/docs/cli/reference/softlayer/index.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[bluemix sl dns zone-delete](/docs/cli/reference/softlayer/index.html#sl_dns_zone_delete)</td>
   <td>[bluemix sl dns zone-list](/docs/cli/reference/softlayer/index.html#sl_dns_zone_list)</td>
   <td>[bluemix sl dns zone-print](/docs/cli/reference/softlayer/index.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 4. Softlayer 글로벌 IP 주소</caption>
 <thead>
 <th colspan="6">SoftLayer 글로벌 IP 주소</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[bluemix sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[bluemix sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[bluemix sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[bluemix sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 이미지 명령

 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 5. Softlayer 이미지 명령</caption>
 <thead>
 <th colspan="6">Softlayer 이미지 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl image delete](/docs/cli/reference/softlayer/index.html#sl_image_delete)</td>
 <td>[bluemix sl image detail](/docs/cli/reference/softlayer/index.html#sl_image_detail)</td>
 <td>[bluemix sl image edit](/docs/cli/reference/softlayer/index.html#sl_image_edit)</td>
 <td>[bluemix sl image list](/docs/cli/reference/softlayer/index.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} Legacy ISCSI 스토리지 명령

  <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 6. Softlayer Legacy ISCSI 스토리지 명령</caption>
 <thead>
 <th colspan="6">Softlayer Legacy ISCSI 스토리지 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl iscsi cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_cancel)</td>
 <td>[bluemix sl iscsi create](/docs/cli/reference/softlayer/index.html#sl_iscsi_create)</td>
 <td>[bluemix sl iscsi detail](/docs/cli/reference/softlayer/index.html#sl_iscsi_detail)</td>
 <td>[bluemix sl iscsi list](/docs/cli/reference/softlayer/index.html#sl_iscsi_list)</td>
 <td>[bluemix sl iscsi snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_cancel)</td>
 <td>[bluemix sl iscsi snapshot-create](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create)</td>
 </tr>
 <tr>
 <td>[bluemix sl iscsi snapshot-create-space](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create-space)</td>
 <td>[bluemix sl iscsi snapshot-list](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_list)</td>
 <td>[bluemix sl iscsi snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_restore)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 보안 명령

 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 7. Softlayer 보안 명령</caption>
 <thead>
 <th colspan="5">Softlayer 보안 명령</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl security sshkey-add](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_add)</td>
  <td>[bluemix sl security sshkey-edit](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_edit)</td>
  <td>[bluemix sl security sshkey-list](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_list)</td>
  <td>[bluemix sl security sshkey-print](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_print)</td>   
  <td>[bluemix sl security sshkey-remove](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[bluemix sl security cert-add](/docs/cli/reference/softlayer/index.html#sl_security_cert_add)</td>
  <td>[bluemix sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[bluemix sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[bluemix sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[bluemix sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 서브넷 명령
 
 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 8. Softlayer 서브넷 명령</caption>
 <thead>
 <th colspan="5">Softlayer 서브넷 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl subnet cancel](/docs/cli/reference/softlayer/index.html#sl_subnet_cancel)</td>
 <td>[bluemix sl subnet create](/docs/cli/reference/softlayer/index.html#sl_subnet_create)</td>
 <td>[bluemix sl subnet detail](/docs/cli/reference/softlayer/index.html#sl_subnet_detail)</td>
 <td>[bluemix sl subnet list](/docs/cli/reference/softlayer/index.html#sl_subnet_list)</td>
 <td>[bluemix sl subnet lookup](/docs/cli/reference/softlayer/index.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} 가상 서버 명령

 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 9. Softlayer 가상 서버 명령</caption>
 <thead>
 <th colspan="6">Softlayer 가상 서버 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[bluemix sl vs capture](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
 <td>[bluemix sl vs create](/docs/cli/reference/softlayer/index.html#sl_vs_create)</td>
 <td>[bluemix sl vs options](/docs/cli/reference/softlayer/index.html#sl_vs_options)</td>
 <td>[bluemix sl vs credentials](/docs/cli/reference/softlayer/index.html#sl_vs_credentials)</td>
 <td>[bluemix sl vs detail](/docs/cli/reference/softlayer/index.html#sl_vs_detail)</td>
 </tr><tr>
 <td>[bluemix sl vs dns-sync](/docs/cli/reference/softlayer/index.html#sl_vs_dns_sync)</td>
 <td>[bluemix sl vs edit](/docs/cli/reference/softlayer/index.html#sl_vs_edit)</td>
 <td>[bluemix sl vs list](/docs/cli/reference/softlayer/index.html#sl_vs_list)</td>
 <td>[bluemix sl vs pause](/docs/cli/reference/softlayer/index.html#sl_vs_pause)</td>
 <td>[bluemix sl vs power-off](/docs/cli/reference/softlayer/index.html#sl_vs_power_off)</td>
 <td>[bluemix sl vs power-on](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
 </tr><tr>
 <td>[bluemix sl vs ready](/docs/cli/reference/softlayer/index.html#sl_vs_ready)</td>
 <td>[bluemix sl vs reboot](/docs/cli/reference/softlayer/index.html#sl_vs_reboot)</td>
 <td>[bluemix sl vs reload](/docs/cli/reference/softlayer/index.html#sl_vs_reload)</td>
 <td>[bluemix sl vs rescure](/docs/cli/reference/softlayer/index.html#sl_vs_rescure)</td>
 <td>[bluemix sl vs resume](/docs/cli/reference/softlayer/index.html#sl_vs_resume)</td>
 <td>[bluemix sl vs upgrade](/docs/cli/reference/softlayer/index.html#sl_vs_upgrade)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} VLAN 명령

  <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 Softlayer 명령">
<caption>표 10. Softlayer VLAN 명령</caption>
 <thead>
 <th colspan="6">Softlayer VLAN 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[bluemix sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[bluemix sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[bluemix sl vlan edit](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[bluemix sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[bluemix sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### 명령 사용
명령에 대한 도움말 정보를 보려면 `bluemix sl [command] -h`를 실행하십시오.

### bluemix sl init
{: #sl_init}

Softlayer 환경에 연결하는 데 사용되는 구성 설정을 초기화하십시오. 구성에는 사용자 이름, API 키 또는 비밀번호, 계정 및 엔드포인트가 포함됩니다.
```
bluemix sl init [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>Softlayer API 엔드포인트 URL, 기본값: https://api.softlayer.com/rest/v3.1</dd>
   <dt>-u,--sl-user</dt>
   <dd>Softlayer 사용자 이름</dd>
   <dt>-p,--sl-password</dt>
   <dd>Softlayer 비밀번호 또는 API 키</dd>
   <dt>-c,--account-id</dt>
   <dd>Softlayer 계정 ID</dd>
   </dl>

예를 들면, Softlayer 사용자 이름 및 비밀번호/API 키로 로그인
```
$ bluemix sl config
Choose how to configure Softlayer authentication: 
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> wangjunl@cn.ibm.com
API key or password: []> abcd

Softlayer API endpoint:    https://api.softlayer.com/rest/v3.1   
Account ID:                278444   
User ID:                   wangjunl@cn.ibm.com   
API Key:                   xxxxxxxxxx
```
예를 들면, Bluemix Single-Sign-On을 사용하여 Softlayer 로그인
```
$ bx login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account Wilma's Account (65ce8074c6c62b5)

Targeted org wangjunl@cn.ibm.com

Targeted space Wilma
                  
API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           wangjunl@cn.ibm.com   
Account:        Wilma's Account (65ce8074c6c62b5)   
Org:            wangjunl@cn.ibm.com   
Space:          Wilma 

$ bx sl init
Choose how to configure Softlayer authentication: 
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number> 2
Softlayer API endpoint URL: [https://api.softlayer.com/mobile/v3.1]> 
Setting account to: 278444
OK
                              
Softlayer API endpoint:    https://api.softlayer.com/mobile/v3.1   
Account ID:                278444   
User ID:                   12345678   
IMS token:                 xxxxxxxxxx
```

### bluemix sl help
{: #sl_help}

Softlayer 환경을 조작하기 위한 모든 명령에 대한 도움말 정보를 보십시오.
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

지정된 볼륨에 액세스하도록 호스트에 권한을 부여하십시오.
```
bluemix sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>권한을 부여할 하나의 하드웨어 서버 ID입니다.</dd>
   <dt>--virtual-id</dt>
   <dd>권한을 부여할 하나의 가상 서버 ID입니다.</dd>
   <dt>--ip-address-id</dt>
   <dd>권한을 부여할 하나의 IP 주소 ID입니다.</dd>
   <dt>--ip-address</dt>
   <dd>권한 부여할 IP 주소입니다.</dd>
    </dl>

**예제**:
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
이 명령은 ID `87654321`인 가상 서버가 ID `12345678`인 볼륨에 액세스하도록 권한을 부여합니다.

### bluemix sl block access-list
{: #sl_block_access_list}

ACL을 나열하십시오.
```
bluemix sl block access-list VOLUME_ID [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: `id`, `name`,  `type`, `private_ip_address`, `host_iqn`, `username` 또는 `password`.</dd>
   <dt>--columns</dt>
   <dd>  표시할 열, 옵션:  `id`, `name`, `type`, `private_ip_address`, `host_iqn`, `username` 또는 `password`.</dd>
</dl>

**예제**:
```
bluemix sl block access-list 12345678 --sortby id
```
이 명령은 ID `12345678`인 볼륨에 액세스하도록 권한이 부여된 모든 호스트를 나열하고 ID별로 정렬합니다.

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

지정된 볼륨에 액세스하는 호스트의 권한을 취소하십시오.
```
 bluemix sl block access-revoke VOLUME_ID [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--hardware-id</dt>
   <dd>권한 부여할 하나의 하드웨어 서버의 ID입니다.</dd>
   <dt>--virtual-id</dt>
   <dd>권한 부여할 하나의 가상 서버의 ID입니다.</dd>
   <dt>--ip-address-id</dt>
   <dd>권한 부여할 하나의 IP 주소의 ID입니다.</dd>
   <dt>--ip-address</dt>
   <dd>권한 부여할 IP 주소입니다.</dd>
    </dl>

**예제**:
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
이 명령은 ID `87654321`인 가상 서버의 ID `12345678`인 볼륨에 대한 액세스 권한을 취소합니다.

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

복제본에서 블록 볼륨 장애 복구.
```
 bluemix sl block replica-failback VOLUME_ID
```
**예제**:
```
 bluemix sl block replica-failback 12345678
```
이 명령은 ID `12345678`인 볼륨에 대해 장애 복구 조작을 수행합니다.

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

지정된 복제본 볼륨으로 블록 볼륨 장애 복구.
```
bluemix sl block replica-failover VOLUME_ID REPLICA_ID
```

**예제**:
```
 bluemix sl block replica-failover 12345678 87654321
```
이 명령은 ID `87654321`인 복제본 볼륨에 ID `12345678`인 볼륨에 대한 장애 복구 조작을 수행합니다.

### bluemix sl block replica-order
{: #sl_block_replica_order}

블록 스토리지 복제본 볼륨 주문.
```
 bluemix sl block replica-order VOLUME_ID [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>필수. 복제에 사용하기 위한 스냅샷 스케줄입니다. 옵션: `HOURLY`,`DAILY` 또는 `WEEKLY`.</dd>
   <dt>-d, --datacenter</dt>
   <dd>필수. 복제본에 대한 데이터 센터의 짧은 이름입니다. 예: `dal09`.</dd>
   <dt>--tier</dt>
   <dd>선택사항. 복제본이 주문되는 기본 볼륨의 Endurance 스토리지 계층(GB당 IOPS)입니다. 옵션: `0.25`, `2`, `4` 또는 `10`.</dd>
   <dt>--os-type</dt>
   <dd>선택사항. 복제본이 주문되는 기본 볼륨의 운영 체제 계층입니다. 옵션: `HYPER_V`, `LINUX`, `VMWARE`, `WINDOWS_2008`, `WINDOWS_GPT`, `WINDOWS` 또는 `XEN`.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>

**예제**:
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
이 명령은 ID `12345678`인 볼륨에 대한 복제본(일별 복제를 수행하며, 계층 레벨 `4` 및 OS 유형 `Linux`인 dal09에 위치함)을 주문합니다.

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

지정된 볼륨에 대한 기존 스냅샷 영역 취소.
```
 bluemix sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>취소에 대한 선택적 이유입니다.</dd>
   <dt>--immediate</dt>
   <dd>청구 주기 대신 즉시 스냅샷 영역 취소.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
	</dl>

**예제**:
```
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
이 명령은 확인을 요청하지 않고 즉시 ID 12345678인 스냅샷을 취소합니다.

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

지정된 볼륨에 스냅샷 작성.
```
 bluemix sl block snapshot-create VOLUME_ID [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt> -n, --note</dt>
   <dd>새 스냅샷에 설정할 참고</dd>
	</dl>

**예제**:
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
이 명령은 `snapshotforbluemix`와 같은 추가 참고와 함께 ID `12345678`인 볼륨에 대한 스냅샷을 작성합니다.

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

지정된 볼륨에 대한 특정 스케줄에 따라 스냅샷 사용 안함.
```
 bluemix sl block snapshot-disable VOLUME_ID [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>필수. 스냅샷 스케줄: `HOURLY`, `DAILY`, or `WEEKLY`.</dd>
	</dl>

**예제**:
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
이 명령은 ID `12345678`인 볼륨에 대한 일별 스냅샷을 사용 안함으로 설정합니다.

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

특정 스케줄에 따른 지정된 볼륨에 대한 스냅샷 사용.
```
 bluemix sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>필수. 스냅샷 스케줄: `HOURLY`, `DAILY`, or `WEEKLY`.</dd>
   <dt>-c, --retention-count</dt>
   <dd>필수. 유지할 스냅샷 수입니다.</dd>
   <dt>-m, --minute</dt>
   <dd>스냅샷을 작성해야 하는 시간(분), 0 - 59 사이의 정수. </dd>
   <dt>--hour</dt>
   <dd>스냅샷을 작성해야 하는 시간, 0 - 23 사이의 정수. </dd>
   <dt>-d, --day-of-week</dt>
   <dd>스냅샷을 작성해야 하는 요일, 0 - 6 사이의 정수.
0은 일요일, 1은 월요일, 2는 화요일, 3은 수요일, 4는 목요일, 5는 금요일, 6은 토요일을 의미합니다. </dd>
	</dl>

**예제**:
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
이 명령은 ID `12345678`인 볼륨에 대한 스냅샷을 사용으로 설정합니다. 스냅샷은 매주 일요일 2시에 작성되며 최대 5개의 스냅샷이 유지됩니다.

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

지정된 볼륨에서 스냅샷 삭제.
```
  bluemix sl block snapshot-delete SNAPSHOT_ID
```

**예제**:
```
 bluemix sl block snapshot-delete 12345678
```
이 명령은 ID `12345678`인 스냅샷을 삭제합니다.

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

블록 스토리지 스냅샷 나열
```
 bluemix sl block snapshot-list VOLUME_ID [OPTIONS]

```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>정렬 기준 열. 옵션: `id`, `name`, `created` 및 `size_bytes`.</dd>
	</dl>

**예제**:
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
이 명령은 ID `12345678`인 볼륨의 모든 스냅샷을 나열하고 ID별로 정렬합니다.

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

블록 스토리지 볼륨에 대한 스냅샷 영역 주문.
```
 bluemix sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-s, --size</dt>
   <dd>필수. 작성할 스냅샷 영역의 크기(GB)입니다.</dd>
   <dt>-t, --tier</dt>
   <dd>선택사항. 영역이 주문되는 블록 볼륨의 Endurance 스토리지 계층(GB당 IOPS)입니다. 옵션: 0.25,2,4,10</dd>
   <dt>-u, --upgrade</dt>
   <dd>업그레이드 주문임을 표시하는 플래그입니다.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
	</dl>

**예제**:
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
이 명령은 ID `12345678`인 볼륨에 대한 스냅샷 영역을 주문합니다. 크기는 1,000GB이고, 계층 레벨은 GB당 4IOPS입니다.


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

지정된 스냅샷을 사용하여 블록 볼륨 복원
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**예제**:
```
 bluemix sl block snapshot-restore 12345678 87654321
```
이 명령은 ID `87654321`인 스냅샷에서 ID `12345678`인 볼륨을 복원합니다.

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

기존 블록 스토리지 볼륨 취소
```
 bluemix sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>취소에 대한 선택적 이유입니다.</dd>
   <dt>--immediate</dt>
   <dd>청구 주기 대신 즉시 스냅샷 영역 취소.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
	</dl>

**예제**:
```
 bluemix sl block volume-cancel 12345678 --immediate -f
```
이 명령은 확인을 요청하지 않고 즉시 ID `12345678`인 볼륨을 취소합니다.

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

지정된 볼륨에 대한 세부사항 표시
```
 bluemix sl block volume-detail VOLUME_ID
```

**예제**:
```
 bluemix sl block volume-detail 12345678
```
이 명령은 ID `12345678`인 볼륨의 세부사항을 표시합니다.

### bluemix sl block volume-list
{: #sl_block_volume_list}

블록 스토리지 나열.
```
 bluemix sl block volume-list [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-u, --username</dt>
   <dd>볼륨 사용자 이름별 필터링.</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름별 필터링.</dd>
   <dt>-t, --storage-type</dt>
   <dd>스토리지 볼륨의 유형별 필터링. 옵션: `performance` 및 `endurance`.</dd>
   <dt>--order</dt>
   <dd>블록 스토리지를 구매한 주문 ID별 필터링.</dd>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
   <dt>--columns</dt>
   <dd>표시할 열, 옵션: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
   </dl>

**예제**:
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
이 명령은 dal09에 위치하는 현재 계정의 모든 endurance 볼륨을 나열하고 용량별로 정렬합니다.


### bluemix sl block volume-order
{: #sl_block_volume_order}

블록 스토리지 볼륨 주문
```
   bluemix sl block volume-order [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--storage-type</dt>
   <dd>스토리지 볼륨의 유형 [필수], 옵션: performance,endurance</dd>
   <dt>--size</dt>
   <dd>스토리지 볼륨의 크기(GB) [필수]</dd>
   <dt>--iops</dt>
   <dd>Performance 스토리지 IOP, 100의 배수이며 100 - 6000 사이 [storage-type performance에 필수]</dd>
   <dt>--tier</dt>
   <dd>Endurance 스토리지 계층(GB당 IOP) [storage-type endurance에 필수], 옵션: 0.25,2,4,10</dd>
   <dt>--os-type</dt>
   <dd>운영 체제 [필수], 옵션: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름 [필수]</dd>
   <dt>--snapshot-size</dt>
   <dd>Endurance 블록 스토리지와 함께 스냅샷 영역을 주문하기 위한 선택적 매개변수이며, 주문할 스냅샷 영역의 크기(GB)를 지정합니다. </dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>


**예제**:

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
이 명령은 크기가 1000GB, IOPS가 4000, OS 유형은 LINUX이고, dal09에 위치하는 performance 볼륨을 주문합니다.

```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
이 명령은 크기가 500GB, 계층 레벨이 GB당 4 IOPS, OS 유형은 XEN이고, dal09에 위치하며 추가 스냅샷 영역 크기가 500GB인 endurance 볼륨을 주문합니다.


### bluemix sl block volume-options
{: #sl_block_volume_options}

블록 스토리지 주문에 대한 모든 옵션 나열
```
 bluemix sl block volume-options
```

**예제**:
```
 bluemix sl block volume-options
```
이 명령은 스토리지 유형, 볼륨 크기, OS 유형, IOPS, 계층 레벨, 데이터 센터 및 스냅샷 크기를 포함하여 블록 스토리지 볼륨 작성에 대한 모든 옵션을 나열합니다.


### bluemix sl dns import
{: #sl_dns_import}

BIND 구역 파일과 다른 구역을 가져옵니다.
```
bluemix sl dns-import [OPTIONS] ZONEFILE
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--dry-run</dt>
   <dd>레코드를 실제로 작성하지 마십시오.</dd>
    </dl>

**예제**:
```
 bluemix sl dns import ~/blumix.net.txt
```
이 명령은 `~/blumix.net.txt` 파일에서 구역 및 해당 리소스 레코드를 가져옵니다.

### bluemix sl dns record-add
{: #sl_dns_record_add}
리소스 레코드 추가.

```
bluemix sl dns-record-add [OPTIONS] ZONE RECORD TYPE DATA
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--ttl</dt>
   <dd>TTL 값(초), 예: 86400 [기본값: 7200].</dd>
    </dl>

**예제**:
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
이 명령은 A 레코드를 bluemix.net 구역에 추가합니다. 그 호스트는 `ftp`이고, 데이터는 `127.0.0.1`이며 ttl은 86400초입니다.

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

구역의 리소스 레코드 업데이트
```
   bluemix sl dns record-edit ZONE [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--by-record</dt>
   <dd>호스트 레코드로 편집(예: www).</dd>
   <dt>--by-id</dt>
   <dd>해당 ID별로 단일 레코드 편집.</dd>
   <dt>--data</dt>
   <dd>레코드 데이터(예: IP 주소).</dd>
   <dt>--ttl</dt>
   <dd>TTL 값(초)(예: 86400).</dd>
   </dl>

**예제**:
```
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
이 명령은 `12345678`인 `bluemix.net` 구역 아래의 레코드를 편집하고, 해당 데이터는 `127.0.0.2`로 설정하고 ttl은 3600으로 설정합니다.

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
이 명령은 호스트 이름이 `kibana`인 `bluemix.net` 구역 아래의 레코드를 편집하고, 해당 ttl을 모두 3600으로 설정합니다.


### bluemix sl dns record-list
{: #sl_dns_record_list}

구역의 모든 리소스 레코드 나열

```
   bluemix sl dns record-list ZONE [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--data</dt>
   <dd>레코드 데이터별 필터링(예: IP 주소).</dd>
   <dt>--record</dt>
   <dd>호스트 레코드로 필터링(예: www).</dd>
   <dt>--ttl</dt>
   <dd>TTL 값별 필터링(초)(예: 86400).</dd>
   <dt>--type</dt>
   <dd>레코드 유형별 필터링(예: A 또는 CNAME)</dd>
   </dl>

**예제**:
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
이 명령은 `bluemix.net` 구역 아래의 모든 A 레코드를 나열합니다. 호스트 기준 필터링은 `elasticsearch`이고 ttl은 900초입니다.


### bluemix sl dns record-remove
{: #sl_dns_record_remove}

구역에서 리소스 레코드 제거
```
 bluemix sl dns record-remove RECORD_ID
```

**예제**:
```   
 bluemix sl dns record-remove 12345678
```
이 명령은 ID `12345678`인 리소스 레코드를 제거합니다.

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

영역 작성.
```
 bluemix sl dns zone-create ZONE
```
**예제**:
```
 bluemix sl dns zone-create bluemix.net
```
이 명령은 이름이 `bluemix.net`인 구역을 작성합니다.

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

영역 삭제.
```
 bluemix sl dns zone-delete ZONE
```
**예제**:
```
 bluemix sl dns zone-delete bluemix.net
```
이 명령은 이름이 `bluemix.net`인 구역을 삭제합니다.

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

계정의 모든 구역 나열
```
   bluemix sl dns zone-list
```
**예제**:
```
   bluemix sl dns zone-list
```
이 명령은 현재 계정 아래의 모든 구역을 나열합니다.

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

BIND 형식으로 구역 및 리소스 레코드 인쇄
```
 bluemix sl dns zone-print ZONE
```

**예제**:
```
 bluemix sl dns zone-print bluemix.net
```
이 명령은 BIND 형식으로 bluemix.net이라는 구역을 인쇄합니다.


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

대상 라우터 또는 디바이스에 글로벌 IP 지정.
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**예제**:
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
이 명령은 ID 12345678인 IP 주소를 IP 주소가 9.111.123.456인 대상 디바이스에 지정합니다.


### bluemix sl globalip-create
{: #sl_globalip_create}

글로벌 IP를 작성합니다.
```
bluemix sl globalip-create [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--v6</dt>
   <dd>IPv6 IP 주문.</dd>
   <dt>--test</dt>
   <dd>테스트 주문.</dd>
    <dt>-f, --force</dt>
   <dd>확인 없이 글로벌 IP 작성.</dd>
    </dl>

**예제**:
```
     bluemix sl globalip create --v6
```
이 명령은 IP V6 주소를 작성합니다.

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

글로벌 IP를 취소합니다.
```
bluemix sl globalip-cancel [OPTIONS] IDENTIFIER
```
<strong>명령 옵션</strong>:

   <dl>
    <dt>-f, --force</dt>
   <dd>확인 없이 글로벌 IP 작성.</dd>
    </dl>

**예제**:
```
 bluemix sl globalip cancel 12345678
```
이 명령은 ID `12345678`인 IP 주소를 취소합니다.

### bluemix sl globalip-list
{: #sl_globalip_list}

모든 글로벌 IP를 나열합니다. 
```
bluemix sl globalip-list [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--v4</dt>
   <dd>IPv4 IP만 표시.</dd>
   <dt>--v6</dt>
   <dd>IPv6 IP만 표시.</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

대상 라우터 또는 디바이스에서 글로벌 IP 지정 해제
```
 bluemix sl globalip unassign IDENTIFIER
```
**예제**:
```
 bluemix sl globalip unassign 12345678
```
이 명령은 대상 디바이스에서 ID `12345678`인 IP 주소의 지정을 해제합니다.

### bluemix sl image delete
{: #sl_dns_image_delete}

이미지 삭제.
```
   bluemix sl image delete IDENTIFIER
```
**예제**:
```
   bluemix sl image delete 12345678
```
이 명령은 ID `12345678`인 이미지를 삭제합니다.


### bluemix sl image detail
{: #sl_dns_image_detail}

이미지에 대한 세부사항 가져오기.
```
 bluemix sl image detail IDENTIFIER
```
**예제**:
```
 bluemix sl image detail 12345678
```
이 명령은 ID 12345678인 이미지의 세부사항을 가져옵니다.

### bluemix sl image edit
{: #sl_dns_image_edit}

이미지의 세부사항 편집
```
   bluemix sl image edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--name</dt>
   <dd>이미지의 이름입니다.</dd>
   <dt>--note</dt>
   <dd>이미지에 대한 추가 참고입니다.</dd>
   <dt>--tag</dt>
   <dd>이미지에 대한 태그입니다.</dd>
   </dl>


**예제**:
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
이 명령은 ID `12345678`인 이미지를 편집하고 그 이름을 `ubuntu16`, 참고는 `testing`, 태그는 `staging`으로 설정합니다.


### bluemix sl image edit
{: #sl_dns_image_edit}

이미지의 세부사항 편집
```
   bluemix sl image edit [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--name</dt>
   <dd>이미지의 이름입니다.</dd>
   <dt>--note</dt>
   <dd>이미지에 대한 추가 참고입니다.</dd>
   <dt>--tag</dt>
   <dd>이미지에 대한 태그입니다.</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

계정의 모든 이미지 나열
```
   bluemix sl image list [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--name</dt>
   <dd>이미지 이름 필터링.</dt>
   <dd>--public</dt>
   <dd>공용 이미지만 표시.</dd>
   <dt>--private</dt>
   <dd>개인용 이미지만 표시.</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

기존 iSCSI 볼륨 취소
```
   bluemix sl iscsi cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>취소에 대한 선택적 이유입니다.</dd>
   <dt>--immediate</dt>
   <dd>청구 주기 대신 즉시 iSCSI를 취소합니다.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

iSCSI 볼륨 작성
```
   bluemix sl iscsi create [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--size</dt>
   <dd>작성할 iSCSI 볼륨의 크기(GB) [필수]</dd>
   <dt>--datacenter</dt>
   <dd>데이터 센터 짧은 이름 [필수]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

iSCSI 볼륨에 대한 세부사항 가져오기
```
   bluemix sl iscsi detail IDENTIFIER [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--password</dt>
   <dd>iSCSI 대상에 액세스하기 위한 신임 정보 표시.</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

iSCSI 볼륨 나열
```
 bluemix sl iscsi list [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--order</dt>
   <dd>이 iscsi 스토리지를 구매한 주문의 ID입니다. </dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

iSCSI 스냅샷 취소/삭제
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPTIONS]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

iSCSI 볼륨의 스냅샷 작성
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--notes</dt>
   <dd>스냅샷에 대한 선택적 참고입니다.</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

지정된 iSCSI 볼륨에 대한 스냅샷 영역 주문
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--capacity</dt>
   <dd>작성할 스냅샷 영역의 크기입니다.</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

iSCSI 볼륨의 스냅샷 나열
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPTIONS]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

새 SSH 키 추가
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --in-file</dt>
   <dd>이 키를 위해 가져올 id_rsa.pub 파일</dd>
   <dt>-k, --key</dt>
   <dd>실제 SSH 키</dd>
   <dt>--note</dt>
   <dd>키와 연관시킬 추가 참고</dd>
   </dl>


**예제**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
이 명령은 ~/.ssh/id_rsa.pub 파일에서 "mykey" 참고가 지정된 SSH 키를 추가합니다.


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH 키 편집
```
 bluemix sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--label</dt>
   <dd>키에 대한 새 레이블</dd>
   <dt>--note</dt>
   <dd>키에 대한 새 참고</dd>
   </dl>


**예제**:
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
이 명령은 ID 12345678인 SSH 키를 업데이트하고 레이블을 "Bluemix"로 설정하고 참고를 "testing"으로 설정합니다.

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

계정의 SSH 키 나열
```
 bluemix sl security sshkey-list [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: `id`, `label`, `fingerprint`, `notes`.</dd>
   </dl>


**예제**:
```
 bluemix sl security sshkey-list --sortby label
```
이 명령은 현재 계정의 모든 SSH 키를 나열하고 레이블별로 정렬합니다.

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

화면에 SSH 키 인쇄
```
 bluemix sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --out-file</dt>
   <dd>공용 SSH 키가 이 파일에 작성됩니다. </dd>
   </dl>


**예제**:
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
이 명령은 ID, 레이블 및 ID 12345678인 SSH 키의 참고를 표시하고 공용 키를 ~/mykey.pub 파일에 작성합니다.

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

SSH 키 영구 제거
```
 bluemix sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>


**예제**:
```
 bluemix sl security sshkey-remove 12345678 -f
```
이 명령은 확인 요청 없이 ID 12345678인 SSH 키를 제거합니다.

### bluemix sl security cert-add
{: #sl_security_cert_add}

SSL 인증서 세부사항 추가 및 업로드
```
 bluemix sl security cert-add [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>인증서 파일</dd>
   <dt>--csr</dt>
   <dd>인증서 서명 요청 파일</dd>
   <dt>--icc</dt>
   <dd>중간 인증서 파일</dd>
   <dt>--key</dt>
   <dd>개인 키 파일</dd>
   <dt>--notes</dt>
   <dd>추가 참고</dd>
   </dl>


**예제**:
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
이 명령은 도메인 bluemix.net에 대한 인증서 파일 ~/bluemix.net.cert 및 개인 키 파일 ~/bluemix.net.key를 추가합니다.

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

SSL 인증서 편집
```
 bluemix sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>인증서 파일</dd>
   <dt>--csr</dt>
   <dd>인증서 서명 요청 파일</dd>
   <dt>--icc</dt>
   <dd>중간 인증서 파일</dd>
   <dt>--key</dt>
   <dd>개인 키 파일</dd>
   <dt>--notes</dt>
   <dd>추가 참고</dd>
   </dl>


**예제**:
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
이 명령은 ID 12345678인 인증서를 편집하고 해당 개인 키를 ~/bluemix.net.key 파일로 업데이트합니다.

### bluemix sl security cert-download
{: #sl_security_cert_download}

SSL 인증서 및 키 파일 다운로드
```
 bluemix sl security cert-download IDENTIFIER
```

**예제**:
```
 bluemix sl security cert-download 12345678
```
이 명령은 ID 12345678인 인증서에 대해 현재 디렉토리에 4개 파일을 다운로드합니다. 4개 파일은 인증서 파일, 인증서 서명 요청 파일, 중간 인증서 파일 및 개인 키 파일입니다.

### bluemix sl security cert-list
{: #sl_security_cert_list}

계정의 SSH 인증서 나열
```
 bluemix sl security cert-list [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--status</dt>
   <dd>이 상태의 인증서 표시, 기본값: all, 옵션: `all`, `valid`, `expired`</dd>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: `id`, `common_name`, `days_until_expire`, `notes`</dd>
   </dl>


**예제**:
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
이 명령은 현재 계정의 모든 유효한 인증서를 나열하고 유효성 검증일 기준으로 정렬합니다.

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

SSL 인증서 제거
```
 bluemix sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt> -f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>


**예제**:
```
 bluemix sl security cert-remove 12345678
```
이 명령은 ID 12345678인 인증서를 제거합니다.

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

서브넷 취소.
```
 bluemix sl subnet cancel [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>


**예제**:
```
 bluemix sl subnet cancel 12345678 -f
```
이 명령은 확인 요청 없이 ID 12345678인 서브넷을 취소합니다.

### bluemix sl subnet create
{: #sl_subnet_create}

계정에 새 서브넷 추가.
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

올바른 수량은 유형에 따라 달라집니다. 

 * 유형    - 올바른 수량(IPv4)
    ** 공용 - 4, 8, 16, 32
    **개인용 - 4, 8, 16, 32, 64
 * 유형    - 올바른 수량(IPv6)
    ** 공용 - 64

<strong>명령 옵션</strong>:
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>IPv6 주소 주문.</dd>
   <dt>--test</dt>
   <dd>서브넷을 주문하지 않음. 견적서만 가져오기.</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>

**예제**:
```
 bluemix sl subnet create public 16 567
```
이 명령은 16개의 IP v4 주소를 사용하여 공용 서브넷을 작성하고 ID 567인 VLAN에 배치합니다.



### bluemix sl subnet detail
{: #sl_subnet_detail}

서브넷의 세부사항 가져오기.
```
   bluemix sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>가상 서버 목록 숨기기.</dd>
   <dt>--no-hardware</dt>
   <dd>하드웨어 목록 숨기기.</dd>
   </dl>


**예제**:
```
 bluemix sl subnet detail 12345678
```
이 명령은 가상 서버 및 하드웨어 서버 정보를 포함하여 ID 12345678인 서브넷에 대한 자세한 정보를 표시합니다.


### bluemix sl subnet-list
{: #sl_subnet_list}

계정의 모든 서브넷 나열
```
   bluemix sl subnet list [OPTIONS]
```


<strong>명령 옵션</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>정렬 기준 열. 옵션: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름별 필터링.</dd>
   <dt>--identifier</dt>
   <dd>네트워크 ID별 필터링.</dd>
   <dt>-t, --subnet-type</dt>
   <dd>서브넷 유형별 필터링.</dd>
   <dt>--network-space</dt>
   <dd>네트워크 영역별 필터링.</dd>
   <dt>--v4, --ipv4</dt>
   <dd>IPv4 서브넷만 표시.</dd>
   <dt>--v6, --ipv6</dt>
   <dd>IPv6 서브넷만 표시.</dd>
   <dt>--order</dt>
   <dd>서브넷을 구매한 주문 ID별 필터링</dd>
   </dl>

**예제**:
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
이 명령은 현재 계정의 IP V4 서브넷을 나열합니다. 데이터 센터 기준 필터링은 dal09이고, 서브넷 유형은 PRIMARY이며 네트워크 영역은 PUBLIC입니다.



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

IP 주소를 찾고 해당 서브넷 및 디바이스 정보 표시
```
   bluemix sl subnet lookup IP_ADDRESS
```

**예제**:
```
 bluemix sl subnet lookup 9.125.235.255
```
이 명령은 주소가 9.125.235.255인 IP 주소 레코드를 찾고 해당 서브넷과 디바이스 정보를 표시합니다.


### bluemix sl vs cancel
{: #sl_vs_cancel}

가상 서버 인스턴스 취소
```
   bluemix sl vs cancel IDENTIFIER [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>

**예제**:
```
 bluemix sl vs cancel 12345678
```
이 명령은 ID가 12345678인 가상 서버 인스턴스를 취소합니다.


### bluemix sl vs capture
{: #sl_vs_capture}

가상 서버 인스턴스를 이미지로 캡처
```
 bluemix sl vs capture IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-n, --name</dt>
   <dd>이미지의 이름 [필수].</dd>
   <dt>--all</dt>
   <dd>VS에 속해 있는 모든 디스크 캡처.</dd>
   <dt>--note</dt>
   <dd>이미지와 연관시킬 참고 추가.</dd>
   </dl>

**예제**:
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
이 명령은 모든 디스크와 함께 ID가 12345678인 가상 서버 인스턴스를 이름이 "mybluemix"이며 "testing" 참고가 지정된 이미지로 캡처합니다.



### bluemix sl vs create
{: #sl_vs_create}

가상 서버 인스턴스 작성
```
   bluemix sl vs create [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-H, --hostname</dt>
   <dd>FQDN의 호스트 부분 [필수]</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN의 도메인 부분 [필수]</dd>
   <dt>-c, --cpu</dt>
   <dd>CPU 코어 수 [필수]</dd>
   <dt>-m, --memory</dt>
   <dd>메모리(MB) [필수]</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름 [필수]</dd>
   <dt>-o, --os</dt>
   <dd>OS 설치 코드. 팁: <OS>_LATEST를 지정할 수 있습니다.</dd>
   <dt>--image</dt>
   <dd>이미지 ID. [bluemix sl image list](#bluemix_sl_image_list)를 참조하십시오. </dd>
   <dt>--billing</dt>
   <dd>청구 비율. 기본값: hourly. 옵션: hourly, monthly</dd>
   <dt>--dedicated</dt>
   <dd>데디케이티드 가상 서버 작성(프라이빗 노드)</dd>
   <dt>--san</dt>
   <dd>로컬 디스크 대신 SAN 스토리지 사용</dd>
   <dt>--test</dt>
   <dd>가상 서버를 실제로 작성하지 않음</dd>
   <dt>--export</dt>
   <dd>템플리트 파일로 옵션 내보내기</dd>
   <dt>-i, --postinstall</dt>
   <dd>다운로드할 사후 설치 스크립트</dd>
   <dt>-k, --key</dt>
   <dd>루트 사용자에게 추가할 SSH 키 ID(다중 발생 허용)</dd>
   <dt>--disk</dt>
   <dd>디스크 크기(다중 발생 허용)</dd>
   <dt>--private</dt>
   <dd>가상 서버가 사설 네트워크만 액세스하도록 강제 실행</dd>
   <dt>--like</dt>
   <dd>기존 가상 서버의 구성 사용</dd>
   <dt>-n, --network</dt>
   <dd>네트워크 포트 속도(Mbps)</dd>
   <dt>--tag</dt>
   <dd>인스턴스에 추가할 태그(다중 발생 허용)</dd>
   <dt>-t, --template</dt>
   <dd>명령행 옵션을 기본값으로 설정하는 템플리트 파일</dd>
   <dt>-u, --userdata</dt>
   <dd>사용자 정의 메타데이터 문자열</dd>
   <dt>-F, --userfile</dt>
   <dd>파일에서 사용자 데이터 읽기</dd>
   <dt>--vlan-public</dt>
   <dd>가상 서버를 배치하려는 퍼블릭 VLAN ID</dd>
   <dt>--vlan-private</dt>
   <dd>가상 서버를 배치하려는 프라이빗 VLAN ID</dd>
   <dt>--wait</dt>
   <dd>리턴하기 전에 가상 서버가 프로비저닝을 완료할 때까지 최대 X초 동안 대기</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
	</dl>

**예제**:
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
이 명령은 호스트 이름이 myvsi이고, 도메인이 bluemix.net이며, 4개의 cpu 코어, 4096M 메모리를 포함하고
dal10 데이터 센터에 위치하며, 운영 체제가 UBUNTU 16 64비트이고, 2개 디스크(1개는 100G, 다른 하나는 1000G)가 있으며 ID 413인 공용 VLAN에 위치하는 가상 서버 인스턴스를 주문합니다.
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
이 명령은 실제로 주문하기 전에 위의 옵션을 포함하여 주문이 올바른지 테스트합니다.
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

이 명령은 나중에 사용하기 위해 사용자 홈 디렉토리 아래 myvsi.txt 파일로 위의 옵션을 내보냅니다. 


### bluemix sl vs options
{: #sl_vs_options}

가상 서버 인스턴스 작성에 대한 옵션 나열
```
   bluemix sl vs options [OPTIONS]
```

**예제**:
```
 bluemix sl vs options
```
이 명령은 가상 서버 인스턴스 작성에 대한 모든 옵션을 나열합니다(예: 데이터 센터, CPU, 메모리, OS, 디스크, 네트워크 속도 등).



### bluemix sl vs credentials
{: #sl_vs_credentials}

가상 서버 인스턴스 신임 정보 나열
```
   bluemix sl vs credentials IDENTIFIER [OPTIONS]
```
**예제**:
```
 bluemix sl vs credentials 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스의 모든 사용자 이름과 비밀번호 쌍을 나열합니다.

### bluemix sl vs detail
{: #sl_vs_detail}

가상 서버 인스턴스에 대한 세부사항 가져오기
```
   bluemix sl vs detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--passwords</dt>
   <dd>비밀번호를 표시합니다.</dd>
   <dt>--price</dt>
   <dd>연관된 가격을 표시합니다.</dd>
   </dl>


**예제**:
```
   bluemix sl vs details 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대한 자세한 정보를 나열합니다.


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

가상 서버 인스턴스에 대한 DNS 레코드 동기화
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONS]
```
참고: 인수를 지정하지 않는 경우, A 및 PTR 레코드를 모두 업데이트하려고 시도합니다. 두 레코드를 모두 업데이트하지 않으려는 경우,
   -a 또는 --ptr 인수를 사용하여 업데이트되는 레코드를 제한할 수 있습니다.

<strong>명령 옵션</strong>:
   <dl>
   <dt>-a, --a-record</dt>
   <dd>호스트에 대한 A 레코드 동기화</dd>
   <dt>--aaaa-record</dt>
   <dd>호스트에 대한 AAAA 레코드 동기화</dd>
   <dt>--ptr</dt>
   <dd>호스트에 대한 PTR 레코드 동기화</dd>
   <dt>--ttl</dt>
   <dd>A 및/또는 PTR 레코드용 TTL 설정, 기본값: 7200</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>


**예제**:
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
이 명령은 ID 12345678인 가상 서버 인스턴스의 A 레코드(IP V4 주소)를 DNS 서버에 동기화하고 이 A 레코드의 ttl을 3600으로 설정합니다.
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
이 명령은 ID 12345678인 가상 서버 인스턴스의 AAAA 레코드(IP V6 주소) 및 PTR 레코드를 모두 DNS 서버에 동기화합니다.


### bluemix sl vs edit
{: #sl_vs_edit}

가상 서버 인스턴스의 세부사항 편집
```
   bluemix sl vs edit IDENTIFIER [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>-D, --domain</dt>
   <dd>FQDN의 도메인 부분</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN의 호스트 부분. 예: server</dd>
   <dt>--tag</dt>
   <dd>설정할 태그 또는 모두 제거하려면 빈 문자열 지정</dd>
   <dt>-u, --userdata</dt>
   <dd>사용자 정의 메타데이터 문자열</dd>
   <dt>-F, --userfile</dt>
   <dd>파일에서 사용자 데이터 읽기</dd>
   <dt>--public-speed</dt>
   <dd>공용 포트 속도, 옵션: 0, 10, 100, 1000, 10000</dd>
   <dt>--private-speed</dt>
   <dd>개인용 포트 속도, 옵션: 0, 10, 100, 1000, 10000</dd>
   </dl>

**예제**:
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
이 명령은 ID `12345678`인 가상 서버 인스턴스를 업데이트하고 해당 도메인을 `bluemix.net`, 호스트 이름을 `myapp`, 태그를 `testcli`, 그리고 공용 네트워크 포트 속도를 1000Mbps로 설정합니다.



### bluemix sl vs list
{: #sl_vs_list}
계정의 가상 서버 인스턴스 나열
```
   bluemix sl vs list [OPTIONS]
```


<strong>명령 옵션</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU 코어 수</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN의 도메인 부분</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN의 호스트 부분</dd>
   <dt>-m, --memory</dt>
   <dd>메모리(MB)</dd>
   <dt>-n, --network</dt>
   <dd>네트워크 포트 속도(Mbps)</dd>
   <dt>--hourly</dt>
   <dd>시간별 인스턴스만 표시</dd>
   <dt>--monthly</dt>
   <dd>월별 인스턴스만 표시</dd>
   <dt>--tag</dt>
   <dd>태그별 필터링(다중 발생 허용)</dd>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: id,hostname,domain,datacenter,cpu,memory,primary_ip,backend_ip. 기본값: hostname</dd>
   <dt>--columns</dt>
   <dd>표시할 열, 옵션: guid,primary_ip,backend_ip,datacenter,action,power_state,created_by,tags. 기본값: id, hostname, primary_ip, backend_ip, datacenter, action</dd>
    </dl>

**예제**:
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
이 명령은 현재 계정의 시간별 청구되는 모든 가상 서버 인스턴스를 나열합니다. 도메인 기준 필터링은 "bluemix.net"과 동일하고 메모리별로 정렬합니다.



### bluemix sl vs-pause
{: #sl_vs_pause}

활성 가상 서버 인스턴스 일시정지
```
   bluemix sl vs pause IDENTIFIER [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>

**예제**:
```
 bluemix sl vs pause 12345678 -f
```
이 명령은 확인 요청 없이 ID 12345678인 가상 서버 인스턴스를 일시정지합니다.



### bluemix sl vs power-off
{: #sl_vs_power_off}

활성 가상 서버 인스턴스 전원 끄기
```
   bluemix sl vs power-off IDENTIFIER [OPTIONS]
```

**예제**:
```
   bluemix sl vs power-off 12345678 --soft
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대해 소프트 전원 끄기를 수행합니다.

<strong>명령 옵션</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>하드 시스템 종료 수행</dd>
   <dt>--soft</dt>
   <dd>소프트 시스템 종료 수행</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

가상 서버 인스턴스 전원 켜기
```
 bluemix sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>

**예제**:
```
 bluemix sl vs power-on 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대해 전원 켜기를 수행합니다.


### bluemix sl vs ready
{: #sl_vs_ready}

가상 서버 인스턴스가 사용할 준비가 되었는지 확인
```
 bluemix sl vs ready IDENTIFIER [OPTIONS]
```

**예제**:
```
 bluemix sl vs ready 12345678 --wait 30
```
이 명령은 계속 사용할 준비가 되었는지 확인하기 위해 ID 12345678인 가상 서버 인스턴스 상태를 확인하고 최대 30초 동안 대기합니다.

<strong>명령 옵션</strong>:
   <dl>
   <dt>--wait</dt>
   <dd>리턴하기 전에 가상 서버가 프로비저닝을 완료할 때까지 최대 X초 동안 대기</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

활성 가상 서버 인스턴스 다시 부팅
```
 bluemix sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>하드 재부팅 수행</dd>
   <dt>--soft</dt>
   <dd>소프트 재부팅 수행</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>

**예제**:
```
 bluemix sl vs reboot 12345678 --hard
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대해 하드 재부팅을 수행합니다.



### bluemix sl vs reload
{: #sl_vs_reload}

가상 서버 인스턴스에서 운영 체제 다시 로드
```
 bluemix sl vs reload IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>다운로드할 사후 설치 스크립트</dd>
   <dt>--image</dt>
   <dd>이미지 ID. 기본값은 현재 운영 체제를 사용하는 것입니다. 'bluemix sl image list'를 참조하십시오. </dd>
   <dt>-k, --key</dt>
   <dd>루트 사용자에게 추가할 SSH 키 ID(다중 발생 허용)</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>

**예제**:
```
   bluemix sl vs reload 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대해 현재 운영 체제를 다시 로드합니다.
```
 bluemix sl vs reload 12345678 --image 1234
```
이 명령은 ID 12345678인 가상 서버 인스턴스에 대해 ID 1234인 이미지에서 운영 체제를 다시 로드합니다.



### bluemix sl vs rescure
{: #sl_vs_rescure}

가상 서버 인스턴스를 복구 이미지로 다시 부팅
```
 bluemix sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
   </dl>
   
**예제**:
```
 bluemix sl vs rescue 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스를 복구 이미지로 다시 부팅합니다.


### bluemix sl vs resume
{: #sl_vs_resume}

일시정지된 가상 서버 인스턴스 재개
```
   bluemix sl vs resume IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>

**예제**:
```
 bluemix sl vs resume 12345678
```
이 명령은 ID 12345678인 가상 서버 인스턴스를 재개합니다.


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

가상 서버 인스턴스 업그레이드
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONS]
```
참고: 업그레이드 요청이 처리되고 나면 SoftLayer는 자동으로 인스턴스를 다시 부팅합니다. 인스턴스는 업그레이드 트랜잭션이 완료될 때까지 정지됩니다. 그러나 네트워크의 경우 다시 부팅할 필요가 없습니다.

<strong>명령 옵션</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU 코어 수</dd>
   <dt>--private</dt>
   <dd>CPU 코어는 전용 호스트 서버에 위치합니다. </dd>
   <dt>-m, --memory</dt>
   <dd>메모리(MB).</dd>
   <dt>--network</dt>
   <dd>네트워크 포트 속도(Mbps).</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행.</dd>
    </dl>

**예제**:
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
이 명령은 ID 12345678인 가상 서버 인스턴스를 업그레이드하고 CPU 코어 수를 8로, 메모리를 8192M로, 네트워크 포트 속도를 1000Mbps로 설정합니다.



### bluemix sl vlan create
{: #sl_vlan_create}

새 VLAN 작성
```
   bluemix sl vlan create [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>VLAN의 유형(공용 또는 개인용 중 하나)</dd>
   <dt>-r, --router</dt>
   <dd>라우터의 호스트 이름</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터의 짧은 이름</dd>
   <dt>-s, --size</dt>
   <dd>서브넷의 크기, 옵션: 8(사용 가능한 5개 IP), 16(사용 가능한 13개 IP) 또는 32(사용 가능한 29개 IP)</dd>
   <dt>-n, --name</dt>
   <dd>VLAN의 이름</dd>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>

**예제**:
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
이 명령은 16개의 IP 주소와 함께 데이터 센터 dal09에 위치하고 이름이 myvlan인 공용 VLAN을 작성합니다.
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
이 명령은 16개의 IP 주소와 함께 라우터 bcr01a.dal09에 배치되고 이름이 myvlan인 VLAN을 작성합니다.



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

VLAN 취소
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>확인 없이 조작 강제 실행</dd>
    </dl>

**예제**:
```
   bluemix sl vlan cancel 12345678 -f
```
이 명령은 확인 요청 없이 ID 12345678인 VLAN을 취소합니다.



### bluemix sl vlan detail
{: #sl_vlan_detail}

VLAN에 대한 세부사항 가져오기.
```
   bluemix sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>가상 서버 목록 숨기기</dd>
   <dt>--no-hardware</dt>
   <dd>하드웨어 목록 숨기기</dd>
   </dl>

**예제**:
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
이 명령은 ID 12345678인 VLAN의 세부사항을 표시하며 가상 서버 또는 하드웨어 서버는 나열하지 않습니다.


### bluemix sl vlan edit
{: #sl_vlan_edite}

VLAN에 대한 세부사항 편집
```
   bluemix sl vlan edit IDENTIFIER [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--n, --name</dt>
   <dd>VLAN의 이름</dd>
    </dl>

**예제**:
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
이 명령은 ID 12345678인 VLAN을 업데이트하고 새 이름으로 "myvlan-rename"을 지정합니다.


### bluemix sl vlan list
{: #sl_vlan_list}

계정의 모든 VLAN 나열
```
 bluemix sl vlan list [OPTIONS]
```
<strong>명령 옵션</strong>:

   <dl>
   <dt>--sortby</dt>
   <dd>정렬 기준 열, 옵션: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
   <dt>-d, --datacenter</dt>
   <dd>데이터 센터 짧은 이름별 필터링</dd>
   <dt>-n, --number</dt>
   <dd>VLAN 번호별 필터링</dd>
   <dt>--name</dt>
   <dd>VLAN 이름별 필터링</dd>
   <dt>--order</dt>
   <dd>VLAN을 구매한 주문 ID별 필터링</dd>
   </dl>

**예제**:
```
 bluemix sl vlan list -d dal09 --sortby number
```
이 명령은 현재 계정의 모든 VLAN을 나열합니다. 데이터 센터 기준 필터링은 dal09와 동일하고 VLAN 번호별로 정렬합니다.




### bluemix sl vlan options
{: #sl_vlan_options}

VLAN 작성에 대한 모든 옵션 나열
```
   bluemix sl vlan options
```
**예제**:
```
 bluemix sl vlan options
```
이 명령은 VLAN 작성에 대한 모든 옵션을 나열합니다(예: VLAN 유형, 데이터 센터, 서브넷 크기, 라우터 등).
