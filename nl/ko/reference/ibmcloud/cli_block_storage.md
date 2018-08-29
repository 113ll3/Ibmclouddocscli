---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} 인프라 블록 스토리지 관리

 <table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 {{site.data.keyword.Bluemix_notm}} 인프라 명령">
<caption>표 1. {{site.data.keyword.Bluemix_notm}} 인프라 블록 스토리지</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} 인프라 블록 스토리지</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_password)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_cancel)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-count](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_count)</td>    <td>[ibmcloud sl block volume-detail](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_detail)</td>
   <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_options)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>

## ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

제공된 볼륨에 액세스하도록 호스트에 권한을 부여합니다.
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>권한 부여할 하나의 하드웨어 서버의 ID입니다.</dd>
<dt>-v, --virtual-id</dt>
<dd>권한 부여할 하나의 가상 서버의 ID입니다.</dd>
<dt>-i, --ip-address-id</dt>
<dd>권한 부여할 하나의 IP 주소의 ID입니다.</dd>
<dt>-p, --ip-address</dt>
<dd>권한 부여할 IP 주소입니다.</dd>
</dl>

**예제**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
이 명령은 ID 87654321인 가상 서버가 ID가 12345678인 볼륨에 액세스하도록 권한을 부여합니다.

## ibmcloud sl block access-list
{: #sl_block_access_list}

ACL을 나열합니다.
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>표시할 열, 옵션: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**예제**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
이 명령은 ID가 12345678인 볼륨에 액세스하도록 권한이 부여된 모든 호스트를 나열하고 ID별로 정렬합니다.

## ibmcloud sl block access-password
{: #sl_block_access_password}

볼륨 액세스를 위한 비밀번호를 변경합니다.
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

제공된 볼륨에 액세스 중인 호스트에 대한 권한 부여를 취소합니다.
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>권한을 취소할 하나의 하드웨어 서버 ID.</dd>
<dt>-v, --virtual-id</dt>
<dd>권한을 취소할 하나의 가상 서버 ID.</dd>
<dt>-i, --ip-address-id</dt>
<dd>권한을 취소할 하나의 IP 주소 ID.</dd>
<dt>-p, --ip-address</dt>
<dd>권한을 취소할 하나의 IP 주소.</dd>
</dl>

**예제**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
이 명령은 ID 87654321인 가상 서버의 ID가 12345678인 볼륨에 대한 액세스 권한을 취소합니다.

## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

복제본에서 블록 볼륨을 장애 복구합니다.
```
ibmcloud sl block replica-failback VOLUME_ID
```


**예제**:
```
ibmcloud sl block replica-failback 12345678
```
이 명령은 ID가 12345678인 볼륨에 대해 장애 복구 조작을 수행합니다.

## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

제공된 복제본 볼륨으로 블록 볼륨을 장애 복구합니다.
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**예제**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
이 명령은 ID 87654321인 복제본 볼륨에 ID가 12345678인 볼륨에 대한 장애 복구 조작을 수행합니다.

## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

제공된 볼륨에 대해 적합한 복제 데이터 센터를 나열합니다.
```
ibmcloud sl block replica-locations VOLUME_ID
```


**예제**:
```
ibmcloud sl block replica-locations 12345678
```
이 명령은 ID가 12345678인 블록 볼륨에 대해 적합한 복제 데이터 센터를 나열합니다.

## ibmcloud sl block replica-order
{: #sl_block_replica_order}

블록 스토리지 복제본 볼륨을 주문합니다.
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>필수. 복제에 사용할 스냅샷 스케줄. 옵션: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>필수. 복제본에 대한 데이터 센터의 짧은 이름(예: dal09).</dd>
<dt>-t, --tier</dt>
<dd>선택사항. 복제본이 주문되는 기본 볼륨의 Endurance Storage Tier(GB당 IOPS). 옵션: 0.25,2,4,10. 계층이 지정되지 않은 경우 원본 볼륨의 계층이 사용됩니다.</dd>
<dt>-i, --iops</dt>
<dd>100 - 6000의 100의 배수인 Performance Storage IOP. 지정되지 않은 경우 원본 볼륨의 IOPS가 사용됩니다.</dd>
<dt>-o, --os-type</dt>
<dd>선택사항. 복제본이 주문되는 기본 볼륨의 운영 체제 유형(예: Linux). 옵션: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
이 명령은 ID가 12345678인 볼륨에 대한 복제본(일별 복제를 수행하며, 계층 레벨 4 및 OS 유형 Linux인 dal09에 위치함)을 주문합니다.

## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

블록 볼륨에 대한 기존 복제본 볼륨을 나열합니다.
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**예제**:
```
ibmcloud sl block replica-partners 12345678
```
이 명령은 ID가 12345678인 블록 볼륨의 기존 복제본 볼륨을 나열합니다.

## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

제공된 볼륨에 대한 기존 스냅샷 영역을 취소합니다.
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--reason</dt>
<dd>취소에 대한 선택적 이유.</dd>
<dt>--immediate</dt>
<dd>청구 주기 대신 즉시 스냅샷 영역 취소.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
이 명령은 확인을 요청하지 않고 즉시 ID가 12345678인 스냅샷을 취소합니다.

## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

제공된 볼륨의 스냅샷을 작성합니다.
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-n, --note</dt>
<dd>새 스냅샷에 설정할 참고.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
이 명령은 snapshotforibmcloud와 같은 추가 참고와 함께 ID가 12345678인 볼륨에 대한 스냅샷을 작성합니다.

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

제공된 볼륨에 대해 지정된 스케줄에 따라 스냅샷을 사용 중지합니다.
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>필수. 스냅샷 스케줄. 옵션: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
이 명령은 ID가 12345678인 볼륨에 대한 일별 스냅샷을 사용 안함으로 설정합니다.

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

지정된 스케줄에 따라 제공된 볼륨에 대한 스냅샷을 사용합니다.
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>필수. 스냅샷 스케줄. 옵션: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>필수. 유지할 스냅샷 수입니다.</dd>
<dt>-m, --minute</dt>
<dd>스냅샷을 작성해야 하는 시간(분), 0 - 59 사이의 정수.</dd>
<dt>-r, --hour</dt>
<dd>스냅샷을 작성해야 하는 시간, 0 - 23 사이의 정수.</dd>
<dt>-d, --day-of-week</dt>
<dd>스냅샷을 작성해야 하는 요일, 0 - 6 사이의 정수. 0은 일요일, 1은 월요일, 2는 화요일, 3은 수요일, 4는 목요일, 5는 금요일, 6은 토요일을 의미합니다.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
이 명령은 ID가 12345678인 볼륨의 스냅샷을 사용으로 설정하고, 스냅샷은 매주 일요일 2시에 작성되며 최대 5개의 스냅샷이 유지됩니다.

## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

제공된 볼륨의 스냅샷을 삭제합니다.
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**예제**:
```
ibmcloud sl block snapshot-delete 12345678
```
이 명령은 ID가 12345678인 스냅샷을 삭제합니다.

## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

블록 스토리지 스냅샷을 나열합니다.
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id,name,created,size_bytes.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
이 명령은 ID가 12345678인 볼륨의 모든 스냅샷을 나열하고 ID별로 정렬합니다.

## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

블록 스토리지 볼륨에 대한 스냅샷 영역을 주문합니다.
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-s, --size</dt>
<dd>필수. 작성할 스냅샷 영역의 크기(GB).</dd>
<dt>-t, --tier</dt>
<dd>선택사항. 영역이 주문되는 블록 볼륨의 Endurance Storage Tier(GB당 IOPS). 옵션: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>100 - 6000의 100의 배수인 Performance Storage IOP.</dd>
<dt>-u, --upgrade</dt>
<dd>업그레이드 주문임을 표시하는 플래그.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
이 명령은 ID가 12345678인 볼륨에 대한 스냅샷 영역을 주문합니다. 크기는 1,000GB이고 계층 레벨은 GB당 4IOPS입니다.

## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

제공된 스냅샷을 사용하여 블록 볼륨을 복원합니다.
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**예제**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
이 명령은 ID 87654321인 스냅샷에서 ID가 12345678인 볼륨을 복원합니다.

## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

기존 블록 스토리지 볼륨을 취소합니다.
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--reason</dt>
<dd>취소에 대한 선택적 이유.</dd>
<dt>--immediate</dt>
<dd>청구 주기 대신에 즉시 블록 스토리지 볼륨 취소.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
이 명령은 확인을 요청하지 않고 즉시 ID가 12345678인 볼륨을 취소합니다.

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

데이터 센터당 블록 스토리지 볼륨의 수를 나열합니다.
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
</dl>

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

블록 스토리지를 나열합니다.
```
ibmcloud sl block volume-list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-u, --username</dt>
<dd>볼륨 사용자 이름별 필터링.</dd>
<dt>-d, --datacenter</dt>
<dd>데이터 센터 짧은 이름별 필터링.</dd>
<dt>-t, --storage-type</dt>
<dd>스토리지 볼륨 유형별 필터링. 옵션: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>블록 스토리지를 구매한 주문 ID별 필터링.</dd>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>표시할 열, 옵션: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**예제**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
이 명령은 dal09에 위치하는 현재 계정의 모든 endurance 볼륨을 나열하고 용량별로 정렬합니다.

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

기존 블록 스토리지 볼륨에서 LUN ID를 설정합니다.
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

제공된 볼륨에 대한 세부사항을 표시합니다.
```
ibmcloud sl block volume-detail VOLUME_ID
```


**예제**:
```
ibmcloud sl block volume-detail 12345678
```
이 명령은 ID가 12345678인 볼륨의 세부사항을 표시합니다.

## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

기존 볼륨을 복제하여 블록 볼륨을 주문합니다.
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>복제에 사용할 원본 볼륨 스냅샷의 ID.</dd>
<dt>-s, --duplicate-size</dt>
<dd>중복 블록 볼륨의 크기(GB). 크기가 지정되지 않은 경우 원본 볼륨의 크기가 사용됩니다.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>100 - 6000의 100의 배수인 Performance Storage IOPS. 지정되지 않은 경우 원본 볼륨의 IOPS가 사용됩니다.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance Storage Tier. 계층이 지정되지 않은 경우 원본 볼륨의 계층이 사용됩니다.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>복제를 위해 주문할 스냅샷 영역의 크기. 스냅샷 영역 크기가 지정되지 않은 경우 원본 볼륨의 스냅샷 영역 크기가 사용됩니다.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block volume-duplicate 12345678
```
이 명령은 ID가 12345678인 볼륨을 복제하여 새 볼륨 주문을 표시합니다.

## ibmcloud sl block volume-order
{: #sl_block_volume_order}

블록 스토리지 볼륨을 주문합니다.
```
ibmcloud sl block volume-order [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>필수. 스토리지 볼륨의 유형. 옵션: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>필수. 스토리지 볼륨의 크기(GB).</dd>
<dt>-i, --iops</dt>
<dd>100 - 6000의 100의 배수인 Performance Storage IOP[storage-type performance에 필요].</dd>
<dt>-e, --tier</dt>
<dd>Endurance Storage Tier(GB당 IOP)[storage-type endurance에 필요]. 옵션: 0.25,2,4,10.</dd>
<dt>-o, --os-type</dt>
<dd>필수. 운영 체제. 옵션: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>필수. 데이터 센터의 짧은 이름.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Endurance 블록 스토리지와 함께 스냅샷 영역을 주문하기 위한 선택적 매개변수. 주문할 스냅샷 영역의 크기(GB)를 지정합니다.</dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
이 명령은 크기가 1000GB, IOPS가 4000, OS 유형은 LINUX이고, dal09에 위치하는 performance 볼륨을 주문합니다.

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

블록 스토리지 주문을 위한 모든 옵션을 나열합니다.
```
ibmcloud sl block volume-options
```


**예제**:
```
ibmcloud sl block volume-options
```
이 명령은 스토리지 유형, 볼륨 크기, OS 유형, IOPS, 계층 레벨, 데이터 센터 및 스냅샷 크기를 포함하여 블록 스토리지 볼륨 작성에 대한 모든 옵션을 나열합니다.
