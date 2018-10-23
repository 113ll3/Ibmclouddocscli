---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 硬體

{{site.data.keyword.baremetal_long}} 是單一承租戶的實體伺服器，可為您提供效能與控制，並且可以對硬體資源進行低階的存取。Bare Metal Server 為您的處理器密集與磁碟 I/O 密集的工作負載，提供您需要的原始馬力。這些伺服器具有標準特性及服務的最完整套件。

請使用下列指令管理 {{site.data.keyword.Bluemix}} 基礎架構裸機硬體伺服器。
{: shortdesc}

<table summary="按字母順序排序的 {{site.data.keyword.Bluemix_notm}} 基礎架構裸機伺服器指令，其鏈結提供指令的相關資訊">
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create_options)</td>
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

取消硬體伺服器。
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-i, --immediate</dt>
<dd>立即取消伺服器，而不是在計費週年日取消。</dd>
<dt>-r, --reason</dt>
<dd>選用的取消原因。如需可用的選項清單，請參閱 'ibmcloud sl hardware cancel-reasons'。</dd>
<dt>-c, --comment</dt>
<dd>要新增至取消問題單的選用註解。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

顯示取消原因清單。
```
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

訂購/建立硬體伺服器。
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN 的主機部分，必要項目。</dd>
<dt>-D, --domain</dt>
<dd>FQDN 的網域部分，必要項目。</dd>
<dt>-s, --size</dt>
<dd>硬體大小，必要項目。</dd>
<dt>-o, --os</dt>
<dd>OS 安裝程式碼，必要項目。</dd>
<dt>-d, --datacenter</dt>
<dd>資料中心簡稱，必要項目。</dd>
<dt>-p, --port-speed</dt>
<dd>埠速度，必要項目。</dd>
<dt>-b, --billing</dt>
<dd>計費費率（按小時或按月）；如果未指定，則預設值為「按小時」。</dd>
<dt>-i, --post-install</dt>
<dd>要下載的後置安裝 Script。</dd>
<dt>-k, --key</dt>
<dd>要新增給 root 使用者的 SSH 金鑰（允許指定多次）。</dd>
<dt>-n, --no-public</dt>
<dd>僅限專用網路。</dd>
<dt>-e, --extra</dt>
<dd>額外選項（允許指定多次）。</dd>
<dt>-t, --test</dt>
<dd>不要實際建立虛擬伺服器。</dd>
<dt>-m, --template</dt>
<dd>預設指令行選項的範本檔。</dd>
<dt>-x, --export</dt>
<dd>將選項匯出至範本檔。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

給定機箱的伺服器訂單選項。
```
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

列出硬體伺服器認證。
```
ibmcloud sl hardware credentials IDENTIFIER
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

取得硬體伺服器的詳細資料。
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-p, --passwords</dt>
<dd>顯示密碼（小心背後有人偷窺！）。</dd>
<dt>-c, --price</dt>
<dd>顯示關聯的價格。</dd>
</dl>

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

編輯硬體伺服器詳細資料。
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN 的主機部分。</dd>
<dt>-D, --domain</dt>
<dd>FQDN 的網域部分。</dd>
<dt>-g, --tag</dt>
<dd>要設定的標籤，或使用空字串以便全部移除。</dd>
<dt>-F, --userfile</dt>
<dd>從檔案讀取使用者資料。</dd>
<dt>-u, --userdata</dt>
<dd>使用者定義的 meta 資料字串。</dd>
<dt>-p, --public-speed</dt>
<dd>公用埠速度，選項包含：0、10、100、1000、10000。</dd>
<dt>-v, --private-speed</dt>
<dd>專用埠速度，選項包含：0、10、100、1000、10000。</dd>
</dl>

## ibmcloud sl hardware list
{: #sl_hardware_list}

列出硬體伺服器。
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>依 CPU 核心數目過濾。</dd>
<dt>-D, --domain</dt>
<dd>依網域過濾。</dd>
<dt>-H, --hostname</dt>
<dd>依主機名稱過濾。</dd>
<dt>-d, --datacenter</dt>
<dd>依資料中心過濾。</dd>
<dt>-m, --memory</dt>
<dd>依記憶體過濾（以 GB 為單位）。</dd>
<dt>-n, --network</dt>
<dd>依網路埠速度過濾（以 Mbps 為單位）。</dd>
<dt>-g, --tag</dt>
<dd>依標籤過濾（允許指定多次）。</dd>
<dt>-p, --public-ip</dt>
<dd>依公用 IP 位址過濾。</dd>
<dt>-v, --private-ip</dt>
<dd>依專用 IP 位址過濾。</dd>
<dt>-o, --order</dt>
<dd>依購買硬體伺服器的訂單 ID 過濾。</dd>
<dt>--owner</dt>
<dd>依擁有者的 ID 過濾。</dd>
<dt>--sortby</dt>
<dd>直欄排序方式，預設值為：hostname，選項包含：id、guid、hostname、domain、public_ip、private_ip、datacenter、status、ipmi_ip、created、created_by。</dd>
<dt>--columns</dt>
<dd>要顯示的直欄，預設值為：id、hostname、domain、public_ip、private_ip、datacenter、status，選項包含：guid、cpu、memory、os、ipmi_ip、created、created_by、tags。</dd>
</dl>

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

將伺服器電源關閉後重開。
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

關閉作用中伺服器的電源。
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

開啟伺服器的電源。
```
ibmcloud sl hardware power-on IDENTIFIER
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

將作用中伺服器重新開機。
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--hard</dt>
<dd>執行正常重新開機。</dd>
<dt>--soft</dt>
<dd>執行正常重新開機。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

在伺服器上重新載入作業系統。
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-i, --postinstall</dt>
<dd>要下載的安裝後置 Script，只有 HTTPS 執行，HTTP 會將檔案留在 /root。</dd>
<dt>-k, --key</dt>
<dd>要新增給 root 使用者的 SSH 金鑰 ID（允許指定多次）。</dd>
<dt>-b, --upgrade-bios</dt>
<dd>升級 BIOS。</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>升級所有硬碟的韌體。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

將伺服器重新開機至救援映像檔。
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

更新伺服器韌體。
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>
