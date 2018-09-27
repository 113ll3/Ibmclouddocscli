---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 虛擬伺服器

請使用下列指令管理 {{site.data.keyword.Bluemix_notm}} 基礎架構虛擬伺服器。
{: shortdesc}

<table summary="按字母順序排序的 {{site.data.keyword.Bluemix_notm}} 基礎架構虛擬伺服器指令，其鏈結提供指令的相關資訊">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ## ibmcloud sl vs cancel
{: #sl_vs_cancel}

取消虛擬伺服器實例。
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs cancel 12345678
```
這個指令會取消 ID 為 12345678 的虛擬伺服器實例。


## ibmcloud sl vs capture
{: #sl_vs_capture}

將虛擬伺服器實例擷取至映像檔。
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>必要。映像檔的名稱。</dd>
<dt>--all</dt>
<dd>擷取屬於 VS 的所有磁碟。</dd>
<dt>--note</dt>
<dd>新增要與映像檔相關聯的附註。</dd>
</dl>

**範例**：
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
這個指令會將 ID 為 12345678 的虛擬伺服器實例及其所有磁碟都擷取至名為 "mycloud" 且附註為 "testing" 的映像檔。

## ibmcloud sl vs create
{: #sl_vs_create}

建立虛擬伺服器實例。
```
ibmcloud sl vs create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>必要。FQDN 的主機部分。</dd>
<dt>-D, --domain</dt>
<dd>必要。FQDN 的網域部分。</dd>
<dt>-c, --cpu</dt>
<dd>必要。CPU 核心數目。</dd>
<dt>-m, --memory</dt>
<dd>必要。記憶體（以 MB 為單位）。</dd>
<dt>--flavor</dt>
<dd>「公用虛擬伺服器」特性金鑰名稱。</dd>
<dt>-d, --datacenter</dt>
<dd>必要。資料中心簡稱。</dd>
<dt>-o, --os</dt>
<dd>OS 安裝程式碼。提示：您可以指定 <OS>_LATEST。</dd>
<dt>--image</dt>
<dd>映像檔 ID。如需參考資料，請參閱：'ibmcloud sl image list'。</dd>
<dt>--billing</dt>
<dd>計費頻率。預設值為：hourly。選項包含：hourly、monthly。</dd>
<dt>--dedicated</dt>
<dd>建立專用虛擬伺服器（專用節點）。</dd>
<dt>--host-id</dt>
<dd>要佈建「專用虛擬伺服器」的主機 ID。</dd>
<dt>--san</dt>
<dd>使用 SAN 儲存空間，而不是本端磁碟。</dd>
<dt>--test</dt>
<dd>不要實際建立虛擬伺服器。</dd>
<dt>--export</dt>
<dd>將選項匯出至範本檔。</dd>
<dt>-i, --postinstall</dt>
<dd>要下載的後置安裝 Script。</dd>
<dt>-k, --key</dt>
<dd>要新增至 root 使用者的 SSH 金鑰 ID（允許指定多次）。</dd>
<dt>--disk</dt>
<dd>磁碟大小（允許指定多次）。</dd>
<dt>--private</dt>
<dd>強制虛擬伺服器只能存取專用網路。</dd>
<dt>--like</dt>
<dd>使用現有虛擬伺服器的配置。</dd>
<dt>-n, --network</dt>
<dd>網路埠速度 (Mbps)。</dd>
<dt>-g, --tag</dt>
<dd>要新增至實例的標籤（允許指定多次）。</dd>
<dt>-t, --template</dt>
<dd>預設指令行選項的範本檔。</dd>
<dt>-u, --userdata</dt>
<dd>使用者定義的 meta 資料字串。</dd>
<dt>-F, --userfile</dt>
<dd>從檔案讀取使用者資料。</dd>
<dt>--vlan-public</dt>
<dd>要放置虛擬伺服器的公用 VLAN 的 ID。</dd>
<dt>--vlan-private</dt>
<dd>要放置虛擬伺服器的專用 VLAN 的 ID。</dd>
<dt>-S, --public-security-group</dt>
<dd>要與公用介面建立關聯的安全群組 ID（允許指定多次）。</dd>
<dt>-s, --private-security-group</dt>
<dd>要與專用介面建立關聯的安全群組 ID（允許指定多次）。</dd>
<dt>--wait</dt>
<dd>等待虛擬伺服器完成佈建，最多 X 秒後才返回。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
這個指令會訂購虛擬伺服器實例，其主機名稱為 myvsi、網域為 ibm.com、有 4 個 CPU 核心及 4096M 的記憶體，位於資料中心：dal10。

## ibmcloud sl vs options
{: #sl_vs_options}

列出用來建立虛擬伺服器實例的選項。
```
ibmcloud sl vs options [OPTIONS]
```


**範例**：
```
ibmcloud sl vs options
```
這個指令會列出用來建立虛擬伺服器實例的所有選項，例如資料中心、CPU、記憶體、OS、磁碟、網路速度等等。

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

列出虛擬伺服器實例認證。
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**範例**：
```
ibmcloud sl vs credentials 12345678
```
這個指令會列出 ID 為 12345678 的虛擬伺服器實例的所有使用者名稱及密碼配對。

## ibmcloud sl vs detail
{: #sl_vs_detail}

取得虛擬伺服器實例的詳細資料。
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--passwords</dt>
<dd>顯示密碼（小心背後有人偷窺！）。</dd>
<dt>--price</dt>
<dd>顯示關聯的價格。</dd>
</dl>

**範例**：
```
ibmcloud sl vs details 12345678
```
這個指令會列出 ID 為 12345678 的虛擬伺服器實例的詳細資訊。

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

為虛擬伺服器實例同步 DNS 記錄。
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-a, --a-record</dt>
<dd>為主機同步 A 記錄。</dd>
<dt>--aaaa-record</dt>
<dd>為主機同步 AAAA 記錄。</dd>
<dt>--ptr</dt>
<dd>為主機同步 PTR 記錄。</dd>
<dt>--ttl</dt>
<dd>設定 A 及（或）PTR 記錄的 TTL，預設值為：7200。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
這個指令會將 ID 為 12345678 的虛擬伺服器實例的 A 記錄（IP V4 位址）同步至 DNS 伺服器，並將這個 A 記錄的 ttl 設為 3600。

## ibmcloud sl vs edit
{: #sl_vs_edit}

編輯虛擬伺服器實例的詳細資料。
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-D, --domain</dt>
<dd>FQDN 的網域部分。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN 的主機部分。範例：server。</dd>
<dt>-g, --tag</dt>
<dd>要設定的標籤，或使用空字串以便全部移除。</dd>
<dt>-u, --userdata</dt>
<dd>使用者定義的 meta 資料字串。</dd>
<dt>-F, --userfile</dt>
<dd>從檔案讀取使用者資料。</dd>
<dt>--public-speed</dt>
<dd>公用埠速度，選項包含：0、10、100、1000、10000。</dd>
<dt>--private-speed</dt>
<dd>專用埠速度，選項包含：0、10、100、1000、10000。</dd>
</dl>

**範例**：
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
這個指令會更新 ID 為 12345678 的虛擬伺服器實例，並將其網域設為 "ibm.com"、將主機名稱設為 "myapp"、將標籤設為 "testcli"。

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

建立專用虛擬伺服器的主機。
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>必要。FQDN 的主機部分。</dd>
<dt>-D, --domain</dt>
<dd>必要。FQDN 的網域部分。</dd>
<dt>-d, --datacenter</dt>
<dd>必要。資料中心簡稱。</dd>
<dt>-s, --size</dt>
<dd>專用主機的大小，目前只有一個大小可用：56_CORES_X_242_RAM_X_1_4_TB。</dd>
<dt>-b, --billing</dt>
<dd>計費頻率。預設值為：hourly。選項包含：hourly、monthly。</dd>
<dt>-v, --vlan-private</dt>
<dd>要放置專用主機之專用 VLAN 的 ID。如需參考資料，請參閱：'ibmcloud sl vlan list'。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

列出您帳戶上的專用主機。
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>依專用主機的名稱過濾。</dd>
<dt>-d, --datacenter</dt>
<dd>依專用主機的資料中心過濾。</dd>
<dt>--owner</dt>
<dd>依專用主機的擁有者過濾。</dd>
<dt>--order</dt>
<dd>依購買此專用主機的訂單 ID 過濾。</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

列出您帳戶上的虛擬伺服器實例。
```
ibmcloud sl vs list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>依 CPU 核心數目過濾。</dd>
<dt>-D, --domain</dt>
<dd>依 FQDN 的網域部分過濾。</dd>
<dt>-d, --datacenter</dt>
<dd>依資料中心簡稱過濾。</dd>
<dt>-H, --hostname</dt>
<dd>依 FQDN 的主機部分過濾。</dd>
<dt>-m, --memory</dt>
<dd>依記憶體過濾（以 MB 為單位）。</dd>
<dt>-n, --network</dt>
<dd>依網路埠速度過濾（以 Mbps 為單位）。</dd>
<dt>-P, --public-ip</dt>
<dd>依公用 IP 位址過濾。</dd>
<dt>-p, --private-ip</dt>
<dd>依專用 IP 位址過濾。</dd>
<dt>--hourly</dt>
<dd>僅顯示按小時計費的實例。</dd>
<dt>--monthly</dt>
<dd>僅顯示按月計費的實例。</dd>
<dt>-g, --tag</dt>
<dd>依標籤過濾（允許指定多次）。</dd>
<dt>-o, --order</dt>
<dd>依購買此實例的訂單 ID 過濾。</dd>
<dt>--owner</dt>
<dd>依擁有實例的使用者 ID 過濾。</dd>
<dt>--sortby</dt>
<dd>直欄排序方式，預設值為：hostname，選項包含：id、hostname、domain、datacenter、cpu、memory、public_ip、private_ip。</dd>
<dt>--columns</dt>
<dd>要顯示的直欄，預設值為：id、hostname、public_ip、private_ip、datacenter、action，選項包含：guid、power_state、created_by、tags。</dd>
</dl>

**範例**：
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
這個指令會列出現行帳戶上所有依時數計費的虛擬伺服器實例，用來過濾的網域為 "ibm.com"，並依記憶體排序。

## ibmcloud sl vs pause
{: #sl_vs_pause}

暫停作用中虛擬伺服器實例。
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs pause 12345678 -f
```
這個指令會暫停 ID 為 12345678 的虛擬伺服器實例，而不要求確認。

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

關閉作用中虛擬伺服器實例。
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--hard</dt>
<dd>執行強迫關機。</dd>
<dt>--soft</dt>
<dd>執行正常關機。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs power-off 12345678 --soft
```
這個指令會針對 ID 為 12345678 的虛擬伺服器實例執行正常關機。

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

啟動虛擬伺服器實例。
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs power-on 12345678
```
這個指令會針對 ID 為 12345678 的虛擬伺服器實例執行開機作業。

## ibmcloud sl vs ready
{: #sl_vs_ready}

檢查是否有虛擬伺服器實例已備妥可供使用。
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--wait</dt>
<dd>等待虛擬伺服器完成佈建，最多 X 秒後才返回。</dd>
</dl>

**範例**：
```
ibmcloud sl vs ready 12345678 --wait 30
```
這個指令會檢查 ID 為 12345678 的虛擬伺服器實例狀態，以查看它是否準備好可繼續使用，最多等待 30 秒。

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

將作用中虛擬伺服器實例重新開機。
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--hard</dt>
<dd>執行強迫重新開機。</dd>
<dt>--soft</dt>
<dd>執行正常重新開機。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs reboot 12345678 --hard
```
這個指令會針對 ID 為 12345678 的虛擬伺服器實例執行強迫重新開機。

## ibmcloud sl vs reload
{: #sl_vs_reload}

在虛擬伺服器實例上重新載入作業系統。
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-i, --postinstall</dt>
<dd>要下載的後置安裝 Script。</dd>
<dt>--image</dt>
<dd>映像檔 ID。預設值為使用現行作業系統。</dd>
<dt>請參閱：</dt>
<dd>'ibmcloud sl image list' for reference.</dd>
<dt>-k, --key</dt>
<dd>要新增至 root 使用者的 SSH 金鑰 ID（允許指定多次）。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs reload 12345678
```
這個指令會針對 ID 為 12345678 的虛擬伺服器實例重新載入現行作業系統。

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

將虛擬伺服器實例重新開機至救援映像檔。
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs rescue 12345678
```
這個指令會將 ID 為 12345678 的虛擬伺服器實例重新開機至救援映像檔。

## ibmcloud sl vs resume
{: #sl_vs_resume}

繼續已暫停的虛擬伺服器實例。
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs resume 12345678
```
這個指令會繼續 ID 為 12345678 的虛擬伺服器實例。

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

升級虛擬伺服器實例。
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>CPU 核心數目。</dd>
<dt>--private</dt>
<dd>CPU 核心將會在專用的主伺服器上。</dd>
<dt>-m, --memory</dt>
<dd>記憶體（以 MB 為單位）。</dd>
<dt>--network</dt>
<dd>網路埠速度 (Mbps)。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
這個指令會升級 ID 為 12345678 的虛擬伺服器實例，並將 CPU 核心數目設為 8、將記憶體設為 8192M、將網路埠速度設為 1000 Mbps。
